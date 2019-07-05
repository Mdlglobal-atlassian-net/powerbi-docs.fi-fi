---
title: Visualisointien lisääminen Power BI -raporttiin, osa 1
description: Visualisointien lisääminen Power BI -raporttiin, osa 1
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/17/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c5838d12351c06d0a76a975c9c473b1c00856d97
ms.sourcegitcommit: 90aa7ea5fcc7cf0fd7f6c3c1efeff5f27e8ef0dd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/20/2019
ms.locfileid: "67299149"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>Visualisointien lisääminen Power BI -raporttiin, osa 1

Tässä artikkelissa annetaan lyhyt esittely visualisointien lisäämisestä raporttiin. Se koskee sekä Power BI -palvelua että Power BI Desktopia. Katso lisätietoja edistyneemmästä sisällöstä tämän sarjan [osasta 2](power-bi-report-add-visualizations-ii.md). Katso kuinka Amanda esittelee joitakin eri tapoja, joilla raportille voidaan luoda visualisointeja ja kuinka niitä voidaan muokata ja muotoilla. Voit sitten kokeilla itse luomalla oman raportin [Myynti- ja markkinointimallista](../sample-datasets.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="open-a-report-and-add-a-new-page"></a>Raportin avaaminen ja uuden sivun lisääminen

1. Avaa [raportti muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md).

    Tässä opetusohjelmassa käytetään [myynti- ja markkinointimallia](../sample-datasets.md).

1. Jos **Kentät**-ruutu ei ole näkyvissä, valitse nuolikuvake sen avaamiseksi.

   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)

1. Lisää raporttiin tyhjä sivu.

## <a name="add-visualizations-to-the-report"></a>Visualisointien lisääminen raporttiin

1. Luo visualisointi vetämällä kenttä **Kentät**-ruudussa.

    Aloita numeerisesta kentästä, kuten **SalesFact** > **Sales $** . Power BI luo pylväskaavion, jossa on yksi pylväs.

    ![Näyttökuva pylväskaaviosta, jossa on yksi pylväs.](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)

    Tai voit aloittaa luokkakentästä, kuten **Nimi** tai **Tuote**. Power BI luo taulukon ja lisää tämän kentän **Arvot**-säilöön.

    ![GIF-kuva henkilöstä valitsemassa tuotetta ja sitten luokkaa taulukon luomiseksi.](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)

    Tai aloita paikkatietokentästä, kuten **Alue** > **Kaupunki**. Power BI ja Bing Maps luovat karttavisualisoinnin.

    ![Näyttökuva karttavisualisoinnista.](media/power-bi-report-add-visualizations-i/power-bi-map.png)

1. Luo visualisointi ja muuta sitten sen tyyppiä. Valitse **Tuote** > **Luokka** ja sitten **Tuote** > **Tuotteen määrä** lisätäksesi ne molemmat **Arvot**-säilöön.

   ![Näyttökuva Kentät-ruudusta, jossa on korostettu Arvot-säilö.](media/power-bi-report-add-visualizations-i/part1table1.png)

1. Muuta visualisointi pylväskaavioksi valitsemalla **pinotun pylväskaavion kuvake**.

   ![Näyttökuva visualisointiruudusta, jossa on korostettu pinotun pylväskaavion kuvake.](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)

1. Kun olet luonut visualisointeja raporttiin, voit [kiinnittää ne raporttinäkymään](../service-dashboard-pin-tile-from-report.md). Kiinnittääksesi visualisoinnin, valitse kiinnityskuvake ![Näyttökuva kiinnityskuvakkeesta.](media/power-bi-report-add-visualizations-i/pinnooutline.png).

   ![Näyttökuva pylväskaaviovisualisoinnista, jossa on korostettu kiinnityskuvake.](media/power-bi-report-add-visualizations-i/part1pin1.png)
  
## <a name="next-steps"></a>Seuraavat vaiheet

 Jatka kohtaan:

* [Osa 2: Visualisointien lisääminen Power BI -raporttiin](power-bi-report-add-visualizations-ii.md)

* [Käsittele raportin visualisointeja](../consumer/end-user-reading-view.md).

* [Luo lisää visualisointeja](power-bi-report-visualizations.md).

* [Tallenna raporttisi](../service-report-save.md).
