---
title: Mitä kehittäjät voivat tehdä Power BI:llä?
description: Power BI tarjoaa useita erilaisia asetuksia kehittäjille. Niitä on upottamisesta mukautettuihin visualisointeihin ja virtautettaviin tietojoukkoihin.
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 07fb8d365a6fe4a874b057a71a90a99fc8a9e5fa
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34564692"
---
# <a name="what-can-developers-do-with-power-bi"></a>Mitä kehittäjät voivat tehdä Power BI:llä?

Kehittäjille on eri vaihtoehtoja Power BI- sisällön sisällyttämisessä sovelluksiin. Näihin vaihtoehtoihin kuuluvat **upottaminen Power BI:llä**, **mukautetut visualisoinnit** ja **tietojen työntäminen Power BI:hin**.

## <a name="embedding"></a>Upottaminen
Power BI -palvelu (SaaS) ja Power BI Embedded -palvelu Azuressa (PaaS) sisältävät ohjelmointirajapintoja raporttinäkymien ja raporttien upottamista varten. Se tarkoittaa, että saat tarvittavat ominaisuudet ja oikeudet käyttää uusimpia Power BI -toimintoja, kuten koontinäyttöjä, yhdyskäytäviä ja sovellustyötiloja, sisältöjen upottamiseen.

Voit käyttää [Perehdyttämiskokemustyökalua](https://aka.ms/embedsetup) aloittaaksesi ja ladataksesi mallisovelluksen nopeasti.

Valitse ratkaisu, joka sopii sinulle:
* [Asiakkaille tarkoitettu upotus](embedding.md#embedding-for-your-customers) mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Suorita [asiakkaille tarkoitettu upotus](https://aka.ms/embedsetup/AppOwnsData).
* [Organisaatiolle tarkoitettu upotus](embedding.md#embedding-for-your-organization) mahdollistaa Power BI -palvelun laajentamisen. Suorita [organisaatiolle tarkoitettu upotus](https://aka.ms/embedsetup/UserOwnsData).

![PBIE-malli](media/what-can-you-do/what-can-you-do-02.png)

## <a name="develop-custom-visuals"></a>Kehitä mukautettuja visualisointeja
Mukautettujen visualisointien avulla voit luoda omia visualisointeja käytettäväksi Power BI ‑raporteissa. Mukautetut visualisoinnit kirjoitetaan Typescriptillä, joka on JavaScriptin yläjoukko. TypeScript tukee edistyneempiä ominaisuuksia ja varhaista pääsyä ES6/ES7-toiminnallisuuteen. Visualisointityylit käsitellään Cascading Style Sheet (CSS) -tyyliohjeiden avulla. Käyttömukavuuden lisäämiseksi käytämme Less-esikääntäjää, joka tukee joitakin kehittyneitä ominaisuuksia, kuten sisäkkäisyyttä, muuttujia, ehtoja, silmukoita jne. Jos et halua käyttää mitään näistä ominaisuuksista, voit kirjoittaa pelkkää CSS:ää Less-tiedostoon.

![CV-malli](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Tietojen työntäminen Power BI:hin
Power BI ‑ohjelmointirajapinnan avulla voit lähettää tietoja tietojoukkoon. Sen avulla voit lisätä tietojoukkoon sisältyvään taulukkoon uuden rivin. Uudet tiedot voidaan sitten esittää koontinäytön ruuduissa sekä raporttiin sisältyvissä visualisoinneissa.

![Tietojen työntämismalli](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Upottaminen Power BI:n avulla](embedding.md)  
[Mukautettujen visualisointien julkaiseminen Office-kauppaan](office-store.md)  
[Tietojen lähettäminen koontinäyttöön](walkthrough-push-data.md)
