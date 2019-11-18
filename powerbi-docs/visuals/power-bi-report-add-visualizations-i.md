---
title: Visualisointien lisääminen Power BI -raporttiin, osa 1
description: Visualisointien lisääminen Power BI -raporttiin, osa 1
author: mihart
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/28/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d68abc7b4509595d4dfa3071dc56673e6af89e4f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73871057"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>Visualisointien lisääminen Power BI -raporttiin, osa 1

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Tässä artikkelissa annetaan lyhyt esittely visualisointien lisäämisestä raporttiin. Se koskee sekä Power BI -palvelua että Power BI Desktopia. Katso lisätietoja edistyneemmästä sisällöstä tämän sarjan [osasta 2](power-bi-report-add-visualizations-ii.md). Katso kuinka Amanda esittelee joitakin eri tapoja, joilla raportille voidaan luoda visualisointeja ja kuinka niitä voidaan muokata ja muotoilla. Voit sitten kokeilla itse luomalla oman raportin [Myynti- ja markkinointimallista](../sample-datasets.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Edellytykset

Tässä opetusohjelmassa käytetään [myynti- ja markkinointi -PBIX-tiedostoa](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix).

1. Valitse Power BI Desktopin valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. Etsi oma **myynti- ja markkinointi -PBIX-tiedostosi**

1. Avaa **myynti- ja markkinointi -PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.

## <a name="add-visualizations-to-the-report"></a>Visualisointien lisääminen raporttiin

1. Luo visualisointi vetämällä kenttä **Kentät**-ruudussa.

    Aloita numeerisesta kentästä, kuten **Sales** > **TotalSales**. Power BI luo pylväskaavion, jossa on yksi pylväs.

    ![Näyttökuva pylväskaaviosta, jossa on yksi pylväs.](media/power-bi-report-add-visualizations-i/power-bi-column-chart.png)

    Tai voit aloittaa luokkakentästä, kuten **Nimi** tai **Tuote**. Power BI luo taulukon ja lisää tämän kentän **Arvot**-säilöön.

    ![Näyttökuva taulukosta, jossa on neljä luokkaa](media/power-bi-report-add-visualizations-i/power-bi-product.png)

    Tai aloita paikkatietokentästä, kuten **Alue** > **Kaupunki**. Power BI ja Bing Maps luovat karttavisualisoinnin.

    ![Näyttökuva karttavisualisoinnista.](media/power-bi-report-add-visualizations-i/power-bi-maps.png)

## <a name="change-the-type-of-visualization"></a>Visualisoinnin tyypin vaihtaminen

 Luo visualisointi ja muuta sitten sen tyyppiä. 
 
 1. Valitse **Tuote** > **Luokka** ja sitten **Tuote** > **Tuotteen määrä** lisätäksesi ne molemmat **Arvot**-säilöön.

    ![Näyttökuva Kentät-ruudusta, jossa on korostettu Arvot-säilö.](media/power-bi-report-add-visualizations-i/power-bi-create-visual.png)

1. Muuta visualisointi pylväskaavioksi valitsemalla **pinotun pylväskaavion kuvake**.

   ![Näyttökuva visualisointiruudusta, jossa on korostettu pinotun pylväskaavion kuvake.](media/power-bi-report-add-visualizations-i/power-bi-convert.png)

1. Muuta visualisoinnin lajittelutapaa valitsemalla **Enemmän vaihtoehtoja** (...).  Lajitteluasetusten avulla voit muuttaa lajittelun suuntaa (nouseva tai laskeva) lajitteluperusteena käytettävää saraketta (**Lajitteluperuste**).

   ![Näyttökuva Lisää toimintoja -valikosta.](media/power-bi-report-add-visualizations-i/power-bi-sort.png)
  
## <a name="next-steps"></a>Seuraavat vaiheet

 Jatka kohtaan:

* [Osa 2: Visualisointien lisääminen Power BI -raporttiin](power-bi-report-add-visualizations-ii.md)

* Toimia raportin [visualisointien kanssa](../consumer/end-user-reading-view.md).

