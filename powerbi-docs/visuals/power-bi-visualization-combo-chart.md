---
title: Yhdistelmäkaavio Power BI:ssä
description: Tässä opetusohjelmassa kerrotaan yhdistelmäkaavioiden käytöstä ja luonnista Power BI -palvelussa ja Power BI Desktopissa.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 896c415028b99db8662e93b5d709b76520996fef
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54275751"
---
# <a name="combo-chart-in-power-bi"></a>Yhdistelmäkaavio Power BI:ssä
Power BI:ssä yhdistelmäkaavio on yksittäinen visualisointi, joka yhdistää viivakaavion ja pylväskaavion. Näiden kahden kaavion yhdistäminen nopeuttaa tietojen vertailua.

Yhdistelmäkaaviossa voi olla yksi tai kaksi Y-akselia.

## <a name="when-to-use-a-combo-chart"></a>Milloin kannattaa käyttää yhdistelmäkaaviota
Yhdistelmäkaavio on hyvä vaihtoehto, kun:

* sinulla on viivakaavio ja pylväskaavio, joilla on sama X-akseli
* haluat vertailla useita mittareita eri arvoalueilla
* haluat havainnollistaa kahden mittarin välistä korrelaatiota yhdessä visualisoinnissa
* haluat tarkistaa, täyttääkö mittari toisen mittarin määrittämän tavoitteen
* haluat säästää tilaa piirtoalustalla.

### <a name="prerequisites"></a>Edellytykset
Yhdistelmäkaaviot ovat käytettävissä Power BI -palvelussa ja Power BI Desktopissa. Tässä opetusohjelmassa luodaan yhdistelmäkaavio Power BI -palvelussa. Seuraa opetusohjelmaa avaamalla Power BI -palvelu ja muodostamalla yhteys jälleenmyyntianalyysimalliin ([ohjeet alla](#create)).


## <a name="create-a-basic-single-axis-combo-chart"></a>Perusmuotoisen yhden akselin yhdistelmäkaavion luominen
Seuraavassa videossa luodaan yhdistelmäkaavio käyttämällä myynti- ja markkinointimallia.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a> Luo oma yhdistelmäkaavio kirjautumalla Power BI -palveluun ja valitsemalla **Nouda tiedot \> Mallit \> Jälleenmyyntianalyysimalli > Yhdistä > Siirry koontinäyttöön**.

1. Avaa raportti valitsemalla koontinäytössä **Myymälöitä yhteensä** -ruutu.
2. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.
3. Lisää uusi raporttisivu.
4. Luo pylväskaavio, joka näyttää tämän vuoden myynnin ja myyntikatteen kuukauden mukaan.

    a.  Valitse Kentät-ruudussa **Myynti** \> **Tämän vuoden myynti** > **Arvo**.

    b.  Vedä **Myynti** \> **Tämän vuoden myyntikate** **Arvo**-kohtaan.

    c.  Valitse **Aika** \> **FiscalMonth** ja lisää se **Akseli**-kohtaan.

    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Valitse kolme pistettä (...) visualisoinnin oikeasta yläkulmasta ja valitse **Lajitteluperuste > FiscalMonth**. Jos haluat muuttaa lajittelujärjestyksen, valitse kolme pistettä uudelleen ja valitse joko **Lajittele nousevaan järjestykseen** tai **Lajittele laskevaan järjestykseen**.

6. Muunna pylväskaavio yhdistelmäkaavioksi. Käytettävissä on kaksi erilaista yhdistelmäkaaviota: **viivakaavio ja pinottu pylväskaavio** sekä **viivakaavio ja lohkopylväskaavio**. Pidä pylväskaavio valittuna ja valitse **Visualisoinnit**-ruudussa **Viiva- ja yhdistelmäpylväskaavio**.

    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. Vedä **Kentät**-ruudusta **Myynti** \> **Edellisen vuoden myynti** säilöön **Riviarvot**.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Yhdistelmäkaavion pitäisi näyttää suunnilleen tältä:

   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Kahden akselin yhdistelmäkaavion luominen
Tässä tehtävässä verrataan myyntikatetta ja myyntiä.

1. Luo uusi viivakaavio, joka seuraa **viime vuoden myyntikateprosenttia** **kuukauden** mukaan. Valitse kolme pistettä ja lajittele kaavio **kuukauden** mukaan **nousevassa järjestyksessä**.  
Myyntikate oli tammikuussa 35 %, huipussaan 45 % huhtikuussa, laski heinäkuussa ja nousi uudelleen elokuussa. Näemmekö samanlaisen kuvion edellisen ja tämän vuoden myynnissä?

   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. Lisää **Tämän vuoden myynti > Arvo** ja **Edellisen vuoden myynti** viivakaavioon. **Edellisen vuoden myyntikateprosentin** asteikko on paljon pienempi kuin **myynnin**, mikä vaikeuttaa vertailua.      

   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Voit helpottaa visualisoinnin tulkitsemista muuntamalla viivakaavion viivakaavioksi ja pinotuksi pylväskaavioksi.

   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. Vedä **Edellisen vuoden myyntikateprosentti** **sarakearvoista** **riviarvoihin**. Power BI luo kaksi akselia, jolloin tietojoukkoja voidaan skaalata erikseen; vasen mittaa myyntiä euroissa ja oikea prosenttilukua. Saat vastauksen kysymykseen; kyllä, samanlainen kuvio on havaittavissa.

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

* [Yhdistelmäkaavion lisääminen koontinäytön ruutuna](../service-dashboard-tiles.md)
* [Tallenna raportti](../service-report-save.md).
* [Tee raportista helpommin käytettävä toimintarajoitteisille ihmisille](../desktop-accessibility.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Ristiinkorostaminen ja ristiinsuodatus

Sarakkeen tai rivin korostaminen yhdistelmäkaaviossa ristiinkorostaa ja ristiinsuodattaa muut raporttisivulla olevat visualisoinnit... ja päinvastoin. Voit muuttaa tätä oletustoimintaa [visualisointitoimien](../service-reports-visual-interactions.md) avulla.

## <a name="next-steps"></a>Seuraavat vaiheet

[Rengaskaaviot Power BI:ssä](power-bi-visualization-doughnut-charts.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
