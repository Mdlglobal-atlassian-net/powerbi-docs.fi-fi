---
title: 'Opetusohjelma: Verkkosivun tietojen tuonti ja analysointi'
description: 'Opetusohjelma: Verkkosivun tietojen tuonti ja analysointi Power BI Desktopilla'
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 01/13/2020
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 5497c56f358470d0d24f69f0d67865dbbd7839a3
ms.sourcegitcommit: 75300b3f53f438ed7d3bd4edc93b9eb5925bf3af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/05/2020
ms.locfileid: "77026734"
---
# <a name="tutorial-analyze-webpage-data-by-using-power-bi-desktop"></a>Opetusohjelma: Verkkosivun tietojen analysointi Power BI Desktopilla

Pitkäaikaisena jalkapallofanina haluat raportin UEFA Euroopan mestaruuskisojen voittajista. Power BI Desktopilla voit tuoda nämä tiedot verkkosivulta raporttiin ja luoda visualisointeja näyttämään tietoja. Tässä opetusohjelmassa opit miten Power BI Desktopilla:

- muodostetaan yhteys verkkotietolähteeseen ja siirrytään käytettävissä olevien taulukoiden välillä,
- muotoillaan ja muunnetaan tietoa Power Query -editorissa,
- annetaan kyselylle nimi ja tuodaan se Power BI Desktop -raporttiin,
- luodaan ja mukautetaan kartan ja ympyräkaavio visualisointeja.

## <a name="connect-to-a-web-data-source"></a>Yhteyden muodostaminen verkkotietolähteeseen

Voit saada UEFA voittajatiedot tulostaulukosta UEFA mestaruuskisojen Wikipedia-sivulta osoitteesta https://en.wikipedia.org/wiki/UEFA_European_Football_Championship. 

![Wikipedian tulostaulukko](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

Verkkoyhteydet muodostetaan vain perustodentamista käyttämällä. Todentamista vaativat verkkosivustot eivät välttämättä toimi kunnolla verkkoyhdistimen kanssa.

Tietojen tuominen:

1. Power BI Desktopin **Koti** -valintanauhan välilehdeltä, avaa nuoli **Nouda tiedot**-kohdan vierestä ja valitse sitten **Verkko**.

   ![Tietojen noutaminen valintanauhasta](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web3.png) 

   >[!NOTE]
   >Voit myös valita **Nouda tiedot** -kohteen itse tai valita **Nouda tiedot** Power BI Desktopin aloitusvalintaikkunasta. Valitse sitten **Verkko**  **Kaikki**- tai **Muut**-osiosta **Nouda tiedot** -valintaikkunasta, ja valitse sitten **Yhdistä**.

1. Liitä URL-osoite **Verkosta**`https://en.wikipedia.org/wiki/UEFA_European_Football_Championship`-valintaikkunan **URL** -tekstiruutuun ja valitse sitten **OK**.

    ![Tietojen noutaminen valintaikkunasta](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web2.png)

   Kun olet yhdistänyt Wikipedia-verkkosivuun, **Siirtymistoiminto**-valintaikkunassa näkyy luettelo sivun käytettävissä olevista taulukoista. Voit valita minkä tahansa taulukon nimen tarkastellaksesi sen sisältämiä tietoja. **Tulokset [muokkaa]** -taulukko sisältää haluamasi tiedot, vaikka ne eivät olekaan tarkalleen haluamassasi muodossa. Voit muotoilla uudelleen ja puhdistaa tiedot ennen niiden lataamista raporttiin.

   ![Siirtymistoiminto-valintaikkuna](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)

   >[!NOTE]
   >**Esikatselu**-ruutu näyttää viimeisimmän valitun taulukon, mutta kaikki valitut taulukot ladataan Power Query -editoriin, kun valitset **Muunna tietoja** tai **Lataa**.

1. Valitse **Tulokset [muokkaa]** -taulukko **Siirtymistoiminto**-luettelosta, ja valitse sitten **Muunna tiedot**.

   Taulukon esikatselu avautuu **Power Query -editoriin**, jossa voit soveltaa muunnoksia tietojen puhdistamiseksi.

   ![Power Query -editori](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)

## <a name="shape-data-in-power-query-editor"></a>Tietojen muotoileminen Power Query -editorissa

Haluat tehdä tietojen tarkastelemisesta helpompaa näyttämällä vain vuodet sekä voittajamaat. Voit käyttää Power Query -editoria tietojen muotoilemiseen ja puhdistamiseen.

Poista taulukosta ensin kaikki sarakkeet kahta saraketta lukuun ottamatta. Nimeä nämä sarakkeet prosessissa myöhemmin uudelleen (*Vuosi* ja *Maa*).

1. Valitse sarakkeet **Power Query -editorin** ruudukossa. Valitse useita kohteita valitsemalla Ctrl.

1. Napsauta hiiren kakkospainiketta ja valitse **Poista muut sarakkeet** tai valitse **Poista sarakkeet** > **Poista muut sarakkeet** **Hallitse sarakkeita** -ryhmästä **Aloitus**-valintanauhan välilehdeltä kaikkien muiden sarakkeiden poistamiseksi taulukosta.

   ![Avattava Poista muut sarakkeet -valikko](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web6.png)

   tai

   ![Poista muut sarakkeet -valintanauha](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

Poista seuraavaksi ylimääräinen *Tiedot*-sana ensimmäisen sarakkeen soluista.

1. Valitse ensimmäinen sarake.

1. Napsauta hiiren kakkospainiketta ja valitse **Korvaa arvot** tai valitse **Korvaa arvot** **Muunna**-ryhmän valintanauhan **Aloitus**-välilehdeltä. Tämä vaihtoehto löytyy myös **Mikä tahansa sarake** -ryhmästä **Muunna**-välilehdeltä.

   ![Avattava Korvaa arvot -valikko](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web7.png) 

   tai

   ![Korvaa arvot -valintanauha](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8a.png)

1. Kirjoita **Korvaa arvot** -valintaikkunassa **Tiedot**-teksti **Etsittävä arvo** -tekstiruutuun ja jätä **Korvaa arvolla** -tekstiruutu tyhjäksi. Valitse sitten **OK** poistaaksesi *Tiedot*-sanan tästä sarakkeesta.

   ![Sanan poistaminen sarakkeesta](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

Jotkin solut sisältävät vain sanan ”Vuosi” vuosiarvojen sijaan. Voit suodattaa sarakkeen näyttämään vain rivit, jotka eivät sisällä sanaa ”Vuosi”.

1. Valitse sarakkeen suodattimen alanuoli.

1. Vieritä avattavaa valikkoa alaspäin ja tyhjennä **Vuosi**-vaihtoehdon vieressä oleva valintaruutu ja valitse sitten **OK**.

   ![Tietojen suodatus](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

Koska etsit nyt vain finaalien voittajatietoja, voit nimetä toisen sarakkeen uudelleen **Maa**-sarakkeeksi. Sarakkeen uudelleennimeäminen:

1. Kaksoisnapsauta tai napauta ja pidä pohjassa toisen sarakkeen otsikkoa, tai
   - napsauta hiiren kakkospainikkeella sarakkeen otsikkoa ja valitse **Nimeä uudelleen**, tai
   - valitse *sarake ja valitse **Nimeä uudelleen** **Mikä tahansa sarake** -ryhmästä valintanauhan **Muunna**-välilehdeltä.

   ![Avattava Nimeä uudelleen -valikko](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7a.png) 
  
   tai

   ![Nimeä uudelleen -valintanauha](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8.png)

1. Syötä sana **Maa** otsikkoon ja paina **Enter** nimetäksesi sarakkeen uudelleen.

Voit myös suodattaa **Maa**-sarakkeesta pois rivit, jotka eivät sisällä käypiä arvoja, kuten ”2020”. Voit käyttää suodatinvalikkoa samalla tavalla kuin suodattaessasi **Vuosi**-sarakkeen arvoja, tai voit:

1. napsauttaa hiiren kakkospainikketta **Maa**-solun **2020**-rivillä, jonka on arvo *tyhjä*.

1. Valitse **Tekstisuodattimet** > **Ei ole yhtä suuri kuin**-pikavalikosta rivit, jotka sisältävät solun arvon.

   ![Tekstisuodatin](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web11.png)

## <a name="import-the-query-into-report-view"></a>Kyselyn tuominen raporttinäkymään

Nyt kun olet muotoillut tietoja haluamallasi tavalla, voit nimetä kyselysi ”Euroopan-mestaruus voittajat”-nimiseksi ja tuoda sen raporttiisi.

1. **Kyselyasetukset**-ruudun **Nimi**-tekstikenttään syötä **Euroopan-mestaruuskisojen voittajat**.

   ![Kyselyn nimeäminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

1. Valitse **Sulje ja ota käyttöön** > **Sulje ja ota käyttöön** **Koti** -valintanauhan välilehdeltä.

   ![Sulje ja ota käyttöön](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)

Kysely ladataan Power BI Desktopin *Raportti*-näkymään, jossa se näkyy **Kentät** -ruudussa.

   ![Kentät-ruutu](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)

>[!TIP]
>Pääset aina takaisin Power Query -editoriin, jossa voit muokata ja hienosäätää kyselyäsi:
>- valitsemalla **Lisäasetuksista** kolme pistettä ( **...** ) **Euroopan-mestaruus voittajat** -kohdan vierestä**Kentät**-ruudusta ja valitsemalla **Muokkaa kyselyä**, tai
>- valitsemalla **Muokkaa kyselyitä** > **Muokkaa kyselyitä** **Ulkoiset tiedot** - ryhmästä raporttinäkymän **Koti** -valintanauhasta. 

## <a name="create-a-visualization"></a>Visualisoinnin luominen

Luodaksesi tietoihin perustuvan visualisoinnin:

1. Valitse **Maa** -kenttä **Kentät**-ruudusta tai vedä se raporttipohjaan. Power BI Desktop tunnistaa tiedot maan niminä ja luo automaattisesti **Kartta** -visualisoinnin.

   ![Kartta-visualisointi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web14.png)

1. Suurenna karttaa vetämällä kulmien kahvoista, jotta kaikki maiden nimet ovat näkyvissä.  

   ![Suurenna kartta](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)

1. Kartassa näkyvät kaikki identtiset arvopisteet jokaisesta maasta, jotka on voittanut Euro Cup -turnauksen. Saadaksesi kunkin arvopisteen koon kuvastamaan kuinka usein maan on voittanut, vedä **Vuosi**-kenttä **Vedä tietokentät tähän** -kohtaan **Koko**-valikon alla, **Visualisoinnit**-ruudun alaosassa. Kenttä muuttuu automaattisesti **Vuosien määrä** -mittariksi ja kartan visualisointi näyttää nyt niiden maiden arvopisteet suurempina, jotka ovat voittaneet useimpia turnauksia.

   ![Vuosien määrä -mittarin vetäminen Koko-kohtaan](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)

## <a name="customize-the-visualization"></a>Visualisointien mukauttaminen

Visualisointien luominen tietojen perusteella on siis hyvin helppoa. Helppoa on myös niiden mukauttaminen halutusti niin, että ne esittävät tiedot paremmin.

### <a name="format-the-map"></a>Kartan muotoileminen

Voit muuttaa visualisoinnin ulkoasua valitsemalla sen ja valitsemalla sitten **Muotoile**-kuvakkeen (maalirulla) **Visualisoinnit**-ruudussa. Visualisointisi ”Saksa”-arvopisteet saattavat olla esimerkiksi harhaanjohtavia, koska Länsi-Saksa on voittanut kaksi turnausta ja Saksa yhden, ja kartta kerrostaa nämä kaksi arvopistettä sen sijaan, että ne erotettaisiin toisistaan tai lisättäisiin yhteen. Voit määrittää näille kahdelle pisteelle eri värit tämän seikan korostamiseksi. Voit myös antaa kartalle sitä paremmin kuvaavan ja kiinnostavamman otsikon.

1. Kun visualisointi on valittu, valitse **Muotoile**-kuvake ja sitten **Tietojen värit**, avataksesi tietojen värit -valikon.

   ![Tietojen värien muotoileminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web15.png)

1. Aseta **Näytä kaikki** **Päällä**-tilaan, ja valitse sitten **Länsi-Saksa**-kohdan vieressä olevasta avautuvasta valikosta keltainen väri.

   ![Värin muuttaminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web16.png)

1. Valitse **Otsikko** avataksesi otsikon asetukset ja syötä **Otsikkoteksti**-kenttään nykyisen otsikon paikalle **Euroopan-mestaruus voittajat**.

1. Vaihda **Tekstin väri** punaiseksi, **Tekstikooksi** **12** ja **Fonttiperheeksi** **Segoe (lihavoitu)** .

   ![Tietojen värien muotoileminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web17.png)

Kartta-visualisointi näyttää nyt tältä:

![Kartan visualisointien muotoileminen](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web18.png)

### <a name="change-the-visualization-type"></a>Visualisointityypin muuttaminen

Voit muuttaa visualisoinnin tyyppiä valitsemalla sen ja valitsemalla sitten eri kuvakkeen **Visualisoinnit**-ruudun yläreunasta. Kartan visualisoinnista puuttuu esimerkiksi Neuvostoliiton ja Tšekkoslovakian tiedot, koska nämä maat ei ole enää olemassa maailman kartalla. Toinen visualisointityyppi, kuten puukaavio tai ympyräkaavio, voi olla tarkempi, koska siinä näkyvät kaikki arvot.

Jos haluat muuttaa kartan ympyräkaavioksi, valitse kartta ja valitse sitten **Ympyräkaavio**-kuvake **Visualisoinnit**-ruudussa.

![Visualisoinnin muuttaminen ympyräkaavioksi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web19.png)

>[!TIP]
>- Voit käyttää **Tietojen värit** -muotoiluasetuksia ja tehdä ”Saksasta” ja ”Länsi-Saksasta” saman väriset. 
>- Ryhmitelläksesi eniten voittaneet maat yhteen ympyräkaaviossa, valitse kolme pistettä ( **...** ) visualisoinnin oikeassa yläkulmassa ja valitse sitten **Lajittele vuosien määrän mukaan**.

Power BI Desktop tarjoaa saumattoman kokemuksen alusta loppuun. Sen avulla voit hakea tietoja laajasta tietolähteiden joukosta ja muotoilla ne analyysitarpeidesi mukaan ja visualisoida tiedot monipuolisilla ja vuorovaikutteisilla tavoilla. Kun raportti on valmis, voit [ladata sen Power BI:hin](desktop-upload-desktop-files.md) ja luoda siihen perustuvia koontinäyttöjä, joita voit jakaa muiden Power BI -käyttäjien kanssa.

## <a name="see-also"></a>Muuta aiheeseen liittyvää

* [Lue muita Power BI Desktop -opetusohjelmia](/power-bi/guided-learning/)
* [Katso Power BI Desktop -videoita](desktop-videos.md)
* [Käy Power BI -keskustelupalstalla](https://go.microsoft.com/fwlink/?LinkID=519326)
* [Lue Power BI -blogia](https://go.microsoft.com/fwlink/?LinkID=519327)

