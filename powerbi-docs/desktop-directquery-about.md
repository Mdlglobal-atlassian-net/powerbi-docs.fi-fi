---
title: DirectQueryn käyttäminen Power BI:ssä
description: Lisätietoja DirectQueryn käyttämisestä Power BI:ssä
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 472be555bb4c46da41eb762c1eeae14ef991e742
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2018
ms.locfileid: "34290863"
---
# <a name="using-directquery-in-power-bi"></a>DirectQueryn käyttäminen Power BI:ssä
Voit muodostaa yhteyksiä kaikenlaisiin tietolähteisiin, kun käytät **Power BI Desktopia** tai **Power BI -palvelua**. Lisäksi voit muodostaa näitä yhteyksiä eri tavoin. Voit joko *tuoda* tietoja Power BI:hin, mikä on yleisin tapa hakea, tai voit muodostaa yhteyden tietoihin suoraan niiden alkuperäisessä lähdesäilössä. Tätä tapaa kutsutaan nimellä **DirectQuery**. Tässä artikkelissa kerrotaan **DirectQuerystä** ja sen toiminnoista. Artikkelissa käsitellään seuraavia aiheita:

* DirectQueryn eri yhdistämistavat
* tilanteet, joissa kannattaa käyttää DirectQueryä tuomisen asemesta
* DirectQueryn käytön varjopuolet
* DirectQueryn käytön parhaat käytännöt.

Lyhyesti sanottuna tuomista kannattaa käyttää DirectQueryn asemesta seuraavien parhaiden käytäntöjen mukaisesti:

* Tiedot kannattaa **tuoda** Power BI:hin aina, kun se on mahdollista. Tässä hyödynnetään Power BI:n tehokasta kyselytoimintoa. Lisäksi tämä tarjoaa kattavammat toiminnot ja paremman tietojen käsittelyn.
* Jos et voi saavuttaa tavoitteitasi tuomalla tietoja, tässä tapauksessa voit harkita **DirectQueryn** käyttöä. Jos tiedot esimerkiksi muuttuvat jatkuvasti ja raporttien täytyy aina olla uusimpien tietojen mukaisia, DirectQuery voi olla paras vaihtoehto. DirectQueryn käyttö on kuitenkin yleensä järkevää vain silloin, kun taustalla oleva tietolähde kykenee tarjoamaan vuorovaikutteisia kyselyitä (alle viisi sekuntia) tyypillisille koostekyselyille ja kykenee suoriutumaan kyselykuormituksesta. Lisäksi DirectQueryn rajoitukset tulee huomioida tarkasti, jotta kykenet varmasti saavuttamaan tavoitteesi.

PowerBI:n tarjoamat toiminnot molemmille yhteystavoille (sekä tuomiselle että DirectQuerylle) kehittyvät ajan myötä. Tämä tuo enemmän joustavuutta tuotujen tietojen käytölle, esimerkiksi siten, että tuotuja tietoja voi käyttää useammissa tapauksissa. Lisäksi tällä tavoin päästää eroon joistain DirectQueryn käytön varjopuolista. Parannuksista riippumatta taustalla olevan tietolähteen suorituskyky on aina merkittävä huomioitava seikka. Jos taustalla oleva tietolähde on hidas, DirectQueryn käyttö tämän tietolähteen kanssa ei ole järkevää.

Tässä ohjeartikkelissa käsitellään DirectQueryn käyttöä Power BI:n kanssa, ei SQL Server Analysis Servicesin kanssa. DirectQueryä voi käyttää myös **SQL Server Analysis Servicesin** kanssa. Monet tässä artikkelissa käsitellyt aiheet koskevat myös sen käyttöä, vaikka tärkeitä eroja onkin olemassa. Jos haluat lisätietoja DirectQueryn käytöstä SQL Server Analysis Servicesin kanssa, lue [raportti, jossa käsitellään DirectQueryä SQL Server Analysis Services 2016:ssa](http://download.microsoft.com/download/F/6/F/F6FBC1FC-F956-49A1-80CD-2941C3B6E417/DirectQuery%20in%20Analysis%20Services%20-%20Whitepaper.pdf).  

Tässä artikkelissa keskitytään DirectQueryn suositeltuun työnkulkuun, kun raportti luodaan **Power BI Desktopissa**, mutta käsittelemme myös yhdistämistä suoraan **Power BI -palvelussa**.

## <a name="power-bi-connectivity-modes"></a>Power BI:n yhteystilat
Power BI:llä voi muodostaa yhteyksiä moniin erilaisiin tietolähteisiin, esimerkiksi seuraaviin:

* verkkopalvelut (Salesforce, Dynamics 365 ja muut)
* tietokannat (SQL Server, Access, Amazon Redshift ja muut)
* yksinkertaiset tiedostot (Excel, JSON ja muut)
* muut tietolähteet (Spark, verkkosivustot, Microsoft Exchange ja muut).

Näitä lähteitä käytettäessä tiedot on yleensä mahdollista tuoda Power BI:hin. Jotkin niistä on mahdollista yhdistää myös DirectQuerylla. DirectQueryn tukemat lähteet esitellään tarkemmin ohjeartikkelissa [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md). DirectQuery tukee jatkossa entistä useampia lähteitä. Aiomme keskittyä ensisijaisesti lähteisiin, joiden uskomme toimivan tehokkaasti vuorovaikutteisten kyselyiden kanssa.

**SQL Server Analysis Services** on erikoistapaus. Kun muodostat yhteyden SQL Server Analysis Servicesiin, voit joko tuoda tiedot tai käyttää *reaaliaikaista yhteyttä*.  Reaaliaikaisen yhteyden käyttö muistuttaa DirectQueryä siinä mielessä, että mitään tietoja ei tuoda ja että taustalla olevaan tietolähteeseen lähetetään aina kysely visualisoinnin päivittämiseksi, mutta *reaaliaikainen yhteys* on erilainen monella muulla tavalla. Siksi käytämme siitä termiä *reaaliaikainen yhteys* *DirectQueryn* asemesta.

Kolme eri tapaa yhdistää tietoihin (**tuominen**, **DirectQuery** ja **reaaliaikainen yhteys**) esitellään seuraavissa osioissa.

### <a name="import-connections"></a>Tuontiyhteydet
Kun muodostat yhteyden tietolähteeseen (esimerkiksi SQL Serveriin) **Power BI Desktopin** **Nouda tiedot** -toiminnolla ja valitset **Tuo**, yhteys toimii seuraavasti:

* **Nouda tiedot** -toiminnon ensimmäisellä suorituskerralla valituista taulukoista kukin määrittää kyselyn, joka palauttaa tietyt tiedot (näitä kyselyitä voi muokata ennen tietojen lataamista, esimerkiksi ottamalla käyttöön suodattimia, koostamalla tietoja tai yhdistämällä erillisiä taulukoita).
* Kun tietoja ladataan, kyselyiden määrittämät tiedot tuodaan Power BI:n välimuistiin.
* Kun luot visualisointia **Power BI Desktopissa**, tuoduille tiedoille tehdään kyselyitä. Power BI -säilö varmistaa, että kysely toimii erittäin nopeasti, minkä ansiosta kaikki muutokset visualisointiin näkyvät välittömästi.
* Mitkään taustalla olevien tietojen muutokset eivät näy missään visualisoinneissa. Jos haluat nähdä nämä muutokset, sinun täytyy *päivittää* tiedot, jolloin ne tuodaan uudelleen.
* Kun julkaiset raportin (.pbix-tiedoston) **Power BI -palveluun**, tietojoukko luodaan ja ladataan Power BI -palveluun.  Tuodut tiedot sisältyvät tähän tietojoukkoon. Tämän jälkeen voit määrittää näiden tietojen ajoitetun päivityksen esimerkiksi siten, että tiedot tuodaan uudelleen joka päivä. Alkuperäisen tietolähteen sijainnista riippuen sinun täytyy ehkä määrittää paikallinen tietoyhdyskäytävä.
* Kun avaat olemassa olevan raportin **Power BI -palvelussa** tai luot uutta raporttia, tuoduille tiedoille tehdään uusi kysely, mikä takaa vuorovaikutteisuuden.
* Visualisointeja tai kokonaisia raporttisivuja voi kiinnittää koontinäytön ruutuihin. Ruudut päivitetään automaattisesti aina, kun taustalla olevaa tietojoukkoa päivitetään.  

### <a name="directquery-connections"></a>DirectQuery-yhteydet
Kun muodostat yhteyden tietolähteeseen **Power BI Desktopin** **Nouda tiedot** -toiminnolla ja valitset **DirectQuery**, yhteys toimii seuraavasti:

* Lähde valitaan **Nouda tiedot** -toiminnon ensimmäisen suorittamisen yhteydessä. Suhteellisia tietolähteitä käytettäessä tämä tarkoittaa sitä, että valitset joukon taulukoita, joista jokainen määrittää kyselyn, joka palauttaa loogisesti joukon tietoja. Monidimensioisia tietolähteitä (esimerkiksi SAP BW) käytettäessä valitaan vain lähde.
* Ladattaessa mitään tietoja ei kuitenkaan varsinaisesti tuoda Power BI -säilöön. Sen sijaan järjestelmä lähettää kyselyt taustalla olevaan tietolähteeseen tarvittavien tietojen hakemiseksi siinä vaiheessa, kun luot visualisointia **Power BI Desktopissa**. Visualisoinnin päivittämiseen kuluva aika määräytyy taustalla olevan tietolähteen tehokkuuden perusteella.
* Mitkään taustalla olevien tietojen muutokset eivät näy heti missään olemassa olevissa visualisoinneissa. Tämä edellyttää päivittämistä, jolloin kunkin visualisoinnin tarvittavat kyselyt lähetetään uudelleen, jotta visualisointi voidaan päivittää.
* Kun raportti julkaistaan **Power BI -palvelussa**, tämä tuottaa tietojoukon Power BI -palveluun, aivan kuten tietoja tuodessakin. Tämä tietojoukko *ei kuitenkaan sisällä mitään tietoja*.
* Kun avaat aiemmin luodun raportin **Power BI -palvelussa** tai luot uuden raportin, tarvittavat tiedot haetaan tekemällä jälleen kysely taustalla olevaan tietolähteeseen. Alkuperäisen tietolähteen sijainnista riippuen sinun täytyy ehkä määrittää paikallinen tietoyhdyskäytävä, aivan kuten tietoja päivitettäessä tuontitilassakin.
* Visualisointeja tai kokonaisia raporttisivuja voi kiinnittää koontinäytön ruutuihin. Koontinäytön avaamisen nopeuden takaamiseksi ruudut päivitetään automaattisesti aikataulun mukaisesti (esimerkiksi kerran tunnissa). Voit muokata päivitysväliä esimerkiksi sen mukaan, kuinka usein tiedot muuttuvat tai kuinka tärkeää uusimpien tietojen näkeminen on. Kun avaat koontinäytön, ruudut näyttävät siis tiedot viimeisimmän päivityksen ajankohdalta, eivät välttämättä taustalla olevan tietolähteen kaikkein uusimpien tietojen mukaisesti. Voit päivittää avatun koontinäytön milloin tahansa varmistaaksesi sen ajantasaisuuden.    

### <a name="live-connections"></a>Reaaliaikaiset yhteydet
Kun yhdistät **SQL Server Analysis Servicesiin** (SSAS), voit joko tuoda tiedot tai muodostaa reaaliaikaisen yhteyden valittuun tietomalliin. Jos valitset **Tuo**, sinun täytyy määrittää kysely ulkoiselle SSAS-lähteelle, minkä jälkeen tiedot tuodaan normaalisti. Jos valitset **Yhdistä reaaliajassa**, sinun ei tarvitse määrittää mitään kyselyä, sillä koko ulkoinen malli näytetään kenttäluettelossa. Jos valitset **DirectQuery**, kyselyt lähetetään ulkoiseen SSAS-lähteeseen, kun luot visualisointeja. Toisin kuin DirectQueryn kohdalla, tällä tavalla et kuitenkaan luo uutta *mallia*. Toisin sanoen et siis voi määrittää uusia laskettuja sarakkeita, hierarkioita, suhteita ja niin edelleen. Muodostat sen sijaan yhteyden suoraan ulkoiseen SSAS-malliin.

Edellisessä kappaleessa kuvattu tilanne koskee myös seuraaviin lähteisiin yhdistämistä, mutta niissä ei ole ollenkaan mahdollisuutta tietojen tuomiseen:

* Power BI -tietojoukot (jos esimerkiksi muodostat yhteyden Power BI -tietojoukkoon, joka on luotu aiemmin ja julkaistu palveluun, luodaksesi uuden raportin tiedoista)
* yleiset tietopalvelut.

SSAS-tietolähteitä käyttävät raportit toimivat **Power BI -palvelussa** julkaisemisen jälkeen samankaltaisesti kuin DirectQuery-raportit seuraavin tavoin:

* Kun avaat aiemmin luodun raportin **Power BI -palvelussa** tai luot uuden raportin, taustalla olevaan SSAS-lähteeseen lähetetään kysely (tämä saattaa vaatia paikallista tietoyhdyskäytävää).
* Koontinäytön ruudut päivitetään automaattisesti aikataulun mukaan (esimerkiksi kerran tunnissa tai minkä tahansa määritetyn aikataulun mukaisesti).

Tavoilla on kuitenkin myös merkittäviä eroja. Reaaliaikaisissa yhteyksissä vaaditaan esimerkiksi sitä, että raportin avaavan käyttäjän henkilöllisyys välitetään aina taustalla olevaan SSAS-lähteeseen.

Nyt kun olemme käsitelleet nämä vertailut, voimme keskittyä artikkelin loppuosassa pelkästään **DirectQueryyn**.

## <a name="when-is-directquery-useful"></a>Milloin DirectQuery on hyödyllinen?
Seuraavassa taulukossa kuvataan tilanteita, joissa yhteyden muodostaminen DirectQueryllä voi olla erityisen hyödyllistä. Lisäksi taulukossa kuvataan tilanteita, joissa tietojen jättäminen alkuperäiseen lähteeseen on hyödyllistä. Kuvauksissa käsitellään myös sitä, voiko kyseisen tilanteen toteuttaa Power BI:llä.

| Rajoitus | Kuvaus |
| --- | --- |
| Tiedot muuttuvat miltei jatkuvasti, joten tarvitaan miltei reaaliaikaista raportointia. |Tuotuja tietoja sisältävät mallit voi päivittää tiheimmillään kerran tunnissa. Jos tiedot siis muuttuvat jatkuvasti ja raporttien täytyy näyttää uusimmat tiedot, tietojen tuominen ja ajoitetut päivitykset eivät ehkä täytä tarpeita. Ota huomioon, että tiedot voi myös suoratoistaa suoraan Power BI:hin, mutta tässä tapauksessa tuettujen tietojen määrällä on rajoituksia. <br/> <br/> DirectQueryn käyttö sitä vastoin tarkoittaa, että raportin tai koontinäytön avaaminen tai päivittäminen näyttää aina uusimmat tiedot lähteestä. Lisäksi koontinäytön ruutuja voi päivittää useammin (jopa vain 15 minuutin välein). |
| Tietoja on erittäin paljon. |Jos tietoja on erittäin paljon, kaikkien tietojen tuominen ei missään tapauksessa ole järkevää. DirectQuery sitä vastoin ei vaadi suuren tietomäärän siirtämistä, sillä tiedot pysyvät paikoillaan, niille vain tehdään kyselyitä. <br/> <br/> Jos tietoja on erittäin paljon, tämä voi kuitenkin tarkoittaa myös sitä, että taustalla olevaan tietolähteeseen tehdyt kyselyt toimivat liian hitaasti. Tätä käsitellään tarkemmin tämän artikkelin kohdassa *DirectQueryn käytössä huomioitavia seikkoja*. Lisäksi aina ei tietenkään ole tarpeen tuoda kaikkia tarkkoja tietoja. Tiedot voidaan sen sijaan esikoostaa tuonnin yhteydessä (**kyselyeditorilla** tämä on helppoa). Äärimmäisessä tapauksessa voit jopa tuoda vain juuri ne koostetiedot, joita kussakin visualisoinnissa tarvitaan. Vaikka DirectQuery on siis yksinkertaisin tapa, kun tietoja on paljon, ota kuitenkin aina huomioon se, että koostetietojen tuominen voi olla ratkaisu, jos taustalla oleva tietolähde on liian hidas. |
| Taustalla olevassa tietolähteessä on määritetty suojaussääntöjä. |Kun tiedot tuodaan, Power BI muodostaa yhteyden tietolähteeseen nykyisen käyttäjän tunnistetiedoilla (jotka ovat peräisin Power BI Desktopista) tai tunnistetiedoilla, jotka on määritetty ajoitetulle päivitykselle (tässä tapauksessa tunnistetiedot ovat peräisin Power BI -palvelusta). Kun tällainen raportti sitten julkaistaan ja jaetaan, sinun täytyy olla tarkkana, jotta jaat raportin vain niille käyttäjille, joilla on oikeudet tarkastella tietoja. Voit myös määrittää rivitason suojauksen osana tietojoukkoa. <br/> <br/> Koska DirectQuery tekee aina kyselyn taustalla olevaan lähteeseen, tämä mahdollistaa tämän taustalla olevan lähteen suojausasetusten noudattamisen, mikä on yleensä toivottua. Tällä hetkellä Power BI kuitenkin muodostaa aina yhteyden taustalla olevaan tietolähteeseen samoilla tunnistetiedoilla, joita käytetään tuonnissa. <br/> <br/> Siihen saakka, kunnes Power BI mahdollistaa raportin käyttäjän henkilöllisyyden välittämisen taustalla olevaan lähteeseen, DirectQuery ei tarjoa mitään etuja tietolähteen suojauksen suhteen. |
| Voimassa on tietojen suvereniteettirajoituksia. |Joillain organisaatioilla on käytäntöjä tietojen suvereniteettiin liittyen, mikä tarkoittaa sitä, että tietoja ei voi siirtää organisaation ulkopuolelle. Tuontiin perustuva ratkaisu on tässä tapauksessa tietysti ongelmallinen. DirectQueryä käytettäessä tiedot sitä vastoin pysyvät taustalla olevassa lähteessä. <br/> <br/> On kuitenkin syytä huomioida, että myös DirectQueryä käytettäessä joitain visualisointitason tietoja tallennetaan Power BI -palvelun välimuistiin (ruutujen ajoitetusta päivityksestä johtuen). |
| Taustalla oleva tietolähde on OLAP-lähde, joka sisältää mittayksiköitä. |Jos taustalla oleva tietolähde (esimerkiksi SAP HANA tai SAP Business Warehouse) sisältää *mittayksiköitä*, tietojen tuominen aiheuttaa muita ongelmia. Tämä tarkoittaa sitä, että tiedot tuodaan tietyllä koostamistasolla kyselyn määrittämällä tavalla. Jos sinulla on esimerkiksi mittayksiköt kokonaismyynnille luokan, vuoden ja kaupungin mukaan ja luot sitten visualisoinnin, joka pyytää tietoja korkeammalta koostetasolta (esimerkiksi kokonaismyynti vuoden mukaan), kysely koostaa koostearvoa edelleen. Tämä ei ole ongelma lisääville mittayksiköille (esimerkiksi Summa ja Vähimmäisarvo), mutta aiheuttaa ongelmia mittayksiköille, jotka eivät ole lisääviä (esimerkiksi Keskiarvo ja Erillisten määrä). <br/> <br/> Jotta saat oikeat koostetiedot helposti (tietyn visualisoinnin tarpeiden mukaisesti) suoraan lähteestä, sinun täytyy lähettää kyselyt visualisointikohtaisesti, kuten DirectQueryssä. <br/> <br/> Kun muodostat yhteyden SAP Business Warehouseen (BW), voit käsitellä mittayksiköitä tällä tavalla valitsemalla DirectQueryn. SAP BW:n tukea käsitellään tarkemmin ohjeartikkelissa [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md). <br/> <br/> Kun käytät DirectQueryä SAP HANAn kanssa, järjestelmä käsittelee tällä hetkellä tietolähdettä kuitenkin suhteellisena lähteenä, joten toiminta on samankaltaista kuin tietoja tuotaessa. Tätä käsitellään tarkemmin ohjeartikkelissa [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md). |

Kun otamme huomioon DirectQueryn nykyiset toiminnot Power BI:n kanssa käytettäessä, DirectQueryn käytöstä on siis etua seuraavissa tilanteissa:

* Tiedot muuttuvat miltei jatkuvasti, joten tarvitaan miltei reaaliaikaista raportointia.
* Käsittelet erittäin suurta määrää tietoja, joita ei tarvitse esikoostaa.
* Voimassa on tietojen suvereniteettirajoituksia.
* Lähde on monidimensioinen lähde (esimerkiksi SAP BW), joka sisältää mittayksiköitä.

Ota huomioon, että edellä olevan luettelon tiedot koskevat vain Power BI:n käyttöä. Sinulla on aina mahdollisuus käyttää sen sijasta myös ulkoista SQL Server Analysis Services- tai Azure Analysis Services -mallia, jolla tuot tiedot. Tämän jälkeen voit muodostaa yhteyden tähän malliin Power BI:llä. Tämä tapa edellyttää enemmän osaamista, mutta se on myös joustavampi tapa. Tällä tavoin voit esimerkiksi tuoda paljon suurempia määriä tietoja eikä tietojen päivitysaikataululla ole rajoituksia.

## <a name="implications-of-using-directquery"></a>DirectQueryn käytössä huomioitavia seikkoja
**DirectQueryn** käytöllä voi olla myös negatiivisia vaikutuksia, joita käsitellään tässä osiossa. Jotkin näistä rajoituksista ovat hieman erilaisia käytetystä tietolähteestä riippuen. Kerromme tällaisista tilanteista erikseen. Lisäksi tarjoamme erilliset ohjeartikkelit lähteille, jotka eroavat merkittävästi.  

### <a name="performance-and-load-on-the-underlying-source"></a>Taustalla olevan lähteen suorituskyky ja kuormitus
Kun käytät **DirectQueryä**, yleinen käytettävyys riippuu hyvin pitkälti taustalla olevan tietolähteen tehokkuudesta. Jos jokaisen visualisoinnin päivitys (esimerkiksi osittaja-arvon muuttamisen jälkeen) vie muutaman sekunnin (alle viisi sekuntia), käytettävyys on kohtuullinen, vaikkakin käyttö saattaa tuntua hitaalta verrattuna siihen, kuinka nopeasti järjestelmä toimii, kun tuot tiedot Power BI:hin. Jos lähde on taas niin hidas, että yksittäisten visualisointien päivittäminen vie tätä kauemmin (kymmeniä sekunteja), käytettävyys on erittäin huono. Se voi olla jopa niin huono, että kyselyt aikakatkaistaan.

Taustalla olevan tietolähteen tehokkuuden lisäksi sinun tulee huomioida tarkasti tietolähteelle koituva kuormitus, mikä tietysti usein vaikuttaa tehokkuuteen. Kuten myöhemmin tässä artikkelissa kerromme, jokainen käyttäjä, joka avaa jaetun raportin, ja jokainen koontinäytön ruutu, joka päivitetään säännöllisesti, lähettää ainakin yhden kyselyn per visualisointi taustalla olevaan lähteeseen. Tämä edellyttää sitä, että lähde kykenee suoriutumaan tällaisesta kuormituksesta siten, että käytettävyys pysyy kohtuullisena.

### <a name="limited-to-a-single-source"></a>Yhden lähteen rajoitus
Kun tuot tietoja, voit yhdistää tietoja useista lähteistä yhteen malliin. Näin voit yhdistää helposti esimerkiksi tietoja yrityksen SQL Server -tietokannasta paikallisessa Excel-tiedostossa ylläpidettäviin tietoihin. Tämä ei ole mahdollista DirectQueryä käytettäessä. Kun valitset lähteeksi DirectQuery, voit käyttää tietoja vain tästä yhdestä lähteestä (esimerkiksi yhdestä SQL Server -tietokannasta).

### <a name="limited-data-transformations"></a>Rajoitetut tietomuunnokset
Lisäksi **kyselyeditorilla** tehtävillä tietomuunnoksilla on rajoituksia. Kun tuot tiedot, voit käyttää kehittyneitä muunnostoimintoja, joilla voit helposti puhdistaa tietoja ja muotoilla niitä uudelleen, ennen kuin luot tiedoista visualisointeja (voit esimerkiksi jäsentää JSON-tiedostoja tai pivotoida tietoja sarakkeesta rivimuotoon). Nämä muunnokset ovat rajoitetumpia DirectQueryä käytettäessä. Kun muodostat yhteyden SAP Business Warehousen kaltaiseen OLAP-malliin, et esimerkiksi voi määrittää mitään muunnoksia, vaan koko ulkoinen malli otetaan lähteestä. Jos käytät SQL Serverin kaltaista suhteellista lähdettä, voit silti määrittää joukon muunnoksia per kysely, mutta näitä muunnoksia rajoitetaan suorituskykysyistä. Mikä tahansa tällainen muunnos täytyy ottaa käyttöön jokaisessa kyselyssä taustalla olevaan tietolähteeseen (sen sijaan, että sitä käytettäisiin kerran tietoja päivitettäessä), joten nämä muunnokset on rajoitettu sellaisiin muunnoksiin, jotka voidaan kohtuullisesti kääntää yhdeksi natiivikyselyksi. Jos käytät liian monimutkaista muunnosta, saat virheilmoituksen, jolloin sinun täytyy joko poistaa muunnos tai vaihtaa malli tuontitilaan.

Lisäksi kyselyä, joka saadaan tulokseksi **Nouda tiedot** -valintaikkunasta tai **kyselyeditorista**, käytetään alivalinnassa kyselyissä, jotka luodaan ja lähetetään visualisoinnissa tarvittavien tietojen hakemiseksi. Tämän johdosta kyselyeditorissa määritetyn kyselyn täytyy olla kelvollinen tässä kontekstissa. Tämä tarkoittaa erityisesti sitä, että et voi käyttää kyselyä, joka käyttää yleisiä taulukkolausekkeita tai kutsuu tallennettuja toimintasarjoja.

### <a name="modeling-limitations"></a>Mallinnusrajoitukset
Tässä kontekstissa *mallinnus* tarkoittaa raakatietojen tarkentamista ja täydentämistä, kun luot tietoja käyttävää raporttia. Esimerkkejä mallinnuksesta ovat muun muassa seuraavat:

* suhteiden määrittäminen taulukoiden välillä
* uusien laskelmien (lasketut sarakkeet ja mittayksiköt) lisääminen
* sarakkeiden ja mittayksiköiden piilottaminen sekä nimeäminen uudelleen
* hierarkioiden määrittäminen
* muotoilun määrittäminen, oletusyhteenvedon määrittäminen ja sarakkeen lajittelujärjestyksen määrittäminen
* arvojen ryhmittely tai klusterointi.

Kun käytät **DirectQueryä**, voit edelleen hyödyntää monia näistä mallinnustoiminnoista. Periaate on edelleen se, että voit jalostaa raakatietoja jatkokäytön parantamiseksi. Jotkin mallinnustoiminnot eivät kuitenkaan ole käytettävissä tai niitä on rajoitettu, kun käytät DirectQueryä. Rajoituksien tarkoituksena on yleensä suorituskykyongelmien välttäminen. Kaikille DirectQuery-lähteille yhteiset rajoitukset on lueteltu seuraavassa luettelossa. Yksittäisillä lähteillä voi olla muitakin rajoituksia. Ne kuvataan tarkemmin tämän artikkelin loppupäässä kohdassa *Tietolähdekohtaiset tiedot*.

* **Ei sisäistä päivämäärähierarkiaa:** Kun tuot tiedot, jokaisella päivämääräsarakkeella ja päivämäärän ja kellonajan sarakkeella on oletusarvoisesti käytettävissä sisäinen hierarkia. Jos tuot esimerkiksi myyntitilaustaulukon, jossa on tilauspäivämäärän sarake, ja käytät tilauspäivämäärää visualisoinnissa, voit valita soveltuvan käytettävän tason (vuosi, kuukausi tai päivä). Tämä sisäinen päivämäärähierarkia ei ole käytettävissä DirectQuery-tilaa käytettäessä. Ota kuitenkin huomioon se, että jos taustalla olevassa lähteessä on käytettävissä päivämäärätaulukko (kuten monissa tietovarastoissa on), DAX-aikatietofunktioita voi käyttää normaalisti.
* **Laskettujen sarakkeiden rajoitukset:** Lasketut sarakkeet voivat olla vain rivin sisäisiä. Tämä tarkoittaa sitä, että ne voivat viitata vain saman taulukon muiden sarakkeiden arvoihin ilman mitään koostefunktioita. Lisäksi sallitut DAX-skalaarifunktiot (esimerkiksi LEFT()) rajoitetaan vain niihin, jotka voidaan vain lähettää taustalla olevaan lähteeseen. Tämän johdosta ne siis vaihtelevat lähteen tukemien toimintojen mukaisesti. Funktioita, joita ei tueta, ei näytetä automaattisessa täydennyksessä, kun kirjoitat lasketun sarakkeen DAX-funktiota. Jos annat funktion, jota ei tueta, saat virheilmoituksen.
* **Ei tuke pää- ja alatason DAX-funktioille:** Kun käytät DirectQuery-mallia, et voi käyttää DAX PATH() -perheen funktioita, jotka yleensä käsittelevät pää- ja alatasorakenteet (esimerkiksi tilikaavio tai työntekijähierarkia).
* **Mittayksiköiden oletusrajoitukset:** Mittayksiköissä käytettäviä DAX-funktioita ja -lausekkeita rajoitetaan oletusarvoisesti. Automaattinen täydennys näyttää vain sallitut funktiot. Jos käytät funktiota tai lauseketta, jota ei sallita, saat virheilmoituksen. Tämä johtuu siitä, että mittayksiköt on oletusarvoisesti rajoitettu yksinkertaisiin mittayksiköihin, jotka eivät yksinään todennäköisesti aiheuta mitään suorituskykyongelmia. Edistyneet käyttäjät voivat ohittaa tämän rajoituksen valitsemalla **Tiedosto > Vaihtoehdot ja asetukset > Vaihtoehdot** > **DirectQuery** ja valitsemalla sitten *Salli rajoittamattomat toimenpiteet DirectQuery-tilassa* -asetuksen. Kun tämä asetus on valittu, voit käyttää mitä tahansa DAX-lauseketta, joka on kelvollinen mittayksikölle. Käyttäjien on kuitenkin otettava huomioon se, että jotkin lausekkeet, jotka toimivat erittäin hyvin tietojen tuonnin yhteydessä, voivat hidastaa merkittävästi kyselyitä taustalähteeseen DirectQuery-tilassa.
  
  * Alla olevassa esimerkissä kuvataan oletustoimintaa:
    
    * Voit esimerkiksi luoda mittayksikön, joka laskee myynnin kokonaissumman:
      
          SalesAmount = SUMX(Web_Sales, [ws_sales_price]* [ws_quantity])
    * *Et* voi luoda mittayksikköä, joka sitten laskee keskiarvon kaikkien kohteiden myyntisummalle:
      
          AverageItemSalesAmount = AVERAGEX('Item', [SalesAmount])
    
    Syynä on se, että tällainen mittayksikkö saattaisi heikentää suorituskykyä, jos kohteita olisi erittäin paljon.
* **Laskettuja taulukoita ei tueta:** laskettua taulukkoa ei voi määrittää DAX-lausekkeella DirectQuery-tilassa.
* **Suhteiden suodatus on rajoitettu yhteen suuntaan:** Kun käytät DirectQueryä, et voi määrittää ristisuodatussuunnaksi molempia. Alla olevassa esimerkissä et voi luoda visualisointia, joka näyttää jokaisen asiakkaan sukupuolen (Customer[Gender]) ja kunkin asiakkaan ostamien tuotteiden (Product[Category]) määrän. Tällaisen kaksisuuntaisen suodatuksen käyttöä [käsitellään tässä raportissa](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional cross-filtering in Analysis Services 2016 and Power BI.docx), joka sisältää esimerkkejä SQL Server Analysis Servicesin käytöstä, mutta pääperiaatteet koskevat myös Power BI:tä.
  
  ![](media/desktop-directquery-about/directquery-about_01.png)
  
  Tämäkin rajoitus johtuu suorituskykysyistä. Erityisen tärkeää tämä on silloin, kun määrität rivitason suojauksen osana raporttia, sillä yleinen tapa on käyttää monesta–moneen-suhteita käyttäjien ja niiden kohteiden välillä, joiden käyttöön heillä on oikeudet, ja kaksisuuntaista suodatusta ei ole tarpeen käyttää tämän toteuttamiseksi. DirectQuery-mallien kaksisuuntaista suodatusta tulisi kuitenkin käyttää harkiten ja suorituskyky erityisen tarkasti huomioiden.  
* **Ei klusterointia:** kun käytät DirectQueryä, et voi etsiä ryhmiä automaattisesti klusterointitoiminnon avulla.

### <a name="reporting-limitations"></a>Raportoinnin rajoitukset
DirectQuery-malleissa tuetaan miltei kaikkia raportointitoimintoja. Voit siis käyttää samoja visualisointeja, kunhan taustalla oleva lähde tarjoaa riittävän suorituskyvyn. **Power BI -palvelussa** raportin julkaisemisen jälkeen tarjottavilla muilla toiminnoilla on kuitenkin joitain tärkeitä rajoituksia. Ne kuvataan alla:

* **Nopeita merkityksellisiä tietoja ei tueta:** Power BI:n Nopeat merkitykselliset tiedot -toiminto hakee tietojoukostasi erilaisia alijoukkoja ja hyödyntää kehittyneitä algoritmeja, joiden avulla se pyrkii tunnistamaan mahdollisesti merkityksellisiä tietoja. Tätä toimintoa ei tueta DirectQueryä käytettäessä, koska kyselyiden täytyy olla erittäin suorituskykyisiä.
* **Q&A-toimintoa ei tueta:** Power BI Q&A -toiminnolla voit tutkia tietojasi helppokäyttöisillä luonnollisen kielen toiminnoilla ja hankkia vastauksia kaavioiden sekä kuvaajien muodossa. Tätä toimintoa ei kuitenkaan tueta DirectQueryä käyttävissä tietojoukoissa.
* **Tutki-toiminnon käyttö Excelissä hidastaa todennäköistä käyttöä:** Voit tutkia tietojasi tietojoukon Tutki Excelissä -toiminnolla. Tällä tavalla voit luoda Pivot-taulukoita ja -kaavioita Excelissä. Vaikka tätä toimintoa tuetaankin DirectQueryä käyttävissä tietojoukossa, se toimii yleensä hitaammin kuin visualisointien luominen Power BI:ssä. Jos siis Excelin käyttö on sinulle tärkeää, ota tämä huomioon, kun mietit, kannattaako sinun käyttää DirectQueryä.

### <a name="security"></a>Tietoturva
Kuten aiemmin tässä artikkelissa mainittiin, **DirectQueryä** käyttävä raportti muodostaa aina yhteyden taustalla olevaan tietolähteeseen samoilla kiinteillä tunnistetiedoilla, kun raportti on julkaistu **Power BI -palvelussa**. Ota huomioon, että tämä koskee nimenomaan DirectQueryä, ei reaaliaikaisia yhteyksiä SQL Server Analysis Servicesiin, jotka ovat erilaisia tässä suhteessa. Kun siis julkaiset DirectQuery-raportin, sinun täytyy määrittää heti käytettävän käyttäjän tunnistetiedot. Raportin avaaminen Power BI -palvelussa ennen tätä aiheuttaa vain virheen.

Kun olet määrittänyt käyttäjätunnistetiedot, niitä käytetään *riippumatta siitä, kuka käyttäjä raportin avaa*. Tämä toimii siis täysin samalla tavalla kuin tuotujen tietojen kanssa, sillä jokainen käyttäjä näkee samat tiedot, ellei rivitason suojausta ole määritetty osana raporttia. Siksi raportin jakamisessa täytyy olla tarkkana, jos taustalla olevassa tietolähteessä on määritetty joitain suojaussääntöjä.

### <a name="behavior-in-the-power-bi-service"></a>Toiminta Power BI -palvelussa
Tässä osiossa kerrotaan **DirectQuery**-raportin toiminnasta **Power BI -palvelussa**. Tarkoituksena on, että ymmärrät, kuinka paljon kuormitusta taustatietolähteelle aiheutuu sen mukaan, kuinka monta käyttäjää raportilla on ja kenen kanssa koontinäyttö jaetaan, kuinka monimutkainen raportti on ja onko rivitason suojaus määritetty raportissa.

#### <a name="reports--opening-interacting-with-editing"></a>Raportit: avaaminen, käyttäminen ja muokkaaminen
Kun avaat raportit, kaikki näytettävän sivun visualisoinnit päivitetään. Jokainen visualisointi edellyttää yleensä ainakin yhtä kyselyä taustatietolähteeseen. Jotkin visualisoinnit saattavat edellyttää useita kyselyitä (jos visualisointi esimerkiksi näyttää koostearvot kahdesta erillisestä taulukosta, sisältää monimutkaisemman mittayksikön tai sisältää summia mittayksiköistä, jotka eivät ole lisääviä, kuten Erillisten määrä). Uudelle sivulle siirtyminen päivittää nämä visualisoinnit, minkä tuloksena taustalähteeseen tehdään uusia kyselyitä.

Jokainen käyttäjän toimi raportissa saattaa aiheuttaa visualisointien päivittämisen. Jos esimerkiksi valitset eri arvon osittajassa, järjestelmän täytyy lähettää uudet kyselyt, jotta kaikki tähän liittyvät visualisoinnit päivitetään. Tämä koskee myös visualisoinnin napsauttamista, kun käyttäjä haluaa ristiinkorostaa muita visualisointeja, ja suodattimen vaihtamista.  

Samalla tavalla myös uuden raportin muokkaaminen edellyttää, että kyselyt lähetetään visualisoinnin luomisen jokaisessa vaiheessa.

Jotkin tulokset tallennetaan välimuistiin, jotta visualisointi päivittyy heti, jos tulokset ovat täysin samat. Näitä välimuisteja ei jaeta käyttäjien kesken, jos raportin osana on määritetty mitään rivitason suojauksia.

#### <a name="dashboard-refresh"></a>Koontinäytön päivittäminen
Yksittäisiä visualisointeja tai kokonaisia sivuja voi kiinnittää koontinäyttöön ruutuina. **DirectQuery**-tietojoukkoihin perustuvat ruudut päivitetään tämän jälkeen automaattisesti aikataulun mukaisesti, jolloin päivityksen yhteydessä lähetetään kyselyitä taustatietolähteeseen. Oletusarvoisesti päivitys suoritetaan kerran tunnissa, mutta päivitysvälin voi määrittää tietojoukon asetuksissa (se voi olla jopa vain 15 minuuttia tai jopa viikko tai näiden väliltä).

Jos mallissa ei ole määritetty mitään rivitason suojausta, jokainen ruutu päivitetään kerran, minkä jälkeen tulokset jaetaan kaikille käyttäjille. Jos rivitason suojauksia on määritetty, tällä voi olla suuri kerrannaisvaikutus, sillä jokainen ruutu edellyttää omat kyselynsä taustalähteeseen käyttäjäkohtaisesti.  

Jos sinulla on siis kymmenen ruutua sisältävä koontinäyttö, joka on jaettu sadalle käyttäjälle, joka on luotu **DirectQuery**-tietojoukosta, jossa käytetään rivitason suojausta ja joka on määritetty päivitettäväksi 15 minuutin välein, tämä tarkoittaa sitä, että järjestelmä lähettää taustatietolähteeseen tuhat kyselyä 15 minuutin välein.

Siksi rivitason suojauksen käyttö ja päivitysaikataulu on syytä harkita tarkkaan.

#### <a name="timeouts"></a>Aikakatkaisut
**Power BI -palvelun** yksittäisten kyselyiden aikakatkaisuraja on neljä minuuttia. Jos kysely kestää tätä kauemmin, se vain epäonnistuu. Kuten aiemmin painotimme, DirectQueryn käyttöä suositellaan lähteille, jotka tarjoavat miltei vuorovaikutteisen kyselykäytön, joten tämän rajoituksen tarkoitus on välttää ongelmat liian pitkistä suoritusajoista.

### <a name="other-implications"></a>Muita huomioitavia seikkoja
**DirectQueryn** käytössä tulisi huomioida myös seuraavat yleiset seikat:

* **Jos tiedot muuttuvat, näytettävät tiedot täytyy päivittää, jotta uusimmat tiedot näytetään:** Välimuistien käytöstä johtuen ei ole mitään takeita sille, että visualisointi näyttää aina uusimmat tiedot. Visualisointi voi näyttää esimerkiksi eilisen tapahtumat. Jos osittajaa sitten muutetaan, se saatetaan päivittää näyttämään kahden edellisen päivän tapahtumat, mukaan lukien kaikkein uusimmat tapahtumat. Osittajan palauttaminen alkuperäiseen arvoonsa johtaisi siihen, että se näyttäisi aiemmin välimuistiin tallennetut tiedot, joissa kaikkein uusimmat tapahtumat eivät ole mukana.
  
  Kun valitset Päivitä, kaikki välimuistit tyhjennetään ja kaikki sivun visualisoinnit näyttävät uusimmat tiedot.
* **Jos tiedot muuttuvat, visualisointien välistä johdonmukaisuutta ei voida taata:** Eri visualisointeja voidaan päivittää eri aikoihin riippumatta siitä, ovatko ne samalla sivulla vai eri sivuilla. Jos taustatietolähteen tiedot muuttuvat, sille ei ole mitään takeita, että jokainen visualisointi näyttäisi tiedot täysin samalta ajankohdalta. Koska usein yksittäinen visualisointi edellyttää useita kyselyitä (esimerkiksi tarkempien tietojen ja kokonaissummien hakemiseksi), ei edes yksittäisen visualisoinnin johdonmukaisuutta voida taata. Tämän takaaminen edellyttäisi sitä, että kaikki visualisoinnit päivitettäisiin taustatietolähteestä aina, kun mitä tahansa visualisointia päivitetään, ja lisäksi tämä täytyisi tehdä samanaikaisesti tilannevedoksen eristämisen kaltaisten raskaiden prosessien kanssa.
  
  Tämä ongelma voidaan kuitenkin kiertää suhteellisen tehokkaasti päivittämällä sivun kaikki visualisoinnit valitsemalla Päivitä. On myös syytä huomioida, että vaikka käyttäisit tuontitilaa, siinä on samankaltainen ongelma johdonmukaisuuden takaamisessa, jos tuot tietoja useista taulukoista.
* **Power BI Desktopissa täytyy suorittaa Päivitä-toiminto, jos haluat ottaa metatietomuutokset käyttöön:** Kun raportti julkaistaan, Päivitä-toiminto päivittää raportin visualisoinnit. Jos taustatietolähteen rakenne muuttuu, näitä muutoksia ei oteta automaattisesti käyttöön kenttäluettelon käytettävissä olevissa kentissä. Jos taustalähteestä on siis poistettu taulukoita tai sarakkeita, kysely saattaa epäonnistua päivitettäessä. Kun avaat raportin Power BI Desktopissa ja valitset siinä Päivitä, mallin kentät päivitetään muutosten mukaisesti.
* **Mikä tahansa kysely voi palauttaa enintään miljoona riviä:** Yhdellä taustatietolähteen kyselyllä voi palauttaa enintään miljoona riviä. Tämä rajoitus on kiinteä. Tällä ei yleensä ole käytännöllisiä vaikutuksia, sillä itse visualisoinnit eivät näytä näin montaa pistettä. Tämä rajoitus saattaa kuitenkin tulla vastaan, jos Power BI ei optimoi täysin lähetettäviä kyselyitä ja jos järjestelmä pyytää jotain välitulosta, joka ylittää tämän rajoituksen. Näin voi käydä myös visualisointia luotaessa, kun se ei ole vielä lopullisessa muodossaan. Esimerkiksi asiakkaiden ja kokonaismyynnin sarakkeiden sisällyttäminen ylittäisi tämän rajoituksen ennen suodattimien käyttöä, jos asiakkaita olisi yli miljoona.
  
  Saisit tässä tapauksessa seuraavan virheilmoituksen: ulkoisen tietolähteen kyselyn tulosjoukko on ylittänyt suurimman sallitun koon, joka on 1 000 000 riviä.
* **Tuontitilasta ei voi vaihtaa DirectQuery-tilaan:** Vaikka yleensä onkin mahdollista vaihtaa malli DirectQuery-tilasta tuontitilaan, ota kuitenkin huomioon, että tämä tarkoittaa sitä, että kaikki tarvittavat tiedot on tuotava. Takaisin vaihtaminen ei kuitenkaan ole mahdollista. Pääasiassa tämä johtuu niistä toiminnoista, joita DirectQuery-tila ei tue. DirectQuery-malleja, jotka käyttävät SAP BW:n kaltaisia monidimensioisia lähteitä, ei myöskään voi vaihtaa DirectQuery-tilasta tuontitilaan, koska ulkoisia mittayksiköitä käsitellään täysin eri tavalla.

## <a name="directquery-in-the-power-bi-service"></a>DirectQuery Power BI -palvelussa
Kaikkia **Power BI Desktopin** malleja tuetaan. Jotkin lähteet ovat myös käytettävissä suoraan **Power BI -palvelusta**. Yrityskäyttäjä voi esimerkiksi muodostaa Power BI:llä yhteyden Salesforce-tietoihinsa, jolloin hän saa heti käyttöönsä koontinäytön ilman **Power BI Desktopin** käyttöä.

Palvelussa on suoraan käytettävissä vain kaksi DirectQueryä käyttävää lähdettä:

* Spark
* Azure SQL Data Warehouse.

Suosittelemme kuitenkin erittäin painokkaasti, että mikä tahansa **DirectQueryn** käyttö näiden kahden lähteen kanssa aloitetaan **Power BI Desktopista**. Syynä on se, että kun yhteys tehdään alun perin **Power BI -palvelussa**, sillä on monia rajoituksia. Vaikka aloittaminen Power BI -palvelusta on helppoa, tällä tavalla käytettäessä on monia rajoituksia sille, kuinka tulokseksi saatavia raportteja voi jalostaa (tällä tavalla ei esimerkiksi voi luoda mitään laskelmia, käyttää monia analyysitoimintoja tai edes päivittää metatietoja taustatietolähteen muutosten mukaisiksi).   

## <a name="guidance-for-using-directquery-successfully"></a>Ohjeet DirectQueryn onnistuneeseen käyttöön
Jos aiot käyttää **DirectQueryä**, tästä osiosta saat yleisiä ohjeita käytön onnistumiseen. Tämän osion ohjeet perustuvat aiemmin tässä artikkelissa käsiteltyihin DirectQueryn käyttöön liittyviin huomioitaviin seikkoihin.

### <a name="backend-data-source-performance"></a>Taustatietolähteen suorituskyky
Suosittelemme ehdottomasti tarkistamaan, että yksinkertaisten visualisointien päivitys onnistuu kohtuullisessa ajassa. Päivityksen tulisi onnistua alle viidessä sekunnissa kohtuullisen käytettävyyden takaamiseksi. Jos visualisointien päivittäminen vie yli 30 sekuntia, kohtaat erittäin todennäköisesti ongelmia raportin julkaisemisen jälkeen. Tämä voi johtaa siihen, että ratkaisu ei ole käyttökelpoinen.

Jos kyselyt toimivat hitaasti, sinun kannattaa ensimmäisenä tarkistaa taustalähteeseen lähetettävät kyselyt ja syy sille, miksi kyselyt toimivat hitaasti. Tässä ohjeartikkelissa ei käsitellä tietokantojen optimoinnin monia erilaisia parhaita käytäntöjä kaikkien mahdollisten taustatietolähteiden kanssa, mutta annamme kuitenkin muutamia yleisiä tietokantojen vakiokäytäntöjä, jotka pätevät useimmissa tilanteissa:

* Kokonaislukusarakkeisiin perustuvat suhteet toimivat yleensä paremmin kuin muiden tietotyyppien sarakkeiden liitokset.
* Soveltuvat indeksit on syytä luoda. Yleensä tämä tarkoittaa sarakesäilöindeksien käyttämistä lähteissä, jotka tukevat niitä (esimerkiksi SQL Server).
* Kaikki lähteen tarvittavat tilastot on syytä päivittää.

### <a name="model-design-guidance"></a>Ohjeita mallin suunnitteluun
Huomioi seuraavat seikat, kun määrität mallia:

* **Vältä monimutkaisia kyselyitä kyselyeditorissa.** Kyselyeditorissa luotu kysely käännetään yhdeksi SQL-kyselyksi, joka sitten sisällytetään alivalintaan jokaisessa kyseiseen taulukkoon lähetettävässä kyselyssä. Jos tämä kysely on monimutkainen, jokainen lähetettävä kysely saattaa toimia hitaasti. Voit tarkistaa vaihejoukon varsinaisen SQL-kyselyn valitsemalla kyselyeditorissa viimeisen vaiheen ja valitsemalla sitten pikavalikosta *Näytä natiivi kysely*.
* **Pidä mittayksiköt yksinkertaisina.** Suosittelemme, että ainakin aluksi käytät mittayksiköinä vain yksinkertaisia koosteita. Jos ne toimivat tyydyttävästi, voit määrittää monimutkaisempia mittayksiköitä. Huomioi kuitenkin niiden jokaisen tehokkuus tarkasti.
* **Vältä suhteita lasketuissa sarakkeissa.** Tämä on erityisen tärkeää tietokannoissa, joissa täytyy yhdistää useita sarakkeita. Power BI ei salli tällä hetkellä sitä, että suhde perustuu useisiin sarakkeisiin viiteavaimena/perusavaimena. Yleensä tämän voi kiertää ketjuttamalla sarakkeet yhteen lasketulla sarakkeella ja perustamalla liitoksen sitten tähän. Vaikka tämä kiertotapa toimii kohtuullisesti tuoduilla tiedoilla, **DirectQueryn** kohdalla se tuottaa lausekeliitoksen, joka yleensä estää kaikkien indeksien käytön, mikä heikentää suorituskykyä. Ainoa tapa tämän kiertämiseen on yhdistää useiden sarakkeiden tiedot yhteen sarakkeen taustatietokannassa.
* **Vältä suhteita uniqueidentifier-sarakkeissa.** Power BI ei oletusarvoisesti tue uniqueidentifier-tietotyyppiä. Jos siis määrität suhteen kahden uniqueidentifier-tietotyypin sarakkeen välille, tuloksena on kysely, jossa on liitos, jossa on mukana muuntolause. Yleensä myös tämä johtaa heikkoon suorituskykyyn. Ellei tätä tapausta nimenomaisesti optimoida, ainoa tapa tämän kiertämiseen on luoda sarakkeet eri tietotyypillä taustatietokannassa.
* **Piilota *to*-sarake suhteissa.** Suhteiden *to*-sarakkeen (yleensä *to*-taulukon perusavain) tulisi yleensä olla piilotettuna, jotta sitä ei näytetä kenttäluettelossa ja jotta sitä ei voi käyttää visualisoinneissa. Usein sarakkeet, joihin suhteet perustuvat, ovat itse asiassa *järjestelmäsarakkeita* (esimerkiksi tietovaraston korvaavia avaimia). Näiden sarakkeiden piilottaminen on hyvä käytäntö joka tapauksessa. Jos sarakkeella on merkitys, luo laskettu sarake, joka on näkyvissä ja jossa on yksinkertainen lauseke sille, että sen arvot vastaavat perusavainta. Esimerkki:
  
      ProductKey_PK   (Destination of a relationship, hidden)
      ProductKey (= [ProductKey_PK],   visible)
      ProductName
      ...
  
  Tällä tavalla voit välttää suorituskykyongelmia, joita voi esiintyä muutoin, jos visualisointi sisältää perusavainsarakkeen.
* **Tarkista laskettujen sarakkeiden kaikki käyttö ja tietotyyppimuutokset.** Näiden toimintojen käyttö ei välttämättä ole haitallista, mutta ne aiheuttavat sen, että taustatietolähteeseen lähetetään kyselyitä, jotka sisältävät lausekkeita yksinkertaisten sarakeviittausten asemesta. Tämäkin saattaa johtaa siihen, että indeksejä ei käytetä.  
* **Vältä kaksisuuntaista ristiinsuodatusta suhteissa (esikatseluvaiheessa).**
* **Kokeile *Oleta viite-eheys* -asetusta.** Suhteiden *Oleta viite-eheys* -asetus mahdollistaa sen, että kyselyt voivat käyttää SISÄLIITOS-lausekkeita ULKOLIITOS-lausekkeiden asemesta. Yleensä tämä parantaa kyselyn tehokkuutta, mutta tämä riippuu kuitenkin tietolähteen ominaisuuksista.
* **Älä käytä suhteellista tietojen suodattamista kyselyeditorissa.** Kyselyeditorissa voi määrittää suhteellisen päivämääräsuodatuksen. Voit esimerkiksi suodattaa näkyviin rivit, joiden päivämäärä on edellisen 14 päivän aikana.
  
  ![](media/desktop-directquery-about/directquery-about_02.png)
  
  Tämä kuitenkin käännetään suodattimeksi, joka perustuu kiinteään päivämäärään (kiinteä päivämäärä on kyselyn luomispäivämäärä). Näet tämän tarkistamalla natiivikyselyn.
  
  ![](media/desktop-directquery-about/directquery-about_03.png)
  
  Et miltei varmasti halua tällä toiminnolla tätä. Jos haluat varmistaa, että suodatinta käytetään sen päivän perusteella, jolloin raportti on suoritettu, ota sen sijaan suodatin käyttöön raportissa raporttisuodattimena. Tällä hetkellä tämä tehdään luomalla laskettu sarake, joka laskee edeltävien päivien määrän (DAX DATE() -funktiolla), ja käyttämällä sitten tätä laskettua saraketta suodattimessa.

### <a name="report-design-guidance"></a>Ohjeita raportin suunnitteluun
Kun luot DirectQuery-yhteyttä käyttävää raporttia, noudata seuraavia ohjeita:

* **Harkitse Kyselyn pienentäminen -asetusten käyttöä:** Power BI tarjoaa raportissa asetukset lähetettävien kyselyiden määrän pienentämiseksi. Lisäksi se tarjoaa mahdollisuuden poistaa käytöstä tiettyjä toimintoja, jotka heikentäisivät käytettävyyttä, jos tulokseksi saatavien kyselyiden suorittaminen kestäisi kauan. Pääset näihin asetuksiin **Power BI Desktopissa** valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset** > **Kyselyn pienentäminen**. 

   ![](media/desktop-directquery-about/directquery-about_03b.png)

    Valitsemalla **Kyselyn pienentäminen** -asetuksia voit poistaa ristiinkorostuksen käytöstä koko raportissa. Voit myös näyttää *Käytä*-painikkeen osittajissa ja/tai suodatinvalinnoissa. Tällä tavalla voit tehdä useita osittaja- ja suodatinvalintoja ennen niiden käyttöön ottamista. Tämän ansiosta mitään kyselyitä ei lähetetä, ennen kuin napsautat osittajan **Käytä**-painiketta. Tiedot voidaan suodattaa sitten valintojesi mukaisesti.

    Nämä asetukset ovat käytössä raportissasi, kun käytät sitä **Power BI Desktopissa** ja kun käyttäjäsi käyttävät sitä **Power BI -palvelussa**.

* **Ota suodattimet käyttöön ensin:** Ota aina kaikki suodattimet käyttöön heti, kun aloitat visualisoinnin luomisen. Älä siis esimerkiksi vedä myynnin kokonaissumman ja tuotenimen sarakkeita mukaan ja suodata sitten näkyviin tiettyä vuotta, vaan ota suodatin käyttöön Vuosi-sarakkeessa heti alussa. Tämä johtuu siitä, että visualisoinnin luomisen jokainen vaihe lähettää kyselyn. Vaikka voitkin tehdä toisen muutoksen, ennen kuin ensimmäinen kysely on suoritettu, tämä aiheuttaa silti tarpeetonta kuormitusta taustalähteelle. Kun otat suodattimet käyttöön aikaisessa vaiheessa, nämä välivaiheen kyselyt eivät ole niin raskaita. Jos et ota suodattimia käyttöön aikaisessa vaiheessa, saatat myös ylittää aiemmin mainitun miljoonan rivin rajoituksen.
* **Rajoita sivun visualisointien määrää:** Kun sivu avataan (tai jotain sivun osittajaa tai suodatinta muutetaan), sivun kaikki visualisoinnit päivitetään. Lisäksi samanaikaisesti lähetettävien kyselyiden määrää on rajoitettu. Joten kun visualisointien määrä kasvaa, osa visualisoinneista päivitetään sarjamaisesti, jolloin koko sivun päivittäminen kestää kauemmin. Tästä syystä suosittelemme, että rajoitat yhden sivun visualisointien määrää. Voit käyttää sen sijaan useita yksinkertaisempia sivuja.
* **Harkitse visualisointien välisen vuorovaikutuksen käytöstä poistamista:** Raporttisivun visualisoinneilla voi oletusarvoisesti ristiinsuodattaa ja ristiinkorostaa sivun muita visualisointeja. Jos esimerkiksi valitset ympyräkaaviosta vuoden 1999, pylväskaavio voidaan ristiinkorostaa näyttämään myynnin luokan mukaan vuonna 1999.                                                                  
  
  ![](media/desktop-directquery-about/directquery-about_04.png)
  
  DirectQueryssä tällainen ristiinsuodatus ja ristiinkorostus edellyttää kyselyiden lähettämistä taustalähteeseen. Tällainen vuorovaikutus tulisi siis poistaa käytöstä, jos käyttäjien valintoihin vastaamiseen menisi kohtuuttoman pitkä aika. Tämän vuorovaikutuksen voi poistaa käytöstä joko koko raportissa (kuten yllä kuvattiin *Kyselyn pienentäminen* -asetusten kohdassa) tai tapauskohtaisesti [tämän artikkelin](service-reports-visual-interactions.md) ohjeiden avulla.

Ota yllä mainittujen ehdotusten lisäksi huomioon myös se, että kaikki seuraavista raportointitoiminnoista voivat aiheuttaa suorituskykyongelmia:

* **Mittayksikkösuodattimet:** Mittayksiköitä sisältävät visualisoinnit (tai sarakkeiden koosteet) voivat sisältää suodattimia näille mittayksiköille. Alla olevassa visualisoinnissa näytetään myynnin summa luokan mukaan (SalesAmount by Category) siten, että mukana ovat vain ne luokat, joiden myynti on vähintään 20 miljoonaa.
  
  ![](media/desktop-directquery-about/directquery-about_05.png)
  
  Tämä aiheuttaa sen, että taustalähteeseen lähetetään kaksi kyselyä:
  
  * Ensimmäinen kysely hakee luokat, jotka täyttävät ehdon (Myynti > 20 miljoonaa).
  * Toinen kysely hakee sitten visualisoinnissa tarvittavat tiedot, mukaan lukien luokat, jotka täyttivät WHERE-lausekkeen ehdon.  
  
  Tämä toimii yleensä ihan hyvin, jos luokkia on satoja tai tuhansia, kuten tässä esimerkissä. Suorituskyky voi kuitenkin heikentyä, jos luokkia on paljon enemmän. Itse asiassa kysely epäonnistuu, jos ehdon täyttäviä luokkia on yleensä miljoona. Tämä johtuu aiemmin mainitusta miljoonan luokan rajoituksesta.
* **Ylimmät N -suodattimet:** Lisäsuodatuksella voidaan suodattaa näkyviin vain Ylimmät N -arvot (tai Alimmat N -arvot) järjestyksessä jonkin mittayksikön perusteella. Näin voi sisällyttää yllä olevassa visualisoinnissa mukaan esimerkiksi 10 myynniltään suurinta luokkaa. Myös tämä aiheuttaa sen, että taustalähteeseen lähetetään kaksi kyselyä. Ensimmäinen kysely kuitenkin palauttaa kaikki luokat taustalähteestä, kun taas Ylimmät N -suodattimella näytettävät arvot määritetään palautettujen tulosten pohjalta. Käytetyn sarakkeen kardinaliteetista riippuen tämä voi johtaa suorituskykyongelmiin (tai kyselyn epäonnistumiseen, jos miljoonan rivin raja ylittyy).
* **Mediaani:** Yleensä mikä tahansa kooste (Summan, Erillisten määrä jne.) lähetetään taustalähteeseen. Tämä ei kuitenkaan pidä paikkaansa mediaanin kohdalla, koska taustalähde ei yleensä tue tätä koostetta. Tässä tapauksessa haetaan tarkat tiedot taustalähteestä ja mediaani lasketaan palautetuista tuloksista. Tämä on kohtuullista, kun mediaani lasketaan kohtuullisen pienestä tulosmäärästä, mutta suorituskykyongelmia ilmenee, jos kardinaliteetti on suuri (tai kysely epäonnistuu, jos miljoonan rivin rajoitus ylittyy).  Esimerkiksi maiden asukaslukujen mediaanin hakeminen voi olla kohtuullista, mutta myyntihinnan mediaanin hakeminen tuskin on.
* **Kehittyneet tekstisuodattimet (sisältää-suodatin ja vastaavat):** Kun suodatat tekstisaraketta, lisäsuodatus mahdollistaa sisältää- ja alkaa merkkijonolla -suodattimien ja muiden vastaavien suodattimien käytön. Nämä suodattimet voivat heikentää suorituskykyä joissain tietolähteissä. Etenkään sisältää-oletussuodatinta ei tulisi käyttää, jos haettu arvo on tarkka vastine (on- tai ei ole -suodattimet). Vaikka tulokset voivat olla samoja, todellisista tiedoista riippuen tehokkuus voi poiketa merkittävästi indeksien käytön johdosta.
* **Monivalintaosittajat:** Osittajat sallivat oletusarvoisesti vain yhden valinnan. Monivalinnan salliminen suodattimissa voi aiheuttaa suorituskykyongelmia, koska jos käyttäjät valitsevat useita kohteita osittajassa (esimerkiksi kymmenen tuotetta, joista he ovat kiinnostuneita), jokainen uusi valinta aiheuttaa kyselyiden lähettämisen taustalähteeseen. Vaikka käyttäjä voikin valita seuraavan kohteen ennen kyselyn valmistumista, tämä aiheuttaa lisäkuormitusta taustalähteelle.

* **Harkitse kokonaissummien poistamista käytöstä visualisoinneissa:** Taulukot ja matriisit näyttävät oletusarvoisesti kokonaissummat ja välisummat. Monissa tapauksissa näiden arvojen hakeminen edellyttää erillisten kyselyiden lähettämistä taustalähteeseen. Tämä koskee kaikkia *erillisten määrän* koosteiden suorituksia tai kaikkia tilanteita, joissa käytät DirectQueryä SAP BW:n tai SAP HANAn kanssa. Tällaiset summat kannattaa poistaa käytöstä (**Muotoile**-ruudussa), jos niitä ei tarvitse. 

### <a name="diagnosing-performance-issues"></a>Suorituskykyongelmien vianmääritys
Tässä osiossa annetaan ohjeita suorituskykyongelmien vianmääritykseen sekä siihen, miten voit hankkia lisätietoja raporttien optimoimiseksi.

Suosittelemme painokkaasti, että aloitat aina suorituskykyongelmien vianmäärityksen **Power BI Desktopista**, ei **Power BI -palvelusta**. Yleensä suorituskykyongelmat johtuvat taustatietolähteen suorituskyvystä. Tällaisten ongelmien tunnistaminen ja määrittäminen on helpompaa **Power BI Desktopin** eristetymmässä ympäristössä. Sen avulla myös vältetään alussa tietyt komponentit (esimerkiksi Power BI -yhdyskäytävä). Keskity ongelmien tutkimisessa Power BI -palvelun raporttiin vasta sitten, jos ongelmaa ei löydy Power BI Desktopissa.

Lisäksi suosittelemme ensin ongelmien määrittämistä yksittäisessä visualisoinnissa sivun useiden visualisointien asemesta.

Oletetaan, että nämä vaiheet (tämän osion aiemmassa kappaleessa) on suoritettu ja että olemme nyt **Power BI Desktopissa** sivun yksittäisessä visualisoinnissa, joka toimii edelleen hitaasti. Jos haluat tarkistaa, mitkä kyselyt Power BI Desktop lähettää taustatietolähteeseen, voi tarkastella lähteen tarjoamia jäljitys- ja vianmääritystietoja. Nämä jäljitystiedot voivat sisältää hyödyllisiä tietoja siitä, miten kysely suoritettiin ja miten sitä voi parantaa.

Vaikka lähde ei tarjoaisi tällaisia jäljitystietoja, voit joka tapauksessa tarkistaa Power BI:n lähettämät kyselyt ja niiden suoritusajat. Saat ohjeet tähän alla.

#### <a name="determining-the-queries-sent-by-power-bi-desktop"></a>Power BI Desktopin lähettämien kyselyiden tarkistaminen
**Power BI Desktop** kirjaa oletusarvoisesti tietyn istunnon tapahtuman jäljitystiedostoon, jonka nimi on FlightRecorderCurrent.trc.

Joissain **DirectQuery**-lähteissä tämä loki sisältää kaikki taustatietolähteeseen lähetetyt kyselyt (muut DirectQuery-lähteet tukevat tätä tulevaisuudessa). Seuraaviin lähteisiin lähetetyt kyselyt kirjataan lokiin:

* SQL Server
* Azure SQL -tietokanta
* Azure SQL Data warehouse
* Oracle
* Teradata
* SAP HANA.

Jäljitystiedosto löytyy nykyisen käyttäjän **AppData**-kansiosta:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces

Pääset sinne helposti valitsemalla **Power BI Desktopissa** **Tiedosto > Asetukset ja vaihtoehdot > Asetukset** > **Diagnostiikka**. Näyttöön avautuu seuraava valintaikkuna:

![](media/desktop-directquery-about/directquery-about_06.png)

Kun valitset **Diagnostiikka-asetukset**-kohdasta *Avaa jäljityskansio*, seuraava kansio avautuu:

    \<User>\AppData\Local\Microsoft\Power BI Desktop\Traces

Siirry tämän kansion yläkansioon. Näet siellä *AnalysisServicesWorkspaces*-kansion, joka sisältää yhden työtila-alikansion jokaiselle avoimelle **Power BI Desktop** -esiintymälle. Näiden alikansioiden nimen lopussa on kokonaisluku, esimerkiksi *AnalysisServicesWorkspace2058279583*.

Tämän kansion sisällä on *\\Data*-alikansio. Se sisältää nykyisen Power BI -istunnon jäljitystiedoston FlightRecorderCurrent.trc. Power BI Desktop -istuntoa vastaava työtilakansio poistetaan, kun istunto lopetetaan.

Voit lukea jäljitystiedostoja **SQL Server Profiler** -työkalulla, jonka voit ladata maksutta osana **SQL Server Management Studioa**. Voit hankkia sen [täältä](https://msdn.microsoft.com/library/mt238290.aspx).

Kun olet ladannut ja asentanut **SQL Server Management Studion**, suorita **SQL Server Profiler**.

![](media/desktop-directquery-about/directquery-about_07.png)

Avaa jäljitystiedosto seuraavasti:

1. Valitse **SQL Server Profilerissa** **File > Open > Trace file**.
2. Anna tällä hetkellä auki olevan Power BI -istunnon jäljitystiedoston polku. Se voi olla esimerkiksi seuraava:
   
         C:\Users\<user>\AppData\Local\Microsoft\Power BI Desktop\AnalysisServicesWorkspaces\AnalysisServicesWorkspace2058279583\Data
3. Avaa FlightRecorderCurrent.trc.

Näet kaikki nykyisen istunnon tapahtumat. Alla olevassa esimerkissä on korostettu tietyt tapahtumat. Jokaisella ryhmällä on seuraavat:

* Niissä on *Query Begin*- ja *Query End* -tapahtuma, joista näet käyttöliittymän luoman DAX-kyselyn (esimerkiksi visualisoinnista tai luettelon arvojen täyttämisestä suodatinkäyttöliittymästä) alkamis- ja päättymisajankohdan.
* Niissä on ainakin yksi pari *DirectQuery Begin*- ja *DirectQuery End* -tapahtumia, joista näet taustatietolähteeseen lähetetyn kyselyn, kun DAX-kysely suoritettiin.

Ota huomioon, että useita DAX-kyselyitä voidaan suorittaa rinnakkain, joten eri ryhmien tapahtumat voivat olla limittäisiä. Niissä on ActivityID-arvo, jonka avulla voit tarkistaa, mitkä tapahtumat kuuluvat samaan ryhmään.

![](media/desktop-directquery-about/directquery-about_08.png)

Muita huomionarvoisia sarakkeita ovat seuraavat:

* **TextData:** Nämä ovat tapahtuman tekstitiedot. Query Begin- ja Query End -tapahtumilla tämä on DAX-kysely. DirectQuery Begin- ja DirectQuery End -tapahtumilla tämä on taustalähteeseen lähetetty SQL-kysely. Valitun tapahtuman TextData näytetään myös alhaalla olevalla alueella.
* **EndTime:** tämä on tapahtuman päättymisaika.
* **Duration:** tämä ilmaisee DAX- tai SQL-kyselyn suoritusajan millisekunteina.
* **Error:** Tämä ilmaisee, aiheuttiko tapahtuma virheen. Jos tapahtuma aiheutti virheen, tapahtuma näytetään punaisena.

Ota huomioon, että yllä olevassa kuvassa joitain vähemmän kiinnostavia sarakkeita on kavennettu, jotta kiinnostavat sarakkeet näkyvät paremmin.

Suosittelemme seuraavaa tapaa mahdollisten suorituskykyongelmien määrittämiseen jäljitystietojen avulla:

* Avaa yksi **Power BI Desktop** -istunto, jotta sinulla ei ole useita työtilakansioita.
* Suorita **Power BI Desktopissa** toiminnot, joita haluat tutkia. Suorita niiden lisäksi myös muutama muu toiminto. Näin varmistat, että tapahtumat, joita haluat tutkia, kirjataan varmasti jäljitystiedostoon.
* Avaa **SQL Server Profiler** ja tutki jäljitystiedostoa aiemmin annettujen ohjeiden mukaisesti. Muista, että jäljitystiedosto poistetaan, kun suljet **Power BI Desktopin**. Ota huomioon myös se, että Power BI Desktopin toiminnot eivät näy heti: sulje jäljitystiedosto ja avaa se uudelleen, jotta näet uudet tapahtumat.
* Pidä yksittäiset istunnot kohtuullisen pieninä (kymmenien sekuntien tapahtumat, ei satojen), jotta jäljitystiedoston lukeminen on helpompaa. Koska jäljitystiedoston koko on rajoitettu, erittäin pitkässä istunnossa et välttämättä näe jäljitystiedostosta istunnon alun tapahtumia.

#### <a name="understanding-the-form-of-query-sent-by-power-bi-desktop"></a>Power BI Desktopin lähettämän kyselyn tulkitseminen
**Power BI Desktopin** luomissa ja lähettämissä kyselyissä käytetään yleensä alivalintoja jokaiselle viitatulle taulukolle: alivalinta määritetään **kyselyeditorissa** määritetyn kyselyn mukaisesti. Otetaan esimerkiksi seuraavat TPC-DS-taulukot SQL Serverissä:

![](media/desktop-directquery-about/directquery-about_09.png)

Esimerkkikysely on seuraava:

![](media/desktop-directquery-about/directquery-about_10.png)

Tämä kysely tuottaa seuraavan visualisoinnin:

![](media/desktop-directquery-about/directquery-about_11.png)

Kun päivität tämän visualisoinnin, tämä tuottaa SQL-kyselyn, joka näytetään seuraavan kappaleen alla. Kuten näet, siinä on kolme alivalintaa (Web Sales, Item ja Date_dim), joista kukin palauttaa kaikki vastaavan taulukon sarakkeet, vaikka visualisoinnissa viitataan todellisuudessa vain neljään sarakkeeseen. Nämä alivalintojen kyselyt (ne näytetään harmaalla taustalla) ovat tarkka tulos kyselyille, jotka on määritetty **kyselyeditorissa**. Alikyselyiden tällaisen käytön ei ole havaittu vaikuttavan suorituskykyyn tietolähteissä, joita DirectQuery tähän mennessä tukee. SQL Serverin kaltaiset tietolähteet yksinkertaisesti optimoivat pois viittaukset muihin sarakkeisiin.

Yksi syy sille, miksi Power BI käyttää tätä tapaa, on se, että käytetty SQL-kysely voidaan tarjota suoraan analyytikolle, joten sitä käytetään tarjottuna ilman yrityksiä kirjoittaa sitä uudelleen.

![](media/desktop-directquery-about/directquery-about_12.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä artikkelissa kuvataan **DirectQueryn** niitä osa-alueita, jotka ovat yhteisiä kaikille tietolähteille. Tietyillä yksittäisillä lähteillä on kuitenkin tiettyjä omia tärkeitä huomioitavia seikkojaan. Saat lisätietoja eri lähteistä seuraavista ohjeartikkeleista:

* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)

Saat lisätietoja **DirectQuerystä** seuraavista resursseista:

* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)

