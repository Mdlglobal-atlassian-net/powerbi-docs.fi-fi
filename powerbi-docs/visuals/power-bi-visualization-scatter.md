---
title: Piste- ja kuplakaaviot Power BI:ssä
description: Pistekaaviot ja kuplakaaviot Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: PVcfPoVE3Ys
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 26dd55f1084d62f9506b02c5852f0396adba305a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54290310"
---
# <a name="scatter-charts-bubble-charts-and-dot-plot-charts-in-power-bi"></a>Pistekaaviot ja kuplakaaviot Power BI:ssä
Pistekaaviossa on aina kaksi arvoakselia, jotka näyttävät yhden numeerisen tietosarjan vaakasuuntaisella akselilla ja toisen numeerisen arvosarjan pystysuuntaisella akselilla. Kaaviossa näytetään arvopisteet numeerisen arvon X ja Y leikkauskohdassa yhdistämällä nämä kaksi arvoa yhdeksi arvopisteeksi. Nämä arvopisteet voidaan jakaa tasaisesti tai epätasaisesti vaakasuuntaiselle akselille tietojen mukaan.

Kuplakaaviossa arvopisteet korvataan kuplilla ja kuplan *koko* kuvastaa tietojen muuta dimensiota.

![kuplakaavion malli](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Pistetulostuskaavio (dot plot) muistuttaa kuplakaaviota ja hajontaa kuvaavaa pistekaaviota sillä erotuksella, että X-akselille voi tulostaa numeerisia tai luokittaisia tietoja. 

![kuplakaavion malli](media/power-bi-visualization-scatter/power-bi-dot-plot.png)

Voit määrittää arvopisteiden määrän. Niiden enimmäismäärä on 10 000.  

## <a name="when-to-use-a-scatter-chart-or-bubble-chart"></a>Milloin kannattaa käyttää pistekaaviota tai kuplakaaviota
### <a name="scatter-charts-are-a-great-choice"></a>Pistekaavio on hyvä valinta:
* suhteiden osoittamiseen 2:n (piste) tai 3:n (kupla) **numeerisen** arvon välillä.
* kahden numeroryhmän piirtämiseen yhtenä XY-koordinaattien sarjana.
* viivakaavion sijaan silloin, kun halutaan muuttaa vaakasuuntaisen akselin asteikkoa    
* vaakasuuntaisen akselin muuttamiseen logaritmiseen asteikkoon.
* sellaisten laskentataulukon tietojen näyttämiseen, joihin sisältyy arvopareja tai ryhmiteltyjä arvosarjoja. Pistekaaviossa on mahdollista säätää akselien yksittäisiä asteikkoja lisätietojen saamiseksi ryhmitellyistä arvoista.
* toistuvien mallien osoittamiseen suurissa tietojoukoissa esimerkiksi osoittamalla lineaarisia tai epälineaarisia trendejä, klustereita ja poikkeavia arvoja.
* suurten arvopistemäärien vertailuun ajasta riippumatta.  Mitä enemmän tietoja sisällytät pistekaavioon, sitä parempia vertailuja voit tehdä.

### <a name="bubble-charts-are-a-great-choice"></a>Kuplakaavio on hyvä valinta:
* jos tiedoissasi on 3 arvosarjaa, joista jokainen sisältää joukon arvoja.
* taloudellisten tietojen esittämiseen.  Erikokoiset kuplat ovat hyödyllisiä erityisten arvojen visuaaliseen korostamiseen.
* neljännesten kanssa käytettäväksi.

### <a name="dot-plot-charts-are-a-great-choice-in-place-of-a-scatter-or-bubble"></a>Pistetulostuskaavio on hyvä valinta piste- tai kuplakaavion sijasta:
* jos haluat sisällyttää X-akselille luokittaista tietoa.

## <a name="create-a-scatter-chart"></a>Pistekaavion luominen
Katso tästä videosta, miten Will luo pistekaavion, ja noudata sitten seuraavia ohjeita luodaksesi sellaisen itse.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Näissä ohjeissa käytetään jälleenmyyntianalyysimallia. Jos haluat seurata ohjeita itse, [lataa malli](../sample-datasets.md) joko Power BI ‑palveluun (app.powerbi.com) tai Power BI Desktopiin.   

1. Avaa raportti muokkausnäkymässä ja valitse keltainen plus-kuvake luodaksesi tyhjän raporttisivun.
 
2. Valitse Kentät-ruudusta seuraavat kentät:
   - **Myynti** > **Myynti/neliöjalka**
   - **Myynti** > **Myyntivariaatio-% yhteensä**
   - **Alue** > **Alue**

     ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)

     Jos käytät Power BI ‑palvelua, varmista, että avaat raportin [muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md).

3. Muunna pistekaavioksi. Valitse Visualisointi-ruudussa Pistekaavio-kuvake.

   ![](media/power-bi-visualization-scatter/power-bi-scatter-new.png).

4. Vedä **Alue** kohteesta **Tiedot** kohteeseen **Selite**. Tämä tuo esille pistekaavion, jossa **Myyntivariaatio-% yhteensä** on piirretty Y-akselille ja **Myynti/neliöjalka** X-akselille. Arvopisteiden värit edustavat alueita:

    ![](media/power-bi-visualization-scatter/power-bi-scatter2.png)

Nyt lisätään kolmas dimensio.

## <a name="create-a-bubble-chart"></a>Kuplakaavion luominen

1. Vedä **Kentät**-ruudusta **Myynti** > **Tämän vuoden myynti** > **Arvo** alueelle **Koko**. Arvopisteet laajenevat myynnin arvon mukaisiin kokoihin.
   
   ![pisteet muuttuvat kupliksi](media/power-bi-visualization-scatter/power-bi-scatter-chart-size.png)

2. Pidä hiiren osoitinta kuplan päällä. Kuplan koko kuvastaa arvoa **Tämän vuoden myynti**.
   
    ![työkaluvihjeiden näyttö](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)

3. Voit määrittää kuplakaaviossa näkyvien arvopisteiden määrän laajentamalla **Visualisoinnit**-ruudun **Muotoilu**-osiossa olevan kortin **Yleistä** ja säätämällä kohtaa **Tietojen määrä**. Voit määrittää tietojen enimmäismääräksi minkä tahansa luvun, joka on enintään 10 000. Suurten lukujen yhteydessä on suositeltavaa testata toiminta ensin hyvän suorituskyvyn varmistamiseksi. 

    ![Tietojen määrä](media/power-bi-visualization-scatter/pbi_scatter_data_volume.png) 

   Enemmän arvopisteitä voi tarkoittaa pidempää latausaikaa, joten jos haluat julkaista raportteja, joiden rajat ovat asteikon yläpäässä, testaa raporttejasi myös verkossa ja mobiililaitteilla sen varmistamiseksi, että suorituskyky vastaa käyttäjien odotuksia. 

4. Voit [muotoilla visualisoinnin värejä, nimiä, otsikoita, taustaa ja muuta](service-getting-started-with-color-formatting-and-axis-properties.md). Jos haluat [parantaa helppokäyttöisyyttä](../desktop-accessibility.md), harkitse merkin muotojen lisäämistä kullekin riville. Erilaisten merkin muotojen käyttö kullekin riville helpottaa raporttien käyttäjiä erottamaan rivit (tai alueet) toisistaan. Voi valita merkin muodon laajentamalla **Muodot**-kortin ja valitsemalla sitten merkin muodon.

      ![Merkin muoto](media/power-bi-visualization-scatter/pbi_scatter_marker.png)

   Voit myös muuttaa merkin muodon vinoneliöksi, kolmioksi tai neliöksi:

   ![Neliömerkki](media/power-bi-visualization-scatter/pbi_scatter_chart_hover_square.png)

## <a name="create-a-dot-plot"></a>Pistekaavion luominen
Luo pistetulostuskaavio (dot plot) korvaamalla numeerinen X-akselin kenttä luokittaisella kentällä.

Poista **X-akselin** ruudusta **Myynti/neliöjalka**-kenttä ja korvaa kentällä **Alue > DM**.
   
![uusi pistekaavio](media/power-bi-visualization-scatter/power-bi-dot-plot-squares.png)


## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

### <a name="your-scatter-chart-has-only-one-data-point"></a>**Pistekaaviossasi on vain yksi arvopiste**
Onko pistekaaviossasi vain yksi arvopiste, joka koostaa kaikki arvot X- ja Y-akseleille?  Vai yhdistääkö kaavio kaikki arvot yhdelle vaaka- tai pystysuuntaiselle riville?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

Lisää kenttä **Tiedot**-alueelle ja kerro näin Power BI:lle, miten arvot ryhmitetään. Kentän on oltava yksilöllinen jokaiselle arvopisteelle, jonka haluat piirtää, esim. yksinkertainen rivin numero tai tunnuskenttä.

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Tai jos tiedoissasi ei ole näitä, luo kenttä, joka liittää X- ja Y-arvot yhteen niin, että ne yksilöivät pisteen:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Jos haluat luoda uuden kentän, [käytä Power BI Desktopin kyselyeditoria lisätäksesi indeksisarakkeen](../desktop-add-custom-column.md) tietojoukkoosi.  Lisää sitten tämä sarake visualisointisi **Tiedot**-alueelle.

## <a name="next-steps"></a>Seuraavat vaiheet

[Suuren tiheyden pistekaaviot](desktop-high-density-scatter-charts.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)

