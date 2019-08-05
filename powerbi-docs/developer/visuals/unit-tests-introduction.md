---
title: Yksikkötestin esittely
description: Yksikkötestien kirjoittaminen Power BI:n visualisointien projektille
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 4b16eaad9b541bf6e5d8df49ffda99d9bbd5bbf2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424535"
---
# <a name="tutorial-add-unit-tests-for-power-bi-visual-projects"></a>Opetusohjelma: yksikkötestien lisääminen Power BI:n visualisointien projekteille

Tässä opetusohjelmassa kerrotaan yksikkötestien kirjoittamisen perusteista Power BI:n visualisoinneille.

Tässä opetusohjelmassa kerromme,

* miten käytetään testisuoritinta karma.js ja testauskehystä jasmine.js
* miten käytetään powerbi-visuals-utils-testutils-pakettia
* miten erilaiset harjoitustestit auttavat yksinkertaistamaan yksikköjen testausta Power BI:n visualisoinneille.

## <a name="prerequisites"></a>Edellytykset

* Power BI:n visualisointien projekti käytössä
* määritetty Node.JS-ympäristö

## <a name="install-and-configure-karmajs-and-jasmine"></a>Asenna ja määritä karma.js ja jasmine

Lisää tarvittavat kirjastot package.json-kohteeseen `devDependencies`-osiossa:

```json
"@babel/polyfill": "^7.2.5",
"@types/d3": "5.5.0",
"@types/jasmine": "2.5.37",
"@types/jasmine-jquery": "1.5.28",
"@types/jquery": "2.0.41",
"@types/karma": "3.0.0",
"@types/lodash-es": "4.17.1",
"coveralls": "3.0.2",
"istanbul-instrumenter-loader": "^3.0.1",
"jasmine": "2.5.2",
"jasmine-core": "2.5.2",
"jasmine-jquery": "2.1.1",
"jquery": "3.1.1",
"karma": "3.1.1",
"karma-chrome-launcher": "2.2.0",
"karma-coverage": "1.1.2",
"karma-coverage-istanbul-reporter": "^2.0.4",
"karma-jasmine": "2.0.1",
"karma-junit-reporter": "^1.2.0",
"karma-sourcemap-loader": "^0.3.7",
"karma-typescript": "^3.0.13",
"karma-typescript-preprocessor": "0.4.0",
"karma-webpack": "3.0.5",
"puppeteer": "1.17.0",
"style-loader": "0.23.1",
"ts-loader": "5.3.0",
"ts-node": "7.0.1",
"tslint": "^5.12.0",
"webpack": "4.26.0"
```

Saat lisätietoja paketista alla olevasta kuvauksesta.

Tallenna `package.json` ja suorita komentorivillä `package.json`-kohteen sijainnissa:

```cmd
npm install
```

Paketin hallinta asentaa kaikki uudet paketit, jotka on lisätty kohteeseen `package.json`

Yksikkötestien suorittamista varten on määritettävä testisuoritin ja `webpack`-määritys. Määrityksen malli löytyy täältä

`test.webpack.config.js`-malli:

```typescript
const path = require('path');
const webpack = require("webpack");

module.exports = {
    devtool: 'source-map',
    mode: 'development',
    optimization : {
        concatenateModules: false,
        minimize: false
    },
    module: {
        rules: [
            {
                test: /\.tsx?$/,
                use: 'ts-loader',
                exclude: /node_modules/
            },
            {
                test: /\.json$/,
                loader: 'json-loader'
            },
            {
                test: /\.tsx?$/i,
                enforce: 'post',
                include: /(src)/,
                exclude: /(node_modules|resources\/js\/vendor)/,
                loader: 'istanbul-instrumenter-loader',
                options: { esModules: true }
            },
            {
                test: /\.less$/,
                use: [
                    {
                        loader: 'style-loader'
                    },
                    {
                        loader: 'css-loader'
                    },
                    {
                        loader: 'less-loader',
                        options: {
                            paths: [path.resolve(__dirname, 'node_modules')]
                        }
                    }
                ]
            }
        ]
    },
    externals: {
        "powerbi-visuals-api": '{}'
    },
    resolve: {
        extensions: ['.tsx', '.ts', '.js', '.css']
    },
    output: {
        path: path.resolve(__dirname, ".tmp/test")
    },
    plugins: [
        new webpack.ProvidePlugin({
            'powerbi-visuals-api': null
        })
    ]
};
```

`karma.conf.ts`-malli

```typescript
"use strict";

const webpackConfig = require("./test.webpack.config.js");
const tsconfig = require("./test.tsconfig.json");
const path = require("path");

const testRecursivePath = "test/visualTest.ts";
const srcOriginalRecursivePath = "src/**/*.ts";
const coverageFolder = "coverage";

process.env.CHROME_BIN = require("puppeteer").executablePath();

import { Config, ConfigOptions } from "karma";

module.exports = (config: Config) => {
    config.set(<ConfigOptions>{
        mode: "development",
        browserNoActivityTimeout: 100000,
        browsers: ["ChromeHeadless"], // or Chrome to use locally installed Chrome browser
        colors: true,
        frameworks: ["jasmine"],
        reporters: [
            "progress",
            "junit",
            "coverage-istanbul"
        ],
        junitReporter: {
            outputDir: path.join(__dirname, coverageFolder),
            outputFile: "TESTS-report.xml",
            useBrowserName: false
        },
        singleRun: true,
        plugins: [
            "karma-coverage",
            "karma-typescript",
            "karma-webpack",
            "karma-jasmine",
            "karma-sourcemap-loader",
            "karma-chrome-launcher",
            "karma-junit-reporter",
            "karma-coverage-istanbul-reporter"
        ],
        files: [
            "node_modules/jquery/dist/jquery.min.js",
            "node_modules/jasmine-jquery/lib/jasmine-jquery.js",
            {
                pattern: './capabilities.json',
                watched: false,
                served: true,
                included: false
            },
            testRecursivePath,
            {
                pattern: srcOriginalRecursivePath,
                included: false,
                served: true
            }
        ],
        preprocessors: {
            [testRecursivePath]: ["webpack", "coverage"]
        },
        typescriptPreprocessor: {
            options: tsconfig.compilerOptions
        },
        coverageIstanbulReporter: {
            reports: ["html", "lcovonly", "text-summary", "cobertura"],
            dir: path.join(__dirname, coverageFolder),
            'report-config': {
                html: {
                    subdir: 'html-report'
                }
            },
            combineBrowserReports: true,
            fixWebpackSourcePaths: true,
            verbose: false
        },
        coverageReporter: {
            dir: path.join(__dirname, coverageFolder),
            reporters: [
                // reporters not supporting the `file` property
                { type: 'html', subdir: 'html-report' },
                { type: 'lcov', subdir: 'lcov' },
                // reporters supporting the `file` property, use `subdir` to directly
                // output them in the `dir` directory
                { type: 'cobertura', subdir: '.', file: 'cobertura-coverage.xml' },
                { type: 'lcovonly', subdir: '.', file: 'report-lcovonly.txt' },
                { type: 'text-summary', subdir: '.', file: 'text-summary.txt' },
            ]
        },
        mime: {
            "text/x-typescript": ["ts", "tsx"]
        },
        webpack: webpackConfig,
        webpackMiddleware: {
            stats: "errors-only"
        }
    });
};
```

Voit muokata tätä määritystä tarvittaessa.

Kohteen `karma.conf.js` asetuksia:

* `recursivePathToTests`-muuttuja etsii testien koodin paikan.

* `srcRecursivePath`-muuttuja etsii JS-tulostekoodin kääntämisen jälkeen.

* `srcCssRecursivePath`-muuttuja etsii CSS-tulosteen sen jälkeen, kun se on kääntänyt vähemmän tiedostoa tyyleillä.

* `srcOriginalRecursivePath`-muuttuja etsii visualisoinnin lähdekoodin.

* `coverageFolder`-muuttuja määrittää paikan, johon kattavuusraportti luodaan.

Määrityksen ominaisuuksia:

* `singleRun: true` – testaa suorituksen CI-järjestelmässä. Se riittää yhden kerran.
Voit muuttaa arvoon `false` testien virheenkorjausta varten. Karma pitää selaimen käynnissä, ja sen avulla voit käyttää konsolia virheenkorjausta varten.

* `files: [...]` – tässä matriisissa voit valita tiedostoja, jotka ladataan selaimeen.
Yleensä ne ovat lähdetiedostoja, testitapauksia, kirjastoja (jasmine, testin apuohjelmat). Voit halutessasi lisätä luetteloon myös muita tiedostoja.

* `preprocessors` – tässä määritysosassa voit määrittää toimintoja, jotka suoritetaan ennen yksikkötestien suorittamista. Niitä voivat olla esimerkiksi typescriptin esikääntäminen JS-muotoon, lähdekarttatiedostojen valmisteleminen ja koodikattavuusraportin luominen. Voit poistaa kohdan `coverage` käytöstä testien virheenkorjausta varten. Kattavuus luo lisäkoodin testikattavuuden tarkistuskoodille, ja se vaikeuttaa virheenkorjaustestejä.

**Kaikkien määritysten kuvauksen löytyvät karma.js-[dokumentaatiosta](https://karma-runner.github.io/1.0/config/configuration-file.html)**

Voit helpottaa käyttöä lisäämällä testikomennon kohteeseen `scripts`:

```json
{
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "typings":"node node_modules/typings/dist/bin.js i",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "pretest": "pbiviz package --resources --no-minify --no-pbiviz --no-plugin",
        "test": "karma start"
    }
    ...
}
```

Olet siis valmis aloittamaan yksikkötestien kirjoittamisen.

## <a name="simple-unit-test-for-check-dom-element-of-the-visual"></a>Yksinkertainen yksikkötesti visualisoinnin DOM-elementin tarkistamiseen

Visualisoinnin testaamista varten on luotava visualisoinnin esiintymä.

### <a name="creating-visual-instance-builder"></a>Visualisoinnin esiintymän muodostimen luominen

Lisää `visualBuilder.ts`-tiedosto `test`-kansioon käyttäen seuraavaa koodia:

```typescript
import {
    VisualBuilderBase
} from "powerbi-visuals-utils-testutils";

import {
    BarChart as VisualClass
} from "../src/visual";

import  powerbi from "powerbi-visuals-api";
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class BarChartBuilder extends VisualBuilderBase<VisualClass> {
    constructor(width: number, height: number) {
        super(width, height);
    }

    protected build(options: VisualConstructorOptions) {
        return new VisualClass(options);
    }

    public get mainElement() {
        return this.element.children("svg.barChart");
    }
}
```

Visualisoinnin esiintymän luonnissa on käytettävissä `build`-menetelmä. `mainElement` on hakumenetelmä, joka palauttaa DOM-pääelementin esiintymän visualisointiin. Getter-elementti on valinnainen, mutta se tekee yksikkötestin kirjoittamisesta helpompaa.

Käytössämme on siis visualisoinnin esiintymän muodostin. Kirjoitetaanpa sitten testitapaus. Testitapauksen avulla tarkistetaan luodut SVG-elementit, kun visualisointi näytetään.

### <a name="creating-typescript-file-to-write-test-cases"></a>Typescript-tiedoston luominen testitapausten kirjoittamista varten

Lisää testitapauksia varten `visualTest.ts`-tiedosto käyttäen seuraavia koodeja:

```typescript
import powerbi from "powerbi-visuals-api";

import { BarChartBuilder } from "./VisualBuilder";

import {
    BarChart as VisualClass
} from "../src/visual";

import VisualBuilder = powerbi.extensibility.visual.test.BarChartBuilder;

describe("BarChart", () => {
    let visualBuilder: VisualBuilder;
    let dataView: DataView;

    beforeEach(() => {
        visualBuilder = new VisualBuilder(500, 500);
    });

    it("root DOM element is created", () => {
        expect(visualBuilder.mainElement).toBeInDOM();
    });
});
```

Useita menetelmiä kutsutaan.

* [`describe`](https://jasmine.github.io/api/2.6/global.html#describe)-menetelmä kuvaa testitapausta. Jasmine-kehyksen yhteydessä kutsutaan usein ominaisuuspaketiksi tai -ryhmäksi.

* `beforeEach`-menetelmä kutsutaan ennen kutakin `it`-menetelmän kutsua, joka on määritetty [`describe`](https://jasmine.github.io/api/2.6/global.html#beforeEach)-menetelmässä.

* `it` määrittää yksittäisen ominaisuuden. [`it`](https://jasmine.github.io/api/2.6/global.html#it)-menetelmän tulee sisältää vähintään yksi `expectations`.

* [`expect`](https://jasmine.github.io/api/2.6/global.html#expect) – menetelmä luo odotukset ominaisuudelle. Menetelmä onnistuu, jos kaikki odotukset läpäisevät ilman virheitä.

* `toBeInDOM` – se on yksi matcher-menetelmistä. Tietoja on olemassa -matchereista on jasmine-kehyksen [dokumentaatiossa](https://jasmine.github.io/api/2.6/matchers.html).

**Lue lisää jasmine-kehyksestä virallisesta [dokumentaatiosta](https://jasmine.github.io/).**

Sen jälkeen voit suorittaa yksikkötestin kirjoittamalla komennon komentorivityökaluun.

Tämä testi tarkistaa, että visualisointien SVG-pääelementti luodaan.

### <a name="launch-unit-tests"></a>Yksikkötestien käynnistys

Voit suorittaa yksikkötestin kirjoittamalla tämän komennon komentorivityökaluun.

```cmd
npm run test
```

`karma.js` käynnistää Chrome-selaimen ja suorittaa testitapauksen.

![KarmaJS käynnistettynä Chromessa](./media/karmajs-chrome.png)

> [!NOTE]
> Google Chrome on asennettava paikallisesti.

Komentoriviltä saat seuraavan tulosteen:

```cmd
> karma start

23 05 2017 12:24:26.842:WARN [watcher]: Pattern "E:/WORKSPACE/PowerBI/PowerBI-visuals-sampleBarChart/data/*.csv" does not match any file.
23 05 2017 12:24:30.836:WARN [karma]: No captured browser, open http://localhost:9876/
23 05 2017 12:24:30.849:INFO [karma]: Karma v1.3.0 server started at http://localhost:9876/
23 05 2017 12:24:30.850:INFO [launcher]: Launching browser Chrome with unlimited concurrency
23 05 2017 12:24:31.059:INFO [launcher]: Starting browser Chrome
23 05 2017 12:24:33.160:INFO [Chrome 58.0.3029 (Windows 10 0.0.0)]: Connected on socket /#2meR6hjXFmsE_fjiAAAA with id 5875251
Chrome 58.0.3029 (Windows 10 0.0.0): Executed 1 of 1 SUCCESS (0.194 secs / 0.011 secs)

=============================== Coverage summary ===============================
Statements   : 27.43% ( 65/237 )
Branches     : 19.84% ( 25/126 )
Functions    : 43.86% ( 25/57 )
Lines        : 20.85% ( 44/211 )
================================================================================
```

### <a name="how-to-add-static-data-for-unit-tests"></a>Staattisten tietojen lisääminen yksikkötesteihin

Luo `visualData.ts`-tiedosto `test`-kansioon. Seuraavilla koodeilla:

```typescript
import powerbi from "powerbi-visuals-api";
import DataView = powerbi.DataView;

import {
    testDataViewBuilder,
    getRandomNumbers
} from "powerbi-visuals-utils-testutils";

export class SampleBarChartDataBuilder extends TestDataViewBuilder {
    public static CategoryColumn: string = "category";
    public static MeasureColumn: string = "measure";

    public constructor() {
        super();
        ...
    }

    public getDataView(columnNames?: string[]): DataView {
        let dateView: any = this.createCategoricalDataViewBuilder([
            ...
        ],
        [
            ...
        ], columnNames).build();

        // there's client side computed maxValue
        let maxLocal = 0;
        this.valuesMeasure.forEach((item) => {
                if (item > maxLocal) {
                    maxLocal = item;
                }
        });
        (<any>dataView).categorical.values[0].maxLocal = maxLocal;
    }
}
```

`SampleBarChartDataBuilder`-luokka laajentaa kohteen `TestDataViewBuilder` ja toteuttaa abstraktin menetelmän `getDataView`.

Kun sijoitat tietoja tietokenttäsäilöihin, Power BI tuottaa tietoihin perustuvan luokittaisen `dataview`-objektin.

![Arkistoidut säilöt](./media/fields-buckets.png)

Yksikkötesteissä sinulla ei ole Power BI:n keskeisiä funktioita sen toistamiseksi. Sinun on kuitenkin yhdistettävä staattiset tietosi luokittaiseksi `dataview`-kohteeksi. `TestDataViewBuilder`-luokka auttaa siinä.

[Lue lisätietoja DataViewMappings-määrityksistä](https://github.com/Microsoft/PowerBI-visuals/blob/master/Capabilities/DataViewMappings.md)

`getDataView`-menetelmässä kutsut `createCategoricalDataViewBuilder`-menetelmän tietojesi kanssa.

`sampleBarChart`-visualisoinnin [capabilities.json](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/capabilities.json#L2)-tiedostossa käytettävissä on dataRoles- ja dataViewMapping-objektit:

```json
"dataRoles": [
    {
        "displayName": "Category Data",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Measure Data",
        "name": "measure",
        "kind": "Measure"
    }
],
"dataViewMappings": [
    {
        "conditions": [
            {
                "category": {
                    "max": 1
                },
                "measure": {
                    "max": 1
                }
            }
        ],
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "select": [
                    {
                        "bind": {
                            "to": "measure"
                        }
                    }
                ]
            }
        }
    }
],
```

Jotta voit luoda saman yhdistämismäärityksen, sinun on määritettävä seuraavat parametrit `createCategoricalDataViewBuilder`-menetelmälle:

```typescript
([
    {
        source: {
            displayName: "Category",
            queryName: SampleBarChartData.ColumnCategory,
            type: ValueType.fromDescriptor({ text: true }),
            roles: {
                Category: true
            },
        },
        values: this.valuesCategory
    }
],
[
    {
        source: {
            displayName: "Measure",
            isMeasure: true,
            queryName: SampleBarChartData.MeasureColumn,
            type: ValueType.fromDescriptor({ numeric: true }),
            roles: {
                Measure: true
            },
        },
        values: this.valuesMeasure
    },
], columnNames)
```

Jossa `this.valuesCategory` luokkamatriisi.

```ts
public valuesCategory: string[] = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"];
```

Ja `this.valuesMeasure` mittamatriisi kullekin luokalle. Esimerkki:

```ts
public valuesMeasure: number[] = [742731.43, 162066.43, 283085.78, 300263.49, 376074.57, 814724.34, 570921.34];
```

Nyt voit käyttää `SampleBarChartDataBuilder`-luokkaa yksikkötestissäsi.

`ValueType`-luokka määritetty `powerbi-visuals-utils-testutils`-paketissa. Ja `createCategoricalDataViewBuilder`-menetelmä edellyttää `lodash`-kirjastoa.

Lisää nämä paketit riippuvuuksiin.

`package.json`-kohdassa osassa `devDependencies`

```json
"lodash-es": "4.17.1",
"powerbi-visuals-utils-testutils": "2.2.0"
```

Kutsu

```cmd
npm install
```

asentaaksesi `lodash-es`-kirjaston.

Nyt voit suorittaa yksikkötestin uudelleen. Sinun pitää saada tämä tuloste

```cmd
> karma start

23 05 2017 16:19:54.318:WARN [watcher]: Pattern "E:/WORKSPACE/PowerBI/PowerBI-visuals-sampleBarChart/data/*.csv" does not match any file.
23 05 2017 16:19:58.333:WARN [karma]: No captured browser, open http://localhost:9876/
23 05 2017 16:19:58.346:INFO [karma]: Karma v1.3.0 server started at http://localhost:9876/
23 05 2017 16:19:58.346:INFO [launcher]: Launching browser Chrome with unlimited concurrency
23 05 2017 16:19:58.394:INFO [launcher]: Starting browser Chrome
23 05 2017 16:19:59.873:INFO [Chrome 58.0.3029 (Windows 10 0.0.0)]: Connected on socket /#NcNTAGH9hWfGMCuEAAAA with id 3551106
Chrome 58.0.3029 (Windows 10 0.0.0): Executed 1 of 1 SUCCESS (1.266 secs / 1.052 secs)

=============================== Coverage summary ===============================
Statements   : 56.72% ( 135/238 )
Branches     : 32.54% ( 41/126 )
Functions    : 66.67% ( 38/57 )
Lines        : 52.83% ( 112/212 )
================================================================================
```

Lisäksi sinun on nähtävä käynnistetty Chrome-selain visualisointisi kanssa.

![UT-käynnistykset Chromessa](./media/karmajs-chrome-ut-runned.png)

Huomio kattavuuden yhteenveto on lisääntynyt. Avaa `coverage\index.html` saadaksesi lisätietoja nykyisestä koodin kattavuudesta

![UT-kattavuuden indeksi](./media/code-coverage-index.png)

Tai `src`-kansion vaikutusalueella

![Src-kansion kattavuus](./media/code-coverage-src-folder.png)

Voit tarkastella lähdekoodia tiedoston vaikutusalueella. `Coverage`-apuohjelmat merkitsevät rivin taustan punaiseksi, jos koodia ei suoritettu yksikkötestien suorittamisen aikana.

![Visual.ts-tiedoston koodin kattavuus](./media/code-coverage-visual-src.png)

> [!IMPORTANT]
> Koodin kattavuus ei kuitenkaan tarkoita, että käytettävissäsi on hyvä toimintojen kattavuus visualisoinnissa. Yksi yksinkertainen yksikkötesti kattoi yli 96 prosenttia kohteessa `src\visual.ts`.

## <a name="next-steps"></a>Seuraavat vaiheet

Kun visualisointi on valmis, voit lähettää visualisoinnin julkaisuun.

[Lue lisää visualisointien julkaisemisesta Appsourceen](../office-store.md)
