---
title: Yhdistelmäkaavio Power BI:ssä
description: Tässä opetusohjelmassa kerrotaan yhdistelmäkaavioiden käytöstä ja luonnista Power BI -palvelussa ja Power BI Desktopissa.
author: mihart
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/22/2020
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: 34d539af94f2bcbe03a2c9d6b870887e371a1a6e
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563911"
---
# <a name="create-and-use-combo-charts-in-power-bi"></a>Yhdistelmäkaavioiden luominen ja käyttäminen Power BI:ssa

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Power BI:ssä yhdistelmäkaavio on yksittäinen visualisointi, joka yhdistää viivakaavion ja pylväskaavion. Näiden kahden kaavion yhdistäminen nopeuttaa tietojen vertailua.

Yhdistelmäkaaviossa voi olla yksi tai kaksi Y-akselia.

## <a name="when-to-use-a-combo-chart"></a>Milloin kannattaa käyttää yhdistelmäkaaviota?
Yhdistelmäkaavio on hyvä vaihtoehto, kun:

* sinulla on viivakaavio ja pylväskaavio, joilla on sama X-akseli
* haluat vertailla useita mittareita eri arvoalueilla
* haluat havainnollistaa kahden mittarin välistä korrelaatiota yhdessä visualisoinnissa
* haluat tarkistaa, täyttääkö mittari toisen mittarin määrittämän tavoitteen
* haluat säästää tilaa piirtoalustalla.

> [!NOTE]
> Raportin jakaminen työtoverin kanssa Power BI:ssä edellyttää, että teillä kummallakin on oma Power BI Pro -käyttöoikeus tai että raportti on tallennettu Premium-kapasiteettiin.

### <a name="prerequisites"></a>Edellytykset
Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.



## <a name="create-a-basic-single-axis-combo-chart"></a>Perusmuotoisen yhden akselin yhdistelmäkaavion luominen
Seuraavassa videossa luodaan yhdistelmäkaavio käyttämällä myynti- ja markkinointimallia.
   > [!NOTE]
   > Tässä videossa käytetään Power BI Desktopin vanhempaa versiota.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a>

1. Aloita tyhjältä raporttisivulta ja luo pylväskaavio, joka näyttää tämän vuoden myynnin ja myyntikatteen kuukauden mukaan.

    a.  Valitse Kentät-ruudussa **Myynti** \> **Tämän vuoden myynti**  >  **Arvo**.

    b.  Vedä **Myynti** \> **Tämän vuoden myyntikate** **Arvo**-kohtaan.

    c. Valitse **Aika**  \> **FiscalMonth** ja lisää se **Akseli**-kohtaan.

    ![yhdistelmä opetusohjelma esimerkki](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Valitse **Enemmän vaihtoehtoja** (...) visualisoinnin oikeasta yläkulmasta ja valitse **Lajitteluperuste > FiscalMonth**. Jos haluat muuttaa lajittelujärjestyksen, valitse kolme pistettä uudelleen ja valitse joko **Lajittele nousevaan järjestykseen** tai **Lajittele laskevaan järjestykseen**. Tässä esimerkissä käytetään vaihtoehtoa **Lajittele nousevaan järjestykseen**.

6. Muunna pylväskaavio yhdistelmäkaavioksi. Käytettävissä on kaksi erilaista yhdistelmäkaaviota: **viivakaavio ja pinottu pylväskaavio** sekä **viivakaavio ja lohkopylväskaavio**. Pidä pylväskaavio valittuna ja valitse **Visualisoinnit**-ruudussa **Viiva- ja yhdistelmäpylväskaavio**.

    ![muunna yhdistelmäkaavio esimerkki](media/power-bi-visualization-combo-chart/converttocombo-new2.png)
7. Vedä **Kentät**-ruudusta **Myynti** \> **Edellisen vuoden myynti** säilöön **Riviarvot**.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Yhdistelmäkaavion pitäisi näyttää suunnilleen tältä:

   ![yhdistelmäkaavio valmis esimerkki](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Kahden akselin yhdistelmäkaavion luominen
Tässä tehtävässä verrataan myyntikatetta ja myyntiä.

1. Luo uusi viivakaavio, joka seuraa **viime vuoden myyntikateprosenttia** **tilikauden kuukauden** mukaan. Valitse kolme pistettä ja lajittele kaavio **kuukauden** mukaan **nousevassa järjestyksessä**.  
Myyntikate oli tammikuussa 35 %, huipussaan 45 % huhtikuussa, laski heinäkuussa ja nousi uudelleen elokuussa. Näemmekö samanlaisen kuvion edellisen ja tämän vuoden myynnissä?

   ![yhdistelmäkaavio esimerkki myynti](media/power-bi-visualization-combo-chart/combo1-new.png)
2. Lisää **Tämän vuoden myynti > Arvo** ja **Edellisen vuoden myynti** viivakaavioon. **Edellisen vuoden myyntikateprosentin** asteikko on paljon pienempi kuin **myynnin**, mikä vaikeuttaa vertailua.      

   ![yhdistelmäkaavio nollaviiva esimerkki](media/power-bi-visualization-combo-chart/flatline-new.png)
3. Voit helpottaa visualisoinnin tulkitsemista muuntamalla viivakaavion viivakaavioksi ja pinotuksi pylväskaavioksi.

   ![muunna yhdistelmäkaavioksi esimerkki](media/power-bi-visualization-combo-chart/converttocombo-new.png)

4. Vedä **Edellisen vuoden myyntikateprosentti** **sarakearvoista** **riviarvoihin**. Power BI luo kaksi akselia, jolloin tietojoukkoja voidaan skaalata erikseen; vasen mittaa myyntiä euroissa ja oikea prosenttilukua. Saat vastauksen kysymykseen; kyllä, samanlainen kuvio on havaittavissa.

   ![klusteriyhdistelmäkaavio esimerkki](media/power-bi-visualization-combo-chart/power-bi-clustered-combo.png)    

## <a name="add-titles-to-the-axes"></a>Akselien otsikoiden lisääminen
1. Valitse maalirullakuvake ![maalirullakuvake](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) muotoiluruudun avaamiseksi.
1. Laajenna **Y-akselin** asetukset alanuolella.
1. Määritä **Y-akseli (sarake)** -kohdan **Sijainti**-asetukseksi **Vasemmalla**, **Otsikko**-asetukseksi **Käytössä**, **Tyyli**-asetukseksi **Näytä vain otsikko** ja **Näyttöyksikkö**-asetukseksi **Miljoonat**.

   ![yhdistelmäkaavio avoin y esimerkki](media/power-bi-visualization-combo-chart/power-bi-open-y.png)
4. Vieritä **Y-akseli (sarake)** -kohdassa alaspäin, kunnes **Näytä toissijainen** on näkyvissä. Koska Y-akseleille on paljon vaihtoehtoja, sinun on ehkä käytettävä molempia vierityspalkkeja. Näytä toissijainen -osassa näkyvät yhdistelmäkaavion viivakaavio-osan muotoiluvaihtoehdot.

   ![yhdistelmäkaavio toissijainen esimerkki](media/power-bi-visualization-combo-chart/power-bi-secondary.png)
5. Jätä **Y-akseli (rivi)** > **Sijainti** > **oikealla** sekä määritä **Otsikko** > **Käytössä** ja **Tyyli** > **Näytä vain otsikko**.

   Yhdistelmäkaavio näyttää nyt kaksi akselia otsikoilla.

   ![yhdistelmäkaavio otsikot esimerkki](media/power-bi-visualization-combo-chart/power-bi-2-titles.png)

6. Halutessasi voit parantaa kaavion luettavuutta muokkaamalla tekstin fonttia, kokoa ja väriä sekä määrittämällä muita muotoiluasetuksia.

Seuraavat toiminnot:

* [Yhdistelmäkaavion lisääminen koontinäytön ruutuna](../create-reports/service-dashboard-tiles.md)
* [Tallenna raportti](../create-reports/service-report-save.md).
* [Tee raportista helpommin käytettävä toimintarajoitteisille ihmisille](../create-reports/desktop-accessibility-overview.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Ristiinkorostaminen ja ristiinsuodatus

Sarakkeen tai rivin korostaminen yhdistelmäkaaviossa ristiinkorostaa ja ristiinsuodattaa muut raporttisivulla olevat visualisoinnit... ja päinvastoin. Voit muuttaa tätä oletustoimintaa [visualisointitoimien](../create-reports/service-reports-visual-interactions.md) avulla.

## <a name="next-steps"></a>Seuraavat vaiheet

[Rengaskaaviot Power BI:ssä](power-bi-visualization-doughnut-charts.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
