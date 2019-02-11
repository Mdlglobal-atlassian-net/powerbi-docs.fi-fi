---
title: Valvo Power BI Premium -kapasiteetteja Power BI Premium -kapasiteetin mittausarvot -sovelluksella.
description: Power BI -hallintaportaalin ja Power BI Premium -kapasiteetin mittausarvot -sovellus
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2019
LocalizationGroup: Premium
ms.openlocfilehash: c4e919de95c86051257ddc38b65c4dfda78dfc03
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794625"
---
# <a name="monitor-premium-capacities-with-the-app"></a>Premium-kapasiteettien valvonta sovelluksen avulla

Kapasiteettien valvonta on tärkeää, jotta voit tehdä järkeviä päätöksiä Premium-kapasiteettien resurssien hyödyntämisen suhteen. Voit valvoa kapasiteetteja hallintaportaalissa tai **Power BI Premium -kapasiteetin mittausarvot** -sovelluksella. Tässä artikkelissa annetaan ohjeet Power BI Premium -kapasiteetin mittausarvot -sovelluksen käyttöön. Sovellus tarjoaa tarkimmat tiedot kapasiteettiesi toiminnasta ja suorituskyvystä. Jos haluat yleisempiä keskiarvotietoja seitsemän edellisen päivän ajalta, voit käyttää hallintaportaalia. Jos haluat lisätietoja valvonnasta portaalissa, lue ohjeartikkeli [Premium-kapasiteettien valvonta hallintaportaalissa](service-admin-premium-monitor-portal.md).

Sovellusta päivitetään säännöllisesti uusin toiminnoin. Varmista, että käytät uusinta versiota.
**Uusin sovellusversio on 1.10.1.1 (5.2.2019)**.   
Jos sinulla on asennettuna sovelluksen vanhempi versio, sinun kannattaa poistaa se sovelluksista. Kun olet tehnyt tämän, tee päivitys painamalla CTRL+F5. 

## <a name="install-the-app"></a>Sovelluksen asentaminen

Voit siirtyä suoraan [Power BI Premium -kapasiteetin mittausarvot -sovellukseen](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) tai asentaa sen muiden Power BI -sovellusten tapaan.


1. Valitse Power BI:ssä **Sovellukset**.   
    ![Sovelluksiin siirtyminen](media/service-admin-premium-monitor-capacity/apps.png)

2. Valitse oikealla puolella **Hanki sovelluksia**.
3. Hae **Sovellukset**-luokasta **Power BI Premium -kapasiteetin mittausarvot -sovellus**.
4. Tilaa sovelluksen asennus.

Ole kärsivällinen. Asennus ja arvojen päivittäminen kestää muutaman minuutin. Jos sovellus näyttää tyhjiä arvoja, päivitä selainnäkymä painamalla F5-näppäintä.


## <a name="get-app-refresh-history"></a>Sovelluksen päivityshistorian hakeminen

Jos haluat tarkistaa, koska Power BI Premium -kapasiteetin mittausarvot -sovellus on viimeksi päivitetty, valitse **Asetukset** > **Tietojoukot** > **Power BI Premium -kapasiteetin mittausarvot** > **Päivityshistoria**. 

![Päivityshistoria asetuksissa](media/settings-refresh-history.png)

Näet viimeisimmän päivityksen. Jos haluat nähdä ajoitetut ja manuaaliset päivitykset, valitse **Päivityshistoria**.

![Viimeisin päivitys](media/service-admin-premium-monitor-capacity/settings-last-refresh.png)

## <a name="monitor-a-capacity-with-the-app"></a>Kapasiteetin valvonta sovelluksen avulla

Nyt kun olet asentanut sovelluksen, näet organisaatiosi kapasiteettien mittausarvot. Tutustutaan muutamaan tärkeimpään käytettävissä olevaan mittausarvoon.

### <a name="metrics-dashboard"></a>Mittareiden koontinäyttö

Kun avaat sovelluksen, se näyttää ensin raporttinäkymältä, jossa on yhteenveto kaikista kapasiteeteista, joihin sinulla on järjestelmänvalvojan oikeudet.

![Mittausarvosovelluksen koontinäyttö](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Koontinäyttö sisältää seuraavat mittausarvot:

| **Raporttiosa** | **Mittausarvot** |
| --- | --- |
| **Järjestelmän yhteenveto** |  Sovelluksen versio<br>  Niiden kapasiteettien määrä, joiden järjestelmänvalvoja olet<br>  Kapasiteettiesi niiden työtilojen määrä, jotka ovat raportointimittareita<br>  Keskimääräinen muistin käyttö gigatavuina viimeisten seitsemän päivän aikana<br>  Muistin enimmäiskäyttö gigatavuina viimeisten seitsemän päivän aikana<br>  Paikallinen aika, jolloin muistin enimmäiskäyttö tapahtui<br>  Kuinka monta kertaa suoritin ylitti 80 prosenttia raja-arvoista viimeisten seitsemän päivän aikana kolmen minuutin osiin jaettuna<br>  Ajankohdat, jolloin suoritin useimmin ylitti 80 prosenttia viimeisten seitsemän päivän aikana tunnin osiin jaettuna<br>  Paikallinen aika, jolloin suoritin useimmin ylitti 80 prosenttia tunnin aikana |
| **Tietojoukon yhteenveto** |  Kapasiteettiesi kaikkien työtilojen tietojoukkojen kokonaismäärä<br>  Kuinka monta kertaa DirectQuery- tai Live-yhteys ylitti 80 prosenttia raja-arvoista viimeisten seitsemän päivän aikana kolmen minuutin osiin jaettuna<br>  Ajankohdat, jolloin DirectQuery- tai Live-yhteys useimmin ylitti 80 prosenttia viimeisten seitsemän päivän aikana tunnin osiin jaettuna<br>  Paikallinen aika, jolloin DirectQuery- tai Live-yhteys useimmin ylitti 80 prosenttia tunnin aikana<br>  Päivitysten kokonaismäärä viimeisten seitsemän päivän aikana<br>  Päivityksen keskimääräinen odotusaika – keskimääräinen viive päivityksen ajoitetun alkamisajan ja sen alkamisen välillä minuutteina<br>  Päivityksen keskimääräinen kesto – päivityksen suorittamiseen tarvittava aika minuutteina<br>  Suoritettujen kyselyjen kokonaismäärä viimeisten seitsemän päivän aikana<br>  Kyselyn keskimääräinen odotusaika – millisekunteina ilmoitettu aika, jonka kysely odotti järjestelmäresursseja ennen suorittamisen aloittamista<br>  Kyselyn keskimääräinen kesto – kyselyn suorittamiseen tarvittava aika millisekunteina<br>  Muistipaineen vuoksi poistettujen mallien kokonaismäärä<br>  Tietojoukkojen keskikoko <br>  Muistiin ladattujen tietojoukkojen keskimäärä |
| **Tietovuon yhteenveto** |  Kapasiteettiesi kaikkien työtilojen tietovoiden kokonaismäärä<br>  Päivitysten kokonaismäärä viimeisten seitsemän päivän aikana<br>  Päivityksen keskimääräinen odotusaika – keskimääräinen viive päivityksen ajoitetun alkamisajan ja sen alkamisen välillä minuutteina<br>  Päivityksen keskimääräinen kesto – päivityksen suorittamiseen tarvittava aika minuutteina |
| **Sivutetun raportin yhteenveto** |  Kapasiteettiesi kaikkien työtilojen sivutettujen raporttien kokonaismäärä<br>  Kaikkien raporttien katselukertojen kokonaismäärä<br>  Kaikkien raporttien tietorivien kokonaismäärä<br>  Millisekunteina ilmoitettu kokonaisaika, joka kaikkien raporttien kaikkiin vaiheisiin (tietojen nouto, käsittely ja hahmontaminen) menee |
|  |  |

### <a name="metrics-report"></a>Mittariraportti

Napsauta koontinäyttöä siirtyäksesi sen pohjana olevaan raporttiin. Raporttieditorin alareunassa on viisi välilehteä:

* [**Tietojoukot**](#datasets): nämä ovat yksityiskohtaiset mittausarvot Power BI -tietojoukkojen kunnosta kapasiteeteissasi.

* [**Sivutetut raportit**](#paginated-reports): nämä ovat yksityiskohtaiset mittausarvot sivutettujen raporttien kunnosta kapasiteeteissasi.

* [**Tietovuot**](#dataflows): nämä tietovoiden yksityiskohtaiset päivitysmittausarvot kapasiteeteissasi.

* [**Resurssien kulutus**](#resource-consumption): nämä ovat yleiset kapasiteetin mittausarvot, mukaan lukien muisti ja suorittimen korkea käyttö.

* [**Tunnukset ja tiedot**](#ids-and-info): nämä ovat kapasiteettien, työtilojen ja työmäärien nimet, tunnukset ja omistajat.

Kussakin välilehdessä voi suodattaa mittareita kapasiteetin ja päivämääräalueen mukaan. Jos suodattimia ei ole valittuna, raportti näyttää oletuksena edellisen viikon mittausarvot kaikille kapasiteeteille, jotka ovat raportointimittareita. 

#### <a name="datasets"></a>Tietojoukot

Käyttämällä **Tietojoukot**-välilehden yläosan painikkeita voit siirtyä eri alueille: **Päivitykset**, **Kyselyn kestot**, **Kysely odottaa** ja **Tietojoukot**.

##### <a name="refreshes-area"></a>Päivitykset-alue

**Päivitykset**-alueella näkyvät seuraavat mittausarvot.

| **Raporttiosa** | **Mittausarvot** |
| --- | --- |
| **Päivityksen luotettavuus** |  Kokonaismäärä: kunkin tietojoukon päivitysten kokonaismäärä<br>  Luotettavuus: kullekin tietojoukolle suoritettujen päivitysten prosenttiosuus<br>  Keskimääräinen odotusaika: keskimääräinen viive ajoitetun ajankohdan ja tietojoukon päivityksen alkamisen välillä minuutteina<br>  Enimmäisodotusaika: tietojoukon enimmäisodotusaika minuutteina <br>  Keskimääräinen kesto: tietojoukon päivityksen keskimääräinen kesto minuutteina<br>  Enimmäiskesto: tietojoukon pitkäkestoisimman päivityksen kesto minuutteina |
| **Top 5 tietojoukkoa päivityksen keskimääräisen keston mukaan** |  Viisi tietojoukkoa, joilla on pisin päivityksen keskimääräinen kesto minuutteina |
| **Top 5 tietojoukkoa keskimääräisen odotusajan mukaan** |  Viisi tietojoukkoa, joilla on pisin päivityksen keskimääräinen odotusaika minuutteina |
| **Päivityksen keskimääräinen odotusaika tunneittain** |  Päivityksen keskimääräinen odotusaika tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna. Useat korkeat päivityksen odotusaikapiikit ovat merkki kuumana käyvästä kapasiteetista. |
| **Päivitysmäärä tunneittain ja muistin käyttö** |  Onnistumiset, epäonnistumiset ja muistin käyttö tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
|  |  |

##### <a name="query-durations-area"></a>Kyselyjen kestot -alue

**Kyselyjen kestot** -alueella näkyvät seuraavat mittausarvot.

| **Raporttiosa** | **Mittausarvot** |
| --- | --- |
| **Kyselyjen kestot** |  Tämän osion tiedot on ositettu tietojoukkojen, työtilan ja tunnittaisten säilöjen mukaan viimeisten seitsemän päivän ajalta<br>  Yhteensä: tietojoukolle suoritettavien kyselyjen kokonaismäärä<br>  Keskiarvo: tietojoukon kyselyn keskimääräinen kesto millisekunteina<br>  Enimmäisarvo: tietojoukon pitkäkestoisimman kyselyn kesto millisekunteina|
| **Kyselyn keston jakauma** |  Kyselyn keston histogrammi on jaoteltu kyselyjen kestojen mukaan (millisekunneissa) seuraaviin luokkiin: < 30 ms, 30–100 ms, 100–300 ms, 300 ms–1 s, 1–3 s, 3–10 s, 10–30 s ja > 30 s. Kyselyjen pitkät kestot ja odotusajat ovat osoitus siitä, että kapasiteetti on äärirajoilla. Se saattaa myös tarkoittaa sitä, että yksi tietojoukko aiheuttaa ongelmia ja tarkempaa tutkimusta tarvitaan. |
| **Top 5 tietojoukkoa keskimääräisen keston mukaan** |  Viisi tietojoukkoa, joilla on pisin kyselyn keskimääräinen kesto millisekunteina |
| **Suora kysely / Reaaliaikaiset yhteydet (> 80 prosentin käyttöaste)** |  Kerrat, jolloin suora kysely tai reaaliaikainen yhteys ylitti suorittimen 80 prosentin käyttöasteen tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
| **Kyselyn keston jakauma tunneittain** |  Kyselyjen määrä ja keskimääräinen kesto (millisekunteina) vs. muistin käyttö gigatavuina tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
|  |  |

##### <a name="query-waits-area"></a>Kysely odottaa -alue

**Kysely odottaa** -alueella näkyvät seuraavat mittausarvot.

| **Raporttiosa** | **Mittausarvot** |
| --- | --- |
| **Kyselyn odotusajat** |  Tämän osion tiedot on ositettu tietojoukkojen, työtilan ja tunnittaisten säilöjen mukaan viimeisten seitsemän päivän ajalta<br>  Yhteensä: tietojoukolle suoritettavien kyselyjen kokonaismäärä<br>  Odotusmäärä: ennen suorittamisen aloittamista järjestelmäresursseissa odottaneiden kyselyjen määrä tietojoukossa <br>  Keskiarvo: tietojoukon kyselyn keskimääräinen odotusaika millisekunteina<br>  Enimmäisarvo: tietojoukon pisimpään odottaneen kyselyn kesto millisekunteina|
| **Odotusajan jakauma** |  Kyselyn keston histogrammi on jaoteltu kyselyjen kestojen mukaan (millisekunneissa) seuraaviin luokkiin: < 50 ms, 50–100 ms, 100–200 ms, 200–400 ms, 400 ms–1 s, 1–5 s ja > 5 s |
| **Top 5 tietojoukkoa keskimääräisen odotusajan mukaan** |  Viisi tietojoukkoa, joilla on pisin keskimääräinen odotusaika kyselyn suorittamisen aloittamiseen millisekunteina |
| **Odottavien kyselyjen määrät ja ajat tunneittain** |  Odottavien kyselyjen määrä ja keskimääräinen odotusaika (millisekunteina) vs. muistin käyttö gigatavuina tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
|  |  |

##### <a name="datasets-area"></a>Tietojoukot-alue

**Tietojoukot**-alueella näkyvät seuraavat mittausarvot.

| **Raporttiosa** | **Mittausarvot** |
| --- | --- |
| **Tietojoukon poistolaskuri** |  Yhteensä: kapasiteetista *häädettävien* tietojoukkojen kokonaismäärä. Kun kapasiteetti kohtaa muistipainetta, solmu häätää yhden tai useamman tietojoukon muistista. Passiiviset tietojoukot (joihin ei kyseisellä hetkellä kohdistu kysely- tai uudelleenlataustoimintoja) häädetään ensin. Seuraavaksi häätöjärjestyksessä sovelletaan ”viimeiseksi käytetyt ensin” -periaatetta.|
| **Tietojoukkojen häätö ja muistin käyttö tunneittain** |  Tietojoukkojen häädöt vs. muistin käyttö gigatavuina tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
| **Tunnittain ladattujen tietojoukkojen määrä** |  Muistiin ladattujen tietojoukkojen määrä vs. muistin käyttö gigatavuina tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
| **Kulutetun muistin prosenttiosuudet** |  Tämä on muistissa olevien aktiivisten tietojoukkojen kokonaismuistista viemä prosenttiosuus. Erottelun aktiivisten ja kaikkien määritettyjen tietojoukkojen välillä voi poistaa. Tämä näytetään tunneittain seitsemältä edelliseltä päivältä. |
| **Tietojoukkojen koko**  |  Enimmäiskoko: tietojoukon enimmäiskoko megatavuina näytetyllä ajanjaksolla |
|  |  |

#### <a name="paginated-reports"></a>Sivutetut raportit

**Sivutetut raportit** -välilehdessä on yksityiskohtaiset mittausarvot sivutettujen raporttien kunnosta kapasiteeteissasi.

| **Raporttiosa** | **Mittausarvot** |
| --- | --- |
| **Kokonaiskäyttö** |  Katselukerrat yhteensä: kuinka monta kertaa käyttäjät ovat katselleet raporttia<br>  Rivimäärä: raportin tietorivien määrä<br>  Nouto (keskimääräinen): raportin tietojen noutamiseen keskimääräisesti kuluva aika millisekunteina. Pitkä kesto voi olla osoitus kyselyjen hitaasta suorittamisesta tai muista tietolähteeseen liittyvistä ongelmista. <br>  Käsittely (keskimääräinen): raportin tietojen käsittelemiseen keskimääräisesti kuluva aika millisekunteina<br> Hahmontaminen (keskimääräinen): raportin hahmontamiseen selaimessa keskimääräisesti kuluva aika millisekunteina<br>  Kokonaisaika: raportin kaikkiin vaiheisiin kuluva aika millisekunteina|
| **Top 5 raporttia tietojen keskimääräisen noutoajan mukaan** |  Viisi raporttia, joissa on pisin tietojen keskimääräinen noutoaika millisekunteina |
| **Top 5 raporttia keskimääräisen käsittelyajan mukaan** |  Viisi raporttia, joissa on pisin raportin keskimääräinen käsittelyaika millisekunteina |
| **Kestot tunneittain** |  Tietojen nouto vs. käsittely- ja hahmonnusaika tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
| **Tulokset tunneittain** |  Onnistumiset, epäonnistumiset ja muistin käyttö tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
|  |  |

#### <a name="dataflows"></a>Tietovuot

**Tietovuot**-välilehdessä on tietovoiden yksityiskohtaiset päivitysmittausarvot kapasiteeteissasi.

| **Raporttiosa** | **Mittausarvot** |
| --- | --- |
| **Päivitys** |  Yhteensä: kunkin tietovuon päivitysten kokonaismäärä<br>  Luotettavuus: kullekin tietovuolle suoritettujen päivitysten prosenttiosuus<br>  Keskimääräinen odotusaika: keskimääräinen viive ajoitetun ajankohdan ja tietovuon päivityksen alkamisen välillä minuutteina<br>  Enimmäisodotusaika: tietovuon enimmäisodotusaika minuutteina <br>  Keskimääräinen kesto: tietovuon päivityksen keskimääräinen kesto minuutteina<br>  Enimmäiskesto: tietovuon pitkäkestoisimman päivityksen kesto minuutteina |
| **Top 5 tietovuota päivityksen keskimääräisen keston mukaan** |  Viisi tietovuota, joilla on pisin päivityksen keskimääräinen kesto minuutteina |
| **Top 5 tietovuota keskimääräisen odotusajan mukaan** |  Viisi tietovuota, joilla on pisin päivityksen keskimääräinen odotusaika minuutteina |
| **Päivityksen keskimääräinen odotusaika tunneittain** |  Tämä on päivityksen keskimääräinen odotusaika tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna. Useat korkeat päivityksen odotusaikapiikit ovat merkki kuumana käyvästä kapasiteetista. |
| **Päivitysmäärä tunneittain ja muistin käyttö** |  Onnistumiset, epäonnistumiset ja muistin käyttö tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna |
|  |  |

#### <a name="resource-consumption"></a>Resurssien kulutus

**Resurssien kulutus** -välilehdessä näkyy suorittimen ja muistin käyttö kaikissa kapasiteeteissa ja työmäärissä.

| **Raporttiosa** | **Mittausarvot** |
| --- | --- |
| **Suorittimen kulutus** |  Tämä on kulutus työmäärittäin prosenttiosuutena suorittimen kokonaiskapasiteetista. Tämä näytetään tunneittain seitsemältä edelliseltä päivältä. |
| **Muistin käyttö** |  Tämä on muistin kulutus gigatavuina työmäärittäin (yhtenäiset viivat), työmäärärajoitukset näytetään myös (katkoviivat). Tämä näytetään tunneittain seitsemältä edelliseltä päivältä. |
|  |  |

#### <a name="ids-and-info"></a>Tunnukset ja tiedot

**Tunnukset ja tiedot** -välilehdessä näkyvät kapasiteettien, työtilojen ja työmäärien nimet, tunnukset ja omistajat.


## <a name="monitor-power-bi-embedded-capacity"></a>Power BI Embedded -kapasiteetin valvonta

Voit käyttää Power BI Premium -kapasiteetin mittausarvot -sovellusta *A SKU* -kapasiteettien valvontaan Power BI Embeddedissä. Kyseiset kapasiteetit näkyvät raportissa niin kauan kuin olet kapasiteetin järjestelmänvalvoja. Raportin päivitys kuitenkin epäonnistuu, ellet myönnä Power BI:lle tiettyjä käyttöoikeuksia A-varastointiyksiköissä:

1. Avaa kapasiteettisi Azure-portaalissa.

1. Valitse **Käyttöoikeuksien valvonta (IAM)** ja lisää Power BI Premium -sovellus lukijan rooliin. Jos et löydä sovellusta nimen mukaan, voit myös lisätä sen asiakastunnuksen mukaan: cb4dc29f 0bf4-402a-8b30-7511498ed654.

    ![Power BI Embeddedin käyttöoikeudet](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> Voit valvoa Power BI Embedded -kapasiteetin käyttöä sovelluksessa tai Azure-portaalissa, mutta et Power BI -hallintaportaalissa.


## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
> [Power BI Premium -kapasiteetin resurssien hallinta ja optimointi](service-premium-understand-how-it-works.md)
