---
title: X- ja Y-akselin ominaisuuksien muokkaaminen
description: X- ja Y-akselin ominaisuuksien muokkaaminen
author: mihart
ms.reviewer: ''
featuredvideoid: 9DeAKM4SNJM
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/3/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 830fbe945405f8ad7aadd7ceac9fb1967daad22b
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/04/2020
ms.locfileid: "75758102"
---
# <a name="customize-x-axis-and-y-axis-properties"></a>X- ja Y-akselin ominaisuuksien muokkaaminen

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Tässä opetusohjelmassa käydään läpi monia tapoja mukauttaa X-akselia ja Y-akselia visualisoinneissa. Kaikilla visualisoinneilla ei ole akseleita. Esimerkiksi ympyräkaaviossa ei ole akseleita. Ja mukautusvaihtoehdot vaihtelevat myös visualisoinnista toiseen. Vaihtoehtoja on niin monta, ettemme voi käsitellä niitä kaikkia tässä yhdessä artikkelissa, joten tutustumme tässä useimmin käytettyihin mukautuksiin ja visualisoinnin **Muotoilu**-ruutuun Power BI -raporttipohjassa.  

Katso, miten Amanda mukauttaa X- ja Y-akseleitaan. Hän esittelee myös erilaisia tapoja hallita ketjutusta käytettäessä porautumista alaspäin ja porautumista ylöspäin.

> [!NOTE]
> Tässä videossa käytetään Power BI:n vanhempaa versiota.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Edellytykset

- Power BI Desktop

- [Jälleenmyyntianalyysimalli ](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)


## <a name="add-a-new-visualization"></a>Uuden visualisoinnin lisääminen

Ennen kuin voit mukauttaa visualisointia, sinun on luotava se.

1. Avaa jälleenmyyntianalyysiotos Power BI Desktopissa.  

2. Lisää uusi sivu valitsemalla alareunasta keltainen plus-kuvake. 

    ![keltainen plus-merkki](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-new-page-icon.png)

1. Valitse **Visualisoinnit**-ruudusta pinotun pylväskaavion kuvake. Tämä lisää tyhjän mallin raporttisi pohjaan.

    ![Näyttökuva Visualisointi-ruudusta ja tyhjästä pinotusta pylväskaaviosta](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-column-chart.png)

1. Määritä X-akselin arvot valitsemalla **Kentät**-ruudussa **Aika** > **FiscalMonth**.

1. Määritä Y-akselin arvot valitsemalla **Kentät**-ruudussa **Myynti** > **Viime vuoden myynti** ja **Myynti** > **Tämän vuoden myynti** > **Arvo**.

    ![Näyttökuva täytetystä pinotusta pylväskaaviosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-build-visual.png)

    Voit nyt mukauttaa X-akselia. Power BI tarjoaa lähes rajattomat visualisoinnin muotoiluvaihtoehdot. 

## <a name="customize-the-x-axis"></a>X-akselin mukauttaminen
X-akselille on monia mukautettavia ominaisuuksia. Voit lisätä ja muokata arvopisteiden otsikoita ja X-akselin otsikkoa. Luokkien osalta voit muokata palkkien, sarakkeiden, viivojen ja alueiden leveyttä, kokoa ja täyttöä. Arvojen osalta voit muokata näyttöyksiköitä, desimaaleja ja ruudukon viivoja. Seuraavassa esimerkissä näytetään sarakekaavion mukautus. Lisätään muutamia mukautuksia, jotta pääset tutustumaan asetuksiin, sen jälkeen voit kokeilla muita omin neuvoin.

### <a name="customize-the-x-axis-labels"></a>X-akselin selitteiden mukauttaminen
X-akselin selitteet näkyvät kaavion sarakkeiden alapuolella. Juuri nyt ne ovat vaaleanharmaita, pieniä ja vaikealukuisia. Muutetaan sitä.

1. Avaa **Visualisoinnit**-ruudusta **Muotoilu** (maalirullakuvake ![Näyttökuva maalirullakuvakkeesta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller-icon.png) ) mukautusasetusten paljastamiseksi.

2. Laajenna X-akselin asetukset.

   ![Näyttökuva X-akselin vaihtoehdoista.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-axis-x.png)

3. Siirrä **X-akselin** liukusäädin tilaan **Käytössä**.

    ![Näyttökuva Käytössä-liukusäätimestä.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-slider-on.png)

    Saatat haluta asettaa X-akselin tilaan **Pois** esimerkiksi silloin, kun visualisointi selittää itse itsensä ilman selitteitä tai jos raporttisivullasi on tungosta ja sinun tarvitsee tehdä tilaa voidaksesi näyttää lisää tietoa.

4. Muotoile tekstin väriä, kokoa ja fonttia:

    - **Väri**: Valitse musta

    - **Tekstin koko**: Syötä *14*

    - **Fonttiperhe**: Valitse **Arial Black**

    - **Sisempi täyttö**: Syötä *40%*

        ![Näyttökuva, jossa on selitteitä kulmassa](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-formatting-x.png)
    
5. Ehkä et pidä siitä, miten X-akselin teksti näytetään lävistäjällä. Sinulla on useita vaihtoehtoja. 
    - Muuta tekstin koko pienemmäksi kuin 14.
    - Tee visualisoinnista suurempi. 
    - Näytä vähemmän sarakkeita ja lisää vierityspalkki suurentamalla **luokan vähimmäisleveyttä**. 
    
    Tässä olemme valinneet toisen vaihtoehdon ja tarttuneet yhteen koonmuuttamispalkeista visualisoinnin tekemiseksi leveämmäksi. Siihen mahtuu nyt 14 pisteen teksti ilman tarvetta näyttää tekstiä kulmassa tai vierityspalkilla varustettuna. 

   ![Kaavio- ja muotoiluruutu, jossa selitteet ovat vaakasuunnassa](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-stretch.png)

### <a name="customize-the-x-axis-title"></a>X-akselin otsikon mukauttaminen
Kun X-akselin otsikko on **Käytössä**, X-akselin otsikko näkyy X-akselin selitteiden alla. 

1. Määritä ensin X-akselin otsikon tilaksi **Käytössä**.  

    ![Otsikon liukusäädin](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-title-on.png)

    Ensimmäiseksi huomaat, että visualisointisi X-akselilla on nyt oletusotsikko.  Tässä tapauksessa se on **FiscalMonth**.

   ![Kaavio, jonka alalaidassa otsikko näkyy](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-title.png)

1. Muotoile otsikon tekstin väriä, kokoa ja fonttia:

    - **Otsikon väri**: Valitse oranssi

    - **Akselin otsikko**: Kirjoita *Fiscal Month* (muista välilyönti)

    - **Otsikon tekstin koko**: Anna *18*

    Kun olet suorittanut mukautukset, pinotun pylväskaaviosi tulisi näyttää suunnilleen tältä:

    ![Näyttökuva mukautetusta pinotusta pylväskaaviosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-title-formatted.png)

1. Tallenna tekemäsi muutokset ja siirry seuraavaan osioon. Jos haluat palauttaa kaikki muutokset, valitse **Palauta oletusasetukseen** **X-akselin** mukauttamisruudun alareunassa. Seuraavaksi mukautat Y-akselin.

## <a name="customize-the-y-axis"></a>Y-akselin mukauttaminen
Y-akselilla on monia mukautettavia ominaisuuksia. Voit lisätä ja muokata arvopisteiden otsikkoja, Y-akselin otsikkoa ja ruudukkoviivoja. Arvojen osalta voit muokata näyttöyksiköitä, desimaaleja, aloituspistettä ja loppupistettä. Luokkien osalta taas voit muokata palkkien, sarakkeiden, viivojen ja alueiden leveyttä, kokoa ja täyttöä. 

Seuraavassa esimerkissä jatkamme pylväskaavion mukauttamista. Tehdään muutamia muutoksia, jotta pääset tutustumaan asetuksiin, sen jälkeen voit kokeilla muita omin neuvoin.

### <a name="customize-the-y-axis-labels"></a>Y-akselin selitteiden mukauttaminen
Y-akselin selitteet näytetään oletusarvoisesti vasemmalla. Juuri nyt ne ovat vaaleanharmaita, pieniä ja vaikealukuisia. Muutetaan sitä.

1. Laajenna Y-akselin asetukset.

   ![Näyttökuva Y-akselin vaihtoehdoista.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-axis-y.png)

1. Siirrä **Y-akselin** liukusäädin tilaan **Käytössä**.  

    ![Näyttökuva Käytössä-liukusäätimestä.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-on.png)

    Haluat ehkä poistaa Y-akselin käytöstä säästääksesi tilaa lisätiedoille.

1. Muotoile tekstin väriä, kokoa ja fonttia:

    - **Väri**: Valitse musta

    - **Tekstin koko**: Anna *10*

    - **Näytön yksiköt**: Valitse **Miljoonat**

    ![Kaavio Y-akselin muotoilun jälkeen](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-formatting-y.png)

### <a name="customize-the-y-axis-title"></a>Y-akselin otsikon mukauttaminen
Kun Y-akselin otsikko on **Käytössä**, Y-akselin otsikko näkyy Y-akselin selitteiden vierellä. Tämän visualisoinnin tapauksessa Y-akselin otsikko ei paranna visualisointia, joten jätä **Otsikko**-kohdan tilaksi **Pois käytöstä**. Lisäämme Y-akselin otsikon myöhemmin kaksoisakselivisualisointiin tässä opetusohjelmassa. 

### <a name="customize-the-gridlines"></a>Ruudukkoviivojen mukauttaminen
Varmista, että ruudukko erottuu, muuttamalla väriä ja suurentamalla viivanleveyttä:

- **Väri**: Valitse oranssi

- **Viivanleveys**: Syötä *2*

Mukautusten jälkeen pylväskaavion pitäisi näyttää suunnilleen tältä:

![Näyttökuva kaaviosta, jossa on mukautettu Y-akseli.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-gridline.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>Visualisointien mukauttaminen kahdelle Y-akselille

Eräät visualisoinnit voivat hyötyä kahdesta Y-akselista. Yhdistelmäkaavio on hyvä esimerkki. Ennen kuin voimme muotoilla kaksinkertaisen Y-akselin, luomme yhdistelmäkaavio, joka vertailee myynnin ja käyttökatteen trendejä.  

### <a name="create-a-chart-with-two-y-axes"></a>Kahden Y-akselin kaavion luominen

1. Valitse pylväskaavio ja muuta se *Viivan ja pinotun sarakkeen* muotoiseksi kaavioksi. Tämä visualisointityyppi tukee yksirivisen kaavion arvoa ja useita pinottavia sarakearvoja. 

    ![Näyttökuva visualisointiruudusta, jossa on korostettu viivan ja pinotun pylväskaavion kuvake.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo.png)
   

2. Vedä **Myynti** > **Käyttökate viime vuodelta %** Kentät-ruudusta **Viiva-arvot** -säilöön.

    ![Näyttökuva viivasta ja pinotusta pylväskaaviosta, joissa on esitetty selvästi kaikki kolme arvoa.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-add-line.png)

    
3. Muotoile visualisointi uudelleen ja poista kulmikkaat X-akselin selitteet. 

   ![Yhdistelmäkaavio ja muotoiluruutu, joiden kirjainkoko on pienennetty 12:ksi](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-font-size.png)

   Power BI luo kaksi Y-akselia, jolloin arvot voidaan skaalata eri tavalla. Vasen akseli mittaa myyntidollareita ja oikea akseli mittaa voittoprosenttia.

### <a name="format-the-second-y-axis"></a>Toisen Y-akselin muotoileminen
Koska aloitimme visualisoinnilla, jossa oli yksi muotoiltu Y-akseli, Power BI loi toisen Y-akselin samoin asetuksin. Voimme kuitenkin muuttaa sen. 

1. Voit näyttää muotoiluvaihtoehdot valitsemalla maalirullakuvakkeen **Visualisoinnit**-ruudussa.

1. Laajenna Y-akselin asetukset.

1. Vieritä alaspäin, kunnes löydät **Näytä toissijainen** -vaihtoehdon. Tarkista, että se on **Käytössä**. Toissijainen Y-akseli edustaa viivakaaviota.

   ![Näyttökuva Näytä toissijainen -vaihtoehdosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-show-secondary.png)

1. (Valinnainen) Mukauta kahden akselin fontin väri, koko ja näytön yksiköt. Jos vaihdat jommankumman akselin **sijaintia**, akselit vaihdetaan päittäin.

### <a name="add-titles-to-both-axes"></a>Otsikoiden lisääminen molempiin akseleihin

Akselien otsikoiden lisääminen auttaa näin mutkikkaassa visualisoinnissa.  Otsikot auttavat työtovereita ymmärtämään visualisoinnin paremmin.

1. Ota sekä **Y-akselin (sarake)** että **Y-akselin (rivi)** **otsikot** **käyttöön**.

1. Määritä **tyylin** arvoksi **Näytä vain otsikko** kummallekin.

   ![Näyttökuva otsikosta ja tyylin vaihtoehdoista.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-show-title.png)

1. Yhdistelmäkaavio näyttää nyt kaksi akselia otsikoilla.

   ![Näyttökuva mukautetusta kahden Y-akselin kaaviosta.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-titles-on.png)

1. Muotoile otsikot. Tässä esimerkissä olemme lyhentäneet toisen otsikoista ja vähentäneet molempien kirjainkokoa. 
    - Fonttikoko: **9**
    - **Akselin otsikko** lyhennetty ensimmäiselle Y-akselille (pylväskaavio): Myynti viime ja tänä vuonna

    ![Näyttökuva yhdistelmäkaaviosta, jossa otsikot näkyvät kokonaan.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual.png)



Katso lisätietoja kohdista [Vinkkejä värimuotoiluun Power BI:ssä](service-tips-and-tricks-for-color-formatting.md) ja [Mukauta visualisoinnin otsikoita, selitteitä ja taustoja](power-bi-visualization-customize-title-background-and-legend.md). Etsi myös pian tulevia uusia päivityksiä muotoiluruuduista. 

## <a name="next-steps"></a>Seuraavat vaiheet

- [Visualisoinnit Power BI -raporteissa](power-bi-report-visualizations.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
