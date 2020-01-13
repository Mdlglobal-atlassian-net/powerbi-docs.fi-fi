---
title: Power BI -visualisoinnin projektirakenne
description: Artikkelissa kuvataan visualisointiprojektien rakenne
author: zBritva
ms.author: v-ilgali
ms.reviewer: ''
ms.service: powerbi
ms.topic: tutorial
ms.subservice: powerbi-custom-visuals
ms.date: 03/15/2019
ms.openlocfilehash: 728aba749f80710fdc0bb1e180b3318e63caa88c
ms.sourcegitcommit: 331ebf6bcb4a5cdbdc82e81a538144a00ec935d4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/28/2019
ms.locfileid: "75542089"
---
# <a name="power-bi-visual-project-structure"></a>Power BI -visualisoinnin projektirakenne

Kun pbiviz uusi `<visual project name>` on suoritettu, työkalu luo kansiossa `<visual project name>` olevien tiedostojen ja kansioiden perusrakenteen.

## <a name="visual-project-structure"></a>Visualisoinnin projektirakenne

![Visualisoinnin projektirakenne](./media/visual-project-structure.png)

* `.vscode` – sisältää projektin asetukset VS Codelle. Määritä työtila muokkaamalla tiedostoa `.vscode/settings.json`. Lue lisää [VS Coden asetuksista dokumentaatiosta](https://code.visualstudio.com/docs/getstarted/settings)

* Kansio `assets` sisältää vain tiedoston `icon.png`. Työkalu käyttää tätä tiedostoa visualisoinnin kuvakkeena Power BI:n Visualisointi-ruudussa.

    ![Visualisointi-ruutu](./media/visualization-pane-analytics-tab.png)

* Kansio `node_modules` sisältää kaikki paketit, jotka [Node Package Manager on asentanut](https://docs.npmjs.com/files/folders.html).

* Kansio `src` sisältää visualisoinnin lähdekoodin. Työkalu luo oletusarvoisesti kaksi tiedostoa:

  * `visual.ts` – visualisoinnin päälähdekoodi.

  * `settings.ts` – visualisoinnin asetusten koodi. Tiedoston luokat yksinkertaistavat [visualisoinnin ominaisuuksien käsittelyä](./objects-properties.md#properties).

* Kansio `style` sisältää tiedoston `visual.less`, jossa on visualisoinnin tyylejä.

* Tiedosto `capabilities.json` sisältää visualisoinnin pääominaisuudet ja asetukset. Sen avulla visualisointi voi esitellä tuetut ominaisuudet, objektit, toiminnot ja tietonäkymän yhdistämismääritykset.

    Lue lisää [ominaisuuksista dokumentaatiosta](./capabilities.md).

* `package-lock.json` luodaan automaattisesti kaikille toiminnoille, joissa npm muokkaa joko puuta `node_modules` tai pakettia `package.json`.

    Lue lisää [aiheesta `package-lock.json` NPM:n virallisesta dokumentaatiosta](https://docs.npmjs.com/files/package-lock.json).

* `package.json` kuvaa projektipakettia. Se sisältää yleensä tietoja projektista, sen tekijöistä, kuvauksesta ja riippuvuuksista.

    Lue lisää [aiheesta `package.json` NPM:n virallisesta dokumentaatiosta](https://docs.npmjs.com/files/package.json.html).

* `pbiviz.json` sisältää visualisoinnin metatiedot. Määritä visualisoinnin metatiedot tässä tiedostossa.

    Tiedoston tyypillinen sisältö:

  ```json
    {
        "visual": {
            "name": "<visual project name>",
            "displayName": "<visual project name>",
            "guid": "<visual project name>23D8B823CF134D3AA7CC0A5D63B20B7F",
            "visualClassName": "Visual",
            "version": "1.0.0",
            "description": "",
            "supportUrl": "",
            "gitHubUrl": ""
        },
        "apiVersion": "2.6.0",
        "author": { "name": "", "email": "" },
        "assets": { "icon": "assets/icon.png" },
        "externalJS": null,
        "style": "style/visual.less",
        "capabilities": "capabilities.json",
        "dependencies": null,
        "stringResources": []
    }
  ```

    jossa

  * `name` – visualisoinnin sisäinen nimi.

  * `displayName` – visualisoinnin nimi Power BI:n käyttöliittymässä.

  * `guid` – visualisoinnin yksilöivä tunnus.

  * `visualClassName` – visualisoinnin pääluokan nimi. Power BI luo tämän luokan esiintymän, jotta visualisointia voi alkaa käyttää Power BI -raportissa.

  * `version` – visualisoinnin versionumero.

  * `author` – sisältää tekijän nimen ja yhteyshenkilön sähköpostiosoitteen.

  * `icon` kohteessa `assets` – polku visualisoinnin kuvaketiedostoon.

  * `externalJS` sisältää visualisoinnissa käytettävien JS-kirjastojen polut.

    > [!IMPORTANT]
    > Työkalun uusin versio 3.x.x tai uudempi versio ei enää käytä kohdetta `externalJS`.

  * `style` on polku tyylitiedostoihin.

  * `capabilities` on polku tiedostoon `capabilities.json`.

  * `dependencies` on polku tiedostoon `dependencies.json`. `dependencies.json` sisältää tietoja R-pohjaisissa visualisoinneissa käytettävistä R-paketeista.

  * `stringResources` on lokalisointeja sisältävien tiedostojen polkujen matriisi.

  Lue lisää [visualisointien lokalisoinnista dokumentaatiosta](./localization.md)

* `tsconfig.json` on TypeScriptin määritystiedosto.

    Lue lisää [TypeScriptin määrityksestä virallisesta dokumentaatiosta](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)

    Osan `files` kohteen `tsconfig.json` on sisällettävä polku *.ts-tiedostoon, jossa visualisoinnin pääluokka sijaitsee, mikä on määritetty tiedoston `pbiviz.json` ominaisuudessa `visualClassName`.

* Tiedosto `tslint.json` sisältää TSLint-määrityksen.

    Lue lisää [TSLintin määrityksestä virallisesta dokumentaatiosta](https://palantir.github.io/tslint/usage/configuration/)

## <a name="next-steps"></a>Seuraavat vaiheet

* Lue lisää [visualisointikonseptista](./power-bi-visuals-concept.md), jotta ymmärrät paremmin visualisointien, käyttäjien ja Power BI:n keskinäistä vuorovaikutusta.

* Aloita omien Power BI -visualisointien kehittäminen alusta alkaen [vaiheittaisten ohjeiden avulla](./custom-visual-develop-tutorial.md).
