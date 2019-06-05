---
title: Käyttöönotto ja hallinta Power BI Premium-kapasiteetteja
description: Tutustu Power BI Premium mahdollisuuksia ja lue, miten voit suunnitella, ottaa käyttöön, valvoa ja vianmääritys skaalattava ratkaisuja.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 03/06/2019
LocalizationGroup: Premium
ms.openlocfilehash: fbae2a8b577c52ae597d44bd6ea9913510c4c65c
ms.sourcegitcommit: dc73e932c9982a4aa0b0ec5297fb9f94c6156bc5
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2019
ms.locfileid: "66518575"
---
# <a name="deploying-and-managing-power-bi-premium-capacities"></a>Käyttöönotto ja hallinta Power BI Premium-kapasiteetteja

**:** Power BI Premium tarjoaa tasaisemman suorituskyvyn, suuri tietomäärät tuki ja yhdistetty Omatoiminen ja yrityksen BI-ympäristössä joustavuutta kaikille organisaatiossasi. Taso 300 Tässä teknisessä raportissa on kirjoitettu erityisesti Power BI-Järjestelmänvalvojat ja sisällön tekijät ja julkaisijat. Se pyrkii heidän on helpompi ymmärtää Power BI Premium mahdollisuuksia ja kerrotaan, kuinka voit suunnitella, ottaa käyttöön, valvoa ja vianmääritys skaalattava ratkaisuja.

**Tekijä:** [Peter Myers](https://www.linkedin.com/in/peterjsmyers) (tietojen Platform MVP ja riippumattoman BI asiantuntijan Bitwise ratkaisuista)

**Tekniset tarkistajat:** Adam Saxton, Akshai Mirchandani, Bhavik Merchant, David Magar, Josh Caplan, Michael Blythe, Nimrod Shalit, Olivier Matrat, Swati Gupta

**Koskee seuraavia:** Power BI-palvelun, Power BI Premium-ja Azure Power BI Embedded kapasiteetit

> [!NOTE]
> Voit tallentaa tai tulostaa tämän teknisen raportin valitsemalla selaimesta **Tulosta** ja valitsemalla sitten **Tallenna PDF-tiedostona**.

## <a name="introducing-power-bi"></a>Power BI:n esittely

Power BI on liiketoiminta-analyysejä palvelu suunniteltu toimittaa merkityksellisiä tietoja, jotka mahdollistavat nopea, tasalla päätöksiä. 2015 version jälkeen siitä on nopeasti tullut suosittuja palvelu, johon lähetetään ratkaisuja pienin organisaatioissa suurin yritysten.

Sen saataville kahdella tavalla: Pilvipalveluun ja paikallisesta reporting ratkaisun nimeltä **Power BI-raporttipalvelimen**. \[[1](#endnote-01)\]

Power BI, kuten pilvipalveluun on ohjelmisto-kuin-(SaaS) \[ [2](#endnote-02)\]. Se edustaa palveluita ja -sovelluksia, joiden avulla organisaatiot voivat kehittää, ottaa käyttöön, hallinta, Jaa valvomaan piirissä, liiketoiminta-ratkaisuja.

Se ei ole tässä raportissa aikoo kattavan kuvauksen Power BI-palvelun. Sen sijaan painopiste on Power BI Premium aihe aiheista. Viittaavat yleistietoja Power BI sopivia [Power BI-dokumentaatio](service-admin-premium-multi-geo.md). Tarkempi kuvaus toteuttaa hyvin toimiva yrityksissä painopisteinä Power BI-palvelun viittaavat sopivia [Planning a Power BI Enterprise Deployment](https://aka.ms/pbienterprisedeploy) tekninen raportti.

Tässä raportissa aihe kontekstissa tässä osiossa esitellään ja kapasiteetit, Power BI-sisältötyypit, mallin tallennustilan tilaa ja käyttöoikeuksien. Käsitys aiheet on keskeistä käyttöönotto ja hallinta Power BI Premium onnistuneesti.

### <a name="capacities"></a>Kapasiteetit

**Kapasiteettien** ovat core Power BI käsite edustava joukon resursseja (tallennustilan, suorittimen ja muistin) isännöi sekä toimittaa Power BI-sisällön. Kapasiteetit ovat joko jaettu tai järjestelmänvalvojalle. A **jaettuun kapasiteettiin** on jaettu muiden Microsoft-asiakkaiden kanssa, mutta **varattuun kapasiteettiin** pyrkii täysin yhdelle asiakkaalle. Varattua kapasiteettia on esitetty [Premium-kapasiteetteja](#premium-capacities) aiheessa.

Jaettu kapasiteetti työnkulut suoritetaan jaetuissa Laskennallisissa muiden asiakkaiden kanssa. Kapasiteetti on jakaa resursseja, kuten rajoitukset johtuvat varmistamiseksi ”Tivolien toista”, kuten suurin mallin koko (1 gt) ja suurin päivittäinen päivitystiheyden (kahdeksan kertaa päivässä).

### <a name="workspaces"></a>Työtilat

Power BI-työtilat sijaitsevat kapasiteettien ja ne edustavat suojauksen, yhteistyö ja käyttöönoton säilöjä. Power BI kullakin käyttäjällä on henkilökohtaista työtilaa, jota kutsutaan **oma työtila**. Lisää työtiloissa voi luoda yhteistyö- ja ota käyttöön ja näitä kutsutaan **Sovellustyötilat**. Oletusarvon mukaan – mukaan lukien Omat työtilat - työtilojen luodaan jaettuun kapasiteettiin.

### <a name="power-bi-content-types"></a>Power BI-sisältötyypit

Ottaa käyttöön Power BI Premium-aiheita, on tärkeää perusteellinen Power BI-arkkitehtuurista esimerkiksi olennainen sisältötyypit alkaa.

Kaikki Power BI-sisältö on tallennettu, ja sitä hallitaan työtiloissa, jotka ovat säilöjä Power BI-sisältöä. Power BI kullakin käyttäjällä on oman työtilansa, mutta Yleiset paras käytäntö on luoda sovelluksen työtiloja. Sovelluksen työtilat käyttöön vuokrattua sisällön ja mahdollisuus tehdä yhteistyötä sisältöä. Ne tarjoavat myös mahdollisuuden valmistella ja jaella sisältöä käyttäjäryhmille leveä sovelluksina.

Työtiloja on tallennettu Power BI-sisältö:

- Tietovuot
- Tietojoukot
- Työkirjat
- Raportit
- koontinäytöt

#### <a name="dataflows"></a>Tietovuot

Power BI dataflows avulla organisaatiot voivat selkeyttää tietoja eri lähteistä. Ne pitää valmistella ja valmistelu käytettäväksi malleja, mutta niitä ei voi käyttää suoraan lähteenä raportointia varten. Ne hyödyntävät Microsoft tietoyhteyksiä, tietojen paikallisen ja pilvipohjainen tietolähteistä käsittely käyttöön laajan valikoiman.

Dataflows vain voidaan luoda ja hallita sovelluksen työtilat, ja ne tallennetaan entiteetit-Common Data mallin (CDM)-Azure Data Lake Storage Gen2. Tavallisesti ne on ajoitettu päivittymään toistuvasti ajan tasalla tietojen tallentamiseen.

Lisätietojen saamiseksi viittaavat [Omatoiminen tietojen valmistautuminen Power BI (esikatselu)](service-dataflows-overview.md) tiedoston.

#### <a name="datasets"></a>Tietojoukot

Power BI-tietojoukkoja edustavat valmis raportoinnissa ja visualisointitehtävissä tietolähdettä. On useita tietojoukoista, luonut:

- Yhteyden muodostaminen aiemmin tietomalliin, joka ei isännöidä Power BI-kapasiteetti
- Ladataan Power BI Desktop-tiedosto, joka sisältää mallin
- Ladataan (jossa Excel-taulukot tai tietomallissa työkirjan) Excel-työkirja tai Comma-Separated arvo CSV-tiedoston lataaminen palvelimeen
- Palveluilmoituksen, streaming tai yhdistelmäyhteyksien suoratoistettavan tietojoukon luominen Power BI-palvelun avulla

Lukuun ottamatta suoratoistettaviin tietojoukkoihin \[ [3](#endnote-03)\], tietojoukko edustaa tietomalliin, joka hyödyntää Analysis Services-kehittynyt mallinnus-tekniikoista.

Huomaa, että osassa, joskus terminologies tietojoukkoja ja malleja tarkoitetaan. Yleensä Power BI-näkökulmasta sitä kutsutaan **tietojoukon** , ja sitä kutsutaan kehityksen näkökulmasta **mallin**. Tässä raportissa kontekstissa ne puhuttaessa paljon.

##### <a name="externally-hosted-models"></a>Ulkoisesti isännöimä mallit

Yhdistäminen ulkoisesti isännöityyn malliin liittyy asennetaan [paikallisen Tietoyhdyskäytävän](service-gateway-onprem.md) yhteyden muodostamiseen SQL Server Analysis Services, onko paikallinen tai VM-isännöityjä infrastruktuurin kuin--palvelun (IaaS). Azure Analysis Services ei edellytä yhdyskäytävää. Tässä tilanteessa on usein järkevää, kun on olemassa olevan mallin sijoitukset, yleensä yksityishenkilöiden yrityksen tietoja tietovaraston (Asennettu). Sen avulla voit suorittaa Power BI **reaaliaikaisen yhteyden** (LC) Analysis Services- ja käyttämällä käyttämällä Power BI-raportin käyttäjän tietojen käyttöoikeudet. SQL Server Analysis Services monidimensiomallit (kuutiot) ja Taulukkomallit tuetaan. Seuraavassa kuvassa esitetyllä reaaliaikaisen yhteyden tietojoukon välittää kyselyt ulkoisesti isännöity malleja.

![Reaaliaikaisen yhteyden tietojoukon välittää kyselyt ulkoisesti isännöity mallit](media/whitepaper-premium-deployment/live-connection-dataset.png)

##### <a name="power-bi-desktop-developed-models"></a>Power BI Desktop kehittyneiden mallit

Power BI Desktop - tarkoitettu Power BI-kehityksen asiakassovellus - voi käyttää mallia, joka toimii käytännössä Analysis Services-taulukkomallissa kehittämiseen. Mallit voidaan kehittää tuomalla tietoja dataflows, joka voidaan integroida sitten muiden tietolähteiden kanssa. Tekniset tiedot, miten voit tehdä mallinnus on tässä raportissa käyttöalueen, on tärkeää ymmärtää, että on kolme eri tietotyyppejä - tai tilaa - mallien, joka voidaan kehittää käyttämällä Power BI Desktop. Tiloista Selvitä, onko tiedot tuodaan malliin tai onko se pysyy tietolähteessä. Kolmessa ovat: Tuo DirectQuery ja kooste. Kussakin tilassa enempää tarkoitettuihin [mallin tallennustilan tilaa](#model-storage-modes) aiheessa.

Ulkoisesti isännöimä mallit ja Power BI Desktopissa on kehitetty mallit voi toteuttaa rivitason suojaus (RLS) rajoittaa tiedot, jotka voidaan noutaa tietyt käyttäjälle. Esimerkiksi myyjien käyttöoikeusryhmä määritetyt käyttäjät voivat vain tarkastella raporttitietoja, joihin ne on varattu myynnin vaarantuneet. Rivitason suojauksen roolit voi olla dynaaminen tai staattinen. **Dynaaminen roolit** suodatin raportin käyttäjä aikana **staattinen roolit** Käytä samoja suodattimia roolissa kaikille käyttäjille.

##### <a name="excel-workbook-models"></a>Excel-työkirjan mallit

Luodaan tietojoukkoja Excel-työkirjoja tai CSV tiedostot johtaa automaattisen luomisen malli. Luo tietomallitaulukoita, kun Excel-työkirjan tietomalliin muuttuu Power BI-mallin luominen ei tuoda Excel-taulukot ja CSV-tiedot. Kaikissa tapauksissa tiedostotiedot on tuotu malli.

Sitten, tunnustukset, voi tehdä Power BI-tietojoukkoja, jotka edustavat mallit:

- Isännöidään joko Power BI-palvelussa tai ulkoisesti hoitaa Analysis Services
- He voivat tallentaa tuotuja tietoja tai he voivat ongelman Passthrough-kohteeksi kyselypyyntöjen pohjana oleville tietolähteille, tai sekä sekä

Tässä on yhteenveto tietoja Power BI-tietojoukkoja, jotka edustavat mallien tärkeitä seikkoja:

- Isännöity SQL Server Analysis Services-mallit edellyttävät yhdyskäytävää suorittaa LC kyselyt
- Power BI-isännöityjä malleja, joka tuo tiedot
  - On oltava täysin ladataan muistiin, jotta hän voi tehdä kyselyitä
  - Edellytä päivityksen pitämään tiedot ajan tasalla ja yhdyskäytävät on oltava mukana, kun lähdetiedot ei voi käyttää suoraan Internetissä
- Power BI-isännöityjä malleja, jotka käyttävät DirectQuery (DQ) tallennustilan edellyttävät lähdetiedot yhteys. Kun mallista tehdään kysely, Power BI myöntää kyselyt lähdetiedot nykyisen tietojen noutamiseen. Tässä tilassa on koskea yhdyskäytäviä, kun lähdetiedot ei voi käyttää suoraan Internetissä.
- Mallit voivat Pakota rivitason suojauksen sääntöjä, otetaan pakotetusti käyttöön suodattimia, voit rajoittaa tietojen käyttöä tietyille käyttäjille

Onnistuneesti ottaa käyttöön ja hallita Power BI Premium, on tärkeää ymmärtää, jossa mallien isännöidään niiden tallennustilan, yhdyskäytäviä, tuotujen tietojen koko mahdolliset riippuvuudet ja lajia ja päivittää. Nämä kaikki voivat merkittävä vaikutus Power BI Premium-resursseja. Lisäksi huomioon mix lisätä mallin rakenteen itse valmistelu kyselyt ja laskutoimituksia.

Myös on tärkeää ymmärtää, että Power BI-isännöityjä tuominen mallit voi päivittää aikataulun mukaisesti ja voi käynnistää pyydettäessä käyttäjän Power BI-palvelussa.

Suunnittelu optimoitu mallien käsitellään myöhemmin tässä tekniset [optimointi mallien](#optimizing-models) aiheessa.

#### <a name="workbooks"></a>Työkirjat

Power BI-työkirjat ovat Power BI-sisällön tyyppi \[ [4](#endnote-04)\]. Ne ovat Excel-työkirjoja, jotka on ladattu Power BI-palveluun ja ei voi sekoittaa ladattu Excel-työkirjoja, Luo tietojoukkoja (mallien). Työkirjan sisällön tyyppi edustaa yhteyden työkirjaan, joka voi joko ladata Power BI-palvelussa tai pysyvät Onedriveen tai SharePoint Onlineen pilvitallennustilaan.

On tärkeää ymmärtää, että tämän sisällön tyyppi ei ole käytettävissä Power BI-tietojen visualisointeja tietolähteenä. Sen sijaan se voi avata työkirjan Power BI-palvelussa käyttämällä Excel Onlinessa. Tämän sisällön tyypin tärkein tarkoituksena on Salli vanhat Excel työkirjan raportteja voi käyttää Power BI-palvelussa ja sallimaan sen tietojen visualisoinnit voidaan kiinnittää Power BI-koontinäyttöihin.

Lisätietoja saat viittaavat [tietojen noutaminen Excel-työkirjatiedostoista](service-excel-workbook-files.md) tiedoston.

#### <a name="reports"></a>Raportit

Raporttien kahdenlaisia: Power BI-raportteja ja sivutettuja raportteja.

**Power BI-raporttien** tarjoavat vuorovaikutteinen tietojen visualisoinnin kokemuksia muodostaa yhteyden vain yhteen tietojoukkoon. Raportit on suunniteltu usein Kannusta käyttäjien osallistumisen käyttäjälle ominaisuuksia, satunnaisen arvomatriisi käsitellä suodatus mittayksikkösovellukseen, mukaan lukien yrityksenlaajuiset suodattaminen ja korostaminen, porautuminen ylöspäin, joka porautuu alaspäin, porautumista läpi, Q & luonnollisen kielen questioning, tutustutaan, sivulla siirtymisen, Spotlight-videoiksi korostetut, tarkastelua kirjanmerkkien ja lisää.

Tässä raportissa kontekstissa, on tärkeää ymmärtää, miten Power BI-arkkitehtuuri Power BI-raportin suunnittelu ja käyttäjän vuorovaikutukset voit kaikki vaikuttaa Power BI-palvelun resursseja:

- Voit ladata ja käsitellä raportteja tuontimalleille perusteella, mallin on oltava täysin ladataan muistiin (joko isännöityjen Power BI-palvelussa tai isännöity ulkoisesti)
- Jokainen raportin visualisoinnin tekee kyselyn tietojen noutamiseen tekemällä malli
- Yleensä suodatin- ja vuorovaikutukset koskea kyselyä mallin. Esimerkiksi muuttaminen osittajan valinta - oletusarvoisesti - edellyttää sivulla olevan kunkin visualisoinnin lataaminen uudelleen \[ [5](#endnote-05)\]
- Power BI-raportteja ei takaa näkyvä nykyiset tiedot, ja ne voivat vaatia käyttäjä lataa raporttisivun ja sen visualisointeja raportin
- Käyttäjät voivat osallistua Q & luonnollisen kielen ominaisuus esittää kysymyksiä, jolloin Power BI-raportin suunnittelun sallii ja tietojoukko edustaa Power BI-isännöityjä tuonti tietomallin tai Q & A käyttöön LC tietojoukko

**Sivutetut raportit** julkaisu sallii ja SQL Server Reporting Services (SSRS)-raporttien hahmontaminen (\*.rdl-muoto). Kun nimensä ehdottaa, sivutettuja raportteja käytetään yleensä vaatimukset määräävät kiinteä sivukokoa tulostuksen tarpeen tai tietoja, jotka on laajennettava kokonaan muuttujan luetteloita ei. Esimerkiksi suunniteltu usean sivun (sijaan vierityksen visualisoinnin sisällä) laskun ja tulostaminen.

Kaksi tuetut raporttityypit Anna valinta-raporttien tekijät ne, voit valita tyypin perusteella vaatimukset ja käyttötarkoitus. Power BI-raportit ovat yleensä sopii erittäin vuorovaikutteisia kokemuksia salliminen tutkia ja löytää merkityksellisiä tietoja, kun parametri perustuvia asetteluja soveltuvat paremmin sivutettuja raportteja.

Raporttityyppi riippumatta saavuttamiseksi reagoiva raportin lataaminen ja tietojen päivitykset (kun suodattimien tai parametrien muutetaan) on ehdottoman luotettavia ja hyvin toimiva käyttäjäkokemuksen toimittaminen.

#### <a name="dashboards"></a>koontinäytöt

Power BI-koontinäytöt on tarkoitettu tarjoavat valvonta kokemuksia ja eroavat käsitteellisesti hyvin Power BI-raportteja. Koontinäyttöjä voidaan näyttää yksittäisen ruudun tarjoava ilmaista arvojen ja tietojen visualisoinnit ruudut. Yleensä koontinäytöt tarjoavat vähemmän vuorovaikutuksen kokemuksia kuin Power BI-raportteja, jotkin koontinäytön rakenteet odotetaan ei toimia. Esimerkiksi automaattisen koontinäytön, esitetään palvelimen huoneessa kosketus näytössä. Toinen merkittävimmistä on koontinäyttöjä voi esittää ruutuja, jotka useita tietojoukkoja, kun Power BI-tietoihin raportin vain koskaan voi perustua yhteen tietojoukkoon.

On tärkeää ymmärtää, että koontinäytön on suunniteltu lataaminen nopeasti ja Express uusimmat tiedot (joita kutsutaan Power BI-palveluun) lainkaan. Tämä saavuttamisen lisäämällä välimuistiin ruudun kyselytulokset, ja se toimii näin kunkin raporttinäkymän. Itse asiassa se tulee tehdä kullekin käyttäjälle, jolla on pääsy koontinäyttö, joka perustuu malleja, jotka vahvistavat dynaamista rivitason Suojausta.

Power BI-palvelu päivittää koontinäytön kyselyn välimuistien automaattisesti heti, kun Power BI-isännöityjä tuontimalleille päivitetään. LC ja DQ malleissa, jos tietojoukon omistaja on aste hallita sitä, kuinka usein Power BI-palvelu päivittää välimuistiin, joka voidaan määrittää usein kuin 15 minuutin välein tai harvoin kerran viikossa. Huomaa, että LC kyselyn välimuistipäivitysten ensin kyselyn määrittämään, onko mallin päivitys on tapahtunut viimeisen välimuistin päivityksen jälkeen, ja se jatkaa ei päivitä välimuisti, kun päivitystä ei ole esiintynyt koska metatietoja. Tämä tarkistus ei ole mahdollista DQ mallien ja niin välimuistipäivitysten tapahtuu onko lähdetiedot muutettu vai ei.

Koontinäytön kyselyn välimuistin päivittää perusteella DQ ja LC mallit voi vaikuttaa merkittävästi Power BI-palveluresursseja ja ulkoisiin tietolähteisiin. Harkitse koontinäytön 20 ruuduissa, Azure Analysis Services-mallin, joka pakottaa dynaamista rivitason Suojausta ja joka päivitetään tunnin välein ja että tämä koontinäyttö on jaettu 100 käyttäjää. Jos tietojoukko on määritetty päivittymään tunnin välein, tämä aiheuttaa vähintään 2000 (20 x 100) LC kyselyitä. Tämä saattaa sijoittaa valtava lataaminen Power BI-palvelussa ja ulkoisiin tietolähteisiin, ja se saattaa myös ylittää rajat käytettäville käytettävissä olevat resurssit. Kapasiteetin resursseja ja rajoitukset on kuvattu [kapasiteetin solmut](#capacity-nodes) aiheessa.

Käyttäjät voivat käyttää eri tavalla, jotka edellyttävät Power BI-palvelun resurssien koontinäytön. Tarkemmin sanottuna he voivat:

- Käynnistää koontinäyttöruutuja, mikä voi johtaa päivitystä, kaikki Power BI-isännöityjä tuonti tietomalleja
- Käytä Q & luonnollisen kielen ominaisuus kysymysten (tarjoaa koontinäyttöjen suunnitteluun sallii ja tietojoukko on Power BI-isännöityjä tuonti tietomallin tai LC tietojoukon määritetty Ota Q & A)
- Nopeat merkitykselliset tiedot-ominaisuus on Power BI käyttää löytää merkityksellisiä tietoja pohjana olevan tietojoukon ja vastata visualisointeja, jotka näyttävät ja niitä (tarjoten, että ruutu perustuu tietojoukko, joka on Power BI-isännöityjä tuonti tietomallia)
- Määritä hälytykset koontinäytön ruuduissa, että Power BI-palvelun vertailtavat arvot - ruudun mahdollisesti niin usein kuin käyttö - ja Ilmoita käyttäjille, kun raja on ylitetty raja-arvot (ruutu näyttää yhden numeerisen arvon ja perustuu tietojoukko, joka on Power BI-isännöityjä tuonti tietomallia)

### <a name="model-storage-modes"></a>Mallin tallennustilan tilat

Peruuta Power BI Desktop sallii kehittäminen mallia yhdessä kolme tilaa. On tärkeää ymmärtää kullekin tietojen mallin tallennustilan ja Power BI-palvelun resurssien vaikutukset perusteet. Tässä osiossa esitellään kaikki kolme tilaa. Nämä käsitellään tarkemmin tarkemmin myöhemmin tässä raportissa optimointi mallit-aiheessa.

#### <a name="import-mode"></a>Tuontitila

Tuontitila tukee yleisin kehittämään malleja vuoksi erittäin suorituskyvyn liittyvät muistissa kyseltäessä käytettävissä mallintajat, suunnittelu-joustavuutta ja tuki Power BI-palvelun ominaisuuksien (Q & A nopeat merkitykselliset tiedot jne.). Se on oletustila, kun luodaan uusi Power BI Desktop-ratkaisu.

On tärkeää ymmärtää, että tuotuja tietoja on aina tallennettu levylle ja on oltava täysin ladataan muistiin, joihin kysely tai päivittää. Kun muistiin tuontimalleille soveltuvasta blazingly nopea kysely. Myös on tärkeää ymmärtää, että ei ole käsite suureen osittain muistiin Tuo-malli.

Päivitetään, kun tiedot on pakattu optimoitu ja tallentaa sitten VertiPaq-säilömoduulissa levylle. Kun ladata levyltä muistiin, on mahdollista Nähdäksesi 10 x pakkaus ja ovat siis kohtuullisen odotettavissa, että lähdetiedot 10 Gigatavua voit pakata noin 1 gigatavun kokoiseksi. Tallennustilan koko levyn voi saavuttaa 20 prosenttia pienentäminen ylimpänä. \[[6](#endnote-06)\]

Rakenteen joustavuutta voidaan saavuttaa kolmella tavalla. Tietomallintajille tehdä seuraavaa:

- Integroida tietoja useista tietolähteistä - riippumatta siitä, tietolähteen tyyppi ja muodon tiedot välimuistiin mukaan
- Hyödynnä Power Query Formula Language-kielellä (epävirallisesti kutsutaan M) Funktiot koko joukon luotaessa valmistelu kyselyt
- Data Analysis Expressions (DAX)-Funktiot koko joukon hyödyntää, kun parantaminen mallin, jonka liiketoimintalogiikkaa, saavuttaa laskettuja sarakkeita, laskettuja taulukoita ja mittayksiköt

Seuraavassa kuvassa esitetyllä tuo mallin voit integroida tietoja tuetuista tietolähdetyypeistä minkä tahansa määrän.

![Tuo mallin voit integroida tietoja tuetuista tietolähdetyypeistä minkä tahansa määrän](media/whitepaper-premium-deployment/import-model.png)

Kun tuontimalleille liittyvät vaikuttavia etuja, on kuitenkin haittaa liian:

- Koko malli on ladattava muistiin, ennen kuin Power BI voi tehdä kyselyn mallista, joka sijoittaa vähissä, käytettävissä olevat resurssit kun määrä ja koko mallien kasvavat
- Mallitiedot ovat vain uusimman päivityksen nykyisen ja niin tuontimalleille on päivitettävä, mieluiten aikataulun perusteella
- Täydellinen poistaa kaikki tiedot kaikista taulukoista ja ladata uudelleen tietolähteestä. Tämä voi olla erittäin kalliita aikaa ja resursseja Power BI-palvelun ja tietolähteet. Power BI on lisäävä päivitys, joka voit välttää katkaistaan ja lataaminen uudelleen kokonaisia taulukoita tuki ja tätä käsitellään [Optimizing Power BI-Hosted mallien](#optimizing-power-bi-hosted-models) aiheessa.

Näkökulmasta Power BI-palvelun resurssi tuontimalleille edellytä:

- Tarpeeksi muistia mallin lataaminen, kun se on kysely tai päivittää
- Käsittelyresursseja ja lisämuistia resurssit, jotta tietojen päivittäminen

#### <a name="directquery-mode"></a>DirectQuery-tilassa

Mallit DirectQuery (DQ) tila on kehitetty tuo tietoja. Sen sijaan ne sisältävät vain metatiedot, että kun kysely ongelmia alkuperäisten kyselyiden pohjana olevaan tietolähteeseen.

![DirectQuery-mallin myöntää alkuperäisiä kyselyitä taustatietolähteeseen](media/whitepaper-premium-deployment/direct-query-model.png)

On kaksi tärkeintä syytä ohjelmoida DQ-malli. Ensimmäinen syy on, kun tietomäärät on liian suuri - silloin, kun käytetään tietojen pienentäminen menetelmät - ladata malliin tai päivitä käytännössä. Toinen syy on, kun raportteja ja koontinäyttöjä tarvitsevat ”lähes reaaliaikaisesti” tietoja, mitä voit tehdä ajoitetun päivityksen rajoissa (48 kertaa päivässä varatun kapasiteetin).

On useita etuja, jotka liittyvät mallit DQ:

- Tuo mallin kokorajoitukset ei käytetä
- Malleja ei tarvitse päivitystä
- Raporttikäyttäjät näkevät uusimmat tiedot, kun raporttisuodattimia ja osittajia, käyttää ja päivittää koko raportin nykyisen tietojen noutamiseen
- Koontinäyttöruudut, kun DQ mallien perusteella voit päivittää automaattisesti yhtä usein kuin 15 minuutin välein

On kuitenkin useita haittaa ja DQ mallien liittyvät rajoitukset:

- Malliin perustuvat tuettua tietolähdettä ja minkä tahansa tietojen integroinnin on jo saavuttaa tietolähteen. Tuetut tietolähteet ovat relaatiotietokanta ja analyyttisten järjestelmien monta suosittuja myymälät tuki \[ [7](#endnote-07)\].
- Suorituskyky voi olla hidas, vaikutuksia mahdollisesti negatiivisesti (kyselyt voivat olla suorittimen paljon) Power BI-palveluun ja tietolähde (joka voi olla optimoimaton analyysikyselyjen)
- Power Query-kyselyitä ei voi olla liian monimutkainen ja rajoittuvat M-lausekkeissa ja toiminnot, jotka voidaan muuttuu tietolähteen ymmärtämällä kyselyt
- DAX-Funktiot ovat vain sellaisia, jotka voidaan muuttuu tietolähteen ymmärtämällä kyselyt ja ei tueta laskettuja taulukoita tai sisäistä aikatiedot ominaisuudet
- Oletusarvon mukaan mallin kyselyt edellyttävät yli miljoona riviä noutaminen ei onnistu
- Voit näyttää raportteja ja koontinäyttöjä, joissa on useita visualisointeja epäyhtenäisiä tuloksia, erityisesti silloin, kun tietolähde on muuttuva
- Q & A ja nopeita merkityksellisiä tietoja ei tueta

Näkökulmasta Power BI-palvelun resurssi edellyttävät DQ mallit:

- Lataa malli (vain metatiedot) mahdollisimman vähän muistia kun se lähetetään kysely
- Joskus merkittäviä suoritinresursseja ja käsitellä tietolähteeseen lähetetyt kyselyt

Lisätietoja saat viittaavat [käyttää suoran kyselyn Power BI Desktop-](desktop-use-directquery.md) tiedoston.

#### <a name="composite-mode"></a>Koosteen tila

Mallien Datasourcemodule-tilassa on kehitetty Salli määrittäminen yksittäiset taulukoiden tallentamista tilassa. Se tukee vuoksi erilaisten tuonti ja DQ taulukot. Se tukee myös laskettuja taulukoita (määritetty DAX-kielen) ja DQ tietolähteiden.

Taulukon tallennustilan voidaan määrittää tuonti, DirectQuery tai kaksois. Taulukko, joka on määritetty Dual tallennustila on sekä tuomista että Directquerya ja näin käytettävä kyselyä mukaan säännöllisesti tehokkain tapa selvittää Power BI-palvelussa.

![Koosteen malli on tuonti- ja DQ määritetty taulukon tasolla tallennustilan tiloja yhdistelmä](media/whitepaper-premium-deployment/composite-model.png)

Yhdistelmämallit pyrkimällä parhaita tuonti- ja DirectQuery-tiloille. Kun määritetty asianmukaisesti ne yhdistää suuren kyselyn suorituskyvyn muistissa mallien mahdollisuuden hakea lähellä reaaliaikaisia tietoja tietolähteestä.

Tietomallintajille, jotka kehittävät yhdistelmämallit todennäköisesti määrittää dimension tyyppi taulukoiden tuonti tai kaksois tallennustilan tila ja fakta-tyyppiä taulukoissa DirectQuery-tilassa. Otetaan esimerkiksi malli, joka sisältää tuote-taulukon dimensiotyypin kaksois-tilan ja fakta-tyypin taulukko DirectQuery-tilassa. Tuote-taulukko saattaa olla nopeasti ja tehokkaasti kysellyt muistissa hahmonnetaan raportin osittaja. Sales-taulukko sitten voi kysellä DirectQuery-tilassa, jotka on liitetty liittyvä tuote-taulukko. Jälkimmäisessä kysely saattaa antaa yksittäisen tehokkaita alkuperäisen kyselyn liittymään tuote- ja taulukot ja suodattaminen osittajan arvot muodostamisen.

Yleensä hyvät ja huonot, mallin kussakin tilassa liittyvät voidaan pitää käytettävä yhdistelmämallit taulukon tallennustilan tila.

Lisätietoja saat viittaavat [yhdistelmämallit käyttäminen Power BI Desktop](desktop-composite-models.md) tiedoston.

### <a name="licensing"></a>Käyttöoikeudet

Power BI on kolme käyttöoikeuksia:

- Power BI (maksuton)
- Power BI Pro
- Power BI Premium

**Power BI ilmainen** käyttöoikeuksien avulla yksityishenkilö toimivat sisällä oman työtilansa julkaisemalla malleja ja raportteja ja kirjaudu sisään Power BI-palveluun. On tärkeää ymmärtää, että se ei voi jakaa Power BI-sisältöä käyttämällä tämän käyttöoikeuden. Tämän käyttöoikeuden, koska sen nimi ilmaisee, on ilmainen.

**Power BI Pro** käyttöoikeuksien avulla yksityishenkilö luoda ja sovelluksen työtiloissa yhteistyötä ja jakaa ja jaella Power BI-sisällön. He myös määrittää niiden tietojoukkojen automaattisesti pitämään tiedot ajan tasalla, mukaan lukien paikallisen tietolähteistä päivitystä. Lisäksi he voivat Valvo ja hallinnoi kuinka käyttää ja käyttää. Tämä käyttöoikeus vaaditaan vastaanottamaan jaettua sisältöä muilta, ellei käyttäjä on liitetty järjestelmänvalvojalle Power BI Premium-kapasiteettiin.

**Power BI Premium** käyttöoikeus on vuokraajatason käyttöoikeus, ja se on kuvattu [esittelyssä Power BI Premium](#introducing-power-bi-premium) osiossa.

Lisätietoja saat Power BI-käyttöoikeuksista viittaavat [Power BI-hinnoittelu](https://powerbi.microsoft.com/pricing/) sivun.

## <a name="introducing-power-bi-premium"></a>Esittelyssä Power BI Premium

Power BI Premium tarjoaa yhdistetyn Omatoiminen ja enterprise BI ympäristössä asteikon, luotettavamman suorituskyvyn ja ennustettavan kustannuksia. Pääasiassa saavuttamisen tämä antamalla organisaatiosi Power BI-palvelun resursseille.

Lisäksi Power BI Premium tarjoaa monia enterprise-ominaisuudet:

- Kustannustehokkaita sisällön jakelu käyttöön rajoittamaton Power BI ilmaiskäyttäjät, mukaan lukien ulkoisten käyttäjien Power BI-sisällön jakaminen
- Tuki suurempi tietojoukkojen koon \[ [8](#endnote-08)\]
- Suurempi päivitystaajuutta dataflows ja tietojoukkoja (jopa 48 kertaa päivässä)
- Lisäävä päivitys dataflows ja tietojoukkoja
- Tietovirrassa linkitetyt entiteetit ja muunnokset rinnakkaissuorittamista
- Sivutetut raportit
- Power BI-raporttipalvelin on paikallinen raportointi-
- Mahdollisuus sisällön upottaminen sovelluksiin puolesta käyttäjät (PaaS)

Monet näistä ominaisuuksista voidaan hyödyntää tehokkaita ja skaalattavien enterprise-ratkaisuja ja on kuvattu [optimointi Premium-kapasiteetteja](#optimizing-premium-capacities) osiossa.

### <a name="subscriptions-and-licensing"></a>Tilaukset ja käyttöoikeudet

Power BI Premium on vuokraajatason Office 365: n tilaus saatavilla kaksi SKU (varastointiyksikkö) perheistä:

- **EM** (EM1 EM3) Varastointiyksiköt voit upottaa, jotka vaativat vuosittaista sitoutumista laskutetaan kuukausittain
- **P** varastointiyksiköitä (P1 – P3) embedding- ja enterprise-, kuukausittaista tai vuosittaista sitoutumista, jotka vaativat laskutetaan kuukausittain, ja asenna paikallinen Power BI Report Server-käyttöoikeus sisältää

Voit ostaa Azure Power BI Embedded tilaus, joka on yksi SKU-perhe on vaihtoehtoinen menetelmä: **A** Varastointiyksiköt (A1 – A6) upottaminen ja kapasiteetin vain testausta varten.

Ovat kaikki Varastointiyksiköt toimittaa v-ytimiä kapasiteettien luomiseen \[ [9](#endnote-09)\], mutta EM-Varastointiyksiköt on rajoitettu pienempi asteikon upottamista varten. Kun tämä julkaisu kohdistus on P-Varastointiyksiköt, paljon mitä käsitellään koskee myös myös A-Varastointiyksikköjä.

Toisin kuin Premium-tilauksen SKU-, Azure-Varastointiyksiköt eivät vaadi aika ei sitoutumista ja laskutetaan tunneittain. Ne toimittaa täysi joustavuus käyttöön skaalaus ylös, vieritettävä asteikon, keskeyttää, jatka ja poistaa.

Azure Power BI Embedded on pitkälti laajuuden Tässä raportissa, mutta se testaus lähestymistapoja aiheessa käsitellään käytännön ja talous-asetusta, Testaa ja mitata kuormituksille.

Lisätietoja saat tietoja Azure-Varastointiyksiköt viittaavat [Azure Power BI Embedded-ohjeet](/azure/power-bi-embedded/).

Power BI Premium-tilaukset on ostettu järjestelmänvalvojat Microsoft 365-hallintakeskuksessa. Tarkemmin sanottuna vain Office 365: n Yleiset Järjestelmänvalvojat ja laskutuksen järjestelmänvalvojat voivat ostaa Varastointiyksiköt.

Kun ostanut, vuokraajan vastaanottaa vastaavan määrän v-ytimiä kapasiteettien - määrittämään tätä kutsutaan **v-ytimien rajoittaminen**. Esimerkiksi P3 SKU: n ostaminen antaa vuokraajan käyttöön 32 v-ydintä.

Lisätietoja saat viittaavat [miten voit ostaa Power BI Premium](service-admin-premium-purchase.md) tiedoston.

### <a name="premium-capacities"></a>Premium-kapasiteetteja

Toisin kuin jossa työnkulut suoritetaan jaetuissa Laskennallisissa muiden asiakkaiden kanssa jaettuun kapasiteettiin **varattu kapasiteetti** on yksinoikeudella organisaatiossa. Sen eristetään varattua Laskennallisissa resursseja, jotka tasalaatuisen ja yhdenmukainen suorituskyky isännöity sisällölle.

Tässä raportissa kohdistus on **Premium-kapasiteettiin** , mikä tarkoittaa se liittyy EM tai P-Varastointiyksiköt.

#### <a name="capacity-nodes"></a>Kapasiteetin solmut

Kuvatulla tavalla tilauksia ja käyttöoikeuksien aiheen on kaksi Power BI Premium-SKU-perheissä: EM- ja s. Kaikki Power BI Premium-SKU ovat saatavilla kapasiteetin solmut edustavien tietyn määrän suorittimen, muistin ja tallennustilan resursseja. Sen lisäksi, että resurssit kunkin Varastointiyksikkö on toiminnalliset rajat DirectQuery (DQ) ja Live-yhteys (LC) yhteyksiä sekunnissa määrän ja parallel mallin määrä päivittää.

Käsittely on saavuttaa tietyn määrän v-ydintä, jakaa tasan taustapalvelu ja edustan välillä.

**Taustan v-ytimet** ovat vastuussa core Power BI-toimintoja, kuten kyselyn käsittelystä, välimuistin hallinnasta, R-palvelut, mallipäivityksen, luonnollisen kielen käsittelystä (Q & A) ja raporttien ja kuvien palvelinpuolen hahmontamisesta. Taustan v-ytimet on määritetty tietty määrä muistia, joka on ensisijainen käytettävä isännän malleja, joita käytetään myös nimitystä aktiivisia tietojoukkoja.

**Edustan v-ytimet** on vastuussa web verkkopalvelusta, koontinäytön ja raportin tiedostohallinnasta, käyttöoikeuksien hallinnasta, ajoituksista, API-liittymiä, lataa ja lataa ja yleisesti ottaen liittyvät käyttäjän käyttäjäkokemuksia varten.

Tallennustila on asetettu 100 TT: N kapasiteetin solmuun.

Resursseja ja rajoitukset kunkin Premium-varastointiyksikön (ja mukauttaa näin A-Varastointiyksikkö) on kuvattu seuraavassa taulukossa.

| Kapasiteetin solmut | V-ytimiä yhteensä | Taustan v-ytimet | RAM (GB) | Edustan v-ytimet | DQ/LC (sekunnissa) | Mallin uudelleen latauksen Parallellisointi |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0.5 | 2.5 | 0.5 | 3.75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7.5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| | | | | | | |

#### <a name="capacity-workloads"></a>Kapasiteetin kuormituksia

Kapasiteetin kuormituksia ovat käyttäjien palveluita. Oletusarvon mukaan Premium ja Azure-kapasiteetit tukevat vain tietojoukon kuormituksen, liittyvä käynnissä Power BI-kyselyt, jotka ei voi poistaa käytöstä.

Lisää kuormituksia voi ottaa käyttöön sivutetut raportit, dataflows ja Tekoäly. Lisää jokainen kuormitus edellyttää määrittäminen muistin enimmäismäärän (yhteensä muistia prosenttilukuna), jonka avulla voidaan kuormituksen mukaan.

#### <a name="how-capacities-function"></a>Miten kapasiteettien toimi

Power BI-palvelu pyrkii kapeammaksi kapasiteetin resurssien aikana ei ylitysten käytettäville kapasiteetin koko ajan.

Kapasiteetin toiminnot luokitellaan joko interactive tai tausta. Vuorovaikutteinen toimintoihin kuuluvat hahmontaminen pyynnöt ja niihin reagoiminen käyttäjän toimet (suodatusta, Q & A: n kyseltäessä jne.). Tuo mallin kyselyä on yleensä muistin paljon resursseja, suorittimen vaativia ollessa LC/DQ mallien kyselyiden tekemistä. Taustan toiminnot sisältävät tietovirrassa ja tuo mallin päivitykset ja koontinäytön kyselyn välimuistiin.

On tärkeää ymmärtää, että vuorovaikutteisia toimintoja ovat aina täytynyt priorisoida taustan toiminnot varmistaaksesi, parhaan mahdollisen kokemuksen käyttäjälle kautta. Jos resurssit eivät riitä, tausta toiminnot lisätään jonoon, kun Vapauta resursseja. Taustan toimintoja, kuten tietojoukkosi päivittyy ja AI-Funktiot, voi olla Keski prosessin Power BI-palvelu ja lisätään jonoon.

Tuontimalleille on oltava täysin ladataan muistiin, jotta he voivat tehdä kyselyitä tai päivittää. Power BI-palvelun hallitsee muistin käytön avulla kehittyneitä algoritmeja varmistamiseksi käytettävissä olevan muistin ja saavuttaa overcommitting kapasiteetti: Kun se on mahdollista, että kapasiteetti tallentamiseen monta tuonti mallien (enintään 100 TT: N Premium-kapasiteettia kohti), kun niiden yhdistetyn levytallennustilaa ylittää tuetut muistia (ja lisämuistia tarvitaan kysely-ja päivitys), sitten ne kaikki voi ladata muistiin samalla kertaa.

Tuontimalleille on tämän vuoksi ladataan - ja poistaa - muistin käytön mukaan. Tuonti-malli on ladattu, kun se on kysellyt (vuorovaikutteinen toiminto) ja vielä muistissa tai kun se on päivitettävä (tausta-toiminto).

Mallin muistista poistamista kutsutaan **häätäminen** , ja se on toiminnon, jota Power BI voidaan suorittaa nopeasti mallit koosta riippuen. Jos kapasiteetti on ei mitään muisti on vähissä, mallit yksinkertaisesti ladataan muistiin ja pysyvät olemassa. \[[10](#endnote-10) \] , kun muisti ei riitä lataa mallia, Power BI-palvelun täytyy ensin Vapauta muistia. Se vapauttaa muistia mukaan tunnistetaan malleilla, jotka on poistuvan pyrkimällä malleja, joita ei ole käytetty viimeisten kolmen minuutin \[ [11](#endnote-11)\], ja häätäen samalla ne. Jos ei malleja ei ole passiivinen häätämään, Power BI-palvelun pyritään mallit ladata taustan toimintoja. Tämä saattaa sisältää taustan kuormituksia, kuten AI kuormituksen häätäminen. Auta 30 sekunnin jälkeen epäonnistuneiden yritysten määrä \[ [11](#endnote-11)\], on vuorovaikutteinen toiminto epäonnistuu. Raportin käyttäjälle ilmoitetaan tällöin Upeasti syyn ehdotuksen yritä uudelleen myöhemmin.

On tärkeää kuormituksen tietojoukon häätäminen on tavallinen ja odotettua toimintaa. Se pyrkii Suurenna muistinkäyttö lataamista ja purkaminen malleja, joiden yhdistetyn koot voi ylittää käytettävissä olevan muistin mukaan. Tämä on tarkoituksellista, ja täysin läpinäkyvä raportin käyttäjille. Suuren häätäminen hinnat ei välttämättä tarkoita kapasiteetin riittämättömästi niille. Ne kuitenkin tulla huolenaiheesta Jos kysely tai päivitys reagoinnin kärsimystä suuren häätäminen hinnat vuoksi.

Tuontimalleille päivitykset ovat aina vaatii paljon muistia, kuten mallit on ladattava muistiin ja lisämuistia tarvitaan käsittelyä varten. Täydellinen käyttää noin kaksinkertaisesti sen määrän muistia mallin vaatima. Näin varmistetaan, että mallin voi tehdä kyselyitä, myös silloin, kun käsitellään (kyselyt lähetetään aiemmin luotua mallia, ennen kuin päivitys on valmis, ja uudet Mallitiedot ovat käytettävissä). Huomaa, että lisäävä päivitys edellyttää vähemmän muistia onnistunut nopeammin ja niin huomattavasti pienentää kapasiteettia resursseille vähissä. Päivitykset voidaan myös suorittimen vaativia malleille, varsinkin monimutkaisia Power Query-muunnoksia tai lasketut taulukot tai sarakkeet, jotka ovat monimutkaisia tai suuren taulukoiden perusteella.

Päivitykset - kyselyt – kuten edellyttävät, että mallin ladataan muistiin. Jos muisti ei riitä, Power BI-palvelu yrittää passiivinen mallit, ja jos tämä ei ole mahdollista (kaikki mallit ovat aktiivisia), päivitystyön jonoon. Päivitykset ovat yleensä suorittimen paljon enemmän näin kuin kyselyitä. Tästä syystä on kapasiteettirajat samanaikaisten päivitykset, määritä taustan v-ydintä, pyöristettynä määrä 1,5 kertaa määrän. Jos on liian monta samanaikaista päivitykset, ajoitettu päivitys asetetaan jonoon. Kun nämä tilanteissa, kestää kauemmin päivityksen päättymistä. Huomautus-demand-päivitykset (aina käyttäjän pyynnöstä tai API-kutsu) yrittää kolme kertaa \[ [11](#endnote-11)\], ja sitten epäonnistua, jos on edelleen resurssit eivät riitä.

## <a name="managing-power-bi-premium"></a>Power BI Premium-hallinta

Power BI Premium hallintaan sisältyy ostamisesta tilaukset, ja luodaan, hallintaan ja valvontaan Premium-kapasiteetteja.

### <a name="creating-and-managing-capacities"></a>Luomisesta ja hallitsemisesta kapasiteetit

**Kapasiteettiasetukset** sivulle **Power BI-järjestelmänvalvojan** Portal näyttää ostanut v-ytimien määrä ja käytettävissä (eli vielä liitetään kapasiteettiin) ja Premium-kapasiteetteja. Sivun järjestelmänvalvojat Office 365: n Yleiset Järjestelmänvalvojat tai Power BI-palvelun avulla voit luoda Premium-kapasiteetteja käytettävissä olevat v-ytimet ja muokata aiemmin Premium-kapasiteetteja.

Kun luot Premium-kapasiteettiin, edellyttää, että järjestelmänvalvoja määrittämään:

- Kapasiteetin nimi (yksilöiviä vuokraajassa)
- Kapasiteetin admin(s)
- Kapasiteetin koko
- Tietojen tallennusta Saksassa vaatimukset alue \[ [12](#endnote-12)\]

Vähintään yksi kapasiteetin järjestelmänvalvojan on määritettävä. Kapasiteetin järjestelmänvalvojat määrittää käyttäjät voivat:

- Määritä työtilat kapasiteettiin
- Hallitse käyttöoikeuksia, voit lisätä muita kapasiteetin Järjestelmänvalvojat tai käyttäjät, joilla on määrityskäyttöoikeudet (jotta ne voivat määrittää työtiloja kapasiteettiin)
- Hallintaan, määrittämään sivutetut raportit ja dataflows kuormituksia muistinkäyttö
- Käynnistä kapasiteetti, jos haluat palauttaa kaikki toiminnot, jos kyseessä on järjestelmän ylikuormitusta \[ [13](#endnote-13)\]

Kapasiteetin järjestelmänvalvojat ei voi käyttää työtilan sisältö (paitsi eksplisiittisesti varattu työtilan käyttöoikeudet) ja niillä ei ole käyttöoikeuksia Power BI-järjestelmänvalvojien kaikkiin alueisiin (paitsi eksplisiittisesti varattu) kuten käyttötilastoihin, Valvontalokeihin tai vuokraaja-asetukset. Ennen kaikkea kapasiteetin järjestelmänvalvojilla ei ole oikeuksia luoda uusien kapasiteettien tai Skaalaa aiemmin kapasiteettien. Lisäksi ne on määritetty perustaksi kapasiteetin-, varmistaa, että he voivat vain tarkastella ja hallita kapasiteetit, joihin ne on varattu.

Kapasiteetin koko on valittava käytettävissä luettelosta SKU-vaihtoehtojen joka on käytettävissäsi v-ytimiä varannossa määrän mukaan. On mahdollista luoda useita kapasiteettien varannosta, joka saattaa vakioentiteeteille yhdestä tai Lisää ostanut Varastointiyksiköt. Esimerkiksi P3-Varastointiyksikkö (32 v-ydintä) avulla voi luoda kolmen kapasiteettien: yksi P2 (16 v-ydintä) ja kaksi P1 (2 x 8 v-ydintä). Parannettu suorituskyvyn ja mittakaavan voidaan saavuttaa luomalla pienempi suuriin kapasiteettien ja tässä aiheessa käsitellään [optimointi Premium-kapasiteetteja](#optimizing-premium-capacities) osiossa. Seuraavassa kuvassa on esimerkki-asennusohjelma kuvitteellisia Contoso organisaation viisi Premium-kapasiteetteja muodostuu (3 x P1 ja 2 x P3) sisältävän kunkin sovelluksen työtilat ja useita työtiloja jaettuun kapasiteettiin.

![Esimerkki-asetukset-kuvitteellisia Contoso-organisaatio](media/whitepaper-premium-deployment/contoso-organization-example.png)

Premium-kapasiteettiin määrittää, että alue kuin Power BI-vuokraajan järjestelmänvalvojan ohjausobjektin päällä mitä palvelinkeskuksiin (sisällä määritettyä maantieteellisellä alueella) Power BI-sisältöä sijaitsee tarjoaa kotialueella. \[[12](#endnote-12)\]

Power BI-palvelun Järjestelmänvalvojat ja Office 365: n Yleiset järjestelmänvalvojat voivat muokata Premium-kapasiteetteja. Tarkemmin sanottuna he voivat:

- Muuta kapasiteetin kokoa, Skaalaa ylös tai Skaalaa alaspäin resursseja. Kuitenkin ei voi heikentää EM SKU: hun P-Varastointiyksikköä tai päivitä päin vastoin.
- Lisää tai poista kapasiteetin Järjestelmänvalvojat
- Lisää tai poista käyttäjät, joilla on määrityskäyttöoikeudet
- Lisää tai poista muut työnkulut
- Muuta alueet

Määrittämisen käyttöoikeudet vaaditaan työtila tietyn Premium-kapasiteettiin. Käyttöoikeuksia voidaan myöntää koko organisaatiolle, tietyille käyttäjille tai ryhmille.

Oletusarvon mukaan Premium-kapasiteetteja tue kuormituksia liittyvät suoritettaessa Power BI-kyselyjä. Se tukee myös kolme muita kuormituksia: **Sivutetut raportit**, **Dataflows**, ja **AI**. Jokainen kuormitus edellyttää määrittäminen muistin enimmäismäärän (yhteensä muistia prosenttilukuna), jonka avulla voidaan kuormituksen mukaan. On tärkeää ymmärtää, että kasvattamista enimmäismuisti estetään voi vaikuttaa active malleja, joita voidaan isännöidä määrä ja päivitykset siirtomäärän.

Muistin kohdistetaan tietovoille dynaamisesti, mutta sivutetuille raporteille staattisesti. Lisämuistin staattisesti muistin enimmäismäärän johtuu sivutetut raportit toimivat kapasiteetin suojatun contained välilyönti. Huolehdittava Kun asetus Sivutettujen raporttien muistin, kun muistia lataamiseen malleja.

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| Sivutetut raportit | – | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| Tietovuot | Oletus 20 %, vähintään 8 %  | Oletus 20 %, vähintään 4 %  | Oletus 20 %, vähintään 2 % | Oletus 20 %, vähintään 1 %  |
| AI | – | 20 prosenttia oletus; Pienin 20 prosenttia  | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 %  |
| | | | | |

Poistetaan Premium-kapasiteettia on mahdollista, ja sen työtilat ja sisällön poistaminen ei tuota. Sen sijaan se siirtyy määritetyt työtilat jaettuun kapasiteettiin. Luotaessa Premium-kapasiteettiin eri alueella, työtilan siirretään jaettuun kapasiteettiin poikkeavalla alueella.

### <a name="assigning-workspaces-to-capacities"></a>Työtilojen määrittäminen kapasiteetit

Työtilat voidaan määrittää Premium-kapasiteettiin **Power BI-järjestelmänvalvojan** **Portal** tai - sovelluksen työtilassa – tässä **työtilan** ruudussa.

Kapasiteetin järjestelmänvalvojat sekä Office 365: n Yleiset Järjestelmänvalvojat tai Power BI-palvelun järjestelmänvalvojat voivat joukkomäärittää työtiloja- **Power BI-järjestelmänvalvojan** **Portal**. Määritetty Bulk käyttää:

- **Työtilat käyttäjien mukaan** : Kaikki kyseisten käyttäjien, mukaan lukien Omat työtilat omistamat työtilat määritetään Premium-kapasiteettiin. Tämä sisältää työtilat uudelleen määrityksen, kun ne on jo määritetty eri Premium-kapasiteettiin. Lisäksi käyttäjät määritetään myös työtilan määrittämisen käyttöoikeudet.

- **Määritetyt työtilat**
- **Koko organisaation työtilat** : Kaikki työtilat, mukaan lukien Omat työtilat määritetään Premium-kapasiteettiin. Lisäksi kaikki nykyiset ja tulevat käyttäjät määritetään työtilan määrittämisen käyttöoikeudet. \[[14](#endnote-14)\]

Työtila voidaan lisätä Premium-kapasiteetin avulla **työtilan** tarjoten käyttäjä on sekä työtilan järjestelmänvalvoja ja on määrittämisen käyttöoikeudet.

![Työtila Premium-kapasiteettiin työtila-ruudussa avulla](media/whitepaper-premium-deployment/assign-workspace-capacity.png)

Työtilan järjestelmänvalvojat voivat poistaa työtilan-kapasiteetti (Voit jaettuun kapasiteettiin) edellyttämättä määrittämisen käyttöoikeus. Työtilan työtilat poistamista varattua kapasiteettia tehokkaasti uudelleensijoittaa jaettuun kapasiteettiin. Huomaa, että poistaminen työtilan Premium-kapasiteettiin voi olla negatiivisia vaikutuksia tuloksena, esimerkiksi jaettua sisältöä muodostumassa ole käytettävissä Power BI ilmainen käyttöoikeus käyttäjät tai ajoitetun päivityksen peruuttamisesta, kun ne ylittävät tueta korvauksia jaettu kapasiteettien käytössä.

Power BI-palvelussa määritetty Premium-kapasiteettiin työtila tunnistetaan helposti avulla vinoneliökuvakkeen, adorns työtilan nimi.

![Tunnistetaan määritetty Premium-kapasiteettiin työtila](media/whitepaper-premium-deployment/premium-diamond-icon.png)

### <a name="monitoring-capacities"></a>Valvonnan kapasiteetit

Premium-kapasiteetteja valvonta tarjoaa Järjestelmänvalvojat, joilla on käsitys siitä, miten kapasiteetit toimivat. Kapasiteettien voidaan valvoa käyttämällä [Power BI Premium-kapasiteetin Mittaustietoihin sovelluksen](service-admin-premium-monitor-capacity.md) tai [Power BI-hallintaportaalissa](service-admin-premium-monitor-portal.md).

#### <a name="interpreting-metrics"></a>Tulkitseminen mittarit

Resurssin käyttö ja kuormituksen toimintaa alkuperäiset käsitys muodostaa olisi seurattava mittareita. Jos kapasiteetin hidas, on tärkeää ymmärtää, mitä mittareita, jotta voit valvoa ja päätelmien voit tehdä.

Ihannetapauksessa kyselyt suoritetaan tarjoavat reagoiva kokemuksia raporttikäyttäjät tai uudempi kyselyn siirtomäärän ottaminen käyttöön sekunnin kuluessa. Se on yleensä vähemmän huolta – mukaan lukien päivitykset - taustan prosessit kestää kauemmin kertaa suorittamiseen.

Yleensä hidas raportit voivat olla osoitus ylikulutusta lämmitys kapasiteetti. Kun raporttien lataaminen epäonnistuu, tämä on perusteettomasti lämmitettävä kapasiteetin osoittaa. Kummassakin tapauksessa sen voitu johtuvat monien tekijöiden mukaan:

- **Epäonnistuneiden kyselyiden** ilmaista erottuu muisti on vähissä, ja että mallia ei voitu ladata muistiin. Power BI-palvelu yrittää ladata mallin 30 sekuntia ennen epäonnistumista.

- **Liiallisen kyselyn Odota kertaa** voi aiheutua useista syistä:
  - Täytyy ensin Power BI-palvelun evict mallit ja lataa sitten to-be-kysely-malli (peruuttaminen että uudempi tietojoukon häätäminen hinnaston mukaisesti yksin eivät ole kapasiteetin ruuhkautuminen osoittaa pitkä kyselyn Odota kertaa, jotka osoittavat muistin tietojen poistaminen ei liity)
  - Mallin lataaminen aikakatkaistaan (erityisesti suurten mallin lataaminen muistiin Odota)
  - Pitkäkestoinen kyselyt
  - Liian monta LC\DQ yhteyttä (kapasiteetin ylitysten)
  - Suorittimen kylläisyys
  - Monimutkainen raportti suunnitteluista ja visualisointien liikaa sivulla (peruuttaminen, että jokainen visualisointi on kysely)
- **Pitkän kyselyn keston** voivat ilmaista, että mallin rakenteet ovat ei ole optimoitu, erityisesti silloin, kun useita tietojoukkoja ovat aktiivisia kapasiteettia ja vain yksi tietojoukko on tekemiseen kyselyn keston. Tämä ilmaisee, että kapasiteetti on riittävän niille ja kysymys-tietojoukko on optimaalisen tai vain hidas. Pitkään suoritettavat kyselyt voivat olla ongelmallinen, kuin ne estä pääsy resursseihin muut prosessit.
- **Pitkä päivitystä odottaa kertaa tai AI-kutsun odottaa kertaa** ilmaista vuoksi useita active mallien muistia ei ole tarpeeksi muistia tai että ongelmallinen päivityksen estää muita päivittää (yli parallel päivityksen rajoitukset).

Mittarit käyttäminen tarkempi kuvaus on kuvattu seuraavaksi [optimointi Premium-kapasiteetteja](#optimizing-premium-capacities) osiossa.

## <a name="optimizing-premium-capacities"></a>Premium-kapasiteetteja optimointi

Premium-kapasiteetin suorituskykyongelmia ilmenee, kun common ensimmäinen tapa on optimoida tai Katso jo otettu käyttöön ratkaisut palauttaa hyväksyttävät vasteaika. Ohittava perusteet on aina Premium lisäkapasiteetin ostamisesta, ellei voida osoittaa.

Lisää Premium-kapasiteettia on pakollinen, kun on kaksi vaihtoehtoa, jossa käsitellään myöhemmin tässä osiossa:

- Skaalauksen Premium-kapasiteetti
- Lisää uusi Premium-kapasiteetti

Lopuksi lähestymistapoja ja Premium-kapasiteetin koon muuttaminen tekee tämän osion.

### <a name="general-best-practices"></a>Yleinen parhaat käytännöt

Kun oppimisen saavuttaa parhaiten käyttö ja suorituskyky on on muutamia parhaita käytäntöjä, joita voidaan käyttää aluksella kuin yleisiä suosituksia. Näitä ovat esimerkiksi seuraavat:

- Sovelluksen työtilat-yhteydellä Omat työtilat
- Erottamassa liiketoiminnan kannalta tärkeä ja Omatoiminen BI (SSBI) tietoja eri kapasiteetit

  ![Erottamassa liiketoiminnan kannalta tärkeä ja Omatoiminen BI tietoja eri kapasiteetit](media/whitepaper-premium-deployment/separate-capacities.png)

- Jos jaat sisältöä vain Power BI Pro-käyttäjien kanssa, ei tarvitse varattua kapasiteettia sisällön tallentamista voi olla
- Käytä varattua kapasiteettia, kun saavuttaa tietyn päivityksen aika tai kun tiettyjä ominaisuuksia on pakollinen, esimerkiksi suuria tietojoukkoja tai sivutettu reporting

### <a name="addressing-common-questions"></a>Lähestymistavat yleisiin kysymyksiin

Power BI Premium-käyttöönottojen optimointi on monimutkainen aihe, joissa käsityksen, kuormituksen vaatimukset, käytettävissä olevat resurssit ja niiden käytössä käyttö.

Tässä ohjeaiheessa käsitellään seitsemän tukikysymyksiin, joka kuvaa mahdolliset ongelmat ja niiden selitykset ja lisätietoja siitä, miten ja ratkaise ne.

#### <a name="why-is-the-capacity-slow-and-what-can-i-do"></a>Miksi hidas kapasiteetti on ja mitä voin tehdä?

On useita syitä, jotka voivat osallistua hidas Premium-kapasiteettiin. Tähän kysymykseen tarvitaan edelleen tietoja ymmärtää, mitä tarkoitetaan hidas. Raporteista hidas lataaminen Tai ne epäonnistuvat lataaminen? Ovat raportin visualisointien lataaminen tai päivittää, kun käyttäjä käyttää raportin hitaasti? Päivitykset kestää kauemmin kuin odotettiin tai aiemmin ilmeni?

On saanut käsityksen, syy, voit alkaa tutkimaan asiaa. Seuraavien kuusi kysymysten vastaukset auttavat osoite Lisää ongelmista.

#### <a name="what-content-is-using-up-my-capacity"></a>Skaalautuuko käyttää sisältöä?

Voit määrittää **Power BI Premium-kapasiteetin Mittaustietoihin** sovelluksen kapasiteetin suodattaminen ja tarkista työtilan sisältö suoritusmittaukset. On mahdollista Tarkista suorituskyvyn mittarit ja resurssin käyttö viimeisten seitsemän päivän ajalta Premium-kapasiteettiin tallennetut kaikki sisältö tunnin mukaan. Tämä on usein ensimmäinen vaihe suoritetaan, kun vianmääritys Yleiset huolta tietoja Premium-kapasiteetin suorituskyvystä.

Avainmittarit valvomaan ovat seuraavat:

- Suorittimen keskiarvo ja suuren käyttöaste määrä
- Keskimääräinen muistin ja suuren käyttöaste määrä ja muistinkäyttö tiettyyn tietojoukkoja, dataflows ja sivutetut raportit
- Ne ladataan muistiin aktiivisia tietojoukkoja
- Keskiarvo- ja kyselyn kestoja
- Kyselyiden keskimääräinen odotusaika kertaa
- Keskimääräinen tietojoukon ja tietovirrassa Päivitä kertaa
- Keskimääräinen AI kutsua kertaa ja odota kertaa

Lisäksi Power BI Premium kapasiteetin mittareita sovelluksen aktiivisen muistin näyttää raportin, joka ei voi poistaa, koska se on käytössä viimeisten kolmen minuutin muistin kokonaismäärä. -Päivitys odotusaika suuren piikin voitu Korreloidun suuri ja/tai active tietojoukon kanssa.

”Top 5 mukaan keskimääräinen kesto”-kaavio korostaa viisi parasta tietojoukkoja, sivutetut raportit, dataflows ja Tekoäly kutsujen kapasiteetin resursseja. Sisällön parhaat viisi luettelot ovat ehdokkaiden tutkimisessa ja mahdollinen optimointi.

#### <a name="why-are-reports-slow"></a>Miksi raportteja hidastaa?

Seuraavissa taulukoissa on mahdollista ongelmia ja tavalla ja käsitellä niitä.

##### <a name="insufficient-capacity-resources"></a>Kapasiteetti ei riitä resurssit

| Mahdollisia syitä | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Suuren active muisti (mallia ei voi poistaa koska se on käytössä viimeisten kolmen minuutin)<br><br> Useita suuren piikkarit kyselyn Odota kertaa<br><br> Useita suuren piikkarit-Odota päivitysajat | Valvoa muistin mittareita \[ [18](#endnote-18)\], ja häätäminen määrät \[ [19](#endnote-19)\] | Pienennä mallin kokoa tai DirectQuery-tilaan – Näytä [optimointi mallien](#optimizing-models) tämän osion aiheessa<br><br> Skaalauksen kapasiteetti<br><br> Määritä sisällön eri kapasiteettiin |

##### <a name="inefficient-report-designs"></a>Tehottomia raportin malleja

| Mahdollisia syitä | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Raporttisivujen sisältää useita visualisointeja (vuorovaikutteinen suodatus voi käynnistää vähintään yhden kyselyn per visualisointi)<br><br> Visualisointien noutaa enemmän tietoja kuin on tarpeen | Tarkista raportin malleja<br><br> Haastattelun raporttikäyttäjät ymmärtää, miten ne käsitellä raportteja<br><br> Valvoa tietojoukon kyselyn mittareita \[ [20](#endnote-20)\] | Uudelleensuunnittelua raportteja, joissa on vähemmän visualisointien sivua kohden |

##### <a name="dataset-slow-especially-when-reports-have-previously-performed-well"></a>Tietojoukon hidastaa (etenkin kun raportit olet aiemmin suorittanut hyvin)

| Mahdollisia syitä | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Tuontitiedot yhä suuria määriä<br><br> Monimutkaisia tai tehottomia laskutoimituksen logiikka, mukaan lukien rivitason suojauksen roolit<br><br> Mallia ei ole täysin optimoitu<br><br> (DQ-LC) Yhdyskäytävän viive<br><br> Hidas DQ tietolähteen kyselyn vasteaika on | Tarkista mallin malleja<br><br> Valvo yhdyskäytävän suorituskykylaskurit | Katso [optimointi mallien](#optimizing-models) tämän osion aiheessa |

##### <a name="high-concurrent-report-usage"></a>Suuren samanaikaisten raportin käyttö

| Mahdollisia syitä | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Suuren kyselyn Odota kertaa<br><br> Suorittimen kylläisyys<br><br> Ylitti DQ/LC yhteyden rajoitukset | Valvo suorittimen käyttöaste \[ [21](#endnote-21)\], kyselyn Odota kertaa ja DQ/LC käyttöä \[ [22](#endnote-22) \] mittareita + kyselyn keston – Jos vaihteleva luku on mahdollista ilmoittavat ongelmista samanaikaisuuden | Kapasiteetin skaalauksen tai määrittää sisällön eri kapasiteettiin<br><br> Uudelleensuunnittelua raportteja, joissa on vähemmän visualisointien sivua kohden |

#### <a name="why-are-reports-not-loading"></a>Miksi raportteja ei ladata?

Kun raportit eivät voi ladata sen on huonointa mahdollista tilannetta skenaarion ja että Kirjaudu kapasiteetin muisti ei riitä ja on perusteettomasti lämmitettävä. Näin voi käydä, kun kaikki ladata mallit ovat aktiivisesti tehdään kyselyjä samalla, ja sitä ei voi poistaa, ja kaikki päivitystoiminnot on keskeytetty tai Viivästetty. Power BI-palvelu yrittää ladata tietojoukko 30 sekuntia, ja käyttäjälle ilmoitetaan Upeasti syyn ehdotuksen yritä uudelleen myöhemmin.

Ei tällä hetkellä ei ole mittausarvo valvomaan raportin ladataan virheitä. Voit tunnistaa tämän ongelman mahdollisesta valvonta järjestelmämuistin, erityisesti suurin käyttö ja suurin käytön aika. Suuren tietojoukon häätöjä ja pitkä tietojoukon päivityksen keskimääräinen odotusaika voitu ehdottaa, että tämä ongelma on käynnissä.

Tässä tapauksessa vain hyvin toisinaan tämä ole voidaan pitää prioriteetti on ongelma. Raporttikäyttäjät ilmoitetaan, että palvelu on varattu ja että ne yritä uudelleen hetken kuluttua. Tässä tapauksessa liian usein ongelma voidaan ratkaista skaalaus ylös Premium-kapasiteettiin tai määrittämällä sisällön eri kapasiteettiin.

Kapasiteetin järjestelmänvalvojat (ja Power BI-palvelun järjestelmänvalvojat) voit valvoa **kysely epäonnistuu** mittausarvoa, jotta voit määrittää, kun näin tapahtuu. Ne uudelleen myös kapasiteetin palautetaan kaikki toiminnot, jos kyseessä on järjestelmän ylikuormitusta.

#### <a name="why-are-refreshes-not-starting-on-schedule"></a>Miksi ovat uudelleen lataukset ei käynnisty aikataulun?

Käynnistä päivitysaikoina taata. Peruuttaminen, Power BI-palvelun priorisoi aina vuorovaikutteisia toimintoja taustan toiminnot kautta. Päivitys on tausta-toiminto, joka voi tapahtua, kun kaksi ehdot täyttyvät:

- Ei tarpeeksi muistia
- Premium-kapasiteetin tueta Samanaikaisten päivitysten määrä ylittyy

Edellytykset eivät täyty, kun päivitys on jonossa, kunnes ehdot ovat hyviä.

Koko päivitystä Peruuta vähintään kaksinkertainen nykyisen tietojoukon muistikoko vaaditaan. Jos tarpeeksi muistia ei ole käytettävissä, päivitystä ei voi aloittaa, kunnes malli häätäminen vapauttaa muistia – Tämä tarkoittaa viiveitä, ennen kuin yksi tai useampi tietojoukko poistuu käytöstä ja voi poistaa.

Peruuta että suurin samanaikaisten päivitysten tuettu määrä on asetettu 1,5 kertaa taustan v-ytimet, pyöristää ylöspäin.

Ajoitettu päivitys epäonnistuu, kun se ei voi aloittaa, ennen kuin seuraava ajoitettu päivitys on aloittaa. Päivitystä käynnistämä manuaalisesti Käyttöliittymän yrittää suorittaa enintään kolme kertaa ennen epäonnistumista.

Kapasiteetin järjestelmänvalvojat (ja Power BI-palvelun järjestelmänvalvojat) voit valvoa **keskimääräinen Päivitä odotusaika (minuuttia)** mittausarvo määrittämään keskimääräinen lag ajoitettu aika – toimintoa alku.

Kun ei yleensä järjestelmänvalvojan prioriteetti muiden ajallaan tiedot päivitetään, varmista, että tarpeeksi muistia on käytettävissä. Tämä saattaa liittyä eristämällä tunnetut tarpeeksi resursseja kuvastaa kapasiteettien tietojoukkoja. On myös mahdollista järjestelmänvalvojat voitu coordinate tietojoukon omistajien lomittaa tai Pienennä ajoitettu päivitysajat minimoimaan rajuille auttamaan. Huomaa, että ei ole mahdollista, jolla järjestelmänvalvoja voi tarkastella päivityksen jono tai noutaa tietojoukon ajoittaa.

#### <a name="why-are-refreshes-slow"></a>Miksi hidas päivitykset?

Päivitykset voivat olla hidas - tai vuoksi olla hidas (edellisen kysymyksen common osoitteita).

Kun päivitys on itse asiassa hidas, se johtua useista syistä:

- Riittämätön suorittimen (päivitys voi olla suorittimen paljon)
- Muisti ei riitä, tuloksena päivitys keskeytetään (joka edellyttää, että päivitys on aloittaa alusta milloin ehdot ovat hyviä aloittaa uudelleen)
- Muut kapasiteetin syistä, kuten tietojen lähde järjestelmän reagoinnin, verkkoviive, virheelliset oikeudet tai yhdyskäytävän siirtomäärän
- Tietojen määrä - hyvä syy, jotta voit määrittää lisäävän päivityksen, käsitellään tarkemmin alla

Kapasiteetin järjestelmänvalvojat (ja Power BI-palvelun järjestelmänvalvojat) voit valvoa **keskimääräinen Päivitä kesto (minuuttia)** mittausarvo määrittämään ajan kuluessa, benchmark vertailun ja **keskimääräinen Päivitä odotusaika (minuuttia)** mittareita, jotta voit määrittää keskimääräinen lag välillä keskimääräinen lag ajoitettu aika – toimintoa alku.

Lisäävä päivitys huomattavasti pienentää tietojen päivityksen kesto erityisesti suuria taulukot. On neljä etuja, jotka liittyvät lisäävä päivitys:

- **Päivitykset ovat entistä nopeampia** : Vain alijoukon taulukon on oltava lastaus, vähentämään suorittimen ja muistin käyttö ja rinnakkaisuutta voi olla suurempi, useita osioita päivittämisen yhteydessä
- **Päivitykset suoritetaan vain, kun vaaditaan** : Lisäävän päivityksen käytännöt voidaan määrittää vain, kun tiedot ovat muuttuneet lataaminen
- **Päivitykset ovat entistä luotettavampia** : Lyhyempi käynnissä yhteyksiä muuttuvia tietojen lähdejärjestelmiin ovat pienempi on katkennut
- **Mallien pysyvät leikkauksen** : Lisäävän päivityksen käytännöt voidaan määrittää Poista automaattisesti asettamiesi siirtyvän ikkuna ajan historia

Lisätietoja saat viittaavat [lisäävä päivitys on Power BI Premium](service-premium-incremental-refresh.md) tiedoston.

#### <a name="why-are-data-refreshes-not-completing"></a>Miksi tietoja päivitetään ei onnistu?

Kun tietojen päivittäminen aloittamista, mutta se ei pysty suorittamaan, se johtua useista syistä:

- Muisti ei riitä, vaikka vain yhtä mallia Premium-kapasiteetissa eli mallin koko on erittäin
- Muut kapasiteetin syistä, kuten tietojen lähde järjestelmän on katkennut, virheelliset oikeudet tai yhdyskäytävän virhe

Kapasiteetin järjestelmänvalvojat (ja Power BI-palvelun järjestelmänvalvojat) voit valvoa **Päivitä virheitä vastaanottaja muisti ei riitä** mittausarvo.

#### <a name="why-are-ai-calls-failing"></a>Miksi AI kutsujen voi?

AI kutsujen saattaa epäonnistua useista syistä. Muistin vähimmäismäärää vaaditaan AI Aloita kuormitus on 5 gt, mutta tämä ei välttämättä riitä syötteen jotkin tietojoukot. Esimerkiksi automatisoituja koneoppimisen mallin Harjoitus edellyttää vähintään kaksi kertaa, ja joskus useita kertoja syötteen tietojoukon kokoa. Lisäksi AI-kutsun lopetetaan, jos kestää kauemmin kuin kaksi tuntia. Automaattinen tietokoneen oppiminen mallin koulutus kutsuja, et suorita kaikkia kahden tunnin aikana näiden kahden tunnin aikana löytyi paras mallin palautetaan.  AI kutsujen voi keskeyttää myös vuorovaikutteisia pyynnöt, jotka ovat etusijalla.

Järjestelmänvalvojien valvoo AI Odota kertaa merkkien muita pyyntöjä ottaen käsittelyjärjestys. Järjestelmänvalvojat voivat myös varmistettava, että tarpeeksi muistia AI kuormituksen syötetietojen koot suhteessa käytettävissä. Tämä voi liittyä eristämällä AI-työmääräsi kapasiteettien tiedetään olevan tarpeeksi resursseja. On myös mahdollista järjestelmänvalvojat voitu coordinate auttamaan lomittaa tai Pienennä tietovirrassa päivitysajat minimoimaan rajuille omistajien tietovirrassa. Huomaa, se ei ole mahdollista, että järjestelmänvalvoja tarkastella AI-kutsun jonon.

### <a name="optimizing-models"></a>Mallien optimointi

Optimaalisen mallin rakenne on tärkeää toimittaa tehokkaita ja skaalattavien ratkaisu. On kuitenkin laajemmin tämä tekninen raportti antaa enempää. Sen sijaan tässä osiossa tarjoaa tärkeiden alueiden meille kun optimointi malleja.

#### <a name="optimizing-power-bi-hosted-models"></a>Power BI-isännöityjä mallien optimointi

Premium-kapasiteettiin isännöidyissä malleissa optimoiminen voidaan saavuttaa osoitteessa lähteiden ja mallin kerrokset.

Harkitse optimoinnin mahdollisuuksia-tuo mallin:

![Tuo mallin optimoinnin mahdollisuudet](media/whitepaper-premium-deployment/import-model-optimizations.png)

Tietojen lähde: tasolla

- Suhteellinen tietolähteitä voi optimoida varmistamiseksi nopein mahdollista päivityksen valmiiksi integrointi tiedot soveltuvat indeksit on otettu käyttöön ja määrittää taulukon osiota, joissa Tasaa lisäävän päivityksen jaksojen materializing laskutoimituksia (sijasta, joka lasketaan malliin taulukot ja sarakkeet) tai laskutoimituksen logiikka lisääminen näkymät
- Ei-relaatiomuotoisiin tietolähteitä voi olla integroitu valmiiksi suhteellisena myymälät
- Varmista, että yhdyskäytävät on tarpeeksi resursseja mieluiten tietokoneissa varattua, riittävät verkon kaistanleveyttä ja ovat lähellä toisiaan tietolähteet

Mallin: tasolla

- Power Query kyselyn suunnittelua varten voit pienentää tai poistaa monimutkaisia muunnoksia ja erityisesti, joka yhdistää eri tietolähteisiin (tietovarastoissa vuokraajajärjestelmänvalvojaa Extract-muunnos-Load niiden vaiheessa). Myös varmistaa, että asianmukainen tietolähteen yksityisyystasot on määritetty, voidaan välttää että Power BI lataaminen koko tulokset tuottamaan yhdistetyn tulos kyselyiden välillä.
- Mallirakenne määrittää ladata tiedot, ja se on suora vaikutus mallin koko. Se on suunniteltu ei lueta tarpeettomat tiedot poistamalla sarakkeita, rivien (etenkin historiatietojen) poistamista tai ladataan yhteenvedetyt tiedot (kustannuksella ladataan yksityiskohtaisia tietoja). Dramaattisia koon pienentäminen voidaan saavuttaa poistamalla kardinaliteetti on suuri-sarakkeet (etenkin tekstisarakkeet), joka ei tallentaa tai Tiivistä erittäin tehokkaasti.
- Mallin kyselyn suorituskyvyn voi parantaa määrittämällä yhteen suuntaan suhteita, ellei sallimaan kaksisuuntaista suodatusta vuoksi. Harkitse myös CROSSFILTER-funktion sijaan kaksisuuntaista suodatusta.
- Koostetaulukoiden saavuttaa nopea kyselyn vastaukset lataamalla valmiiksi yhteenvedetyt tiedot, mutta tämä kasvattaa mallin ja tuloksen koko pidempi päivitysajat. Yleensä koostetaulukoiden varataan erittäin isojen mallien tai koosteen mallin malleja.
- Laskettuja taulukoita ja sarakkeita mallin suurentaa ja pidempi päivitysajat johtaa. Yleensä pienempi tallennustilan koko ja Päivitä nopeammin voidaan saavuttaa, kun tiedot on muodostettu tai laskettu tietolähteen. Jos tämä ei ole mahdollista, käyttämällä Power Query mukautettuja sarakkeita tarjota parannettu tallennustilan pakkaus.
- Saatat mahdollisuuden virittää DAX-lausekkeet mittayksiköt ja rivitason suojauksen sääntöjä, Uudelleenkirjoittamisen ehkä logic välttämiseksi kalliita kaavat
- Lisäävä päivitys voi huomattavasti pienentää päivityksen aika ja säästää muistin ja suorittimen. Lisäävä päivitys voidaan määrittää myös Poista malleja leikkauksen säilyttäen historiatietojen.
- Mallin voitu voi uudistaneet kaksi mallit on eri ja ristiriitaiset kyselymallien. Esimerkiksi joitakin raportteja olemassa korkean tason koosteet kaikki historian ja voivat sallii 24 tunnin viive. Muut raportit ovat kuluva, ja sinun myöntää käyttöoikeuksia yksittäisiä tapahtumia. Sen sijaan, että kaikki raportit täyttämiseksi yhden mallin rakenteen optimoitu kaikki kaksi mallien luomiseen.

Harkitse optimoinnin mahdollisuuksia DirectQuery-mallille. Malli tekee kyselypyyntöjen pohjana olevaan tietolähteeseen, kuten tietojen lähde optimointi on toimittaa reagoiva mallin kyselyt.

 ![DirectQuery-mallille mahdollisuuksia optimointi](media/whitepaper-premium-deployment/direct-query-model-optimizations.png)

Tietojen lähde: tasolla

- Tietolähde voi optimoida sen varmistamiseksi, nopein mahdollista kyselyä integroimalla valmiiksi tietoja (joka ei ole mahdollista mallin kerroksessa), soveltuvat indeksit on otettu käyttöön, määrittäminen taulukon osiot materializing yhteenvedetyt tiedot (ja indeksoituja näkymiä), ja säästämällä laskenta määrä. Parhaan käyttökokemuksen saavutetaan, kun Passthrough-kohteeksi kyselyitä on vain suodattaa ja suorittaa Sisäliitos indeksoidun taulukoiden tai näkymien välillä.
- Varmista, että yhdyskäytävät on tarpeeksi resursseja mieluiten tietokoneissa varattua, riittävät verkon kaistanleveyttä ja kaikissa sen tietolähteen lähellä toisiaan

Mallin: tasolla

- Power Query-kyselyn malleja tulee mieluiten muunnoksia ei - muussa yrittää säilyttää absoluuttisen muunnoksia pienin
- Mallin kyselyn suorituskyvyn voi parantaa määrittämällä yhteen suuntaan suhteita, ellei sallimaan kaksisuuntaista suodatusta vuoksi. Lisäksi mallisuhteet määritetty olettaa viite-eheys on käytössä, (kun tämä on) aiheuttaa tietolähdeluettelossa yhteydellä tehokkaampia sisäliitos (ulkoliitos).
- Vältä luomasta Power Query-kyselyn mukautetut sarakkeet tai mallin lasketun sarakkeen – ellei nämä tietolähteeseen, kun se on mahdollista
- Saatat mahdollisuuden virittää DAX-lausekkeet mittayksiköt ja rivitason suojauksen sääntöjä, Uudelleenkirjoittamisen ehkä logic välttämiseksi kalliita kaavat

Harkitse koosteen mallin optimoinnin mahdollisuuksista. Peruuta koosteen malli mahdollistaa tuonti- ja DirectQuery-taulukot yhdistelmän.

![Koosteen mallin mahdollisuuksia optimointi](media/whitepaper-premium-deployment/composite-model-optimizations.png)

- Yleensä optimoinnin ohjeita tuonti- ja DirectQuery-malleille koskevat koosteen tietomallitaulukoita, jotka käyttävät tallennustilan tiloista.
- Yleensä pyrkimällä saavuttaa Tasapainotettu rakenteen määrittämällä dimensiotyyppiä taulukot (joka liiketoimintaentiteettejä) taulukkoina Dual tallennustilan tilan ja fakta-tyyppi (usein suuria taulukot, joka toiminnallisien tietojen) kuin DirectQuery-tallennustilaa. Dual tallennustilan tarkoittaa sekä tuoda ja tallennustilan DirectQuery-tiloista ja Tämä sallii Power BI-palvelun määrittämään tehokkain tallennustilan käytetään luotaessa alkuperäisen kyselyn tälle Passthrough-kohteeksi.
- Varmista, että yhdyskäytävät on tarpeeksi resursseja mieluiten tietokoneissa varattua, riittävät verkon kaistanleveyttä ja ovat lähellä toisiaan tietolähteet
- Koosteiden taulukoiden määritetty tuonti-tallennustila voit toimittaa dramaattisia kyselyn suorituskyvyn parannukset, kun käytetään DirectQuery tallennustilan tilan fakta-type-taulukot. Tässä tapauksessa koostetaulukoiden suurentaa mallin ja suurenna päivityksen aika ja hyväksyttävä tarjoa nopeammin kyselyiden on usein.

#### <a name="optimizing-externally-hosted-models"></a>Ulkoisesti isännöimä mallien optimointi

Kuvattu optimoinnin monia mahdollisuuksia [Optimizing Power BI-Hosted mallien](#optimizing-power-bi-hosted-models) aiheessa sovelletaan myös analyticsilla Azure Analysis Services- ja SQL Server Analysis Services-malleja. Tyhjennä poikkeuksia ovat ominaisuuksia, jotka eivät ole tuettuja, mukaan lukien yhdistelmämallit ja koostetaulukoiden.

Muita huomioitavia ulkoisesti isännöimä tietojoukkojen on suhteessa Power BI-palvelun isännöinnin tietokanta. Azure Analysis Services Tämä tarkoittaa sitä luominen Azure-resurssi Power BI-vuokraajan (kotialueella) samalla alueella. SQL Server Analysis Services,-IaaS Tämä tarkoittaa, että isännöinnin samalla alueella VM ja paikallisen, se tarkoittaa, että varmistaa tehokasta yhdyskäytävän asennus.

Kesantoala kuin voi olla kiinnostavat Huomaa, että Azure Analysis Services-tietokannat ja SQL Server Analysis Services-taulukkotietokantoja edellyttävät, että niiden ladataan muistiin täysin ja että ne pysyvät olemassa lainkaan tukemaan kyselyä. Power BI-palvelun tavoin täyttäviä voi päivittää, jos mallin on oltava online-tilassa päivityksen aikana tarpeeksi muistia. Toisin kuin Power BI-palvelussa ei ole käsite, että mallit ovat saavuttaneet automaattisesti uloskirjautuminen muistin käytön mukaan. Power BI Premium tarjoaa tehokkaampi lähestymistapa maksimoimaan mallin kyseltäessä kanssa alempaan muistinkäytön vuoksi.

### <a name="capacity-planning"></a>Kapasiteetin suunnitteluun

Premium-kapasiteetin koon määrittää käytettävissä olevan muistin ja suorittimen resursseja ja kapasiteetin rajoissa. Premium-kapasiteetteja määrä on myös merkitystä, kuin luominen useita Premium kapasiteettien voivat auttaa selvittämään kuormituksia toisistaan. Huomaa, että tallennustila on 100 TT: N kapasiteetin solmuun, tämä on todennäköisesti riitä yli tahansa kuormituksen.

Koon ja Premium-kapasiteetteja määrä voi olla hankalaa, erityisesti voit luoda ensimmäisen kapasiteetit. Ensimmäinen vaihe, kun kapasiteetin koon muuttaminen on ymmärtää keskimääräinen kuormituksen, joka vastaa odotettua päivittäisiä käyttö. On tärkeää ymmärtää, että kaikki työnkulut ovat yhtä suuret. Esimerkiksi - liukuväripalkissa - yhdessä päässä 100 samanaikaista käyttäjää käytettäessä yhdelle raporttisivulle, joka sisältää yksittäisen visualisoinnin on voi saavuttaa helposti. – Toisessa päässä sävy - 100 käytettäessä 100 erilaisia raportteja samanaikaisten käyttäjien kunkin 100 visualisointeja raportin sivulla siirtyy tehdä hyvin eri kapasiteetin resurssien vaatimukset.

Kapasiteetin järjestelmänvalvojat vuoksi on otettava huomioon useita tekijät tietyn ympäristön, sisällön ja oletetun käyttötavan. Ohittava tavoitteena on tehokas kapasiteetin käyttö yksityisyyden yhtenäisen kertaa ja hyväksyttävä Odota kertaa häätäminen hinnat. Meille tekijät voivat sisältää:

- **Mallin koko ja tietojen ominaisuudet** : Tuontimalleille on oltava täysin ladataan muistiin, jotta kyselyä tai päivittää. LC/DQ tietojoukkoja voi vaatia merkittävän suoritinajan ja mahdollisesti merkittäviä muistin laskettava monimutkaisia mittareita tai rivitason suojauksen sääntöjä. Muistin ja suorittimen kokoa ja LC/DQ kyselyn siirtomäärän rajoitettu kapasiteetin koon mukaan.
- **Samanaikaisten active mallien** : Eri tuontimalleille samanaikaisten kyseltäessä toimittaa parhaan vasteajan ja suorituskyvyn kun ne pysyvät muistissa. Pitäisi olla isännöimään kaikki vahvasti kysely malleja, niin, että heidän päivityksensä että lisämuistia tarpeeksi muistia.
- **Tuo mallipäivityksen** : Tyypin (täysi tai lisäävä), kesto ja monimutkaisuuden Power Query-kyselyt ja lasketun taulukon tai sarakkeen logic voi vaikuttaa muistin ja erityisesti suorittimen käyttö. Samanaikaisten päivitykset ovat rajoitetuille kapasiteetin koko (1,5 x backend v-ydintä, pyöristää ylöspäin).
- **Samanaikaisten kyselyiden** : Monta samanaikaista kyselyitä voi aiheuttaa ei vastaa raportit kun suoritin tai LC/DQ yhteydet ylittää kapasiteetin rajan. Tämä koskee erityisesti raporttisivujen, jotka sisältävät useita visualisointeja.
- **Dataflows, sivutetut raportit ja Tekoäly funktiot** : Kapasiteetti on määritetty tukemaan dataflows, sivutetut raportit ja Tekoäly funktioita, että kapasiteetti muistin määritettävissä oleva suurin prosenttiosuus. Muistin kohdistetaan dynaamisesti dataflows, mutta se jaetaan staattisesti sivutetut raportit ja Tekoäly kuormituksen.

Sen lisäksi, että näihin tekijöihin kapasiteetin järjestelmänvalvojat voit harkita useita kapasiteettien. Useita kapasiteettien sallia kuormitusten eristämisen ja varmistamiseksi prioriteetti kuormituksia on taata resursseja voidaan määrittää. Esimerkiksi kaksi kapasiteettien voidaan luoda liiketoiminnan kannalta tärkeitä kuormituksia erota Omatoiminen BI (SSBI) kuormituksista. Liiketoiminnan kannalta kapasiteetin voidaan ongelmien suuret tarjoaa niiden taatut resurssit, käyttöoikeuden myöntää vain IT-osastosi authoring yrityksen mallit. SSBI kapasiteetin voidaan isännöidä pienempien mallien kasvava määrä liiketoiminta-analyytikkojen myöntää käyttöoikeuden. SSBI kapasiteetin Joskus saatat kohdata kyselyn tai päivitys odottaa, jotka ovat suurin sallittu.

Ajan kuluessa kapasiteetin järjestelmänvalvojat voivat saldo työtilat kaikissa kapasiteettien siirtämällä sisältöä työtilat tai työtilojen välillä ja skaalaamalla kapasiteettien ylös tai alas. Yleensä isännöimään suurempi malleja, Skaalaa ylös ja suurempi samanaikaisuuden voit skaalausta.

Peruuta että käyttöoikeus ostaminen antaa vuokraajan käyttöön v-ydintä. Hankinta **P3** tilauksen avulla voidaan luoda sellaisen tai enintään neljä Premium-kapasiteetteja 1 x P3 tai 2 x P2 tai 4 x P1. Lisäksi ennen muuntamista P2-kapasiteetti P3 kapasiteettia, voit kiinnitettävä huomiota jakaminen v-ydintä kaksi P1 kuvastaa kapasiteettien luomiseen.

### <a name="testing-approaches"></a>Vain lähestymistapoja

Kun kapasiteetin koko on päättänyt, testaus voidaan suorittaa luomalla valvotussa ympäristössä. Käytännön ja talous-vaihtoehto on luoda (A-Varastointiyksiköt) Azure-kapasiteetti, molemmilla P1 kapasiteetti on yhtä suuri kuin A4-kapasiteetti, jonka P2 ja P3 kapasiteetit saman kokoinen kuin A5 ja A6-kapasiteetit vastaavasti. Azure-kapasiteetit voidaan luoda nopeasti ja laskutetaan tuntipohjaisesti. Siis testaus on suoritettu, ne voidaan helposti poistaa pysäyttää kerätä julkaisemiesi kustannuksia.

Test-sisältöä voidaan lisätä luoda Azure-kapasiteetti työtilat ja sitten yhden käyttäjän voi suorittaa raportteja realistinen ja edustava kuormituksen kyselyiden luomiseen. Jos tuontimalleille, jokainen malli-päivityksen tulisi suorittaa myös. Valvonnan Työkalut sitten voidaan tarkistaa kaikki mittarit ymmärtää resurssien käytön.

On tärkeää, että testit ovat repeatable: Testaa tulee suorittaa useita kertoja, ja ne pitäisi toimittaa noin saman tuloksen aina, kun. Nämä tulokset keskiarvo voidaan ekstrapoloida ja arvioi kuormituksen true tuotannon olosuhteissa.

Luo ruuhkautuminen testi ohjelmoida kuormitustestauksen sovelluksen Simuloi realistinen kuormituksen. Tarkemmat tiedot siitä, miten tämän ei käsitellä tässä raportissa on. Lisätietoja saat mallikoodi mukaan lukien viittaavat [lataaminen testaus Power BI-sovellukset, joissa Visual Studio-Kuormitustesti](https://blogs.msdn.microsoft.com/charles_sterling/2018/04/04/webinar-load-testing-power-bi-applications-with-visual-studio-load-test/) verkkoseminaari.

## <a name="exploring-real-world-scenarios"></a>Oikeiden skenaarioita tutkiminen

Tässä osiossa oikeiden tilanteissa käyttöön kuvataan yleisiä ongelmia tai haasteista, miten voit tunnistaa ja miten voit korjata ne:

- [Tietojoukot pitäminen ajan tasalla](#keeping-datasets-up-to-date)
- [Tunnistetaan hidastaa vastaamisen tietojoukot](#identifying-slow-responding-datasets)
- [Tunnistetaan syitä 0x1E hidastaa-DSR-tietojoukot](#identifying-causes-for-sporadically-slow-responding-datasets)
- [Selvitettäessä, onko tarpeeksi muistia](#determining-whether-there-is-enough-memory)
- [Selvitettäessä, onko tarpeeksi Suoritin](#determining-whether-there-is-enough-cpu)

Kaavio ja taulukko esimerkkejä ja ohjeita ovat **Power BI Premium kapasiteetin mittareita sovelluksen** (sovelluksen), että Power BI-järjestelmänvalvoja pystyy käyttämään.

### <a name="keeping-datasets-up-to-date"></a>Pitäminen tietojoukkoja ylös päivämäärä

Tässä skenaariossa tutkimuksen käynnistettiin, kun käyttäjät havaittujen, että raporttitietoja joskus ominaisuudelta vanhojen tai ”vanhentuneiden”.

Järjestelmänvalvoja vuorovaikutuksessa sovelluksen kanssa **päivittää** visualisoinnin lajittelua tietojoukkojen latautuminen **Max odotusaika** tilastot laskevassa järjestyksessä. Tämä auttaa heitä paljastaa tietojoukkoja, joista on pisimpään Odota kertaa, työtilan nimen mukaan.

![Lajiteltu laskevaan järjestykseen max Tietojoukkosi päivittyy odotusaika, työtilan Ryhmittelyperuste](media/whitepaper-premium-deployment/dataset-refreshes.png)

Lisäksi **tunneittain keskimääräinen Päivitä Odota kertaa** visualisoinnin, hän Huomaa, että Odota päivitysajat piikin johdonmukaisesti noin 4 PM päivä.

![Päivitä odottaa piikin säännöllisesti kello 4](media/whitepaper-premium-deployment/peak-refresh-waits.png)

On useita mahdollisia syitä, että nämä tulokset:

- Liian monta päivityksen yritysten voitu voi tapahtuvista samaan aikaan ylitysten asettaman kapasiteetin solmu (kuusi samanaikaisten päivitykset käyttöön oletusarvon muistin varaaminen kanssa P1)

- Tietojoukkoja voi päivittää saattaa olla liian suuri sopimaan muistia (vaatia vähintään 2 täydellinen vaatimaa muistia)
- Tehottomia Power Query-logic saattaa tuloksena muistin käyttö huipussaan tietojoukon päivityksen aikana. Varattu kapasiteetti, tämä yhteyttä toisinaan fyysinen raja päivitys epäonnistuu, jotka vaikuttavat mahdollisesti muut raportin Näytä toiminnot kapasiteetin.
- Usein kysellyt tietojoukkoja, jotka on pysy muistissa saattaa vaikuttaa muihin tietojoukkoihin kyky päivittää rajoitettu muistia vuoksi

Power BI-järjestelmänvalvoja voit etsiä auttamaan tutkia tämä:

- Tietojen päivittäminen, kun käytettävissä olevaa muistia on pienempi kuin 2, on päivitettävä tietojoukon koosta x milloin käytettävissä muisti
- Tietojoukkoja, jotka olivat ei päivitetä. se ei ollut muistissa ennen päivityksen vielä joka alkoi Näytä vuorovaikutteinen liikenne raskas päivitysajat aikana. Nähdä, mitä tietojoukkoja ladattiin muistiin milloin tahansa Power BI-tietojoukkoja alueen tarkastella järjestelmänvalvojan **tietojoukkoja** ajasta napsauttamalla palkkien sovellus ja rajat suodatin-välilehteen **tunneittain Ladattu tietojoukon määrät**. Paikallinen huipussaan (Katso alla olevassa kuvassa) ilmaisee, tunti, kun useita tietojoukkoja ladattiin muistiin, joka saattaa kestää ajoitetut päivitykset alku
- Parannettu tietojoukon häätöjä ottaen Sijoita Aloita oli aiheutua liian monta eri vuorovaikutteisia raportteja ennen päivityksen aika käsittelevä suuren muisti on vähissä, joka ilmaisee ajoitettuja tietojen päivityksiä. **Tunneittain tietojoukon Häätöjä ja muistin kulutuksen** visual selvästi ilmaistaan häätöjä piikkarit.

Seuraavassa kuvassa näytetään paikallisen huipussaan ladattujen tietojoukkojen joka ehdottaa vuorovaikutteinen kyselyä viivyttää alkuun päivitykset. Valitsemalla tietyn ajanjakson **tunneittain ladata tietojoukko laskee** visualisointi ristiinsuodatuksen **tietojoukkojen koon** visualisoinnin.

![Paikallinen huipussaan ladata tietojoukoissa ehdottaa vuorovaikutteinen kyseltäessä Viivästetty alku päivitykset](media/whitepaper-premium-deployment/hourly-loaded-dataset-counts.png)

Power BI-järjestelmänvalvoja, voit yrittää ratkaista ongelman noudattamalla ohjeita sen varmistamiseksi, että tarpeeksi muistia on käytettävissä tietojen päivityksiä käynnistäminen:

- Muodostettaessa yhteyttä tietojoukon omistajat ja jossa heitä lomittaa välilyönti ulos tietojen päivittäminen ajoitukset
- Tietojoukon vähentää kyselyn kuormitusta poistamalla tarpeettomat koontinäyttöjä tai koontinäytön ruutuja, varsinkin, joka ottaa käyttöön rivitason suojauksen
- Nopeuttaminen tietojen päivityksiä Power Query logic optimoimalla mallin laskettujen sarakkeiden tai taulukoiden tietojoukkojen koon pienentämistä tai määritetään suurempi tietojoukkoja suorittaa lisäävä päivitys

### <a name="identifying-slow-responding-datasets"></a>Tunnistetaan hidastaa vastaamisen tietojoukot

Tässä skenaariossa tutkimuksen käynnistettiin, kun käyttäjät havaittujen tiettyjen raporttien kesti kauan, jotta voit avata ja joskus sulkemalla puhelin.

Sovelluksessa on Power BI-järjestelmänvalvoja voi käyttää **kyselyn keston** visual määrittämään huonoiten suoriutuva tietojoukkoja lajittelemalla tietojoukkoja mukaan laskevasti **keskimääräinen kesto**. Tämä visualisointi näkyy myös tietojoukon kyselyn määrää, jotta näet, miten usein tietojoukkoja tehdään kysely.

![Mahdollinen paljastuminen huonoiten suoriutuva tietojoukot](media/whitepaper-premium-deployment/worst-performing-datasets.png)

Power BI-järjestelmänvalvoja voi viitata **kyselyn keston jakelu** visualisoinnin, joka näyttää tuloksesi kyselyn suorituskyvyn yleisen jakautumisen (< = 30 MS, 0 – 100 millisekunnin yksikköinä, jne.) suodatettu ajanjaksolla. Yleensä kyselyt, ota yksi sekunti tai enintään käsittelemien reagoiva useimmat käyttäjille. Kyselyt, jotka kestää kauemmin tapana luoda näkemys virheellinen suorituskyvystä.

**Tunneittain kyselyn keston jakelu** visualisoinnin avulla Power BI-järjestelmänvalvoja voi tunnistaa yhden tunnin kun kapasiteetin suorituskyky saattaa olla on valittuna käytetä tarkastellaan kokonaisena niin huono. Mitä suurempi palkin lohkoja edustavat kysely kestot yli yksi sekunti, suurempaa riskin, että käyttäjät näkee heikentää suorituskykyä.

Visualisointi on vuorovaikutteinen ja segmentin palkin valittaessa vastaava **kyselyn keston** taulukkovisualisointi raportin sivulla on ristiinsuodatuksia näyttämään se edustaa tietojoukkoja. Tämä ristiinsuodatus avulla Power BI-järjestelmänvalvoja voi helposti joka tietojoukot ovat vastaamisen hitaasti.

Seuraavassa kuvassa näytetään visualisoinnin suodattanut **tunneittain kyselyn keston jaot**, kohdentaminen yhden tunnin säilöjen huonoiten suoriutuva tietojoukoille. 

![Suodatettu tunneittain kyselyn keston jaot visual näyttää tietämättäsi suorittamisen tietojoukot](media/whitepaper-premium-deployment/hourly-query-duration-distributions.png)

Kun tunnistetaan tietyn 1 tunnin timespan huono suorittavan tietojoukon, Power BI-järjestelmänvalvoja voi tutkia asiaa heikentää suorituskykyä aiheutuu ylikuormittunut kapasiteetti, onko vuoksi huonosti suunniteltu tietojoukon tai raportin. Tätä ne voi viitata **kyselyn Odota kertaa** visualisoinnin ja Lajittele tietojoukkoja mukaan laskevasti kyselyiden keskimääräinen odotusaika. Jos kyselyt suuri prosenttiosuus odottavat suuren tarvittaessa tietojoukon on todennäköisesti useita kyselyn odottaa syyn. Jos kyselyiden keskimääräinen odotusaika on merkittäviä (> 100 millisekunnin yksikköinä), se voi olla tarpeen harkita tarkastelet tietojoukon ja raportin nähdäksesi, jos optimointeja voi tehdä. Esimerkiksi ehkä vähemmän visualisoinnit annettu raporttisivujen tai DAX-lausekkeen optimoinnin.

![Kyselyn Odota kertaa visualisointi auttaa paljastaa huonosti suorittavan tietojoukot](media/whitepaper-premium-deployment/query-wait-times.png)

On kyselyn Odota aika koontikäännöksen tietojoukoissa useita mahdollisia syitä:

- Optimaalisen mallin rakenteen tai jopa raportin suunnittelun - kaikissa tilanteissa, voit itse osallistua measure-lausekkeiden pitkään suoritettavat kyselyt, jotka käyttävät suorittimen korkean. Tämä pakottaa uusien kyselyiden Odota, kunnes suorittimen säikeiden saataville ja luoda convoy voimaan (Kuvittele liikenteen hillot), joka on nähty yleisesti piikin virka-aikana. **Kyselyn odottaa** sivu on tärkein resurssin päätellä, tietojoukot suuren kyselyiden keskimääräinen odotusaika kertaa.
- Samanaikainen kapasiteetti käyttäjät (satoja tuhansia) määrä kuluttaja saman raportin tai tietojoukon. Jopa hyvin suunniteltu tietojoukot voivat suorittaa virheellisesti asettamiesi samanaikaisuuden raja-arvo. Tämä ilmaistaan yleensä näytetään huomattavasti suurempi arvo-kyselyn laskee kuin muut tietojoukot Näytä yksi tietojoukko (eli 300K kyselyt-yksi tietojoukko verrattuna < 30K kyselyt muihin tietojoukkoihin). Joskus kyselyn odottaa tälle tietojoukolle alkaa lomittaa ja tämä voi nähdä **kyselyn keston** visualisoinnin.
- Monta eri tietojoukkoa kysely samanaikaisesti, aiheuttaa tietojen poistaminen, kuten tietojoukot käydä usein uloskirjautuminen muistia. Tämän tuloksena käyttäjät ilmenee hidas, kun tietojoukko ladataan muistiin. Vahvista Power BI-järjestelmänvalvoja voi viitata **tunneittain tietojoukon Häätöjä ja muistin kulutuksen** visualisoinnin, joka saattaa ilmaista, että suuren määrän tietojoukkoja ladataan muistiin ovat toistuvasti häädettävän.

### <a name="identifying-causes-for-sporadically-slow-responding-datasets"></a>Tunnistetaan syitä 0x1E hidastaa-DSR-tietojoukot

Tässä skenaariossa tutkimuksen käynnistettiin, kun käyttäjät, jotka on kuvattu, että raportin visualisointien joskus huopa hidastaa vastata tai saattaa lopettaa vastaamisen, mutta joskus ne olivat acceptably reagoiva.

Sovelluksessa **kyselyn keston** osiossa käytettiin löytää virheen aiheuttaja tietojoukon seuraavalla tavalla:

- - **Kyselyn keston** visual järjestelmänvalvoja suodatettu tietojoukon mukaan tietojoukon (alkaen kysely yläreunan tietojoukot) ja tutkia ristisuodatuksen suodatettu palkkien **tunneittain kyselyn jaot** visualisoinnin.
- Kun yhden tunnin palkin näytimme merkittäviä muutoksia kaikki kyselyn keston ryhmät ja yhden tunnin muita palkkeja tietojoukossa suhde (eli värit väliset suhteet muuttuu raporttikyselyt), se tarkoittaa, että tätä tietojoukkoa osoittaa tilapäisiä muutos suorituskyvyn.
- Näytetään suoriutuvien kyselyiden, epäsäännölliset osan yhden tunnin palkit osoittaa timespan, jossa tietojoukko on vaikuttaa Meluisa naapuri voimassa, jotka muihin tietojoukkoihin.

Kuva alla näkyy tunnin 30. tammikuuta, jos ilmeni merkittäviä aikaisemmin tietojoukon suorituskykyä, merkkinä kokoa ”(3,10s]” suorituksen kesto säilöön. Valitsemalla yhden tunnin rivi paljastaa, että kaikki tietojoukkoja ladataan muistiin tänä aikana henkilöstö näin Meluisa naapuri vaikutuksen aiheuttavat hakija virheen aiheuttaja tietojoukkoja.

![Palkki, joka näyttää pahimmassa suorituskyvyn suuri osa](media/whitepaper-premium-deployment/worst-performing-queries.png)

Kun ongelmallinen timespan tunnistetaan (eli aikana Jan 30 yllä olevassa kuvassa) Power BI-järjestelmänvalvoja voi poistaa kaikki tietojoukon suodattimet sitten suodattaminen kyseisen timespan määrittämään, mitä tietojoukkoja on aktiivisesti kyselyitä tänä aikana. Meluisa naapuri tehosteen virheen aiheuttaja-tietojoukko on yleensä yläreunan kysellyt tietojoukon tai jokin pisimpään kyselyiden keskimääräinen kesto.

Jakaa eri työtilat eri Premium-kapasiteetteja tai jaettuun kapasiteettiin, jos tietojoukon kokoa, vaatimusten ja tietojen päivittäminen mallien kautta tietojoukkoja tuetaan virheen aiheuttaja voi ratkaista tämän ongelman.

Vastaavasti voi olla tosi myös. Power BI-järjestelmänvalvoja voi tunnistaa kertaa, kun tietojoukko kyselyn suorituskyvyn raporttikyselyt parantaa ja Etsi mitä katosi. Jos tiettyjä puuttuu kyseisen vaiheessa, sitten, jotka auttavat osoittamaan aiheuttavan ongelma.

### <a name="determining-whether-there-is-enough-memory"></a>Määrittää onko ei tarpeeksi muistia

Voit selvittää, onko tarpeeksi muistia kapasiteetin suorittamiseen sen kuormituksia, Power BI-järjestelmänvalvoja voi viitata **kuluttaa muistia prosenttiosuudet** visualisointia **tietojoukkoja** sovelluksen-välilehdessä. **Kaikki** (yhteensä) muistin edustaa tietojoukkoja ladataan muistiin, riippumatta siitä, ovatko ne aktiivisesti kyselyitä tai käsitellä kuluttaa muistia. **Aktiivinen** muistin edustaa tietojoukkoja, jotka aktiivisesti käsitellään kuluttaa muistia.

Kunnossa olevaa kapasiteettia visualisointi näyttää tämän, näytetään kaikki (yhteensä) välille välin ja aktiivinen:

![Kunnossa olevaa kapasiteettia näyttää kaikki (yhteensä) välille välin ja aktiivinen](media/whitepaper-premium-deployment/memory-healthy-capacity.png)

Muistipainetta ilmenee kapasiteettia samaan visualisointiin näkyvät selvästi, aktiivisen muistin ja muistin kokonaismäärä Yhtyvä, mikä tarkoittaa, että se on mahdotonta muita tietojoukkojen lataaminen muistiin aika tässä. Tässä tapauksessa Power BI-järjestelmänvalvojan napsauttamalla **kapasiteetin uudelleen** (- **lisäasetukset** hallintaportaalin kapasiteetin asetukset-alueen). Käynnistetään uudelleen kapasiteetin tulokset kaikki tietojoukot on tyhjentää muistista ja sallimalla uudelleen muistiin (jota kyselyitä tai tietojen päivitys).

![** Aktiivinen ** muistin Yhtyvä kanssa ** kaikki ** muisti](media/whitepaper-premium-deployment/memory-unhealthy-capacity.png)

### <a name="determining-whether-there-is-enough-cpu"></a>Määrittää onko on tarpeeksi Suoritin

Yleensä ostat kapasiteettia keskimääräinen suorittimen käyttöaste pitäisi pysyä 80 prosentin alla. Suurempi kuin tämä arvo tarkoittaa kapasiteetin lähestyy suorittimen kylläisyys.

Suorittimen kylläisyys vaikutukset ilmaistaan kauemmin pidä vuoksi tiedoillesi monta suorittimen kontekstissa valitsinta, kun se yrittää käsitellä kaikki toiminnot kapasiteetin toiminnot. Premium-kapasiteetissa kanssa tämä näkyy suuren kyselyn samanaikaisten kyselyiden määrä odottaa kertaa. Suuren kyselyn Odota kertaa seurausta on tavallista hitaammin reagoinnin. Power BI-järjestelmänvalvojan muistat helposti, kun suorittimen on tyydyttyneet tarkastelemalla **tunneittain kyselyn Odota aika jaot** visualisoinnin. Kyselyn kausittaisten päät määrät ilmaista mahdollisen suorittimen kylläisyys odotusaika.

![Kyselyn kausittaisten päät odotusaika määrät ilmaista mahdollisen suorittimen kylläisyys](media/whitepaper-premium-deployment/peak-query-wait-times.png)

Samanlaisen kuvion joskus voidaan tunnistaa taustan toiminnot, jos ne osallistua suorittimen kylläisyys. Power BI-järjestelmänvalvoja voi etsiä kausittaisten huipussaan päivitysajat, määritetyn tietojoukon, mikä voi ilmaista suorittimen kylläisyys milloin (todennäköisesti vuoksi muita jatkuvan tietojoukkosi päivittyy ja/tai vuorovaikutteisia kyselyitä). Tässä esiintymässä, viittaavat **järjestelmän** näkymä sovelluksen eivät saa välttämättä paljastaa, että Suoritin on 100 prosenttia. **Järjestelmän** näkymä näyttää tunneittain keskiarvot, mutta Suoritin voi tulla tyydyttyneet muutaman minuutin ajan raskas toiminnoista, joka näkyy kuin piikkarit Odota kertaa.

On lisätietoja erityispiirteensä vaikutusta suorittimen kylläisyys tarkastelua. Odota kyselyiden määrä on tärkeää, kyselyn odotusaika aina tapahtuu jossain määrin aiheuttamatta discernable kansiohierarkiassa. Jotkin tietojoukot (jonka unohtui keskimääräinen kyselyn kertaa, joka ilmaisee monimutkaisuutta tai koko) on enemmän jotka altistuvat paketin suorittimen kylläisyys vaikutukset kuin muut. Tunnistamisessa nämä tietojoukot, Power BI-järjestelmänvalvoja voi hakea muutosten väri palkkien **tunneittain Odota aika jakelu** visualisoinnin. Jälkeen spotting harha palkki näyttää tietojoukoille, jotka oli kyselyn odottaa tänä aikana ne myös verrattuna keskimääräinen kesto kyselyn kyselyiden keskimääräinen odotusaika seurantaan. Kun nämä kaksi tiedot ovat samassa moninkertaisesti ja tietojoukon kyselyn kuormitus on muu kuin yksinkertainen, todennäköisesti tilauksista tietojoukko ei ole tarpeeksi suorittimen mukaan.

Tämä voi olla erityisen selviä, kun tietojoukko on kulutettu lyhyt bursts tiheän käyttövälin kyselyiden useat käyttäjät (eli-koulutus istunnossa), tuloksena suorittimen kylläisyys kunkin jaksopyyntöjen aikana. Tässä tapauksessa merkittäviä kyselyn Odota kertaa tälle tietojoukolle voi kohtasi sekä vaikutuksia-kapasiteetti (Meluisa naapuri vaikutus) muihin tietojoukkoihin.

Joissakin tapauksissa Power BI-järjestelmänvalvoja voi myös pyytää, että tietojoukon omistajat luoda pienempi muuttuvia kyselyn kuormituksen luomalla raportin sijasta (välimuistiin ruutujen Päivitä kyselyt säännöllisesti kaikkien niiden tietojoukkojen kanssa) koontinäytön. Tämä estää piikkarit koontinäytön lataamisen yhteydessä. Tämä ratkaisu ei aina ole mahdollista, että annettu liiketoimintavaatimusten, mutta se voi olla tehokas tapa välttää suorittimen kylläisyys tekemättä muuttaminen tietojoukkoon.

## <a name="conclusion"></a>Päätelmät

Power BI Premium tarjoaa tasaisemman suorituskyvyn, suuri tietomäärät tuki ja yhdistetty Omatoiminen ja yrityksen BI-ympäristössä joustavuutta kaikille organisaatiossasi. Taso 300 Tässä teknisessä raportissa on kirjoitettu erityisesti Power BI-Järjestelmänvalvojat ja sisällön tekijät ja julkaisijat. Se pyrkii heidän on helpompi ymmärtää Power BI Premium mahdollisuuksia ja kerrotaan, kuinka voit suunnitella, ottaa käyttöön, valvoa ja vianmääritys skaalattava ratkaisuja.

Ottaa käyttöön ja hallita Power BI Premium-kapasiteetteja, järjestelmänvalvojat ja mallin kehittäjille vaativat erittäin hyvä käsitys siitä, miten kapasiteettien funktion, miten ne voidaan hallita ja ja miten mallit voidaan optimoida, jotta voit vastata asianmukaisesti Suorituskykyongelmien ja pullonkauloja tulee ne esiintyvät.

## <a name="end-notes"></a>Loppuun huomautukset

<a name="endnote-01"></a>\[1\] tekniset tämä artikkeli koskee Power BI Premium, jota tuetaan vain Power BI-pilvipalvelu ja jotta Power BI-raporttipalvelin ei ole vaikutusalue lukuun ottamatta tilaan, jossa käyttöoikeuden asentaminen edellyttää Power BI-raporttipalvelin sisältyy joitakin Power BI Premium-Varastointiyksiköt.

<a name="endnote-02"></a>\[2\] Power BI-sovelluksen käyttäjien puolesta-sisällön upottamiseksi käytettäessä pilvipalveluna on Platform-kuin-(PaaS). Tämän tyyppinen upottaminen onnistuu yksi niistä Power BI Premium on kaksi eri tuotteiden kanssa.

<a name="endnote-03"></a>\[3\] push streaming ja yhdistelmäyhteyksien tietojoukkoja ei ole tallennettu Premium-kapasiteetteja ja joten ne eivät ole huomioon, kun otetaan käyttöön, hallintaan ja valvontaan Premium-kapasiteetteja.

<a name="endnote-04"></a>\[4\] Excel-työkirjoja Power BI-sisällön tyypiksi ei ole tallennettu Premium-kapasiteetteja ja joten ne eivät ole huomioon, kun käyttöönottoa, hallintaa tai valvonta Premium-kapasiteetteja.

<a name="endnote-05"></a>\[5\] visualisointeja voidaan määrittää Ohita osittajan käsittely. Lisätietoja saat viittaavat [visualisointien vuorovaikutukset Power BI-raportissa](service-reports-visual-interactions.md) tiedoston.

<a name="endnote-06"></a>\[6\] koon ero on määritettävissä Power BI Desktop-tiedoston kokoa ja tehtävien hallinnan muistin käyttämällä tiedoston.

<a name="endnote-07"></a>\[7\] Microsoft tietolähteiden tuki ovat SQL Server, Azure Data lohkoja, Azure HDInsight Spark (beeta), Azure SQL-tietokannan ja Azure SQL Data Warehouse. Lisätietoja siitä, mitä uusia lähteitä viittaavat [Power BI suoran kyselyn tukemat tietolähteet](desktop-directquery-data-sources.md) tiedoston.

<a name="endnote-08"></a>\[8\] Power BI Premium tukee enintään 10 gigatavua kokoa Power BI Desktop (.pbix)-tiedoston lataaminen palvelimeen. Kun ladannut, tietojoukko voi kasvaa enintään 12 Gigatavun kokoiseksi tuloksena päivitys. Latauksen enimmäiskoko vaihtelee SKU. Lisätietoja saat viittaavat [suurten tietojoukkojen tuki Power BI Premium](service-premium-large-datasets.md) tiedoston.

<a name="endnote-09"></a>\[9\] Varastointiyksiköt, jossa on vähemmän kuin neljä v-ydintä ei suoriteta varattua infrastruktuurin. Tämä sisältää EM1, EM2, A1 ja A2-Varastointiyksiköt.

<a name="endnote-10"></a>\[10\] aikana harvinainen, mallit voi olla muistista, koska service toimintoja.

<a name="endnote-11"></a>\[11\] nämä ajoitukset voidaan muuttaa milloin tahansa.

<a name="endnote-12"></a>\[12\] tätä kutsutaan multi-geo tällä hetkellä esikatseluvaiheessa. Useiden geo-käyttöönoton perusteet on yleensä yrityksen tai valtionhallinnon yhteensopivuuden sijaan suorituskyvyn ja mittakaavan. Raportin ja koontinäytön lataamisen liittyy yhä metatietojen kotialue pyyntöjä. Lisätietojen saamiseksi viittaavat [useiden Geo tuki Power BI Premium (esikatselu)](service-admin-premium-multi-geo.md) tiedoston.

<a name="endnote-13"></a>\[13\] on mahdollista, että käyttäjät voivat aiheuttaa suorituskykyongelmia ylikuormittuu Power BI-palvelu, jonka töitä, kirjoitettaessa monimutkaiselta kyselyt, luominen kehäviittauksia jne.

<a name="endnote-14"></a>\[14\] mahdollisuus määrittää koko organisaation työtilat ei suositella ja lisää lähestymistapaan suositellaan. Yleensä se ei ole paras käytäntö Omat työtilat käytettävä tuotannon sisältö.

<a name="endnote-15"></a>\[15\] voi valvoa A-Varastointiyksikköjä sovelluksessa tai Azure-portaalissa, mutta ei Power BI-hallintaportaalissa. Valvomaan A-Varastointiyksikköjä raportin päivitys epäonnistuu, jos sovellus ei ole lisätty resurssin lukija-rooliin. Lisätietojen saamiseksi viittaavat [valvonnan Power BI Premium- ja Power BI Embedded-kapasiteetteja](service-admin-premium-monitor-capacity.md) tiedoston.

<a name="endnote-16"></a>\[16\] päivitykset odottaa, kun ei ole tarpeeksi suorittimen tai muisti.

<a name="endnote-17"></a>\[17\] tietojoukon koko muistissa voi olla suurempi kuin levyllä enintään 20 prosenttia.

<a name="endnote-18"></a>\[18\] keskimääräinen muistinkäyttö (gt) ja suurin muistinkulutus (gt)

<a name="endnote-19"></a>\[19\] tietojoukon häätöjä

<a name="endnote-20"></a>\[20\] tietojoukon kyselyt, tietojoukon keskiarvo kyselyn kesto (ms) tietojoukon Odota määrä ja tietojoukon keskimääräinen odotusaika (ms)

<a name="endnote-21"></a>\[21\] suuri suorittimen käyttöaste-arvo ja suoritinajan suurin käytön (viimeiset seitsemän päivää)

<a name="endnote-22"></a>\[22\] DQ/LC suuren käyttöaste määrä ja DQ/LC aikaa suurin käyttö (viimeiset seitsemän päivää)