---
title: Power BI Premium -kapasiteettien valvominen organisaatiossasi
description: Power BI -hallintaportaalin ja Power BI Premium -kapasiteetin mittausarvot -sovellus
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/09/2018
LocalizationGroup: Premium
ms.openlocfilehash: 2623dd3280636583d5dd6d6e3f57518550032193
ms.sourcegitcommit: 42475ac398358d2725f98228247b78aedb8cbc4f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003198"
---
# <a name="monitor-power-bi-premium-and-power-bi-embedded-capacities"></a>Power BI Premiumin ja Power BI Embeddedin kapasiteettien valvonta

Tässä artikkelissa annetaan yleiskatsaus Power BI Premium -kapasiteettien mittausarvojen valvonnasta. Kapasiteetin käytön valvonnan avulla voit hallita kapasiteettejasi valistuneesti.

Voit valvoa kapasiteettia Power BI Premium -kapasiteetin mittausarvot -sovelluksen avulla tai hallintaportaalissa. Sovelluksen käyttäminen on suositeltavaa, koska se tarjoaa paljon enemmän tietoja, mutta tässä artikkelissa käsitellään molemmat vaihtoehdot.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UgsjMbhi_Bk?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="install-the-premium-capacity-metrics-app"></a>Premium-kapasiteetin mittausarvot -sovelluksen asentaminen

Voit siirtyä suoraan [Premium-kapasiteetin mittausarvot -sovellukseen](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) tai asentaa sen muiden Power BI -sovellusten tapaan.

1. Valitse Power BI:ssä **Sovellukset**.

    ![Sovelluksiin siirtyminen](media/service-admin-premium-monitor-capacity/apps.png)

2. Valitse oikealla puolella **Hanki sovelluksia**.

3. Hae **Sovellukset**-luokasta **Power BI Premium -kapasiteetin mittausarvot -sovellus**.

4. Tilaa sovelluksen asennus.

Nyt kun olet asentanut sovelluksen, voit nähdä kapasiteetteja koskevia mittausarvoja organisaatiossasi. Tutustutaan muutamaan tärkeimpään käytettävissä olevaan mittausarvoon.

## <a name="use-the-metrics-app"></a>Mittausarvosovelluksen käyttäminen

Kun avaat sovelluksen, se näyttää ensin raporttinäkymältä, jossa on yhteenveto kaikista kapasiteeteista, joihin sinulla on järjestelmänvalvojan oikeudet.

![Mittausarvosovelluksen koontinäyttö](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Raportissa on kolme välilehteä, jotka kuvataan tarkemmin seuraavissa osissa.

* **Kaikkia sivuja koskevat suodattimet**: voit suodattaa raportin muut sivut tiettyyn kapasiteettiin.
* **Tietojoukot**: tarjoaa yksityiskohtaisia mittausarvoja tietojoukkojen kunnosta kapasiteettiesi sisällä.
* **Järjestelmä**: antaa yleiset kapasiteetin mittausarvot, mukaan lukien muisti ja suorittimen korkea käyttö. 

### <a name="filters-applied-to-all-pages-tab"></a>Kaikkia sivuja koskevat suodattimet -välilehti

**Kaikkia sivuja koskevat suodattimet** -välilehden avulla voit valita kapasiteetin, tietojoukon ja päivämääräalueen viimeisten seitsemän päivän aikana. Suodattimia käytetään sitten kaikilla raportin asiaankuuluvilla sivuilla ja ruuduissa. Jos mitään suodattimia ei ole valittuna, raportti näyttää oletuksena edellisen viikon mittausarvot jokaisesta omistamastasi kapasiteetista.

![Suodattimet-välilehti](media/service-admin-premium-monitor-capacity/filters-tab.png)

### <a name="datasets-tab"></a>Tietojoukot-välilehti

**Tietojoukot**-välilehdessä ovat sovelluksen mittausarvojoukot. Voit siirtyä eri alueille välilehden yläreunassa olevien painikkeiden avulla: **Yhteenveto**, **Päivitykset**, **Kyselyjen kestot**, **Kysely odottaa** ja **Tietojoukot**.

![Tietojoukot-välilehti](media/service-admin-premium-monitor-capacity/datasets-tab.png)

#### <a name="summary-area"></a>Yhteenveto-alue

**Yhteenveto**-alue näyttää kapasiteettiesi näkymät entiteettien, järjestelmäresurssien ja tietojoukon kuormitusten perusteella.

| | **Mittausarvot** |
| --- | --- |
| **Entiteetit** | * Omistamiesi kapasiteettien määrä<br> * Tietojoukkojen erillinen määrä kapasiteetissasi<br> * Työtilojen erillinen määrä kapasiteetissasi |
| **Järjestelmä** | * Keskimääräinen muistin käyttö gigatavuina viimeisten seitsemän päivän aikana<br> * Suurin muistin kulutus gigatavuina viimeisten seitsemän päivän aikana ja paikallinen tapahtumisaika<br> * Kuinka monta kertaa suoritin ylitti 80 prosenttia raja-arvoista viimeisten seitsemän päivän aikana kolmen minuutin osiin jaettuna<br> * Ajankohdat, jolloin suoritin useimmin ylitti 80 prosenttia viimeisten seitsemän päivän aikana tunnin osiin jaettuna sekä paikallinen tapahtumisaika<br> * Kuinka monta kertaa Direct Query- / reaaliaikainen yhteys ylitti 80 prosenttia raja-arvoista viimeisten seitsemän päivän aikana kolmen minuutin osiin jaettuna<br> * Ajankohdat, jolloin Direct Query- / reaaliaikainen yhteys useimmin ylitti 80 prosenttia viimeisten seitsemän päivän aikana tunnin osiin jaettuna sekä paikallinen tapahtumisaika |
| **Tietojoukon kuormitukset** | * Päivitysten kokonaismäärä viimeisten seitsemän päivän aikana<br> * Onnistuneiden päivitysten kokonaismäärä viimeisten seitsemän päivän aikana<br> * Epäonnistuneiden päivitysten kokonaismäärä viimeisten seitsemän päivän aikana<br> * Muistin loppumisen vuoksi epäonnistuneiden päivitysten kokonaismäärä<br> * Päivityksen keskimääräinen kesto mitataan minuutteina, toiminnon suorittamiseen tarvittava aika<br> * Päivityksen keskimääräinen odotusaika mitataan minuutteina, keskimääräinen viive ajoitetun ajankohdan ja toiminnon alun välillä<br> * Suoritettujen kyselyjen kokonaismäärä viimeisten seitsemän päivän aikana<br> * Onnistuneiden kyselyjen kokonaismäärä viimeisten seitsemän päivän aikana<br> * Epäonnistuneiden kyselyjen kokonaismäärä viimeisten seitsemän päivän aikana<br> * Kyselyn keskimääräinen kesto mitataan minuutteina, toiminnon suorittamiseen tarvittava aika<br> * Muistipaineen vuoksi poistettujen mallien kokonaismäärä |
|  |  |

#### <a name="refreshes-area"></a>Päivitykset-alue

**Päivitykset**-alue sisältää valmiit päivitykset, onnistuneet mittaukset, päivityksen odotusajan keski-/enimmäisarvon ja päivityksen keston keski-/enimmäisarvon tietojoukkojen mukaan ositettuna viimeisten seitsemän päivän aikana. Kahdessa alimmassa kaaviossa näkyvät päivitykset ja muistin käyttö gigatavuina ja keskimääräiset odotusajat tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna. Yläreunan palkkikaaviot sisältävät viisi parasta tietojoukkoa tietojoukon päivittämiseen kuluneen (päivityksen keston) keskiarvon sekä päivityksen odotusajan keskiarvon mukaan. Useat korkeat päivityksen odotusaikapiikit ovat merkki kuumana käyvästä kapasiteetista.

#### <a name="query-durations-area"></a>Kyselyjen kestot -alue

**Kyselyjen kestot** -alueella luetellaan suoritettujen kyselyjen kokonaismäärä ja niiden keskimääräinen ja enimmäiskesto millisekunteina. Nämä tiedot on ositettu tietojoukkojen, työtilan ja tunnittaisten säilöjen mukaan viimeisten seitsemän päivän ajalta. Alimmainen kaavio näyttää kyselyjen määrän ja keston keskiarvon (millisekunteina) vs. muistin kulutuksen gigatavuina tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna.

Oikean yläkulman kaavio näyttää kyselyn keston jakaumahistogrammin. Histogrammi on jaoteltu millisekunneissa ilmoitettujen kyselyjen kestojen mukaan seuraaviin luokkiin: < 30 ms, 30–100 ms, 100–300 ms, 300 ms–1 s, 1–3 s, 3–10 s, 10–30 s ja > 30 s.

Oikean alakulman kaavio näyttää viisi parasta tietojoukkoa kyselyn suorittamisen keston keskiarvon mukaan.

Kyselyjen pitkät kestot ja odotusajat ovat osoitus siitä, että kapasiteetti on äärirajoilla. Se saattaa myös tarkoittaa sitä, että yksi tietojoukko aiheuttaa ongelmia ja tarkempaa tutkimusta tarvitaan.

#### <a name="query-waits-area"></a>Kysely odottaa -alue

**Kysely odottaa**  -alueella luetellaan suoritettujen kyselyiden kokonaismäärä, odottavien kyselyjen kokonaismäärä reaaliaikaiselle/suoralle kyselylle ja odotusajan keski-/enimmäisarvo millisekunteina. Nämä tiedot on ositettu tietojoukkojen, työtilan ja tunnittaisten säilöjen mukaan viimeisten seitsemän päivän ajalta. Alimmainen kaavio näyttää odottavien kyselyjen määrän ja odotusajan keskiarvon (millisekunteina) vs. muistin kulutuksen gigatavuina tunnin osiin jaettuna paikallisessa ajassa ilmoitettuna.

Oikean yläkulman kaavio näyttää kyselyn odotusajan jakaumahistogrammin. Histogrammi on jaoteltu millisekunneissa ilmoitettujen kyselyjen kestojen mukaan seuraaviin luokkiin: < 50 ms, 50–100 ms, 100–200 ms, 200–400 ms, 400 ms–1 s, 1–5 s ja > 5 s.

Oikean alakulman kaavio näyttää viisi parasta tietojoukkoa kyselyn aloittamisen odotusajan keskiarvon mukaan.

#### <a name="datasets-area"></a>Tietojoukot-alue

**Tietojoukot**-alue näyttää muistipaineen vuoksi poistetut valmiit tietojoukot tunnin mukaan.

### <a name="system-tab"></a>Järjestelmä-välilehti

**Järjestelmä**-välilehti näyttää suorittimen korkean käytön ajat (80 prosentin käyttöaste ylittymiskertojen määrä), suoran kyselyn / reaaliaikaisen yhteyden korkean käyttöasteen ja muistin käytön.

![Premium-järjestelmäraportti](media/service-admin-premium-monitor-capacity/system-tab.png)

## <a name="monitor-power-bi-embedded-capacity"></a>Power BI Embedded -kapasiteetin valvonta

Voit käyttää myös Power BI Premium -kapasiteetin mittausarvot -sovellusta *A-varastointiyksikkö*-kapasiteettien valvontaan Power BI Embeddedissä. Kyseiset kapasiteetit näkyvät raportissa niin kauan kuin olet kapasiteetin järjestelmänvalvoja. Raportin päivitys kuitenkin epäonnistuu, ellet myönnä Power BI:lle tiettyjä käyttöoikeuksia A-varastointiyksiköissä:

1. Avaa kapasiteettisi Azure-portaalissa.
1. Valitse **Käyttöoikeuksien valvonta (IAM)** ja lisää Power BI Premium -sovellus lukijan rooliin. Jos et löydä sovellusta nimen mukaan, voit myös lisätä sen asiakastunnuksen mukaan: cb4dc29f 0bf4-402a-8b30-7511498ed654.

    ![Power BI Embeddedin käyttöoikeudet](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> Voit valvoa Power BI Embedded -kapasiteetin käyttöä sovelluksessa tai Azure-portaalissa, mutta et Power BI -hallintaportaalissa.

## <a name="basic-monitoring-in-the-admin-portal"></a>Perustason valvonta hallintaportaalissa

Hallintaportaalin **Kapasiteettiasetukset**-alueella on neljä mittaria, jotka ilmoittavat kapasiteetin asettamat kuormitukset ja käyttämät resurssit viimeisten seitsemän päivän ajalta. Nämä neljä ruutua toimivat tuntikohtaisessa aikaikkunassa, joka ilmaisee, kuinka monta tuntia vastaava mittausarvo oli yli 80 prosenttia viimeisten seitsemän päivän aikana. Tämä mittausarvo ilmaisee mahdollisen käyttäjäkokemuksen heikkenemisen.

![Käyttö 7 päivän aikana](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Suoritin |Kuinka monta kertaa suoritin ylitti 80 prosentin käyttöasteen. |
| Muistin tietojen poistaminen |Kuvastaa taustatoimintojen ydinten muistin vähyyttä. Tarkemmin sanottuna tämä ilmaisee, kuinka monta kertaa tietojoukkoja poistetaan muistista useiden tietojoukkojen aiheuttaman muistin vähäisyyden vuoksi. |
| Muistin käyttö |Keskimääräinen muistin käyttö gigatavuina (Gt). |
| DQ-kyselyjä/s | Kuinka monta kertaa DirectQueryn ja reaaliaikaisten yhteyksien määrä ylitti 80 prosenttia rajoituksesta. <br> * DirectQuery- ja reaaliaikaisen yhteyden kyselyiden sekuntikohtainen kokonaismäärä on rajoitettu.* Rajoitus on 30/s P1:llä, 60/s P2:lla ja 120/s P3:lla. * DirectQuery- ja reaaliaikaisen yhteyden kyselyiden määrä lasketaan kiintiöön. Jos sinulla on käynnissä esimerkiksi 15 DirectQuery-kyselyä ja 15 reaaliaikaista yhteyttä samalla sekunnilla, nopeutta rajoitetaan.<br>* Tämä koskee niin paikallisia kuin pilviyhteyksiäkin. |
|  |  |

Mittarit kuvaavat käyttöä viime viikon aikana.  Jos haluat tarkastella mittareita tarkemmin, voit tehdä niin napsauttamalla jotakin yhteenvetoruutua.  Sen jälkeen näet yksityiskohtaiset kaaviot Premium-kapasiteetin mittareista. Seuraavassa kaaviossa näkyvät suorittimen mittausarvon tiedot.

![Suorittimen yksityiskohtainen käyttökaavio](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Näissä kaavioissa on tuntikohtainen yhteenveto viime viikolta ja ne voivat auttaa selvittämään, jos Premium-kapasiteetissasi on ollut jokin suorituskykyyn liittyvä tapahtuma.

Voit myös viedä minkä tahansa mittarin pohjana olevat tiedot csv-tiedostoon.  Tämän viennin ansiosta saat yksityiskohtaista tietoa kolmen minuutin välein viime viikon kultakin päivältä.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun tiedät, miten voit valvoa Power BI Premium -kapasiteetteja, lue lisätietoja kapasiteettien optimoinnista.

> [!div class="nextstepaction"]
> [Power BI Premium -kapasiteetin resurssien hallinta ja optimointi](service-premium-understand-how-it-works.md)
