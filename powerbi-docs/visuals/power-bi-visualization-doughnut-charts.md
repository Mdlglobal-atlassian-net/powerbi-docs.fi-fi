---
title: Rengaskaaviot Power BI:ssä
description: Rengaskaaviot Power BI:ssä
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/05/2020
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: 2e2c108a5d05c7095526a813d33bed718f68f4c4
ms.sourcegitcommit: a199dda2ab50184ce25f7c9a01e7ada382a88d2c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/06/2020
ms.locfileid: "82865341"
---
# <a name="create-and-use-doughnut-charts-in-power-bi"></a>Rengaskaavioiden luominen ja käyttäminen Power BI:ssa

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Rengaskaavio muistuttaa ympyräkaaviota siten, että se näyttää osien suhteen kokonaisuuteen. Ainoa ero on se, että keskellä on tyhjää tilaa otsikkoa tai kuvaketta varten.

## <a name="prerequisite"></a>Edellytys

Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.


> [!NOTE]
> Raportin jakaminen työtoverin kanssa Power BI:ssä edellyttää, että teillä kummallakin on oma Power BI Pro -käyttöoikeus tai että raportti on tallennettu Premium-kapasiteettiin.    

## <a name="create-a-doughnut-chart"></a>Rengaskaavion luominen

1. Aloita tyhjältä raporttisivulta ja valitse Kentät-ruudusta **Myynti**\>**Viime vuoden myynti**.  
   
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


