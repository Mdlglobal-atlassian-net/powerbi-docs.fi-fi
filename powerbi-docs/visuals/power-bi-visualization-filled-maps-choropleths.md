---
title: Täytetyt kartat (koropleettikartat) Power BI:ssä
description: Ohjeet täytettyjen karttojen (koropleettikarttojen) luomiseksi Power BI:ssä
author: mihart
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/05/2019
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: ba344d66f967d502d9de8adef7defcae434fb3ef
ms.sourcegitcommit: a199dda2ab50184ce25f7c9a01e7ada382a88d2c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/06/2020
ms.locfileid: "82865456"
---
# <a name="create-and-use-filled-maps-choropleth-maps-in-power-bi"></a>Täytettyjen karttojen (koropleettikartat) luominen ja käyttäminen Power BI:ssä

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

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
Tässä oppaassa käytetään [myynti- ja markkinointi-PBIX-mallitiedostoa](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix).
1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. Etsi oma kappaleesi **PBIX-esimerkkitiedostosta**

1. Avaa **myynti- ja markkinointi-PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.

> [!NOTE]
> Raportin jakaminen työtoverin kanssa Power BI:ssä edellyttää, että teillä kummallakin on oma Power BI Pro -käyttöoikeus tai että raportti on tallennettu Premium-kapasiteettiin.    

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

    ![Muotoiluruutu, jossa näkyy Tietojen värit -vaihtoehto](media/power-bi-visualization-filled-maps-choropleths/power-bi-colors-data.png)

5. Valitse **Ehdollinen muotoilu** -vaihtoehto napsauttamalla kolmea päällekkäistä pistettä.

    ![Tietojen värit -vaihtoehdon ehdollisen muotoilun painike](media/power-bi-visualization-filled-maps-choropleths/power-bi-conditional.png)

6. Käytä **Oletusväri - Tietojen värit** -näyttöä määrittääksesi, miten täytetty karttasi sävytetään. Asetukset antavat sinun muun muassa valita, mihin kenttään sävytys perustuu ja miten sävytys lisätään. Tässä esimerkissä käytetään kenttää **SalesFact** > **Sentiment**, ja asenteen pienin arvo määritetään oranssiksi ja suurin arvo siniseksi. Arvot, jotka jäävät maksimi- ja minimiarvon väliin, näkyvät oranssin ja sinisen sävyissä. Käytetyt värit näkyvät näytön alareunassa olevassa kuvassa. 

    ![Oletusarvoinen väriruutu Asenne valittuna](media/power-bi-visualization-filled-maps-choropleths/power-bi-sentiment-field.png)

7. Täytetty kartta sävytetään vihreällä ja punaisella niin, että punainen edustaa alempia asennearvoja ja vihreät suurempia, positiivisempia asenteita.  Jos haluat lisätietoja, vedä kenttä työkaluvihjeisiin.  Olemme lisänneet **SalesFact** > **Sentiment -välin**. Idahon (ID) tilan korostaminen osoittaa, että asenneväli on alhainen, 6.
   ![täytetty kartta jossa näkyy Idaho-työkaluvihjeet](media/power-bi-visualization-filled-maps-choropleths/power-bi-idaho-filled-map.png)

10. [Tallenna raportti](../service-report-save.md).

Power BI:n avulla voit hallita täytetyn kartan ulkoasua vapaasti. Harjoittele väriasetusten käyttöä, kunnes ulkoasu vastaa odotuksiasi. 

## <a name="highlighting-and-cross-filtering"></a>Korostaminen ja ristiinsuodatus
Lisätietoja Suodattimet-paneelin käyttämisestä saat ohjeaiheesta [Suodattimen lisääminen raporttiin](../power-bi-report-add-filter.md).

Yksittäisen sijainnin korostaminen täytetyssä kartassa ristiinsuodattaa muut raporttisivulla olevat visualisoinnit – ja päinvastoin.

1. Tallenna tämä raportti valitsemalla **tiedosto > Tallenna**, ennen kuin siirryt eteenpäin. 

2. Kopioi täytetty kartta painamalla CTRL-C.

3. Avaa Asenne-raporttisivu valitsemalla raporttipohjan alaosasta **Asenne**-välilehti.

    ![Asenne-välilehti valittuna](media/power-bi-visualization-filled-maps-choropleths/power-bi-sentiment-tab.png)

4. Siirrä visualisointeja ja muuta niiden kokoa sivulla tilan lisäämiseksi, ja liitä sitten komennolla CTRL-V täytetty kartta edellisestä raportista. (Näet seuraavat kuva.)

   ![Täytetty kartta lisätään Asenne-sivulle](media/power-bi-visualization-filled-maps-choropleths/power-bi-map.png)

5. Valitse täytetystä kartasta jokin osavaltio.  Tämä ristiinkorostaa ja -suodattaa muut sivulla olevat visualisoinnit. Valitsemalla **Texas** ristiinsuodatat kortteja ja ristiinkorostat palkkikaaviota. Tästä näet, että asenne on 75 ja että Texas on keskialueella 23.   
   ![Texas valittuna](media/power-bi-visualization-filled-maps-choropleths/power-bi-filter.png)
2. Valitse arvopiste VanArsdel – Asenne kuukauden mukaan -viivakaaviosta. Toiminto suodattaa täytetyn kartan niin, että se näyttää asennearvot VanArsdelista eikä sen kilpailijasta.  
   ![uusi varjostus](media/power-bi-visualization-filled-maps-choropleths/power-bi-vanarsdel.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Karttatiedot saattavat olla epäselviä.  Esimerkiksi Ranskassa on Paris (Pariisi) mutta myös Texasissa on Paris. Olet luultavasti tallentanut maantieteelliset tiedot erillisiin sarakkeisiin: oma sarake kaupunkien nimille, oma osavaltion tai provinssin nimille ja niin edelleen. Bing ei välttämättä pysty sen vuoksi päättelemään, kumpi Paris on kyseessä. Jos tietojoukossasi on valmiiksi mukana leveys- ja pituusasteet, Power BI:ssä on erityiskenttiä, joiden avulla voit poistaa kartoista edellä kuvatun kaltaiset epäselvyydet. Vedä leveystiedot sisältävä kenttä Visualisoinnit \> Leveysaste-alue.  Tee sama pituusastetiedoille.    

![Visualisoinnit- ja Kentät-ruudut](media/power-bi-visualization-filled-maps-choropleths/pbi-latitude.png)

Jos sinulla on oikeudet muokata tietojoukkoa Power BI Desktopissa, katso seuraava video, jossa käsitellään karttaepäselvyyksien vähentämistä.

> [VIDEO https://www.youtube.com/embed/Co2z9b-s_yM ]

Jos sinulla ei käytettävissäsi leveys- ja pituusastetietoja mutta sinulla on tietojoukon käyttöoikeus, [päivitä tietojoukkosi näiden ohjeiden mukaisesti](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7).

Lisäohjeita karttavisualisointien tekemiseen saat ohjeaiheesta [Vihjeitä ja vinkkejä karttavisualisointeja varten](../power-bi-map-tips-and-tricks.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Muotokartta](desktop-shape-map.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
