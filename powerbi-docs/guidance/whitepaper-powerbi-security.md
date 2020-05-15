---
title: Power BI:n suojausraportti
description: Tekninen raportti, jossa käsitellään ja kuvataan Power BI:n tietoturva-arkkitehtuuria ja tietoturvan toteutusta
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/14/2020
LocalizationGroup: Conceptual
ms.openlocfilehash: 4454269803c45948c21c4448ab76b5397d3388b2
ms.sourcegitcommit: 21b06e49056c2f69a363d3a19337374baa84c83f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/15/2020
ms.locfileid: "83407529"
---
# <a name="power-bi-security-whitepaper"></a>Power BI:n suojausraportti

**Yhteenveto:** Power BI on Microsoftin online-ohjelmisto palvelu (*SaaS*tai Software as a Service), jonka avulla voit helposti ja nopeasti luoda omatoimisen liiketoiminta tietojen koonti näyttöjä, raportteja, tieto joukkoja ja visualisointeja. Power BI:n avulla voit muodostaa yhteyden moniin eri tietolähteisiin, yhdistää ja muotoilla tietoja kyseisistä yhteyksistä sekä luoda sitten raportteja ja koontinäyttöjä, jotka voidaan jakaa muiden kanssa.

**Kirjoittaja:** David Isoteminer

**Tekniset tarkistajat:** Pedram rezaei, Cristian Petculescu, Siva Hariath, TOD Manning, Haydn Richardson, Adam Wilson, Ben Childs, Robert Bruckner, Sergei Gundorov

**Koskee seuraavia:** Power BI SaaS, Power BI Desktop, Power BI Embedded Power BI Premium

> [!NOTE]
> Voit tallentaa tai tulostaa tämän raportti valitsemalla **Tulosta** selaimesta ja valitsemalla sitten **Tallenna PDF-** tiedostona.

## <a name="introduction"></a>Johdanto

**Power BI** on Microsoftin online-ohjelmisto palvelu (_SaaS_tai Software as a Service), jonka avulla voit helposti ja nopeasti luoda omatoimisen liiketoiminta tietojen koonti näyttöjä, raportteja, tieto joukkoja ja visualisointeja. Power BI:n avulla voit muodostaa yhteyden moniin eri tietolähteisiin, yhdistää ja muotoilla tietoja kyseisistä yhteyksistä sekä luoda sitten raportteja ja koontinäyttöjä, jotka voidaan jakaa muiden kanssa.

Power BI-palveluun liittyvät [Microsoftin verkkopalvelujen ehdot](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=31) ja [Microsoftin yritystason tietosuojalausunto](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx). Tietojenkäsittelyn sijainti on Microsoftin verkkopalvelujen ehtojen kohdassa Tietojen siirrot ja sijaintipaikka. Yhteensopivuuden lisätietojen osalta [Microsoft Trust Center](https://www.microsoft.com/trustcenter) on ensisijainen resurssi Power BI:tä varten. Power BI -ryhmä tekee kovasti töitä saadakseen asiakkaidensa käyttöön uusimmat innovaatiot ja parhaan tuottavuuden. Power BI on tällä hetkellä [Office 365-yhteensopivuus kehyksen](https://www.microsoft.com/trust-center/compliance/compliance-overview)tasolla D.

Tässä artikkelissa kuvataan Power BI -suojausta kertomalla Power BI -arkkitehtuurista sekä selitetään, miten käyttäjät todennetaan Power BI -palvelussa ja miten tietoyhteydet muodostetaan. Lisäksi kuvataan, kuinka Power BI tallentaa ja siirtää tietoja palvelussa. Viimeisessä osiossa käsitellään tietoturvaan liittyviä kysymyksiä ja myös vastataan niihin.

## <a name="power-bi-architecture"></a>Power BI -arkkitehtuuri

**Power BI** -palvelu perustuu **Azureen**, joka on Microsoftin [pilvitietojen käsittelyalusta](https://azure.microsoft.com/overview/what-is-azure/). Power BI on nykyään käytössä useissa tietokeskuksissa ympäri maailmaa – tarjolla on useita aktiivisia käyttöönottoja, joita kyseisten tietokeskusten alueella toimivat asiakkaat voivat hyödyntää, minkä lisäksi on yhtä monta passiivista käyttöönottoa, jotka toimivat kunkin aktiivisen käyttöönoton varmuuskopioina.

Kukin Power BI -käyttöönotto koostuu kahdesta klusterista – Web Front End (**WFE**) -klusterista ja **Back End** -klusterista. Nämä kaksi klusteria esitetään seuraavassa kuvassa, ja ne liittyvät artikkelin muissa osissa käsiteltyihin aiheisiin. 

![WFE ja Back End](media/whitepaper-powerbi-security/powerbi-security-whitepaper_01.png)

Power BI käyttää tilin todentamiseen ja hallintaan Azure Active Directorya (**AAD**). Power BI käyttää myös **Azure Traffic Manageria** (ATM) ohjaamaan käyttäjät lähimpään palvelinkeskukseen, joka perustuu yhdistämistä yrittävän asiakkaan DNS-tietueeseen. Näin käyttäjä voidaan todentaa ja staattinen sisältö ja tiedostot ladata. Power BI käyttää maantieteellisesti lähimpänä olevaa WFE-kenttää tehokkaasti tarvittavan staattisen sisällön ja tiedostojen tehokkaaseen jakeluun käyttäjille, lukuun ottamatta **Azure Content Delivery Networkin (CDN)** kautta toimitettavaa Power BI visualisointia.

### <a name="the-wfe-cluster"></a>WFE-klusteri

**WFE**-klusteri vastaa Power BI:n ensiyhteydenotosta ja todentamisesta. Se todentaa asiakkaat AAD:n avulla ja tarjoaa tunnukset asiakkaiden myöhemmille Power BI -palvelun yhteyksille.

![WEF-klusteri](media/whitepaper-powerbi-security/powerbi-security-whitepaper_02.png)

Kun käyttäjät yrittävät muodostaa yhteyden Power BI-palveluun, asiakkaan DNS-palvelu voi olla yhteydessä **Azure-liikennehallintaan** ja etsiä lähimmän palvelinkeskuksen, jossa on Power BI -käyttöönotto. Katso tähän prosessiin liittyviä lisätietoja artikkelista [Suorituskyvyn liikenteen reititysmenetelmä Azure-liikennehallinnalle](https://azure.microsoft.com/documentation/articles/traffic-manager-routing-methods/#performance-traffic-routing-method).

Käyttäjän lähin WFE-klusteri hoitaa kirjautumis- ja todentamisvaiheen (kuvataan myöhemmin tässä artikkelissa) sekä toimittaa käyttäjälle AAD-tunnuksen, kun todentaminen on onnistunut. WFE-klusterin ASP.NET-osa jäsentää pyynnön ja määrittää, mihin organisaatioon käyttäjä kuuluu, minkä jälkeen se konsultoi Power BI:n **yleistä palvelua**. Yleinen palvelu on yksittäinen Azure-taulukko, joka on jaettu maailman kaikkien WFE- ja Back-End-klustereiden kesken ja joka liittää käyttäjät ja asiakasorganisaatiot tietokeskukseen, jossa heidän Power BI -vuokraajaansa säilytetään. WFE määrittää selaimelle, missä Back-End-klusterissa organisaation vuokraajaa säilytetään. Kun käyttäjä on todennettu, seuraavat vuorovaikutukset asiakkaan kanssa tapahtuvat suoraan Back-End-klusterissa, niin että WFE ei toimi välittäjänä pyynnöille.

### <a name="the-power-bi-back-end-cluster"></a>Power BI -palvelun Back-End-klusteri

Todennetut asiakkaat vuorovaikuttavat Power BI -palvelun kanssa **Back End** -klusterin kautta. **Back End** -klusteri hallitsee visualisointeja, käyttäjien koontinäyttöjä, tietojoukkoja, raportteja, tiedon tallennusta, tietoyhteyksiä, tietojen päivittämistä ja muita Power BI -palvelun vuorovaikutusominaisuuksia.

![Back-End-klusteri](media/whitepaper-powerbi-security/powerbi-security-whitepaper_03.png)

**Yhdyskäytävän rooli** toimii yhdyskäytävänä käyttäjäpyyntöjen ja Power BI -palvelun välillä. Käyttäjät eivät ole suorassa vuorovaikutuksessa muun roolin kuin yhdyskäytävän roolin kanssa.

**Tärkeää:** On tärkeää huomata, että _vain_ Azure API Management (**APIM**)-ja Gateway (**GW**)-roolit ovat käytettävissä julkisessa Inter netissä. Ne tarjoavat todennus-, valtuutus-, SSoS-suojaus-, rajoittamis-, kuormituksen tasaus-, reititys- ja muut ominaisuudet.

Pisteviiva yllä olevassa **Back-End**-klusterin kuvassa osoittaa käyttäjien käytettävissä olevien kahden roolin (pisteviivan vasemmalla puolella) ja vain järjestelmän käytettävissä olevien roolien välisen rajan. Kun todennettu käyttäjä muodostaa yhteyden Power BI -palveluun, **yhdyskäytävän rooli** ja **Azure API Management** hyväksyvät yhteyden ja asiakkaan pyynnön ja hallitsevat niitä. Ne vuorovaikuttavat sitten muun Power BI -palvelun kanssa käyttäjän puolesta. Kun asiakas esimerkiksi yrittää tarkastella koontinäyttöä, **yhdyskäytävän rooli** hyväksyy pyynnön ja lähettää pyynnön erikseen **esityksen roolille**, joka noutaa selaimen koontinäytön hahmontamiseen tarvitsemat tiedot.

![Yhdyskäytävän rooli](media/whitepaper-powerbi-security/powerbi-security-whitepaper_04.png)

### <a name="power-bi-premium"></a>Power BI Premium

**Power BI Premium** tarjoaa erillisen, valmistellun ja ositetun palvelutyötilan tilaajille, jotka tarvitsevat Power BI -toimiaan varten erillisiä resursseja. Kun asiakas rekisteröi Power BI Premium -tilauksen, Premium-kapasiteetti luodaan käyttämällä **Azure Resource Manageria**. Tilauksen käyttöönotto määrittää tilaustasoa vastaavan joukon näennäiskoneita tietokeskuksessa, jossa Power BI -vuokraajaa isännöidään (lukuun ottamatta Multi-Geo-ympäristöjä, jotka kuvataan edempänä tässä asiakirjassa), ja tämä joukko alustetaan **Azure-palvelun Fabric**-käyttöönottona.

![Power BI Premium](media/whitepaper-powerbi-security/powerbi-security-whitepaper_05.png)

Luonnin jälkeen kaikki liikenne Premium-klusterin kanssa reititetään Power BI:n Back-End-klusterin kautta, jossa muodostetaan yhteys asiakkaan erillisiin **Power BI Premium** -tilauksen näennäiskoneisiin.

### <a name="data-storage-architecture"></a>Tietojen tallentamisen arkkitehtuuri

Power BI käyttää kahta ensisijaista säilöä tietojen tallentamiseen ja hallintaan: käyttäjien lataamat tiedot lähetetään tavallisesti **Azure Blob** -tallennustilaan, ja kaikki metatiedot sekä järjestelmän kohteet tallennetaan palomuurin taakse **Azuren SQL-tietokantaan**.

![Tietojen tallentaminen](media/whitepaper-powerbi-security/powerbi-security-whitepaper_06.png)

Jos käyttäjä esimerkiksi tuo Excel-työkirjan Power BI -palveluun, järjestelmä luo muistissa olevan Analysis Services -taulukkotietokannan ja tiedot tallennetaan muistiin enintään tunnin ajaksi (tai kunnes järjestelmässä ilmenee muistin kuormitusta). Tiedot lähetetään myös **Azure Blob** -säilöön.

Käyttäjän Power BI -tilaukseen liittyvät metatiedot, kuten koontinäytöt, raportit, viimeisimmät tietolähteet, työtilat, organisaation tiedot, vuokraajan tiedot ja muut järjestelmän metatiedot, tallennetaan **Azuren SQL-tietokantaan** ja päivitetään siellä. Kaikki Azuren SQL-tietokantaan tallennetut tiedot salataan täysin käyttämällä [Azuren SQL-tietokannan TDE (Transparent Data Encryption)](https://msdn.microsoft.com/library/dn948096.aspx) -tekniikkaa. Myös kaikki Azure Blob -säilöön tallennetut tiedot salataan. Lisätietoja tietojen lataamisesta, tallentamisesta ja siirtämisestä on osiossa **Tietojen tallentaminen ja siirtäminen**.

## <a name="tenant-creation"></a>Vuokraajan luominen

Vuokraaja on Azure AD -palvelun erillinen esiintymä, jonka organisaatio vastaanottaa ja saa omistukseensa, kun se rekisteröityy Microsoftin pilvipalveluun, kuten Azureen, Microsoft Intuneen, Power BI:hin tai Office 365:een. Kukin Azure AD -vuokraaja on yksilöllinen ja erillinen muista Azure AD -vuokraajista.

Vuokraaja säilyttää yrityksen käyttäjät ja niihin liittyvät tiedot – salasanat, käyttäjäprofiilitiedot, käyttöoikeudet ja niin edelleen. Lisäksi vuokraaja sisältää ryhmiä, sovelluksia ja muita tietoja, jotka liittyvät organisaatioon ja sen suojaukseen. Jos haluat lisätietoja, katso [Mikä on Azure AD -vuokraaja?](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).

Power BI -vuokraaja luodaan siinä tietokeskuksessa, jonka katsotaan olevan lähimpänä niitä maa- (tai alue-) ja osavaltiotietoja, jotka vuokraajalle määritettiin Azure Active Directoryssa, kun Office 365- tai Power BI -palvelu alunperin valmisteltiin. Power BI -vuokraaja ei nykyään siirry kyseisestä tietokeskuksen sijainnista.

### <a name="multiple-geographies-multi-geo"></a>Useita alueita (Multi-Geo)

Jotkin organisaatiot vaativat Power BI -tavoitettavuutta useilla alueilla liiketoiminnan tarpeiden vuoksi. Esimerkiksi yrityksen Power BI Vuokraaja voi olla Yhdysvallat, mutta hän voi myös tehdä liike toimintaa muilla maantieteellisillä alueilla, kuten Australiassa, ja edellyttää, että jotkin Power BI tiedot pysyvät levossa kyseisellä alueella, jotta ne noudattavat paikallisia sääntöjä. Vuoden 2018 toisesta puoliskosta alkaen organisaatiot, joilla on koti-vuokraaja yhdessä maan tieteen parissa, voivat myös valmistella ja käyttää Power BI resursseja, jotka sijaitsevat toisessa maan tieteessä. Tätä ominaisuutta kutsutaan kätevyyden vuoksi tässä asiakirjassa nimellä **Multi-Geo**.

Multi-Geo-tietojen uusin ja ensisijainen artikkeli on [Power BI Premium artikkelin Multi-Geo-tuki](../admin/service-admin-premium-multi-geo.md) . 

On olemassa useita teknisiä tietoja, jotka on arvioitava paikallisten lakien ja säädösten yhteydessä, kun ne toimivat eri maantieteellisillä alueilla. Näitä tietoja ovat esimerkiksi seuraavat:

- Etätietokoneen kyselyn suoritus taso on etäkapasiteettialueella, ja sen avulla varmistetaan, että tieto malli, väli muistit ja suurin mahdollinen tietojenkäsittely pysyvät etäkapasiteettialueella. On joitakin poikkeuksia, jotka on kuvattu [Multi-Geo for Power BI Premium-](../admin/service-admin-premium-multi-geo.md) artikkelissa.
- Väli muistissa oleva kysely teksti ja siihen tallennettu syrjäiseen alueeseen tallennettu vastaava tulos pysyvät tällä alueella levossa, mutta muut kauttakulussa olevat tiedot voivat siirtyä edestakaisin useiden maantieteellisille alueille.
- PBIX-tai XLSX-tiedostot, jotka on julkaistu (ladattu) Power BI-palvelu Multi-Geo-kapasiteettiin, saattavat johtaa siihen, että kopio tallennetaan tilapäisesti Azure BLOB-säilöön Power BI vuokraajaalueella. Tällaisissa tilanteissa tiedot salataan käyttämällä Azure-tallennus palvelun salausta (SSE), ja kopiointi on ajoitettu roska-kokoelmalle heti, kun tiedoston sisällön käsittely ja siirtäminen etäalueelle on valmis. 
- Kun siirrät tietoja alueiden välillä Multi-Geo-ympäristössä, lähde alueen tietojen esiintymä poistetaan 7-30 päivän kuluessa. 

### <a name="datacenters-and-locales"></a>Tietokeskukset ja aluekohtaiset asetukset

Power BI on tarjolla tietyillä alueilla sen mukaan, missä Power BI -klustereita on otettu käyttöön alueellisissa tietokeskuksissa. Microsoft aikoo laajentaa Power BI -infrastruktuuriaan uusiin tietokeskuksiin.

Seuraavissa linkeissä on lisätietoja Azure-tietokeskuksista.

- [Azure-alueet](https://azure.microsoft.com/regions/) – tietoa Azuren maailmanlaajuisesta edustuksesta ja sijainneista
- [Azure-palvelut alueittain](https://azure.microsoft.com/regions/#services) – Täydellinen luettelo kullakin alueella saatavilla olevista Microsoftin Azure-palveluista (sekä infrastruktuuripalvelut että käyttöympäristön palvelut).

Tällä hetkellä Power BI-palvelu on käytettävissä tietyillä alueilla, joita palvelin keskukset tarjoavat [Microsoft Trust Centerissä](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)kuvatulla tavalla. Seuraava linkki näyttää kartan Power BI -palvelinkeskuksista. Kun viet hiiren osoittimen alueen päällä, näet alueella sijaitsevat palvelinkeskukset:

* [Power BI -palvelinkeskukset](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)

Microsoft tarjoaa palvelinkeskuksia myös maakohtaisesti. Lisätietoja Power BI-palvelun käytettävyydestä kansallisissa pilvipalveluissa on artikkelissa [Power BI:n kansalliset pilvipalvelut](https://powerbi.microsoft.com/clouds/).

Lisätietoja siitä, mihin tietosi tallennetaan ja miten niitä käytetään, löydät [Microsoft Trust Centeristä](https://www.microsoft.com/TrustCenter/Transparency/default.aspx#_You_know_where). Sitoumukset levossa säilytettävien asiakastietojen sijainnista määritetään [Microsoftin verkkopalvelujen ehdoissa](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=31) kohdassa **Tietojenkäsittelyehdot**.

## <a name="user-authentication"></a>Käyttäjän todennus

Käyttäjän todennus Power BI -palveluun koostuu sarjasta pyyntöjä, vastauksia ja uudelleenohjauksia käyttäjän selaimen sekä Power BI -palvelun tai Power BI:n käyttämien Azure-palveluiden välillä. Kyseinen pyyntösarja kuvaa käyttäjän todentamisprosessia Power BI:ssä. Katso lisätietoja organisaation käyttäjien todentamismallien (sisäänkirjautumisen mallien) vaihtoehdoista artikkelista [Office 365 -sisäänkirjautumismallin valitseminen](https://blogs.office.com/2014/05/13/choosing-a-sign-in-model-for-office-365/).

### <a name="authentication-sequence"></a>Todentamisjakso

Power BI -palvelun käyttäjän todentamisjakso tapahtuu seuraavissa vaiheissa kuvatulla tavalla, ja vaiheet on kuvattu seuraavissa kuvissa.

1. Käyttäjä aloittaa yhteyden Power BI-palvelu selaimesta joko kirjoittamalla osoite rivillä olevaan Power BI osoitteeseen (esimerkiksi `https://app.powerbi.com` ) tai valitsemalla _kirjaudu_ sisään Power BI aloitus sivulta ( https://powerbi.microsoft.com) . Yhteys muodostetaan TLS 1.2 -suojauksella ja HTTPS-yhteysprotokollalla, ja kaikkeen seuraavaan tietoliikenteeseen selaimen ja Power BI -palveluun käytetään HTTPS-yhteyttä. Pyyntö lähetetään **Azure-liikennehallintaan**.

2. **Azure-liikennehallinta** tarkistaa käyttäjän DNS-tietueen ja määrittää lähimmän tietokeskuksen, jossa Power BI on käytössä, minkä jälkeen se vastaa DNS-tietueeseen sen WFE-klusterin IP-osoitteella, johon käyttäjä tulee lähettää.

3. WFE ohjaa käyttäjän sitten Microsoft Online Services -kirjautumissivulle.

    ![Todentamisjakso](media/whitepaper-powerbi-security/powerbi-security-whitepaper_08.png)

1. Kun käyttäjä on todennettu, kirjautumissivu ohjaa käyttäjän aiemmin määritettyyn lähimpään Power BI -palvelun **WFE-klusteriin**.

2. Selain lähettää evästeen, joka saatiin onnistuneen Microsoft Online Services -palveluihin kirjautumisen yhteydessä ja jonka **ASP.NET-palvelu** tutkii **WFE-klusterissa**.

3. WFE-klusteri tarkistaa **Azure Active Directory** (**AAD**) -palvelulta käyttäjän Power BI -palvelun tilauksen todennuksen ja hankkii palvelulta AAD-suojaustunnuksen. Kun AAD palauttaa käyttäjän onnistuneen todennuksen ja palauttaa AAD-suojaustunnuksen, WFE-klusteri konsultoi **Power BI *** yleistä palvelua**, joka ylläpitää vuokraajaluetteloa sekä vuokraajien Power BI -Back-End-klusterien sijainteja, ja määrittää, mikä Power BI -palvelun klusteri sisältää käyttäjän vuokraajan. WFE-klusteri ohjaa sitten käyttäjän Power BI -klusteriin, jossa sen vuokraaja sijaitsee, ja palauttaa käyttäjän selaimeen kokoelman kohteita:

      - **AAD-suojaustunnuksen**
      - **istunnon tiedot**
      - sen **Back-End**-klusterin verkko-osoitteen, jonka kanssa käyttäjä voi viestiä ja jota käyttäjä voi käsitellä

1. Käyttäjän selain muodostaa sitten yhteyden määritettyyn Azure-sisältöverkkoon (tai joidenkin tiedostojen yhteydessä WFE:hen) ja lataa kokoelman määritettyjä yleisiä tiedostoja, joiden avulla selain voi olla vuorovaikutuksessa Power BI -palvelun kanssa. Selaimen sivu sisältää AAD-tunnuksen, istunnon tiedot, istuntoon liittyvän Back-End-klusterin sijainnin sekä joukon tiedostoja, jotka on ladattu Azure CDN- ja WFE- klusterista Power BI -palvelun selainistunnon ajaksi.

![Azure-sisältöverkon vuorovaikutus](media/whitepaper-powerbi-security/powerbi-security-whitepaper_09.png)

Kun kohteet ovat valmiita, selain ottaa yhteyden määritettyyn Back-End-klusteriin ja käyttäjän toiminta Power BI -palvelun kanssa alkaa. Tästä eteenpäin kaikki kutsut Power BI -palveluun liittyvät määritettyyn Back-End-klusteriin ja kaikki kutsut sisältävät käyttäjän AAD-tunnuksen. AAD-tunnuksella on yhden tunnin aikakatkaisu; WFE päivittää tunnuksen säännöllisesti, jos käyttäjän istunto pysyy avoimena, niin että käyttöoikeudet säilyvät.

## <a name="data-storage-and-movement"></a>Tietojen tallentaminen ja siirtäminen

Power BI -palvelussa tiedot ovat joko _levossa säilytettäviä_ (Power BI -käyttäjän käytettävissä olevat tiedot, joita ei parhaillaan käsitellä) tai _käsittelyssä_ (esimerkiksi kyselyitä suoritetaan, tietoyhteyksiä ja malleja käsitellään, tietoja ja/tai malleja ladataan Power BI -palveluun sekä muita toimintoja, joita käyttäjät tai Power BI -palvelu saattavat suorittaa tietoihin, joita käytetään aktiivisesti tai päivitetään). Käsiteltävänä olevia tietoja kutsutaan _käsittelyssä oleviksi tiedoiksi_. Levossa säilytettävät tiedot on salattu Power BI:ssä. Myös siirrossa olevat tiedot (eli Power BI -palvelu lähettää tai vastaanottaa tietoja) on salattu.

Lisäksi Power BI -palvelu hallitsee tietoja eri tavoin sen mukaan, käsitelläänkö tietoja **DirectQuery-kyselyllä** vai tuonnilla. Power BI:ssä on siis kaksi käyttäjätietojen luokkaa: DirectQuery-kyselyn käsittelemiä tietoja sekä tietoja, joita DirectQuery ei käsittele.

**DirectQuery** on kysely, jota varten Power BI -käyttäjän kysely on käännetty Microsoftin DAX (Data Analysis Expressions) -kielestä – siis kielestä, jota Power BI ja muut Microsoftin tuotteet käyttävät kyselyiden muodostamiseen – tietolähteen alkuperäiseksi tietokieleksi (kuten T-SQL-kieleksi tai muuksi alkuperäiseksi tietokantakieleksi). DirectQuery-kyselyyn liittyvät tiedot on tallennettu vain viitteeksi, eli lähdetietoja ei säilytetä Power BI:ssä, kun DirectQuery ei ole aktiivinen (lukuun ottamatta visualisointitietoja, joita käytetään koontinäyttöjen ja raporttien esittämiseen, kuten jäljempänä olevassa _Käsittelyssä olevat tiedot (tietojen siirto)_ -osiossa on kuvattu). Sen sijaan tallennetaan viittaukset DirectQuery-tietoihin, jotka mahdollistavat kyseisten tietojen käytön, kun DirectQuery-kysely suoritetaan. DirectQuery sisältää kaikki tarvittavat tiedot kyselyn suorittamiseen, mukaan lukien yhteysmerkkijonon ja tunnistetiedot, joilla tietolähteitä käytetään, joten DirectQuery voi muodostaa yhteyden sisältyviin tietolähteisiin automaattista päivitystä varten. DirectQuery-kyselyssä pohjana olevan tietomallin tiedot sisältyvät DirectQuery-kyselyyn.

Tuontitietojoukon kysely kostuu joukosta DAX-kyselyitä, jota _ei_ käännetä suoraan minkään pohjana olevan tietolähteen omalle kielelle. Tuontikyselyt eivät sisällä pohjana olevien tietojen tunnistetietoja ja pohjana olevat tiedot ladataan Power BI-palveluun, elleivät ne ole paikallisia tietoja, joita käsitellään [Power BI Gatewayn](../connect-data/service-gateway-onprem.md) kautta, jolloin kysely tallentaa vain viittaukset paikallisiin tietoihin.

Seuraava taulukko kuvaa Power BI -tietoja käytettävän kyselyn tyypin mukaan. **X** ilmaisee liittyvää kyselytyyppiä käytettäessä Power BI -tietojen olemassaolon.


|  |Tuo  |DirectQuery  |Reaaliaikainen yhteys  |
|---------|---------|---------|---------|
|Rakenne     |     X    |    X     |         |
|Rivitiedot     |    X     |         |         |
|Visualisointitietojen tallentaminen välimuistiin     |    X     |     X    |    X     |

DirectQuery-kyselyiden ja muiden kyselyiden välinen ero määrittää sen, miten Power BI -palvelu käsittelee levossa säilytettäviä tietoja ja onko itse kysely salattu. Seuraavissa osissa kuvataan levossa säilytettäviä tietoja ja siirrettäviä tietoja sekä kuvataan salaus, sijainti ja tietojen käsittelyn prosessi.

### <a name="data-at-rest"></a>Levossa säilytettävät tiedot

Kun tietoja säilytetään levossa, Power BI -palvelu tallentaa tietojoukot, raportit ja koontinäyttöruudut seuraavissa alakohdissa kuvatulla tavalla. Kuten aiemmin mainittiin, Power BI:n levossa säilytettävät tiedot salataan. PML on seuraavissa osioissa lyhenne sanoista Poimi, Muunna ja Lataa.

#### <a name="encryption-keys"></a>Salausavaimet

- Azuren Blob-avaimien salausavaimet säilytetään salattuina Azure Key Vaultissa.
- Azuren SQL-tietokannan TDE-teknologian salausavaimia hallitsee Azure SQL itse.
- Tietojen siirto -palvelun ja paikallisen tietoyhdyskäytävän salausavainta säilytetään:
  - Asiakkaan infrastruktuurin paikallisessa tietoyhdyskäytävässä – paikallisten tietolähteiden osalta
  - Tietojen siirto -roolissa – pilvipohjaisten tietolähteiden osalta

Microsoft Azure BLOB-säilön salaamiseen käytetty sisällön salaus avain (CEK) on satunnaisesti muodostettu 256-bittinen avain. Algoritmi, jonka avulla CEK salaa sisällön, on AES\_CBC\_256.

CEK:n salaamiseen seuraavaksi käytetty avaimen salausavain (Key Encryption Key, KEK) on ennalta määritetty 256-bittinen avain. Algoritmi, jonka avulla KEK salaa CEK:n, on A256KW.

Palautusavaimeen perustuvat yhdyskäytävän salausavaimet eivät koskaan poistu paikallisesta infrastruktuurista. Power BI ei voi käsitellä salattuja paikallisia tunnistetietoarvoja eikä siepata näitä tunnistetietoja; verkkoasiakkaat salaavat tunnistetiedot julkisella avaimella, joka liittyy siihen tiettyyn yhdyskäytävään, jonka kanssa verkkoasiakas on yhteydessä.

Pilvipohjaisten tietolähteiden osalta Tietojen siirron rooli salaa salausavaimet käyttämällä [Aina salattu](https://msdn.microsoft.com/library/mt163865.aspx) -menetelmiä. Voit lukea lisätietoja [tietokantojen Aina salattu -toiminnosta](https://msdn.microsoft.com/library/mt163865.aspx).

#### <a name="datasets"></a>Tietojoukot

1. Metatiedot (taulukot, sarakkeet, mittarit, laskutoimitukset, yhteysmerkkijonot jne.)

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

1. Tiedot

    a. Analysis Services paikallisena ja DirectQuery – Mitään ei tallenneta Power BI -palveluun.

    b. PML – Salataan Azure Blob -säilössä, mutta kaikki parhaillaan Power BI -palvelun Azure Blob -tallennustilassa olevat tiedot käyttävät [Azuren SSE (Storage Service Encryption)](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) -salausta, joka tunnetaan myös palvelinpuolen salauksena. Myös Multi-Geo käyttää SSE-salausta.

    c. Työnnetyt tiedot v1 – Tallennetaan salattuina Azure Blob -säilöön, mutta kaikki parhaillaan Power BI -palvelun Azure Blob -tallennustilassa olevat tiedot käyttävät [Azuren SSE (Storage Service Encryption)](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) -salausta, joka tunnetaan myös palvelinpuolen salauksena. Myös Multi-Geo käyttää SSE-salausta. Työntö tiedot v1 lopetettiin alkaen 2016. 

    d. Työnnetyt tiedot v2 – Tallennetaan salattuina Azuren SQL-tietokantaan.

Power BI käyttää asiakaspuolen salausmenetelmää ja salaa Azuren Blob-säilön CBC (Cipher Block Chaining) -menetelmällä ja AES (Advanced Encryption Standard) -salauksella. Voit [lukea lisätietoja asiakaspuolen salauksesta](https://azure.microsoft.com/documentation/articles/storage-client-side-encryption/).

Power BI toteuttaa tietojen eheyden valvonnan seuraavilla tavoilla:

* Azuren SQL-tietokannassa levossa säilytettävien tietojen osalta Power BI käyttää dbcc:tä, TDE:tä ja yhtenäistä sivun tarkistussummaa osana SQL:n alkuperäisiä tarjouksia.

* Azure Blob -säilössä levossa säilytettävien tietojen osalta Power BI käyttää asiakaspuolen salausta ja HTTPS:ää siirtääkseen tietoja säilöön, joka sisältää eheystarkistuksia tietojen noutamisen yhteydessä. Voit [lukea lisätietoja Azuren Blob -säilön tietoturvasta](https://azure.microsoft.com/documentation/articles/storage-security-guide/).

#### <a name="reports"></a>Raportit

1. Metatiedot (raportin määritys)

   a. Raportit voivat olla joko Office 365:n Excel-raportteja tai Power BI -raportteja. Raportin lajin mukaan metatietoihin pätevät seuraavat asiat:
        
    &ensp;&ensp;a. Excel-raportin metatiedot tallennetaan salattuina SQL Azureen. Metatiedot tallennetaan myös Officeen 365.

    &ensp;&ensp;b. Power BI raportit tallennetaan salattuina Azure SQL-tieto kantaan.

2. Staattiset tiedot

   Staattiset tiedot sisältävät artefakteja, kuten tausta kuvia ja Power BI visualisointeja.

    &ensp;&ensp;a. Jos raportti on luotu Office 365:n Excelillä, mitään ei tallenneta.

    &ensp;&ensp;b. Jos kyseessä on Power BI -raportti, staattiset tiedot tallennetaan Azure Blob -säilöön ja salataan.

3. Väli muisteja

    &ensp;&ensp;a. Jos raportti on luotu Office 365:n Excelillä, mitään ei tallenneta välimuistiin.

    &ensp;&ensp;b. Power BI raportteja varten näytettävien raporttien visualisointien tiedot tallennetaan väli muistiin ja tallennetaan seuraavassa osiossa kuvattuun visuaalisen tietojen väli muistiin.
 

4. Power BI:hin julkaistut alkuperäiset Power BI Desktop (.pbix)- tai Excel (.xlsx) -tiedostot

    Joskus .xlsx- tai .pbix-tiedostojen kopio tai tilannevedos tallennetaan Power BI:n Azure Blob -säilöön, ja tällöin tiedot salataan. Kaikki tällaiset Power BI -palvelun Azure Blob -säilöön tallennetut raportit käyttävät [Azuren SSE (Storage Service Encryption) -salausta](https://docs.microsoft.com/azure/storage/common/storage-service-encryption), joka tunnetaan myös palvelinpuolen salauksena. Myös Multi-Geo käyttää SSE-salausta.

#### <a name="dashboards-and-dashboard-tiles"></a>Koontinäytöt ja koontinäyttöruudut

1. Väli muistit – koonti näytön visualisointien tarvitsemat tiedot tallennetaan yleensä väli muistiin ja tallennetaan seuraavassa osiossa kuvattuun visuaalisen tietojen väli muistiin. Muut ruudut, kuten kiinnitetyt visualisoinnit Excelistä ja SSRS (SQL Server Reporting Services) -palvelut, tallennetaan Azure Blobiin kuvina ja salataan.

2. Staattiset tiedot, jotka sisältävät esimerkiksi tausta kuvia ja Power BI visualisointeja, jotka on tallennettu, salattu, Azure BLOB-säilöön.

Huolimatta käytetyistä salaus menetelmistä, Microsoft hallitsee avain salausta asiakkaiden puolesta.

#### <a name="visual-data-cache"></a>Visuaalisen tietojen väli muisti

Visuaaliset tiedot tallennetaan väli muistiin eri sijainteihin sen mukaan, isännöitääkö tieto joukkoa Power BI Premium kapasiteettia. Tieto joukoissa, joita ei isännöidään kapasiteetissa, visualisoinnin tiedot tallennetaan väli muistiin ja salataan Azure SQL-tieto kannassa. Tieto joukkojen, joiden kapasiteetti on isännöity, visualisointi tiedot voidaan sijoittaa väli muistiin seuraavissa sijainneissa:

* Azure-blob-objektitallennus
* Azure Premium-tiedostot
* Power BI Premium kapasiteetti solmu


### <a name="data-transiently-stored-on-non-volatile-devices"></a>Tilapäisesti ei-väliaikaisiin laitteisiin tallennetut tiedot

Muut kuin pysyvät laitteet ovat laitteita, joiden muisti pysyy muuttumattomana ilman jatkuvaa tehoa. Seuraavassa kuvataan tietoja, jotka on tallennettu tilapäisesti ei-väliaikaisiin laitteisiin. 

#### <a name="datasets"></a>Tietojoukot

1. Metatiedot (taulukot, sarakkeet, mittarit, laskutoimitukset, yhteysmerkkijonot jne.)

2. Jotkin rakenteeseen liittyvät artefaktit voidaan tallentaa tietokonesolmujen levylle rajoitetuksi ajaksi. Jotkin artefaktit voidaan tallentaa salaamattomina myös Azure REDIS Cache -välimuistiin rajoitetuksi ajaksi.

3. Alkuperäisten tietolähteiden tunnistetiedot

    a. Analysis Services paikallisesti – Mitään ei tallenneta.

    b. DirectQuery – Tämä riippuu siitä, luodaanko malli palvelussa suoraan, jolloin se tallennetaan yhteysmerkkijonoon salatussa muodossa, niin että salausavain tallennetaan salaamattomana tekstinä samaan paikkaan (salattujen tietojen rinnalle); vai tuodaanko malli Power BI Desktopista, jolloin tunnistetietoja ei tallenneta ei-väliaikaisiin laitteisiin.

    > [!NOTE]
    > Palvelu puolen mallin luonti ominaisuus lopetettiin 2017 alkaen.

    c. Lähetetyt tiedot – Ei mitään (ei käytettävissä).

    d. PML – Ei mitään (mitään ei tallenneta käsittelysolmuun tai eri tavalla kuin yllä olevassa osiossa **Levossa säilytettävät tiedot** on kuvattu).
4. Tiedot

    Jotkin tieto-artefaktit voidaan tallentaa tietokonesolmujen levylle rajoitetuksi ajaksi.

### <a name="data-in-process"></a>Käsittelyssä olevat tiedot

Tiedot ovat käsittelyssä, kun käyttäjä käyttää tai käsittelee niitä aktiivisesti. Tiedot ovat käsittelyssä esimerkiksi, kun käyttäjä käsittelee tietojoukkoa tai muokkaa koontinäyttöä tai raporttia, kun päivitys suoritetaan tai kun tapahtuu muita mahdollisia tietojen käsittelytapahtumia. Kun jokin tällainen tapahtuma ilmenee ja saa tiedot käsittelyyn, Power BI -palvelun **tietojen rooli** luo muistissa Analysis Services (AS) -tietokannan ja tietojoukko ladataan kyseiseen muistissa olevaan Analysis Services -tietokantaan. Perustuipa tietojoukko DirectQuery-kyselyyn tai ei, AS-tietokantaan ladatut tiedot ovat salaamattomia, jotta niiden käyttö on sallittu **tietojen roolille**, minkä lisäksi ne säilytetään muistissa myöhempää käyttöä varten, kunnes Power BI -palvelu ei enää tarvitse tietojoukkoa. Jos asiakkaalla on Power BI Premium -tilaus, Power BI luo muistiin Analysis Services (AS) -tietokannan asiakkaan erikseen valmisteltuun Power BI -näennäiskoneiden kokoelmaan.

Kun tietoja käytetään (mihin sisältyy tietojen alustava lataus Power BI:hin), Power BI -palvelu voi tallentaa visualisointitiedot välimuistiin salattuun **Azuren SQL-tietokantaan** riippumatta siitä, perustuuko tietojoukko DirectQuery-kyselyyn.

Power BI valvoo käsiteltävänä olevien tietojen eheyttä käyttämällä HTTPS-, TCP/IP- ja TLS-tekniikkaa ja varmistaa, että tiedot salataan ja että tietojen eheys säilyy siirron aikana.

## <a name="user-authentication-to-data-sources"></a>Käyttäjän todentaminen tietolähteissä

Jokainen käyttäjä muodostaa yhteyden kunkin tieto lähteen kirjautumistunnuksen perusteella ja käyttää näitä tunniste tietoja. Käyttäjät voivat luoda sitten kyselyitä, koontinäyttöjä ja raportteja pohjana olevien tietojen perusteella.

Kun käyttäjä jakaa kyselyitä, koontinäyttöjä, raportteja tai mitä tahansa visualisointeja, kyseisten tietojen ja visualisointien käyttöoikeus määräytyy sen mukaan, tukevatko taustalla olevat tietolähteet roolitason suojausta (RLS).

Jos taustalla oleva tietolähde kykenee **Power BI:n roolitason suojaukseen (RLS)**, Power BI -palvelu käyttää kyseisen roolitason suojausta ja käyttäjät, joiden tunnistetiedot eivät riitä pohjana olevien tietojen käsittelyyn (esimerkiksi koontinäytössä, raportissa tai muussa tieto-artefaktissa käytetty kysely), eivät näe sellaisia tietoja, joihin käyttäjän oikeudet eivät riitä. Jos käyttäjän oikeudet pohjana oleviin tietoihin poikkeavat siitä käyttäjästä, joka on luonut koontinäytön tai raportin, visualisoinnit ja muut artefaktit näyttävät vain sellaisia tietoja, joihin käyttäjällä on oikeudet.

Jos tietolähde **ei** käytä roolitason suojausta, Power BI -kirjautumistunnuksia käytetään pohjana olevaan tietolähteeseen, tai jos yhteyden aikana on annettu muut tunnistetiedot, käytetään kyseisiä annettuja tunnistetietoja. Kun käyttäjä lataa Power BI -palveluun tietoja muusta kuin RLS-tietolähteestä, tiedot tallennetaan Power BI:hin niin kuin tämän asiakirjan **Tietojen tallentaminen ja siirtäminen** -osassa kuvataan. Jos kyseessä on muu kuin RLS-tietolähde ja tietoja jaetaan muiden käyttäjien kanssa (esimerkiksi koontinäytössä tai raportissa) tai tiedot päivitetään, tietojen käsittelyyn tai näyttämiseen käytetään alkuperäisiä tunnistetietoja.

![Roolitason suojaus (RLS)](media/whitepaper-powerbi-security/powerbi-security-whitepaper_10.png)

Roolitason suojauksen tietolähteitä ja muun kuin roolitason suojauksen tietolähteitä voidaan verrata nopeasti kuvittelemalla, että Sami luo raportin ja koontinäytön, jotka hän sitten jakaa Aapon ja Riitan kanssa. Jos raportissa ja koontinäytössä käytetyt tietolähteet ovat sellaisista, tietolähteistä, jotka **eivät** tue roolitason suojausta, sekä Aapo että Riitta voivat molemmat nähdä Samin koontinäyttöön sisällyttämät tiedot (jotka on ladattu Power BI -palveluun) ja sekä Aapo että Riitta voivat käsitellä tietoja. Jos Sami sen sijaan luo raportin ja koontinäytön tietolähteistä, jotka tukevat roolitason suojausta, ja jakaa ne sitten Aapon ja Riitan kanssa, Aapon yrittäessä tarkastella koontinäyttöä käy seuraavasti:

1. Koska koontinäyttö on RLS-tietolähteestä, koontinäytön visualisoinneissa näytetään lyhyesti &quot;ladataan&quot;-viesti, kun Power BI -palvelu lähettää tietolähteeseen kyselyn noutaakseen nykyisen tietojoukon, joka on määritetty koontinäytön pohjana olevaan kyselyyn liittyvässä yhteysmerkkijonossa.

2. Tiedot käsitellään ja noudetaan Aapon tunnistetietojen ja roolin perusteella, ja koontinäyttöön ja raporttiin ladataan vain sellaisten tiedot, joihin Aapon käyttöoikeudet riittävät.

3. Koontinäytön ja raportin visualisoinnit näytetään Aapon roolitason perusteella.

Jos Riitta käyttäisi jaettua koontinäyttöä tai raporttia, samat toimet suoritettaisiin hänen roolitasonsa perusteella.

## <a name="power-bi-mobile"></a>Power BI Mobile

Power BI-mobiilisovellus on kokoelma sovelluksia, jotka on suunniteltu kolmelle ensisijaiselle mobiilialustalle: Android, iOS ja Windows Mobile. Power BI Mobile -sovellusten suojausta tulee harkita kahdesta näkökulmasta:

* Laitteiden välinen tietoliikenne
* Laitteessa olevat sovellukset ja tiedot

**Laitteiden välisen tietoliikenteen** osalta kaikki Power BI -mobiilisovellukset ovat yhteydessä Power BI -palveluun sekä käyttävät samaa yhteyttä ja käyttöoikeuksien tarkistusmenetelmiä kuin selaimet; nämä on kuvattu tarkemmin aiemmin tässä raportissa. IOS:n ja Androidin Power BI -mobiilisovellukset tuovat selainistunnon itse sovellukseen, kun taas Windows-mobiilisovellus käyttää välittäjää, joka muodostaa tiedonvälityskanavan Power BI:n kanssa.

Seuraavassa taulukossa selvitetään, mitkä mobiililaitteiden käyttöympäristöt tukevat Power BI Mobilen varmennepohjaista todennusta (CBA):

| **CBA-tuki** | **iOS** | **Android-** | **Windows** |
| --- | --- | --- | --- |
| **Power BI** (palveluun kirjautuminen) | Tuetaan | Tuetaan | Ei tueta |
| **SSRS-ADFS** (yhteys SSRS-palvelimeen) | Ei tueta | Tuetaan | Ei tueta |

Power BI Mobile -sovellukset ovat aktiivisesti yhteydessä Power BI -palvelun kanssa. Telemetrian avulla kerätään mobiilisovelluksen käyttötilastoja ja vastaavaa tietoa, jotka toimitetaan palveluihin, joilla valvotaan käyttöä ja aktiivisuutta; telemetrian tietojen yhteydessä ei lähetetä henkilökohtaisia tietoja.

**Laitteessa oleva Power BI -sovellus** tallentaa laitteeseen tiedot, jotka helpottavat sovelluksen käyttöä:

* Azure Active Directory- ja päivitystunnukset tallennetaan laitteessa suojattuun mekanismiin käyttämällä yleisesti käytettyjä suojausmenetelmiä.

* Tiedot tallennetaan laitteen tallennustilaan, jota sovellus ei suoraan itse salaa.

* Asetukset tallennetaan myös laitteeseen salaamattomina, mutta varsinaisia käyttäjätietoja ei tallenneta.

Power BI Mobilen välimuisti säilyy laitteessa joko kahden viikon ajan tai kunnes sovellus poistetaan, käyttäjä kirjautuu ulos Power BI Mobilesta tai käyttäjä ei onnistu kirjautumaan sisään (jos esimerkiksi tunnuksen voimassaoloaika päättyy tai salasana vaihtuu). Välimuisti sisältää koontinäytöt ja raportit, joita on aiemmin käytetty Power BI Mobile -sovelluksen kautta.

Power BI Mobile -sovellukset eivät käsittele laitteen kansioita. 

Kaikki kolme ympäristöä, joissa Power BI Mobile on käytettävissä, tukevat Microsoft Intune -ohjelmistopalvelua, joka mahdollistaa mobiililaitteiden ja sovellusten hallinnan. Kun Intune on otettu käyttöön ja määritetty, mobiililaitteen tiedot salataan eikä itse Power BI -sovellusta voi asentaa SD-kortille. Lue [lisätietoja Microsoft Intunesta](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="power-bi-security-questions-and-answers"></a>Power BI:n tietoturvaan liittyviä kysymyksiä ja vastauksia

Seuraavat kysymykset ovat yleisiä Power BI:n suojaukseen liittyviä kysymyksiä ja vastauksia. Ne on järjestetty sen mukaan, milloin ne lisätty tähän raporttiin, jotta löytäisit uudet kysymykset ja vastaukset helposti, kun niitä lisätään. Uusimmat kysymykset on lisätty luettelon loppuun.

**Kuinka käyttäjät muodostavat yhteyden tietolähteisiin ja pääsevät käyttämään tietolähteitä Power BI:tä käyttäessään?**

* **Power BI tunniste tiedot ja toimi alueen tunniste tiedot:** Käyttäjät Kirjautu maan sisään Power BI Sähkö posti osoitteella; Kun käyttäjä yrittää muodostaa yhteyden tieto resurssiin, Power BI välittää Power BI kirjautumissähköpostiosoitteen tunniste tietoina. Jos kyseessä on toimialueeseen yhdistetty resurssi (joko paikallinen tai pilvipohjainen), hakemistopalvelu määrittää kirjautumissähköpostiosoitetta vastaavan _käyttäjän ensisijaisen nimen_ ([UPN](https://msdn.microsoft.com/library/windows/desktop/aa380525(v=vs.85).aspx)), joka määrittää, riittävätkö tunnistetiedot sallimaan käytön. Organisaatioille, jotka käyttävät työpohjaisia Sähkö posti osoitteita kirjautuakseen Power BI (sama Sähkö posti osoite, jolla he kirjautuvat työresursseihin, kuten _david@contoso.com_ ), yhdistäminen voi tapahtua saumattomasti. Jos kyseessä on organisaatio, joka ei käyttänyt työpohjaisia Sähkö posti osoitteita (kuten _david@contoso.onmicrosoft.com_ ), hakemiston yhdistäminen on määritettävä, jotta paikallisia resursseja voidaan käyttää Power BI kirjautumistunnusten kanssa.

* **SQL Server Analysis Services ja Power BI:** Organisaation, joka käyttää paikallista SQL Server Analysis Services, Power BI tarjoaa Power BI paikallisen tietoyhdyskäytävän (joka on **yhdyskäytävä**, johon viitataan edellisissä osissa).  Power BI:n paikallinen tietoyhdyskäytävä voi toteuttaa tietolähteissä roolitason suojauksen (RLS). Jos haluat lisätietoja RLS-suojauksesta, katso tämän asiakirjan aiempi osio **Käyttäjien todentaminen tietolähteissä**. Lisä tietoja yhdyskäytävien käyttämisestä on kohdassa [Paikallinen tietoyhdyskäytävä](../connect-data/service-gateway-onprem.md).

  Organisaatiot voivat myös käyttää Kerberosta **kertakirjautumiseen** (SSO) ja muodostaa saumattoman yhteyden Power BI:stä paikallisiin tietolähteisiin, joita voivat olla esimerkiksi SQL Server, SAP HANA ja Teradata. Katso lisätietoja ja määritysvaatimukset artikkelista [**Käytä Kerberosta kertakirjautumiseen Power BI:stä paikallisiin tietolähteisiin**](https://docs.microsoft.com/power-bi/service-gateway-kerberos-for-sso-pbi-to-on-premises-data).

* **Muut kuin toimi alue yhteydet**: tieto yhteyksille, jotka eivät ole toimi alue liitoksia ja jotka eivät ole kykeneviä rooli tason suoja ukseen (RLS), käyttäjän on annettava tunniste tiedot yhteys jakson aikana, joka Power BI sitten välittää yhteyden tieto lähteeseen. Jos käyttöoikeudet riittävät, tiedot ladataan tietolähteestä Power BI -palveluun.

**Miten tietoja siirretään Power BI:hin?**

* Kaikki Power BI:n pyytämät ja välittämät tiedot salataan siirrettäessä, kun HTTPS-yhteys muodostetaan tietolähteestä Power BI -palveluun. Tietopalvelun kanssa muodostetaan suojattu yhteys ja tiedot kulkevat verkossa vasta, kun yhteys on muodostettu.

**Miten Power BI tallentaa välimuistiin raportti-, koontinäyttö- tai mallitietoja, ja tehdäänkö se turvallisesti?**

* Kun tietolähdettä käytetään, Power BI-palvelu suorittaa tämän asiakirjan kohdassa **Tietojen tallennus ja siirtäminen** kuvatun prosessin.

**Tallentavatko asiakkaat verkkosivujen tietoja paikallisesti välimuistiin?**

* Kun selainasiakkaat käyttävät Power BI:tä, Power BI -verkkopalvelimet määrittävät _Cache-Control_-direktiivin arvoksi _no-store_. Tämä _no-store_-direktiivi määrittää, että selaimet eivät tallenna välimuistiin käyttäjän katsomia verkkosivuja eivätkä tallenna verkkosivua asiakkaan välimuistikansioon.

**Entä roolipohjainen suojaus, raporttien tai koonti näyttöjen jakaminen sekä tieto yhteydet? Miten tämä toimii tietojen käytön, koonti näytön tarkastelemisen, raportin käyttö oikeuden tai päivityksen suhteen?**

* Jos kyseessä on **muu kuin roolipohjaista suojausta (RLS)** käyttävä tietolähde ja jos koontinäyttö, raportti tai tietomalli jaetaan muiden käyttäjien kanssa Power BI:n kautta, tiedot ovat sellaisten käyttäjien käytettävissä, joiden kanssa tiedot on jaettu, ja nämä käyttäjät voivat tarkastella ja käsitellä tietoja. Power BI *ei* todenna käyttäjiä uudelleen tietojen alkuperäisestä lähteestä; kun tiedot on ladattu Power BI:hin, lähdetietojen osalta todennettu käyttäjä on vastuussa sen hallinnoinnista, ketkä toiset käyttäjät ja ryhmät voivat tarkastella tietoja.

  Jos tietoyhteyksiä muodostetaan **RLS**-yhteensopivan tietolähteen kanssa, kuten Analysis Services -tietolähteen kanssa, Power BI:n välimuistiin tallennetaan vain koontinäytön tiedot. Aina kun sellaista raporttia tai tietojoukkoa tarkastellaan tai käsitellään Power BI:ssä, joka käyttää RLS-yhteensopivaa tietolähdettä, Power BI -palvelu käsittelee tietolähdettä käyttäjän tunnistetiedoilla saadakseen tiedot, ja jos tunnistetietoihin liittyy riittävät käyttöoikeudet, tiedot ladataan käyttäjälle raporttiin tai tietomalliin. Jos todentaminen epäonnistuu, käyttäjä näkee virheen.

  Jos haluat lisätietoja, katso tämän asiakirjan aiempi osio **Käyttäjien todentaminen tietolähteissä**.

**Käyttäjämme muodostavat yhteyden samoihin tieto lähteisiin koko ajan, joista osa edellyttää tunniste tietoja, jotka eroavat toimi alueen tunniste tiedoillaan. Miten he voivat välttyä syöttämasta näitä tunniste tietoja aina, kun he tekevät tieto yhteyden?**

* Power BI tarjoaa [henkilökohtaisen Power BI -yhdyskäytävän](https://support.powerbi.com/knowledgebase/articles/649846), jonka avulla käyttäjät voivat luoda tunnistetiedot useille eri tietolähteille ja käyttää kyseisiä tunnistetietoja automaattisesti, kun he sitten käsittelevät kutakin tietolähdettä. Jos haluat lisätietoja, katso [Henkilökohtainen Power BI -yhdyskäytävä](https://support.powerbi.com/knowledgebase/articles/649846).

**Miten Power BI -ryhmät toimivat?**

* Power BI -ryhmien avulla käyttäjät voivat nopeasti ja helposti luoda yhteistyönä raporttinäkymiä, raportteja ja tietomalleja vakiintuneissa tiimeissä. Jos esimerkiksi jokin Power BI -ryhmä sisältää kaikki oman lähiryhmäsi käyttäjät, voit tehdä helposti yhteistyötä koko tiimisi kanssa valitsemalla ryhmän Power BI:ssä. Power BI -ryhmät vastaavat Office 365:n universaaleja ryhmiä (joista voit [lukea](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1) ja joita voit [luoda](https://support.office.com/Article/View-create-and-delete-Groups-in-the-Office-365-admin-center-a6360120-2fc4-46af-b105-6a04dc5461c7) ja [hallita](https://support.office.com/Article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)), ja ne käyttävät samaa todentamistapoja kuin mitä Azure Active Directoryssa käytetään tietojen suojaamiseen. Voit [luoda ryhmiä Power BI:ssä](https://support.powerbi.com/knowledgebase/articles/654250) tai luoda universaalin ryhmän Microsoft 365 -hallintakeskuksessa; molemmilla toiminnoilla on sama tulos Power BI:n ryhmien luonnin kannalta.

  Huomaa, että Power BI -ryhmien kanssa jaetut tiedot noudattavat samoja suojausperiaatteita kuin kaikki Power BI:ssä jaetut tiedot. Jos kyseessä on **muu kuin RLS**-tietolähde, Power BI **ei** todenna käyttäjiä uudelleen tietojen alkuperäisestä tietolähteestä, ja kun tiedot on ladattu Power BI:hin, lähdetietojen osalta todennettu käyttäjä on vastuussa sen hallinnoinnista, ketkä toiset käyttäjät ja ryhmät voivat tarkastella tietoja. Jos haluat lisätietoja, katso tämän asiakirjan aiempi osio **Käyttäjien todentaminen tietolähteissä**.

  Voit lukea lisätietoja [ryhmistä Power BI:ssä](https://support.powerbi.com/knowledgebase/articles/654247).

**Mitä portteja paikallinen tietoyhdyskäytävä ja henkilökohtainen yhdyskäytävä käyttävät? Onko olemassa toimi alue nimiä, jotka on sallittava yhdistettävyyttä varten?**

* Yksityiskohtainen vastaus tähän kysymykseen on saatavilla seuraavasta linkistä: [Gateway-portit](/data-integration/gateway/service-gateway-communication#ports)

**Kun käsittelet paikallista tietoyhdyskäytävää, miten palautus avaimia käytetään ja mihin ne tallennetaan? Entä turvallinen tunniste tietojen hallinta?**

* Yhdyskäytävän asentamisen ja määrittämisen aikana järjestelmänvalvoja kirjoittaa yhdyskäytävän **palautusavaimen**. **Palautus avainta** käytetään luomaan vahva **AES** -symmetrinen avain. Myös **RSA** -asymmetrinen avain luodaan samalla kertaa.

    Luodut avaimet (**RSA** ja **AES**) tallennetaan tiedostoon paikallisessa koneessa. Tiedosto on myös salattu. Tiedoston sisällön salauksen voi purkaa vain kyseisellä Windows-koneella, ja vain kyseistä yhdyskäytävän palvelutiliä käyttämällä.

    Kun käyttäjä kirjoittaa tietolähteen tunnistetiedot Power BI-palvelun käyttöliittymään, tunnistetiedot salataan selaimessa julkisella avaimella. Yhdyskäytävä purkaa tunniste tiedot käyttämällä RSA-yksityistä avainta ja salaa ne uudelleen käyttäen AES-symmetristä avainta, ennen kuin tiedot tallennetaan Power BI-palvelu. Tämän prosessin ansiosta Power BI -palvelussa ei koskaan ole salaamattomia tietoja.

**Mitä kommunikaatioprotokollia paikallinen tietoyhdyskäytävä käyttää, ja miten ne on suojattu?**

* Yhdyskäytävä tukee seuraavia kahta kommunikaatioprotokollaa:

  - **AMQP 1,0 – TCP + TLS**: Tämä protokolla edellyttää, että portit 443, 5671-5672 ja 9350-9354 avataan lähtevää viestintää varten. Tätä protokollaa suositellaan, koska sen tietoliikennekustannukset ovat pienemmät.

  - **Https – WebSockets https + TLS-yhteydellä**: Tämä protokolla käyttää vain porttia 443. WebSocket käynnistetään yksittäisellä HTTP CONNECT -viestillä. Kun kanava on muodostettu, tietoliikenne on käytännössä muotoa TCP + TLS. Voit pakottaa yhdyskäytävän käyttämään tätä protokollaa muokkaamalla [paikallista yhdyskäytävää käsittelevässä artikkelissa](/data-integration/gateway/service-gateway-communication#force-https-communication-with-azure-service-bus)kuvattua asetusta.

**Mikä on Azure CDN:n rooli Power BI:ssä?**

* Kuten aiemmin todettiin, Power BI käyttää **Azure Content Delivery Networkia** (CDN) tarpeellisen staattisen sisällön ja tiedostojen jakamiseen käyttäjille aluekohtaisten asetusten perusteella. Tarkemmin sanottuna Power BI -palvelu käyttää useita **CDN**-kohteita, jotta se saa tehokkaasti jaettua tarpeellisen staattisen sisällön ja tiedostot käyttäjille julkisen Internetin kautta. Näitä staattisia tiedostoja ovat tuotelataukset (kuten **Power BI Desktop**, **paikallinen tietoyhdyskäytävä** tai riippumattomien palveluntarjoajien Power BI -sovellukset), selaimen määritystiedostot, joilla alustetaan ja muodostetaan myöhempiä yhteyksiä Power BI -palvelulle, sekä alkuperäinen turvallinen Power BI -kirjautumissivu.

  Ensimmäisen Power BI-palveluyhteyden aikana toimitettujen tietojen perusteella käyttäjän selain muodostaa yhteyden määritettyyn Azure-**sisältöverkkoon** (tai joidenkin tiedostojen yhteydessä **WFE**:hen) ja lataa kokoelman määritettyjä yleisiä tiedostoja, joiden avulla selain voi olla vuorovaikutuksessa Power BI -palvelun kanssa. Selaimen sivu sisältää AAD-tunnuksen, istunnon tiedot, istuntoon liittyvän **Back-End**-klusterin sijainnin sekä joukon tiedostoja, jotka on ladattu Azure **CDN**- ja **WFE **- klusterista Power BI -palvelun selainistunnon ajaksi.

**Power BI visualisointien osalta, onko Microsoft suorittanut mukautetun visuaalisen koodin suojaus-tai yksityisyys arvioinnin ennen kohteiden julkaisemista valikoimaan?**

* Et. On asiakkaan vastuulla tarkistaa mukautettu visualisointikoodi ja päättää, voiko siihen luottaa. Kaikkia mukautettuja visualisointikoodeja käytetään sandbox-ympäristössä, joten mukautetun visualisoinnin virheelliset koodit eivät vaikuta haitallisesti muuhun Power BI -palveluun.

**Lähettävätkö muut Power BI -visualisoinnit tietoja asiakkaan verkon ulkopuolelle?**

* Kyllä. Bing Maps- ja ESRI-visualisoinnit siirtävät tietoja Power BI -palvelun ulkopuolelle kyseisiä palveluita käyttäville visualisoinneille.

**Onko Microsoft tehnyt malli sovelluksille tieto turva-tai tieto suoja-arvioinnin malli sovelluksesta ennen kohteiden julkaisemista valikoimaan?**
* Et. Sovelluksen julkaisija on vastuussa sisällöstä, kun asiakkaan vastuulla on tarkastella ja tarkistaa, luotatko malliin sovelluksen julkaisijaan. 

**Onko olemassa malli sovelluksia, jotka voivat lähettää tietoja asiakas verkon ulkopuolella?**
* Kyllä. Asiakkaan vastuulla on tarkistaa julkaisijan tieto suoja käytäntö ja päättää, asennetaanko malli sovellus vuokraajaan. Lisäksi julkaisijan vastuulla on ilmoittaa sovelluksen toiminnasta ja toiminnoista.

**Entä tietojen suvereniteetti? Voimmeko valmistella vuokraajille tietyillä maantieteellisillä alueilla sijaitsevia tieto keskuksia, jotta tiedot eivät poistu maan rajojen ulkopuolelle?**

* Tietyillä maantieteellisillä alueilla jotkut asiakkaat voivat luoda vuokraajan kansallisessa pilvipalvelussa, jossa tietojen tallennus ja käsittely suoritetaan erillään kaikista muista tietokeskuksista. Kansallisissa pilvipalveluissa suojaus toteutetaan hieman eri tavalla, koska erillinen tietojen valtuuttaja käyttää kansallista Power BI -palvelua Microsoftin puolesta.

  Vaihtoehtoisesti asiakkaat voivat myös määrittää vuokraajan tietyllä alueella, mutta tällaisilla vuokraajilla ei ole erillistä tietojen valtuuttajaa Microsoftin lisäksi. Kansallisten pilvipalveluiden hinnoittelu eroaa yleisesti saatavilla olevasta kaupallisesta Power BI -palvelusta. Lisätietoja Power BI-palvelun käytettävyydestä kansallisissa pilvipalveluissa on artikkelissa [Power BI:n kansalliset pilvipalvelut](https://powerbi.microsoft.com/clouds/).

**Miten Microsoft kohtelee yhteyksiä asiakkaille, joilla on Power BI Premium tila uksia? Ovatko nämä yhteydet erilaisia kuin Premium-Power BI-palvelu?**

* Power BI Premium -tilauksia hankkineiden asiakkaiden yhteydet käyttävät [Azure Business-to-Business (B2B)](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) -valtuutusprosessia, jossa Azure Active Directoryn (AD) avulla toteutetaan käyttöoikeuksien hallinta ja myöntäminen. Power BI käsittelee Power BI Premium -tilaajien yhteydet Power BI Premium -resursseihin samalla tavalla kuin kaikkien Azure AD -käyttäjien.

## <a name="conclusion"></a>Päätelmät

Power BI -palveluarkkitehtuuri perustuu kahteen klusteriin – WFE (Web Front End) -klusteriin ja Back-End-klusteriin. WFE-klusteri vastaa Power BI -palvelun ensiyhteydenotosta ja todentamisesta. Todennuksen jälkeen Back End käsittelee kaiken käyttäjien vuorovaikutuksen. Power BI käyttää Azure Active Directorya (AAD) käyttäjätietojen tallentamiseen ja hallitsemiseen. Se hallitsee tietoja ja metatietoja Azure Blob- ja Azuren SQL-tietokantojen avulla (vastaavassa järjestyksessä).

Tietojen tallennus ja tietojen käsittely Power BI:ssä eroaa sen mukaan, käsitelläänkö tietoja DirectQueryn avulla ja ovatko tietolähteet pilvessä vai paikallisia. Power BI voi myös pakottaa roolitason suojauksen (Role Level Security, RLS), ja se toimii sellaisten yhdyskäytävien kanssa, jotka mahdollistavat pääsyn paikallisiin tietoihin.

## <a name="feedback-and-suggestions"></a>Palaute ja ehdotukset

Arvostamme kaikkea saamaamme palautetta. Toivomme kuulevamme ehdotuksia, jotka liittyvät joko tämän teknisen raportin tai muun Power BI -palveluun liittyvän sisällön parannuksiin, lisäyksiin tai selvennyksiin. Lähetä ehdotuksesi kohteeseen [pbidocfeedback@microsoft.com](mailto:pbidocfeedback@microsoft.com) .

## <a name="additional-resources"></a>Lisäresurssit

Lisää tietoja Power BI -palvelusta on seuraavissa resursseissa.

- [Ryhmät Power BI:ssä](https://support.powerbi.com/knowledgebase/articles/654247)
- [Power BI Desktopin käytön aloittaminen](https://support.powerbi.com/knowledgebase/articles/471664)
- [Power BI REST -ohjelmointirajapinnan yleiskatsaus](https://msdn.microsoft.com/library/dn877544.aspx)
- [Power BI -ohjelmointirajapinnan viite](https://msdn.microsoft.com/library/mt147898.aspx)
- [Paikallinen tietoyhdyskäytävä](../connect-data/service-gateway-onprem.md)
- [Power BI:n kansalliset pilvipalvelut](https://powerbi.microsoft.com/clouds/)
- [Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
- [Kerberoksen käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin](../connect-data/service-gateway-sso-overview.md)
