---
title: Mitä Power BI:n ohjelmointirajapinnalla voi tehdä?
description: Mitä Power BI:n ohjelmointirajapinnalla voi tehdä?
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 03/25/2019
ms.openlocfilehash: fd49c69a14d3dac6b1a045f6aba407ec7aac0deb
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61269412"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Mitä kehittäjät voivat tehdä Power BI -ohjelmointirajapinnalla?

Power BI:n REST-ohjelmointirajapinnan avulla voit luoda sovelluksia, jotka integroidaan Power BI -raportteihin, koontinäyttöihin ja ruutuihin.

Power BI:n REST-ohjelmointirajapinnan avulla on mahdollista suorittaa hallintatehtäviä Power BI -objekteissa, kuten raporteissa, tietojoukoissa ja työtiloissa.

Seuraavassa on joitakin asioita, joita voit tehdä Power BI -ohjelmointirajapinnan avulla.

| **Lisätietoja** | **Tämä viitetiedot** |
|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| Upottaa raportteja, koontinäyttöjä ja ruutuja sekä Power BI:tä käyttävien että Power BI:tä käyttämättömien käyttäjien saataville. | [Power BI-koontinäyttöjen, raporttien ja ruutujen upottaminen ](embedding-content.md) |
| Suorittaa hallintatehtäviä Power BI -objekteille | [Power BI:n REST-ohjelmointirajapinnan viite](https://docs.microsoft.com/rest/api/power-bi/) |
| Laajentaa aiemmin luotua liiketoiminnan työnkulkua työntääksesi avaintietoja Power BI ‑koontinäyttöön | [Tietojen lähettäminen koontinäyttöön ](walkthrough-push-data.md) |
| Todentaa käyttäjiä Power BI -palvelussa | [Power BI-todentaminen ](get-azuread-access-token.md) |

> [!NOTE]
> Power BI -ohjelmointirajapinnat viittaavat sovelluksen työtiloihin edelleen ryhminä. Mitkä tahansa viittaukset ryhmiin tarkoittavat sitä, että työskentelet sovelluksen työtilojen parissa.

## <a name="api-developer-tools"></a>Ohjelmointirajapinnan kehitystyökalut

| Työkalu(t) | Kuvaus |  |  |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
| [Leikkikenttä työkalu](https://microsoft.github.io/PowerBI-JavaScript/demo) | Täydellinen malli Power BI JavaScript -ohjelmointirajapintojen käyttämisestä. Tämä työkalu on lisäksi nopea tapa kokeilla erilaisia Power BI Embedded -malleja. |  |  |
| [Power BI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) | Lisätietojen saaminen Power BI JavaScript -ohjelmointirajapinnoista. |  |  |
| [Postman](https://www.getpostman.com/) | Pyyntöjen suorittaminen, testaaminen, virheiden korjaaminen, seuranta, automaattisten testien suorittaminen ja paljon muuta. |

## <a name="push-data-into-power-bi"></a>Tietojen työntäminen Power BI:hin

Power BI ‑ohjelmointirajapinnan avulla voit [lähettää tietoja tietojoukkoon](walkthrough-push-data.md). Tämän ominaisuuden avulla voit lisätä tietojoukkoon sisältyvään taulukkoon uuden rivin. Uudet tiedot esitetään sitten koontinäytön ruuduissa sekä raporttiin sisältyvissä visualisoinneissa.

![Tietojen työntämismalli](media/what-can-you-do/powerbi-push-data.png)

## <a name="github-repositories"></a>GitHub-säilöt

* [Power BI:n kehittäjämallit](https://github.com/Microsoft/PowerBI-Developer-Samples)
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript-ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="next-steps"></a>Seuraavat vaiheet

* [Tietojen työntäminen tietojoukkoon](walkthrough-push-data.md)
* [Power BI:n mukautetun visualisoinnin kehittäminen](custom-visual-develop-tutorial.md)
* [Power BI REST-Ohjelmointirajapinnan viittaus](rest-api-reference.md)
* [Power BI:n REST-ohjelmointirajapinnat](https://docs.microsoft.com/rest/api/power-bi/)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
