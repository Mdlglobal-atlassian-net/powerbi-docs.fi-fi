---
title: Rengaskaaviot Power BI:ssä
description: Rengaskaaviot Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 4c69113d245d47a4d2702f16f6cea21a6cbd3b0b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61136045"
---
# <a name="doughnut-charts-in-power-bi"></a>Rengaskaaviot Power BI:ssä
Rengaskaavio muistuttaa ympyräkaaviota siten, että se näyttää osien suhteen kokonaisuuteen. Ainoa ero on se, että keskellä on tyhjää tilaa otsikkoa tai kuvaketta varten.

## <a name="create-a-doughnut-chart"></a>Rengaskaavion luominen
Näissä ohjeissa käytetään esimerkkiä jälleenmyyjän analyysista. Sen avulla voit luoda rengaskaavion tämän vuoden myynnistä luokittain. Jos haluat seurata ohjeita itse, [lataa malli](../sample-datasets.md) joko Power BI ‑palveluun tai Power BI Desktopiin.

1. Aloita tyhjältä raporttisivulta. Jos käytät Power BI ‑palvelua, varmista, että avaat raportin [muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md).

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


