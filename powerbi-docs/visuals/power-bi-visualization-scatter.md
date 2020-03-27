---
title: Piste- ja kuplakaaviot Power BI:ssä
description: Pistekaaviot ja kuplakaaviot Power BI:ssä
author: mihart
ms.reviewer: amac
featuredvideoid: PVcfPoVE3Ys
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/21/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e7160505a720b6629067d7b1486f0dd227efd862
ms.sourcegitcommit: ad638d553d5f7f5831587791ffa7aa37a47dd6ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/26/2020
ms.locfileid: "80273313"
---
# <a name="scatter-charts-bubble-charts-and-dot-plot-charts-in-power-bi"></a>Pistekaaviot ja kuplakaaviot Power BI:ssä

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Pistekaaviossa on aina kaksi arvoakselia, jotka näyttävät yhden numeerisen tietosarjan vaakasuuntaisella akselilla ja toisen numeerisen arvosarjan pystysuuntaisella akselilla. Kaaviossa näytetään arvopisteet numeerisen arvon X ja Y leikkauskohdassa yhdistämällä nämä kaksi arvoa yhdeksi arvopisteeksi. Power BI voi jakaa nämä arvopisteet tasaisesti tai epätasaisesti vaakasuuntaiselle akselille kaavion edustamien tietojen mukaan.

Katso tästä videosta, miten Will luo pistekaavion, ja noudata sitten seuraavia ohjeita luodaksesi sellaisen itse.
   > [!NOTE]
   > Tässä videossa käytetään Power BI Desktopin vanhempaa versiota.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

Voit määrittää arvopisteiden määrän. Niiden enimmäismäärä on 10 000.  

## <a name="when-to-use-a-scatter-chart-bubble-chart-or-a-dot-plot-chart"></a>Milloin kannattaa käyttää pistekaaviota, kuplakaaviota tai pistetulostuskaaviota

### <a name="scatter-and-bubble-charts"></a>Piste- ja kuplakaaviot

Pistekaavio näyttää kahden numeerisen arvon välisen suhteen. Kuplakaavio korvaa arvopisteet kuplilla, joissa kuplan *koko* edustaa kolmansien lisätietojen dimensiota.

![Näyttökuva mallikuplakaaviosta.](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Pistekaavio on hyvä valinta:

* Suhteiden osoittamiseen kahden numeerisen arvon välillä.

* Kahden numeroryhmän piirtämiseen yhtenä X- ja Y-koordinaattien sarjana.

* Viivakaavion sijaan silloin, kun halutaan muuttaa vaakasuuntaisen akselin asteikkoa.

* Vaakasuuntaisen akselin muuttamiseen logaritmiseen asteikkoon.

* Sellaisten laskentataulukon tietojen näyttämiseen, joihin sisältyy arvopareja tai ryhmiteltyjä arvosarjoja.

    > [!TIP]
    > Pistekaaviossa on mahdollista säätää akselien yksittäisiä asteikkoja lisätietojen saamiseksi ryhmitellyistä arvoista.

* Toistuvien mallien osoittamiseen suurissa tietojoukoissa esimerkiksi osoittamalla lineaarisia tai epälineaarisia trendejä, klustereita ja poikkeavia arvoja.

* Suurten arvopistemäärien vertailuun ajasta riippumatta.  Mitä enemmän tietoja sisällytät pistekaavioon, sitä parempia vertailuja voit tehdä.

Pistekaavioiden lisäksi hyvä vaihtoehto ovat kuplakaaviot:

* Jos tiedoissasi on kolme arvosarjaa, joista jokainen sisältää joukon arvoja.

* Taloudellisten tietojen esittämiseen.  Erikokoiset kuplat ovat hyödyllisiä erityisten arvojen visuaaliseen korostamiseen.

* Neljännesten kanssa käytettäväksi.

### <a name="dot-plot-charts"></a>Pistetulostuskaaviot

Pistetulostuskaavio muistuttaa kuplakaaviota ja pistekaaviota, mutta niiden sijaan sitä käytetään luokittaisten tietojen tulostamiseen X-akselille.

![Näyttökuva pistetulostuskaaviosta.](media/power-bi-visualization-scatter/power-bi-dot-plot.png)

Se on mainio valinta, jos haluat sisällyttää X-akselille luokittaista tietoa.

## <a name="prerequisites"></a>Edellytykset

Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.


## <a name="create-a-scatter-chart"></a>Pistekaavion luominen

1. Aloita tyhjältä raporttisivulta ja valitse **Kentät**-ruudusta seuraavat kentät:

    * **Myynti** > **Myynti/neliöjalka**

    * **Myynti** > **Myyntivariaatio-% yhteensä**

    * **Alue** > **Alue**

    ![Näyttökuva klusteroidusta pylväskaaviosta, Visualisoinnit-ruudusta ja Kentät-ruudusta, jossa on kentät, jotka valitsit korostettaviksi.](media/power-bi-visualization-scatter/power-bi-bar-chart.png)

1. Valitse **Visualisointi**-ruudusta ![Näyttökuva pistekaaviokuvakkeesta.](media/power-bi-visualization-scatter/power-bi-scatter-chart-icon.png) klusteroidun pylväskaavion muuntamiseksi pistekaavioksi.

   ![Näyttökuva klusteroidusta pylväskaaviosta, joka muunnetaan pistekaavioksi.](media/power-bi-visualization-scatter/power-bi-scatter-new.png)

1. Vedä **Alue** kohteesta **Tiedot** kohteeseen **Selite**.

    Power BI näyttää pistekaavion, jossa **Myyntivariaatio-% yhteensä** on piirretty Y-akselille ja **Myynti/neliöjalka** X-akselille. Arvopisteiden värit edustavat alueita:

    ![Näyttökuva pistekaaviosta.](media/power-bi-visualization-scatter/power-bi-scatter2.png)

Nyt lisätään kolmas dimensio.

## <a name="create-a-bubble-chart"></a>Kuplakaavion luominen

1. Vedä **Kentät**-ruudusta **Myynti** > **Tämän vuoden myynti** > **Arvo** **Koko**-säilöön. Arvopisteet laajenevat myynnin arvon mukaisiin kokoihin.

   ![Näyttökuva pistekaaviosta, josta tulee kuplakaavio lisäämällä myynnin arvo Koko-säilöön.](media/power-bi-visualization-scatter/power-bi-scatter-chart-size.png)

1. Pidä hiiren osoitinta kuplan päällä. Kuplan koko kuvastaa arvoa **Tämän vuoden myynti**.

    ![työkaluvihjeiden näyttö](media/power-bi-visualization-scatter/pbi-scatter-chart-hover.png)

1. Voit määrittää kuplakaaviossa näkyvien arvopisteiden määrän laajentamalla **Visualisoinnit**-ruudun **Muotoilu**-osiossa olevaa **Yleistä**-kohtaa ja säätämällä **Tietojen määrä**-kohtaa.

    ![Näyttökuva Visualisoinnit-ruudusta, jossa on korostettu Muotoile-kuvake, yleinen avattava valikko ja Tietomäärä-vaihtoehto.](media/power-bi-visualization-scatter/pbi-scatter-data-volume.png)

    Voit määrittää tietojen enimmäismääräksi minkä tahansa luvun, joka on enintään 10 000. Suurten lukujen yhteydessä on suositeltavaa testata toiminta ensin hyvän suorituskyvyn varmistamiseksi.

    > [!NOTE]
    > Useammat arvopisteet saattavat merkitä pidempää latausaikaa. Jos haluat julkaista raportteja, joissa on rajat asteikon lopussa, testaa raporttisi myös verkossa ja mobiililaitteessa. Voit näin varmistaa, että kaavion suorituskyky vastaa käyttäjien odotuksia.

1. Jatka visualisoinnin värien, selitteiden, otsikoiden, taustan ja muiden muotoilua. Jos haluat [parantaa helppokäyttöisyyttä](../desktop-accessibility.md), harkitse merkin muotojen lisäämistä kullekin riville. Jos haluat valita merkin muodon, laajenna **Muodot**-kohtaa, valitse **Merkin muoto** ja valitse muoto.

    ![Näyttökuva avattavasta Muodot-valikosta, jossa on korostettu Merkin muoto -vaihtoehdot.](media/power-bi-visualization-scatter/pbi-scatter-marker.png)

    Vaihda merkin muoto vinoneliöksi, kolmioksi tai neliöksi. Erilaisten merkin muotojen käyttö kullekin riville helpottaa raporttien käyttäjiä erottamaan rivit (tai alueet) toisistaan.

1. Avaa Analysointi-ruutu ![Näyttökuvassa on Analysointi-ruudun kuvake.](media/power-bi-visualization-scatter/power-bi-analytics.png) lisätäksesi tietoja visualisointiisi.  
    - Lisää mediaanin viiva. Valitse **Mediaanin viiva** > **Lisää**. Power BI lisää oletusarvoisesti mediaanin viivan *myynnille per neliöjalka*. Tästä ei ole juuri hyötyä, koska näemme, että arvopisteitä on 10, ja tiedämme, että mediaani luodaan siten, että kummallakin puolella on viisi arvopistettä. Vaihda **mittariksi** sen sijaan *Myyntivariaatio-% yhteensä*.  

        ![Näyttökuvassa on kuplakaavio, johon on lisätty mediaanin viiva.](media/power-bi-visualization-scatter/power-bi-analytics-median.png)

    - Lisää symmetriavarjostus näyttääksesi, minkä pisteiden arvo on suurempi x-akselin mittarilla y-akselin mittariin verrattuna ja päinvastoin. Kun otat symmetriavarjostuksen käyttöön Analysointi-ruudussa, Power BI näyttää pistekaavion taustan symmetrisesti nykyisen akselin ylä- ja alarajojen perusteella. Tämä on erittäin nopea tapa nähdä, minkä akselin mittarin puolella arvopiste on, etenkin silloin, jos sinulla on eri akselialueet x- ja y-akseleille.

        a. Vaihda **Myyntivariaatio-% yhteensä** -kenttä **Edellisen vuoden myyntikateprosentti** -kenttään.

        ![Näyttökuvassa on kuplakaavio, johon on lisätty mediaanin viiva.](media/power-bi-visualization-scatter/power-bi-format-symmetry.png)

        b. Valitse Analysointiruudusta **Symmetriavarjostus**. Näemme varjostuksesta, että Sukkatuotteet (vihreä kupla vaaleanpunaisella varjostetulla alueella) on ainoa luokka, joka myyntikateprosentin puolella, ei neliöjalka- ja myymäläkohtaisen myynnin puolella. 

        ![Näyttökuvassa on kuplakaavio, johon on lisätty symmetriavarjostus.](media/power-bi-visualization-scatter/power-bi-symmetry.png)

    - Jatka Analysointi-ruudun tarkastelua ja etsi kiinnostavia oivalluksia tiedoistasi. 

        ![Näyttökuvassa on kuplakaavio, johon on lisätty symmetriavarjostus.](media/power-bi-visualization-scatter/power-bi-analytics-example.png)

## <a name="create-a-dot-plot-chart"></a>Pistetulostuskaavion luominen

Luo pistetulostuskaavio korvaamalla **numeerinen X-akseli**-kenttä luokittaisella kentällä.

Poista **X-akselin** ruudusta **Myynti/neliöjalka** ja korvaa se kentällä **Alue** > **Aluejohtaja**.

![Näyttökuva uudesta pistetulostuskaaviosta.](media/power-bi-visualization-scatter/power-bi-dot-plot-squares.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

### <a name="your-scatter-chart-has-only-one-data-point"></a>Pistekaaviossasi on vain yksi arvopiste

Onko pistekaaviossasi vain yksi arvopiste, joka koostaa kaikki arvot X- ja Y-akseleille?  Vai yhdistääkö kaavio kaikki arvot yhdelle vaaka- tai pystysuuntaiselle riville?

![Näyttökuva pistekaaviosta, jossa on yksi arvopiste.](media/power-bi-visualization-scatter/pbi-scatter-tshoot1.png)

Lisää kenttä **Tiedot**-säilöön ja kerro näin Power BI:lle, miten arvot ryhmitetään. Kentän on oltava yksilöllinen jokaiselle arvopisteelle, jonka haluat piirtää. Esimerkiksi yksinkertainen rivin numero tai tunnuskenttä.

![Näyttökuva pistekaaviosta, jossa RowNum on lisätty Tiedot-säilöön.](media/power-bi-visualization-scatter/pbi-scatter-tshoot.png)

Tai jos tiedoissasi ei ole näitä, luo kenttä, joka liittää X- ja Y-arvot yhteen niin, että ne yksilöivät pisteen:

![Näyttökuva pistekaaviosta, jossa TempTime on lisätty Tiedot-säilöön.](media/power-bi-visualization-scatter/pbi-scatter-tshoot2.png)

Jos haluat luoda uuden kentän, [käytä Power BI Desktopin kyselyeditoria lisätäksesi indeksisarakkeen](../desktop-add-custom-column.md) tietojoukkoosi. Lisää sitten tämä sarake visualisointisi **Tiedot**-säilöön.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit olla kiinnostunut myös seuraavista artikkeleista:

* [Suuren tiheyden näytteenotto Power BI:n pistekaavioissa](desktop-high-density-scatter-charts.md)
* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [Vihjeitä tietolohkojen lajittelemiseen ja jakeluun Power BI ‑raporteissa](../guidance/report-tips-sort-distribute-data-plots.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
