---
title: Täytetyt kartat (koropleettikartat) Power BI:ssä
description: Ohjeet täytettyjen karttojen (koropleettikarttojen) luomiseksi Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 7cd2266ef8d0fd161bda1f9d91a1ceb7f4217675
ms.sourcegitcommit: 769ef3c8cbafd9ad5979eb4023a394ac7dba8d02
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/28/2018
ms.locfileid: "47448887"
---
# <a name="filled-maps-choropleths-in-power-bi"></a>Täytetyt kartat (koropleettikartat) Power BI:ssä
Täytetyssä kartassa käytetään sävytystä tai kuvioita esittämään, miten arvot vaihtelevat suhteellisesti maantieteellisellä alueella.  Suhteelliset erot hahmottuvat nopeasti, kun sävytys vaihtelee vaaleammasta (tarkoittaen harvinaisempaa/pienempää) tummempaan (yleisempi/enemmän).    

![Yhdysvaltain kartta](media/power-bi-visualization-filled-maps-choropleths/large_map.png)

## <a name="what-is-sent-to-bing"></a>Mitä Bingille lähetetään?
Power BI:n voi integroida Bingin kanssa, jotta käytettäviin saadaan oletusarvoiset karttakoordinaatit (prosessia kutsutaan geokoodaukseksi). Kun luot karttavisualisoinnin Power BI -palvelussa tai Power BI Desktopissa, Bingille lähetetään tiedot visualisoinnin luonnissa käytettävistä **Sijainti**-, **Leveysaste**- ja **Pituusaste**-säilöistä.

Palomuuri on ehkä päivitettävä, jotta Bingin geokoodauksessa hyödyntämiä URL-osoitteita voidaan käyttää.  Tässä on luettelo näistä URL-osoitteista:
- https://dev.virtualearth.net/REST/V1/Locations    
- https://platform.bing.com/geo/spatial/v1/public/Geodata    
- https://www.bing.com/api/maps/mapcontrol

Lisätietoja Bingille lähetettävistä tiedoista sekä vinkkejä geokoodauksen parantamiseen saat ohjeaiheesta [Vihjeitä ja vinkkejä karttavisualisointeja varten](power-bi-map-tips-and-tricks.md).

## <a name="when-to-use-a-filled-map"></a>Milloin kannattaa käyttää täytettyä karttaa?
Täytetyt kartat ovat hyvä vaihtoehto, kun:

* haluat esittää kvantitatiivista tietoa kartalla.
* haluat esittää paikkaan liittyviä malleja ja paikkojen välisiä suhteita.
* kun tiedot on standardoitu.
* kun käsittelet sosioekonomisia tietoja.
* kun määritetyt alueet ovat tärkeitä.
* kun haluat yleiskuvan jakaumasta maantieteellisten sijaintien suhteen.

### <a name="prerequisites"></a>Edellytykset
- Power BI -palvelu tai Power BI Desktop
- Myynti- ja markkinointimalli

Jos haluat tehdä samat toimet opetusohjelman mukana, opetusohjelmassa käytetään Power BI -palvelua, ei Power BI Desktopia.

## <a name="create-a-basic-filled-map"></a>Perusluontoisen täytetyn kartan luominen
Tällä videolla Kim luo peruskartan ja muuntaa sen täytetyksi kartaksi.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>

### <a name="get-data-and-add-a-new-blank-page-to-the-report"></a>Nouda tiedot ja lisää uusi tyhjä sivu raporttiin
1. Jos haluat luoda täytetyn kartan opetusohjelman mukana, [lataa itsellesi Myynti- ja markkinointimalli](../sample-datasets.md) kirjautumalla sisään Power BI:hin ja valitsemalla **Nouda tiedot \> Mallit \> Myynti ja markkinointi\> Yhdistä**.
2. Kun näet onnistumisilmoituksen, sulje se ja valitse **Raportit**-välilehti. Avaa raportti valitsemalla **Myynti- ja markkinointimalli**.

   ![Raportit-sisältöluettelo](media/power-bi-visualization-filled-maps-choropleths/power-bi-content-reports2.png)
3. Raportti avautuu Power BI:ssä. Avaa raportti [Muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md) valitsemalla **Muokkaa raporttia**.

4. Lisää uusi sivu valitsemalla keltainen plus-kuvake raportin pohjan alareunasta.

    ![Raportin välilehdet](media/power-bi-visualization-filled-maps-choropleths/power-bi-new-page.png)

### <a name="create-a-filled-map"></a>Täytetyn kartan luominen
1. Valitse Kentät-ruudusta **Alue** \> **Osavaltio**.    

   ![keltainen valintamerkki osavaltion vieressä](media/power-bi-visualization-filled-maps-choropleths/power-bi-state.png)
5. [Muuta kaavio](power-bi-report-change-visualization-type.md) täytetyksi kartaksi. Huomaa, että kohdassa **Sijainti** näkyy nyt **Osavaltio**. Bing Maps käyttää **Sijainti**-kohdan kenttää kartan luomiseen.  Sijainti voi tarkoittaa monenlaisia kelvollisia paikkatietoja: maita, osavaltioita, piirikuntia, kaupunkeja, postinumeroita ja niin edelleen. Bing Maps tarjoaa täytettävät karttamuodot sijainteja varten, olivatpa ne missä päin maailmaa tahansa. Jos Sijainti-kohdassa ei ole kelvollista merkintää, Power BI ei voi luoda täytettyä karttaa.  

   ![mallit, joissa on korostettu täytetyn kartan kuvake](media/power-bi-visualization-filled-maps-choropleths/img003.png)
6. Voit suodattaa kartan näyttämään vain Yhdysvaltojen mannerosat.

   a.  Etsi Visualisoinnit-ruudun alaosasta **Suodattimet**-alue.

   b.  Vie hiiren osoitin kohtaan **Osavaltio** ja napsauta laajennusnuolta.  
   ![Visuaaliset tasosuodattimet, jotka näyttävät osavaltion (Kaikki)](media/power-bi-visualization-filled-maps-choropleths/img004.png)

   c.  Valitse valintaruutu **Kaikki**-kohdan vierestä ja poista valintamerkki vaihtoehdosta **AK**.

   ![Osavaltion avattava valikko, jossa vaihtoehtoja Kaikki ja AK ei ole valittu](media/power-bi-visualization-filled-maps-choropleths/img005.png)
7. Valitse **SalesFact** \> **Asenne**, jolloin valittu vaihtoehto tulee näkyviin kohtaan **Värikylläisyys**. **Värikylläisyys**-kohdassa oleva kenttää määrittää kartan sävytyksen.  
   ![Asennearvo Värien kylläisyys -kentässä hyvä](media/power-bi-visualization-filled-maps-choropleths/power-bi-filled-map.png)
8. Täytetty kartta sävytetään vihreällä ja punaisella niin, että punainen edustaa alempia asennearvoja ja vihreät suurempia, positiivisempia asenteita.  Seuraavassa kuvassa näkyy korostettuna Wyomingin osavaltio (WY), josta voi nähdä, että sen asennearvo on erittäin hyvä, 74.  
   ![musta valintaikkuna, jossa näkyy osavaltio ja asennearvo](media/power-bi-visualization-filled-maps-choropleths/power-bi-wy.png)
9. [Tallenna raportti](../service-report-save.md).
##    <a name="adjust-the-color-formatting"></a>Värimuotoilun säätäminen
Power BI:n avulla voit hallita täytetyn kartan ulkoasua vapaasti.
1. Avaa Muotoilu-ruutu valitsemalla maalitelakuvake.

    ![Muotoilu-ruutu](media/power-bi-visualization-filled-maps-choropleths/power-bi-data-colors.png)

2. Avaa väriasetukset valitsemalla **Tietojen värit**.
3. Määritä keltainen ja sininen pienimmän ja suurimman arvon väreiksi. Lisätä suurin ja pienin arvo tietojesi perusteella. Harjoittele hallinta-asetusten käyttöä, kunnes ulkoasu vastaa odotuksiasi. 

    ![ei-eriytyvät värit](media/power-bi-visualization-filled-maps-choropleths/power-bi-color.png)

## <a name="highlighting-and-cross-filtering"></a>Korostaminen ja ristiinsuodatus
Lisätietoja Suodattimet-paneelin käyttämisestä saat ohjeaiheesta [Suodattimen lisääminen raporttiin](../power-bi-report-add-filter.md).

Yksittäisen sijainnin korostaminen täytetyssä kartassa ristiinsuodattaa muut raporttisivulla olevat visualisoinnit – ja päinvastoin.

1. Tallenna tämä raportti valitsemalla **tiedosto > Tallenna**, ennen kuin siirryt eteenpäin. 

2. Kopioi täytetty kartta painamalla CTRL-C.

3. Avaa Asenne-raporttisivu valitsemalla raporttipohjan alaosasta **Asenne**-välilehti.

    ![Asenne-välilehti valittuna](media/power-bi-visualization-filled-maps-choropleths/power-bi-sentiment-tab.png)

4. Siirrä visualisointeja sivulla ja muuta niiden kokoa tehdäksesi tilaa ja liitä sitten edellisen raportin täytetty kartta painamalla CTRL-V.

   ![Täytetty kartta lisätään Asenne-sivulle](media/power-bi-visualization-filled-maps-choropleths/power-bi-map.png)

5. Valitse täytetystä kartasta jokin osavaltio.  Osavaltio korostuu myös muissa saman sivun visualisoinneissa. Jos valitset esimerkiksi **Texas**, näet, että Asenne on 74. Texas on keskialueella \#23.   
   ![Texas valittuna](media/power-bi-visualization-filled-maps-choropleths/power-bi-texas.png)
2. Valitse arvopiste VanArsdel – Asenne kuukauden mukaan -viivakaaviosta. Toiminto suodattaa täytetyn kartan niin, että se näyttää asennearvot VanArsdelista eikä sen kilpailijasta.  
   ![uusi varjostus](media/power-bi-visualization-filled-maps-choropleths/power-bi-yes.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Karttatiedot saattavat olla epäselviä.  Esimerkiksi Ranskassa on Paris (Pariisi) mutta myös Texasissa on Paris. Olet luultavasti tallentanut maantieteelliset tiedot erillisiin sarakkeisiin: oma sarake kaupunkien nimille, oma osavaltion tai provinssin nimille ja niin edelleen. Bing ei välttämättä pysty sen vuoksi päättelemään, kumpi Paris on kyseessä. Jos tietojoukossasi on valmiiksi mukana leveys- ja pituusasteet, Power BI:ssä on erityiskenttiä, joiden avulla voit poistaa kartoista edellä kuvatun kaltaiset epäselvyydet. Vedä leveystiedot sisältävä kenttä Visualisoinnit \> Leveysaste-alue.  Tee sama pituusastetiedoille.    

![Visualisoinnit- ja Kentät-ruudut](media/power-bi-visualization-filled-maps-choropleths/pbi_latitude.png)

Jos sinulla on oikeudet muokata tietojoukkoa Power BI Desktopissa, katso seuraava video, jossa käsitellään karttaepäselvyyksien vähentämistä.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Co2z9b-s_yM" frameborder="0" allowfullscreen></iframe>

Jos sinulla ei käytettävissäsi leveys- ja pituusastetietoja [päivitä tietojoukkosi näiden ohjeiden mukaan](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7).

Lisäohjeita karttavisualisointien tekemiseen saat ohjeaiheesta [Vihjeitä ja vinkkejä karttavisualisointeja varten](../power-bi-map-tips-and-tricks.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Muotokartta](desktop-shape-map.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)