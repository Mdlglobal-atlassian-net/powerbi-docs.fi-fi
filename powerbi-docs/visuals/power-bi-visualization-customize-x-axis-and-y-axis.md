---
title: X- ja Y-akselin ominaisuuksien muokkaaminen
description: X- ja Y-akselin ominaisuuksien muokkaaminen
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: 9DeAKM4SNJM
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3bfe84acdf73fcb5ace791c9a84943262d0f73ab
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390097"
---
# <a name="customize-x-axis-and-y-axis-properties"></a>X- ja Y-akselin ominaisuuksien muokkaaminen

Tässä opetusohjelmassa käydään läpi monia tapoja mukauttaa X-akselia ja Y-akselia visualisoinneissa. Kaikilla visualisoinneilla ei ole akseleita. Esimerkiksi ympyräkaaviossa ei ole akseleita. Ja mukautusvaihtoehdot vaihtelevat myös visualisoinnista toiseen. Vaihtoehtoja on niin monta, ettemme voi käsitellä niitä kaikkia tässä yhdessä artikkelissa, joten tutustut tässä useimmin käytettyihin akselien mukautuksiin ja visualisoinnin **Muotoilu**-ruutuun Power BI -raporttipohjassa.  

> [!NOTE]
> Tämä sivu koskee sekä Power BI -palvelua että Power BI Desktopia. Nämä mukautukset, jotka ovat käytettävissä, kun **Muotoilu** (maalirullakuvakkeen ![Näyttökuva maalirullakuvakkeesta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) kuvake on valittuna, ovat myös käytettävissä Power BI Desktopissa.

Katso, miten Amanda mukauttaa X- ja Y-akseleitaan. Hän esittelee erilaisia tapoja hallita ketjutusta käytettäessä porautumista alaspäin ja porautumista ylöspäin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Edellytykset

- Power BI -palvelu

- Jälleenmyyntianalyysimallin raportti

## <a name="customize-visualization-x--and-y-axes-in-reports"></a>Visualisoinnin X- ja Y-akselien mukauttaminen raporteissa

Seuraa mukana kirjautumalla sisään [Power BI -palveluun](https://app.powerbi.com) ja avaamalla [Jälleenmyyntianalyysimalli](../sample-datasets.md)-raportti [Muokkaa raporttia](../service-interact-with-a-report-in-editing-view.md) -näkymässä.

### <a name="create-a-stacked-column-chart-visualization"></a>Pinotun pylväskaavion visualisoinnin luominen

Ennen kuin voit mukauttaa visualisointia, sinun on luotava se.

1. Laajenna Power BI -palvelussa **Oma työtila** -kohtaa.

1. Vieritä alaspäin ja valitse **Jälleenmyyntianalyysimalli** **Tietojoukot**-luettelosta.

1. Valitse **Visualisoinnit**-ruudusta pinotun pylväskaavion kuvake.

    ![Näyttökuva Visualisointi-ruudusta ja tyhjästä pinotusta pylväskaaviosta](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-stacked-column-chart.png)

1. Määritä X-akselin arvot valitsemalla **Kentät**-ruudussa **Aika** > **FiscalMonth**.

1. Määritä Y-akselin arvot valitsemalla **Kentät**-ruudussa **Myynti** > **Viime vuoden myynti** ja **Myynti** > **Tämän vuoden myynti** > **Arvo**.

    ![Näyttökuva täytetystä pinotusta pylväskaaviosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-create-chart.png)

### <a name="customize-the-x-axis"></a>X-akselin mukauttaminen

Voit nyt mukauttaa X-akselia.

1. Avaa **Visualisoinnit**-ruudusta **Muotoilu** (maalirullakuvake ![Näyttökuva maalirullakuvakkeesta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) mukautusvaihtoehtojen paljastamiseksi.

1. Laajenna X-akselin vaihtoehtoja.

   ![Näyttökuva X-akselin vaihtoehdoista.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-axis.png)

1. Siirrä **X-akselin** liukusäädin tilaan **Käytössä**.

    ![Näyttökuva Käytössä-liukusäätimestä.](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)

    X-akselin voi poistaa käytöstä esimerkiksi tilan säästämiseksi uusille tiedoille.

1. Muotoile tekstin väriä, kokoa ja fonttia:

    - **Väri**: Valitse musta

    - **Tekstin koko**: Syötä *14*

    - **Fonttiperhe**: Valitse **Arial Black**

1. Siirrä **Otsikko**-vaihtoehdon tilaksi **Käytössä** X-akselin nimen näyttämiseksi. Tässä tapauksessa se on **FiscalMonth**.

1. Muotoile otsikon tekstin väriä, kokoa ja fonttia:

    - **Otsikon väri**: Valitse oranssi

    - **Akselin otsikko**: Syötä *tilikauden kuukausi*

    - **Otsikon tekstin koko**: Syötä *21*

Kun olet suorittanut mukautukset, pinottu pylväskaaviosi näyttää suunnilleen tältä:

![Näyttökuva mukautetusta pinotusta pylväskaaviosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-customize-axis.png)

Tallenna tekemäsi muutokset ja siirry seuraavaan osioon.

Jos haluat palauttaa kaikki muutokset, valitse **Palauta oletusasetukseen** **X-akselin** mukauttamisruudun alareunassa.

### <a name="customize-the-y-axis"></a>Y-akselin mukauttaminen

Seuraavaksi mukautat Y-akselin.

1. Laajenna Y-akselin asetukset.

   ![Näyttökuva Y-akselin vaihtoehdoista.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis.png)

1. Siirrä **Y-akselin** liukusäädin tilaan **Käytössä**.  

    ![Näyttökuva Käytössä-liukusäätimestä.](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)

    Y-akselin voi poistaa käytöstä esimerkiksi tilan säästämiseksi lisätiedoille.

1. Siirrä Y-akselin **sijainti** **oikealle**.

1. Muotoile tekstin väriä, kokoa ja fonttia:

    - **Väri**: Valitse musta

    - **Tekstin koko**: Syötä *14*

    - **Fonttiperhe**: Valitse **Arial Black**

1. Määritä **Näytä yksiköt** -kohdan arvoksi **Miljoonat** ja **Arvon desimaalit** -kohdan arvoksi *0*.

1. Tämän visualisoinnin tapauksessa Y-akselin otsikko ei paranna visualisointia, joten jätä **Otsikko**-kohdan tilaksi **Pois käytöstä**.  

1. Varmista, että ruudukko erottuu, muuttamalla väriä ja suurentamalla viivanleveyttä:

    - **Väri**: Valitse tummanharmaa

    - **Viivanleveys**: Syötä *2*

Mukautusten jälkeen pylväskaavion pitäisi näyttää suunnilleen tältä:

![Näyttökuva kaaviosta, jossa on mukautettu Y-akseli.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-complete.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>Visualisointien mukauttaminen kahden Y-akselin kanssa

Sinun täytyy ensin luoda yhdistelmäkaavio myymälöiden määrän vaikutuksesta myyntiin. Tämä on sama kaavio, joka luodaan [Yhdistelmäkaavion opetusohjelmassa](power-bi-visualization-combo-chart.md). Muotoile sitten molemmat Y-akselit.

### <a name="create-a-chart-with-two-y-axes"></a>Kahden Y-akselin kaavion luominen

1. Luo uusi viivakaavio, joka seuraa **myyntiä > viime vuoden myyntikateprosenttia** **ajan > FiscalMonth** mukaan.

    ![Näyttökuva uudesta viivakaaviosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-line-chart.png)

    > [!NOTE]
    > Lisätietoja lajittelusta kuukauden mukaan on artikkelissa [Lajittelu muilla ehdoilla](../consumer/end-user-change-sort.md#other).

    Käyttökateprosentti oli tammikuussa 35 %, se oli huipussaan 45 % huhtikuussa, se laski heinäkuussa ja se nousi uudelleen elokuussa. Näemmekö samanlaisen kuvion edellisen ja tämän vuoden myynnissä?

1. Lisää **Tämän vuoden myynti > Arvo** ja **Edellisen vuoden myynti** viivakaavioon.

    ![Näyttökuva viivakaaviosta, johon on lisätty uusia tietoja.](media/power-bi-visualization-customize-x-axis-and-y-axis/flatline_new.png)

    **Edellisen vuoden myyntikateprosentin** asteikko (sininen **0M%** -ruudukkoviiva) on paljon pienempi kuin **myynnin** asteikko, mikä vaikeuttaa vertailua. Y-akselin prosenttiosuudet ovat myös naurettavia.

1. Voit helpottaa visualisoinnin tulkitsemista muuntamalla viivakaavion viivaksi ja pinotuksi pylväskaavioksi.

   ![Näyttökuva visualisointiruudusta, jossa on korostettu viivan ja pinotun pylväskaavion kuvake.](media/power-bi-visualization-customize-x-axis-and-y-axis/converttocombo_new.png)

1. Vedä **Edellisen vuoden myyntikateprosentti** **sarakearvoista** **riviarvoihin**.

    ![Näyttökuva viivasta ja pinotusta pylväskaaviosta, joissa on esitetty selvästi kaikki kolme arvoa.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes.png)

    Nyt sinulla on pinottu pylväskaavio, jonka loit ensimmäisessä osiossa ja jonka päällä on viivakaavio. Halutessasi voit käyttää aiemmin oppimaasi ja muokata akselien fonttien väriä ja kokoa.

   ![Näyttökuva mukautetusta viivasta ja pinotusta pylväskaaviosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes-new.png)

   Power BI luo kaksi Y-akselia, jolloin tietojoukot voidaan skaalata eri tavalla. Vasen akseli mittaa dollareita ja oikea akseli mittaa prosenttilukua.

### <a name="format-the-secondary-y-axis"></a>Toissijaisen Y-akselin muotoileminen

1. Voit näyttää muotoiluvaihtoehdot valitsemalla maalirullakuvakkeen **Visualisoinnit**-ruudussa.

1. Laajenna Y-akselin asetukset.

1. Vieritä alaspäin, kunnes löydät **Näytä toissijainen** -vaihtoehdon. Tarkista, että se on **Käytössä**.

   ![Näyttökuva Näytä toissijainen -vaihtoehdosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/combo3.png)

1. (Valinnainen) Mukauta akselit. Jos vaihdat jommankumman akselin **sijaintia**, akselit vaihdetaan päittäin.

### <a name="add-titles-to-both-axes"></a>Otsikoiden lisääminen molempiin akseleihin

Akselien otsikoiden lisääminen auttaa näin monimutkaisessa visualisoinnissa.  Otsikot auttavat työtovereita ymmärtämään visualisointisi tarinan paremmin.

1. Ota sekä **Y-akselin (sarake)** että **Y-akselin (rivi)** **otsikot** **käyttöön**.

1. Määritä **tyylin** arvoksi **Näytä vain otsikko** kummallekin.

   ![Näyttökuva otsikosta ja tyylin vaihtoehdoista.](media/power-bi-visualization-customize-x-axis-and-y-axis/yaxissettings.png)

1. Yhdistelmäkaavio näyttää nyt kaksi akselia otsikoilla.

   ![Näyttökuva mukautetusta kahden Y-akselin kaaviosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo-chart.png)

Katso lisätietoja artikkelista [Vinkkejä värimuotoiluun Power BI:ssä](service-tips-and-tricks-for-color-formatting.md).

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

Jos raportin omistaja on luokitellut X-akselin päivämääräksi, **Tyyppi**-vaihtoehto on näkyvissä ja voit valita jatkuvan tai luokittaisen välillä.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Visualisoinnit Power BI -raporteissa](power-bi-report-visualizations.md)

- [Visualisoinnin otsikoiden, selitteiden ja taustojen mukauttaminen](power-bi-visualization-customize-title-background-and-legend.md)

- [Värimuotoilun ja akseliominaisuuksien käytön aloittaminen](service-getting-started-with-color-formatting-and-axis-properties.md)

- [Peruskäsitteet Power BI -palvelun kuluttajille](../consumer/end-user-basic-concepts.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
