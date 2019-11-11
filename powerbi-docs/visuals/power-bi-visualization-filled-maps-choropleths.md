---
title: Täytetyt kartat (koropleettikartat) Power BI:ssä
description: Ohjeet täytettyjen karttojen (koropleettikarttojen) luomiseksi Power BI:ssä
author: mihart
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/19/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 9c35e97fba55230277f9f144a5155071656b6add
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73870952"
---
# <a name="filled-maps-choropleths-in-power-bi"></a>Täytetyt kartat (koropleettikartat) Power BI:ssä

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Täytetyssä kartassa käytetään sävytystä tai kuvioita esittämään, miten arvot vaihtelevat suhteellisesti maantieteellisellä alueella.  Suhteelliset erot hahmottuvat nopeasti, kun sävytys vaihtelee vaaleammasta (tarkoittaen harvinaisempaa/pienempää) tummempaan (yleisempi/enemmän).    

![Yhdysvaltain kartta](media/power-bi-visualization-filled-maps-choropleths/large-map.png)

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
Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix).
1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.


## <a name="create-a-basic-filled-map"></a>Perusluontoisen täytetyn kartan luominen
Tällä videolla Kim luo peruskartan ja muuntaa sen täytetyksi kartaksi.
   > [!NOTE]
   > Tässä videossa käytetään Power BI Desktopin vanhempaa versiota.
   > 
   > 

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>

### <a name="create-a-filled-map"></a>Täytetyn kartan luominen
1. Valitse Kentät-ruudusta **Alue** \> **Osavaltio**.    

   ![keltainen valintamerkki osavaltion vieressä](media/power-bi-visualization-filled-maps-choropleths/power-bi-state.png)
2. [Muuta kaavio](power-bi-report-change-visualization-type.md) täytetyksi kartaksi. Huomaa, että kohdassa **Sijainti** näkyy nyt **Osavaltio**. Bing Maps käyttää **Sijainti**-kohdan kenttää kartan luomiseen.  Sijainti voi tarkoittaa monenlaisia kelvollisia paikkatietoja: maita, osavaltioita, piirikuntia, kaupunkeja, postinumeroita ja niin edelleen. Bing Maps tarjoaa täytettävät karttamuodot sijainteja varten, olivatpa ne missä päin maailmaa tahansa. Jos Sijainti-kohdassa ei ole kelvollista merkintää, Power BI ei voi luoda täytettyä karttaa.  

   ![mallit, joissa on korostettu täytetyn kartan kuvake](media/power-bi-visualization-filled-maps-choropleths/img003.png)
3. Voit suodattaa kartan näyttämään vain Yhdysvaltojen mannerosat.

   a.  Etsi Visualisoinnit-ruudun vasemmalta puolelta **Suodattimet**-ruutu. Jos se on pienennettynä, suurenna se.

   b.  Vie hiiren osoitin kohtaan **Osavaltio** ja valitse laajennusnuoli.  
   ![Visuaaliset tasosuodattimet, jotka näyttävät osavaltion (Kaikki)](media/power-bi-visualization-filled-maps-choropleths/img004.png)

   c.  Valitse valintaruutu **Kaikki**-kohdan vierestä ja poista valintamerkki vaihtoehdosta **AK**.

   ![Osavaltion avattava valikko, jossa vaihtoehtoja Kaikki ja AK ei ole valittu](media/power-bi-visualization-filled-maps-choropleths/img005.png)
4. Avaa Muotoilu-ruutu valitsemalla maalitelakuvake ja valitse **Tietojen värit**.

    ![Muotoiluruutu, jossa näkyy Tietojen värit -vaihtoehto](media/power-bi-visualization-filled-maps-choropleths/power-bi-data-color.png)

5. Valitse **Ehdollinen muotoilu** -vaihtoehto napsauttamalla kolmea päällekkäistä pistettä.

    ![Tietojen värit -vaihtoehdon ehdollisen muotoilun painike](media/power-bi-visualization-filled-maps-choropleths/power-bi-conditional-formatting.png)

6. Käytä **Oletusväri - Tietojen värit** -näyttöä määrittääksesi, miten täytetty karttasi sävytetään. Asetukset antavat sinun muun muassa valita, mihin kenttään sävytys perustuu ja miten sävytys lisätään. Tässä esimerkissä käytetään kenttää **Myyntitiedot** > **Asenne**, ja asenteen pienin arvo määritetään punaiseksi ja suurin arvo vihreäksi. Arvot, jotka jäävät maksimi- ja minimiarvon väliin, näkyvät punaisen ja vihreän sävyissä. Käytetyt värit näkyvät näytön alareunassa olevassa kuvassa. 

    ![Oletusarvoinen väriruutu Asenne valittuna](media/power-bi-visualization-filled-maps-choropleths/power-bi-sentiment.png)

7. Täytetty kartta sävytetään vihreällä ja punaisella niin, että punainen edustaa alempia asennearvoja ja vihreät suurempia, positiivisempia asenteita.  Jos haluat lisätietoja, vedä kenttä työkaluvihjeisiin.  Tässä olen lisännyt **Asenne-eron** ja korostanut tilan Idaho (ID), ja että asenne-ero on pieni, 6.
   ![täytetty kartta jossa näkyy Idaho-työkaluvihjeet](media/power-bi-visualization-filled-maps-choropleths/power-bi-filled-map-idaho.png)

10. [Tallenna raportti](../service-report-save.md).

Power BI:n avulla voit hallita täytetyn kartan ulkoasua vapaasti. Vaihtele tietojen väriohjausobjektien kanssa, kunnes olet tyytyväinen ulkoasuun. 

## <a name="highlighting-and-cross-filtering"></a>Korostaminen ja ristiinsuodatus
Lisätietoja Suodattimet-paneelin käyttämisestä saat ohjeaiheesta [Suodattimen lisääminen raporttiin](../power-bi-report-add-filter.md).

Yksittäisen sijainnin korostaminen täytetyssä kartassa ristiinsuodattaa muut raporttisivulla olevat visualisoinnit – ja päinvastoin.

1. Tallenna tämä raportti valitsemalla **tiedosto > Tallenna**, ennen kuin siirryt eteenpäin. 

2. Kopioi täytetty kartta painamalla CTRL-C.

3. Avaa Asenne-raporttisivu valitsemalla raporttipohjan alaosasta **Asenne**-välilehti.

    ![Asenne-välilehti valittuna](media/power-bi-visualization-filled-maps-choropleths/power-bi-sentiment-tab.png)

4. Siirrä visualisointeja ja muuta niiden kokoa sivulla tilan lisäämiseksi, ja liitä sitten komennolla CTRL-V täytetty kartta edellisestä raportista. (Näet seuraavat kuva.)

   ![Täytetty kartta lisätään Asenne-sivulle](media/power-bi-visualization-filled-maps-choropleths/power-bi-map.png)

5. Valitse täytetystä kartasta jokin osavaltio.  Tämä ristiinkorostaa ja -suodattaa muut sivulla olevat visualisoinnit. Jos valitset esimerkiksi **Texas**, näet, että Asenne on 75 ja että Texas on keskialueella 23.   
   ![Texas valittuna](media/power-bi-visualization-filled-maps-choropleths/power-bi-texas.png)
2. Valitse arvopiste VanArsdel – Asenne kuukauden mukaan -viivakaaviosta. Toiminto suodattaa täytetyn kartan niin, että se näyttää asennearvot VanArsdelista eikä sen kilpailijasta.  
   ![uusi varjostus](media/power-bi-visualization-filled-maps-choropleths/power-bi-yes.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Karttatiedot saattavat olla epäselviä.  Esimerkiksi Ranskassa on Paris (Pariisi) mutta myös Texasissa on Paris. Olet luultavasti tallentanut maantieteelliset tiedot erillisiin sarakkeisiin: oma sarake kaupunkien nimille, oma osavaltion tai provinssin nimille ja niin edelleen. Bing ei välttämättä pysty sen vuoksi päättelemään, kumpi Paris on kyseessä. Jos tietojoukossasi on valmiiksi mukana leveys- ja pituusasteet, Power BI:ssä on erityiskenttiä, joiden avulla voit poistaa kartoista edellä kuvatun kaltaiset epäselvyydet. Vedä leveystiedot sisältävä kenttä Visualisoinnit \> Leveysaste-alue.  Tee sama pituusastetiedoille.    

![Visualisoinnit- ja Kentät-ruudut](media/power-bi-visualization-filled-maps-choropleths/pbi-latitude.png)

Jos sinulla on oikeudet muokata tietojoukkoa Power BI Desktopissa, katso seuraava video, jossa käsitellään karttaepäselvyyksien vähentämistä.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Co2z9b-s_yM" frameborder="0" allowfullscreen></iframe>

Jos sinulla ei käytettävissäsi leveys- ja pituusastetietoja mutta sinulla on tietojoukon käyttöoikeus, [päivitä tietojoukkosi näiden ohjeiden mukaisesti](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7).

Lisäohjeita karttavisualisointien tekemiseen saat ohjeaiheesta [Vihjeitä ja vinkkejä karttavisualisointeja varten](../power-bi-map-tips-and-tricks.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Muotokartta](desktop-shape-map.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)