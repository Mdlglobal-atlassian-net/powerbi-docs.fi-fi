---
title: Power BI:n suojausraportti
description: Tekninen raportti, jossa käsitellään ja kuvataan Power BI:n tietoturva-arkkitehtuuria ja tietoturvan toteutusta
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/28/2019
ms.author: davidi
LocalizationGroup: Conceptual
ms.openlocfilehash: 8415e731fd8749397b9604277f9f37f126b5413f
ms.sourcegitcommit: 76772a361e6cd4dd88824b2e4b32af30656e69db
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/27/2019
ms.locfileid: "56892987"
---
# <a name="power-bi-security-whitepaper"></a>Power BI:n suojausraportti

**:** Power BI on Microsoftin online-ohjelmistopalvelu (*SaaS* eli Software as a Service, ”ohjelmisto palveluna”), jonka avulla voit nopeasti ja helposti luoda omatoimisia liiketoimintatietojen koontinäyttöjä, raportteja, tietojoukkoja ja visualisointeja. Power BI:n avulla voit muodostaa yhteyden moniin eri tietolähteisiin, yhdistää ja muotoilla tietoja kyseisistä yhteyksistä sekä luoda sitten raportteja ja koontinäyttöjä, jotka voidaan jakaa muiden kanssa.

**Kirjoittaja:** David Iseminger

**Tekniset tarkistajat:** Pedram Rezaei, Cristian Petculescu, Siva Harinath, Tod Manning, Haydn Richardson, Adam Wilson, Ben Childs, Robert Bruckner, Sergei Gundorov, Kasper de Jonge

**Koskee seuraavia:** Power BI SaaS, Power BI Desktop, Power BI Embedded, Power BI Premium

> [!NOTE]
> Voit tallentaa tai tulostaa tämän teknisen raportin valitsemalla selaimesta **Tulosta** ja valitsemalla sitten **Tallenna PDF-tiedostona**.

## <a name="introduction"></a>Johdanto

**Power BI** on Microsoftin online-ohjelmistopalvelu (_SaaS_ eli Software as a Service, ”ohjelmisto palveluna”), jonka avulla voit nopeasti ja helposti luoda omatoimisia liiketoimintatietojen koontinäyttöjä, raportteja, tietojoukkoja ja visualisointeja. Power BI:n avulla voit muodostaa yhteyden moniin eri tietolähteisiin, yhdistää ja muotoilla tietoja kyseisistä yhteyksistä sekä luoda sitten raportteja ja koontinäyttöjä, jotka voidaan jakaa muiden kanssa.

Power BI-palveluun liittyvät [Microsoftin verkkopalvelujen ehdot](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=31) ja [Microsoftin yritystason tietosuojalausunto](http://www.microsoft.com/privacystatement/OnlineServices/Default.aspx). Tietojenkäsittelyn sijainti ilmoitetaan Microsoftin verkkopalvelujen ehtojen kohdassa Tietojen siirrot ja sijaintipaikka. Yhteensopivuuden lisätietojen osalta [Microsoft Trust Center](https://www.microsoft.com/trustcenter) on ensisijainen resurssi Power BI:tä varten. Power BI -ryhmä tekee kovasti töitä saadakseen asiakkaidensa käyttöön uusimmat innovaatiot ja parhaan tuottavuuden. Power BI on tällä hetkellä [Office 365 -yhteensopivuuskehyksen](http://go.microsoft.com/fwlink/p/?LinkID=618494) tasolla D.

Tässä artikkelissa kuvataan Power BI -suojausta kertomalla Power BI -arkkitehtuurista sekä selitetään, miten käyttäjät todennetaan Power BI -palvelussa ja miten tietoyhteydet muodostetaan. Lisäksi kuvataan, kuinka Power BI tallentaa ja siirtää tietoja palvelussa. Viimeisessä osiossa käsitellään tietoturvaan liittyviä kysymyksiä ja myös vastataan niihin.

## <a name="power-bi-architecture"></a>Power BI -arkkitehtuuri

**Power BI** -palvelu perustuu **Azureen**, joka on Microsoftin [pilvitietojen käsittelyalusta](http://azure.microsoft.com/overview/what-is-azure/). Power BI on nykyään käytössä useissa tietokeskuksissa ympäri maailmaa – tarjolla on useita aktiivisia käyttöönottoja, joita kyseisten tietokeskusten alueella toimivat asiakkaat voivat hyödyntää, minkä lisäksi on yhtä monta passiivista käyttöönottoa, jotka toimivat kunkin aktiivisen käyttöönoton varmuuskopioina.

Kukin Power BI -käyttöönotto koostuu kahdesta klusterista – Web Front End (**WFE**) -klusterista ja **Back End** -klusterista. Nämä kaksi klusteria esitetään seuraavassa kuvassa, ja ne liittyvät artikkelin muissa osissa käsiteltyihin aiheisiin. 

![WFE ja Back End](media/whitepaper-powerbi-security/powerbi-security-whitepaper_01.png)

Power BI käyttää tilin todentamiseen ja hallintaan Azure Active Directorya (**AAD**). Power BI käyttää myös **Azure Traffic Manageria** (ATM) ohjaamaan käyttäjät lähimpään palvelinkeskukseen, joka perustuu yhdistämistä yrittävän asiakkaan DNS-tietueeseen. Näin käyttäjä voidaan todentaa ja staattinen sisältö ja tiedostot ladata. Power BI käyttää **Azure Content Delivery Networkia** (CDN) tarpeellisen staattisen sisällön ja tiedostojen jakamiseen käyttäjille aluekohtaisten asetusten perusteella.

### <a name="the-wfe-cluster"></a>WFE-klusteri

**WFE**-klusteri vastaa Power BI:n ensiyhteydenotosta ja todentamisesta. Se todentaa asiakkaat AAD:n avulla ja tarjoaa tunnukset asiakkaiden myöhemmille Power BI -palvelun yhteyksille.

![WEF-klusteri](media/whitepaper-powerbi-security/powerbi-security-whitepaper_02.png)

Kun käyttäjät yrittävät muodostaa yhteyden Power BI-palveluun, asiakkaan DNS-palvelu voi olla yhteydessä **Azure-liikennehallintaan** ja etsiä lähimmän palvelinkeskuksen, jossa on Power BI -käyttöönotto. Katso tähän prosessiin liittyviä lisätietoja artikkelista [Suorituskyvyn liikenteen reititysmenetelmä Azure-liikennehallinnalle](https://azure.microsoft.com/documentation/articles/traffic-manager-routing-methods/#performance-traffic-routing-method).

Käyttäjän lähin WFE-klusteri hoitaa kirjautumis- ja todentamisvaiheen (kuvataan myöhemmin tässä artikkelissa) sekä toimittaa käyttäjälle AAD-tunnuksen, kun todentaminen on onnistunut. WFE-klusterin ASP.NET-osa jäsentää pyynnön ja määrittää, mihin organisaatioon käyttäjä kuuluu, minkä jälkeen se konsultoi Power BI:n **yleistä palvelua**. Yleinen palvelu on yksittäinen Azure-taulukko, joka on jaettu maailman kaikkien WFE- ja Back End -klustereiden kesken ja joka liittää käyttäjät ja asiakasorganisaatiot tietokeskukseen, jossa heidän Power BI -vuokraajaansa säilytetään. WFE määrittää selaimelle, missä Back End -klusterissa organisaation vuokraajaa säilytetään. Kun käyttäjä on todennettu, seuraavat vuorovaikutukset asiakkaan kanssa tapahtuvat suoraan Back End -klusterissa, niin että WFE ei toimi välittäjänä pyynnöille.

### <a name="the-power-bi-back-end-cluster"></a>Power BI -palvelun Back End -klusteri

Todennetut asiakkaat vuorovaikuttavat Power BI -palvelun kanssa **Back End** -klusterin kautta. **Back End** -klusteri hallitsee visualisointeja, käyttäjien koontinäyttöjä, tietojoukkoja, raportteja, tiedon tallennusta, tietoyhteyksiä, tietojen päivittämistä ja muita Power BI -palvelun vuorovaikutusominaisuuksia.

![Back End -klusteri](media/whitepaper-powerbi-security/powerbi-security-whitepaper_03.png)

**Yhdyskäytävän rooli** toimii yhdyskäytävänä käyttäjäpyyntöjen ja Power BI -palvelun välillä. Käyttäjät eivät ole suorassa vuorovaikutuksessa muun roolin kuin yhdyskäytävän roolin kanssa.

**Tärkeää:** On ehdottoman tärkeää huomata, että _vain_ Azure API Management (**APIM**)- ja yhdyskäytävä (**GW**) -roolit ovat käytettävissä julkisen Internetin kautta. Ne tarjoavat todennus-, valtuutus-, SSoS-suojaus-, rajoittamis-, kuormituksen tasaus-, reititys- ja muut ominaisuudet.

Pisteviiva yllä olevassa **Back End** -klusterin kuvassa osoittaa käyttäjien käytettävissä olevien kahden roolin (pisteviivan vasemmalla puolella) ja vain järjestelmän käytettävissä olevien roolien välisen rajan. Kun todennettu käyttäjä muodostaa yhteyden Power BI -palveluun, **yhdyskäytävän rooli** ja **Azure API Management** hyväksyvät yhteyden ja asiakkaan pyynnön ja hallitsevat niitä. Ne vuorovaikuttavat sitten muun Power BI -palvelun kanssa käyttäjän puolesta. Kun asiakas esimerkiksi yrittää tarkastella koontinäyttöä, **yhdyskäytävän rooli** hyväksyy pyynnön ja lähettää pyynnön erikseen **esityksen roolille**, joka noutaa selaimen koontinäytön hahmontamiseen tarvitsemat tiedot.

![Yhdyskäytävän rooli](media/whitepaper-powerbi-security/powerbi-security-whitepaper_04.png)

### <a name="power-bi-premium"></a>Power BI Premium

**Power BI Premium** tarjoaa erillisen, valmistellun ja ositetun palvelutyötilan tilaajille, jotka tarvitsevat Power BI -toimiaan varten erillisiä resursseja. Kun asiakas rekisteröi Power BI Premium -tilauksen, Premium-kapasiteetti luodaan käyttämällä **Azure Resource Manageria**. Tilauksen käyttöönotto määrittää tilaustasoa vastaavan joukon näennäiskoneita tietokeskuksessa, jossa Power BI -vuokraajaa isännöidään (lukuun ottamatta Multi-Geo-ympäristöjä, jotka kuvataan edempänä tässä asiakirjassa), ja tämä joukko alustetaan **Azure-palvelun Fabric**-käyttöönottona.

![Power BI Premium](media/whitepaper-powerbi-security/powerbi-security-whitepaper_05.png)

Luonnin jälkeen kaikki liikenne Premium-klusterin kanssa reititetään Power BI:n Back End -klusterin kautta, jossa muodostetaan yhteys asiakkaan erillisiin **Power BI Premium** -tilauksen näennäiskoneisiin.

### <a name="data-storage-architecture"></a>Tietojen tallentamisen arkkitehtuuri

Power BI käyttää kahta ensisijaista säilöä tietojen tallentamiseen ja hallintaan: käyttäjien lataamat tiedot lähetetään tavallisesti **Azure Blob** -tallennustilaan, ja kaikki metatiedot sekä järjestelmän kohteet tallennetaan palomuurin taakse **Azuren SQL-tietokantaan**.

![Tietojen tallentaminen](media/whitepaper-powerbi-security/powerbi-security-whitepaper_06.png)

Jos käyttäjä esimerkiksi tuo Excel-työkirjan Power BI -palveluun, järjestelmä luo muistissa olevan Analysis Services -taulukkotietokannan ja tiedot tallennetaan muistiin enintään tunnin ajaksi (tai kunnes järjestelmässä ilmenee muistin kuormitusta). Tiedot lähetetään myös **Azure Blob** -säilöön.

Käyttäjän Power BI -tilaukseen liittyvät metatiedot, kuten koontinäytöt, raportit, viimeisimmät tietolähteet, työtilat, organisaation tiedot, vuokraajan tiedot ja muut järjestelmän metatiedot, tallennetaan **Azuren SQL-tietokantaan** ja päivitetään siellä. Kaikki Azuren SQL-tietokantaan tallennetut tiedot salataan täysin käyttämällä [Azuren SQL-tietokannan TDE (Transparent Data Encryption)](https://msdn.microsoft.com/library/dn948096.aspx) -tekniikkaa. Myös kaikki Azure Blob -säilöön tallennetut tiedot salataan. Lisätietoja tietojen lataamisesta, tallentamisesta ja siirtämisestä on osiossa **Tietojen tallentaminen ja siirtäminen**.

## <a name="tenant-creation"></a>Vuokraajan luominen

Vuokraaja on Azure AD -palvelun erillinen esiintymä, jonka organisaatio vastaanottaa ja saa omistukseensa, kun se rekisteröityy Microsoftin pilvipalveluun, kuten Azureen, Microsoft Intuneen, Power BI:hin tai Office 365:een. Kukin Azure AD -vuokraaja on yksilöllinen ja erillinen muista Azure AD -vuokraajista.

Vuokraaja säilyttää yrityksen käyttäjät ja niihin liittyvät tiedot – salasanat, käyttäjäprofiilitiedot, käyttöoikeudet ja niin edelleen. Lisäksi vuokraaja sisältää ryhmiä, sovelluksia ja muita tietoja, jotka liittyvät organisaatioon ja sen suojaukseen. Jos haluat lisätietoja, katso [Mikä on Azure AD -vuokraaja?](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).

Power BI -vuokraaja luodaan siinä tietokeskuksessa, jonka katsotaan olevan lähimpänä niitä maa- (tai alue-) ja osavaltiotietoja, jotka vuokraajalle määritettiin Azure Active Directoryssa, kun Office 365- tai Power BI -palvelu alunperin valmisteltiin. Power BI -vuokraaja ei nykyään siirry kyseisestä tietokeskuksen sijainnista.

### <a name="multiple-geographies-multi-geo---preview"></a>Multi-Geo – esikatselu

Jotkin organisaatiot vaativat Power BI -tavoitettavuutta useilla alueilla liiketoiminnan tarpeiden vuoksi. Yrityksellä saattaa esimerkiksi olla Power BI -vuokraaja Yhdysvalloissa, minkä lisäksi yrityksellä on liiketoimintaa muilla maantieteellisillä alueilla, kuten Australiassa, joten yritys tarvitsee Power BI -palveluita ja -tietoja voidakseen jatkaa toimintaansa kyseisellä etäalueella.  Vuoden 2018 toiselta puoliskolta alkaen organisaatiot, joiden vuokraaja sijaitsee jollakin alueella, voivat käyttää myös toisen alueen Power BI -resursseja, jos valmistelut on tehty oikein. Tätä ominaisuutta kutsutaan kätevyyden vuoksi tässä asiakirjassa nimellä **Multi-Geo**.

Eri alueilla toimittaessa tulee pitää mielessä tiettyjä teknisiä seikkoja, jotka kuvataan tarkemmin tässä asiakirjassa. Tärkeisiin huomioitaviin asioihin kuuluvat muun muassa seuraavat:

- Etäalueella välimuistiin tallennettu kysely säilyy levossa, mutta muut siirrossa olevat tiedot saattavat kulkea useiden eri alueiden välillä.
- Etäalueella olevat PBIX- ja XLSX-tiedostojen raportit, jotka julkaistaan Power BI:hin, saattavat joskus aiheuttaa sen, että kopio tai tilannevedos tallennetaan Power BI:n Azure Blob -säilöön, jolloin tiedot salataan käyttäen Azuren SSE (Storage Service Encryption) -salausta.
- Kun tietoja siirretään Multi-Geo-ympäristössä alueelta toiselle, muistin tiivistäminen alueella, jolta tietoja on siirretty pois, suositetaan tehtäväksi 7–10 päivän kuluessa, jolloin alkuperäisestä sijainnista siirrettyjen tietojen kopio poistetaan.

Seuraavassa kuvassa esitetään, miten Multi-Geo-ympäristössä etäalueen Power BI -palvelut reititetään **Power BI -palvelun Back End** -klusteriin, jossa muodostetaan yhteys asiakkaan Power BI -tilauksen etänäennäiskoneeseen.

![Multi-Geo](media/whitepaper-powerbi-security/powerbi-security-whitepaper_07.png)

### <a name="datacenters-and-locales"></a>Tietokeskukset ja aluekohtaiset asetukset

Power BI on tarjolla tietyillä alueilla sen mukaan, missä Power BI -klustereita on otettu käyttöön alueellisissa tietokeskuksissa. Microsoft aikoo laajentaa Power BI -infrastruktuuriaan uusiin tietokeskuksiin.

Seuraavissa linkeissä on lisätietoja Azure-tietokeskuksista.

- [Azure-alueet](http://azure.microsoft.com/regions/) – tietoa Azuren maailmanlaajuisesta edustuksesta ja sijainneista
- [Azure-palvelut alueittain](http://azure.microsoft.com/regions/#services) – Täydellinen luettelo kullakin alueella saatavilla olevista Microsoftin Azure-palveluista (sekä infrastruktuuripalvelut että käyttöympäristön palvelut).

Tällä hetkellä Power BI -palvelu on saatavilla seuraavilla alueilla, joilla palvelun tarjoavat seuraavat ensisijaiset tietokeskukset:

- United States
  - Itäinen Yhdysvallat
  - Itäinen Yhdysvallat 2
  - Yhdysvaltojen pohjoinen keskiosa
  - Yhdysvaltojen eteläinen keskiosa
  - Länsi-Yhdysvallat
  - Länsi-Yhdysvallat 2
- Kanada
  - Kanada, keskinen
  - Kanada, itäinen
- Yhdistynyt kuningaskunta
  - Yhdistynyt kuningaskunta, länsi
  - Yhdistynyt kuningaskunta, etelä
- Brasilia
  - Brasilia, etelä
- Saksa
  - Saksa, keskinen
  - Saksa, koillinen
- Eurooppa
  - Pohjois-Eurooppa
  - Länsi-Eurooppa
- Japani
  - Japani, itä
  - Japani, länsi
- Intia
  - Keski-Intia
  - Etelä-Intia
  - Länsi-Intia
- Tyynenmeren Aasia
  - Itä-Aasia
  - Kaakkois-Aasia
- Australia
  - Itä-Australia
  - Kaakkois-Australia

Microsoft tarjoaa palvelinkeskuksia myös maakohtaisesti. Lisätietoja Power BI-palvelun käytettävyydestä maakohtaisissa pilvipalveluissa on artikkelissa [Power BI:n maakohtaiset pilvipalvelut](https://powerbi.microsoft.com/clouds/).

Lisätietoja siitä, mihin tietosi tallennetaan ja miten niitä käytetään, on [Microsoft Trust Centerissä](https://www.microsoft.com/TrustCenter/Transparency/default.aspx#_You_know_where). Sitoumukset levossa säilytettävien asiakastietojen sijainnista määritetään [Microsoftin verkkopalvelujen ehdoissa](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=31) kohdassa **Tietojenkäsittelyehdot**.

## <a name="user-authentication"></a>Käyttäjän todennus

Käyttäjän todennus Power BI -palveluun koostuu sarjasta pyyntöjä, vastauksia ja uudelleenohjauksia käyttäjän selaimen sekä Power BI -palvelun tai Power BI:n käyttämien Azure-palveluiden välillä. Kyseinen pyyntösarja kuvaa käyttäjän todentamisprosessia Power BI:ssä. Katso lisätietoja organisaation käyttäjien todentamismallien (sisäänkirjautumisen mallien) vaihtoehdoista artikkelista [Office 365 -sisäänkirjautumismallin valitseminen](https://blogs.office.com/2014/05/13/choosing-a-sign-in-model-for-office-365/).

### <a name="authentication-sequence"></a>Todentamisjakso

Power BI -palvelun käyttäjän todentamisjakso tapahtuu seuraavissa vaiheissa kuvatulla tavalla, ja vaiheet on kuvattu seuraavissa kuvissa.

1. Käyttäjä käynnistää yhteyden Power BI-palveluun selaimesta joko kirjoittamalla osoiteriville Power BI-osoitteen (kuten https://app.powerbi.com) tai valitsemalla Power BI -aloitussivulla vaihtoehdon _Kirjaudu sisään_ (https://powerbi.microsoft.com). Yhteys muodostetaan TLS 1.2 -suojauksella ja HTTPS-yhteysprotokollalla, ja kaikkeen seuraavaan tietoliikenteeseen selaimen ja Power BI -palveluun käytetään HTTPS-yhteyttä. Pyyntö lähetetään **Azure-liikennehallintaan**.

2. **Azure-liikennehallinta** tarkistaa käyttäjän DNS-tietueen ja määrittää lähimmän tietokeskuksen, jossa Power BI on käytössä, minkä jälkeen se vastaa DNS-tietueeseen sen WFE-klusterin IP-osoitteella, johon käyttäjä tulee lähettää.

3. WFE ohjaa käyttäjän sitten Microsoft Online Services -kirjautumissivulle.

    ![Todentamisjakso](media/whitepaper-powerbi-security/powerbi-security-whitepaper_08.png)

1. Kun käyttäjä on todennettu, kirjautumissivu ohjaa käyttäjän aiemmin määritettyyn lähimpään Power BI -palvelun **WFE-klusteriin**.

2. Selain lähettää evästeen, joka saatiin onnistuneen Microsoft Online Services -palveluihin kirjautumisen yhteydessä ja jonka **ASP.NET-palvelu** tutkii **WFE-klusterissa**.

3. WFE-klusteri tarkistaa **Azure Active Directory** (**AAD**) -palvelulta käyttäjän Power BI -palvelun tilauksen todennuksen ja hankkii palvelulta AAD-suojaustunnuksen. Kun AAD palauttaa käyttäjän onnistuneen todennuksen ja palauttaa AAD-suojaustunnuksen, WFE-klusteri konsultoi **Power BI *** yleistä palvelua**, joka ylläpitää vuokraajaluetteloa sekä vuokraajien Power BI -Back End -klusterien sijainteja, ja määrittää, mikä Power BI -palvelun klusteri sisältää käyttäjän vuokraajan. WFE-klusteri ohjaa sitten käyttäjän Power BI -klusteriin, jossa sen vuokraaja sijaitsee, ja palauttaa käyttäjän selaimeen kokoelman kohteita:


      - **AAD-suojaustunnuksen**
      - **istunnon tiedot**
      - sen **Back End** -klusterin verkko-osoitteen, jonka kanssa käyttäjä voi viestiä ja jota käyttäjä voi käsitellä.


1. Käyttäjän selain muodostaa sitten yhteyden määritettyyn Azure-sisältöverkkoon (tai joidenkin tiedostojen yhteydessä WFE:hen) ja lataa kokoelman määritettyjä yleisiä tiedostoja, joiden avulla selain voi olla vuorovaikutuksessa Power BI -palvelun kanssa. Selaimen sivu sisältää AAD-tunnuksen, istunnon tiedot, istuntoon liittyvän Back End -klusterin sijainnin sekä joukon tiedostoja, jotka on ladattu Azure CDN- ja WFE-klusterista Power BI-palvelun selainistunnon ajaksi.

![Azure-sisältöverkon vuorovaikutus](media/whitepaper-powerbi-security/powerbi-security-whitepaper_09.png)

Kun kohteet ovat valmiita, selain ottaa yhteyden määritettyyn Back End -klusteriin ja käyttäjän toiminta Power BI -palvelun kanssa alkaa. Tästä eteenpäin kaikki kutsut Power BI -palveluun liittyvät määritettyyn Back End -klusteriin ja kaikki kutsut sisältävät käyttäjän AAD-tunnuksen. AAD-tunnuksella on yhden tunnin aikakatkaisu; WFE päivittää tunnuksen säännöllisesti, jos käyttäjän istunto pysyy avoimena, niin että käyttöoikeudet säilyvät.

## <a name="data-storage-and-movement"></a>Tietojen tallentaminen ja siirtäminen

Power BI -palvelussa tiedot ovat joko _levossa säilytettäviä_ (Power BI -käyttäjän käytettävissä olevat tiedot, joita ei parhaillaan käsitellä) tai _käsittelyssä_ (esimerkiksi kyselyitä suoritetaan, tietoyhteyksiä ja malleja käsitellään, tietoja ja/tai malleja ladataan Power BI -palveluun sekä muita toimintoja, joita käyttäjät tai Power BI -palvelu saattavat suorittaa tietoihin, joita käytetään aktiivisesti tai päivitetään). Käsiteltävänä olevia tietoja kutsutaan _käsittelyssä oleviksi tiedoiksi_. Levossa säilytettävät tiedot on salattu Power BI:ssä. Myös siirrossa olevat tiedot (eli Power BI -palvelu lähettää tai vastaanottaa tietoja) on salattu.

Lisäksi Power BI -palvelu hallitsee tietoja eri tavoin sen mukaan, käsitelläänkö tietoja **DirectQuery-kyselyllä** vai _ei_ DirectQuery-kyselyllä. Power BI:ssä on siis kaksi käyttäjätietojen luokkaa: DirectQuery-kyselyn käsittelemiä tietoja sekä tietoja, joita DirectQuery ei käsittele.

**DirectQuery** on kysely, jota varten Power BI -käyttäjän kysely on käännetty Microsoftin DAX (Data Analysis Expressions) -kielestä – siis kielestä, jota Power BI ja muut Microsoftin tuotteet käyttävät kyselyiden muodostamiseen – tietolähteen alkuperäiseksi tietokieleksi (kuten T-SQL-kieleksi tai muuksi alkuperäiseksi tietokantakieleksi). DirectQuery-kyselyyn liittyvät tiedot on tallennettu vain viitteeksi, eli lähdetietoja ei säilytetä Power BI:ssä, kun DirectQuery ei ole aktiivinen (lukuun ottamatta visualisointitietoja, joita käytetään koontinäyttöjen ja raporttien esittämiseen, kuten jäljempänä olevassa _Käsittelyssä olevat tiedot (tietojen siirto)_ -osiossa on kuvattu). Sen sijaan tallennetaan viittaukset DirectQuery-tietoihin, jotka mahdollistavat kyseisten tietojen käytön, kun DirectQuery-kysely suoritetaan. DirectQuery sisältää kaikki tarvittavat tiedot kyselyn suorittamiseen, mukaan lukien yhteysmerkkijonon ja tunnistetiedot, joilla tietolähteitä käytetään, joten DirectQuery voi muodostaa yhteyden sisältyviin tietolähteisiin automaattista päivitystä varten. DirectQuery-kyselyssä pohjana olevan tietomallin tiedot sisältyvät DirectQuery-kyselyyn.

Jos kysely **ei** käytä DirectQuery-kyselyä, koostuu se DAX-kyselyiden kokoelmasta, jota _ei_ voi kääntää suoraan minkään pohjana olevan tietolähteen omalle kielelle. Muut kuin DirectQuery-kyselyt eivät sisällä pohjana olevien tietojen tunnistetietoja ja pohjana olevat tiedot ladataan Power BI-palveluun, elleivät ne ole paikallisia tietoja, joita käsitellään [Power BI Gatewayn](https://powerbi.microsoft.com/documentation/powerbi-gateway-enterprise/) kautta, jolloin kysely tallentaa vain viittaukset paikallisiin tietoihin.

DirectQuery-kyselyiden ja muiden kyselyiden välinen ero määrittää sen, miten Power BI -palvelu käsittelee levossa säilytettäviä tietoja ja onko itse kysely salattu. Seuraavissa osissa kuvataan levossa säilytettäviä tietoja ja siirrettäviä tietoja sekä kuvataan salaus, sijainti ja tietojen käsittelyn prosessi.

### <a name="data-at-rest"></a>Levossa säilytettävät tiedot

Kun tietoja säilytetään levossa, Power BI -palvelu tallentaa tietojoukot, raportit ja koontinäyttöruudut seuraavissa osioissa kuvatulla tavalla. Kuten aiemmin mainittiin, Power BI:n levossa säilytettävät tiedot salataan. PML on seuraavissa osioissa lyhenne sanoista Poimi, Muunna ja Lataa.

#### <a name="encryption-keys"></a>Salausavaimet

- Azuren Blob-avaimien salausavaimet säilytetään salattuina Azure Key Vaultissa.
- Azuren SQL-tietokannan TDE-teknologian salausavaimia hallitsee Azure SQL itse.
- Tietojen siirto -palvelun ja paikallisen tietoyhdyskäytävän salausavainta säilytetään:
  - Asiakkaan infrastruktuurin paikallisessa tietoyhdyskäytävässä – paikallisten tietolähteiden osalta
  - Tietojen siirto -roolissa – pilvipohjaisten tietolähteiden osalta

Windowsin Azure Blob -säilön salaamiseen käytetty sisällön salausavain (Content Encryption Key, CEK) on sattumanvaraisesti muodostettu 256-bittinen avain. Algoritmi, jonka avulla CEK salaa sisällön, on AES\_CBC\_256.

CEK:n salaamiseen seuraavaksi käytetty avaimen salausavain (Key Encryption Key, KEK) on ennalta määritetty 256-bittinen avain. Algoritmi, jonka avulla KEK salaa CEK:n, on A256KW.

Palautusavaimeen perustuvat yhdyskäytävän salausavaimet eivät koskaan poistu paikallisesta infrastruktuurista. Power BI ei voi käsitellä salattuja paikallisia tunnistetietoarvoja eikä siepata näitä tunnistetietoja; verkkoasiakkaat salaavat tunnistetiedot julkisella avaimella, joka liittyy siihen tiettyyn yhdyskäytävään, jonka kanssa verkkoasiakas on yhteydessä.

Pilvipohjaisten tietolähteiden osalta Tietojen siirron rooli salaa salausavaimet käyttämällä [Aina salattu](https://msdn.microsoft.com/library/mt163865.aspx) -menetelmiä. Voit lukea lisätietoja [tietokantojen Aina salattu -toiminnosta](https://msdn.microsoft.com/library/mt163865.aspx).

#### <a name="datasets"></a>Tietojoukot

1. Metatiedot (taulukot, sarakkeet, mittayksiköt, laskutoimitukset, yhteysmerkkijonot jne.)
      
    a. Paikallisen Analysis Services -palvelun osalta mitään ei tallenneta palveluun, lukuun ottamatta viittausta tietokantaan, joka tallennetaan salattuna Azuren SQL-tietokantaan.
 
    b. Kaikki muut PML:n, DirectQueryn ja Push-tietojen metatiedot salataan ja tallennetaan Azure Blob -säilöön.

1. Alkuperäisten tietolähteiden tunnistetiedot
  
      a. Paikallinen Analysis Services – Tunnistetietoja ei tarvita, joten tunnistetietoja ei tallenneta.

      b. DirectQuery – Tämä riippuu siitä, luodaanko malli suoraan palvelussa (jolloin malli tallennetaan yhteysmerkkijonoon ja salataan Azure Blobissa) vai tuodaanko mali Power BI Desktopista (jolloin tunnistetiedot tallennetaan salattuina tietojen siirron Azuren SQL-tietokantaan). Salausavain tallennetaan koneeseen, joka suorittaa yhdyskäytävää asiakkaan infrastruktuurissa.

      c. Lähetetyt tiedot – ei käytettävissä

      d. PML

      - **Salesforce** tai **OneDrive** – Päivitystunnukset tallennetaan salattuina Power BI-palvelun Azuren SQL-tietokantaan.
      - Muussa tapauksessa:
        - Jos tietojoukko on määritetty päivitettäväksi, tunnistetiedot tallennetaan salattuina tietojen siirron Azuren SQL-tietokantaan. Salausavain tallennetaan koneeseen, joka suorittaa yhdyskäytävää asiakkaan infrastruktuurissa.
        - Jos tietojoukkoa ei ole määritetty päivitettäväksi, tietolähteisiin ei tallenneta tunnistetietoja.

1. tiedot

    a. Analysis Services paikallisena ja DirectQuery – Mitään ei tallenneta Power BI -palveluun.

    b. PML – Salataan Azure Blob -säilössä, mutta kaikki parhaillaan Power BI -palvelun Azure Blob -tallennustilassa olevat tiedot käyttävät [Azuren SSE (Storage Service Encryption)](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) -salausta, joka tunnetaan myös palvelinpuolen salauksena. Myös Multi-Geo käyttää SSE-salausta.

    c. Työnnetyt tiedot v1 – Tallennetaan salattuina Azure Blob -säilöön, mutta kaikki parhaillaan Power BI -palvelun Azure Blob -tallennustilassa olevat tiedot käyttävät [Azuren SSE (Storage Service Encryption)](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) -salausta, joka tunnetaan myös palvelinpuolen salauksena. Myös Multi-Geo käyttää SSE-salausta.

    d. Työnnetyt tiedot v2 – Tallennetaan salattuina Azuren SQL-tietokantaan.

Power BI käyttää asiakaspuolen salausmenetelmää ja salaa Azuren Blob-säilön CBC (Cipher Block Chaining) -menetelmällä ja AES (Advanced Encryption Standard) -salauksella. Voit [lukea lisätietoja asiakaspuolen salauksesta](https://azure.microsoft.com/documentation/articles/storage-client-side-encryption/).

Power BI toteuttaa tietojen eheyden valvonnan seuraavilla tavoilla:

* Azuren SQL-tietokannassa levossa säilytettävien tietojen osalta Power BI käyttää dbcc:tä, TDE:tä ja yhtenäistä sivun tarkistussummaa osana SQL:n alkuperäisiä tarjouksia.

* Azure Blob -säilössä levossa säilytettävien tietojen osalta Power BI käyttää asiakaspuolen salausta ja HTTPS:ää siirtääkseen tietoja säilöön, joka sisältää eheystarkistuksia tietojen noutamisen yhteydessä. Voit [lukea lisätietoja Azuren Blob -säilön tietoturvasta](https://azure.microsoft.com/documentation/articles/storage-security-guide/).

#### <a name="reports"></a>Raportit

1. Metatiedot (raportin määritys)

   a. Raportit voivat olla joko Office 365:n Excel-raportteja tai Power BI -raportteja. Raportin lajin mukaan metatietoihin pätevät seuraavat asiat:

       a. Excel Report metadata is stored encrypted in SQL Azure. Metadata is also stored in Office 365.
       
       b. Power BI reports are stored encrypted in Azure SQL database.

2. Staattiset tiedot

   Staattisiin tietoihin sisältyy artefakteja, kuten taustakuvat ja mukautetut visualisoinnit.

    a. Jos raportti on luotu Office 365:n Excelillä, mitään ei tallenneta.

    b. Jos kyseessä on Power BI -raportti, staattiset tiedot tallennetaan Azure Blob -säilöön ja salataan.

3. Välimuistit a. Jos raportti on luotu Office 365:n Excelillä, mitään ei tallenneta välimuistiin.

    b. Jos kyseessä on Power BI -raportti, visualisointien tiedot tallennetaan salattuina välimuistiin Azuren SQL-tietokannassa.
 

4. Power BI:hin julkaistut alkuperäiset Power BI Desktop (.pbix)- tai Excel (.xlsx) -tiedostot

    Joskus .xlsx- tai .pbix-tiedostojen kopio tai tilannevedos tallennetaan Power BI:n Azure Blob -säilöön, ja tällöin tiedot salataan. Kaikki tällaiset Power BI -palvelun Azure Blob -säilöön tallennetut raportit käyttävät [Azuren SSE (Storage Service Encryption) -salausta](https://docs.microsoft.com/azure/storage/common/storage-service-encryption), joka tunnetaan myös palvelinpuolen salauksena. Myös Multi-Geo käyttää SSE-salausta.

#### <a name="dashboards-and-dashboard-tiles"></a>Koontinäytöt ja koontinäyttöruudut

1. Välimuistit – Koontinäytön visualisointeihin tarvittavat tiedot on yleensä tallennettu välimuistiin, ja ne säilytetään salattuina Azuren SQL-tietokannassa. Muut ruudut, kuten kiinnitetyt visualisoinnit Excelistä ja SSRS (SQL Server Reporting Services) -palvelut, tallennetaan Azure Blobiin kuvina ja salataan.

2. Staattiset tiedot, joihin sisältyvät taustakuvien ja mukautettujen visualisointien tapaiset artefaktit, tallennetaan ja salataan Azure Blob -säilössä.

Käytetystä salausmenetelmästä huolimatta Microsoft hallitsee avainten salausta asiakkaiden puolesta joko salaisessa säilössä tai Azure Key Vaultissa.

### <a name="data-transiently-stored-on-non-volatile-devices"></a>Tilapäisesti ei-väliaikaisiin laitteisiin tallennetut tiedot

Seuraavassa kuvataan tietoja, jotka on tallennettu tilapäisesti ei-väliaikaisiin laitteisiin.

#### <a name="datasets"></a>Tietojoukot

1. Metatiedot (taulukot, sarakkeet, mittayksiköt, laskutoimitukset, yhteysmerkkijonot jne.)

2. Jotkin rakenteeseen liittyvät artefaktit voidaan tallentaa tietokonesolmujen levylle rajoitetuksi ajaksi. Jotkin artefaktit voidaan tallentaa salaamattomina myös Azure REDIS Cache -välimuistiin rajoitetuksi ajaksi.

3. Alkuperäisten tietolähteiden tunnistetiedot

    a. Analysis Services paikallisesti – Mitään ei tallenneta.

    b. DirectQuery – Tämä riippuu siitä, luodaanko malli palvelussa suoraan, jolloin se tallennetaan yhteysmerkkijonoon salatussa muodossa, niin että salausavain tallennetaan salaamattomana tekstinä samaan paikkaan (salattujen tietojen rinnalle); vai tuodaanko malli Power BI Desktopista, jolloin tunnistetietoja ei tallenneta ei-väliaikaisiin laitteisiin.

    c. Lähetetyt tiedot – Ei mitään (ei käytettävissä).

    d. PML – Ei mitään (mitään ei tallenneta käsittelysolmuun tai eri tavalla kuin yllä olevassa osiossa **Levossa säilytettävät tiedot** on kuvattu).
4. tiedot

    Jotkin tieto-artefaktit voidaan tallentaa tietokonesolmujen levylle rajoitetuksi ajaksi.

### <a name="data-in-process"></a>Käsittelyssä olevat tiedot

Tiedot ovat käsittelyssä, kun käyttäjä käyttää tai käsittelee niitä aktiivisesti. Tiedot ovat käsittelyssä esimerkiksi, kun käyttäjä käsittelee tietojoukkoa tai muokkaa koontinäyttöä tai raporttia, kun päivitys suoritetaan tai kun tapahtuu muita mahdollisia tietojen käsittelytapahtumia. Kun jokin tällainen tapahtuma ilmenee ja saa tiedot käsittelyyn, Power BI -palvelun **tietojen rooli** luo muistissa Analysis Services (AS) -tietokannan ja tietojoukko ladataan kyseiseen muistissa olevaan Analysis Services -tietokantaan. Perustuipa tietojoukko DirectQuery-kyselyyn tai ei, AS-tietokantaan ladatut tiedot ovat salaamattomia, jotta niiden käyttö on sallittu **tietojen roolille**, minkä lisäksi ne säilytetään muistissa myöhempää käyttöä varten, kunnes Power BI -palvelu ei enää tarvitse tietojoukkoa. Jos asiakkaalla on Power BI Premium -tilaus, Power BI luo muistiin Analysis Services (AS) -tietokannan asiakkaan erikseen valmisteltuun Power BI -näennäiskoneiden kokoelmaan.

Kun tietoja käytetään (mihin sisältyy tietojen alustava lataus Power BI:hin), Power BI -palvelu voi tallentaa visualisointitiedot välimuistiin salattuun **Azuren SQL-tietokantaan** riippumatta siitä, perustuuko tietojoukko DirectQuery-kyselyyn.

Power BI valvoo käsiteltävänä olevien tietojen eheyttä käyttämällä HTTPS-, TCP/IP- ja TLS-tekniikkaa ja varmistaa, että tiedot salataan ja että tietojen eheys säilyy siirron aikana.

## <a name="user-authentication-to-data-sources"></a>Käyttäjän todentaminen tietolähteissä

Kunkin tietolähteen yhteydessä käyttäjä muodostaa yhteyden kirjautumisensa perusteella ja käsittelee tietoja näillä tunnistetiedoilla. Käyttäjät voivat luoda sitten kyselyitä, koontinäyttöjä ja raportteja pohjana olevien tietojen perusteella.

Kun käyttäjä jakaa kyselyitä, koontinäyttöjä, raportteja tai mitä tahansa visualisointeja, kyseisten tietojen ja visualisointien käyttöoikeus määräytyy sen mukaan, tukevatko taustalla olevat tietolähteet roolitason suojausta (RLS).

Jos taustalla oleva tietolähde kykenee **Power BI:n roolitason suojaukseen (RLS)**, Power BI -palvelu käyttää kyseisen roolitason suojausta ja käyttäjät, joiden tunnistetiedot eivät riitä pohjana olevien tietojen käsittelyyn (esimerkiksi koontinäytössä, raportissa tai muussa tieto-artefaktissa käytetty kysely), eivät näe sellaisia tietoja, joihin käyttäjän oikeudet eivät riitä. Jos käyttäjän oikeudet pohjana oleviin tietoihin poikkeavat siitä käyttäjästä, joka on luonut koontinäytön tai raportin, visualisoinnit ja muut artefaktit näyttävät vain sellaisia tietoja, joihin käyttäjällä on oikeudet.

Jos tietolähde **ei** käytä roolitason suojausta, Power BI -kirjautumistunnuksia käytetään pohjana olevaan tietolähteeseen, tai jos yhteyden aikana on annettu muut tunnistetiedot, käytetään kyseisiä annettuja tunnistetietoja. Kun käyttäjä lataa Power BI -palveluun tietoja muusta kuin RLS-tietolähteestä, tiedot tallennetaan Power BI:hin niin kuin tämän asiakirjan **Tietojen tallentaminen ja siirtäminen** -osassa kuvataan. Jos kyseessä on muu kuin RLS-tietolähde ja tietoja jaetaan muiden käyttäjien kanssa (esimerkiksi koontinäytössä tai raportissa) tai tiedot päivitetään, tietojen käsittelyyn tai näyttämiseen käytetään alkuperäisiä tunnistetietoja.

![Roolitason suojaus (RLS)](media/whitepaper-powerbi-security/powerbi-security-whitepaper_10.png)

Roolitason suojauksen tietolähteitä ja muun kuin roolitason suojauksen tietolähteitä voidaan verrata nopeasti kuvittelemalla, että Sami luo raportin ja koontinäytön, jotka hän sitten jakaa Aapon ja Riitan kanssa. Jos raportissa ja koontinäytössä käytetyt tietolähteet ovat sellaisista, tietolähteistä, jotka **eivät** tue roolitason suojausta, sekä Aapo että Riitta voivat molemmat nähdä Samin koontinäyttöön sisällyttämät tiedot (jotka on ladattu Power BI -palveluun) ja sekä Aapo että Riitta voivat käsitellä tietoja. Jos Sami sen sijaan luo raportin ja koontinäytön tietolähteistä, jotka tukevat roolitason suojausta, ja jakaa ne sitten Aapon ja Riitan kanssa, Aapon yrittäessä tarkastella koontinäyttöä käy seuraavasti:

1. Koska koontinäyttö on RLS-tietolähteestä, koontinäytön visualisoinneissa näytetään lyhyesti &quot;ladataan&quot;-viesti, kun Power BI -palvelu lähettää tietolähteeseen kyselyn noutaakseen nykyisen tietojoukon, joka on määritetty koontinäytön pohjana olevaan kyselyyn liittyvässä yhteysmerkkijonossa.

2. Tiedot käsitellään ja noudetaan Aapon tunnistetietojen ja roolin perusteella, ja koontinäyttöön ja raporttiin ladataan vain sellaisten tiedot, joihin Aapon käyttöoikeudet riittävät.

3. Koontinäytön ja raportin visualisoinnit näytetään Aapon roolitason perusteella.

Jos Riitta käyttäisi jaettua koontinäyttöä tai raporttia, samat toimet suoritettaisiin hänen roolitasonsa perusteella.

## <a name="power-bi-and-expressroute"></a>Power BI ja ExpressRoute

Power BI:n ja ExpressRouten avulla voit luoda yksityisen verkkoyhteyden omasta organisaatiostasi Power BI:hin (tai käyttämällä palveluntarjoajan ulkoistamisominaisuutta), niin että ohitat Internetin ja suojaat entistä paremmin luottamuksellisia Power BI -tietoja ja yhteyksiä.

ExpressRoute on Azure-palvelu, jonka avulla voit luoda yksityisen yhteyden Azure-tietokeskuksen (jossa Power BI sijaitsee) ja paikallisen infrastruktuurin välille tai luoda yksityisiä yhteyksiä Azure-palvelinkeskusten ja colocation-ympäristön välillä. Lisätietoja on artikkelissa [Power BI ja ExpressRoute](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/).

## <a name="power-bi-mobile"></a>Power BI Mobile

Power BI Mobile on kokoelma sovelluksia, jotka on suunniteltu kolmea ensisijaista mobiiliympäristöä varten: Android, iOS ja Windows Mobile. Power BI Mobile -sovellusten suojausta tulee harkita kahdesta näkökulmasta:

* Laitteiden välinen tietoliikenne
* Laitteessa olevat sovellukset ja tiedot

**Laitteiden välisen tietoliikenteen** osalta kaikki Power BI Mobile -sovellukset ovat yhteydessä Power BI -palveluun sekä käyttävät samaa yhteyttä ja käyttöoikeuksien tarkistusmenetelmiä kuin selaimet; nämä on kuvattu tarkemmin aiemmin tässä raportissa. IOS:n ja Androidin Power BI -mobiilisovellukset tuovat selainistunnon itse sovellukseen, kun taas Windows-mobiilisovellus käyttää välittäjää, joka muodostaa tiedonvälityskanavan Power BI:n kanssa.

Seuraavassa taulukossa selvitetään, mitkä mobiililaitteiden käyttöympäristöt tukevat Power BI Mobilen varmennepohjaista todennusta (CBA):

| **CBA-tuki** | **iOS** | **Android** | **Windows** |
| --- | --- | --- | --- |
| **Power BI** (palveluun kirjautuminen) | Tuetaan | Tuetaan | Ei tueta |
| **SSRS-ADFS** (yhteys SSRS-palvelimeen) | Ei tueta | Tuetaan | Ei tueta |

Power BI Mobile -sovellukset ovat aktiivisesti yhteydessä Power BI -palvelun kanssa. Telemetrian avulla kerätään mobiilisovelluksen käyttötilastoja ja vastaavaa tietoa, jotka toimitetaan palveluihin, joilla valvotaan käyttöä ja aktiivisuutta; telemetrian tietojen yhteydessä ei lähetetä henkilötietoja (Personally Identifiable Information, PII).

**Laitteessa oleva Power BI -sovellus** tallentaa laitteeseen tiedot, jotka helpottavat sovelluksen käyttöä:

* Azure Active Directory- ja päivitystunnukset tallennetaan laitteessa suojattuun mekanismiin käyttämällä yleisesti käytettyjä suojausmenetelmiä.

* Tiedot tallennetaan laitteen tallennustilaan, jota sovellus ei suoraan itse salaa.

* Asetukset tallennetaan myös laitteeseen salaamattomina, mutta varsinaisia käyttäjätietoja ei tallenneta.

Power BI Mobilen välimuisti säilyy laitteessa joko kahden viikon ajan tai kunnes sovellus poistetaan, käyttäjä kirjautuu ulos Power BI Mobilesta tai käyttäjä ei onnistu kirjautumaan sisään (jos esimerkiksi tunnuksen voimassaoloaika päättyy tai salasana vaihtuu). Välimuisti sisältää koontinäytöt ja raportit, joita on aiemmin käytetty Power BI Mobile -sovelluksen kautta.

Power BI Mobile -sovellukset eivät käsittele laitteen kansioita. Lue [lisätietoja offline-tiedoista Power BI Mobile -sovelluksissa](https://powerbi.microsoft.com/documentation/powerbi-mobile-offline-android/).

Kaikki kolme ympäristöä, joissa Power BI Mobile on käytettävissä, tukevat Microsoft Intune -ohjelmistopalvelua, joka mahdollistaa mobiililaitteiden ja sovellusten hallinnan. Kun Intune on otettu käyttöön ja määritetty, mobiililaitteen tiedot salataan eikä itse Power BI -sovellusta voi asentaa SD-kortille. Lue [lisätietoja Microsoft Intunesta](http://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="power-bi-security-questions-and-answers"></a>Power BI:n tietoturvaan liittyviä kysymyksiä ja vastauksia

Seuraavat kysymykset ovat yleisiä Power BI:n suojaukseen liittyviä kysymyksiä ja vastauksia. Ne on järjestetty sen mukaan, milloin ne lisätty tähän raporttiin, jotta löytäisit uudet kysymykset ja vastaukset helposti, kun niitä lisätään. Uusimmat kysymykset on lisätty luettelon loppuun.

**Kuinka käyttäjät muodostavat yhteyden tietolähteisiin ja pääsevät käyttämään tietolähteitä Power BI:tä käyttäessään?**

* **Power BI:n tunnistetiedot ja toimialueen tunnistetiedot:** Käyttäjät kirjautuvat Power BI:hin käyttämällä sähköpostiosoitetta; kun käyttäjä yrittää muodostaa yhteyden tietoresurssiin, Power BI välittää Power BI -kirjautumissähköpostiosoitteen tunnistetietoina. Jos kyseessä on toimialueeseen yhdistetty resurssi (joko paikallinen tai pilvipohjainen), hakemistopalvelu määrittää kirjautumissähköpostiosoitetta vastaavan _käyttäjän ensisijaisen nimen_ ([UPN](https://msdn.microsoft.com/library/windows/desktop/aa380525(v=vs.85).aspx)), joka määrittää, riittävätkö tunnistetiedot sallimaan käytön. Jos organisaatio käyttää Power BI:hin kirjautumiseen työpohjaisia sähköpostiosoitteita (samaa sähköpostia, jolla organisaatiossa kirjaudutaan työresursseihin, esimerkiksi _david@contoso.com_), yhdistäminen voi tapahtua saumattomasti; jos organisaatio käyttää muita kuin työpohjaisia sähköpostiosoitteita (esimerkiksi _david@contoso.onmicrosoft.com_), hakemistojen yhdistäminen on suoritettava, jotta Power BI -sisäänkirjautumistiedoilla voidaan sallia paikallisten resurssien käyttöoikeus.

* **SQL Server Analysis Services ja Power BI:** Power BI tarjoaa organisaatioille, jotka käyttävät paikallisia SQL Server Analysis Services -palveluita, Power BI:n paikallisen tietoyhdyskäytävän (joka on **yhdyskäytävä**, kuten aiemmissa osioissa on kuvattu).  Power BI:n paikallinen tietoyhdyskäytävä voi toteuttaa tietolähteissä roolitason suojauksen (RLS). Jos haluat lisätietoja RLS-suojauksesta, katso tämän asiakirjan aiempi osio **Käyttäjien todentaminen tietolähteissä**. Voit myös lukea syvällisemmän artikkelin, jonka aiheena on [Power BI Gateway](https://powerbi.microsoft.com/documentation/powerbi-gateway-enterprise/).

  Organisaatiot voivat myös käyttää Kerberosta **kertakirjautumiseen** (SSO) ja muodostaa saumattoman yhteyden Power BI:stä paikallisiin tietolähteisiin, joita voivat olla esimerkiksi SQL Server, SAP HANA ja Teradata. Katso lisätietoja ja määritysvaatimukset artikkelista [ **Käytä Kerberosta kertakirjautumiseen Power BI:stä paikallisiin tietolähteisiin**](https://docs.microsoft.com/power-bi/service-gateway-kerberos-for-sso-pbi-to-on-premises-data).

* **Muut kuin toimialueen yhteydet** : Jos tietoyhteyttä ei ole liitetty toimialueeseen eikä tietoyhteys voi suorittaa roolitason suojausta (RLS), käyttäjän on annettava yhteydenmuodostusvaiheessa tunnistetiedot, jotka Power BI sitten välittää tietolähteeseen yhteyden muodostamiseksi. Jos käyttöoikeudet riittävät, tiedot ladataan tietolähteestä Power BI -palveluun.

**Miten tietoja siirretään Power BI:hin?**

* Kaikki Power BI:n pyytämät ja välittämät tiedot salataan siirrettäessä, kun HTTPS-yhteys muodostetaan tietolähteestä Power BI -palveluun. Tietopalvelun kanssa muodostetaan suojattu yhteys ja tiedot kulkevat verkossa vasta, kun yhteys on muodostettu.

**Miten Power BI tallentaa välimuistiin raportti-, koontinäyttö- tai mallitietoja, ja tehdäänkö se turvallisesti?**

* Kun tietolähdettä käytetään, Power BI-palvelu suorittaa tämän asiakirjan kohdassa **Tietojen tallennus ja siirtäminen** kuvatun prosessin.

**Tallentavatko asiakkaat verkkosivujen tietoja paikallisesti välimuistiin?**

* Kun selainasiakkaat käyttävät Power BI:tä, Power BI -verkkopalvelimet määrittävät _Cache-Control_-direktiivin arvoksi _no-store_. Tämä _no-store_-direktiivi määrittää, että selaimet eivät tallenna välimuistiin käyttäjän katsomia verkkosivuja eivätkä tallenna verkkosivua asiakkaan välimuistikansioon.

**Entä roolipohjainen suojaus, raporttien tai koontinäyttöjen jakaminen ja tietoyhteydet? Miten ne toimivat tietojen käsittelyn, koontinäyttöjen katselun, raportin käsittelyn tai tietojen päivityksen osalta?**

* Jos kyseessä on **muu kuin roolipohjaista suojausta (RLS)** käyttävä tietolähde ja jos koontinäyttö, raportti tai tietomalli jaetaan muiden käyttäjien kanssa Power BI:n kautta, tiedot ovat sellaisten käyttäjien käytettävissä, joiden kanssa tiedot on jaettu, ja nämä käyttäjät voivat tarkastella ja käsitellä tietoja. Power BI *ei* todenna käyttäjiä uudelleen tietojen alkuperäisestä lähteestä; kun tiedot on ladattu Power BI:hin, lähdetietojen osalta todennettu käyttäjä on vastuussa sen hallinnoinnista, ketkä toiset käyttäjät ja ryhmät voivat tarkastella tietoja.

  Jos tietoyhteyksiä muodostetaan **RLS**-yhteensopivan tietolähteen kanssa, kuten Analysis Services -tietolähteen kanssa, Power BI:n välimuistiin tallennetaan vain koontinäytön tiedot. Aina kun sellaista raporttia tai tietojoukkoa tarkastellaan tai käsitellään Power BI:ssä, joka käyttää RLS-yhteensopivaa tietolähdettä, Power BI -palvelu käsittelee tietolähdettä käyttäjän tunnistetiedoilla saadakseen tiedot, ja jos tunnistetietoihin liittyy riittävät käyttöoikeudet, tiedot ladataan käyttäjälle raporttiin tai tietomalliin. Jos todentaminen epäonnistuu, käyttäjä näkee virheen.

  Jos haluat lisätietoja, katso tämän asiakirjan aiempi osio **Käyttäjien todentaminen tietolähteissä**.

**Käyttäjämme muodostavat jatkuvasti yhteyksiä samoihin tietolähteisiin, joista osa vaatii eri tunnistetietoja kuin käyttäjien toimialueen tunnistetiedot. Kuinka käyttäjien ei tarvitsisi antaa näitä tunnistetietoja aina, kun he muodostavat tietoyhteyden?**

* Power BI tarjoaa [henkilökohtaisen Power BI -yhdyskäytävän](https://support.powerbi.com/knowledgebase/articles/649846), jonka avulla käyttäjät voivat luoda tunnistetiedot useille eri tietolähteille ja käyttää kyseisiä tunnistetietoja automaattisesti, kun he sitten käsittelevät kutakin tietolähdettä. Jos haluat lisätietoja, katso [Henkilökohtainen Power BI -yhdyskäytävä](https://support.powerbi.com/knowledgebase/articles/649846).

**Miten Power BI -ryhmät toimivat?**

* Power BI -ryhmien avulla käyttäjät voivat nopeasti ja helposti luoda yhteistyönä raporttinäkymiä, raportteja ja tietomalleja vakiintuneissa tiimeissä. Jos esimerkiksi jokin Power BI -ryhmä sisältää kaikki oman lähiryhmäsi käyttäjät, voit tehdä helposti yhteistyötä koko tiimisi kanssa valitsemalla ryhmän Power BI:ssä. Power BI -ryhmät vastaavat Office 365:n universaaleja ryhmiä (joista voit [lukea](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1) ja joita voit [luoda](https://support.office.com/Article/View-create-and-delete-Groups-in-the-Office-365-admin-center-a6360120-2fc4-46af-b105-6a04dc5461c7) ja [hallita](https://support.office.com/Article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)), ja ne käyttävät samaa todentamistapoja kuin mitä Azure Active Directoryssa käytetään tietojen suojaamiseen. Voit [luoda ryhmiä Power BI:ssä](https://support.powerbi.com/knowledgebase/articles/654250) tai luoda universaalin ryhmän Office 365 -hallintakeskuksessa; molemmilla toiminnoilla on sama tulos Power BI:n ryhmien luonnin kannalta.

  Huomaa, että Power BI -ryhmien kanssa jaetut tiedot noudattavat samoja suojausperiaatteita kuin kaikki Power BI:ssä jaetut tiedot. Jos kyseessä on **muu kuin RLS**-tietolähde, Power BI **ei** todenna käyttäjiä uudelleen tietojen alkuperäisestä tietolähteestä, ja kun tiedot on ladattu Power BI:hin, lähdetietojen osalta todennettu käyttäjä on vastuussa sen hallinnoinnista, ketkä toiset käyttäjät ja ryhmät voivat tarkastella tietoja. Jos haluat lisätietoja, katso tämän asiakirjan aiempi osio **Käyttäjien todentaminen tietolähteissä**.

  Voit lukea lisätietoja [ryhmistä Power BI:ssä](https://support.powerbi.com/knowledgebase/articles/654247).

**Mitä portteja paikallinen tietoyhdyskäytävä ja henkilökohtainen yhdyskäytävä käyttävät? Onko sellaisia toimialuenimiä, jotka on sallittava yhteyksiä varten?**

* Yksityiskohtainen vastaus tähän kysymykseen on saatavilla seuraavan linkin kautta: [https://powerbi.microsoft.com/documentation/powerbi-gateway-enterprise](https://powerbi.microsoft.com/documentation/powerbi-gateway-enterprise)

**Kun käytössä on paikallinen tietoyhdyskäytävä, miten palautusavaimia käytetään ja mihin ne on tallennettu? Entä suojattu käyttöoikeuksien hallinta?**

* Yhdyskäytävän asentamisen ja määrittämisen aikana järjestelmänvalvoja kirjoittaa yhdyskäytävän **palautusavaimen**. Tämän **palautusavaimen** avulla luodaan kaksi joukkoa paljon vahvempia avaimia:

  - Epäsymmetrinen **RSA**-avain
  - Symmetrinen **AES**-avain

  Luodut avaimet (**RSA** ja **AES**) tallennetaan tiedostoon paikallisessa koneessa. Tiedosto on myös salattu. Tiedoston sisällön salauksen voi purkaa vain kyseisellä Windows-koneella, ja vain kyseistä yhdyskäytävän palvelutiliä käyttämällä.

  Kun käyttäjä kirjoittaa tietolähteen tunnistetiedot Power BI-palvelun käyttöliittymään, tunnistetiedot salataan selaimessa julkisella avaimella. Yhdyskäytävä salaa uudelleen (jo salatut) tunnistetiedot symmetrisellä AES-avaimella, ennen kuin tiedot tallennetaan Power BI:hin. Tämän prosessin ansiosta Power BI -palvelussa ei koskaan ole salaamattomia tietoja.

**Mitä kommunikaatioprotokollia paikallinen tietoyhdyskäytävä käyttää, ja miten ne on suojattu?**

* Yhdyskäytävä tukee seuraavia kahta kommunikaatioprotokollaa:

  - **AMQP 1.0 – TCP + TLS** : Tämä protokolla edellyttää, että portit 443, 5671–5672 ja 9350–9354 ovat avoinna lähtevää tietoliikennettä varten. Tätä protokollaa suositellaan, koska sen tietoliikennekustannukset ovat pienemmät.

  - **HTTPS – WebSockets ja HTTPS + TLS** : Tämä protokolla käyttää vain porttia 443. WebSocket käynnistetään yksittäisellä HTTP CONNECT -viestillä. Kun kanava on muodostettu, tietoliikenne on käytännössä muotoa TCP + TLS. Voit pakottaa yhdyskäytävän käyttämään tätä protokollaa muokkaamalla asetusta, joka on kuvattu [paikallisen yhdyskäytävän artikkelissa](https://powerbi.microsoft.com/documentation/powerbi-gateway-onprem/).

**Mikä on Azure CDN:n rooli Power BI:ssä?**

* Kuten aiemmin todettiin, Power BI käyttää **Azure Content Delivery Networkia** (CDN) tarpeellisen staattisen sisällön ja tiedostojen jakamiseen käyttäjille aluekohtaisten asetusten perusteella. Tarkemmin sanottuna Power BI -palvelu käyttää useita **CDN**-kohteita, jotta se saa tehokkaasti jaettua tarpeellisen staattisen sisällön ja tiedostot käyttäjille julkisen Internetin kautta. Näitä staattisia tiedostoja ovat tuotelataukset (kuten **Power BI Desktop**, **paikallinen tietoyhdyskäytävä** tai riippumattomien palveluntarjoajien Power BI -sovellukset), selaimen määritystiedostot, joilla alustetaan ja muodostetaan myöhempiä yhteyksiä Power BI -palvelulle, sekä alkuperäinen turvallinen Power BI -kirjautumissivu.

  Ensimmäisen Power BI-palveluyhteyden aikana toimitettujen tietojen perusteella käyttäjän selain muodostaa yhteyden määritettyyn Azure-**sisältöverkkoon** (tai joidenkin tiedostojen yhteydessä **WFE**:hen) ja lataa kokoelman määritettyjä yleisiä tiedostoja, joiden avulla selain voi olla vuorovaikutuksessa Power BI -palvelun kanssa. Selaimen sivu sisältää AAD-tunnuksen, istunnon tiedot, istuntoon liittyvän **Back End** -klusterin sijainnin sekä joukon tiedostoja, jotka on ladattu Azure **CDN**- ja **WFE** - klusterista Power BI -palvelun selainistunnon ajaksi.

**Suorittaako Microsoft mukautettujen visualisointien suhteen minkäänlaista mukautetun visualisointikoodin arviointia suojauksen tai tietoturvan kannalta, ennen kuin kohteita julkaistaan Valikoimaan?**

* Ei. On asiakkaan vastuulla tarkistaa mukautettu visualisointikoodi ja päättää, voiko siihen luottaa. Kaikkia mukautettuja visualisointikoodeja käytetään sandbox-ympäristössä, joten mukautetun visualisoinnin virheelliset koodit eivät vaikuta haitallisesti muuhun Power BI -palveluun.

**Lähettävätkö muut Power BI -visualisoinnit tietoja asiakkaan verkon ulkopuolelle?**

* Kyllä. Bing Maps- ja ESRI-visualisoinnit siirtävät tietoja Power BI -palvelun ulkopuolelle kyseisiä palveluita käyttäville visualisoinneille. Voit katsoa lisätietoja ja tarkat kuvaukset Power BI:n ulkopuolelle suuntautuvasta vuokraajan liikenteestä artikkelista [ **Power BI ja ExpressRoute**](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/).

**Entä tietojen maakohtaisuus? Voimmeko valmistella vuokraajat palvelinkeskuksissa, jotka sijaitsevat tietyillä maantieteellisillä alueilla, jotta tiedot eivät varmasti siirry maan rajojen ulkopuolelle?**

* Tietyillä maantieteellisillä alueilla jotkut asiakkaat voivat luoda vuokraajan maakohtaisessa pilvipalvelussa, jossa tietojen tallennus ja käsittely suoritetaan erillään kaikista muista tietokeskuksista. Maakohtaisissa pilvipalveluissa suojaus toteutetaan hieman eri tavalla, koska erillinen tietojen valtuuttaja käyttää maakohtaista Power BI -palvelua Microsoftin puolesta.

  Vaihtoehtoisesti asiakkaat voivat myös määrittää vuokraajan tietyllä alueella, mutta tällaisilla vuokraajilla ei ole erillistä tietojen valtuuttajaa Microsoftin lisäksi. Maakohtaisten pilvipalveluiden hinnoittelu eroaa yleisesti saatavilla olevasta kaupallisesta Power BI -palvelusta. Lisätietoja Power BI-palvelun käytettävyydestä maakohtaisissa pilvipalveluissa on artikkelissa [Power BI:n maakohtaiset pilvipalvelut](https://powerbi.microsoft.com/clouds/).

**Miten Microsoft käsittelee sellaisten asiakkaiden yhteydet, joilla on Power BI Premium -tilauksia? Eroavatko kyseiset yhteydet niistä yhteyksistä, joita on tarjolla muille kuin Premium Power BI -palvelun käyttäjille?**

* Power BI Premium -tilauksia hankkineiden asiakkaiden yhteydet käyttävät [Azure Business-to-Business (B2B)](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) -valtuutusprosessia, jossa Azure Active Directoryn (AD) avulla toteutetaan käyttöoikeuksien hallinta ja myöntäminen. Power BI käsittelee Power BI Premium -tilaajien yhteydet Power BI Premium -resursseihin samalla tavalla kuin kaikkien Azure AD -käyttäjien.

## <a name="conclusion"></a>Päätelmät

Power BI -palveluarkkitehtuuri perustuu kahteen klusteriin – WFE (Web Front End) -klusteriin ja Back End -klusteriin. WFE-klusteri vastaa Power BI -palvelun ensiyhteydenotosta ja todentamisesta. Todennuksen jälkeen Back End käsittelee kaiken käyttäjien vuorovaikutuksen. Power BI käyttää Azure Active Directorya (AAD) käyttäjätietojen tallentamiseen ja hallitsemiseen. Se hallitsee tietoja ja metatietoja Azure Blob- ja Azuren SQL-tietokantojen avulla (vastaavassa järjestyksessä).

Tietojen tallennus ja tietojen käsittely Power BI:ssä eroaa sen mukaan, käsitelläänkö tietoja DirectQueryn avulla ja ovatko tietolähteet pilvessä vai paikallisia. Power BI voi myös pakottaa roolitason suojauksen (Role Level Security, RLS), ja se toimii sellaisten yhdyskäytävien kanssa, jotka mahdollistavat pääsyn paikallisiin tietoihin.

## <a name="feedback-and-suggestions"></a>Palaute ja ehdotukset

Arvostamme kaikkea saamaamme palautetta. Toivomme kuulevamme ehdotuksia, jotka liittyvät joko tämän teknisen raportin tai muun Power BI -palveluun liittyvän sisällön parannuksiin, lisäyksiin tai selvennyksiin. Lähetä ehdotuksesi osoitteeseen [pbidocfeedback@microsoft.com](mailto:pbidocfeedback@microsoft.com).

## <a name="additional-resources"></a>Lisäresurssit

Lisätietoja Power BI -palvelusta on seuraavissa resursseissa.

- [Ryhmät Power BI:ssä](https://support.powerbi.com/knowledgebase/articles/654247)
- [Power BI Desktopin käytön aloittaminen](https://support.powerbi.com/knowledgebase/articles/471664)
- [Power BI Gateway](https://powerbi.microsoft.com/documentation/powerbi-gateway-enterprise/)
- [Power BI REST -ohjelmointirajapinnan yleiskatsaus](https://msdn.microsoft.com/library/dn877544.aspx)
- [Power BI -ohjelmointirajapinnan viite](https://msdn.microsoft.com/library/mt147898.aspx)
- [Paikallinen tietoyhdyskäytävä](https://powerbi.microsoft.com/documentation/powerbi-gateway-onprem/)
- [Power BI ja ExpressRoute](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
- [Power BI:n maakohtaiset pilvipalvelut](https://powerbi.microsoft.com/clouds/)
- [Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
- [Kerberoksen käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin](https://docs.microsoft.com/power-bi/service-gateway-kerberos-for-sso-pbi-to-on-premises-data)