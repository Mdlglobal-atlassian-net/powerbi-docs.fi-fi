---
title: Visualisointien lisääminen Power BI -raporttiin, osa 2
description: Visualisointien lisääminen Power BI -raporttiin, osa 2
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: a15975f456bab94fd04fa7501760c9874fabf952
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/12/2018
ms.locfileid: "44732649"
---
# <a name="part-2-add-visualizations-to-a-power-bi-report"></a>Visualisointien lisääminen Power BI -raporttiin, osa 2
[Osassa 1](power-bi-report-add-visualizations-ii.md) opettelit luomaan tavallisia visualisointeja valitsemalla kenttien nimien vieressä olevia valintaruutuja.  Osassa 2 opetetaan luomaan visualisointeja ja muokkaamaan niitä vetämis- ja pudottamistoiminnon avulla sekä hyödyntämällä **Kentät**- ja **Visualisoinnit**-paneeleja.

### <a name="prerequisites"></a>Edellytykset
- [Osa 1](power-bi-report-add-visualizations-ii.md)
- Power BI Desktop – Raportteihin voi lisätä visualisointeja käyttämällä joko Power BI -palvelua tai Power BI Desktopia. Tässä opetusohjelmassa käytetään Power BI Desktopia. 
- [Jälleenmyyntianalyysimalli](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

## <a name="create-a-new-visualization"></a>Uuden visualisoinnin luominen
Tässä opetusohjelmassa perehdymme jälleenmyyntianalyysimallin tietojoukkoon ja luomme siitä muutamia olennaisimpia visualisointeja.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Avaa raportti ja lisää uusi tyhjä sivu.
1. Avaa jälleenmyyntianalyysin .PBIX-mallitiedosto Power BI Desktop -versiossa. 
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-desktop.png)   

2.  [Lisää uusi sivu](../power-bi-report-add-page.md) valitsemalla alareunasta keltainen plus-kuvake.

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Lisää visualisointi, jossa esitetään tämän vuoden myynti viime vuoteen verrattuna.
1. Valitse **Myynti**-taulukosta **Myynti tänä vuonna** > **Arvo** ja **Myynti edellisvuonna**. Power BI luo pylväskaavion.  Se näyttää kiinnostavalta, joten haluat perehtyä myyntiin tarkemmin. Miltä myynti näyttää kuukausittain?  
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-barchart.png)
2. Vedä Aika-taulukosta **Akseli**-alueelle **FiscalMonth**.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-month.png)
3. [Vaihda visualisointi](power-bi-report-change-visualization-type.md) aluekaavioksi.  Valittavissa on monenlaisia visualisointityyppejä. Voit päättää, mitä niistä haluat käyttää katsomalla [niiden kuvaukset, vinkit parhaista käytännöistä ja opetusohjelmia](power-bi-visualization-types-for-reports-and-q-and-a.md). Valitse Visualisoinnit-ruudusta aluekaavion kuvake ![](media/power-bi-report-add-visualizations-ii/power-bi-areachart.png).
4. Lajittele visualisointi valitsemalla kolme pistettä ja valitsemalla **Lajitteluperuste: FiscalMonth**.
5. [Muokkaa visualisoinnin kokoa](power-bi-visualization-move-and-resize.md) valitsemalla visualisointi, tarttumalla kiinni yhdestä sen kehyksessä olevista ympyröistä ja vetämällä. Tee visualisoinnista niin suuri, ettei vierityspalkkia enää näy, ja niin pieni, että tilaa jää toisellekin visualisoinnille.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Tallenna raportti](../service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Lisää karttavisualisointi, joka näyttää myynnin sijainnin mukaan.
1. Valitse **Kauppa**-taulukosta **Alue**. Power BI tunnistaa, että Alue-arvo tarkoittaa sijaintia, ja luo karttavisualisoinnin.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map.png)
2. Vedä Koko-alueelle vaihtoehto **Myymälöitä yhteensä**.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map2.png)
3. Lisää visualisoinnille selite.  Jos haluat nähdä tiedot kaupan nimen mukaan, vedä selitealueelle vaihtoehto **Ketju**.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-legend.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* Lisätietoja [Power BI -raporttien visualisoinneista](power-bi-report-visualizations.md).  
* Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

