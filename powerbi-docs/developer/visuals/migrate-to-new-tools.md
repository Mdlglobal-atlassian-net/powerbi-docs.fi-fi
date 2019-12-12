---
title: Siirtyminen powerbi-visuals-tools-versioon 3.x
description: Uuden powerbi-visuals-tools-version käytön aloittaminen
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 245475feeb43ee544117aaa54969f2de1e207cd5
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74696278"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-3xx"></a>Siirtyminen uuteen powerbi-visuals-tools-versioon 3.x.x

Versiosta 3 alkaen Power BI -visualisointien työkalut käyttävät Webpackia mukautettujen visualisointien luomiseen.
Uusi versio tarjoaa kehittäjille monia uusia mahdollisuuksia visualisointien luomiseen:

* TypeScript v3.x.x oletusarvon mukaan. TypeScript 1.5 -versiosta alkaen nimikkeistöä on muutettu. [Lue lisää TypeScript-moduuleista](https://www.typescriptlang.org/docs/handbook/modules.html).

* ES6-moduuleja tuetaan. [externalJS](migrate-to-new-tools.md#fix-loading-external-libraries)-moduuleita ei tarvitse enää käyttää, voit käyttää niiden sijasta ES6-tuonteja.

* Uusia versioita [D3v5](https://d3js.org/):stä ja muista ES6-moduulipohjaisista kirjastoista tuetaan.

* Paketin koko on pienempi. Webpack poistaa käyttämättömän koodin [puunravistelulla](https://webpack.js.org/guides/tree-shaking/). Se vähentää JS-koodia, minkä seurauksena saat paremman suorituskyvyn visuaalisen lataamisen aikana.

* Ohjelmointirajapinnan suorituskykyä on parannettu.

* Globaloize.js-kirjasto [on integroitu](migrate-to-new-tools.md#remove-globalizejs-library) formatting-utils-kirjastoon.

* Työkalut käyttävät [webpack-bundle-analyzeria](https://github.com/webpack-contrib/webpack-bundle-analyzer) visualisoinnin koodikannan näyttämiseen.

Kaikki Power BI -visualisointien työkalujen uuteen versioon siirtymisen vaiheet on kuvattu alla.

## <a name="backward-compatibility"></a>Yhteensopivuus aikaisempien versioiden kanssa

Uudet työkalut säilyttävät yhteensopivuuden aiempien versioiden visualisointien koodikannan kanssa, mutta ne saattavat vaatia lisämuutoksia ulkoisten kirjastojen lataamiseen.

Moduulijärjestelmiä tukevat libs-moduulit tuodaan Webpack-moduuleina. Kaikki muut libs-moduulit ja visual source -koodit kääritään yhdeksi moduuliksi.

Aikaisemmissa pbiviz-työkaluissa käytetyt yleiset muuttujat, kuten JQuery ja Lodash, ovat nyt vanhentuneita. Tämä tarkoittaa sitä, että jos vanha visuaalinen koodi välittää globaaleilla muuttujilla, visualisointi voidaan tässä tapauksessa murtaa.

Power BI -visualisointien työkalujen aiempaa versiota tarvitaan Visual-luokan määrittämiseen moduulissa `powerbi.extensibility.visual`.

## <a name="how-to-install-powerbi-visuals-tools"></a>Powerbi-visuals-tools-työkalujen asentaminen

Uusi työkalusarja voidaan asentaa suorittamalla komento

```cmd
npm install -g powerbi-visuals-tools
```

Esimerkki sampleBarChart-visualisoinnista ja vastaavista [muutoksista](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L16) kohteessa `package.json`:

```json
{
    "name": "visual",
    "version": "1.2.3",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
      "@types/d3": "5.0.0",
      "d3": "5.5.0",
      "powerbi-visuals-tools": "^3.1.0",
      "tslint": "^4.4.2",
      "tslint-microsoft-contrib": "^4.0.0"
    }
}
```

## <a name="how-to-install-power-bi-custom-visuals-api"></a>Power BI Custom Visuals -ohjelmointirajapinnan asentaminen

Uusi powerbi-visual-tools-versio ei sisällä kaikkia ohjelmointirajapintojen versioita. Sen sijaan kehittäjän tulee asentaa tietty versio paketista [`powerbi-visuals-api`](https://www.npmjs.com/package/powerbi-visuals-api). Paketin versio vastaa Power BI:n mukautettujen visualisointien ohjelmointirajapinnan versiota, ja se tarjoaa kaikki Power BI:n mukautettujen visualisointien ohjelmointirajapinnan tyyppimääritykset.

Lisää `powerbi-visuals-api` projektin riippuvuuksiin suorittamalla komento `npm install --save-dev powerbi-visuals-api`.
Poista lisäksi linkki vanhoihin ohjelmointirajapinnan tyyppimäärityksiin. Koska Webpack sisällyttää automaattisesti kohteen `powerbi-visuals-api` tyypit. Vastaavat muutokset ovat [tällä](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L14) rivillä kohteessa `package.json`.

## <a name="update-tsconfigjson"></a>Päivitä `tsconfig.json`

Jos haluat käyttää ulkoisia moduuleja, vaihda `out`-asetuksen tilalle `outDir`.
`"outDir": "./.tmp/build/",` sen sijaan `"out": "./.tmp/build/visual.js",`.

Sitä tarvitaan, koska TypeScript-tiedostot käännetään JavaScript-tiedostoiksi itsenäisesti. Siksi visual.js-tiedostoa ei enää tarvitse määrittää tulosteena.

Voit myös muuttaa `target`-asetukseksi `ES6`, jos haluat käyttää tulosteena modernia JavaScriptiä. [Se on valinnaista](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/tsconfig.json#L6).

## <a name="update-custom-visuals-utils"></a>Mukautetut visualisoinnit -apuohjelman päivittäminen

Jos käytät jotakin powerbi-visuals-utils https://www.npmjs.com/search?q=powerbi-visuals-utils) -kohdetta, päivitä nekin uusimpaan versioon.

Suorita komento `npm install powerbi-visuals-utils-<UTILNAME> --save`. (Esim. `npm install powerbi-visuals-utils-dataviewutils --save` ), jos haluat uuden version TypeScript-kohteen ulkoisilla moduuleilla.

Esimerkki on MekkoChart-[säilössä](https://github.com/Microsoft/powerbi-visuals-mekkochart).
Tämä visualisointi käyttää kaikkia apuohjelmia.

## <a name="remove-globalizejs-library"></a>Globalelize.js-kirjaston poistaminen

Uusi [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) -versio sisältää valmiina globalize.js-kohteen.
Tätä kirjastoa ei tarvitse sisällyttää manuaalisesti projektiin.
Kaikki vaaditut lokalisoinnit lisätään lopulliseen pakettiin automaattisesti.

## <a name="fix-loading-external-libraries"></a>Korjaa ulkoisten kirjastojen lataaminen

Sisällytä sen sijaan uusi JS-tiedosto libsin jälkeen `pbiviz.json`-kohteen `externalJS`-matriisissa. Esimerkki:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

Tuo libs lähteessä. Esimerkki – `lodash-es`:

```JS
import * as _ from "lodash-es";
```

missä `_` on kirjaston `lodash` yleinen muuttuja.

## <a name="changes-in-the-visuals-sources"></a>Visualisointilähteiden muutokset

Tärkein muutos on sisäisten moduulien muuntaminen ulkoisiksi moduuleiksi, koska ulkoisia moduuleja ei voi käyttää sisäisten moduulien sisällä.

Muutokset kuvailevat muokkauksia, jotka on otettu käyttöön palkkikaaviomallissa

Seuraavassa ovat muutosten yksityiskohtaiset kuvaukset:

1. Poista kaikki moduulien määritykset kustakin [lähdekoodin](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L153) tiedostosta

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Tuo Power BI:n mukautetun visualisoinnin ohjelmointirajapinnan määritelmät](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L2).

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. [Tuo](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L12-L23) tarvittavat käyttöliittymät tai luokat sisäisestä `powerbi`-moduulista.

    ```typescript
    import PrimitiveValue = powerbi.PrimitiveValue; 
    import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions; 
    import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions; 
    import IVisualHost = powerbi.extensibility.visual.IVisualHost; 
    import IColorPalette = powerbi.extensibility.IColorPalette; 
    import IVisual = powerbi.extensibility.visual.IVisual; 
    import VisualObjectInstance = powerbi.VisualObjectInstance; 
    import VisualObjectInstanceEnumeration = powerbi.VisualObjectInstanceEnumeration; 
    import EnumerateVisualObjectInstancesOptions = powerbi.EnumerateVisualObjectInstancesOptions; 
    import Fill = powerbi.Fill; 
    import VisualTooltipDataItem = powerbi.extensibility.VisualTooltipDataItem; 
    import ISelectionManager = powerbi.extensibility.ISelectionManager; 
    ```

4. [Tuo](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L1) D3.js-kirjasto

    ```typescript
    import * as d3 from "d3";
    ```

    Tai tuo vain vaaditut d3-kirjastomoduulit

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [Tuo](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L4-L10) visualisointiprojektissa määritetyt apuohjelmat, luokat, liittymät päälähdetiedostoon

    ```typescript
    import { getLocalizedString } from "./localization/localizationHelper";
    import { getValue, getCategoricalObjectValue } from "./objectEnumerationUtility";
    import {
        ITooltipServiceWrapper,
        TooltipEventArgs,
        createTooltipServiceWrapper
    } from "./tooltipServiceWrapper";
    ```

### <a name="import-css-styles"></a>Tuo CSS-tyylit

Työkalujen uuden version avulla kehittäjät voivat tuoda CSS, LESS -tyylin suoraan TypeScript-koodiin.

Kääntäjä siis ohittaa aiemmin käytetyn [tyyliosion](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L22).

Jos haluat käyttää omaa tyylisivua, avaa main ts -tiedosto ja lisää seuraava rivi:  

```typescript
import "./../style/visual.less";
```  

CSS, LESS -tyylit käännetään automaattisesti.  

### <a name="externaljs-section-in-pbivizjson"></a>externalJS-osa kohteessa pbiviz.json

Työkalut [eivät edellytä](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L20) `externalJS`-luetteloa visualisointipaketin lataamiseen. Webpack sisältää kaikki tuodut lib-tiedot.

**Pbivi.json-kohteen externnalJS-osan tulee olla tyhjä.**

Kutsumalla tyypillisiä komentoja voit `npm run package` luoda visuaalisen paketin tai `npm run start` käynnistää kehityspalvelimen.

## <a name="updating-d3js-library-to-version-5"></a>D3.js-kirjaston päivittäminen versioon 5

Uusilla työkaluilla voit aloittaa D3.js-kirjaston uuden version käyttämisen.

Kutsukomento, joilla D3 päivitetään visualisointiprojektissa

`npm install --save d3@5` asentaa uuden D3.js-kirjaston.

`npm install --save-dev @types/d3@5` asentaa D3.js-kirjaston uudet tyyppimääritykset.

Useat muutokset saattavat aiheuttaa virheitä muissa komponenteissa, joten muokkaa koodiasi käyttämään uutta D3.js-kirjastoa.

1. Liittymäksi `d3.Selection<T>` [vaihdettiin](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157) `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`

2. Et voi käyttää useita määritteitä yhdellä `attr`-metodin kutsulla. Jokainen määrite [tulee välittää](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278) `attr`-metodin eri kutsuissa. Asia toimii [samoin](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247) myös `style`-metodille.

3. D3.js-kirjaston v4-versiossa esitellään uusi merge-metodi. Tämän metodin avulla yhdistetään enter- ja update-valinnat tietojen yhdistämisen jälkeen. [Kutsu merge-metodia](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272), jotta d3-kirjastoa käytetään oikein.

[Lue lisää](https://github.com/d3/d3/blob/master/CHANGES.md) D3.js-kirjaston muutoksista.

## <a name="babel"></a>Babel

Versiosta 3.1 alkaen työkalut käyttävät Babel-työkalua uuden modernin JS-koodin kääntämiseen vanhaan ES5-muotoon, joten useita eri selaimia tuetaan.

Tämä asetus on oletusarvoisesti käytössä, mutta paketti [`@babel/polyfill`](https://babeljs.io/docs/en/babel-polyfill) on tuotava manuaalisesti.

Asenna paketti antamalla komento

`npm install --save @babel/polyfill`

ja tuo paketti visuaalisen koodin alkupisteeseen (yleensä src/visual.ts-tiedosto):

`import "@babel/polyfill";`

Lue lisätietoa Babel-työkalusta [dokumentaatiosta](https://babeljs.io/docs/en/).

Suorita lopuksi [webpack-visualizer](https://github.com/chrisbateman/webpack-visualizer), niin saat näkyviin visualisoinnin koodiversion.  

![Visualisoinnin koodin tilastotiedot](./media/webpack-stats.png)
