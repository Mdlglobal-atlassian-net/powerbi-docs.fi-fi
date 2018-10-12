---
title: Rengaskaaviot Power BI:ssä
description: Rengaskaaviot Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: ab292964bb1b6b1f4218d41c46eb2c28c82a034c
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/27/2018
ms.locfileid: "47416747"
---
# <a name="doughnut-charts-in-power-bi"></a>Rengaskaaviot Power BI:ssä
Rengaskaavio muistuttaa ympyräkaaviota siten, että se näyttää osien suhteen kokonaisuuteen. Ainoa ero on se, että keskellä on tyhjää tilaa otsikkoa tai kuvaketta varten.

## <a name="create-a-doughnut-chart"></a>Rengaskaavion luominen
Näissä ohjeissa käytetään esimerkkiä jälleenmyyjän analyysista. Sen avulla voit luoda rengaskaavion tämän vuoden myynnistä luokittain. Jos haluat seurata ohjeita itse, [lataa malli](../sample-datasets.md) joko Power BI ‑palveluun tai Power BI Desktopiin.

1. Aloita [tyhjältä raporttisivulta](../power-bi-report-add-page.md). Jos käytät Power BI ‑palvelua, varmista, että avaat raportin [muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md).

2. Valitse Kentät-ruudussa **Myynti** \> **Viime vuoden myynti**.  
   
3. Valitse Visualisointi-ruudusta ![rengaskaavion kuvake](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) muuntamaan pylväskaavio rengaskaavioksi. Jos **Viime vuoden myynti** ei ole **Arvot**-alueella, vedä se sinne.
     
   ![Rengaskaavio valittuna Visualisointi-ruudulla](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Valitse **Kohteen** \> **luokka** sen lisäämiseksi **Selite**-alueelle. 
     
    ![rengaskaavio Kentät-ruudun vieressä](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. Voit vaihtoehtoisesti [säätää kaavion tekstin väriä ja kokoa](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Rengaskaavion arvojen summan on oltava 100 %.
* Liian monta luokkaa vaikeuttaa luettavuutta ja tulkintaa.
* Rengaskaavioita kannattaa käyttää vertailemaan tiettyä osaa kokonaisuuteen sen sijaan, että verrattaisiin yksittäisiä osia keskenään. 

## <a name="next-steps"></a>Seuraavat vaiheet
[Suppilokaaviot Power BI:ssä](power-bi-visualization-funnel-charts.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)


