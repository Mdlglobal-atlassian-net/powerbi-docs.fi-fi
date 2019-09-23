---
title: 'Opetusohjelma: Verkkosivun tietojen tuonti ja analysointi'
description: 'Opetusohjelma: Verkkosivun tietojen tuonti ja analysointi Power BI Desktopissa'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: d6cdcf47b42be4a9b541aa355efb3dd5e9667204
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514626"
---
# <a name="tutorial-analyze-web-page-data-using-power-bi-desktop"></a>Opetusohjelma: Verkkosivun tietojen analysointi Power BI Desktopissa

Pitkäaikaisena jalkapallofanina haluat raportin UEFA Euroopan mestaruuskisojen voittajista. Power BI Desktopilla voit tuoda nämä tiedot verkkosivulta raporttiin ja luoda visualisointeja näyttämään tietoja. Tässä opetusohjelmassa opit miten Power BI Desktopilla:

- Muodostetaan yhteys verkkotietolähteeseen ja siirrytään käytettävissä olevien taulukoiden välillä,
- muotoillaan ja muunnetaan tietoa **Power Query -editorissa**,
- annetaan kyselylle nimi ja tuodaan se Power BI Desktop -raporttiin ja 
- luodaan ja mukautetaan kartan ja ympyräkaavio visualisointeja.

## <a name="connect-to-a-web-data-source"></a>Yhteyden muodostaminen verkkotietolähteeseen

Voit saada UEFA voittajatiedot tulostaulukosta UEFA mestaruuskisojen Wikipedia-sivulta osoitteesta http://en.wikipedia.org/wiki/UEFA_European_Football_Championship. 

![Wikipedian tulostaulukko](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

Huomaa, että verkkoyhteydet muodostetaan vain perustodentamista käyttämällä. Todentamista vaativat verkkosivustot eivät välttämättä toimi kunnolla verkkoyhdistimen kanssa.

Tietojen tuominen:

1. Power BI Desktopin **Koti** -valintanauhan välilehdeltä, avaa nuoli **Nouda tiedot**-kohdan vierestä ja valitse sitten **Verkko**.
   
   ![Tietojen noutaminen valintanauhasta](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web3.png) 
   
   >[!NOTE]
   >Voit myös valita **Nouda tiedot** kohteen itse, tai valita **Nouda tiedot** Power BI:n **Aloita** -valintaikkunasta, valitse sitten **Verkko** ja **Kaikki** tai **Muut** **Nouda tiedot** -valintaikkunasta ja valitse vielä **Yhdistä**.
   
2. Liitä URL-osoite **Verkosta** `http://en.wikipedia.org/wiki/UEFA_European_Football_Championship`-valintaikkunan **URL** -tekstiruutuun ja valitse sitten **OK**.
   
    ![Tietojen noutaminen valintaikkunasta](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web2.png)
   
   Kun olet yhdistänyt Wikipedia-verkkosivuun, Power BI **Navigator** -valintaikkunassa näkyy luettelo sivun käytettävissä olevista taulukoista. Voit valita minkä tahansa taulukon nimen tarkastellaksesi sen sisältämiä tietoja. **Tulokset [muokkaa]** -tauluko sisältää haluamasi tiedot, vaikka ne eivät olekaan tarkalleen haluamassasi muodossa. Voit uudelleenmuotoilla ja puhdistaa tiedot ennen niiden lataamista raporttiin. 
   
   ![Siirtymistoiminto-valintaikkuna](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)
   
   >[!NOTE]
   >**Esikatselu**-ruutu näyttää viimeisimmän valitun taulukon, mutta kaikki valitut taulukot ladataan **Power Query -editoriin** kun valitset **Muokkaa** tai **Lataa**. 
   
3. Valitse **Tulokset [muokkaa]** -taulukko **Siirtymistoiminto**-luettelosta ja valitse sitten **Muokkaa**. 
   
   Taulukon esikatselu avautuu **Power Query -editoriin**, jonka avulla voit muokata ja puhdistaa tietoja. 
   
   ![Power Query -editori](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)
   
## <a name="shape-data-in-power-query-editor"></a>Tietojen muotoileminen Power Query -editorissa

Haluat tehdä tietojen tarkastelemisesta helpompaa näyttämällä vain vuodet sekä voittajamaat. Voit käyttää **Power Query -editoria** tietojen muotoilemiseen ja puhdistamiseen.

Poista taulukosta ensin kaikki sarakkeet lukuun ottamatta sarakkeita **Vuosi** ja **Finaalin voittajat** -sarakkeita.

1. Valitse **Power Query -editorin** ruudukosta **Vuosi** ja **Finaalin voittajat** -sarakkeet (pidä **Ctrl**-näppäin pohjassa valitaksesi useita kohteita).
   
2. Napsauta hiiren kakkospainiketta ja valitse avautuvasta valikosta **Poista muut sarakkeet** tai **Poista sarakkeet** > **Poista muut sarakkeet** **Hallitse sarakkeita** -ryhmästä **Koti**-valintanauhan välilehdeltä, poistaaksesi kaikki muut sarakkeet taulukosta. 
   
   ![Poista muut sarakkeet -valikko](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web6.png) tai ![Poista muut sarakkeet -valintanauha](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

Poista seuraavaksi ylimääräinen **Tiedot**-sana **Vuosi** -sarakkeen soluista.

1. Valitse **Vuosi**-sarake.
   
2. Napsauta hiiren kakkospainiketta ja valitse avautuvasta valikosta **Korvaa arvot** tai valitse **Korvaa arvot** **Muunna** -ryhmän **Koti**-välilehden valintanauhalta (löytyy myös **Mikä tahansa sarake** -ryhmän **Muunna** välilehdeltä). 
   
   ![Korvaa arvot -valikko](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web7.png) tai ![Korvaa arvot -valintanauha](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8a.png)
   
3. Syötä **Korvaa arvot** -valintaikkunassa **Tiedot**-teksti **Etsittävä arvo** -tekstiruutuun ja jätä **Korvaa arvolla** -tekstiruutu tyhjäksi. Valitse sitten **OK** poistaaksesi “Tiedot” **Vuosi**-sarakkeen soluista.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

Jotkin **Vuosi**-sarakkeen solut sisältävät vain sana ”vuosi” numeraalisen arvon sijaan. Voit suodattaa **Vuosi**-sarakkeen näyttämään vain rivit, jotka eivät sisällä sanaa “vuosi”. 

1. Napsauta **Vuosi**-sarakkeen suodatinnuolta.
   
2. Vieritä avautuvaa valikkoa alas ja tyhjennä valintaruutu **Vuosi** -vaihtoehdon vieressä. Valitse sitten **OK** poistaaksesi **Vuosi**-sarakkeen rivit, joissa on vain sana ”vuosi”. 

   ![Tietojen suodatus](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

Kun **Vuosi**-sarakkeen tiedot on puhdistettu, voit siirtyä työstämään **Finaalin voittaja** -saraketta. Koska käsittelemme ainoastaan finaalien voittajatietoja, voimme nimetä tämän sarakkeen uudelleen **Maa**-sarakkeeksi. Sarakkeen uudelleennimeäminen:

1. Kaksoisnapsauta tai napauta ja pidä pohjassa **Finaalin voittaja** -sarakeotsikkoa, tai 
   - napsauta hiiren kakkospainikkeella **Finaalin voittaja** -sarakeotsikkoa ja valitse avautuvasta valikosta **Nimeä uudelleen**, tai 
   - valitse **Finaalin voittaja** -sarake ja valitse **Nimeä uudelleen** **Mikä tahansa sarake** -ryhmän valintanauhan **Muunna** -välilehdeltä. 
   
   ![Nimeä uudelleen -valikko](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7a.png) tai ![Nimeä uudelleen -valintanauha](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8.png)
   
2. Syötä sana **Maa** otsikkoon ja paina **Enter** nimetäksesi sarakkeen uudelleen.

Voit myös suodattaa **Maa**-sarakkeesta pois rivit, jotka eivät sisällä käypiä arvoja, kuten ”2020”. Voit käyttää suodatinvalikkoa samalla tavalla kuin suodattaessasi **Vuosi**-sarakkeen arvoja, tai voit:

1. napsauttaa hiiren kakkospainikketta **Maa**-solun **2020**-rivillä, jonka on arvo *tyhjä*. 
2. Valitse **Tekstisuodattimet** > **Ei ole yhtä suuri kuin**-pikavalikosta rivit, jotka sisältävät solun arvon.
   
   ![Tekstisuodatin](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web11.png)
   
## <a name="import-the-query-into-report-view"></a>Kyselyn tuominen raporttinäkymään

Nyt kun olet muotoillut tietoja haluamallasi tavalla, voit nimetä kyselysi ”Euroopan-mestaruus voittajat”-nimiseksi ja tuoda sen raporttiisi.

1. Syötä **Euroopan-mestaruus voittajat** **Kyselyasetukset**-ruudun **Nimi**-tekstikenttään ja paina **Enter**.
   
   ![Kyselyn nimeäminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

2. Valitse **Sulje ja ota käyttöön** > **Sulje ja ota käyttöön** **Koti** -valintanauhan välilehdeltä.
   
   ![Sulje ja ota käyttöön](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)
   
Kysely ladataan Power BI Desktopin **Raporttinäkymään**, jossa se näkyy **Kentät** -ruudussa. 
   
   ![Kentät-ruutu](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)
>[!TIP]
>Pääset aina takaisin **Power Query -editoriin**, jossa voit muokata ja parannella kyselyäsi:
>- valitsemalla **Lisäasetuksista** kolme pistettä ( **...** ) **Euroopan-mestaruus voittajat**-kohdan vierestä**Kentät**-ruudusta ja valitsemalla avautuvasta valikosta **Muokkaa kyselyä** tai
>- valitsemalla **Muokkaa kyselyitä** > **Muokkaa kyselyitä** **Ulkoiset tiedot** - ryhmästä raporttinäkymän **Koti** -valintanauhasta. 

## <a name="create-a-visualization"></a>Visualisoinnin luominen

Luodaksesi tietoihin perustuvan visualisoinnin: 

1. Valitse **Maa** -kenttä **Kentät**-ruudusta tai vedä se raporttipohjaan. Power BI Desktop tunnistaa tiedot maan niminä ja luo automaattisesti **Kartta** -visualisoinnin. 
   
   ![Kartta-visualisointi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web14.png)
   
2. Suurenna karttaa vetämällä kulmien kahvoista, jotta kaikki maiden nimet ovat näkyvissä.  

   ![Suurenna kartta](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
   
3. Kartassa näkyvät kaikki identtiset arvopisteet jokaisesta maasta, jotka on voittanut Euro Cup -turnauksen. Saadaksesi kunkin arvopisteen koon kuvastamaan kuinka usein maan on voittanut, vedä **Vuosi**-kenttä **Vedä tietokentät tähän** -kohtaan **Koko**-valikon alla, **Visualisoinnit**-ruudun alaosassa. Kenttä muuttuu automaattisesti **Vuosien määrä** -mittariksi ja kartan visualisointi näyttää nyt niiden maiden arvopisteet suurempina, jotka ovat voittaneet useimpia turnauksia. 
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)
   

## <a name="customize-the-visualization"></a>Visualisointien mukauttaminen

Visualisointien luominen tietojen perusteella on siis hyvin helppoa. Helppoa on myös niiden mukauttaminen halutusti niin, että ne esittävät tiedot paremmin. 

### <a name="format-the-map"></a>Kartan muotoileminen
Voit muuttaa visualisoinnin ulkoasua valitsemalla sen ja valitsemalla sitten **Muotoile**-kuvakkeen (maalirulla) **Visualisoinnit**-ruudussa. Visualisointisi Saksa-arvopisteet saattavat olla esimerkiksi harhaanjohtavia, koska Länsi-Saksan on voittanut kaksi turnausta ja Saksa yhden, ja kartta puolestaan kerrostaa nämä kaksi arvopistettä, sen sijaan, että ne erotettaisiin toisistaan tai lisättäisiin yhteen. Voit määrittää kyseisille pisteille eri värit, korostaaksesi tätä. Voit myös antaa kartalle sitä paremmin kuvaavan ja kiinnostavamman otsikon. 

1. Kun visualisointi on valittu, valitse **Muotoile**-kuvake ja sitten **Tietojen värit**, avataksesi tietojen värit -valikon. 
   
   ![Tietojen värien muotoileminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web15.png)
   
2. Aseta **Näytä kaikki** **Päällä**-tilaan, ja valitse sitten **Länsi-Saksan**vieressä olevasta avautuvasta valikosta keltainen väri. 
   
   ![Värin muuttaminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web16.png)
   
3. Valitse **Otsikko** avataksesi otsikon asetukset ja syötä **Otsikkoteksti**-kenttään nykyisen otsikon paikalle **Euroopan-mestaruus voittajat**. 
4. Vaihda **Tekstin väri** punaiseksi, **Tekstikooksi** **12** ja **Fonttiperheeksi** **Segoe (lihavoitu)** . 
   
   ![Tietojen värien muotoileminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web17.png)
   

Kartta-visualisointi näyttää nyt tältä:

![Kartan visualisointien muotoileminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web18.png)
   
### <a name="change-the-visualization-type"></a>Visualisointityypin muuttaminen
Voit muuttaa visualisoinnin tyyppiä valitsemalla sen ja valitsemalla sitten eri kuvakkeen **Visualisointi**-ruudun yläreunasta. Kartan visualisoinnista puuttuu esimerkiksi Neuvostoliiton ja Tšekkoslovakian tiedot, koska nämä maat ei ole enää olemassa maailman kartalla. Toinen visualisointityyppi, kuten puukaavio tai ympyräkaavio, voi olla tarkempi, koska siinä näkyvät kaikki arvot. 

Jos haluat muuttaa kartan ympyräkaavioksi, valitse kartta ja valitse sitten **Ympyräkaavio**-kuvake **Visualisointi**-ruudussa. 
   
![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web19.png)

>[!TIP]
>- Voit käyttää **Tietojen värit** -muotoiluasetuksia ja tehdä ”Saksasta” ja ”Länsi-Saksasta” saman väriset. 
>- Ryhmitelläksesi eniten voittaneet maat yhteen ympyräkaaviossa, valitse kolme pistettä ( **...** ) visualisoinnin oikeassa yläkulmassa ja valitse sitten avautuvasta luettelosta **Lajittele vuosimäärän perusteella**. 

Power BI Desktop tarjoaa saumattoman kokemuksen alusta loppuun. Sen avulla voit hakea tietoja laajasta tietolähteiden joukosta ja muotoilla ne analyysitarpeidesi mukaan ja visualisoida tiedot monipuolisilla ja vuorovaikutteisilla tavoilla. Kun raportti on valmis, voit [ladata sen Power BI:hin](desktop-upload-desktop-files.md) ja luoda siihen perustuvia koontinäyttöjä, joita voit jakaa muiden Power BI -käyttäjien kanssa.

## <a name="see-also"></a>Katso myös
* [Lue muita Power BI Desktop -opetusohjelmia](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Katso Power BI Desktop -videoita](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Käy Power BI -keskustelupalstalla](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lue Power BI -blogia](http://go.microsoft.com/fwlink/?LinkID=519327)

