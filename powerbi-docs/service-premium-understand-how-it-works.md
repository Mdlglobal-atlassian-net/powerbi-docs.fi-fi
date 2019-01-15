---
title: Power BI Premium -kapasiteetin muistin käyttö ja optimointi
description: Power BI Premium -kapasiteetin muistin hallinnan ja optimoinnin ymmärtäminen.
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-admin
ms.author: mblythe
ms.reviewer: mblythe
author: mgblythe
manager: kfile
ms.openlocfilehash: efb0f1dfd340c0defcba8a67e0e46051d0d9be25
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54293839"
---
# <a name="microsoft-power-bi-premium-capacity-resource-management-and-optimization"></a>Microsoft Power BI Premium -kapasiteetin resurssien hallinta ja optimointi

Tässä artikkelissa kuvataan, miten Power BI Premium hallinnoi resursseja. Artikkeli sisältää myös esimerkkejä ja vianmääritysehdotuksia. Katso yleiskatsaus aiheesta kohdassa [Mikä on Power BI Premium?](service-premium.md).

## <a name="premium-capacity-memory-management"></a>Premium-kapasiteetin muistinhallinta

 Premium-kapasiteetin muistia kuluttavat:

* Muistiin ladattavat tietojoukot
* Tietojoukkojen uudelleen lataaminen (sekä ajastetut että pyydetyt)
* Kuormitukset, joita kapasiteetti tukee
* Raporttikyselyt

Kun kapasiteetissäsi olevasta, julkaistusta tietojoukosta tulee pyyntö, kyseinen tietojoukko ladataan muistiin pysyvästä tallennusvälineestä (tätä kutsutaan myös kuvan lataamiseksi). Tietojoukon pitäminen ladattuna muistiin auttaa nopeuttamaan kyseiseen tietojoukkoon liittyviin kyselyihin vastaamista tulevaisuudessa. Tietojoukon muistiin lataamisen viemän muistin lisäksi raporttikyselyt ja tietojoukkojen uudelleen lataaminen vievät lisämuistia.

### <a name="dataset-memory-estimation"></a>Tietojoukon muistitilan arvio

Kun tietojoukkoa yritetään ladata muistiin, Power BI arvioi muistin määrän, jonka kyseinen tietojoukko tulee vaatimaan, jotta annettu komento voidaan suorittaa loppuun. Muistissa olevat tietojoukot vaativat usein enemmän muistitilaa kuin levylle tallennetut. Tietojoukkojen uudelleen lataamisen yhteydessä Power BI vaatii vähintään kaksinkertaisesti sen määrän muistia kuin silloin, kun tietojoukkoa ei käytetä.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Kapasiteetin ylikäyttö, häätäminen ja tietojoukkojen lataaminen uudelleen

Power BI Premium antaa sinulle sen edun, että voit *ylikuormittaa* kapasiteettiasi. Voit esimerkiksi julkaista enemmän tietojoukkoja kuin mitä kapasiteettiin mahtuu. Jos julkaistut tietojoukot tarvitsevat enemmän muistia kuin mitä kapasiteetilla on käytettävissä, osa tietojoukoista tallennetaan erikseen pysyvään muistiin. Pysyvä muisti on osa 100 TB:n tallennustilaa, joka liittyy jokaiseen kapasiteettiisi.

Mitkä tietojoukot säilytetään muistissa ja mitä muille tietojoukoille tapahtuu? Kuten yllä on kuvattu, kun tietojoukkoon kohdistuu pyyntö, se ladataan muistiin (kuvalataus). Kysely voi olla raporttipyyntö tai tietojen uudelleen lataaminen. Mutta koska voit ylikuormittaa kapasiteettisi, siihen voi myös kohdistua muistipainetta. Kun kapasiteetti kohtaa muistipainetta, solmun *häätää* yhden tai useamman tietojoukon muistista. Passiiviset tietojoukot (joihin ei kyseisellä hetkellä kohdistu kysely- tai uudelleenlataustoimintoja) häädetään ensin. Seuraavaksi häätöjärjestyksessä sovelletaan ”viimeiseksi käytetyt ensin” -periaatetta. Jos häädettyyn tietojoukkoon kohdistuu uusia komentoja, palvelu yrittää ladata tietojoukon uudelleen muistiin, mahdollisesti häätäen samalla muita tietojoukkoja. Tämä toiminta mahdollistaa tehokkaamman käytön mahdollistamalla sen, että kapasiteetti palvelee suurempaa määrää tietojoukkoja kuin mitä sen muistiin mahtuu.

Tietojoukkojen lataaminen muistiin on varsin muistia vievä toiminto. Tietojoukon koosta riippuen se saattaa kestää parista sekunnista pienten tietojoukkojen kohdalla kymmeniin sekunteihin tai jopa minuutteja merkittävien, ~10 GB:n kokoisten tietojoukkojen kohdalla. Premium-kapasiteetti pyrkii minimoimaan kapasiteetin lataamiseen tarvittavien kertojen määrän pitämällä viimeksi käytetyt tietojoukot muistissa niin pitkään kuin mahdollista. Kun lisämuistia tarvitaan, jotkin tietojoukot täytyy häätää. Järjestelmä pyrkii valitsemaan sellaisen, jonka poistumisella on pienin vaikutus käyttökokemukseen. Kun lisämuistia tarvitaan, jotkin tietojoukot täytyy häätää. Järjestelmä pyrkii valitsemaan sellaisen, jonka poistumisella on pienin vaikutus käyttökokemukseen. Järjestelmä yrittää esimerkiksi olla häätämättä sellaisia tietojoukkoja, joita on käytetty aktiivisesti viimeisen muutaman minuutin aikana. On hyvin todennäköistä, että näihin tietojoukkoihin kohdistuu kyselyitä pian uudelleen.

Itse häätöprosessi on nopea. Jos tietojoukko ei ole aktiivisessa käytössä häätöhetkellä, käyttäjä ei tule havaitsemaan juurikaan häädön vaikutusta. Mutta jos liian monta tietojoukkoa on aktiivisessa käytössä samanaikaisesti ja muisti ei riitä niiden kaikkien ylläpitämiseen, häätöjä voi olla paljon. Jos sinulla on liian monta aktiivista tietojoukkoa, tämä voi johtaa toistuviin häätöihin, jolloin tietojoukkoja häädetään ja ladataan uudelleen jatkuvasti ja käyttäjät voivat huomata selkeän laskun vasteajoissa ja tehokkuudessa.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Tietojoukon uudelleen lataamisen muistivaatimus kilpailee aktiivisten tietojoukkojen muistivaatimuksen kanssa

Tietojoukot voidaan ladata uudelleen ajastetusti tai käyttäjien pyynnöstä. Kuten yllä on kuvattu, täyden uudelleen lataamisen vaatima muistin määrä on vähintään kaksinkertainen verrattuna ladattuihin ja käyttämättöminä oleviin tietojoukkoihin. Ennen uudelleen lataamisen alkamista arvioidaan lataamisen vaatima muisti. Jos tarvittavan muistin kokonaismäärä on suurempi kuin käytettävissä oleva muistikapasiteetti, jotkin tietojoukot häädetään. Muistutuksena vielä, että häätämisjärjestys perustuu ”viimeiseksi käytetyt ensin” -periaatteeseen.

Jos tarvittava muisti ei riitä häädöistä huolimatta, tietojen lataaminen uudelleen siirretään jonoon odottamaan uutta yritystä. Palvelu yrittää tietojen hakua kunnes se onnistuu tai kunnes uusi tietojen uudelleen lataaminen käynnistetään.

Jos millekään kapasiteetissa olevalle tietojoukolle tehdään interaktiivinen kysely ja tarvittava muisti ei ole käytettävissä käynnissä olevan tietojen uudelleen lataamisen takia, pyyntö epäonnistuu ja käyttäjän on yritettävä sitä uudelleen.

### <a name="workloads"></a>Kuormitukset

Oletusarvoisesti **Power BI Premiumin** ja **Power BI Embeddedin** kapasiteetit tukevat vain kuormitusta, joka liittyy Power BI -kyselyiden suorittamiseen pilvipalvelussa. Esikatselun tuki tarjotaan nyt myös kahdelle muulle kuormitukselle: **sivutetut raportit** ja **tietovuot**. Jos nämä työnkulut ovat käytössä, ne voivat vaikuttaa muistin käyttöön kapasiteetissasi. Lisätietoja on kohdassa [Kuormituksien määrittäminen](service-admin-premium-manage.md#configure-workloads).

## <a name="cpu-resource-management-in-premium-capacity"></a>Suorittimen resurssien hallinta premium-kapasiteetissa

Suoritinresursseilla on kaksi pääkuluttajaa:

* Raporttien kyselyt
* Tietojen uudelleen lataaminen (käsittely)

### <a name="queries-from-reports"></a>Raporttien kyselyt

Raporttien kyselyt käyttävät kapasiteettisi suoritinresursseja. Raportit, jotka sisältävät tehottomia kyselyitä tai monia samanaikaisia käyttäjiä, voivat käyttää paljon suoritinresursseja. Olemassa oleva kapasiteettisi ei välttämättä pysty käsittelemään siihen kohdistuvaa kuormitusta.

### <a name="refresh-parallelization-policy"></a>Uudelleen lataamisen parallellisoimisen käytäntö

Muisti ei ole ainoa resurssi, joka saattaa rajoittaa tietojoukkojen uudelleen lataamista. Palvelimen näennäisytimien määrä voi myös olla tekijä. Koska jokainen uudelleen lataus vaatii tietyn määrän näennäisytimiä, yhtäaikaisten uudelleen latausten määrällä on raja. Rajoitus varastointiyksikköä kohden on esitetty seuraavassa taulukossa. Nämä rajat ylittävät uudelleen lataukset liitetään jonoon.

 | SKU | Taustan näennäisytimet | Mallin uudelleen latauksen parallellisointi |
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

Tässä muutama tavallinen tilanne sekä esimerkkejä toiminnoista, joihin palvelu ryhtyy:

**Samaan aikaan aloitetaan 20 ajoitettua uudelleen latausta**. Power BI yrittää käynnistää ensimmäiset *x* uudelleen latausta yhtä aikaa. *X:n* arvo määräytyy varastointiyksikön uudelleen latausten parallellisointikäytännöstä. Jos Power BI ei pysty vapauttamaan tarpeeksi muistia häätämällä tietojoukkoja (joita ei ole käytetty hiljattain), kaikki *x* uudelleen latausta eivät käynnisty yhtä aikaa. Sellainen uudelleen lataus, joka ei pysty käynnistymään, siirtyy jonoon, kunnes se voi käynnistyä.

**Kaksi uudelleen latausta on käynnissä yhtä aikaa ja muisti riittää vain toisen suorittamiseen loppuun**. Se, joka voidaan suorittaa loppuun, käynnistetään. Toista yritetään uudelleen myöhemmin.

**Suurelle määrälle tietojoukkoja tehdään kyselyjä samalla, kun useita tietojoukkoja ladataan uudelleen**. Jos tarpeeksi muistia ei ole käytettävissä, Power BI yrittää pysäyttää aktiiviset uudelleen lataukset antaakseen prioriteetin interaktiivisille kyselyille. Tämä vähentää uudelleen lataamisen tehokkuutta.

**Tietojoukko vaatii liikaa muistia, jotta se voitaisiin ladata uudelleen olemassa olevalla kapasiteetilla**. Uudelleen lataaminen epäonnistuu. Yrityksiä hankkia lisämuistia häätöjen avulla ei tehdä.

**Yksittäisen tietojoukon uudelleen lataaminen aiheuttaa suuren piikin muistissa**. Jos piikki on suurempi kuin se muistin määrä, joka voidaan saavuttaa häätämällä käyttämättömiä tietojoukkoja, uudelleen lataamista yritetään uudelleen, kunnes muisti riittää piikin käsittelyyn.

**Sellaiselle tietojoukolle, joka ei voi saada tarpeeksi muistia häätämällä kaikki käyttämättömät tietojoukot ja uudelleen lataukset, tehdään kysely**. Kyselyt epäonnistuvat. Tällaisia työkuormitustilanteita varten tulee hankkia korkeampi kapasiteetti.

## <a name="troubleshooting-and-testing"></a>Vianmääritys ja testaus

Jos raportit ovat hitaita tai eivät vastaa, aloita testaamalla raporttiasi vain yhdellä käyttäjällä. Nosta sitten yhtäaikaista käyttäjäkuormitusta löytääksesi rajan. Monissa tapauksissa voit muuttaa raporttiesi tehokkuutta huomattavasti säätämällä DAX-kyselyitäsi. Kyselyiden säätäminen kasvattaa myös kapasiteettisi tukemien samanaikaisten käyttäjien määrää. [Valvo kapasiteettiasi](service-admin-premium-monitor-capacity.md) tunnistaaksesi mahdollisia suorituskykyongelmia.

Käytä Power BI Embedded -kapasiteettia Azuressa testataksesi eri varastointiyksikköjä ja määrittääksesi parhaan Premium-varastointiyksikön odotetulle kuormitukselle. Power BI Embedded A4 -varastointiyksikkö vastaa P1:stä, A5 = P2 ja A6 = P3. Azuressa voit vaihtaa helposti varastointiyksiköiden välillä skaalaamalla Azure-portaalissa suurempaan ja pienempään. Kun löydät varastointiyksikön, joka toimii kuormituksellesi parhaiten ja olet lopettanut testauksen, voit poistaa varastointiyksikön.

Joissain tapauksissa mallin Power BI Desktop (.pbix) -tiedoston avaaminen tietokoneellasi ja muistin ja suorittimen kulutuksen tarkistaminen voi kertoa paljon ongelmasta. Tämä ei auta erittäin isojen mallien yhteydessä, mutta joidenkin pienempien mallien kohdalla voit yrittää mallin avaamista, uudelleen lataamista ja kyselemistä tietokoneellasi. Tarkista mallin koko, käytetty muisti ja suorittimen kulutus, kun avaat mallin. Yritä päivittämistä uudelleen ja kyselyä. Käytä tehtävienhallintaa suorittimen ja muistin käytön tarkistamiseen paikallisessa tiedostossa. Joskus nämä mittatiedot yksinään kertovat, että alempi kapasiteetti kuten P1/P2 ei välttämättä riitä ratkaisullesi.

## <a name="next-steps"></a>Seuraavat vaiheet

[Kapasiteettien hallinta Power BI Premiumissa ja Power BI Embeddedissä](service-admin-premium-manage.md)