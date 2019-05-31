---
title: Power BI -palvelun ja Power BI Desktopin raporttien visualisointien yleiskatsaus
description: Microsoft Power BI:n raporttien visualisointien yleiskatsaus.
author: mihart
ms.author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: SYk_gWrtKvM
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/28/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: d470a262bd8a5e6590746fb07889b1230f5cfc25
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375652"
---
# <a name="visualizations-in-power-bi-reports"></a>Visualisoinnit Power BI -raporteissa

Visualisoinnit näyttävät merkityksellisiä tietoja datasta. Power BI -raportissa voi olla yksittäinen visualisointi yhdellä sivulla tai sivukaupalla visualisointeja. Power BI -palvelussa visualisointeja voi [kiinnittää raporteista koontinäyttöihin](../service-dashboard-pin-tile-from-report.md).

On tärkeää erottaa raportin *suunnittelijat* ja raportin *kuluttajien* Jos olet tai muokkaat raporttia ja olet suunnittelutyökalua.  Kehittäjät ovat raportin ja sen pohjana olevan tietojoukon muokkausoikeuksia. Power BI Desktopissa tämä tarkoittaa, että voit avata tietojoukon tietonäkymässä ja luoda visualisointeja raporttinäkymässä. Power BI-palvelussa Tämä tarkoittaa sitä, voit avata tietojoukon tai raportin raporttieditorin [muokkausnäkymässä](../consumer/end-user-reading-view.md). Jos raportti tai koontinäyttö on [jaettu kanssasi](../consumer/end-user-shared-with-me.md), olet raportin **kuluttaja**. Pystyt voit tarkastella ja käsitellä raporttia ja sen visualisointeja, mutta ei voi tallentaa merkittäviä muutoksia.

Power BI:ssä on monta erilaista visualisointityyppiä käytettävissä suoraan VISUALISOINNIT-ruudusta.

![](media/power-bi-report-visualizations/power-bi-templates.png)

Voit myös hakea lisää vaihtoehtoja [Microsoft AppSource -yhteisösivustossa](https://appsource.microsoft.com), josta voit [ladata](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) Microsoftin ja yhteisön tarjoamia [mukautettuja visualisointeja](../developer/custom-visual-develop-tutorial.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


  Jos olet uusi Power BI -käyttäjä tai haluat kerrata, löydät Power BI -visualisointien perusteet alla olevien linkkien kautta.  Vaihtoehtoisesti voit hakea lisätietoja sisällysluettelosta (artikkelin vasemmassa reunassa).

## <a name="add-a-visualization-in-power-bi"></a>Visualisoinnin lisääminen Power BI:ssä

[Luo visualisointeja](power-bi-report-add-visualizations-i.md) raporttien sivuilla. Selaa [käytettävissä olevien visualisointien ja niiden opetusohjelmien luetteloa.](power-bi-visualization-types-for-reports-and-q-and-a.md) 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>Mukautetun visualisoinnin lataaminen ja käyttäminen Power BI:ssä

Lisää oma tai [Microsoft AppSource -yhteisösivustosta](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) löytämäsi mukautettu visualisointi. Oletko luova henkilö? Tutustu lähdekoodiimme ja luo [kehittäjien työkalujen](../developer/custom-visual-develop-tutorial.md) avulla uusi visualisointityyppi. Halutessasi voit [jakaa sen yhteisölle](../developer/office-store.md). Saat lisätietoja mukautetun visualisoinnin kehittämisestä [Power BI:n mukautetun visualisoinnin kehittäminen](../developer/custom-visual-develop-tutorial.md) -ohjeartikkelista.

## <a name="change-the-visualization-type"></a>Visualisointityypin muuttaminen

Kokeile [muuttaa visualisointityyppiä](power-bi-report-change-visualization-type.md) ja tutki, mikä toimii parhaiten omien tietojesi kohdalla.

## <a name="pin-the-visualization"></a>Visualisoinnin kiinnittäminen

Power BI -palvelussa visualisointeja voi [kiinnittää koontinäyttöön](../service-dashboard-pin-tile-from-report.md) ruutuna. Jos muutat visualisointia kiinnittämisen jälkeen, koontinäytön ruutu ei muutu – jos se oli viivakaavio, se pysyy viivakaaviona, vaikka muuttaisit sen raportissa rengaskaavioksi.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat
- Visualisoinnin voi ladata hitaasti tietolähteen ja (mittareilla tai sarakkeilla) kenttien määrän mukaan.  On suositeltavaa rajoittaa visualisoinnit 10 – 20 yhteensä kenttiin, sekä luettavuutta ja suorituskyvyn syistä. 

- Visualisointien yläraja on 100 kentät (mittareilla tai sarakkeilla). Jos visualisoinnin lataaminen epäonnistuu, pienentää kenttien määrän.   

## <a name="next-steps"></a>Seuraavat vaiheet

* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [Mukautetut visualisoinnit](../power-bi-custom-visuals.md)