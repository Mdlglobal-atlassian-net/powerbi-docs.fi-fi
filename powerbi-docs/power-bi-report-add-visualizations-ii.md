---
title: 'Osa 2: visualisointien lisääminen Power BI -raporttiin (opetusohjelma)'
description: 'Opetusohjelma: visualisointien lisääminen Power BI -raporttiin (osa 2)'
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 567bece0089a01170e218af9606331e44cb7834f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973912"
---
# <a name="part-2-add-visualizations-to-a-power-bi-report-tutorial"></a>Osa 2: visualisointien lisääminen Power BI -raporttiin (opetusohjelma)
[Osassa 1](power-bi-report-add-visualizations-ii.md) opettelit luomaan tavallisia visualisointeja valitsemalla kenttien nimien vieressä olevia valintaruutuja.  Osassa 2 opetetaan luomaan visualisointeja ja muokkaamaan niitä vetämis- ja pudottamistoiminnon avulla sekä hyödyntämällä **Kentät**- ja **Visualisoinnit**-paneeleja.

### <a name="prerequisites"></a>Edellytykset
- [Osa 1](power-bi-report-add-visualizations-ii.md)
- Power BI -palvelu – Raportteihin voi lisätä visualisointeja käyttämällä joko Power BI -palvelua tai Power BI Desktopia. Tässä opetusohjelmassa käytetään Power BI -palvelua. 
- Jälleenmyyntianalyysimalli

## <a name="create-a-new-visualization"></a>Uuden visualisoinnin luominen
Tässä opetusohjelmassa perehdymme jälleenmyyntianalyysimallin tietojoukkoon ja luomme siitä muutamia olennaisimpia visualisointeja.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Avaa raportti ja lisää uusi tyhjä sivu.
1. Avaa työtila, johon olet tallentanut jälleenmyyntianalyysimallin. Avaa raportti lukunäkymässä valitsemalla **Jälleenmyyntianalyysimalli**.
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-report.png)
2. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.
   
   ![](media/power-bi-report-add-visualizations-ii/editreport1.png)
3. [Lisää uusi sivu](power-bi-report-add-page.md) valitsemalla alareunasta keltainen plus-kuvake.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_addreportpage.png)

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Lisää visualisointi, jossa esitetään tämän vuoden myynti viime vuoteen verrattuna.
1. Valitse **Myynti**-taulukosta **Myynti tänä vuonna** > **Arvo** ja **Myynti edellisvuonna**. Power BI luo pylväskaavion.  Se näyttää kiinnostavalta, joten haluat perehtyä myyntiin tarkemmin. Miltä myynti näyttää kuukausittain?  
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_4bnew.png)
2. Vedä Aika-taulukosta **Akseli**-alueelle **Kuukausi**.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_5newnew.png)
3. [Vaihda visualisointi](power-bi-report-change-visualization-type.md) aluekaavioksi.  Valittavissa on monenlaisia visualisointityyppejä. Voit päättää, mitä niistä haluat käyttää katsomalla [niiden kuvaukset, vinkit parhaista käytännöistä ja opetusohjelmia](power-bi-visualization-types-for-reports-and-q-and-a.md). Valitse Visualisoinnit-ruudusta aluekaavion kuvake.
4. Lajittele visualisointi valitsemalla kolme pistettä (...) ja valitsemalla **Lajitteluperuste: kuukausi**.
5. [Muokkaa visualisoinnin kokoa](power-bi-visualization-move-and-resize.md) valitsemalla visualisointi, tarttumalla kiinni yhdestä sen kehyksessä olevista ympyröistä ja vetämällä. Tee visualisoinnista niin suuri, ettei vierityspalkkia enää näy, ja niin pieni, että tilaa jää toisellekin visualisoinnille.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Tallenna raportti](service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Lisää karttavisualisointi, joka näyttää myynnin sijainnin mukaan.
1. Valitse **Kauppa**-taulukosta **Alue**. Power BI tunnistaa, että Alue-arvo tarkoittaa sijaintia, ja luo karttavisualisoinnin.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_8newnew.png)
2. Vedä Koko-alueelle vaihtoehto **Myymälöitä yhteensä**.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-reportnew.png)
3. Lisää visualisoinnille selite.  Jos haluat nähdä tiedot kaupan nimen mukaan, vedä selitealueelle vaihtoehto **Ketju**.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-report-3new.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* Lisätietoja Kentät-ruudusta on ohjeaiheessa [Raporttieditorin esittely](service-the-report-editor-take-a-tour.md).   
* Ohjeet visualisointien suodattamiseen ja korostamiseen on ohjeaiheessa [Tietoja Power BI -raporttien suodattimista ja korostamisesta](power-bi-reports-filters-and-highlighting.md).  
* Lisätietoja [Power BI -raporttien visualisoinneista](power-bi-report-visualizations.md).  
* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

