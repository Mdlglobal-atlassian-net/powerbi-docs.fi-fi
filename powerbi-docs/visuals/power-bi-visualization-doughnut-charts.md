---
title: Rengaskaaviot Power BI:ssä
description: Rengaskaaviot Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/23/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3bf0aa516f50d363b53d2ed91b86d999e7855c30
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/21/2018
ms.locfileid: "46545018"
---
# <a name="doughnut-charts-in-power-bi"></a>Rengaskaaviot Power BI:ssä
Rengaskaavio muistuttaa ympyräkaaviota siten, että se näyttää osien suhteen kokonaisuuteen. Ainoa ero on se, että keskellä on tyhjää tilaa otsikkoa tai kuvaketta varten.

## <a name="create-a-doughnut-chart"></a>Rengaskaavion luominen
Näissä ohjeissa käytetään esimerkkiä jälleenmyyjän analyysista. Sen avulla voit luoda rengaskaavion tämän vuoden myynnistä luokittain. Jos haluat seurata ohjeita itse, [lataa malli](../sample-datasets.md) joko Power BI ‑palveluun (app.powerbi.com) tai Power BI Desktopiin.

1. Aloita [tyhjältä raporttisivulta](../power-bi-report-add-page.md) ja valitse kenttä **Myyntivaihe** \> **Myyntivaihe**. Jos käytät Power BI ‑palvelua, varmista, että avaat raportin [muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md).

2. Valitse Kentät-ruudussa **Myynti** \> **Viime vuoden myynti**.  
   
3. Valitse Visualisointi-ruudusta ![rengaskaavion kuvake]() muuntamaan pylväskaavio rengaskaavioksi. Jos **Viime vuoden myynti** ei ole **Arvot**-alueella, vedä se sinne.
     
   ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Valitse **Kohteen** \> **luokka** sen lisäämiseksi **Selite**-alueelle. 
     
    ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. Voit vaihtoehtoisesti [säätää kaavion tekstin väriä ja kokoa](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Rengaskaavion arvojen summan on oltava 100 %.
* Liian monta luokkaa vaikeuttaa luettavuutta ja tulkintaa.
* Rengaskaavioita kannattaa käyttää vertailemaan tiettyä osaa kokonaisuuteen sen sijaan, että verrattaisiin yksittäisiä osia keskenään. 

## <a name="next-steps"></a>Seuraavat vaiheet
[Raportit Power BI:ssä](../consumer/end-user-reports.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Visualisoinnit Power BI -raporteissa](power-bi-report-visualizations.md)

[Power BI:n peruskäsitteet](../consumer/end-user-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

