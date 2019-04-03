---
title: Mitä kehittäjät voivat tehdä Power BI:llä?
description: Power BI tarjoaa useita erilaisia asetuksia kehittäjille. Niitä on upottamisesta mukautettuihin visualisointeihin ja virtautettaviin tietojoukkoihin.
author: markingmyname
ms.author: maghan
manager: kfile
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: mvc
ms.date: 03/15/2019
ms.openlocfilehash: 63ee9ed96ed699d116b8d81b0cd612f76994a68d
ms.sourcegitcommit: 3a05f34dbeabac62ea8c35c12a045284271971bc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/03/2019
ms.locfileid: "58872681"
---
# <a name="what-can-developers-do-with-power-bi"></a>Mitä kehittäjät voivat tehdä Power BI:llä?

Kehittäjille on eri vaihtoehtoja Power BI- sisällön sisällyttämisessä sovelluksiin. Kehittäjien kohdalla näihin vaihtoehtoihin kuuluvat **upottaminen Power BI:llä**, **mukautetut visualisoinnit** ja **tietojen työntäminen Power BI:hin**.

## <a name="embedding-power-bi-content"></a>Power BI -sisällön upottaminen

Power BI -palvelu (SaaS) ja Power BI Embedded -palvelu Azuressa (PaaS) sisältävät ohjelmointirajapintoja raporttinäkymien ja raporttien upottamista varten. Tämä ominaisuus tarkoittaa, että saat oikeudet käyttää uusimpia Power BI -toimintoja, kuten koontinäyttöjä, yhdyskäytäviä ja sovellustyötiloja, sisältöjen upottamiseen.

Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup) päästäksesi nopeasti alkuun ja ladataksesi mallisovelluksen.

Valitse ratkaisu, joka sopii sinulle:

* [Asiakkaille tarkoitettu upotus](embedding.md#embedding-for-your-customers) mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Suorita [asiakkaille tarkoitettu upotus](https://aka.ms/embedsetup/AppOwnsData).

* [Organisaatiolle tarkoitettu upotus](embedding.md#embedding-for-your-organization) mahdollistaa Power BI -palvelun laajentamisen. Suorita [organisaatiolle tarkoitettu upotus](https://aka.ms/embedsetup/UserOwnsData).

![PBIE-malli](media/what-can-you-do/what-can-you-do-02.png)

Saat lisätietoja upottamisesta Power BI:llä kohdasta [Upottaminen Power BI:llä](embedding.md).

## <a name="developing-custom-visuals"></a>Mukautettujen visualisointien kehittäminen

Power BI:n mukautettujen visualisointien avulla voit luoda yksilöllisen visualisointityypin, joka on räätälöity sinulle tai yrityksellesi. Usein näitä mukautettuja visualisointeja luovat kehittäjät. Ne luodaan, kun Power BI:n visualisointien valikoima ei täysin vastaa tarpeitasi.

Mukautettujen visualisointien avulla voit luoda omia visualisointeja käytettäväksi Power BI ‑raporteissa. Mukautetut visualisoinnit kirjoitetaan Typescriptillä, joka on JavaScriptin yläjoukko. TypeScript tukee edistyneempiä ominaisuuksia ja varhaista pääsyä ES6/ES7-toiminnallisuuteen. Visualisointityylit käsitellään Cascading Style Sheet (CSS) -tyyliohjeiden avulla. Käyttömukavuuden lisäämiseksi käytämme Less-esikääntäjää, joka tukee joitakin kehittyneitä ominaisuuksia, kuten sisäkkäisyyttä, muuttujia, ehtoja, silmukoita ja muita ominaisuuksia. Jos et halua käyttää mitään näistä ominaisuuksista, voit kirjoittaa pelkkää CSS:ää Less-tiedostoon.

![CV-malli](media/what-can-you-do/powerbi-custom-visual-store.png)

Saat lisätietoja mukautetun visualisoinnin kehittämisestä kohdasta [Power BI:n mukautettujen visualisointien luominen](custom-visual-develop-tutorial.md).

## <a name="using-api-automation"></a>Ohjelmointirajapinta-automaation käyttäminen

Power BI esittää koontinäyttöjä, jotka ovat vuorovaikutteisia ja joita voi luoda ja päivittää useista eri tietolähteistä reaaliaikaisesti. Voit luoda Power BI ‑koontinäyttöihin integroituja reaaliaikaisia sovelluksia käyttämällä mitä tahansa ohjelmointikieltä, joka tukee REST-kutsuja. Voit myös integroida Power BI-ruutuja ja raportteja sovelluksiin.

Lisäksi kehittäjät voivat luoda tiedoista omia visualisointejaan, joita voidaan käyttää vuorovaikutteisissa raporteissa ja koontinäkymissä.

![Tietojen työntämismalli](media/what-can-you-do/powerbi-push-data.png)

Voit tutustua Power BI -ohjelmointirajapinnoilla tehtäviin asioihin kohdassa [Mitä kehittäjä voi tehdä Power BI -ohjelmointirajapinnoilla](overview-of-power-bi-rest-api.md)?

## <a name="next-steps"></a>Seuraavat vaiheet

[Upottaminen Power BI:llä](embedding.md)  

[Power BI:n mukautetun visualisoinnin kehittäminen](https://microsoft.github.io/PowerBI-visuals/docs/step-by-step-lab/developing-a-power-bi-custom-visual/)

[Mitä kehittäjät voivat tehdä Power BI -ohjelmointirajapinnalla?](overview-of-power-bi-rest-api.md)

[Power BI -kehittäjäkeskus](https://powerbi.microsoft.com/developers/)