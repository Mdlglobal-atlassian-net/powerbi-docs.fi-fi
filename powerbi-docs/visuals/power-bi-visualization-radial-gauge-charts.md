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
ms.date: 09/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 079494a47452ca0ca043032f78fa35c7d1755d11
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282559"
---
# <a name="radial-gauge-charts-in-power-bi"></a>Viisarimittarikaaviot Power BI:ssä
Viisarimittarikaaviossa on pyöreä kaari, ja siinä on yksi arvo, joka mittaa edistymistä kohti tavoitetta/suorituskyvyn mittaria.  Tavoite tai tavoitearvo esitetään riveittäin (neula). Tämän päämäärän edistyminen esitetään varjostuksella.  Arvo, joka edustaa kyseistä edistymistä, näkyy lihavoituna kaaren sisällä. Kaikki mahdolliset arvot on jaettu tasaisesti kaarta pitkin minimistä (äärimmäisenä vasemmalla oleva arvo) maksimiin (äärimmäisenä oikealla oleva arvo).

Seuraavassa esimerkissä olemme automyyjä, joka seuraa myyntitiimin keskimääräistä myyntiä kuukaudessa. Tavoitteemme on 140, ja sitä edustaa musta neula.  Pienin mahdollinen keskimääräinen myynti on 0, ja maksimiksi on asetettu 200.  Sininen varjostus näyttää, että olemme tällä hetkellä noin 120 kappaleen vauhdissa tässä kuussa. Onneksi meillä on vielä viikko aikaa tavoitteiden saavuttamiseksi.

![](media/power-bi-visualization-radial-gauge-charts/gauge_m.png)

## <a name="when-to-use-a-radial-gauge"></a>Milloin käyttää viisarimittaria?
Viisarimittarit ovat hyvä vaihtoehto, kun:

* esitetään edistyminen kohti tavoitetta.
* esitetään prosenttiyksiköitä, kuten suorituskyvyn mittareita.
* näytetään yhden mittauksen kunto.
* näytetään tiedot, joita voidaan nopeasti tarkistaa ja ymmärtää.

### <a name="prerequisites"></a>Edellytykset
 - Power BI -palvelu tai Power BI Desktop
 - Talousmalli-Excel-työkirjan: [lataa näyte suoraan](http://go.microsoft.com/fwlink/?LinkID=521962).

## <a name="create-a-basic-radial-gauge"></a>Luo viisarimittarin perusmalli
Näissä ohjeissa käytetään Power BI -palvelua. Jatka kirjautumalla Power BI -palveluun ja avaa Excel Talousmalli -tiedosto.  

Tai kello näyttää, miten voit luoda yksittäisten arvojen visualisoinnit: mittarit, kortit ja suorituskyvyn mittarit.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

### <a name="step-1-open-the-financial-sample-excel-file"></a>Vaihe 1: Avaa Excelin Talousmalli-tiedosto
1. [Lataa Excel Talousmalli -mallitiedosto](../sample-financial-download.md), jos et ole vielä tehnyt sitä. Muista, mihin tallensit sen.

2. Avaa tiedosto ***Power BI -palvelussa*** valitsemalla **Nouda tiedot \>**  ja selaamalla sijaintiin, johon tallensit tiedoston. Valitse **Tuo**. Talousmalli lisätään työtilaasi tietojoukkona.

3. Valitse **tietojoukon** sisältöluettelosta **Talousmalli** ja avaa se Tutustu-tilassa.

    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-dataset.png)

### <a name="step-2-create-a-gauge-to-track-gross-sales"></a>Vaihe 2: Luo mittari bruttomyynnin seuraamiseen
1. Valitse **Kentät** -ruudussa **Bruttomyynti**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/grosssalesvalue_new.png)
2. Muuta koostaminen arvoon **Keskimääräinen**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/changetoaverage_new.png)
3. Valitse mittarikuvake ![](media/power-bi-visualization-radial-gauge-charts/gaugeicon_new.png) pylväskaavion muuntamiseksi mittariksi.
   
   Oletusarvon mukaan Power BI luo mittakaavion, jossa nykyinen arvo (tässä tapauksessa keskimääräinen bruttomyynti) oletetaan olevan mittarin puolivälissä. Koska keskimääräinen bruttomyynti on $ 182. 76K, aloitusarvo (minimi) on 0 ja loppuarvo (maksimi) on määritetty kaksinkertaiseksi nykyiseen arvoon nähden.
   
   ![](media/power-bi-visualization-radial-gauge-charts/gauge_no_target.png)

### <a name="step-3-set-a-target-value"></a>Vaihe 3: Määritä tavoitearvo
1. Vedä **myytyjen tuotteiden kustannukset (COGS)** **tavoitearvoon**.
2. Muuta koostaminen arvoon **Keskimääräinen**.
   Power BI Lisää neulan edustamaan Microsoftin tavoitearvoa **$145. 48K**. Huomaa, että olemme ylittäneet tavoitteemme.
   
   ![](media/power-bi-visualization-radial-gauge-charts/gaugeinprogress_new.png)
   
   > [!NOTE]
   > Voit syöttää tavoitearvon myös manuaalisesti.  Lue seuraava kohta ”Käytä muotoiluasetuksia, minimi-, maksimi- ja tavoitearvojen asettamiseen”.
   > 
   > 

### <a name="step-4-set-a-maximum-value"></a>Vaihe 4: Aseta maksimiarvo
Vaiheessa 2 Power BI käytti Arvo-kenttää asettamana automaattisesti minimin (alku) ja maksimin (loppu).  Mutta entä jos haluat määrittää oman maksimiarvon?  Oletetaan, että sen sijasta, että käyttäisit kaksinkertaista nykyistä arvoa suurimpana mahdollisena arvona, haluat asettaa sen suurimpaan bruttomyyntimäärään tietojoukossasi. 

1. Vedä **Bruttomyynti** **Kentät**-luettelosta **suurimman arvon** kohdalle.
2. Muuta koostaminen arvoon **Maksimi**.
   
   ![](media/power-bi-visualization-radial-gauge-charts/setmaximum_new.png)
   
   Mittarin piirretään uudelleen uudella loppuarvolla 1,21 miljoonaa bruttomyyntinä.
   
   ![](media/power-bi-visualization-radial-gauge-charts/power-bi-final-gauge.png)

### <a name="step-5-save-your-report"></a>Vaihe 5: Tallenna raporttisi
1. [Tallenna raportti](../service-report-save.md).
2. [Mittarikaavion lisääminen koontinäytön ruutuna](../service-dashboard-pin-tile-from-report.md). 

## <a name="use-formatting-options-to-manually-set-minimum-maximum-and-target-values"></a>Käytä muotoiluasetuksia, minimi-, maksimi- ja tavoitearvojen asettamiseen
1. Vedä **Maksimibruttomyynti** kohdasta **Maksimiarvo**.
2. Avaa muotoiluruutu valitsemalla maalitelakuvake.
   
   ![](media/power-bi-visualization-radial-gauge-charts/power-bi-roller.png)
3. Laajenna **Mittarin akselia** ja syötä arvot **Min** ja **Max**.
   
    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-axis.png)
4. Poista nykyinen tavoitearvo poistamalla valintamerkki kohdasta **COGS**.
   
    ![](media/power-bi-visualization-radial-gauge-charts/pbi_remove_target.png)
5. Kun **Tavoite**-kenttä näkyy kohdassa **Mittarin akseli**, syötä arvo.
   
    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-target.png)
6. Jatka vaihtoehtoisesti mittarikaavion muotoilua.

## <a name="next-step"></a>Seuraava vaihe

[Mittarit Power BI:ssä](power-bi-visualization-kpi.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
