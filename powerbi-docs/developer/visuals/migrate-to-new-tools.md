---
title: Siirtyminen powerbi-visuals-tools-versioon 3.x
description: Uuden powerbi-visuals-tools-version käytön aloittaminen
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: d9af0ab870732990201ab3478d71fdafa9e13439
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/04/2020
ms.locfileid: "76818820"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-version-3x"></a>Siirry uuteen powerbi-visuals-tools-versioon 3.*x*

Versiosta 3 alkaen Power BI -visualisointityökalut (powerbi-visuals-tools tai `pbiviz`) luovat mukautetut visualisoinnit Webpackilla.
Uusi versio tarjoaa kehittäjille monia parannuksia visualisointien luomiseen:

- TypeScript-versio 3.*x* on oletusarvoisesti käytössä. TypeScript 1.5 -versiosta alkaen nimikkeistöä on muutettu. [Lue lisää TypeScript-moduuleista](https://www.typescriptlang.org/docs/handbook/modules.html).

- ECMAScript 6 (ES6) -moduuleja tuetaan. Voit nyt käyttää ES6-tuonteja [externalJS:n](migrate-to-new-tools.md#configure-loading-of-external-libraries) sijaan.

- Uusia versioita [D3v5](https://d3js.org/):stä (Data-Driven Documents) ja muista ES6-moduulipohjaisista kirjastoista tuetaan.

- Paketin koko on pienempi. Webpack poistaa käyttämättömän koodin [puunravistelulla](https://webpack.js.org/guides/tree-shaking/). Tämä vähentää JavaScript-koodia ja tarjoaa paremman suorituskyvyn visualisointien lataamisessa.

- Ohjelmointirajapinnan suorituskykyä on parannettu.

- Globalize.js-kirjasto [on integroitu](migrate-to-new-tools.md#remove-the- globalizejs-library) FormattingUtilsiin.

- Power BI -visualisointityökalut näyttävät visualisoinnin koodikannan [webpack-bundle-analyzerilla](https://github.com/webpack-contrib/webpack-bundle-analyzer).

Tämä artikkeli kuvaa kaikki Power BI -visualisointien työkalujen uuteen versioon siirtymisen vaiheet.

## <a name="backward-compatibility"></a>Yhteensopivuus aikaisempien versioiden kanssa

Uudet työkalut säilyttävät yhteensopivuuden aiempien versioiden visualisointien koodikannan kanssa, mutta ne saattavat vaatia lisämuutoksia ulkoisten kirjastojen lataamiseen.

Moduulijärjestelmiä tukevat kirjastot tuodaan Webpack-moduuleina. Kaikki muut kirjastot ja visualisointien lähdekoodit kerätään yhdeksi moduuliksi.

Aikaisemmissa Power BI -visualisointityökaluissa käytetyt yleiset muuttujat ovat nyt vanhentuneita (esimerkiksi JQuery ja Lodash). Jos visualisointisi vanha koodi käyttää yleisiä muuttujia, se ei todennäköisesti toimi uusilla työkaluilla.

Tarvitset Power BI -visualisointityökalujen vanhemman versio, jos haluat määrittää visualisointiluokan moduulissa `powerbi.extensibility.visual`. Työkalujen uudella versiolla sinun täytyy sen sijaan määrittää visualisointiluokka TypeScript-päätiedostossa (.ts). Yleensä tämä tiedosto on `src/visual.ts`.

## <a name="install-powerbi-visuals-tools"></a>Powerbi-visuals-tools-työkalujen asentaminen

Asenna uudet työkalut suorittamalla tämä komento:

```cmd
npm install -g powerbi-visuals-tools
```

Seuraava koodi on peräisin tiedostosta `package.json` [sampleBarChart-visualisointisäilöstä](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L15) sen jälkeen, kun visualisointiprojekti on päivitetty toimimaan uusien työkalujen kanssa:

```json
{
    "name": "visual",
    "version": "3.0.0",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "package": "pbiviz package",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
        "@types/d3": "5.7.2",
        "d3": "5.12.0",
        "powerbi-visuals-api": "^2.6.1",
        "powerbi-visuals-tools": "^3.1.7",
        "powerbi-visuals-utils-dataviewutils": "^2.2.1",
        "powerbi-visuals-utils-formattingutils": "^4.4.2",
        "powerbi-visuals-utils-interactivityutils": "^5.6.0",
        "powerbi-visuals-utils-tooltiputils": "^2.3.1",
        "tslint": "^5.20.0",
        "tslint-microsoft-contrib": "^6.2.0"
    }
}
```

## <a name="install-the-power-bi-custom-visuals-api"></a>Power BI:n mukautettujen visualisointien ohjelmointirajapinnan asentaminen

Uusi powerbi-visual-tools-versio ei sisällä kaikkia ohjelmointirajapintojen versioita. Sinun täytyy sen sijaan asentaa tietty versio [powerbi-visuals-api](https://www.npmjs.com/package/powerbi-visuals-api)-paketista. Valitse se paketin versio, joka vastaa Power BI:n mukautettujen visualisointien ohjelmointirajapintaversiotasi. Paketti tarjoaa kaikki tyyppimääritelmät Power BI:n mukautettujen visualisointien ohjelmointirajapinnalle.

Lisää `powerbi-visuals-api` projektiriippuvuuksiisi suorittamalla tämä komento:

```cmd
npm install --save-dev powerbi-visuals-api
```

Poista myös kaikki linkit vanhoihin ohjelmointirajapintatyyppimääritelmiin, koska Webpack sisällyttää automaattisesti tyypit kohteesta `powerbi-visuals-api`. Vastaavat muutokset ovat tiedostoissa [package.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L14) ja [tsconfig.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L14).

## <a name="update-tsconfigjson"></a>tsconfig.json-tiedoston päivittäminen

Jos haluat käyttää ulkoisia moduuleja, vaihda asetus `out` asetukseen `outDir`. Ota esimerkiksi käyttöön `"outDir": "./.tmp/build/",` (ei `"out": "./.tmp/build/visual.js",`).

Tämä muutos vaaditaan, koska TypeScript-tiedostot käännetään JavaScript-tiedostoiksi itsenäisesti. Siksi visual.js-tiedostoa ei enää tarvitse määrittää tuloksena.

Voit myös muuttaa asetuksen `target` asetukseksi `ES6`, jos haluat käyttää tuloksena nykyaikaista JavaScriptia. Tämä muutos on [vapaaehtoinen](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L7).

## <a name="update-custom-visuals-utilities"></a>Mukautetut visualisoinnit -apuohjelman päivittäminen

Jos käytät joitain [powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils)-paketteja, päivitä nekin uusimpaan versioon. Voit tehdä tämän suorittamalla seuraavan komennon:

```cmd
npm install powerbi-visuals-utils-<UTILNAME> --save
```

Jos haluat esimerkiksi uuden version TypeScriptin ulkoisilla moduuleilla, suorita seuraava komento: 

```cmd
npm install powerbi-visuals-utils-dataviewutils --save
```

Jos haluat visualisoinnin, joka käyttää kaikkia `powerbi-visuals-utils`-paketteja, tutustu [MekkoChart-säilöön](https://github.com/Microsoft/powerbi-visuals-mekkochart).

## <a name="remove-the-globalizejs-library"></a>Globalelize.js-kirjaston poistaminen

Uusi [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) sisältää valmiina globalize.js-kirjaston. Sinun ei siis tarvitse sisällyttää sitä projektiin manuaalisesti. Kaikki vaaditut lokalisoinnit lisätään lopulliseen pakettiin automaattisesti.

## <a name="configure-loading-of-external-libraries"></a>Ulkoisten kirjastojen lataamisen määrittäminen

Sisällytä uudet JavaScript-tiedostot kirjastojen jälkeen matriisiin `externalJS` kohteessa `pbiviz.json`. Esimerkki:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

Tuo kirjastot lähdekoodiisi. Jos kyseessä on esimerkiksi `lodash-es`, käytä seuraavaa lauseketta:

```JS
import * as _ from "lodash-es";
```

Edellisessä esimerkissä `_` on yleinen muuttuja kirjastolle `lodash`.

## <a name="make-changes-in-the-sources-of-your-visuals"></a>Muutosten tekeminen visualisointien lähteisiin

Tärkein muutos, joka sinun täytyy tehdä, on muuntaa sisäiset moduulit ulkoisiksi moduuleiksi. Et voi käyttää ulkoisia moduuleja sisäisissä moduuleissa.

Tässä on tarkka kuvaus muutoksista, jotka sinun täytyy tehdä. Muutokset kuvataan mukautetun palkkikaaviovisualisoinnin koodiesimerkin kontekstissa:

1. Poista kaikki moduulien määritykset kustakin [lähdekoodin](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbL1-L3) tiedostosta:

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Tuo Power BI:n mukautetun visualisoinnin ohjelmointirajapinnan määritelmät](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR4):

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. [Tuo tarvittavat liittymät tai luokat](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR12-R35) sisäisestä moduulista `powerbi`.

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

4. [Tuo D3.js-kirjasto](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR2):

    ```typescript
    import * as d3 from "d3";
    ```

    Voit myös tuoda vain vaaditut D3-kirjastomoduulit:

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [Tuo visualisointiprojektissa määritetyt apuohjelmat, luokat ja liittymät](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR38-R41) päälähdetiedostoon:

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

Työkalujen uuden version avulla voit tyylejä (`CSS` ja `Less`) suoraan TypeScript-koodiin. Kääntäjä ohittaa nyt aiemmin käytetyn [styles-osan](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/pbiviz.json#L21).

Jos haluat käyttää omaa tyylisivua, avaa TypeScript-päätiedosto (.ts) ja lisää seuraava rivi:  

```typescript
import "./../style/visual.less";
```  

Tyylit (`CSS` ja `Less`) käännetään automaattisesti.

### <a name="externaljs-section-in-pbivizjson"></a>externalJS-osa kohteessa pbiviz.json

Työkalut [eivät edellytä luetteloa `externalJS`-kirjastoista](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-a1a7bbee7e7d2f9d449f4b534532bcf2R20), jotka ladataan visualisointipakettiin, koska Webpack sisältää kaikki tuodut kirjastot.

> [!NOTE]
> Avaa `pbiviz.json` ja jätä osio `externalJS` tyhjäksi.

Tyypillisellä komennolla `npm run package` voit luoda visualisointipaketin ja komennolla `npm run start` käynnistää kehityspalvelimen.

## <a name="update-the-d3js-library-to-version-5"></a>Päivitä D3.js-kirjasto versioon 5

Uusilla visualisointityökaluilla voit aloittaa D3.js-kirjaston uuden version käytön. Päivitä D3 visualisointiprojektissasi suorittamalla nämä komennot:

- `npm install --save d3@5` asentaa uuden D3.js-kirjaston.

- `npm install --save-dev @types/d3@5` asentaa D3.js-kirjaston uudet tyyppimääritykset.

> [!IMPORTANT]
> D3-versio 5 sisältää useita rikkovia muutoksia.

Muokkaa koodisi yhteensopivaksi uuden D3.js:n kanssa:

- Liittymä `d3.Selection<T>` [on nyt](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157) `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`.

- Et voi käyttää useita määritteitä yhdellä menetelmän `attr` kutsulla. Sinun täytyy sen sijaan [välittää kukin määrite erillisellä kutsulla](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278) menetelmälle `attr`. Tee [erilliset kutsut myös menetelmälle `style`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247).

- D3.js versio 4 sisälsi uuden menetelmän `merge`. Tällä menetelmällä yhdistetään `enter`- ja `update`-valinnat tietojen yhdistämisen jälkeen. Jos haluat käyttää D3:a oikein, [kutsu menetelmää `merge`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272).

[Lue lisää](https://github.com/d3/d3/blob/master/CHANGES.md) D3.js-kirjaston muutoksista.

## <a name="install-babel-and-core-js"></a>Asenna Babel ja core-js

Versiosta 3.1 alkaen visualisointityökalut kääntävät uuden nykyaikaisen JS-koodin vanhaan ECMAScript 5 (ES5) -muotoon Babelilla, jotta useita eri selaimia voidaan tukea.

Babel-asetus on oletusarvoisesti käytössä, mutta sinun täytyy tuoda paketti [`core-js`](https://www.npmjs.com/package/core-js) manuaalisesti. Asenna paketti suorittamalla tämä komento:

```cmd
npm install --save core-js
```

Tuo sitten paketti visuaalisen koodin alkupisteeseen. Yleensä se on src/visual.ts-tiedosto.

```JS
import "core-js/stable";
```

Lue lisätietoa Babel-työkalusta [dokumentaatiosta](https://babeljs.io/docs/en/).
