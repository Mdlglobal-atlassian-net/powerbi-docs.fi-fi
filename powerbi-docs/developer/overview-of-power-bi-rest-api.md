---
title: Mitä Power BI:n ohjelmointirajapinnalla voi tehdä?
description: Mitä Power BI:n ohjelmointirajapinnalla voi tehdä?
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 3b19740616e7b9a390a883fde2fd96320de7b94a
ms.sourcegitcommit: 698b788720282b67d3e22ae5de572b54056f1b6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/17/2018
ms.locfileid: "45973582"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Mitä kehittäjät voivat tehdä Power BI -ohjelmointirajapinnalla?

Power BI esittää koontinäyttöjä, jotka ovat vuorovaikutteisia ja joita voi luoda ja päivittää useista eri tietolähteistä reaaliaikaisesti. Voit luoda Power BI ‑koontinäyttöihin integroituja reaaliaikaisia sovelluksia käyttämällä mitä tahansa ohjelmointikieltä, joka tukee REST-kutsuja. Voit myös integroida Power BI-ruutuja ja raportteja sovelluksiin.

Lisäksi kehittäjät voivat luoda tiedoista omia visualisointejaan, joita voidaan käyttää vuorovaikutteisissa raporteissa ja koontinäkymissä.

Seuraavassa on joitakin asioita, joita voit tehdä Power BI -ohjelmointirajapinnan avulla.

| **Jos haluat tehdä tämän...** | **...siirry tänne** |
| --- | --- |
| Upottaa koontinäyttöjä, raportteja ja ruutuja sekä Power BI:tä käyttävien että Power BI:tä käyttämättömien (sovellus omistaa tiedot) käyttäjien saataville |[Power BI:n koontinäyttöjen, raporttien ja ruutujen upottaminen](embedding-content.md) |
| Laajentaa aiemmin luotua liiketoiminnan työnkulkua työntääksesi avaintietoja Power BI ‑koontinäyttöön |[Tietojen lähettäminen koontinäyttöön](walkthrough-push-data.md) |
| Todentaa käyttäjiä Power BI -palvelussa |[Power BI -palveluun todentaminen](get-azuread-access-token.md) |
| Luoda mukautetun visualisoinnin |[Mukautettujen visualisointien luominen kehittäjätyökalujen avulla](../service-custom-visuals-getting-started-with-developer-tools.md) |

> [!NOTE]
> Power BI -ohjelmointirajapinnat viittaavat sovelluksen työtiloihin edelleen ryhminä. Mitkä tahansa viittaukset ryhmiin tarkoittavat sitä, että työskentelet sovelluksen työtilojen parissa.

## <a name="power-bi-developer-samples"></a>Power BI:n kehittäjämallit

Power BI:n kehittäjämallit sisältävät kohteita, joita voi käyttää koontinäyttöjen, raporttien ja ruutujen upottamisessa.

[Power BI:n kehittäjämallit](https://github.com/Microsoft/PowerBI-Developer-Samples)

* **App Owns Data** ‑hakemiston mallit on tarkoitettu sisällön upottamiseen muita kuin Power BI ‑käyttäjiä varten.
* **User Owns Data** ‑hakemiston mallit on tarkoitettu sisällön upottamiseen Power BI ‑käyttäjiä varten.

## <a name="github-repositories"></a>GitHub-säilöt

* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript-ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript)
* [Mukautetut visualisoinnit](https://github.com/Microsoft/PowerBI-visuals)

## <a name="developer-tools"></a>Kehitystyökalut

Seuraavassa on työkaluja, joiden avulla voit kehittää omia Power BI ‑kohteitasi.

Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup) päästäksesi nopeasti alkuun ja ladataksesi mallisovelluksen, jolla opit upottamaan Power BI -sisältöä.

Valitse ratkaisu, joka sopii sinulle:

* [Asiakkaille tarkoitettu upotus](embedding.md#embedding-for-your-customers) mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Suorita [asiakkaille tarkoitettu upotus](https://aka.ms/embedsetup/AppOwnsData).

* [Organisaatiolle tarkoitettu upotus](embedding.md#embedding-for-your-organization) mahdollistaa Power BI -palvelun laajentamisen. Suorita [organisaatiolle tarkoitettu upotus](https://aka.ms/embedsetup/UserOwnsData).

Voit käyttää [Playground-työkalua](https://microsoft.github.io/PowerBI-JavaScript/demo), saadaksesi käyttöösi kokonaisen mallin, joka käyttää JavaScript-ohjelmointirajapintaa. Tämä työkalu on nopea tapa kokeilla erilaisia Power BI Embedded -malleja. Saat lisätietoja JavaScript-ohjelmointirajapinnasta vierailemassa [Power BI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) -sivulla.

## <a name="push-data-into-power-bi"></a>Tietojen työntäminen Power BI:hin

Power BI ‑ohjelmointirajapinnan avulla voit lähettää tietoja tietojoukkoon. Tämän ominaisuuden avulla voit lisätä tietojoukkoon sisältyvään taulukkoon uuden rivin. Uudet tiedot voidaan sitten esittää koontinäytön ruuduissa sekä raporttiin sisältyvissä visualisoinneissa.

![Tietojen työntämismalli](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Tietojen työntäminen tietojoukkoon](walkthrough-push-data.md)  
[Mukautettujen visualisointien kehittäjätyökalujen käytön aloittaminen](../service-custom-visuals-getting-started-with-developer-tools.md)  
[Power BI:n REST-ohjelmointirajapinnan viite](https://docs.microsoft.com/rest/api/power-bi/)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
