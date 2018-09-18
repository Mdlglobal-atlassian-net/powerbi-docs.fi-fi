---
title: Pistekaaviot Power BI:ssä
description: Pistekaaviot Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: PVcfPoVE3Ys
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/28/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 13bc26eaecdcc9b3a00f22f75f6f9a5322d823f6
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/12/2018
ms.locfileid: "44736435"
---
# <a name="scatter-charts-and-bubble-charts-in-power-bi"></a>Pistekaaviot ja kuplakaaviot Power BI:ssä
Pistekaaviossa on aina kaksi arvoakselia, jotka näyttävät yhden numeerisen tietosarjan vaakasuuntaisella akselilla ja toisen numeerisen arvosarjan pystysuuntaisella akselilla. Kaaviossa näytetään arvopisteet numeerisen arvon X ja Y leikkauskohdassa yhdistämällä nämä kaksi arvoa yhdeksi arvopisteeksi. Nämä arvopisteet voidaan jakaa tasaisesti tai epätasaisesti vaakasuuntaiselle akselille tietojen mukaan.

Kuplakaaviossa arvopisteet korvataan kuplilla ja kuplan *koko* kuvastaa tietojen muuta dimensiota.

![](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Voit määrittää arvopisteiden määrän  

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

## <a name="create-a-scatter-chart"></a>Pistekaavion luominen
Katso tästä videosta, miten Will luo pistekaavion, ja noudata sitten seuraavia ohjeita luodaksesi sellaisen itse.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Näissä ohjeissa käytetään jälleenmyyntianalyysimallia. Jos haluat seurata ohjeita itse, [lataa malli](../sample-datasets.md) joko Power BI ‑palveluun (app.powerbi.com) tai Power BI Desktopiin.   

1. Valitse keltainen plus-kuvake luodaksesi [tyhjän raporttisivun](../power-bi-report-add-page.md).
 
2. Valitse Kentät-ruudusta seuraavat kentät:
   - **Myynti** > **Myynti/neliöjalka**
   - **Myynti** > **Myyntivariaatio-% yhteensä**
   - **Alue** > **Alue**

     ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)

     Jos käytät Power BI ‑palvelua, varmista, että avaat raportin [muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md).

3. Muunna pistekaavioksi. Valitse Visualisointi-ruudussa Pistekaavio-kuvake.

   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png).

4. Vedä **Alue** kohteesta **Tiedot** kohteeseen **Selite**. Tämä tuo esille pistekaavion, jossa **Myyntivariaatio-% yhteensä** on piirretty Y-akselille ja **Myynti/neliöjalka** X-akselille. Arvopisteiden värit edustavat alueita:

    ![](media/power-bi-visualization-scatter/power-bi-scatter.png)

Nyt lisätään kolmas dimensio.

## <a name="create-a-bubble-chart"></a>Kuplakaavion luominen

1. Vedä **Kentät**-ruudusta **Myynti** > **Tämän vuoden myynti** > **Arvo** alueelle **Koko**. Arvopisteet laajenevat myynnin arvon mukaisiin kokoihin.
   
   ![](media/power-bi-visualization-scatter/power-bi-bubble.png)

2. Pidä hiiren osoitinta kuplan päällä. Kuplan koko kuvastaa arvoa **Tämän vuoden myynti**.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)

3. Voit määrittää kuplakaaviossa näkyvien arvopisteiden määrän laajentamalla **Visualisoinnit**-ruudun **Muoto**-osiossa olevan kortin **Yleistä** ja säätämällä kohtaa **Tietojen määrä**. Voit määrittää tietojen enimmäismääräksi minkä tahansa luvun, joka on enintään 10 000. Suurten lukujen yhteydessä on suositeltavaa testata toiminta ensin hyvän suorituskyvyn varmistamiseksi. 

    ![Tietojen määrä](./media/power-bi-visualization-scatter/pbi_scatter_data_volume.png) 

   > [!NOTE]
   > Enemmän arvopisteitä voi tarkoittaa pidempää latausaikaa, joten jos haluat julkaista raportteja, joiden rajat ovat asteikon yläpäässä, testaa raporttejasi myös verkossa ja mobiililaitteilla sen varmistamiseksi, että suorituskyky vastaa käyttäjien odotuksia. Ota huomioon, että suurempien arvopistemäärien osalta sinun on testattava tuloksia erilaisilla muototekijöillä hyvän suorituskyvyn varmistamiseksi.

4. Voit [muotoilla visualisoinnin värejä, nimiä, otsikoita, taustaa ja muuta](service-getting-started-with-color-formatting-and-axis-properties.md). Jos haluat [parantaa helppokäyttöisyyttä](../desktop-accessibility.md), harkitse merkin muotojen lisäämistä kullekin riville. Erilaisten merkin muotojen käyttö kullekin riville helpottaa raporttien käyttäjiä erottamaan rivit (tai alueet) toisistaan. Voi valita merkin muodon laajentamalla **Muodot**-kortin ja valitsemalla sitten merkin muodon.

      ![Merkin muoto](./media/power-bi-visualization-scatter/pbi_scatter_marker.png)

   Voit myös muuttaa merkin muodon vinoneliöksi, kolmioksi tai neliöksi:

   ![Neliömerkki](./media/power-bi-visualization-scatter/pbi_scatter_chart_hover_square.png)


## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

### <a name="your-scatter-chart-has-only-one-data-point"></a>**Pistekaaviossasi on vain yksi arvopiste**
Onko pistekaaviossasi vain yksi arvopiste, joka koostaa kaikki arvot X- ja Y-akseleille?  Vai yhdistääkö kaavio kaikki arvot yhdelle vaaka- tai pystysuuntaiselle riville?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

Lisää kenttä **Tiedot**-alueelle ja kerro näin Power BI:lle, miten arvot ryhmitetään. Kentän on oltava yksilöllinen jokaiselle arvopisteelle, jonka haluat piirtää.  
Esimerkiksi yksinkertainen rivin numero tai tunnuskenttä:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Tai jos tiedoissasi ei ole näitä, luo kenttä, joka liittää X- ja Y-arvot yhteen niin, että ne yksilöivät pisteen:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Jos haluat luoda uuden kentän, [käytä Power BI Desktopin kyselyeditoria lisätäksesi indeksisarakkeen](../desktop-add-custom-column.md) tietojoukkoosi.  Lisää sitten tämä sarake visualisointisi **Tiedot**-alueelle.

## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Rekisteröi ilmainen kokeiluversio](https://powerbi.microsoft.com/get-started/)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

