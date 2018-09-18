---
title: Visualisointien lisääminen Power BI -raporttiin, osa 1
description: Visualisointien lisääminen Power BI -raporttiin, osa 1
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8095db86b8954b3f91a83f2e83c0108d1676cf76
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/12/2018
ms.locfileid: "44736382"
---
# <a name="part-i-add-visualizations-to-a-power-bi-report"></a>Visualisointien lisääminen Power BI -raporttiin, osa 1
Tässä artikkelissa annetaan lyhyt esittely visualisointien lisäämisestä raporttiin joko Power BI -palvelulla tai Power BI Desktopilla.  Katso lisätietoja edistyneemmästä sisällöstä [osasta II](power-bi-report-add-visualizations-ii.md). Katso kuinka Amanda esittelee joitakin eri tapoja, joilla raportille voidaan luoda visualisointeja ja kuinka niitä voidaan muokata ja muotoilla. Voit sitten kokeilla itse luomalla oman raportin [Myynti- ja markkinointimallista](../sample-datasets.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="open-a-report-and-add-a-new-page"></a>Raportin avaaminen ja uuden sivun lisääminen
1. Avaa [raportti muokkausnäkymässä](../service-reading-view-and-editing-view.md). Tässä opetusohjelmassa käytetään [myynti- ja markkinointimallia](../sample-datasets.md).
2. Jos Kentät-ruutu ei ole näkyvissä, valitse nuolikuvake sen avaamiseksi. 
   
   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)
3. [Lisää raporttiin tyhjä sivu](../power-bi-report-add-page.md).

## <a name="add-visualizations-to-the-report"></a>Visualisointien lisääminen raporttiin
1. Luo visualisointi vetämällä kenttä **Kentät**-ruudussa.  
   
   **Aloita numeerisesta kentästä**, kuten SalesFact > Myynti $. Power BI luo pylväskaavion, jossa on yksi pylväs.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)
   
   **Voit aloittaa myös luokkakentästä**, kuten nimi tai tuote: Power BI luo taulukon ja lisää kentän **arvoihin**.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)
   
   **Tai aloita paikkatietokentästä**, kuten Alue > Kaupunki. Power BI ja Bing Maps luovat karttavisualisoinnin.
   
   ![](media/power-bi-report-add-visualizations-i/power-bi-map.png)
2. Luo visualisointi ja muuta sitten sen tyyppiä. Valitse **Tuote > Luokka** ja **Tuote > Tuotteen määrä** lisätäksesi ne molemmat **arvoihin**.
   
   ![](media/power-bi-report-add-visualizations-i/part1table1.png)
3. Muuta visualisointi pylväskaavioksi valitsemalla pylväskaaviokuvake.
   
   ![](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)
4. Kun olet luonut visualisointeja raporttiin, voit [kiinnittää ne raporttinäkymään](../service-dashboard-pin-tile-from-report.md). Kiinnittääksesi visualisoinnin, valitse kiinnitä-kuvake ![](media/power-bi-report-add-visualizations-i/pinnooutline.png).
   
   ![](media/power-bi-report-add-visualizations-i/part1pin1.png)
  

## <a name="next-steps"></a>Seuraavat vaiheet
 Jatkaa [Osaan 2: Visualisointien lisääminen Power BI -raporttiin](power-bi-report-add-visualizations-ii.md)
   
   Toimia raportin [visualisointien kanssa](../service-reading-view-and-editing-view.md).
   
   [Luoda lisää visualisointeja](power-bi-report-visualizations.md).
   
   [Tallentaa raporttisi](../service-report-save.md).
