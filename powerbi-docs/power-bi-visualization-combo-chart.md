---
title: Opetusohjelma – Yhdistelmäkaavio
description: Tässä opetusohjelmassa kerrotaan yhdistelmäkaavioiden käytöstä ja luonnista Power BI -palvelussa ja Power BI Desktopissa.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: lnv66cTZ5ho
qualityfocus: monitoring
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: b5e89a9a1f2e88ed793dff6457b58fd9ac609ef5
ms.sourcegitcommit: e571de2afa3f34fac06a6aab0df0e8940cb00a0d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/05/2018
ms.locfileid: "30976777"
---
# <a name="combo-chart-in-power--tutorial"></a>Yhdistelmäkaavio Power BI:ssä (opetusohjelma)
Power BI:ssä yhdistelmäkaavio on yksittäinen visualisointi, joka yhdistää viivakaavion ja pylväskaavion. Näiden kahden kaavion yhdistäminen nopeuttaa tietojen vertailua.

Yhdistelmäkaaviossa voi olla yksi tai kaksi Y-akselia.

## <a name="when-to-use-a-combo-chart"></a>Milloin kannattaa käyttää yhdistelmäkaaviota
Yhdistelmäkaavio on hyvä vaihtoehto, kun:

* sinulla on viivakaavio ja pylväskaavio, joilla on sama X-akseli
* haluat vertailla useita mittayksiköitä eri arvoalueilla
* haluat havainnollistaa kahden mittayksikön välistä korrelaatiota yhdessä visualisoinnissa
* haluat tarkistaa, täyttääkö mittayksikkö toisen mittayksikön määrittämän tavoitteen
* haluat säästää tilaa piirtoalustalla.

### <a name="prerequisites"></a>Edellytykset
Yhdistelmäkaaviot ovat käytettävissä Power BI -palvelussa ja Power BI Desktopissa. Tässä opetusohjelmassa luodaan yhdistelmäkaavio Power BI -palvelussa. Seuraa opetusohjelmaa avaamalla Power BI -palvelu ja muodostamalla yhteys jälleenmyyntianalyysimalliin ([ohjeet alla](#create)).


## <a name="create-a-basic-single-axis-combo-chart"></a>Perusmuotoisen yhden akselin yhdistelmäkaavion luominen
Seuraavassa videossa luodaan yhdistelmäkaavio käyttämällä myynti- ja markkinointimallia.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a> Luo oma yhdistelmäkaavio kirjautumalla Power BI -palveluun ja valitsemalla **Nouda tiedot \> Mallit \> Jälleenmyyntianalyysimalli > Yhdistä > Siirry koontinäyttöön**.

1. Avaa raportti valitsemalla koontinäytössä **Myymälöitä yhteensä** -ruutu.
2. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.
3. [Lisää uusi raporttisivu](power-bi-report-add-page.md).
4. Luo pylväskaavio, joka näyttää tämän vuoden myynnin ja myyntikatteen kuukauden mukaan.

    a.  Valitse Kentät-ruudussa **Myynti** \> **Tämän vuoden myynti** > **Arvo**.

    b.  Vedä **Myynti** \> **Tämän vuoden myyntikate** **Arvo**-kohtaan.

    c.  Valitse **Aika** \> **FiscalMonth** ja lisää se **Akseli**-kohtaan.

    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Valitse kolme pistettä (...) visualisoinnin oikeassa yläkulmassa ja valitse **Lajitteluperuste: FiscalMonth**. Joudut ehkä valitsemaan sen kahdesti, jos haluat lajitella nousevaan tai laskevaan järjestykseen.

6. Muunna pylväskaavio yhdistelmäkaavioksi. Pidä pylväskaavio valittuna ja valitse **Visualisoinnit**-ruudussa **Viiva- ja yhdistelmäpylväskaavio**.

    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. Vedä **Kentät**-ruudusta **Myynti** \> **Edellisen vuoden myynti** säilöön **Riviarvot**.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Yhdistelmäkaavion pitäisi näyttää suunnilleen tältä:

   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Kahden akselin yhdistelmäkaavion luominen
Tässä tehtävässä verrataan myyntikatetta ja myyntiä.

1. Luo uusi viivakaavio, joka seuraa **viime vuoden myyntikateprosenttia** **kuukauden** mukaan.  Myyntikate oli tammikuussa 35 %, huipussaan 45 % huhtikuussa, laski heinäkuussa ja nousi uudelleen elokuussa. Näemmekö samanlaisen kuvion myös tämän vuoden myynnissä?

   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. Lisää **Tämän vuoden myynti > Arvo** ja **Edellisen vuoden myynti** viivakaavioon. **Edellisen vuoden myyntikateprosentin** asteikko on paljon pienempi kuin **myynnin**, mikä vaikeuttaa vertailua.      

   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Voit helpottaa visualisoinnin tulkitsemista muuntamalla viivakaavion viivakaavioksi ja pinotuksi pylväskaavioksi.

   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. Vedä **Edellisen vuoden myyntikateprosentti** **sarakearvoista** **riviarvoihin**. Power BI luo kaksi akselia, jolloin tietojoukkoja voidaan skaalata erikseen; vasen mittaa myyntiä euroissa ja oikea prosenttilukua.

   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>Akselien otsikoiden lisääminen
1. Avaa Muotoilu-ruutu valitsemalla maalitelakuvakkeen ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png).
2. Laajenna **Y-akselin** asetukset alanuolella.
3. Aseta **Y-akseli (sarake)** > **Sijainti** > **vasemmalla**, **Otsikko** > **Käytössä**, **Tyyli** > **Näytä vain otsikko** ja **Näytä** > **Miljoonat**.

   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. Kohdassa **Y-akseli (sarake)** vieritä alaspäin ja varmista, että **Näytä toissijainen** on **Käytössä**. Tämä näyttää yhdistelmäkaavion viivakaavio-osan muotoiluvaihtoehdot.

   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. Jätä **Y-akseli (rivi)** > **Sijainti** > **oikealla** sekä määritä **Otsikko** > **Käytössä** ja **Tyyli** > **Näytä vain otsikko**.

   Yhdistelmäkaavio näyttää nyt kaksi akselia otsikoilla.

   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

6. Halutessasi voit parantaa kaavion luettavuutta muokkaamalla tekstin fonttia, kokoa ja väriä sekä määrittämällä muita muotoiluasetuksia.

Seuraavat toiminnot:

* [Yhdistelmäkaavion lisääminen koontinäytön ruutuna](service-dashboard-tiles.md)
* [Raportin tallentaminen](service-report-save.md)

## <a name="cross-highlighting-and-cross-filtering"></a>Ristiinkorostaminen ja ristiinsuodatus

Sarakkeen tai rivin korostaminen yhdistelmäkaaviossa ristiinkorostaa ja ristiinsuodattaa muut raporttisivulla olevat visualisoinnit... ja päinvastoin. Voit muuttaa tätä oletustoimintaa [visualisointitoimien](service-reports-visual-interactions.md) avulla.

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI -raporttien visualisointien yleiskatsaus](power-bi-report-visualizations.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
