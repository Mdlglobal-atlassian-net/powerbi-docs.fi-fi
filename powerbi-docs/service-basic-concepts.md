---
title: Power BI -palvelun peruskäsitteitä suunnittelijoille
description: Power BI -palvelun työtilat, koontinäytöt, raportit, tietojoukot ja työkirjat.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/18/2018
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 487a67f48913ee774904377956eee85ccbae49fc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296681"
---
# <a name="basic-concepts-for-designers-in-the-power-bi-service"></a>Power BI -palvelun peruskäsitteitä suunnittelijoille

Tässä artikkelissa oletetaan, että olet jo [rekisteröitynyt Power BI -palvelun käyttäjäksi](service-self-service-signup-for-power-bi.md) ja [lisännyt palveluun joitakin tietoja](service-get-data.md). Jos sinulla ei ole vielä tietoja, yritä asentaa [Power BI -mallin sisältöpaketti](sample-datasets.md#the-power-bi-samples-as-content-packs).

![Power BI -palvelun aloitusnäyttö selaimessa](media/service-basic-concepts/power-bi-home-screen.png)

Seuraavassa on elementtejä, jotka näet, kun avaat Power BI -palvelun selaimessa:

1. Siirtymisruutu (vasen siirtymispalkki)
2. Office 365 -sovellusten käynnistystoiminto
3. Power BI:n aloituspainike
4. Kuvakepainikkeet, mukaan lukien asetukset, ohjeet ja palautteet
5. Hakuruutu
6. Ruudut suosituimmasta koontinäytöstä
7. Suosituimmat ja yleisimmät koontinäytöt ja raportit

Tutustumme näihin ominaisuuksiin myöhemmin tarkemmin, mutta käydään ensin läpi muutamia Power BI:n peruskäsitteitä.

Voit myös katsoa tämän videon ennen kuin luet tämän artikkelin loppuun.  Videolla Will kertoo peruskäsitteistä ja esittelee Power BI -palvelua.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>


## <a name="power-bi-concepts"></a>Power BI:n käsitteet
Power BI:n neljä peruselementtiä ovat: **_koontinäytöt_**, **_raportit_**, **_työkirjat_** ja **_tietojoukot_**. Ne on kaikki järjestetty **_työtiloiksi_**. Työtilojen käsite on tärkeä ymmärtää ennen neljään peruselementtiin tutustumista, joten aloitetaan siitä.

## <a name="workspaces"></a>Työtilat
Työtilat ovat Power BI:ssä olevia säilöjä koontinäytöille, raporteille, työkirjoille ja tietojoukoille. Työtiloja on kahdenlaisia: *Oma työtila* ja *sovellustyötilat*. Entä mitä tarkoitetaan *sovelluksella*? Power BI -*sovellus* on kokoelma koontinäyttöjä ja raportteja, joiden avulla voit kuvata organisaatiosi keskeisiä mittalukuja. Sovellukset ovat vuorovaikutteisia, mutta niitä ei voi muokata.

- *Oma työtila* on jokaisen Power BI -asiakkaan henkilökohtainen työtila oman sisällön käsittelyyn. Vain sinulla on käyttöoikeus omaan työtilaasi. Oman työtilan kautta voi jakaa raporttinäkymiä ja raportteja. Jos haluat käsitellä koontinäyttöjä ja raportteja yhteistyössä tai luoda sovelluksen, sinun kannattaa käyttää sovellustyötilaa.      
-  *Sovellustyötiloja* käytetään yhteistyöhön ja sisällön jakamiseen kollegoiden kanssa. Niissä voi myös luoda, julkaista ja hallita sovelluksia organisaatiollesi. Niitä voi ajatella tietynlaisina valmisteluympäristöinä ja säilöinä sisällölle, josta muodostuu Power BI -sovellus. Voit lisätä kollegoita sovellustyötilan käyttäjiksi ja käsitellä koontinäyttöjä, raportteja, työkirjoja ja tietojoukkoja yhteistyössä. Kaikki sovellustyötilan jäsenet tarvitsevat Power BI Pro -käyttöoikeudet, mutta sovelluksen kuluttajilla (sovelluksen käyttöoikeuden saaneilla kollegoilla) ei välttämättä tarvitse olla Pro-käyttöoikeuksia.  

Lisätietoja on sisällysluettelon **Työn jakaminen** -osiossa, jonka ensimmäisenä aiheena on [Miten voin jakaa koontinäyttöjä ja raportteja sekä työstää niitä yhdessä muiden kanssa?](service-how-to-collaborate-distribute-dashboards-reports.md)


Siirrytään nyt Power BI:n peruselementteihin. Raporttinäkymiä tai raportteja ei voi olla ilman tietoja – tai tyhjinä niistä ei ainakaan ole hyötyä –, joten aloitetaan **tietojoukoista**.

## <a name="datasets"></a>tietojoukot
*Tietojoukko* on kokoelma tietoja, jotka voit *tuoda* tai joihin voit *muodostaa yhteyden*. Power BI:n avulla voit koota yhteen kaikenlaisia tietojoukkoja muodostamalla niihin yhteyden ja tuomalla niitä.  

Tietojoukot liittyvät *työtiloihin*, ja yksi tietojoukko voi olla osa useita työtiloja. Kun avaat työtilan, siihen liittyvät tietojoukot luetellaan **Tietojoukot**-välilehdellä. Jokainen luettelon tietojoukko edustaa yhtä tietolähdettä, kuten Excel-laskentataulukkoa OneDrivessa, paikallista taulukkomuotoista SSAS-tietojoukkoa tai Salesforce-tietojoukkoa. Tuettuja tietolähteitä on monenlaisia, ja uusia lisätään koko ajan. [Katso luettelo Power BI:n kanssa käytettävistä tietojoukkotyypeistä](service-get-data.md).

Alla olevassa esimerkissä olen valinnut Myynti ja markkinointi -sovellustyötilan ja napsauttanut **Tietojoukot**-välilehteä.

![Tietojoukot on valittu](media/service-basic-concepts/power-bi-datasets.png)

**YHTÄ** tietojoukkoa...

* voi käyttää yhä uudelleen yhdessä tai useissa työtiloissa.
* voi käyttää useissa erilaisissa raporteissa.
* Tämän yhden tietojoukon visualisointeja voi näyttää useissa eri koontinäytöissä.

  ![Tietojoukkokaavio](media/service-basic-concepts/drawing2.png)

Voit [yhdistää tietojoukkoon tai tuoda tietojoukon](service-get-data.md) valitsemalla **Nouda tiedot** (vasemman siirtymisruudun alareunassa) tai valitsemalla **+ Luo > Tietojoukko** (oikeassa yläkulmassa). Noudata ohjeita yhteyden muodostamiseen tiettyyn lähteeseen tai lähteen tuomiseen. Lisää tietojoukko aktiiviseen työtilaan. Uudet tietojoukot on merkitty keltaisella tähdellä. Power BI:ssä tekemäsi työ ei muuta pohjana olevaa tietojoukkoa.

Jos olet [osa **_sovellustyötilaa_**](service-collaborate-power-bi-workspace.md), yhden työtilan jäsenen lisäämät tietojoukot ovat työtilan muiden jäsenten käytettävissä.

Tietojoukkoja voi päivittää, nimetä uudelleen, tarkastella ja poistaa. Tietojoukon avulla voit luoda raportin alusta alkaen tai [Nopeat merkitykselliset tiedot](service-insights.md) -toiminnolla.  Valitsemalla **Näytä aiheeseen liittyvät** voit nähdä, mitkä raportit ja koontinäytöt käyttävät jo tietojoukkoa. Voit tutustua tietojoukkoon valitsemalla sen. Silloin käytännössä avaat tietojoukon raporttieditorissa, jossa voit aloittaa tietoihin pureutumisen ja visualisointien luomisen. Siirrytään siis seuraavaan aiheeseen eli raportteihin.

### <a name="dig-deeper"></a>Pureudu syvemmälle
* [Mikä on Power BI Premium?](service-premium.md)
* [Tietojen noutaminen Power BI:hin](service-get-data.md)
* [Mallitietojoukkoja Power BI:lle](sample-datasets.md)

## <a name="reports"></a>Raportit
Power BI -raportti sisältää yhden tai useamman sivun verran visualisointeja, kuten viivakaavioita, karttoja ja puukarttoja. Visualisointeja voidaan kutsua myös **_graafeiksi_**. Kaikki raportin visualisoinnit ovat peräisin yhdestä tietojoukosta. Raportteja voi luoda alusta alkaen Power BI:ssä, tai niitä voi tuoda raporttinäkyminä, joita kollegat jakavat kanssasi. Niitä voi myös luoda muodostamalla yhteyden tietojoukkoihin Excelissä, Power BI Desktopissa, tietokannoissa, SaaS-sovelluksissa ja [sovelluksissa](service-get-data.md).  Kun esimerkiksi muodostat yhteyden Power View -taulukoita sisältävään Excel-työkirjaan, Power BI luo raportin näiden taulukoiden perusteella. Ja kun muodostat yhteyden SaaS-sovellukseen, Power BI tuo valmiiksi luodun raportin.

Voit tarkastella ja käsitellä raportteja kahdessa tilassa: [lukunäkymässä ja muokkausnäkymässä](service-reading-view-and-editing-view.md).  Vain raportin luonut henkilö, sen muut omistajat ja siihen käyttöoikeuden saaneet saavat käyttöönsä kaikki tutustumis-, suunnittelu-, luomis- ja jakamistoiminnot raportin **_muokkausnäkymässä_**. Henkilöt, joille raportti jaetaan, voivat tarkastella ja käsitellä sitä **_lukunäkymässä_**.   

Kun avaat työtilan, siihen liittyvät raportit luetellaan **Raportit**-välilehdellä. Jokainen luettelon raportti edustaa yhtä tai useampaa visualisointien sivua, joka perustuu vain yhteen pohjana olevista tietojoukoista. Avaa raportti valitsemalla se.

Kun avaat sovelluksen, näet koontinäytön.  Voit käyttää sen pohjana olevaa raporttia valitsemalla raporttinäkymän ruudun (näistä lisää myöhemmin), joka oli kiinnitetty raportista. Pidä mielessä, että kaikkia ruutuja ei ole kiinnitetty raporteista, joten saatat joutua napsauttamaan useita ruutuja, ennen kuin löydät raportin.

Raportti avautuu oletusarvoisesti lukunäkymässä.  Valitse **Muokkaa raporttia**, niin se avautuu muokkausnäkymässä, jos sinulla on tarvittavat oikeudet.

Alla olevassa esimerkissä olen valinnut Myynti ja markkinointi -sovellustyötilan ja napsauttanut **Raportit**-välilehteä.

![Raportit valittu](media/service-basic-concepts/power-bi-reports.png)

**YKSI** raportti...

* sisältyy yhteen työtilaan.
* voi liittyä useisiin koontinäyttöihin kyseisessä työtilassa (tästä yhdestä raportista kiinnitettyjä ruutuja voi olla useissa koontinäytöissä).
* voidaan luoda käyttämällä yhden tietojoukon tietoja. (Pienenä poikkeuksena tähän on se, että Power BI Desktopissa on mahdollista yhdistää useampi kuin yksi tietojoukko yhteen raporttiin ja että tämä raportti voidaan tuoda Power BI:hin.)

  ![Raporttien kaavio](media/service-basic-concepts/drawing3new.png)

### <a name="dig-deeper"></a>Pureudu syvemmälle
* [Raportit Power BI -palvelussa ja Power BI Desktopissa](service-reports.md)
* [Raportit Power BI -mobiilisovelluksissa](mobile-reports-in-the-mobile-apps.md)

## <a name="dashboards"></a>koontinäytöt
*Koontinäytön* voit luoda itse **Power BI -palvelussa**, tai vaihtoehtoisesti kollega luo sen **Power BI -palvelussa** ja jakaa kanssasi. Se on yksittäinen kangas, joka sisältää ruutuja ja pienoissovelluksia – tai voi olla myös tyhjä. Jokainen raportista tai [Q&A](power-bi-q-and-a.md)-tuloksista kiinnitetty ruutu näyttää yksittäisen [visualisoinnin](power-bi-report-visualizations.md), jotka on luotu tietojoukosta ja kiinnitetty koontinäyttöön. Myös raportin kokonaisia sivuja voi kiinnittää koontinäyttöön yksittäisenä ruutuna. Ruutuja voi lisätä koontinäyttöön monella tavalla, joista kaikkia ei käsitellä tässä yleiskatsauksessa. Lisätietoja on artikkelissa [Koontinäyttöruudut Power BI:ssä](service-dashboard-tiles.md).

Miksi koontinäyttöjä luodaan?  Tässä on vain muutamia syitä:

* Voit nähdä kaikki tarvittavat tiedot päätöksenteon tueksi yhdellä silmäyksellä.
* Voit valvoa liiketoimintasi tärkeimpiä tietoja.
* Voit varmistaa, että kaikki kollegat näkevät ja käyttävät samalla sivulla samoja tietoja.
* Voit valvoa yrityksen, liiketoimintayksikön, tuotteen tai markkinointikampanjan menestymistä.
* Voit luoda mukautetun näkymän suuremmasta koontinäytöstä ja valita siihen itsellesi tärkeimmät tiedot.

Kun avaat työtilan, siihen liittyvät koontinäytöt luetellaan **Koontinäytöt**-välilehdellä. Avaa raporttinäkymä valitsemalla se. Kun avaat sovelluksen, näet koontinäytön.  Jokainen koontinäyttö edustaa mukautettua näkymää pohjana olevan tietojoukon tai tietojoukkojen tietystä alijoukosta.  Jos omistat koontinäytön, sinulla on myös muokkausoikeus pohjana oleviin tietojoukkoihin ja raportteihin.  Jos koontinäyttö jaettiin kanssasi, pystyt käyttämään sitä ja pohjana olevia raportteja, mutta et voi tallentaa tekemiäsi muutoksia.

[Koontinäytön voi jakaa](service-share-dashboards.md) monilla eri tavoilla. Koontinäytön jakamiseen ja mahdollisesti myös jaetun koontinäytön tarkasteluun vaaditaan Power BI Pro.

**YKSI** koontinäyttö...

* liittyy yksittäiseen työtilaan
* voi näyttää visualisointeja monista eri tietojoukoista
* voi näyttää visualisointeja monista eri raporteista
* voi näyttää visualisointeja, jotka on kiinnitetty muista työkaluista (esimerkiksi Excelistä)

  ![Raporttinäkymä valittuna](media/service-basic-concepts/drawing1.png)

### <a name="dig-deeper"></a>Pureudu syvemmälle
* [Luo uusi tyhjä koontinäyttö ja hae siihen tietoja](service-dashboard-create.md).
* [Koontinäytön monistaminen](service-dashboard-copy.md)
* [Koontinäytön puhelinnäkymän luominen](service-create-dashboard-mobile-phone-view.md)


## <a name="workbooks"></a>Työkirjat
Työkirjat ovat omanlaisensa tietojoukkotyyppi. Jos luit yllä olevan **Tietojoukot**-osion, tiedät jo työkirjoistakin melkein kaiken tarvittavan. Saatat kuitenkin ihmetellä, miksi Power BI joskus luokittelee Excel-työkirjan **tietojoukoksi** ja joskus taas **työkirjaksi**.

Kun käytät **Nouda tiedot** -toimintoa Excel-tiedostoihin, voit joko *tuoda tiedot* tai *muodostaa yhteyden* tiedostoon. Kun valitset Muodosta yhteys, työkirjasi näkyy Power BI:ssä aivan samalla tavalla kuin se näkyisi Excel Onlinessa. Mutta toisin kuin Excel Onlinessa, käytettävissäsi on käteviä ominaisuuksia, joilla voit kiinnittää laskentataulukoiden elementtejä suoraan koontinäyttöihin.

Työkirjaa ei voi muokata Power BI:ssä. Jos muutoksia on tehtävä, voit valita Muokkaa-vaihtoehdon ja sitten työkirjan muokkaamisen joko Excel Onlinessa tai tietokoneesi Excelissä. Tekemäsi muutokset tallennetaan työkirjaan OneDrivessa.

### <a name="dig-deeper"></a>Pureudu syvemmälle
* [Tietojen hakeminen Excel-työkirjatiedostoista](service-excel-workbook-files.md)
* [Julkaiseminen Excelistä Power BI:hin](service-publish-from-excel.md)


## <a name="a-dashboard-in-my-workspace"></a>Koontinäyttö Omassa työtilassa
Olemme nyt käsitelleet työtilat ja Power BI:n elementit. Tuodaanpa ne nyt yhteen ja tarkastellaan osia, jotka muodostavat koontinäyttökokemuksen Power BI -palvelussa.

![Power BI -palvelu selaimessa](media/service-basic-concepts/completenewest.png)

### <a name="1-navigation-pane-left-nav"></a>1. **Siirtymisruutu** (vasen siirtymispalkki)
Siirtymisruudun avulla voit etsiä työtiloja ja Power BI:n elementtejä sekä siirtyä niiden välillä. Elementtejä ovat koontinäytöt, raportit, työkirjat ja tietojoukot.  

  ![Siirtymisruutu](media/service-basic-concepts/power-bi-navigation.png)

* Valitse **Nouda tiedot**, kun haluat [lisätä tietojoukkoja, raportteja ja koontinäyttöjä Power BI:hin](service-get-data.md).
* Laajenna ja kutista siirtymisruutua tällä kuvakkeella ![siirtymisruudun kuvake](media/service-basic-concepts/expand-icon.png).
* Avaa tai hallitse suosikkisisältöäsi valitsemalla **Suosikit**.
* Tarkastele ja avaa viimeksi käytettyä sisältöä valitsemalla **Viimeaikaiset**
* Tarkastele, avaa tai poista sovelluksia valitsemalla **Sovellukset**.
* Jakoiko kollega sisältöä kanssasi? Valitse **Jaettu kanssani**, niin voit hakea ja lajitella jaettua sisältöä.
* Näytä ja avaa työtiloja valitsemalla **Työtilat**.

Napsauta näitä elementtejä kerran:

* kuvaketta tai otsikkoa, niin avaat kohteen sisältönäkymässä
* oikeaa nuolta (>), niin avaat pikaikkunan, jossa valittavina ovat Suosikit, Viimeaikaiset ja Työtilat.
* alanuolta (), niin näet vieritettävän **Oma työtila** -luettelon, joka sisältää koontinäytöt, raportit, työkirjat ja tietojoukot.

### <a name="2-canvas"></a>2. **Kangas**
Koska olemme olet avanneet koontinäytön, kangasalue näyttää visualisointien ruudut. Jos olisimme avanneet esimerkiksi raporttieditorin, alustalla näkyisi raporttisivu.

Koontinäytöt koostuvat [ruuduista](service-dashboard-tiles.md).  Ruudut luodaan raportin muokkausnäkymässä, Q&A-kysymysruudussa tai muissa koontinäytöissä. Niitä voi liittää Excelistä, SSRS:stä ja muista lähteistä. [Pienoissovelluksiksi](service-dashboard-add-widget.md) kutsutut erikoisruudut lisätään suoraan koontinäyttöön. Koontinäytössä näkyvät ruudut ovat raportin tekijän tai omistajan siihen varta vasten lisäämiä.  Ruudun lisäämistä koontinäyttöön kutsutaan *kiinnittämiseksi*.

![Power BI -koontinäytön kangas](media/service-basic-concepts/canvas.png)

Lisätietoja on ohjeaiheessa [Koontinäytöt](#dashboards) (yllä).

### <a name="3-qa-question-box"></a>3. **Q&A-kysymysruutu**
Yksi tapa tarkastella tietoja on kysyä kysymyksiä ja antaa Power BI:n Q&A-toiminnon antaa vastaukset visualisoinnin muodossa. Q&A-kysymyksillä voidaan lisätä sisältöä koontinäyttöön tai raporttiin.

Q&A-toiminto etsii vastausta koontinäyttöön yhdistetyistä tietojoukoista.  Yhdistetty tietojoukko on tietojoukko, jolla on vähintään yksi kiinnitetty ruutu koontinäytössä.

![Q&A-kysymysruutu](media/service-basic-concepts/power-bi-qna.png)

Kun alat kirjoittaa kysymystä, siirryt Q&A-sivulle. Kirjoittaessasi Q&A-toiminto auttaa oikean kysymyksen kysymisessä ja parhaan vastauksen löytämisessä. Se esimerkiksi ehdottaa kysymyksen uudelleenmuotoilua sekä tarjoaa automaattista täyttöä ja ehdotuksia. Kun olet saanut haluamasi visualisoinnin, kiinnitä se koontinäyttöön. Lisätietoja on artikkelissa [Power BI:n Q&A-toiminto](power-bi-q-and-a.md).

### <a name="4-icon-buttons"></a>4. **Kuvakepainikkeet**
Oikeassa yläkulmassa olevilla kuvakkeiden kautta voit säätää asetuksia, tarkastella ilmoituksia, ladata sisältöä, hankkia ohjeita ja antaa palautetta Power BI -tiimille. Kaksoisnuolella voit avata koontinäytön **koko näytön** tilassa.  

![kuvakepainikkeet](media/service-basic-concepts/power-bi-icons.png)

### <a name="5-dashboard-title-navigation-path-aka-breadcrumbs"></a>5. **Koontinäytön otsikko** (navigointipolku)
Aina ei ole helppo selvittää, mikä työtila ja koontinäyttö ovat aktiivisina. Siinä auttaa Power BI:n luoma navigointipolku.  Tässä esimerkissä näemme työtilan (Oma työtila) ja raporttinäkymän otsikon (Jälleenmyyntianalyysimalli).  Jos avaamme raportin, raportin nimi liitetään navigointipolun loppuun.  Jokainen polun osa on aktiivinen hyperlinkki.  

Huomaa C-kuvake koontinäytön otsikon perässä. Tällä koontinäytöllä [tietojen luokitustunniste](service-data-classification.md) C, joka tarkoittaa luottamuksellista. Tunniste ilmoittaa tietojen luottamuksellisuus- ja suojaustason. Jos järjestelmänvalvoja on ottanut tietojen luokituksen käyttöön, jokaisella raporttinäkymällä on oletusarvoinen tunnistejoukko. Koontinäytön omistajien tulisi muuttaa tunnistetta vastaamaan koontinäytön todellista suojaustasoa.

![Tietojen luokittelukuvake](media/service-basic-concepts/power-bi-title.png)

### <a name="6-office-365-app-launcher"></a>6. **Office 365 -sovellusten käynnistystoiminto**
Käynnistystoiminnon ansiosta kaikki Office 365 -sovelluksesi ovat helposti käytettävissä yhdellä napsautuksella. Täältä voit nopeasti käynnistää sähköpostin, tiedostot, kalenterin ja paljon muuta.

![Office-sovellusten käynnistys](media/service-basic-concepts/power-bi-waffle.png)

### <a name="7-power-bi-home"></a>7. **Power BI:n aloitussivu**
Valitsemalla **Power BI**:n palaat takaisin Power BI:n aloitussivulle.

   ![Power BI palvelussa](media/service-basic-concepts/version-new.png)

### <a name="8-labeled-icon-buttons"></a>8. **Nimetyt kuvakepainikkeet**
Tämä näytön alue sisältää lisävaihtoehtoja vuorovaikutukseen sisällön eli tässä tapauksessa koontinäytön kanssa.  Nimettyjen kuvakkeiden lisäksi näet pistekuvakkeita napsauttamalla vaihtoehtoja koontinäytön monistamiseen, tulostamiseen, päivittämiseen ja muihin toimintoihin.

   ![Nimetyt kuvakepainikkeet](media/service-basic-concepts/power-bi-labeled-icons.png)

## <a name="next-steps"></a>Seuraavat vaiheet
- [Mikä on Power BI?](power-bi-overview.md)  
- [Siirtyminen: Power BI -palvelussa liikkuminen](service-the-new-power-bi-experience.md)
- [Power BI -videot](videos.md)  
- [Raporttieditorin esittely](service-the-report-editor-take-a-tour.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
