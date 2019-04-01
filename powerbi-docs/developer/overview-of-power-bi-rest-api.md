---
title: Mitä Power BI:n ohjelmointirajapinnalla voi tehdä?
description: Mitä Power BI:n ohjelmointirajapinnalla voi tehdä?
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.openlocfilehash: 764718ab86e040509790dd4debbbef25b6079a14
ms.sourcegitcommit: 9f31cd41bd92e398717da5a69a074273e8c6f8a6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/26/2019
ms.locfileid: "58473771"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Mitä kehittäjät voivat tehdä Power BI -ohjelmointirajapinnalla?

Power BI:n REST-ohjelmointirajapinnan avulla voit luoda sovelluksia, jotka upottavat Power BI -raportteja. Voit myös integroida Power BI -ruutuja ja -koontinäyttöjä sovelluksiin.

Power BI:n REST-ohjelmointirajapinnan avulla on mahdollista suorittaa hallintatehtäviä Power BI -objekteissa, kuten raporteissa, tietojoukoissa ja työtiloissa.

Seuraavassa on joitakin asioita, joita voit tehdä Power BI -ohjelmointirajapinnan avulla.

| **Jos haluat tehdä tämän...** | **...siirry tänne** |
| --- | --- |
| Upottaa raportteja, koontinäyttöjä ja ruutuja sekä Power BI:tä käyttävien että Power BI:tä käyttämättömien käyttäjien saataville |[Power BI:n koontinäyttöjen, raporttien ja ruutujen upottaminen](embedding-content.md) |
| Suorittaa hallintatehtäviä Power BI -objekteille |[Power BI:n REST-ohjelmointirajapinnan viite](https://docs.microsoft.com/rest/api/power-bi/) |

> [!NOTE]
> Power BI -ohjelmointirajapinnat viittaavat sovelluksen työtiloihin edelleen ryhminä. Mitkä tahansa viittaukset ryhmiin tarkoittavat sitä, että työskentelet sovelluksen työtilojen parissa.

## <a name="developer-tools"></a>Kehitystyökalut

Seuraavassa on työkaluja, joiden avulla voit kehittää omia Power BI ‑kohteitasi.

Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup) päästäksesi nopeasti alkuun ja ladataksesi mallisovelluksen, jolla opit upottamaan Power BI -sisältöä.

Valitse ratkaisu, joka sopii sinulle:

* [Asiakkaille tarkoitettu upotus](embedding.md#embedding-for-your-customers) mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Suorita [asiakkaille tarkoitettu upotus](https://aka.ms/embedsetup/AppOwnsData).

* [Organisaatiolle tarkoitettu upotus](embedding.md#embedding-for-your-organization) mahdollistaa Power BI -palvelun laajentamisen. Suorita [organisaatiolle tarkoitettu upotus](https://aka.ms/embedsetup/UserOwnsData).

[Playground-työkalun](https://microsoft.github.io/PowerBI-JavaScript/demo) avulla saat kokonaisen mallin JavaScript-ohjelmointirajapinnan käytöstä. Tämä työkalu on nopea tapa kokeilla erilaisia Power BI Embedded -malleja. Saat lisätietoja JavaScript-ohjelmointirajapinnasta vierailemassa [Power BI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) -sivulla.

## <a name="github-repositories"></a>GitHub-säilöt

* [Power BI:n kehittäjämallit](https://github.com/Microsoft/PowerBI-Developer-Samples)
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript-ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
