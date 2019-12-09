---
title: Microsoft Power BI Premium -kapasiteettien optimointi
description: Kuvailee Power BI Premium -kapasiteettien optimointistrategioita.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/09/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 0486abd448158baafeaac3047bcb7b461470bac9
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74699149"
---
# <a name="optimizing-premium-capacities"></a>Premium-kapasiteettien optimointi

Kun Premium-kapasiteetin suorituskykyyn liittyvä ongelma tulee esiin, yleinen ensimmäinen menettelytapa on optimoida tai hienosäätää ratkaisuja hyväksyttävien vasteaikojen palauttamiseksi. Ajatuksena on välttää ylimääräisen Premium-kapasiteetin hankkimista, ellei se ole perusteltua.

Kun ylimääräinen Premium-kapasiteetti on tarpeen, tässä artikkelissa kerrotaan kahdesta vaihtoehdosta:

- Nykyisen Premium-kapasiteetin suurentaminen
- Uuden Premium-kapasiteetin lisääminen

Lopuksi tämän artikkelin lopussa testataan menettelytapoja ja Premium-kapasiteetin koon muuttamista.

## <a name="best-practices"></a>Parhaat käytännöt

Parhaan mahdollisen käyttökokemuksen ja suorituskyvyn saamiseksi suosittelemme esimerkiksi seuraavia parhaita käytäntöjä:

- Työtilojen käyttäminen henkilökohtaisten työtilojen sijaan.
- Liiketoiminnan kannalta tärkeän ja omatoimisen BI:n (SSBI:n) erottaminen eri kapasiteetteihin.

  ![Liiketoiminnan kannalta tärkeän ja omatoimisen BI:n (SSBI:n) erottaminen eri kapasiteetteihin](media/service-premium-capacity-optimize/separate-capacities.png)

- Jos sisältöä jaetaan vain Power BI Pro -käyttäjien kanssa, sisältöä ei välttämättä tarvitse tallentaa erilliseen kapasiteettiin.
- Käytä erillisiä kapasiteetteja, kun haluat saavuttaa tietyn päivitysajan tai kun tiettyjä ominaisuuksia vaaditaan. Näin voi olla esimerkiksi suurten tietojoukkojen tai sivutettujen raporttien kohdalla.

### <a name="addressing-common-questions"></a>Yleisiin kysymyksiin vastaaminen

Power BI Premium -käyttöönottojen optimoiminen on monimutkainen aihe, jota varten pitää ymmärtää kuormitusvaatimuksia, käytettävissä olevia resursseja ja niiden tehokasta käyttöä.

Tässä artikkelissa käsitellään seitsemää yleistä tukeen liittyvää kysymystä, kuvataan mahdollisia ongelmia ja selityksiä sekä annetaan tietoja niiden tunnistamiseksi ja ratkaisemiseksi.

### <a name="why-is-the-capacity-slow-and-what-can-i-do"></a>Miksi kapasiteetti on hidas ja mitä voin tehdä?

On monia syitä, jotka voivat vaikuttaa hitaaseen Premium-kapasiteettiin. Tämä kysymys edellyttää lisätietoja, jotta ymmärretään, mitä hitaalla tarkoitetaan. Onko raporttien lataaminen hidasta? Vai eikö niiden lataaminen onnistu? Latautuvatko tai päivittyvätkö raportin visualisoinnit hitaasti, kun käyttäjät ovat vuorovaikutuksessa raportin kanssa? Kestääkö päivittäminen odotettua kauemmin tai kauemmin kuin aiemmin?

Kun olet saanut käsityksen syystä, voit alkaa tutkia asiaa. Vastauksen seuraavaan kuuteen kysymykseen auttavat sinua ratkaisemaan tarkempia ongelmia.

### <a name="what-content-is-using-up-my-capacity"></a>Minkälainen sisältö käyttää eniten kapasiteettia?

**Power BI Premium -kapasiteettiarvot** -sovelluksella voit suodattaa kapasiteetin mukaan ja tarkastella työtilan sisällön suorituskyvyn mittareita. Suorituskyvyn arvoja ja resurssien käyttöä on mahdollista tarkastella tunneittain viimeisen seitsemän päivän ajalta kaiken Premium-kapasiteettiin tallennetun sisällön kohdalla. Valvonta on usein ensimmäinen suoritettava vaihe Premium-kapasiteetin suorituskykyyn liittyvän yleisen ongelman vianmäärityksessä.

Tärkeimmät valvottavat arvot:

- suorittimen keskiarvo ja suuren käytön määrä
- keskimääräinen muisti ja suuren käytön määrä sekä muistin käyttö tietyissä tietojoukoissa, tietovoissa ja sivutetuissa raporteissa
- muistiin ladatut aktiiviset tietojoukot
- kyselyjen keskimääräiset ja enimmäiskestot
- kyselyjen keskimääräiset odotusajat
- tietojoukkojen ja tietovoiden keskimääräiset päivitysajat.

Power BI Premium -kapasiteettiarvot -sovelluksessa aktiivinen muisti näyttää raportille annetun muistin kokonaismäärän, jota ei voi häätää, koska se on ollut käytössä viimeisten kolmen minuutin aikana. Korkea päivityksen odotusaikapiikki saattaa korreloida suuren ja/tai aktiivisen tietojoukon kanssa.

**5 parasta keskimääräisen keston mukaan** -kaavio korostaa viisi eniten kapasiteettiresursseja vievää tietojoukkoa, sivutettua raporttia ja tietovuota. Viiden parhaan luetteloissa on ehdokkaita tutkimusta ja mahdollista optimointia varten.

### <a name="why-are-reports-slow"></a>Miksi raportit ovat hitaita?

Seuraavissa taulukoissa näytetään mahdollisia ongelmia ja tapoja tunnistaa ja käsitellä niitä.

#### <a name="insufficient-capacity-resources"></a>Riittämättömät kapasiteettiresurssit

| Mahdolliset selitykset | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Aktiivisen muistin suuri kokonaismäärä (mallia ei voi häätää, koska se on ollut käytössä viimeisten kolmen minuutin aikana).<br><br> Monta suurta piikkiä kyselyn odotusaikoina.<br><br> Monta suurta piikkiä päivityksen odotusaikoina. | Valvo muistin arvoja \[[1](#endnote-1)\] ja häätömääriä \[[2](#endnote-2)\]. | Pienennä mallin kokoa tai muunna DirectQuery-tilaan. Lue tämän artikkelin [Mallien optimointi](#optimizing-models) -osio.<br><br> Suurenna kapasiteettia.<br><br> Määritä sisältö eri kapasiteettiin. |

#### <a name="inefficient-report-designs"></a>Tehottomat raporttimallit

| Mahdolliset selitykset | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Raporttisivut sisältävät liikaa visualisointeja (vuorovaikutteinen suodatus voi käynnistää vähintään yhden kyselyn visualisointia kohden).<br><br> Visualisoinnit noutavat enemmän tietoja kuin on tarpeen. | Tarkastele raportin malleja.<br><br> Haastattele raportin käyttäjiä siitä, kuinka he käyttävät raportteja.<br><br> Valvo tietojoukon kyselyn arvoja \[[3](#endnote-3)\]. | Suunnittele uudelleen raportteja niin, että visualisointeja sivua kohden on vähemmän. |

#### <a name="dataset-is-slow-especially-when-reports-have-previously-performed-well"></a>Tietojoukko on hidas, etenkin kun raportit ovat aiemmin toimineet hyvin

| Mahdolliset selitykset | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Yhä suurempi määrä tuontitietoja.<br><br> Monimutkainen tai tehoton laskentalogiikka, mukaan lukien rivitason suojauksen roolit.<br><br> Mallia ei ole optimoitu täysin.<br><br> (DQ/LC) Yhdyskäytävän viive.<br><br> Hitaat DQ-lähdekyselyn vastausajat. | Tarkastele mallien suunnittelua.<br><br> Valvo yhdyskäytävän resurssilaskureita. | Lue tämän artikkelin [Mallien optimointi](#optimizing-models) -osio. |

#### <a name="high-concurrent-report-usage"></a>Suuri raportin samanaikainen käyttö

| Mahdolliset selitykset | Tunnistaminen | Ratkaiseminen |
| --- | --- | --- |
| Kyselyjen pitkät odotusajat.<br><br> Suorittimen kylläisyys.<br><br> DQ/LC-yhteyksien rajat ylitetty. | Valvo suorittimen käyttöä \[[4](#endnote-4)\], kyselyjen odotusaikoja ja DQ/LC-käytön \[[5](#endnote-5)\] arvoja sekä kyselyjen kestoja. Vaihtelu voi olla merkki samanaikaisuusongelmista. | Suurenna kapasiteettia tai määritä sisältö eri kapasiteettiin.<br><br> Suunnittele uudelleen raportteja niin, että visualisointeja sivua kohden on vähemmän. |

**Huomautukset:**    
<a name="endnote-1"></a>\[1\] Keskimääräinen muistin käyttö (Gt) ja suurin muistin käyttö (Gt).   
<a name="endnote-2"></a>\[2\] Tietojoukkojen häädöt.   
<a name="endnote-3"></a>\[3\] Tietojoukkojen kyselyt, tietojoukon keskimääräinen kyselyn kesto (ms), tietojoukon odotusmäärä ja tietojoukon keskimääräinen odotusaika (ms).   
<a name="endnote-4"></a>\[4\] Suorittimen suuren käytön määrä ja suorittimen suurimman käytön aika (viimeisten seitsemän päivän aikana).   
<a name="endnote-5"></a>\[5\] Suorittimen suuren käytön määrä ja suorittimen suurimman käytön aika (viimeisten seitsemän päivän aikana).   

### <a name="why-are-reports-not-loading"></a>Miksi raportit eivät lataudu?

Kun raporttien lataaminen epäonnistuu, on varmaa, että kapasiteetin muisti ei riitä ja että se on ylikuumentunut. Näin voi käydä, kun kaikille ladatuille malleille tehdään aktiivinen kysely, joten niitä ei voi häätää, ja kaikki päivitystoiminnot on keskeytetty tai ne ovat viivästyneet. Power BI -palvelu yrittää ladata tietojoukkoa 30 sekunnin ajan, ja käyttäjälle ilmoitetaan virheestä ja häntä pyydetään yrittämään pian uudelleen.

Tällä hetkellä raportin latausvirheiden valvontaan ei ole määritetty mittaria. Voit tunnistaa tämän ongelman mahdollisuuden seuraamalla järjestelmämuistia, erityisesti suurinta käyttöä ja suurimman käytön aikaa. Suuret tietojoukkojen häädöt ja pitkä tietojoukon päivityksen keskimääräinen odotusaika voi viitata siihen, että tämä ongelma on olemassa.

Jos tämä tapahtuu vain hyvin satunnaisesti, tätä ei välttämättä pidetä ensisijaisena ongelmana. Raportin käyttäjille ilmoitetaan, että palvelu on varattu ja että heidän kannattaa yrittää uudelleen lyhyen ajan kuluttua. Jos tämä tapahtuu liian usein, ongelma voidaan ratkaista suurentamalla Premium-kapasiteettia tai määrittämällä sisältö eri kapasiteettiin.

Kapasiteetin järjestelmänvalvojat (ja Power BI -palvelun järjestelmänvalvojat) voivat tarkkailla **kyselyvirheiden** arvoa ja päätellä sen perusteella, milloin näin tapahtuu. He voivat myös käynnistää kapasiteetin uudelleen ja näin nollata kaikki toiminnot järjestelmän ylikuormituksen varalta.

### <a name="why-are-refreshes-not-starting-on-schedule"></a>Miksi päivityksiä ei aloiteta aikataulun mukaisesti?

Ajoitettuja päivitysten alkamisaikoja ei taata. Muista, että Power BI -palvelu priorisoi aina vuorovaikutteisia toimintoja taustatoimintoihin verrattuna. Päivitys on taustatoiminto, joka voi ilmetä, kun kaksi ehtoa täyttyy:

- muistia on riittävästi
- Premium-kapasiteetin tuettujen samanaikaisten päivitysten määrää ei ylitetä.

Kun ehdot eivät täyty, päivitys on jonossa, kunnes ehdot ovat suotuisat.

Jos kyseessä on täysi päivitys, muista, että se edellyttää vähintään kaksinkertaista nykyisen tietojoukon muistin kokoa. Jos muistia ei ole käytettävissä tarpeeksi, päivitys ei voi alkaa, ennen kuin mallin häätö vapauttaa muistia. Viiveitä siis esiintyy, kunnes vähintään yhdestä tietojoukosta tulee passiivinen ja se voidaan häätää.

Muista, että samanaikaisten päivitysten tuettu enimmäismäärä on 1,5 kertaa taustan näennäisytimien määrä, pyöristettynä ylöspäin.

Ajoitettu päivitys epäonnistuu, kun sitä ei voi aloittaa ennen seuraavan ajoitetun päivityksen aloittamista. Manuaalisesti käyttöliittymästä käynnistetty pyydettäessä suoritettava päivitys yritetään suorittaa enintään kolme kertaa ennen epäonnistumista.

Kapasiteetin järjestelmänvalvojat (ja Power BI -palvelun järjestelmänvalvojat) voivat seurata **Päivityksen keskimääräinen odotusaika (minuutteina)** -arvoa määrittääkseen keskimääräisen viiveen ajoitetun ajan ja toiminnon aloittamisen välillä.

Varmista, että käytettävissä on tarpeeksi muistia, jotta voit vaikuttaa ajallaan tehtyihin tietojen päivityksiin, vaikka tämä ei yleensä olekaan järjestelmänvalvojan prioriteettina. Tämä saattaa edellyttää tietojoukkojen eristämistä kapasiteetteihin, joiden resurssit ovat varmasti riittävät. Järjestelmänvalvojat voivat myös koordinoida tietojoukkojen omistajien kanssa, jotta he voivat porrastaa tai pienentää ajoitettuja tietojen päivitysaikoja yhteentörmäysten minimoimiseksi. Ota huomioon, että järjestelmänvalvoja ei voi tarkastella päivitysjonoa tai noutaa tietojoukon ajoituksia.

### <a name="why-are-refreshes-slow"></a>Miksi päivitykset ovat hitaita?

Päivitykset voivat olla hitaita, tai ne koetaan hitaiksi (asia, jota käsiteltiin edellisessä yleisessä kysymyksessä).

Kun päivitys on hidasta, se voi johtua useista syistä:

- riittämättömät suoritinresurssit (päivitykset vaativat tavallisesti paljon suorittimelta)
- muisti ei riitä, mikä aiheuttaa päivityksen keskeyttämisen (jolloin päivitys pitää aloittaa uudelleen, kun olosuhteet ovat sille suotuisat)
- kapasiteetista riippumattomat syyt, mukaan lukien tietolähteen järjestelmän reagointi, verkon viive, virheelliset käyttöoikeudet tai yhdyskäytävän siirto
- tietojen määrä – hyvä syy määrittää lisäävä päivitys, kuten artikkelin myöhemmässä osassa kerrotaan.

Kapasiteetin järjestelmänvalvojat (ja Power BI -palvelun järjestelmänvalvojat) voivat seurata **Päivityksen keskimääräinen kesto (minuutteina)** -arvoa määrittääkseen vertailuarvon ajan kuluessa tehtävään vertailuun sekä **Päivityksen keskimääräinen odotusaika (minuutteina)** -arvoa määrittääkseen keskimääräisen viiveen ajoitetun ajan ja toiminnon aloittamisen välillä.

Lisäävä päivitys voi vähentää huomattavasti tietojen päivittämisen kestoa etenkin suurissa mallitaulukoissa. Lisäävään päivitykseen liittyy neljä etua:

- **Päivitykset ovat nopeampia** – vain taulukon alijoukko pitää ladata, mikä vähentää suorittimen ja muistin käyttöä, ja rinnakkaisuus voi olla suurempi päivitettäessä useita osioita.
- **Päivitykset tehdään vain tarpeen mukaan** – lisäävän päivityksen käytännöt voidaan määrittää latautumaan vain, kun tiedot ovat muuttuneet.
- **Päivitykset ovat luotettavampia** – lyhyemmät käynnissä olevat yhteydet muuttuviin tietolähteiden järjestelmiin ovat vähemmän alttiita yhteyden katkaisemiselle.
- **Mallit pysyvät rajattuina** – lisäävän päivityksen käytännöt voidaan määrittää poistamaan historiatiedot automaattisesti liukuvan aikaikkunan ulkopuolella.

Lisätietoja on artikkelissa [Lisäävää päivitys Power BI Premiumissa](service-premium-incremental-refresh.md).

### <a name="why-are-data-refreshes-not-completing"></a>Miksi tietojen päivityksiä ei suoriteta loppuun?

Kun tietojen päivitykset aloitetaan, mutta ne eivät valmistu, se voi johtua useista syistä:

- muisti ei riitä, vaikka Premium-kapasiteetissa on vain yksi malli, eli mallin koko on hyvin suuri
- kapasiteetista riippumattomat syyt, mukaan lukien tietolähteen järjestelmän katkaisu, virheelliset käyttöoikeudet tai yhdyskäytävän virhe.

Kapasiteetin järjestelmänvalvojat (ja Power BI -palvelun järjestelmänvalvojat) voivat tarkkailla **Muistin loppumisen vuoksi epäonnistuneet päivitykset** -arvoa.

## <a name="optimizing-models"></a>Mallien optimointi

Mallin optimaalinen suunnittelu on hyvin tärkeää tehokkaan ja skaalattavan ratkaisun saamisessa. Tämä artikkeli ei kuitenkaan kata kaikkia osa-alueita. Sen sijaan tässä osiossa annetaan kerrotaan tärkeimmistä aiheista mallien optimoinnin suhteen.

### <a name="optimizing-power-bi-hosted-models"></a>Power BI:ssä isännöityjen mallien optimointi

Premium-kapasiteetissa isännöityjen mallien optimoiminen voidaan toteuttaa tietolähteissä ja mallikerroksissa.

Mieti tuontimallin optimointimahdollisuuksia:

![Tuontimallin optimointimahdollisuudet](media/service-premium-capacity-optimize/import-model-optimizations.png)

Tietolähdekerroksessa:

- Relaatiotietolähteet voidaan optimoida siten, että ne varmistavat nopeimman mahdollisen päivityksen integroimalla tiedot ennalta, ottamalla käyttöön sopivia indeksejä, määrittämällä lisääviin päivitysjaksoihin tasattavia taulukon osiointeja ja muodostamalla laskutoimitukset (laskettujen mallitaulukkojen ja -sarakkeiden sijaan) tai lisäämällä laskentalogiikan näkymiin.
- Muut kuin relaatiotietolähteet voidaan integroida ennalta relaatiosäilöihin.
- Varmista, että yhdyskäytävissä on tarpeeksi resursseja, mieluiten erillisissä koneissa, joissa on riittävä verkon kaistanleveys ja jotka ovat lähellä tietolähteitä.

Mallikerroksessa:

- Power Query -kyselymallit voivat pienentää tai poistaa monimutkaisia muunnoksia ja etenkin niitä, jotka yhdistävät eri tietolähteitä (tietovarastot saavuttavat tämän Poimi-Muunna-Lataa-vaiheen aikana). Lisäksi varmistamalla, että asianmukaiset tietolähteen yksityisyystasot on määritetty, Power BI:n ei tarvitse ladata kokonaisia tuloksia tuottaakseen yhdistetyn tuloksen kyselyiden välillä.
- Mallirakenne määrittää ladattavat tiedot ja vaikuttaa suoraan mallin kokoon. Se voidaan suunnitella siten, että vältetään tarpeettomien tietojen lataaminen poistamalla sarakkeita, poistamalla rivejä (erityisesti historiallisia tietoja) tai lataamalla yhteenvedettyjä tietoja (yksityiskohtaisten tietojen lataamisen kustannuksella). Koon merkittävä pienentäminen onnistuu poistamalla suuren kardinaliteetin sarakkeet (erityisesti tekstisarakkeet), joita ei voi tallentaa tai pakata kovin tehokkaasti.
- Mallikyselyn suorituskykyä voidaan parantaa määrittämällä yksisuuntaisia suhteita, ellei kaksisuuntaisen suodatuksen sallimiseen ole pakottavaa syytä. Harkitse myös [CROSSFILTER](https://docs.microsoft.com/dax/crossfilter-function)-function käyttämistä kaksisuuntaisen suodatuksen sijaan.
- Koostamistaulukot voivat saavuttaa nopeita kyselyvastauksia lataamalla ennalta yhteenvedetyt tiedot, mutta tämä kuitenkin kasvattaa mallin kokoa ja pidentää päivitysaikoja. Yleensä koostetaulukot tulee varata erittäin suurille malleille tai yhdistelmämalleille.
- Lasketut taulukot ja sarakkeet lisäävät mallin kokoa ja pidentävät päivitysaikoja. Yleensä pienempi tallennustilan koko ja nopeampi päivitysaika voidaan saavuttaa, kun tiedot muodostetaan tai lasketaan tietolähteessä. Jos tämä ei ole mahdollista, Power Queryn mukautettujen sarakkeiden avulla voidaan parantaa tallennustilan pakkausta.
- DAX-lausekkeiden säätäminen mittareita ja RLS-sääntöjä varten saattaa olla mahdollista, ehkäpä logiikan kirjoittamisella uudelleen kalliiden kaavojen välttämiseksi.
- Lisäävä päivitys voi merkittävästi lyhentää päivitysaikaa ja säästää muistia ja suoritinta. Lisäävä päivitys voidaan myös määrittää poistamaan historialliset tiedot, jolloin mallien koot pysyvät rajattuina.
- Malli voidaan suunnitella uudelleen kahtena mallina, kun kyselymallit poikkeavat toisistaan ja ovat ristiriitaisia. Jotkin raportit esimerkiksi esittävät korkean tason koosteita koko historiassa, ja ne kestävät 24 tunnin viiveen. Toiset raportit koskevat nykypäivän tietoja ja edellyttävät yksilöllisten tapahtumien vaiheittaista käyttöä. Sen sijaan, että suunnittelisit yksittäisen mallin täyttämään kaikkien raporttien tarpeet, voit luoda kaksi mallia, jotka on optimoitu kullekin vaatimukselle.

Mieti DirectQuery-mallin optimointimahdollisuuksia. Koska malli lähettää kyselypyyntöjä pohjana olevaan tietolähteeseen, tietolähteen optimointi on erittäin tärkeää reagoivien mallikyselyiden toimittamiseksi.

 ![DirectQuery-mallin optimointimahdollisuudet](media/service-premium-capacity-optimize/direct-query-model-optimizations.png)

Tietolähdekerroksessa:

- Tietolähde voidaan optimoida siten, että se varmistaa nopeimman mahdollisen kyselyn integroimalla tiedot ennalta (mikä ei ole mahdollista mallikerroksessa), ottamalla käyttöön sopivia indeksejä, määrittämällä taulukon osiointeja, muodostamalla yhteenvetotietoja (indeksoiduilla näkymillä) ja pienentämällä laskennan määrää. Paras käyttökokemus saavutetaan, kun läpivientikyselyt tarvitsevat vain suodattimia ja suorittavat sisäliitoksia indeksoitujen taulukoiden tai näkymien välillä.
- Varmista, että yhdyskäytävissä on tarpeeksi resursseja, mieluiten erillisissä koneissa, joissa on riittävä verkon kaistanleveys ja jotka ovat lähellä tietolähdettä.

Mallikerroksessa:

- Power Query -kyselymalleissa ei mielellään tulisi olla yhtään muunnoksia, tai yritä ainakin pitää muunnokset mahdollisimman vähäisinä.
- Mallikyselyn suorituskykyä voidaan parantaa määrittämällä yksisuuntaisia suhteita, ellei kaksisuuntaisen suodatuksen sallimiseen ole pakottavaa syytä. Myös malliyhteydet tulee määrittää niin, että viite-eheys on pakotettu (tarvittaessa), jolloin tietolähdekyselyt käyttävät tehokkaampia sisäliitoksia (ulkoliitosten sijaan).
- Vältä Power Query -kyselyn mukautettujen sarakkeiden tai mallin lasketun sarakkeen luomista – muodosta ne tietolähteessä, kun se on mahdollista.
- DAX-lausekkeiden säätäminen mittareita ja RLS-sääntöjä varten saattaa olla mahdollista, ehkäpä logiikan kirjoittamisella uudelleen kalliiden kaavojen välttämiseksi.

Mieti yhdistelmämallin optimointimahdollisuuksia. Muista, että yhdistelmämalli mahdollistaa tuonti- ja DirectQuery-taulukoiden yhdistelmän.

![Yhdistelmämallin optimointimahdollisuudet](media/service-premium-capacity-optimize/composite-model-optimizations.png)

- Yleensä tuonti- ja DirectQuery-mallien optimointi koskee yhdistelmämallitaulukoita, jotka käyttävät näitä tallennustiloja.
- Pyri yleensä tasapainoiseen muotoiluun määrittämällä dimensiotyyppisiä taulukoita (jotka edustavat yritysentiteettejä) Kaksois-tallennustilana ja faktatyypin taulukkoja (usein suuria taulukoita, jotka edustavat toiminnallisia faktoja) DirectQuery-tallennustilana. Kaksois-tallennustila tarkoittaa sekä Tuonti- että DirectQuery-tallennustilaa, ja tämän avulla Power BI -palvelu voi määrittää tehokkaimman tallennustilan, jota käytetään luotaessa alkuperäistä kyselyä läpivientiä varten.
- Varmista, että yhdyskäytävissä on tarpeeksi resursseja, mieluiten erillisissä koneissa, joissa on riittävä verkon kaistanleveys ja jotka ovat lähellä tietolähteitä.
- Tuonti-tallennustilaksi määritetyt koostetaulukot voivat parantaa kyselyjen suorituskykyä huomattavasti, kun niitä käytetään yhteenvedon tekemiseen DirectQuery-tallennustilan faktatyypin taulukoista. Tässä tapauksessa koostetaulukot lisäävät mallin kokoa ja pidentävät päivitysaikaa, ja usein tämä on hyväksyttävä kompromissi kyselyjen nopeuttamiseksi.

### <a name="optimizing-externally-hosted-models"></a>Ulkoisesti isännöityjen mallien optimoiminen

Monet [Power BI:ssä isännöityjen mallien optimointi](#optimizing-power-bi-hosted-models) -osiossa käsitellyt optimointimahdollisuudet soveltuvat myös malleihin, jotka on kehitetty Azure Analysis Servicesin ja SQL Server Analysis Servicesin kanssa. Selkeät poikkeukset ovat tiettyjä ominaisuuksia, joita ei tällä hetkellä tueta, mukaan lukien yhdistelmämallit ja koostetaulukot.

Lisäksi ulkoisesti isännöidyn tietojoukon kohdalla kannattaa ottaa huomioon tietokannan isännöinti suhteessa Power BI -palveluun. Jos kyseessä on Azure Analysis Services, Azure-resurssi luodaan samalla alueella kuin Power BI -vuokraaja (kotialue). Jos kyseessä on SQL Server Analysis Services ja IaaS, näennäiskonetta isännöidään samalla alueella, ja jos kyseessä on paikallinen, varmistetaan tehokas yhdyskäytävän määrittäminen.

Voi olla myös kiinnostavaa huomata, että Azure Analysis Servicesin tietokannat ja SQL Server Analysis Servicesin taulukkotietokannat edellyttävät, että niiden mallit ladataan kokonaan muistiin ja että ne pysyvät siellä aina tukemassa kyselyä. Power BI -palvelun tapaan muistia on oltava riittävästi päivittämiseen, jos mallin on pysyttävä online-tilassa päivityksen aikana. Kuitenkin toisin kuin Power BI -palvelussa, mallit eivät automaattisesti vanhene muistissa käytön mukaan. Power BI Premium tarjoaa näin ollen tehokkaamman lähestymistavan mallin kyselyiden maksimoimiseen pienemmällä muistin käytöllä.

## <a name="capacity-planning"></a>Kapasiteetin suunnittelu

Premium-kapasiteetin koko määrittää sen käytettävissä olevat muisti- ja suoritinresurssit sekä kapasiteettiin asetetut rajoitukset. Premium-kapasiteettien määrä kannattaa myös huomioida, sillä useiden Premium-kapasiteettien luominen voi auttaa eristämään kuormitukset toisistaan. Huomioi, että tallennustila on 100 Tt kapasiteetin solmua kohden, ja tämä todennäköisesti riittää hyvin mille tahansa työmäärälle.

Premium-kapasiteettien koon ja määrän määrittäminen voi olla haastavaa erityisesti ensimmäisten luomiesi kapasiteettien kohdalla. Ensimmäinen vaihe kapasiteetin koon määrittämisessä on ymmärtää keskimääräinen kuormitus, joka edustaa odotettua päivittäistä käyttöä. On tärkeää ymmärtää, että kaikki kuormitukset eivät ole yhtä suuria. Yhdessä ääripäässä voi olla esimerkiksi 100 samanaikaista käyttäjää, jotka käyttävät yhden visualisoinnin sisältävää raporttisivua – tämä on helposti toteutettavissa. Toisessa ääripäässä voi kuitenkin olla 100 samanaikaista käyttäjää, jotka käyttävät 100 eri raporttia, ja raporttisivulla on 100 visualisointia – tämä edellyttää kapasiteetin resursseilta paljon enemmän.

Kapasiteetin järjestelmänvalvojien on siis otettava huomioon monia ympäristöösi, sisältöösi ja odotettuun käyttöön liittyviä tekijöitä. Ensisijaisena tavoitteena on maksimoida kapasiteetin käyttöaste ja antaa samalla yhtenäiset kyselyajat sekä hyväksyttävät odotusajat ja häätömäärät. Huomioon otettavia seikkoja voivat olla seuraavat:

- **Mallin koko ja tietojen ominaisuudet** – tuontimallit on ladattava kokonaan muistiin kyselyjen tai päivitysten sallimiseksi. LC/DQ-tietojoukot saattavat edellyttää huomattavasti suoritinaikaa ja mahdollisesti merkittävästi muistia monimutkaisten mittareiden tai RLS-sääntöjen arvioimiseksi. Kapasiteetin koko rajoittaa muistin ja suorittimen kokoa sekä LC/DQ-kyselyn siirtomäärää.
- **Samanaikaiset aktiiviset mallit** – eri tuontimallien samanaikaisissa kyselyissä saadaan paras vasteaika ja suorituskyky, kun ne pysyvät muistissa. Muistia on oltava riittävästi kaikkien useiden kyselyjen kohteena olevien mallien isännöintiin, ja lisämuisti on tarpeen niiden päivittämistä varten.
- **Tuontimallin päivitys** – päivitystyyppi (täysi tai lisäävä), Power Query -kyselyiden kesto ja monimutkaisuus sekä lasketun taulukon/sarakkeen logiikka voivat vaikuttaa muistiin ja erityisesti suorittimen käyttöön. Kapasiteetin koko (1,5 kertaa taustan näennäisytimien määrä, pyöristettynä ylöspäin) rajoittaa samanaikaisia päivityksiä.
- **Samanaikaiset kyselyt** – useat samanaikaiset kyselyt voivat johtaa vastaamattomiin raportteihin, kun suoritin- tai LC/DQ-yhteydet ylittävät kapasiteettirajan. Tämä koskee etenkin raporttisivuja, jotka sisältävät useita visualisointeja.
- **Tietovuot ja sivutetut raportit** – kapasiteetti voidaan määrittää tukemaan tietovoita ja sivutettuja raportteja, joista jokainen edellyttää määritettävissä olevaa enimmäisprosenttiosuutta kapasiteettimuistista. Muisti kohdistetaan tietovoille dynaamisesti mutta sivutetuille raporteille staattisesti.

Näiden tekijöiden lisäksi kapasiteetin järjestelmänvalvojat voivat harkita useiden kapasiteettien luomista. Useat kapasiteetit mahdollistavat kuormituksen eristämisen, ja ne voidaan määrittää varmistamaan, että ensisijaisilla kuormituksilla on taatut resurssit. Voit esimerkiksi luoda kaksi kapasiteettia erottamaan liiketoiminnan kannalta tärkeät kuormitukset omatoimisen BI:n (SSBI) kuormituksista. Liiketoiminnan kannalta tärkeän kapasiteetin avulla voidaan eristää suuria yritysmalleja, jolloin ne saavat taatut resurssit ja käyttöoikeus myönnetään vain IT-osastolle. SSBI-kapasiteetin avulla voidaan isännöidä kasvavaa määrää pienempiä malleja, ja käyttöoikeus myönnetään yritysanalyytikoille. SSBI-kapasiteetti voi toisinaan esiintyä kyselyn tai päivityksen viiveitä, jotka ovat siedettäviä.

Kapasiteetin järjestelmänvalvojat voivat ajan mittaan tasapainottaa työtiloja eri kapasiteeteissa siirtämällä sisältöä työtilojen välillä tai työtiloja kapasiteettien välillä sekä suurentamalla tai pienentämällä kapasiteetteja. Yleisesti ottaen suurempien mallien isännöinti edellyttää suurentamista ja suurempi samanaikaisuus pienentämistä.

Muista, että käyttöoikeuden ostaminen antaa vuokraajalle näennäisytimiä. **P3**-tilauksella voidaan luoda yksi tai enintään neljä Premium-kapasiteettia eli 1 x P3 tai 2 x P2 tai 4 x P1. Lisäksi ennen kuin P2-kapasiteetti muunnetaan P3-kapasiteettiin, kannattaa harkita näennäisytimien jakamista kahden P1-kapasiteetin luomiseksi.

## <a name="testing-approaches"></a>Testausmenetelmät

Kun kapasiteetin koko on päätetty, testaaminen voidaan suorittaa luomalla hallittu ympäristö. Käytännöllinen ja taloudellinen vaihtoehto on luoda Azure (A-SKU) -kapasiteetti. Huomaa, että P1-kapasiteetti on samankokoinen kuin A4-kapasiteetti, P2-kapasiteetti samankokoinen kuin A5-kapasiteetti P3-kapasiteetti samankokoinen kuin A6-kapasiteetti. Azure-kapasiteetit voidaan luoda nopeasti, ja niistä laskutetaan tunneittain. Joten kun testaus on valmis, ne voidaan poistaa helposti, jolloin kustannuksia ei enää kerry.

Testisisältö voidaan lisätä Azure-kapasiteetissa luotuihin työtiloihin, minkä jälkeen yksittäinen käyttäjä voi suorittaa raportteja ja luoda kyselyistä realistisen ja edustavan kuormituksen. Jos käytössä on tuontimalleja, kunkin mallin kohdalla on myös suoritettava päivitys. Valvontatyökaluilla voidaan sitten tarkistaa kaikki arvot resurssien käytön ymmärtämiseksi.

On tärkeää, että testit ovat toistettavissa. Testit tulee suorittaa useita kertoja, ja niiden pitäisi antaa suunnilleen sama tulos joka kerta. Näiden tulosten keskiarvoa voidaan käyttää kuormituksen määrittämiseen ja arvioimiseen todellisissa tuotanto-olosuhteissa.

Jos olet jo määrittänyt kapasiteetin ja raportit, joille haluat tehdä testin, voit luoda kuormitustestin nopeasti [PowerShellin kuormituksen luontityökalun](https://aka.ms/PowerBILoadTestingTool) avulla. Työkalun avulla voit arvioida, kuinka monta kunkin raportin esiintymää kapasiteettisi pystyy suorittamaan tunnissa. Työkalun avulla voit lisäksi arvioida kapasiteettisi kyvyn yksittäisen raportin hahmontamiseen tai useiden eri raporttien hahmontamiseen rinnakkain. Lisätietoja on videossa [Microsoft Power BI: Premium-kapasiteetti](https://www.youtube.com/watch?time_continue=1860&v=C6vk6wk9dcw).

Voit luoda monimutkaisemman testin kehittämällä kuormituksen testaussovelluksen, joka simuloi realistista kuormitusta. Lisätietoja on verkkoseminaarissa [Power BI -sovellusten kuormituksen testaus Visual Studion kuormitustestillä](https://powerbi.microsoft.com/blog/week-4-11-webinars-load-testing-power-bi-applications-with-visual-studio-load-test-and-getting-started-with-cds-for-apps-based-model-driven-apps/).

## <a name="acknowledgements"></a>Kiitokset

Tämän artikkelin on kirjoittanut Peter Myers, joka on Data Platform MVP ja itsenäinen BI-asiantuntija, yhdessä [Bitwise Solutionsin](https://www.bitwisesolutions.com.au/) kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
> [Premium-kapasiteettitilanteet](service-premium-capacity-scenarios.md)   
  
Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

||||||