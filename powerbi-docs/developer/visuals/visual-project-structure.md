---
title: Power BI -visualisoinnin projektirakenne
description: Tässä artikkelissa kuvataan Power BI -visualisointiprojektin kansio- ja tiedostorakenne
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 01/12/2020
ms.openlocfilehash: 18267f06bd43166cb1958d3aff73913a31189953
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80550755"
---
# <a name="power-bi-visual-project-structure"></a>Power BI -visualisoinnin projektirakenne

Paras tapa aloittaa uuden Power BI -visualisoinnin luominen on käyttää Power BI -visualisoinnin [pbiviz](https://www.npmjs.com/package/powerbi-visuals-tools)-työkalua.

Jos haluat luoda uuden visualisoinnin, siirry siihen hakemistoon, jossa haluat Power BI -visualisoinnin sijaitsevan, ja suorita komento:

`pbiviz new <visual project name>`

Tämän komennon suorittamalla luot Power BI -visualisointikansion, joka sisältää seuraavat tiedostot:

```markdown
project
├───.vscode
│   ├───launch.json
│   └───settings.json
├───assets
│   └───icon.png
├───node_modules
├───src
│   ├───settings.ts
│   └───visual.ts
├───style
│   └───visual.less
├───capabilities.json
├───package-lock.json
├───package.json
├───pbiviz.json
├───tsconfig.json
└───tslint.json
```

## <a name="folder-and-file-description"></a>Kansion ja tiedoston kuvaus

Tämä osa sisältää tietoja kaikista kansioista ja tiedostoista, jotka Power BI -visualisoinnin **pbiviz**-työkalu luo.  

### <a name="vscode"></a>.vscode

Tämä kansio sisältää VS-koodin projektiasetukset.

Määritä työtila muokkaamalla `.vscode/settings.json`-tiedostoa.

Katso lisätietoja kohdasta [Käyttäjän ja työtilan asetukset](https://code.visualstudio.com/docs/getstarted/settings)

### <a name="assets"></a>assets

Tämä kansio sisältää `icon.png`-tiedoston.

Power BI -visualisointityökalu käyttää tätä uuden Power BI -visualisoinnin kuvakkeena Power BI -visualisointiruudussa.

### <a name="src"></a>src

Tämä kansio sisältää visualisoinnin lähdekoodin.

Tähän kansioon Power BI -visualisointityökalu luo seuraavat tiedostot:
* `visual.ts` – Visualisoinnin päälähdekoodi.
* `settings.ts` – Visualisoinnin asetusten koodi. Tiedoston luokat toimivat rajapintana, jonka avulla voit määrittää [visualisoinnin ominaisuudet](./objects-properties.md#properties).

### <a name="style"></a>style

Tämä kansio sisältää `visual.less`-tiedoston, joka sisältää visualisoinnin tyylitiedot.

### <a name="capabilitiesjson"></a>capabilities.json

Tämä tiedosto sisältää visualisoinnin tärkeimmät ominaisuudet ja asetukset ([ominaisuudet](./capabilities.md)). Sen avulla visualisointi voi esitellä tuetut ominaisuudet, objektit, toiminnot ja [tietonäkymän yhdistämismääritykset](./dataview-mappings.md).

### <a name="package-lockjson"></a>package-lock.json

Tämä tiedosto luodaan automaattisesti kaikille toiminnoille, joissa *npm* muokkaa joko `node_modules`-puuta tai `package.json`-tiedostoa.

Lisätietoja tästä tiedostosta saat virallisesta [npm-package-lock.json](https://docs.npmjs.com/files/package-lock.json)-dokumentaatiosta.

### <a name="packagejson"></a>package.json

Tämä tiedosto kuvaa projektipakettia. Se sisältää sellaista projektia koskevaa tietoa kuin tekijät, kuvauksen ja projektin riippuvuudet.

Lisätietoja tästä tiedostosta saat virallisesta [npm-package.json](https://docs.npmjs.com/files/package.json.html)-dokumentaatiosta.

### <a name="pbivizjson"></a>pbiviz.json

Tämä tiedosto sisältää visualisoinnin metatiedot.

Jos haluat tarkastella `pbiviz.json`-esimerkkitiedostoa, jonka kommentit kuvaavat metatietojen merkintöjä, katso osaa [metatietojen merkinnät](#metadata-entries).

### <a name="tsconfigjson"></a>tsconfig.json

Määritystiedosto kohteelle [TypeScript](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).

Tämän tiedoston on sisällettävä polku **\*.ts**-tiedostoon, jossa visualisoinnin pääluokka sijaitsee, kuten `visualClassName`-ominaisuudessa, `pbiviz.json`-tiedostossa on täsmennetty.

### <a name="tslintjson"></a>tslint.json

Tämä tiedosto sisältää [TSLintin määrityksen](https://palantir.github.io/tslint/usage/configuration/).

## <a name="metadata-entries"></a>Metatietojen merkinnät

Seuraavan koodiotsikon kommentit, jotka ovat peräisin `pbiviz.json`-tiedostosta, kuvaavat metatietomerkintöjä.

> [!NOTE]
> * **pbiviz**-työkalun versiosta 3.x.x alkaen `externalJS`:n tuki loppuu.
> * Jos tarvitset lokalisointitukea, [lisää Power BI -kieliasetukset visualisointiisi](./localization.md).

```json
{
  "visual": {
     // The visual's internal name.
    "name": "<visual project name>",

    // The visual's display name.
    "displayName": "<visual project name>",

    // The visual's unique ID.
    "guid": "<visual project name>23D8B823CF134D3AA7CC0A5D63B20B7F",

    // The name of the visual's main class. Power BI creates the instance of this class to start using the visual in a Power BI report.
    "visualClassName": "Visual",

    // The visual's version number.
    "version": "1.0.0",
    
    // The visual's description (optional)
    "description": "",

    // A URL linking to the visual's support page (optional).
    "supportUrl": "",

    // A link to the source code available from GitHub (optional).
    "gitHubUrl": ""
  },
  // The version of the Power BI API the visual is using.
  "apiVersion": "2.6.0",

  // The name of the visual's author and email.
  "author": { "name": "", "email": "" },

  // 'icon' holds the path to the icon file in the assets folder; the visual's display icon.
  "assets": { "icon": "assets/icon.png" },

  // Contains the paths for JS libraries used in the visual.
  // Note: externalJS' isn't used in the Power BI visuals tool version 3.x.x or higher.
  "externalJS": null,

  // The path to the 'visual.less' style file.
  "style": "style/visual.less",

  // The path to the `capabilities.json` file.
  "capabilities": "capabilities.json",

  // The path to the `dependencies.json` file which contains information about R packages used in R based visuals.
  "dependencies": null,

  // An array of paths to files with localizations.
  "stringResources": []
}
```

## <a name="next-steps"></a>Seuraavat vaiheet

* Jos haluat ymmärtää visualisoinnin, käyttäjän ja Power BI:n vuorovaikutusta, katso kohtaa [Power BI -visualisointikonsepti](./power-bi-visuals-concept.md).

* Aloita omien Power BI -visualisointien kehittäminen alusta alkaen käyttämällä [vaiheittaisia ohjeita](./custom-visual-develop-tutorial.md).
