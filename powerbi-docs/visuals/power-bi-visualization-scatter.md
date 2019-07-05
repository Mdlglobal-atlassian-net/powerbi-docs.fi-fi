---
title: Piste-, kupla- ja pistetulostuskaaviot Power BI:ssä
description: Piste-, pistetulostus- ja kuplakaaviot Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: PVcfPoVE3Ys
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8222194359077cb0d88286a33d1c9b2a05f6bd80
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390934"
---
# <a name="scatter-charts-bubble-charts-and-dot-plot-charts-in-power-bi"></a>Piste-, kupla- ja pistetulostuskaaviot Power BI:ssä

Pistekaaviossa on aina kaksi arvoakselia, jotka näyttävät yhden numeerisen tietosarjan vaakasuuntaisella akselilla ja toisen numeerisen arvosarjan pystysuuntaisella akselilla. Kaaviossa näytetään arvopisteet numeerisen arvon X ja Y leikkauskohdassa yhdistämällä nämä kaksi arvoa yhdeksi arvopisteeksi. Power BI voi jakaa nämä arvopisteet tasaisesti tai epätasaisesti vaakasuuntaiselle akselille kaavion edustamien tietojen mukaan.

Katso tästä videosta, miten Will luo pistekaavion, ja noudata sitten seuraavia ohjeita luodaksesi sellaisen itse.

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

Pistetulostuskaavio muistuttaa kuplakaaviota ja pistekaaviota, mutta X-akselille voi tulostaa myös numeerisia tai luokittaisia tietoja.

![Näyttökuva pistetulostuskaaviosta.](media/power-bi-visualization-scatter/power-bi-dot-plot.png)

Se on mainio valinta, jos haluat sisällyttää X-akselille luokittaista tietoa.

## <a name="prerequisites"></a>Edellytykset

* Power BI -palvelu

* Jälleenmyyntianalyysimallin raportti

## <a name="create-a-scatter-chart"></a>Pistekaavion luominen

Seuraa mukana kirjautumalla sisään [Power BI -palveluun](https://app.powerbi.com) ja avaamalla [Jälleenmyyntianalyysimalli](../sample-datasets.md)-raportti [Muokkaa raporttia](../service-interact-with-a-report-in-editing-view.md) -näkymässä.

1. Valitse ![Näyttökuva keltaisesta Plus-kuvakkeesta.](media/power-bi-visualization-scatter/power-bi-yellow-plus-icon.png) tyhjän raporttisivun luomiseksi.

1. Valitse **Kentät**-ruudusta seuraavat kentät:

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

    ![työkaluvihjeiden näyttö](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)

1. Voit määrittää kuplakaaviossa näkyvien arvopisteiden määrän laajentamalla **Visualisoinnit**-ruudun **Muotoilu**-osiossa olevaa **Yleistä**-kohtaa ja säätämällä **Tietojen määrä**-kohtaa.

    ![Näyttökuva Visualisoinnit-ruudusta, jossa on korostettu Muotoile-kuvake, yleinen avattava valikko ja Tietomäärä-vaihtoehto.](media/power-bi-visualization-scatter/pbi_scatter_data_volume.png)

    Voit määrittää tietojen enimmäismääräksi minkä tahansa luvun, joka on enintään 10 000. Suurten lukujen yhteydessä on suositeltavaa testata toiminta ensin hyvän suorituskyvyn varmistamiseksi.

    > [!NOTE]
    > Useammat arvopisteet saattavat merkitä pidempää latausaikaa. Jos haluat julkaista raportteja, joissa on rajat asteikon lopussa, testaa raporttisi myös verkossa ja mobiililaitteessa. Voit näin varmistaa, että kaavion suorituskyky vastaa käyttäjien odotuksia.

1. Voit [muotoilla visualisoinnin värejä, nimiä, otsikoita, taustaa ja muuta](service-getting-started-with-color-formatting-and-axis-properties.md).

    Jos haluat [parantaa helppokäyttöisyyttä](../desktop-accessibility.md), harkitse merkin muotojen lisäämistä kullekin riville. Jos haluat valita merkin muodon, laajenna **Muodot**-kohtaa, valitse **Merkin muoto** ja valitse muoto.

    ![Näyttökuva avattavasta Muodot-valikosta, jossa on korostettu Merkin muoto -vaihtoehdot.](media/power-bi-visualization-scatter/pbi_scatter_marker.png)

    Voit muuttaa merkin muodon vinoneliöksi, kolmioksi tai neliöksi. Erilaisten merkin muotojen käyttö kullekin riville helpottaa raporttien käyttäjiä erottamaan rivit (tai alueet) toisistaan.

## <a name="create-a-dot-plot-chart"></a>Pistetulostuskaavion luominen

Luo pistetulostuskaavio korvaamalla **numeerinen X-akseli**-kenttä luokittaisella kentällä.

Poista **X-akselin** ruudusta **Myynti/neliöjalka** ja korvaa se kentällä **Alue** > **Aluejohtaja**.

![Näyttökuva uudesta pistetulostuskaaviosta.](media/power-bi-visualization-scatter/power-bi-dot-plot-squares.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

### <a name="your-scatter-chart-has-only-one-data-point"></a>Pistekaaviossasi on vain yksi arvopiste

Onko pistekaaviossasi vain yksi arvopiste, joka koostaa kaikki arvot X- ja Y-akseleille?  Vai yhdistääkö kaavio kaikki arvot yhdelle vaaka- tai pystysuuntaiselle riville?

![Näyttökuva pistekaaviosta, jossa on yksi arvopiste.](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

Lisää kenttä **Tiedot**-säilöön ja kerro näin Power BI:lle, miten arvot ryhmitetään. Kentän on oltava yksilöllinen jokaiselle arvopisteelle, jonka haluat piirtää. Esimerkiksi yksinkertainen rivin numero tai tunnuskenttä.

![Näyttökuva pistekaaviosta, jossa RowNum on lisätty Tiedot-säilöön.](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Tai jos tiedoissasi ei ole näitä, luo kenttä, joka liittää X- ja Y-arvot yhteen niin, että ne yksilöivät pisteen:

![Näyttökuva pistekaaviosta, jossa TempTime on lisätty Tiedot-säilöön.](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Jos haluat luoda uuden kentän, [käytä Power BI Desktopin kyselyeditoria lisätäksesi indeksisarakkeen](../desktop-add-custom-column.md) tietojoukkoosi. Lisää sitten tämä sarake visualisointisi **Tiedot**-säilöön.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Suuren tiheyden näytteenotto Power BI:n pistekaavioissa](desktop-high-density-scatter-charts.md)

* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
