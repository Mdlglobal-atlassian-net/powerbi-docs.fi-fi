---
title: Power BI Premium -kapasiteetin muistin käyttö ja optimointi
description: Power BI Premium -kapasiteetin muistin hallinnan ja optimoinnin ymmärtäminen.
ms.date: 04/30/2018
ms.topic: conceptual
ms.service: powerbi
ms.component: powerbi-admin
ms.author: susuresh
ms.reviewer: susuresh
author: suds001
manager: kfile
ms.openlocfilehash: 03c5e56c5f516bb1f09f51463d4c533185fbb63c
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34298454"
---
# <a name="power-bi-premium-capacity-resource-management-and-optimization"></a>Power BI Premium -kapasiteetin resurssien hallinta ja optimointi

Tässä artikkelissa kuvataan miten Power BI Premium -palvelu hallinnoi resursseja. Artikkeli antaa myös vinkkejä ratkaisusi suunnitteluun ja optimointiin.

## <a name="premium-capacity-memory-management"></a>Premium-kapasiteetin muistinhallinta

 Premium-kapasiteetin muistia kuluttavat:

* Ladattujen tietojoukkojen varaama muisti
* Tietojoukkojen uudelleen lataamiseen käytetty muisti (sekä ajastetut että pyydetyt)
* Raporttikyselyiden käyttämä muisti

Kun kapasiteetissäsi olevasta, julkaistusta tietojoukosta tulee pyyntö, kyseinen tietojoukko ladataan muistiin pysyvästä tallennusvälineestä (tätä kutsutaan myös kuvan lataamiseksi). Tietojoukon pitäminen ladattuna muistiin auttaa nopeuttamaan kyseiseen tietojoukkoon liittyviin kyselyihin vastaamista tulevaisuudessa. Tietojoukon muistiin lataamisen viemän muistin lisäksi raporttikyselyt ja tietojoukkojen uudelleen lataamiset vievät myös lisämuistia.

### <a name="dataset-memory-estimation"></a>Tietojoukon muistitilan arvio

Kun tietojoukkoa yritetään ladata muistiin, Power BI arvioi muistin määrän, jonka kyseinen tietojoukko tulee vaatimaan, jotta annettu komento voidaan suorittaa loppuun. Muistissa olevat tietojoukot vaativat usein enemmän muistitilaa kuin levylle tallennetut. Tietojoukkojen uudelleen lataamisen yhteydessä muistikapasiteetti vaatii vähintään kaksinkertaisesti sen määrän muistia kuin silloin, kun muistikapasiteettia ei käytetä.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Kapasiteetin ylikäyttö, häätäminen ja tietojoukkojen lataaminen uudelleen

Power BI Premium antaa sinulle sen edun, että voit ylikuormittaa kapasiteettiasi. Voit esimerkiksi julkaista enemmän tietojoukkoja kuin mitä kapasiteettimuistiin mahtuu. Jos kapasiteettisi julkaistut tietojoukot tarvitsevat enemmän muistitilaa kuin kapasiteettiin mahtuu, osa tietojoukoista tallennetaan erikseen pysyvään muistiin. Pysyvä muisti on osa 100 TB:n tallennustilaa, joka liittyy jokaiseen kapasiteettiisi.

Mitkä tietojoukot säilytetään muistissa ja mitä muille tietojoukoille tapahtuu? Kuten yllä on kuvattu, kun tietojoukkoon kohdistuu pyyntö, se ladataan muistiin (kuvalataus). Kysely voi olla raporttipyyntö tai tietojen uudelleen lataaminen.

Koska voit ylikuormittaa kapasiteettisi, siihen voi myös kohdistua muistipainetta. Kun kapasiteetti kohtaa muistipainetta (koska uusi tietojoukko täytyy ladata tai joihinkin ladattuihin tietojoukkoihin kohdistuvat kyselyt lisäävät muistin tarvetta), solmu *häätää yhden tai useampia kapasiteettimuistissa olevista tietojoukkoista*. Tietojoukot, jotka ovat käyttämättöminä (eli niihin ei kohdistu kyseisellä hetkellä kyselyitä tai niitä ei ladata uudelleen), häädetään ensin ja häätöjärjestyksessä sovelletaan ”viimeksi käytetty ensin” -periaatetta. Jos häädettyihin tietojoukkoihin kohdistuu uusia komentoja, palvelu yrittää ladata ne uudelleen muistiin, mahdollisesti häätäen samalla muita tietojoukkoja. Tämä toiminta mahdollistaa tehokkaamman käytön mahdollistamalla sen, että kapasiteetti palvelee suurempaa määrää tietojoukkoja kuin mitä sen muistiin mahtuu.

Tietojoukkojen lataaminen muistiin on varsin muistia vievä toiminto. Tietojoukon koosta riippuen se saattaa kestää parista sekunnista pienten tietojoukkojen kohdalla kymmeniin sekunteihin tai jopa minuutteja suurien, ~10 GB:n kokoisten tietojoukkojen kohdalla. Premium-kapasiteetti pyrkii minimoimaan kapasiteetin lataamiseen tarvittavien kertojen määrän pitämällä viimeksi käytetyt tietojoukot muistissa niin pitkään kuin mahdollista. Kun lisämuistia tarvitaan, jotkin tietojoukot täytyy häätää. Järjestelmä pyrkii valitsemaan sellaisen, jonka poistumisella on pienin vaikutus käyttökokemukseen. Kun lisämuistia tarvitaan, jotkin tietojoukot täytyy häätää. Järjestelmä pyrkii valitsemaan sellaisen, jonka poistumisella on pienin vaikutus käyttökokemukseen. Esimerkiksi järjestelmä pyrkii välttämään sellaisten tietojoukkojen häätämistä, joita käytettiin aktiivisesti viimeisten muutaman minuutin aikana, koska niitä kysellään todennäköisesti uudelleen pian.

Itse häätöprosessi on nopea. Jos tietojoukko ei ole aktiivisessa käytössä häätöhetkellä, käyttäjä ei tule havaitsemaan juurikaan häädön vaikutusta. Kuitenkin, jos liian monta tietojoukkoa on aktiivisessa käytössä samaan aikaan ja muisti ei riitä niiden kaikkien ylläpitämiseen, häätöjä voi olla paljon. Tämä voi johtaa toistuviin häätöihin, jolloin tietojoukkoja häädetään ja ladataan uudelleen jatkuvasti ja käyttäjät voivat huomata selkeän laskun vasteajoissa ja tehokkuudessa.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Tietojoukon uudelleen lataamisen muistivaatimus kilpailee aktiivisten tietojoukkojen muistivaatimuksen kanssa

Tietojoukot voidaan ladata uudelleen ajastetusti tai käyttäjien pyynnöstä. Kuten yllä on kuvattu, täyden uudelleen lataamisen vaatima muistin määrä on vähintään kaksinkertainen verrattuna ladattuihin ja käyttämättöminä oleviin tietojoukkoihin. Ennen uudelleen lataamisen alkamista arvioidaan lataamisen vaatima muisti. Jos tarvittavan muistin kokonaismäärä on suurempi kuin käytettävissä oleva muistikapasiteetti, jotkin tietojoukot häädetään. Häätöehdokkaat valitaan sen mukaan mitä tietojoukkoja on käytetty viimeksi eli palvelu yrittää säilyttää muistissa niin monta hiljattain käytettyä tietojoukkoa kuin mahdollista.

Jos tarvittava muisti ei riitä häädöistä huolimatta, tietojen lataaminen uudelleen siirretään jonoon odottamaan uutta yritystä. Palvelu yrittää tietojen hakua kunnes se onnistuu tai kunnes uusi tietojen uudelleen lataaminen käynnistetään.

Jos millekään kapasiteetissa olevalle tietojoukolle tehdään interaktiivinen kysely ja tarvittava muisti ei ole käytettävissä käynnissä olevan tietojen uudelleen lataamisen takia, pyyntö epäonnistuu ja käyttäjän on yritettävä sitä uudelleen.

## <a name="cpu-resource-management-in-premium-capacity"></a>Suorittimen resurssien hallinta premium-kapasiteetissa

Suoritinresursseilla on kaksi pääkuluttajaa:

- Raporttien kyselyt
- Tietojen uudelleen lataaminen (käsittely)

### <a name="queries-from-reports"></a>Raporttien kyselyt

Raporttien kyselyt käyttävät kapasiteettisi suoritinresursseja. Jos raportissasi on kyselyjä, jotka ovat tehottomia tai jos sinulla on paljon yhtäaikaisia käyttäjiä, tämä saattaa käyttää paljon suoritinresursseja ja olemassa oleva kapasiteettisi ei välttämättä riitä kuormituksen käsittelemiseen.

### <a name="refresh-parallelization-policy"></a>Uudelleen lataamisen parallellisoimisen käytäntö

Muisti ei ole ainoa resurssi, joka saattaa rajoittaa tietojoukkojen uudelleen lataamista. Palvelimen näennäisytimien määrä voi myös olla tekijä. Koska jokainen uudelleen lataus vaatii tietyn määrän näennäisytimiä, yhtäaikaisten uudelleen latausten määrällä on raja. Rajoitus varastointiyksikköä kohden on esitetty seuraavassa taulukossa. Nämä rajat ylittävät uudelleen lataukset liitetään jonoon.

 | Varastointiyksikkö  | Taustan näennäisytimet  | Mallin uudelleen latauksen parallellisointi   |
 | --- | --- | --- |
 | A1  | 0.5  | 1  |
 | A2  | 1  | 2  |
 | A3  | 2  | 3  |
 | A4  | 4  | 6  |
 | A5  | 8  | 12  |
 | A6  | 16  | 24  |
 | EM1  | 0.5  | 1  |
 | EM2  | 1  | 2  |
 | EM3  | 2  | 3  |
 | P1  | 4  | 6  |
 | P2  | 8  | 12  |
 | P3  | 16  | 24  |
 | P4  | 32  | 48  |
 | P5  | 64  | 96  |

 > [!TIP]
> Jos uudelleen latauksesi viivästyvät, tarkista kapasiteettisi tukemien yhtäaikaisten uudelleen latausten määrä.

## <a name="example-scenarios"></a>Esimerkkejä

Seuraavassa kuvataan tavallisia tilanteita ja toimintoja, joihin palvelu ryhtyy:

 **Samaan aikaan aloitetaan 20 ajoitettua uudelleen latausta** - Power BI yrittää käynnistää ensimmäiset *x* uudelleen latausta yhtä aikaa. *X:n* arvo määräytyy varastointiyksikön uudelleen latausten parallellisointikäytännöstä. Jos Power BI ei pysty vapauttamaan tarpeeksi muistia häätämällä tietojoukkoja (joita ei ole käytetty hiljattain), kaikki *x* uudelleen latausta eivät käynnisty yhtä aikaa. Sellainen uudelleen lataus, joka ei pysty käynnistymään, siirtyy jonoon, kunnes se voi käynnistyä.

 **Kaksi uudelleen latausta on käynnissä yhtä aikaa ja muisti riittää vain toisen suorittamiseen loppuun** - Se, joka voidaan suorittaa loppuun, käynnistetään. Toista yritetään uudelleen myöhemmin.

 **Suurelle määrälle tietojoukkoja tehdään kyselyjä samalla, kun useita tietojoukkoja ladataan uudelleen** - Jos muistia ei ole tarpeeksi, Power BI yrittää pysäyttää aktiiviset uudelleen lataukset antaakseen prioriteetin interaktiivisille kyselyille. Tämä vähentää uudelleen lataamisen tehokkuutta.

 **Tietojoukko vaatii liikaa muistia, jotta se voitaisiin ladata uudelleen olemassa olevalla kapasiteetilla** - Uudelleen lataaminen epäonnistuu. Yrityksiä hankkia lisämuistia häätöjen avulla ei tehdä.

 **Yksittäisen tietojoukon uudelleen lataaminen aiheuttaa suuren piikin muistissa** - Jos piikki on suurempi kuin se muistin määrä, joka voidaan saavuttaa häätämällä käyttämättömiä tietojoukkoja, uudelleen lataamista yritetään uudelleen, kunnes muisti riittää piikin käsittelyyn.

 **Sellaiselle tietojoukolle, joka ei voi saada tarpeeksi muistia häätämällä kaikki käyttämättömät tietojoukot ja uudelleen lataukset, tehdään kysely** - Kyselyt epäonnistuvat. Tällaisia työkuormitustilanteita varten tulee hankkia korkeampi kapasiteetti.

## <a name="troubleshooting-and-testing"></a>Vianmääritys ja testaus

Jos raportit ovat hitaita tai eivät vastaa, aloita testaamalla raporttiasi vain yhdellä käyttäjällä. Nosta sitten yhtäaikaista käyttäjäkuormitusta löytääksesi rajan. Monissa tapauksissa DAX (raporttikyselyt) voi vaikuttaa merkittävästi raporttiesi tehokkuuteen (ja nostaa kapasiteettisi tukemien yhtä aikaisten käyttäjien määrää).

Käytä Power BI Embedded -kapasiteettia Azuressa testataksesi eri varastointiyksikköjä ja määrittääksesi parhaan Premium-varastointiyksikön odotetulle kuormitukselle. Power BI Embedded A4 -varastointiyksikkö vastaa P1:stä, A5 = P2 ja A6 = P3. Azuressa voit vaihtaa helposti varastointiyksiköiden välillä skaalaamalla Azure-portaalissa suurempaan ja pienempään. Kun löydät varastointiyksikön, joka toimii kuormituksellesi parhaiten ja olet lopettanut testauksen, voit poistaa varastointiyksikön.

Joissain tapauksissa mallin PBIX-tiedoston avaaminen tietokoneellasi ja muistin ja suorittimen kulutuksen tarkistaminen voi kertoa paljon ongelmasta. Tämä ei auta erittäin isojen mallien yhteydessä, mutta joidenkin pienempien mallien kohdalla voit yrittää mallin avaamista, uudelleen lataamista ja kyselemistä tietokoneellasi. Tarkista mallin koko, käytetty muisti ja suorittimen kulutus, kun avaat mallin. Yritä päivittämistä uudelleen ja kyselyä. Käytä tehtävienhallintaa suorittimen ja muistin käytön tarkistamiseen paikallisessa PBIX-tiedostossa. Joskus nämä mittatiedot yksinään kertovat, että alempi kapasiteetti kuten P1/P2 ei välttämättä riitä ratkaisullesi.
