---
title: Yhdistelmäkaavio Power BI:ssä
description: Tässä yhdistelmäkaavioita koskevassa opetusohjelmassa selitetään, milloin niitä kannattaa käyttää ja miten niitä voidaan luoda Power BI -palvelussa ja Desktopissa.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/23/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e4b7b4b336b376f6ccec0bc0fe56de107ab8bd09
ms.sourcegitcommit: 7d52401f50944feaaa112c84113ee47f606dbf68
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/13/2019
ms.locfileid: "67124200"
---
# <a name="combo-chart-in-power-bi"></a>Yhdistelmäkaavio Power BI:ssä

Power BI:ssä yhdistelmäkaavio on yksittäinen visualisointi, joka yhdistää viivakaavion ja pylväskaavion. Näiden kahden kaavion yhdistäminen nopeuttaa tietojen vertailua.

Yhdistelmäkaaviossa voi olla yksi tai kaksi Y-akselia.

## <a name="when-to-use-a-combo-chart"></a>Milloin kannattaa käyttää yhdistelmäkaaviota

Yhdistelmäkaavio on hyvä vaihtoehto, kun:

* sinulla on viivakaavio ja pylväskaavio, joilla on sama X-akseli

* haluat vertailla useita mittareita eri arvoalueilla

* haluat havainnollistaa kahden mittarin välistä korrelaatiota yhdessä visualisoinnissa

* haluat tarkistaa, täyttääkö yksi mittari toisen mittarin määrittämän tavoitteen

* haluat säästää tilaa piirtoalustalla.

## <a name="prerequisites"></a>Edellytykset

Yhdistelmäkaaviot ovat käytettävissä Power BI -palvelussa ja Power BI Desktopissa. Tässä opetusohjelmassa luodaan yhdistelmäkaavio Power BI -palvelussa. Varmista, että sinulla on käyttäjän tunnistetiedot kirjautuaksesi sisään Power BI:hin.

Seuraavassa videossa luodaan yhdistelmäkaavio käyttämällä myynti- ja markkinointimallia.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

## <a name="create-a-basic-single-axis-combo-chart"></a>Perusmuotoisen yhden akselin yhdistelmäkaavion luominen

Seuraa opetusohjelmaa avaamalla Power BI -palvelu ja muodostamalla yhteys **jälleenmyyntianalyysimalliin**. Luo oma yhdistelmäkaavio kirjautumalla sisään Power BI -palveluun ja valitsemalla **Nouda tiedot** > **Mallit** > **Jälleenmyyntianalyysimalli** > **Yhdistä**. Esiin tulee **jälleenmyyntianalyysimallin** koontinäkymä.

1. Avaa **Myymälän myynnin yleiskatsaus** -raportti valitsemalla jälleenmyyntianalyysimallin koontinäytöstä **Myymälöitä yhteensä** -ruutu.

1. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.

1. Valitse sivun alareunasta **+** uuden raporttisivun lisäämiseksi.

1. Luo pylväskaavio, joka näyttää tämän vuoden myynnin ja myyntikatteen kuukauden mukaan.

    1. Valitse Kentät-ruudussa **Myynti** \> **Tämän vuoden myynti** > **Arvo**.

    1. Vedä **Myynti** \> **Tämän vuoden myyntikate** **Arvo**-kohtaan.

    1. Valitse **Aika** \> **FiscalMonth** ja lisää se **Akseli**-kohtaan.

        ![Näyttökuva äskettäin luodusta pylväskaaviosta.](media/power-bi-visualization-combo-chart/combotutorial1new.png)

1. Valitse kolme pistettä (...) visualisoinnin oikeasta yläkulmasta ja valitse **Lajitteluperuste > FiscalMonth**. Jos haluat muuttaa lajittelujärjestyksen, valitse kolme pistettä uudelleen ja valitse joko **Lajittele nousevaan järjestykseen** tai **Lajittele laskevaan järjestykseen**.

1. Muunna pylväskaavio yhdistelmäkaavioksi. Käytettävissä on kaksi erilaista yhdistelmäkaaviota: **viivakaavio ja pinottu pylväskaavio** sekä **viivakaavio ja lohkopylväskaavio**. Pidä pylväskaavio valittuna ja valitse **Visualisoinnit**-ruudussa **Viiva- ja yhdistelmäpylväskaavio**.

    ![Näyttökuva visualisointiruudusta, jossa on valittu viivakaavion ja yhdistelmäpylväskaavion vaihtoehto.](media/power-bi-visualization-combo-chart/converttocombo_new2.png)

1. Vedä **Kentät**-ruudusta **Myynti** > **Edellisen vuoden myynti** **Riviarvot**-säilöön.

    ![Näyttökuva Riviarvot-säilöstä, johon on vedetty edellisen vuoden myynti.](media/power-bi-visualization-combo-chart/linevaluebucket.png)

    Yhdistelmäkaavion pitäisi näyttää suunnilleen tältä:

    ![Näyttökuva pylväskaaviosta, johon on lisätty Edellisen vuoden myynti -rivi.](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Kahden akselin yhdistelmäkaavion luominen

Tässä tehtävässä verrataan myyntikatetta ja myyntiä.

1. Luo uusi viivakaavio, joka seuraa **viime vuoden myyntikateprosenttia** **kuukauden** mukaan. Valitse kolme pistettä ja lajittele kaavio **kuukauden** mukaan **nousevassa järjestyksessä**.

    ![Näyttökuva uudesta viivakaaviosta.](media/power-bi-visualization-combo-chart/combo1_new.png)

     Myyntikate oli tammikuussa 35 %, huipussaan 45 % huhtikuussa, laski heinäkuussa ja nousi uudelleen elokuussa. Näemmekö samanlaisen kuvion edellisen ja tämän vuoden myynnissä?

1. Lisää **Tämän vuoden myynti** > **Arvo** ja **Edellisen vuoden myynti** rivikaavioon. **Edellisen vuoden myyntikateprosentti** on selvästi pienempi kuin **myynnin** asteikko. Sitä on vaikea verrata.

    ![Näyttökuva viivakaaviosta, johon on lisätty arvo ja edellisen vuoden myynti.](media/power-bi-visualization-combo-chart/flatline_new.png)

1. Voit helpottaa visualisoinnin tulkitsemista muuntamalla viivakaavion viivakaavioksi ja pinotuksi pylväskaavioksi.

    ![Näyttökuva visualisointiruudusta, jossa on valittu viivakaavion ja pinotun pylväskaavion vaihtoehto.](media/power-bi-visualization-combo-chart/converttocombo_new.png)

1. Vedä **Edellisen vuoden myyntikateprosentti** **sarakearvoista** **riviarvoihin**. 

    ![Näyttökuva viivakaaviosta ja pinotusta pylväskaaviosta](media/power-bi-visualization-combo-chart/power-bi-combochart.png)

    Power BI luo kaksi akselia, jolloin palvelu voi skaalata tietojoukot eri tavalla. Vasen akseli mittaa myyntiä dollareissa ja oikea akseli mittaa prosenttilukua. Näemme vastauksen kysymykseemme: Kyllä, näemme samanlaisen kaavion.

## <a name="add-titles-to-the-axes"></a>Akselien otsikoiden lisääminen

1. Valitse maalirullakuvake ![Näyttökuva maalirullakuvakkeesta.](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) muotoiluruudun avaamiseksi.

1. Laajenna **Y-akselin** asetukset alanuolella.

1. Valitse **Y-akselille (sarake)** nämä vaihtoehdot:

    | Asetus | Arvo |
    | ------- | ----- |
    | Sijainti | Valitse **Vasen**. |
    | Näytön yksiköt | Valitse **Miljoonat**. |
    | Otsikko | Siirrä liukusäädin asentoon **Käytössä**. |
    | Tyyli | Valitse **Näytä vain otsikko**. |
    | Näytä toissijainen | Siirrä liukusäädin asentoon **Käytössä**.  Tämä näyttää yhdistelmäkaavion viivakaavio-osan muotoiluvaihtoehdot. |

1. Valitse **Y-akselille (rivi)** nämä vaihtoehdot:

    | Asetus | Arvo |
    | ------- | ----- |
    | Sijainti | Valitse **Oikea**. |
    | Otsikko | Siirrä liukusäädin asentoon **Käytössä**. |
    | Tyyli | Valitse **Näytä vain otsikko**. |

    Yhdistelmäkaavio näyttää nyt kaksi akselia otsikoilla.

    ![Näyttökuva viivakaaviosta ja pinotusta pylväskaaviosta, jossa otsikot ovat käytössä.](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

1. Halutessasi voit parantaa kaavion luettavuutta muokkaamalla tekstin fonttia, kokoa ja väriä sekä määrittämällä muita muotoiluasetuksia.

Seuraavat toiminnot:

* [Yhdistelmäkaavion lisääminen koontinäytön ruutuna](../service-dashboard-tiles.md)

* [Tallenna raportti](../service-report-save.md).

* [Tee raportista helpommin käytettävä toimintarajoitteisille ihmisille](../desktop-accessibility.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Ristiinkorostaminen ja ristiinsuodatus

Sarakkeen tai rivin korostaminen yhdistelmäkaaviossa ristiinkorostaa ja ristiinsuodattaa muut raporttisivulla olevat visualisoinnit. Voit muuttaa tätä oletustoimintaa [visualisointitoimien](../service-reports-visual-interactions.md) avulla.

## <a name="next-steps"></a>Seuraavat vaiheet

[Rengaskaaviot Power BI:ssä](power-bi-visualization-doughnut-charts.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)