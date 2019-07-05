---
title: Viisarimittarikaaviot Power BI:ssä
description: Viisarimittarikaaviot Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: xmja6Epqa
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8b0db9aebe72d54aa464ec012e614ae0ec5bc723
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390475"
---
# <a name="radial-gauge-charts-in-power-bi"></a>Viisarimittarikaaviot Power BI:ssä

Viisarimittarikaaviossa on pyöreä kaari, ja siinä on yksi arvo, joka mittaa edistymistä kohti tavoitetta tai suorituskyvyn mittaria. Rivi (tai *neula*) edustaa tavoitetta tai tavoitearvoa. Varjostus edustaa edistymistä tätä tavoitetta kohti. Kaaren sisällä oleva arvo tarkoittaa edistymisen arvoa. Power BI jakaa kaikki mahdolliset arvot tasaisesti kaarta pitkin minimistä (äärimmäisenä vasemmalla oleva arvo) maksimiin (äärimmäisenä oikealla oleva arvo).

![Näyttökuva viisarimittarista.](media/power-bi-visualization-radial-gauge-charts/gauge_m.png)

Tässä esimerkissä olet automyyjä, joka seuraa myyntitiimin keskimääräistä myyntiä kuukaudessa. Neula edustaa 140 auton myyntitavoitetta. Pienin mahdollinen keskimääräinen myynti on 0, ja maksimi on 200.  Sininen varjostus näyttää, että tiimin myyntivauhti on tässä kuussa noin 120 kappaletta. Onneksi tiimillä on vielä toinen viikko aikaa tavoitteen saavuttamiseen.

Will näyttää sivulle, miten voit luoda yksittäisten arvojen visualisoinnit: mittarit, kortit ja suorituskyvyn mittarit.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="when-to-use-a-radial-gauge"></a>Milloin käyttää viisarimittaria?

Viisarimittarit ovat hyvä vaihtoehto, kun:

* esitetään edistyminen kohti tavoitetta

* esitetään prosenttiyksiköitä, kuten suorituskyvyn mittareita

* näytetään yhden mittarin kunto

* näytetään tiedot, jotka voit lukea ja ymmärtää nopeasti.

## <a name="prerequisites"></a>Edellytykset

* Power BI -palvelu tai Power BI Desktop

* Talousmalli-Excel-työkirja: [lataa malli suoraan](http://go.microsoft.com/fwlink/?LinkID=521962).

## <a name="create-a-basic-radial-gauge"></a>Luo viisarimittarin perusmalli

Näissä ohjeissa käytetään Power BI -palvelua. Jatka kirjautumalla Power BI -palveluun ja avaa Excel Talousmalli -tiedosto.

### <a name="step-1-open-the-financial-sample-excel-file"></a>Vaihe 1: Avaa Excelin Talousmalli-tiedosto

1. Lataa [Excelin Talousmalli-tiedosto](../sample-financial-download.md), jos et ole vielä tehnyt sitä. Muista, mihin tallensit sen.

1. Valitse Power BI -palvelusta **Nouda tiedot** > **Tiedostot**.

1. Valitse **paikallinen tiedosto** ja siirry mallitiedoston sijaintiin.

1. Valitse **Tuo**. Power BI lisää talousmallin työtilaasi tietojoukkona.

1. Valitse **Tietojoukot**-sisältöluettelosta **Luo raportti** -kuvake **talousmallille**.

    ![Näyttökuva Tietojoukot-luettelosta, jossa nuoli osoittaa talousmallin Luo raportti -kuvakkeeseen.](media/power-bi-visualization-radial-gauge-charts/power-bi-dataset.png)

### <a name="step-2-create-a-gauge-to-track-gross-sales"></a>Vaihe 2: Luo mittari bruttomyynnin seuraamiseen

Viimeisessä osiossa, kun olet valinnut **Luo raportti** -kuvakkeen, Power BI luo tyhjän raportin muokkausnäkymään.

1. Valitse **Kentät**-ruudusta **Bruttomyynti**.

   ![](media/power-bi-visualization-radial-gauge-charts/grosssalesvalue_new.png)

1. Muuta koostaminen arvoon **Keskimääräinen**.

   ![Näyttökuva Kentät-ruudusta, jossa on korostettu bruttomyynti ja keskimäärän kooste.](media/power-bi-visualization-radial-gauge-charts/changetoaverage_new.png)

1. Valitse mittarikuvake ![Näyttökuva mittarikuvakkeesta.](media/power-bi-visualization-radial-gauge-charts/gaugeicon_new.png) pylväskaavion muuntamiseksi mittarikaavioksi.

    ![Näyttökuva mittarikaaviosta.](media/power-bi-visualization-radial-gauge-charts/gauge_no_target.png)

    Sen mukaan, milloin lataat **Talousmalli**-tiedoston, saatat nähdä lukuja, jotka eivät täsmää näiden lukujen kanssa.

    > [!TIP]
    > Oletusarvon mukaan Power BI luo mittarikaavion, jossa nykyisen arvon (tässä tapauksessa **keskimääräinen myynti**) oletetaan olevan mittarin puolivälissä. Koska **keskimääräinen bruttomyynti** on $ 182. 76K, aloitusarvo (minimi) on 0 ja loppuarvo (maksimi) on määritetty kaksinkertaiseksi nykyiseen arvoon nähden.

### <a name="step-3-set-a-target-value"></a>Vaihe 3: Määritä tavoitearvo

1. Vedä **myytyjen tuotteiden kustannukset** **Kentät**-ruudusta **Tavoitearvo**-säilöön.

1. Muuta koostaminen arvoon **Keskimääräinen**.

   Power BI Lisää neulan edustamaan Microsoftin tavoitearvoa **$145. 48K**.

   ![Näyttökuva mittarikaaviosta, johon on lisätty myytyjen tuotteiden kustannusten keskiarvo.](media/power-bi-visualization-radial-gauge-charts/gaugeinprogress_new.png)

    Huomaa, että olemme ylittäneet tavoitteemme.

   > [!NOTE]
   > Voit syöttää tavoitearvon myös manuaalisesti. Katso [Käytä manuaalisia muotoiluvaihtoehtoja minimi-, maksimi- ja tavoitearvojen asettamiseen](#use-manual-format-options-to-set-minimum-maximum-and-target-values).

### <a name="step-4-set-a-maximum-value"></a>Vaihe 4: Aseta maksimiarvo

Vaiheessa 2 Power BI asetti **Arvo**-kentän avulla automaattisesti minimi- ja maksimiarvot. Entä jos haluat määrittää oman maksimiarvon? Oletetaan, että sen sijasta, että käyttäisit kaksinkertaista nykyistä arvoa suurimpana mahdollisena arvona, haluat asettaa sen suurimpaan bruttomyyntimäärään tietojoukossasi.

1. Vedä **Bruttomyynti** **Kentät**-ruudusta **Maksimiarvo**-säilöön.

1. Muuta koostaminen arvoon **Maksimi**.

   ![Näyttökuva Kentät-ruudusta, jossa on korostettu bruttomyynti ja maksimikooste.](media/power-bi-visualization-radial-gauge-charts/setmaximum_new.png)

   Mittarin piirretään uudelleen uudella loppuarvolla 1,21 miljoonaa bruttomyyntinä.

   ![Näyttökuva valmiista mittarikaaviosta.](media/power-bi-visualization-radial-gauge-charts/power-bi-final-gauge.png)

### <a name="step-5-save-your-report"></a>Vaihe 5: Tallenna raporttisi

1. [Tallenna raportti](../service-report-save.md).

1. [Mittarikaavion lisääminen koontinäytön ruutuna](../service-dashboard-pin-tile-from-report.md). 

## <a name="use-manual-format-options-to-set-minimum-maximum-and-target-values"></a>Käytä manuaalisia muotoiluvaihtoehtoja minimi-, maksimi- ja tavoitearvojen asettamiseen

1. Vedä **Maksimibruttomyynti** kohdasta **Maksimiarvo**.

1. Avaa **Muotoilu**-ruutu valitsemalla maalirullakuvake.

   ![Näyttökuva mittarikaaviosta ja Muotoilu-ruudusta, jossa on korostettu maalirullakuvake.](media/power-bi-visualization-radial-gauge-charts/power-bi-roller.png)

1. Laajenna **Mittarin akselia** ja syötä arvot kohteille **Min** ja **Max**.

    ![Näyttökuva mittarikaavion vaihtoehdoista.](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-axis.png)

1. Tyhjennä **Myytyjen tuotteiden kustannukset** -vaihtoehto **Kentät**-ruudusta tavoitearvon poistamiseksi.

    ![Näyttökuva tyhjennetystä Myytyjen tuotteiden kustannukset -vaihtoehdosta.](media/power-bi-visualization-radial-gauge-charts/pbi_remove_target.png)

1. Kun **Tavoite**-kenttä näkyy kohdassa **Mittarin akseli**, syötä arvo.

     ![Näyttökuva Mittari akseli -vaihtoehdoista, joissa on korostettu Tavoite.](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-target.png)

1. Jatka vaihtoehtoisesti mittarikaavion muotoilua.

Kun olet käynyt läpi nämä vaiheet, sinulla on mittarikaavio, joka näyttää suunnilleen tältä:

![Näyttökuva lopullisesta mittarikaaviosta.](media/power-bi-visualization-radial-gauge-charts/power-bi-final.png)

## <a name="next-step"></a>Seuraava vaihe

* [Suorituskyvyn mittarin visualisoinnit](power-bi-visualization-kpi.md)

* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)