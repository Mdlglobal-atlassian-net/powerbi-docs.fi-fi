---
title: Optimoi Microsoft Power BI Premium-kapasiteetteja
description: Tässä artikkelissa kuvataan optimoinnin strategioiden Power BI Premium-kapasiteeteille.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/09/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 06712b6bcf57ca84ec03d2c7b99b32ea61ad8c71
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565349"
---
# <a name="optimizing-premium-capacities"></a>Premium-kapasiteetteja optimointi

Premium-kapasiteetin suorituskykyongelmia ilmenee, kun common ensimmäinen tapa on optimoida tai virittää palauttaa hyväksyttävät vasteaika ratkaisuja. Voit välttää Premium lisäkapasiteetin ostamisesta, jollei käytössä perusteet.

Kun Lisää Premium-kapasiteettia on pakollinen, on artikkelissa kuvattu kaksi vaihtoehtoa:

- Skaalaa suuremmaksi, aiemmin Premium-kapasiteetti
- Lisää uusi Premium-kapasiteetti

Lopuksi testaus lähestymistapoja ja Premium-kapasiteetin koon muuttaminen tekevät tässä artikkelissa.

## <a name="best-practices"></a>Parhaat käytännöt

Kun yritettäessä saada parhaan käyttöä ja suorituskykyä, on joitakin suositellut parhaita käytäntöjä, mukaan lukien:

- Omat työtilat-yhteydellä sovellustyötilat.
- Erottamassa liiketoiminnan kannalta tärkeä ja Omatoiminen BI (SSBI) vastaavia tietoja.

  ![Erottamassa liiketoiminnan kannalta tärkeä ja Omatoiminen BI tietoja eri kapasiteetit](media/service-premium-capacity-optimize/separate-capacities.png)

- Jos jaat sisältöä vain Power BI Pro-käyttäjien kanssa, voi olla ei tarvitse varattua kapasiteettia sisällön tallentamista.
- Käytä varattua kapasiteettia, kun saavuttaa tietyn päivityksen aika tai kun tietyt ominaisuudet ovat pakollisia. Esimerkiksi suurten tietojoukkojen tai kanssa sivutettu reporting.

### <a name="addressing-common-questions"></a>Lähestymistavat yleisiin kysymyksiin

Power BI Premium-käyttöönottojen optimointi on monimutkainen aihe välinen tietoliikenne käsityksen, kuormituksen vaatimukset, käytettävissä olevat resurssit ja niiden käytössä käyttö.

Tämä artikkeli käsittelee seitsemän tukikysymyksiin, joka kuvaa mahdolliset ongelmat ja niiden selitykset ja lisätietoja siitä, miten ja ratkaise ne.

### <a name="why-is-the-capacity-slow-and-what-can-i-do"></a>Miksi hidas kapasiteetti on ja mitä voin tehdä?

On useita syitä, jotka voivat osallistua hidas Premium-kapasiteettiin. Tähän kysymykseen tarvitaan edelleen tietoja ymmärtää, mitä tarkoitetaan hidas. Raporteista hidas lataaminen Tai ne epäonnistuvat lataaminen? Ovat raportin visualisointien lataaminen tai päivittää, kun käyttäjä käyttää raportin hitaasti? Päivitetään kestää kauemmin kuin odotettiin tai aiemmin ilmeni?

On saanut käsityksen, syy, voit alkaa tutkimaan asiaa. Seuraavien kuusi kysymysten vastaukset auttavat osoite Lisää ongelmista.

### <a name="what-content-is-using-up-my-capacity"></a>Skaalautuuko käyttää sisältöä?

Voit määrittää **Power BI Premium-kapasiteetin Mittaustietoihin** sovelluksen kapasiteetin suodattaminen ja tarkista työtilan sisältö suoritusmittaukset. On mahdollista Tarkista suorituskyvyn mittarit ja resurssin käyttö viimeisten seitsemän päivän ajalta Premium-kapasiteettiin tallennetut kaikki sisältö tunnin mukaan. Valvonta on usein ensimmäinen vaihe suoritetaan, kun vianmääritys Yleiset huolta tietoja Premium-kapasiteetin suorituskyvystä.

Avainmittarit valvomaan ovat seuraavat:

- Suorittimen keskiarvo ja suuren käyttöaste määrä.
- Keskimääräinen muistin ja suuren käyttöaste määrä ja muistinkäyttö tiettyyn tietojoukoille, dataflows ja sivutettuja raportteja.
- Aktiivisia tietojoukkoja ne ladataan muistiin.
- Keskiarvo- ja kyselyn keston.
- Kyselyiden keskimääräinen odotusaika kertaa.
- Keskimääräinen tietojoukon ja tietovirrassa päivittää kertaa.

Power BI Premium-kapasiteetin Mittaustietoihin sovelluksessa aktiivisen muistin näyttää raportin, joka ei voi poistaa, koska se on ollut käytössä viimeisten kolmen minuutin kuluessa annetut muistin kokonaismäärä. -Päivitys odotusaika suuren piikin voitu Korreloidun suuri ja/tai active tietojoukon kanssa.

**Top 5 keskimääräinen kesto** kaavion korostaa viisi parasta tietojoukkojen, sivutetut raportit ja dataflows kapasiteetin resursseja. Viisi parasta sisällön luettelot on ehdokkaiden tutkimisessa ja mahdollinen optimointia varten.

### <a name="why-are-reports-slow"></a>Miksi raportteja hidastaa?

Seuraavissa taulukoissa on mahdollista ongelmia ja tavalla ja käsitellä niitä.

#### <a name="insufficient-capacity-resources"></a>Kapasiteetti ei riitä resurssit

| Mahdollisia syitä | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Suuren active muisti (mallia ei voi poistaa koska se on käytössä viimeisten kolmen minuutin kuluessa).<br><br> Useita suuren piikkarit kyselyn odottaa kertaa.<br><br> Päivitykseen useisiin suuren piikkarit odottaa kertaa. | Valvoa muistin mittareita \[ [1](#endnote-1)\], ja häätäminen määrät \[ [2](#endnote-2)\]. | Mallin pienentää tai DirectQuery-tilaan. Katso [optimointi mallien](#optimizing-models) tämän artikkelin kohdassa.<br><br> Skaalaa suuremmaksi kapasiteetti.<br><br> Määritä sisällön eri kapasiteettiin. |

#### <a name="inefficient-report-designs"></a>Tehottomia raportin malleja

| Mahdollisia syitä | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Raporttisivujen sisältää liian monta visualisointeja (vuorovaikutteinen suodatus voi käynnistää vähintään yhden kyselyn per visualisointi).<br><br> Visualisointien noutaa enemmän tietoja kuin on tarpeen. | Tarkista raportin suunnitteluista.<br><br> Haastattelun raporttikäyttäjät ymmärtää, miten ne käsitellä raportteja.<br><br> Valvoa tietojoukon kyselyn mittareita \[ [3](#endnote-3)\]. | Uudelleensuunnittelua raportit vähemmän visualisointeja sivulla. |

#### <a name="dataset-is-slow-especially-when-reports-have-previously-performed-well"></a>Tietojoukko on hidas, erityisesti silloin, kun raportteja olet aiemmin suorittanut hyvin

| Mahdollisia syitä | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Tuontitiedot yhä suuria määriä.<br><br> Monimutkaisia tai tehottomia laskutoimituksen logiikka, mukaan lukien rivitason suojauksen roolit.<br><br> Mallia ei ole täysin optimoitu.<br><br> (DQ-LC) Yhdyskäytävän odotusaika.<br><br> Hidas DQ tietolähteen kyselyn vasteaika. | Tarkista mallin malleja.<br><br> Valvo yhdyskäytävän resurssilaskureita. | Katso [optimointi mallien](#optimizing-models) tämän artikkelin kohdassa. |

#### <a name="high-concurrent-report-usage"></a>Suuren samanaikaisten raportin käyttö

| Mahdollisia syitä | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Suuren kyselyn Odota kertaa.<br><br> Suorittimen kylläisyys.<br><br> DQ/LC yhteyden rajoitukset on ylitetty. | Valvo suorittimen käyttöaste \[ [4](#endnote-4)\], kyselyn Odota kertaa ja DQ/LC käyttöä \[ [5](#endnote-5) \] mittareita + kyselyn keston. Jos vaihteleva luku, Määritä samanaikaisuuden ongelmia. | Skaalaa suuremmaksi kapasiteetin tai määrittää sisällön eri kapasiteettiin.<br><br> Uudelleensuunnittelua raportit vähemmän visualisointeja sivulla. |

**Huomautus:**    
<a name="endnote-1"></a>\[1\] keskimääräinen muistinkäyttö (gt) ja suurin muistinkulutus (gt).   
<a name="endnote-2"></a>\[2\] tietojoukon häätöjä.   
<a name="endnote-3"></a>\[3\] tietojoukon kyselyt, tietojoukon keskiarvo kyselyn kesto (ms) tietojoukon Odota määrä ja tietojoukon keskimääräinen odotusaika (ms).   
<a name="endnote-4"></a>\[4\] suuri suorittimen käyttöaste-arvo ja suoritinajan suurin käytön (viimeiset seitsemän päivää).   
<a name="endnote-5"></a>\[5\] DQ/LC suuren käyttöaste määrä ja DQ/LC aikaa suurin käyttö (viimeiset seitsemän päivää).   

### <a name="why-are-reports-not-loading"></a>Miksi raportteja ei ladata?

Raporttien lataaminen epäonnistuu, kun se on että kapasiteetin muisti ei riitä ja on perusteettomasti lämmitettävä. Näin voi käydä, kun kaikki ladata mallit ovat aktiivisesti tehdään kyselyjä samalla, ja sitä ei voi poistaa, ja kaikki päivitystoiminnot on keskeytetty tai Viivästetty. Power BI-palvelu yrittää ladata tietojoukko 30 sekuntia, ja käyttäjälle ilmoitetaan Upeasti syyn ehdotuksen yritä uudelleen myöhemmin.

Ei tällä hetkellä ei ole mittausarvo valvomaan raportin ladataan virheitä. Voit tunnistaa tämän ongelman mahdollisesta valvonta järjestelmämuistin, erityisesti suurin käyttö ja suurin käytön aika. Suuren tietojoukon häätöjä ja pitkä tietojoukon päivityksen keskimääräinen odotusaika voitu ehdottaa, että tämä ongelma on käynnissä.

Tässä tapauksessa vain hyvin toisinaan tämä ole voidaan pitää prioriteetti on ongelma. Raporttikäyttäjät ilmoitetaan, että palvelu on varattu ja että ne yritä uudelleen hetken kuluttua. Tässä tapauksessa liian usein ongelma voidaan ratkaista skaalaus ylös Premium-kapasiteettiin tai määrittämällä sisällön eri kapasiteettiin.

Kapasiteetin järjestelmänvalvojat (ja Power BI-palvelun järjestelmänvalvojat) voit valvoa **kysely epäonnistuu** mittausarvoa, jotta voit määrittää, kun näin tapahtuu. Ne uudelleen myös kapasiteetin palautetaan kaikki toiminnot, jos kyseessä on järjestelmän ylikuormitusta.

### <a name="why-are-refreshes-not-starting-on-schedule"></a>Miksi ovat uudelleen lataukset ei käynnisty aikataulun?

Käynnistä päivitysaikoina taata. Peruuttaminen, Power BI-palvelun priorisoi aina vuorovaikutteisia toimintoja taustan toiminnot kautta. Päivitys on tausta-toiminto, joka voi tapahtua, kun kaksi ehdot täyttyvät:

- Ei tarpeeksi muistia
- Premium-kapasiteetin tueta Samanaikaisten päivitysten määrä ylittyy

Edellytykset eivät täyty, kun päivitys on jonossa, kunnes ehdot ovat hyviä.

Koko päivitystä Peruuta vähintään kaksinkertainen nykyisen tietojoukon muistikoko vaaditaan. Jos tarpeeksi muistia ei ole käytettävissä, päivitystä ei voi aloittaa, kunnes malli häätäminen vapauttaa muistia – Tämä tarkoittaa viiveitä, ennen kuin yksi tai useampi tietojoukko poistuu käytöstä ja voi poistaa.

Peruuta että suurin samanaikaisten päivitysten tuettu määrä on asetettu 1,5 kertaa taustan v-ytimet, pyöristää ylöspäin.

Ajoitettu päivitys epäonnistuu, kun se ei voi aloittaa, ennen kuin seuraava ajoitettu päivitys on aloittaa. Päivitystä käynnistämä manuaalisesti Käyttöliittymän yrittää suorittaa enintään kolme kertaa ennen epäonnistumista.

Kapasiteetin järjestelmänvalvojat (ja Power BI-palvelun järjestelmänvalvojat) voit valvoa **keskimääräinen Päivitä odotusaika (minuuttia)** mittausarvo määrittämään keskimääräinen lag ajoitettu aika – toimintoa alku.

Kun ei yleensä järjestelmänvalvojan prioriteetti muiden ajallaan tiedot päivitetään, varmista, että tarpeeksi muistia on käytettävissä. Tämä saattaa liittyä eristämällä tunnetut tarpeeksi resursseja kuvastaa kapasiteettien tietojoukkoja. On myös mahdollista järjestelmänvalvojat voitu coordinate tietojoukon omistajien lomittaa tai Pienennä ajoitettu päivitysajat minimoimaan rajuille auttamaan. Huomaa, että ei ole mahdollista, jolla järjestelmänvalvoja voi tarkastella päivityksen jono tai noutaa tietojoukon ajoittaa.

### <a name="why-are-refreshes-slow"></a>Miksi hidas päivitykset?

Päivitykset voivat olla hidas - tai vuoksi olla hidas (edellisen kysymyksen common osoitteita).

Kun päivitys on itse asiassa hidas, se johtua useista syistä:

- Riittämätön suorittimen (päivitys voi olla suorittimen paljon).
- Muisti ei riitä, tuloksena päivitys keskeytetään (joka edellyttää, että päivitys on aloittaa alusta milloin ehdot ovat hyviä aloittaa uudelleen).
- Muut kapasiteetin syistä datasource järjestelmän reagoinnin, verkkoviive, virheelliset oikeudet tai yhdyskäytävän siirtomäärän.
- Tietojen määrä - hyvä syy, jotta voit määrittää lisäävän päivityksen, käsitellään tarkemmin alla.

Kapasiteetin järjestelmänvalvojat (ja Power BI-palvelun järjestelmänvalvojat) voit valvoa **keskimääräinen Päivitä kesto (minuuttia)** mittausarvo määrittämään ajan kuluessa, benchmark vertailun ja **keskimääräinen Päivitä odotusaika (minuuttia)** mittareita, jotta voit määrittää keskimääräinen lag välillä keskimääräinen lag ajoitettu aika – toimintoa alku.

Lisäävä päivitys huomattavasti pienentää tietojen päivityksen kesto erityisesti suuria taulukot. On neljä etuja, jotka liittyvät lisäävä päivitys:

- **Päivitykset ovat entistä nopeampia** – vain alijoukon taulukon on oltava lastaus, vähentämään suorittimen ja muistin käyttö ja rinnakkaisuutta voi olla suurempi, useita osioita päivittämisen yhteydessä.
- **Päivitykset suoritetaan vain, kun vaaditaan** -lisäävän päivityksen käytännöt voidaan määrittää vain, kun tiedot ovat muuttuneet lataaminen.
- **Päivitykset ovat entistä luotettavampia** -muuttuvia datasource-järjestelmien lyhyempi käynnissä yhteyksiä ovat pienempi on katkennut.
- **Mallien pysyvät leikkauksen** -lisäävän päivityksen käytännöt voidaan määrittää Poista automaattisesti historia ajan siirtyvän ikkunan ulkopuolella.

Lisätietoja on artikkelissa [lisäävä päivitys on Power BI Premium](service-premium-incremental-refresh.md).

### <a name="why-are-data-refreshes-not-completing"></a>Miksi tietoja päivitetään ei onnistu?

Kun tietojen päivittäminen aloittamista, mutta se ei pysty suorittamaan, se johtua useista syistä:

- Muisti ei riitä, vaikka vain yhtä mallia Premium-kapasiteetissa eli mallin koko on erittäin paljon.
- Muut kapasiteetin syistä datasource järjestelmän on katkennut, virheelliset oikeudet tai yhdyskäytävän virhe.

Kapasiteetin järjestelmänvalvojat (ja Power BI-palvelun järjestelmänvalvojat) voit valvoa **Päivitä virheitä vastaanottaja muisti ei riitä** mittausarvo.

## <a name="optimizing-models"></a>Mallien optimointi

Optimaalisen mallin rakenne on tärkeää toimittaa tehokkaita ja skaalattavien ratkaisu. On kuitenkin tässä artikkelissa on annettava täydellinen laajemmin. Sen sijaan tässä osiossa tarjoaa tärkeiden alueiden meille kun optimointi malleja.

### <a name="optimizing-power-bi-hosted-models"></a>Isännöidyt optimoiminen Power BI-mallit

Premium-kapasiteettiin isännöidyissä malleissa optimointi voidaan saavuttaa osoitteessa datasource(s) ja mallin kerrokset.

Harkitse optimoinnin mahdollisuuksia-tuo mallin:

![Tuo mallin optimoinnin mahdollisuudet](media/service-premium-capacity-optimize/import-model-optimizations.png)

Datasource-kerroksessa:

- Suhteellinen tietolähteitä voi optimoida varmistamiseksi nopein mahdollista päivityksen valmiiksi integrointi tiedot soveltuvat indeksit on otettu käyttöön ja määrittää taulukon osiota, joissa Tasaa lisäävän päivityksen jaksojen materializing laskutoimituksia (sijasta, joka lasketaan malliin taulukot ja sarakkeet) tai lisäämällä laskutoimituksen logiikka näkymiin.
- Ei-relaatiomuotoisiin tietolähteet voidaan valmiiksi integroida suhteellisena myymälät.
- Varmista, että yhdyskäytävät on tarpeeksi resursseja mieluiten tietokoneissa varattua, riittävät verkon kaistanleveyttä ja ovat lähellä toisiaan tietolähteitä.

Mallin: tasolla

- Power Query kyselyn suunnittelua varten voit pienentää tai poistaa monimutkaisia muunnoksia ja erityisesti, joka yhdistää eri tietolähteisiin (tietovarastoissa vuokraajajärjestelmänvalvojaa Extract-muunnos-Load niiden vaiheessa). Myös varmistaa, että asianmukainen tietolähde yksityisyystasot määritetään, että Power BI lataaminen koko tulokset tuottamaan yhdistetyn tulos eri kyselyt voidaan välttää.
- Mallirakenne määrittää ladata tiedot, ja se on suora vaikutus mallin koko. Se on suunniteltu ei lueta tarpeettomat tiedot poistamalla sarakkeita, rivien (etenkin historiatietojen) poistamista tai ladataan yhteenvedetyt tiedot (kustannuksella ladataan yksityiskohtaisia tietoja). Dramaattisia koon pienentäminen voidaan saavuttaa poistamalla kardinaliteetti on suuri-sarakkeet (etenkin tekstisarakkeet), joka ei tallentaa tai Tiivistä erittäin tehokkaasti.
- Mallin kyselyn suorituskyvyn voi parantaa määrittämällä yhteen suuntaan suhteita, ellei sallimaan kaksisuuntaista suodatusta vuoksi. Harkitse myös [CROSSFILTER](https://docs.microsoft.com/dax/crossfilter-function) funktion sijaan kaksisuuntaista suodatusta.
- Koostetaulukoiden saavuttaa nopea kyselyn vastaukset lataamalla valmiiksi yhteenvedetyt tiedot, mutta tämä kasvattaa mallin ja tuloksen koko pidempi päivitysajat. Yleensä koostetaulukoiden varataan erittäin isojen mallien tai koosteen mallin malleja.
- Laskettuja taulukoita ja sarakkeita mallin suurentaa ja pidempi päivitysajat johtaa. Yleensä pienempi tallennustilan koko ja nopeammin päivityksen aika voidaan saavuttaa, kun tiedot on muodostettu tai laskettu tietolähteen. Jos tämä ei ole mahdollista, käyttämällä Power Query mukautettuja sarakkeita tarjota parannettu tallennustilan pakkaus.
- Saatat mahdollisuuden virittää DAX-lausekkeet mittayksiköt ja rivitason suojauksen sääntöjä, Uudelleenkirjoittamisen ehkä logic välttämiseksi kalliita kaavat
- Lisäävä päivitys voi huomattavasti pienentää päivityksen aika ja säästää muistin ja suorittimen. Lisäävä päivitys voidaan määrittää myös Poista malleja leikkauksen säilyttäen historiatietojen.
- Mallin voitu voi uudistaneet kaksi mallit on eri ja ristiriitaiset kyselymallien. Esimerkiksi joitakin raportteja olemassa korkean tason koosteet kaikki historian ja voivat sallii 24 tunnin viive. Muut raportit ovat kuluva, ja sinun myöntää käyttöoikeuksia yksittäisiä tapahtumia. Sen sijaan, että kaikki raportit täyttämiseksi yhden mallin rakenteen optimoitu kaikki kaksi mallien luomiseen.

Harkitse optimoinnin mahdollisuuksia DirectQuery-mallille. Mallin myöntää kyselypyyntöjen pohjana olevaan tietolähteeseen, kuten tietolähteen optimointi on toimittaa reagoiva mallin kyselyt.

 ![DirectQuery-mallille mahdollisuuksia optimointi](media/service-premium-capacity-optimize/direct-query-model-optimizations.png)

Datasource-kerroksessa:

- Tietolähde voi optimoida sen varmistamiseksi, nopein mahdollista kyselyä integroimalla valmiiksi tietoja (joka ei ole mahdollista mallin kerroksessa), soveltuvat indeksit on otettu käyttöön, määrittäminen taulukon osiot materializing yhteenvedetyt tiedot (ja indeksoituja näkymiä), ja säästämällä laskenta määrä. Parhaan käyttökokemuksen saavutetaan, kun läpivientikyselyt täytyy suodattaa vain ja suorittaa Sisäliitos indeksoidun taulukoiden tai näkymien välillä.
- Varmista, että yhdyskäytävät on tarpeeksi resursseja mieluiten tietokoneissa varattua, riittävät verkon kaistanleveyttä ja kaikissa sen tietolähteen lähellä toisiaan.

Mallin: tasolla

- Power Query-kyselyn malleja tulee mieluiten muunnoksia ei - muussa yrittää säilyttää absoluuttisen muunnoksia pienin.
- Mallin kyselyn suorituskyvyn voi parantaa määrittämällä yhteen suuntaan suhteita, ellei sallimaan kaksisuuntaista suodatusta vuoksi. Lisäksi mallisuhteet määritetty olettaa viite-eheys on käytössä, (kun tämä on) ja aiheuttaa datasource-kyselyiden yhteydellä tehokkaampia sisäliitos (ulkoliitos).
- Vältä luomasta Power Query-kyselyn mukautetut sarakkeet tai mallin lasketun sarakkeen - ellei nämä tietolähteessä, kun se on mahdollista.
- Saatat mahdollisuuden virittää DAX-lausekkeet mittayksiköt ja rivitason suojauksen sääntöjä, Uudelleenkirjoittamisen ehkä logic kalliita kaavat välttämiseksi.

Harkitse koosteen mallin optimoinnin mahdollisuuksista. Peruuta koosteen malli mahdollistaa tuonti- ja DirectQuery-taulukot yhdistelmän.

![Koosteen mallin mahdollisuuksia optimointi](media/service-premium-capacity-optimize/composite-model-optimizations.png)

- Yleensä tuonti- ja DirectQuery-malleille optimoinnin käyttöön koosteen tietomallitaulukoita, jotka käyttävät tallennustilan tiloista.
- Yleensä pyrkimällä saavuttaa Tasapainotettu rakenteen määrittämällä dimensiotyyppiä taulukot (joka liiketoimintaentiteettejä) taulukkoina Dual tallennustilan tilan ja fakta-tyyppi (usein suuria taulukot, joka toiminnallisien tietojen) kuin DirectQuery-tallennustilaa. Dual tallennustilan tarkoittaa sekä tuoda ja tallennustilan DirectQuery-tiloista ja Tämä mahdollistaa määrittämään tehokkain tallennustilan käytetään luotaessa alkuperäisen kyselyn tälle läpivientikyselyn Power BI-palvelussa.
- Varmista, että yhdyskäytävät on tarpeeksi resursseja mieluiten tietokoneissa varattua, riittävät verkon kaistanleveyttä ja ovat lähellä toisiaan tietolähteet
- Koosteiden taulukoiden määritetty tuonti-tallennustila voit toimittaa dramaattisia kyselyn suorituskyvyn parannukset, kun käytetään DirectQuery tallennustilan tilan fakta-type-taulukot. Tässä tapauksessa koostetaulukoiden suurentaa mallin ja suurenna päivityksen aika ja hyväksyttävä tarjoa nopeammin kyselyiden on usein.

### <a name="optimizing-externally-hosted-models"></a>Optimointi ulkoisesti isännöity mallit

Optimoinnin monia mahdollisuuksia kuvattu [optimointi Power BI-Isännöidyt mallien](#optimizing-power-bi-hosted-models) osiossa sovelletaan myös analyticsilla Azure Analysis Services- ja SQL Server Analysis Services-malleja. Tyhjennä poikkeuksia ovat ominaisuuksia, jotka eivät ole tuettuja, mukaan lukien yhdistelmämallit ja koostetaulukoiden.

Muita huomioitavia ulkoisesti isännöimä tietojoukkojen on suhteessa Power BI-palvelun isännöinnin tietokanta. Azure Analysis Services Tämä tarkoittaa sitä luominen Azure-resurssi Power BI-vuokraajan (kotialueella) samalla alueella. SQL Server Analysis Services,-IaaS Tämä tarkoittaa, että isännöinnin samalla alueella VM ja paikallisen, se tarkoittaa, että varmistaa tehokasta yhdyskäytävän asennus.

Kesantoala kuin voi olla kiinnostavat Huomaa, että Azure Analysis Services-tietokannat ja SQL Server Analysis Services-taulukkotietokantoja edellyttävät, että niiden ladataan muistiin täysin ja että ne pysyvät olemassa lainkaan tukemaan kyselyä. Power BI-palvelun tavoin täyttäviä voi päivittää, jos mallin on oltava online-tilassa päivityksen aikana tarpeeksi muistia. Toisin kuin Power BI-palvelussa ei ole käsite, että mallit ovat saavuttaneet automaattisesti uloskirjautuminen muistin käytön mukaan. Power BI Premium tarjoaa tehokkaampi lähestymistapa maksimoimaan mallin kyseltäessä kanssa alempaan muistinkäytön vuoksi.

## <a name="capacity-planning"></a>Kapasiteetin suunnitteluun

Premium-kapasiteetin koon määrittää käytettävissä olevan muistin ja suorittimen resursseja ja kapasiteetin rajoissa. Premium-kapasiteetteja määrä on myös merkitystä, kuin luominen useita Premium kapasiteettien voivat auttaa selvittämään kuormituksia toisistaan. Huomaa, että tallennustila on 100 TT: N kapasiteetin solmuun, tämä on todennäköisesti riitä yli tahansa kuormituksen.

Koon ja Premium-kapasiteetteja määrä voi olla hankalaa, erityisesti voit luoda ensimmäisen kapasiteetit. Ensimmäinen vaihe, kun kapasiteetin koon muuttaminen on ymmärtää keskimääräinen kuormituksen, joka vastaa odotettua päivittäisiä käyttö. On tärkeää ymmärtää, että kaikki työnkulut ovat yhtä suuret. Esimerkiksi - liukuväripalkissa - yhdessä päässä 100 samanaikaista käyttäjää käytettäessä yhdelle raporttisivulle, joka sisältää yksittäisen visualisoinnin on voi saavuttaa helposti. – Toisessa päässä sävy - 100 käytettäessä 100 erilaisia raportteja samanaikaisten käyttäjien kunkin 100 visualisointeja raportin sivulla siirtyy tehdä hyvin eri kapasiteetin resurssien vaatimukset.

Kapasiteetin järjestelmänvalvojat vuoksi on otettava huomioon useita tekijät tietyn ympäristön, sisällön ja oletetun käyttötavan. Ohittava tavoitteena on tehokas kapasiteetin käyttö yksityisyyden yhtenäisen kertaa ja hyväksyttävä Odota kertaa häätäminen hinnat. Meille tekijät voivat sisältää:

- **Mallin koko ja tietojen ominaisuudet** -tuontimalleille on oltava täysin ladataan muistiin, jotta kyseltäessä tai päivittämisen. LC/DQ tietojoukkoja voi vaatia merkittävän suoritinajan ja mahdollisesti merkittäviä muistin laskettava monimutkaisia mittareita tai rivitason suojauksen sääntöjä. Muistin ja suorittimen kokoa ja LC/DQ kyselyn siirtomäärän rajoitettu kapasiteetin koon mukaan.
- **Samanaikaisten active mallien** -eri tuontimalleille samanaikaisten kyseltäessä toimittaa parhaan vasteajan ja suorituskyvyn kun ne pysyvät muistissa. Pitäisi olla isännöimään kaikki vahvasti kysely malleja, niin, että heidän päivityksensä että lisämuistia tarpeeksi muistia.
- **Tuo mallipäivityksen** -tyypin (täysi tai lisäävä), kesto ja monimutkaisuuden Power Query-kyselyt ja lasketun taulukon tai sarakkeen logic voi vaikuttaa muistin ja erityisesti suorittimen käyttö. Samanaikaisten päivitykset ovat rajoitetuille kapasiteetin koko (1,5 x backend v-ydintä, pyöristää ylöspäin).
- **Samanaikaisten kyselyiden** -monta samanaikaista kyselyitä voi aiheuttaa ei vastaa raportit kun suoritin tai LC/DQ yhteydet ylittää kapasiteetin rajan. Tämä koskee erityisesti raporttisivujen, jotka sisältävät useita visualisointeja.
- **Dataflows sekä Sivutettujen raporttien** -kapasiteetti on määritetty tukemaan dataflows ja sivutettuja raportteja, että kapasiteetti muistin määritettävissä oleva suurin prosenttiosuus. Muistin kohdistetaan dynaamisesti dataflows, mutta kohdistetaan staattisesti sivutettuja raportteja.

Sen lisäksi, että näihin tekijöihin kapasiteetin järjestelmänvalvojat voit harkita useita kapasiteettien. Useita kapasiteettien sallia kuormitusten eristämisen ja varmistamiseksi prioriteetti kuormituksia on taata resursseja voidaan määrittää. Esimerkiksi kaksi kapasiteettien voidaan luoda liiketoiminnan kannalta tärkeitä kuormituksia erota Omatoiminen BI (SSBI) kuormituksista. Liiketoiminnan kannalta kapasiteetin voidaan ongelmien suuret tarjoaa niiden taatut resurssit, käyttöoikeuden myöntää vain IT-osastosi authoring yrityksen mallit. SSBI kapasiteetin voidaan isännöidä pienempien mallien kasvava määrä liiketoiminta-analyytikkojen myöntää käyttöoikeuden. SSBI kapasiteetin Joskus saatat kohdata kyselyn tai päivitys odottaa, jotka ovat suurin sallittu.

Ajan kuluessa kapasiteetin järjestelmänvalvojat voivat saldo työtilat kaikissa kapasiteettien siirtämällä sisältöä työtilat tai työtilojen välillä ja skaalaamalla kapasiteettien ylös tai alas. Yleensä suurempi mallien isäntä, Skaalaa suuremmaksi, ja suurempi samanaikaisuuden skaalaat ulos.

Peruuta että käyttöoikeus ostaminen antaa vuokraajan käyttöön v-ydintä. Hankinta **P3** tilauksen avulla voidaan luoda sellaisen tai enintään neljä Premium-kapasiteetteja 1 x P3 tai 2 x P2 tai 4 x P1. Lisäksi ennen muuntamista P2-kapasiteetti P3 kapasiteettia, voit kiinnitettävä huomiota jakaminen v-ydintä kaksi P1 kuvastaa kapasiteettien luomiseen.

## <a name="testing-approaches"></a>Vain lähestymistapoja

Kun kapasiteetin koko on päättänyt, testaus voidaan suorittaa luomalla valvotussa ympäristössä. Käytännön ja talous-vaihtoehto on luoda (A-Varastointiyksiköt) Azure-kapasiteetti, molemmilla P1 kapasiteetti on yhtä suuri kuin A4-kapasiteetti, jonka P2 ja P3 kapasiteetit saman kokoinen kuin A5 ja A6-kapasiteetit vastaavasti. Azure-kapasiteetit voidaan luoda nopeasti ja laskutetaan tuntipohjaisesti. Siis testaus on suoritettu, ne voidaan helposti poistaa pysäyttää kerätä julkaisemiesi kustannuksia.

Test-sisältöä voidaan lisätä luoda Azure-kapasiteetti työtilat ja sitten yhden käyttäjän voi suorittaa raportteja realistinen ja edustava kuormituksen kyselyiden luomiseen. Jos tuontimalleille, jokainen malli-päivityksen tulisi suorittaa myös. Valvonnan Työkalut sitten voidaan tarkistaa kaikki mittarit ymmärtää resurssien käytön.

On tärkeää, että testit ovat repeatable. Testaa tulee suorittaa useita kertoja, ja ne pitäisi toimittaa noin saman tuloksen aina, kun. Nämä tulokset keskiarvo voidaan ekstrapoloida ja arvioi kuormituksen true tuotannon olosuhteissa.

Luo ruuhkautuminen testi ohjelmoida kuormitustestauksen sovelluksen Simuloi realistinen kuormituksen. Tarkemmat tiedot siitä, miten tämän ei käsitellä tässä artikkelissa. Lisätietoja saat mallikoodi mukaan lukien viittaavat [ladata vain Power BI-sovellusten Visual Studio kuormitustesti](https://blogs.msdn.microsoft.com/charles_sterling/2018/04/04/webinar-load-testing-power-bi-applications-with-visual-studio-load-test/) verkkoseminaari.

## <a name="acknowledgements"></a>Kuittaussanomien

Tämä artikkeli koskee Peter Myers, tietojen Platform MVP ja riippumattoman BI asiantuntijan kanssa [Bitwise ratkaisuja](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
> [Premium-kapasiteetin skenaarioita](service-premium-capacity-scenarios.md)   
  
Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

||||||