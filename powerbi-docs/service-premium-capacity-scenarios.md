---
title: Microsoft Power BI Premium-kapasiteetin skenaarioita
description: Tässä artikkelissa kuvataan Power BI Premium-kapasiteetin yleisiä skenaarioita.
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
ms.openlocfilehash: 1d666a6702515a935d93549d026f207848f2bca8
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565332"
---
# <a name="premium-capacity-scenarios"></a>Premium-kapasiteetin skenaarioita

Tässä artikkelissa kuvataan todellisia skenaarioita, joissa Power BI premium-kapasiteetteja on toteutettu. Yleisiä ongelmia ja haasteita on kuvattu myös ongelmien tunnistaminen ja korjata ne:

- [Tietojoukot pitäminen ajan tasalla](#keeping-datasets-up-to-date)
- [Tunnistetaan hidastaa vastaamisen tietojoukot](#identifying-slow-responding-datasets)
- [Tunnistetaan syitä 0x1E hidastaa-DSR-tietojoukot](#identifying-causes-for-sporadically-slow-responding-datasets)
- [Selvitettäessä, onko tarpeeksi muistia](#determining-whether-there-is-enough-memory)
- [Selvitettäessä, onko tarpeeksi Suoritin](#determining-whether-there-is-enough-cpu)

Kaavio ja taulukko esimerkkejä ja ohjeita ovat **Power BI Premium-kapasiteetin Mittaustietoihin sovelluksen** , että Power BI-järjestelmänvalvoja pystyy käyttämään.

## <a name="keeping-datasets-up-to-date"></a>Tietojoukot pitäminen ajan tasalla

Tässä skenaariossa tutkimuksen käynnistettiin, kun käyttäjät havaittujen, että raporttitietoja joskus ominaisuudelta vanhojen tai ”vanhentuneiden”.

Järjestelmänvalvoja vuorovaikutuksessa sovelluksen kanssa **päivittää** visualisoinnin lajittelua tietojoukkojen latautuminen **Max odotusaika** tilastot laskevassa järjestyksessä. Tämä visualisointi auttaa heitä paljastaa tietojoukot on pisimmän Odota-kertaa työtilan nimen mukaan.

![Lajiteltu laskevaan järjestykseen max Tietojoukkosi päivittyy odotusaika, työtilan Ryhmittelyperuste](media/service-premium-capacity-scenarios/dataset-refreshes.png)

- **Tunneittain keskimääräinen Päivitä Odota kertaa** visualisoinnin, hän Huomaa, että Odota päivitysajat piikin johdonmukaisesti noin 4 PM päivä.

![Päivitä odottaa piikin säännöllisesti kello 4](media/service-premium-capacity-scenarios/peak-refresh-waits.png)

On useita mahdollisia syitä, että nämä tulokset:

- Liian monta päivityksen yritysten voitu voi suoritetaan samaan aikaan ylitysten määritetty kapasiteetin solmu. Tässä tapauksessa kuusi samanaikaisten päivitykset käyttöön P1 oletusarvon muistin varaaminen kanssa.

- Tietojoukkoja voi päivittää voi olla liian suuri mahtuu käytettävissä olevaa muistia (vaatia vähintään 2 täydellinen vaatimaa muistia).
- Tehottomia Power Query-logic saattaa tuloksena muistin käyttö huipussaan tietojoukon päivityksen aikana. Tämä piikki on varattu kapasiteetti toisinaan matkapuhelimessasi fyysinen raja päivitys epäonnistuu, jotka vaikuttavat mahdollisesti muut raportin Näytä toiminnot kapasiteetin.
- Usein kysellyt tietojoukkoja, jotka on pysy muistissa saattaa vaikuttaa muihin tietojoukkoihin, Päivitä rajoitettu muistia vuoksi.

Power BI-järjestelmänvalvoja voi etsiä asiaa, joiden:

- Tietojen milloin käytettävissä muisti päivitetään, kun käytettävissä olevaa muistia on pienempi kuin 2, on päivitettävä tietojoukon koosta x.
- Tietojoukkoja ei päivitetty ja ole muistissa ennen päivityksen, vielä alkanut näyttämään vuorovaikutteinen liikenteen raskas päivitysajat aikana. Jos haluat nähdä, mitä tietojoukkoja ladataan muistiin milloin tahansa, tietojoukot alueen tarkastella Power BI-järjestelmänvalvojan **tietojoukkoja** välilehti sovelluksessa. Järjestelmänvalvoja voi sitten ristiinsuodatuksen annetun ajaksi napsauttamalla palkkien **tunneittain ladata tietojoukko laskee**. Paikallinen huipussaan, kuvassa alla ilmaisee tunti, kun useita tietojoukkoja ladattiin muistiin, joka saattaa viive ajoitettujen päivitysten alku.
- Parannettu tietojoukon häätöjä ottaen Sijoita Aloita ajoitettuja tietojen päivityksiä. Häätöjä voi ilmaista on suuri muistipainetta aiheutui käsittelevä liian monta eri vuorovaikutteisia raportteja ennen päivityksen aikana. **Tunneittain tietojoukon Häätöjä ja muistin kulutuksen** visual selvästi ilmaistaan häätöjä piikkarit.

Seuraavassa kuvassa näytetään paikallisen huipussaan ladattujen tietojoukkojen joka ehdottaa vuorovaikutteinen kyselyä viivyttää alkuun päivitykset. Valitsemalla tietyn ajanjakson **tunneittain ladata tietojoukko laskee** visualisointi ristiinsuodatuksen **tietojoukkojen koon** visualisoinnin.

![Paikallinen huipussaan ladata tietojoukoissa ehdottaa vuorovaikutteinen kyseltäessä Viivästetty alku päivitykset](media/service-premium-capacity-scenarios/hourly-loaded-dataset-counts.png)

Power BI-järjestelmänvalvoja, voit yrittää ratkaista ongelman noudattamalla ohjeita sen varmistamiseksi, että tarpeeksi muistia on käytettävissä tietojen päivityksiä käynnistäminen:

- Muodostettaessa yhteyttä tietojoukon omistajat ja jossa heitä lomittaa välilyönti pois tiedot päivittää aikatauluja.
- Pienentää tietojoukon kyselyn kuormitusta poistamalla tarpeettomat koontinäyttöjä tai koontinäytön ruuduista, etenkin sellaisia, jotka rivitason suojausta.
- Nopeuttaminen Power Query logic optimoimalla tietojen päivityksiä. Parantaa mallinnus lasketut sarakkeet tai taulukot. Pienentää tietojoukon kokoa tai määritä suurempi tietojoukkoja suorittaa lisäävä tietojen päivittäminen.

## <a name="identifying-slow-responding-datasets"></a>Tunnistetaan hidastaa vastaamisen tietojoukot

Tässä skenaariossa käyttäjät havaittujen tiettyjen raporttien kesti liian kauan avata, tutkimuksen alkamisen ja joskus sulkemalla puhelin.

Sovelluksessa on Power BI-järjestelmänvalvoja voi käyttää **kyselyn keston** visual määrittämään huonoiten suoriutuva tietojoukkoja lajittelemalla tietojoukkoja mukaan laskevasti **keskimääräinen kesto**. Tämä visualisointi näkyy myös tietojoukon kyselyn määrää, jotta näet, miten usein tietojoukkoja tehdään kysely.

![Huonoiten suoriutuva tietojoukot](media/service-premium-capacity-scenarios/worst-performing-datasets.png)

Järjestelmänvalvoja voi viitata **kyselyn keston jakelu** visualisoinnin, joka näyttää tuloksesi kyselyn suorituskyvyn yleisen jakautumisen (< = 30 MS, 0 – 100 millisekunnin yksikköinä) suodatettu ajanjaksolla. Yleensä kyselyt, ota yksi sekunti tai enintään käsittelemien reagoiva useimmat käyttäjille. Kyselyt, jotka kestää kauemmin tapana luoda näkemys virheellinen suorituskyvystä.

**Tunneittain kyselyn keston jakelu** visualisoinnin avulla Power BI-järjestelmänvalvoja voi tunnistaa yhden tunnin kun kapasiteetin suorituskyky saattaa olla on valittuna käytetä tarkastellaan kokonaisena niin huono. Mitä suurempi palkin lohkoja edustavat kysely kestot yli yksi sekunti, suurempaa riskin, että käyttäjät näkee heikentää suorituskykyä.

Visualisointi on vuorovaikutteinen ja segmentin palkin valittaessa vastaava **kyselyn keston** taulukkovisualisointi raportin sivulla on ristiinsuodatuksia näyttämään se edustaa tietojoukkoja. Tämä ristiinsuodatus avulla Power BI-järjestelmänvalvoja voi helposti joka tietojoukot ovat vastaamisen hitaasti.

Seuraavassa kuvassa näytetään visualisoinnin suodattanut **tunneittain kyselyn keston jaot**, kohdentaminen yhden tunnin säilöjen huonoiten suoriutuva tietojoukoille. 

![Suodatettu tunneittain kyselyn keston jaot visual näyttää tietämättäsi suorittamisen tietojoukot](media/service-premium-capacity-scenarios/hourly-query-duration-distributions.png)

Kun tunnistetaan tietyn tunnin timespan huono suorittavan tietojoukon, Power BI-järjestelmänvalvoja voi tutkia asiaa heikentää suorituskykyä aiheutuu ylikuormittunut kapasiteetti, onko vuoksi huonosti suunniteltu tietojoukon tai raportin. He voivat viitata **kyselyn Odota kertaa** visualisoinnin ja Lajittele tietojoukkoja mukaan laskevasti kyselyiden keskimääräinen odotusaika. Jos kyselyt suuri prosenttiosuus odottaa, tietojoukon suuren tarvittaessa on todennäköisesti liikaa kyselyn odottaa syyn. Jos kyselyiden keskimääräinen odotusaika on merkittäviä (> 100 ms), se voi olla tarpeen harkita tarkastelet tietojoukon ja raportin nähdäksesi, jos optimointeja voi tehdä. Esimerkiksi vähemmän visualisoinnit annettu raporttisivujen tai DAX-lausekkeen optimoinnin.

![Kyselyn Odota kertaa visualisointi auttaa paljastaa huonosti suorittavan tietojoukot](media/service-premium-capacity-scenarios/query-wait-times.png)

On kyselyn Odota aika kertymisen tietojoukoissa useita mahdollisia syitä:

- Mahdollisimman mallin rakenteen tai jopa raportin suunnittelun - kaikissa tilanteissa, voit itse osallistua measure-lausekkeiden pitkään suoritettavat kyselyt, jotka käyttävät suorittimen korkean. Tämä pakottaa uusien kyselyiden Odota, kunnes suorittimen säikeiden saataville ja luoda convoy voimaan (Kuvittele liikenteen hillot), joka on nähty yleisesti piikin virka-aikana. **Kyselyn odottaa** sivu on tärkein resurssin päätellä, tietojoukot suuren kyselyiden keskimääräinen odotusaika kertaa.
- Samanaikainen kapasiteetti käyttäjät (satoja tuhansia) määrä kuluttaja saman raportin tai tietojoukon. Jopa hyvin suunniteltu tietojoukot voivat suorittaa virheellisesti asettamiesi samanaikaisuuden raja-arvo. Tämä ilmaistaan yleensä näytetään huomattavasti suurempi arvo-kyselyn laskee kuin muut tietojoukot Näytä yksi tietojoukko (esimerkiksi 300 K kyselyt-yksi tietojoukko verrattuna < 30K kyselyt muihin tietojoukkoihin). Jotkin kohdassa kyselyn odottaa-tämän tietojoukon alkaa lomittaa, joka voi nähdä **kyselyn keston** visualisoinnin.
- Monta eri tietojoukkoa kysely samanaikaisesti, aiheuttaa tietojen poistaminen, kuten tietojoukot käydä usein uloskirjautuminen muistia. Tämän tuloksena käyttäjät ilmenee hidas, kun tietojoukko ladataan muistiin. Vahvista, Power BI-järjestelmänvalvoja voi viitata **tunneittain tietojoukon Häätöjä ja muistin kulutuksen** visualisoinnin, joka saattaa ilmaista, että suuren määrän tietojoukkoja ladataan muistiin ovat toistuvasti häädettävän.

## <a name="identifying-causes-for-sporadically-slow-responding-datasets"></a>Tunnistetaan syitä 0x1E hidastaa-DSR-tietojoukot

Tässä skenaariossa tutkimuksen alkamisen, kun käyttäjät, jotka on kuvattu, että raportin visualisointien joskus on hidas vastaa tai saattaa lopettaa vastaamisen, mutta joskus ne olivat acceptably reagoiva.

Sovelluksessa **kyselyn keston** osiossa käytettiin löytää virheen aiheuttaja tietojoukon seuraavalla tavalla:

- - **Kyselyn keston** visual järjestelmänvalvoja suodatettu tietojoukon mukaan tietojoukon (alkaen kysely yläreunan tietojoukot) ja tutkia ristisuodatuksen suodatettu palkkien **tunneittain kyselyn jaot** visualisoinnin.
- Kun yhden tunnin palkin näytimme merkittäviä muutoksia kaikki kyselyn keston ryhmät ja yhden tunnin muita palkkeja tietojoukossa suhde (esimerkiksi värit väliset suhteet muuttuu raporttikyselyt), se tarkoittaa, että tätä tietojoukkoa osoittaa tilapäisiä muutos suorituskyvyn.
- Näytetään suoriutuvien kyselyiden, epäsäännölliset osan yhden tunnin palkit osoittaa timespan, jossa tietojoukko on vaikuttaa Meluisa naapuri voimassa, jotka muihin tietojoukkoihin.

Kuva alla näkyy tunnin 30. tammikuuta, jos ilmeni merkittäviä aikaisemmin tietojoukon suorituskykyä, merkkinä kokoa ”(3,10s]” suorituksen kesto säilöön. Valitsemalla yhden tunnin rivi paljastaa, että kaikki tietojoukkoja ladataan muistiin tänä aikana henkilöstö voi aiheuttaa Meluisa naapuri voimaan tietojoukkoja.

![Palkki, joka näyttää pahimmassa suorituskyvyn suuri osa](media/service-premium-capacity-scenarios/worst-performing-queries.png)

Kun ongelmallinen timespan tunnistetaan (esimerkiksi aikana tämän 30 yllä olevassa kuvassa) Power BI-järjestelmänvalvoja voi poistaa kaikki tietojoukon suodattimet sitten suodattaminen kyseisen timespan määrittämään, mitä tietojoukkoja on aktiivisesti kyselyitä tänä aikana. Meluisa naapuri tehosteen virheen aiheuttaja-tietojoukko on yleensä yläreunan kysellyt tietojoukon tai jokin pisimpään kyselyiden keskimääräinen kesto.

Jakaa eri työtilat eri Premium-kapasiteetteja tai jaettuun kapasiteettiin, jos tietojoukon kokoa, vaatimusten ja tietojen päivittäminen mallien kautta tietojoukkoja tuetaan virheen aiheuttaja voi ratkaista tämän ongelman.

Vastaavasti voi olla tosi myös. Power BI-järjestelmänvalvoja voi tunnistaa kertaa, kun tietojoukko kyselyn suorituskyvyn raporttikyselyt parantaa ja Etsi mitä katosi. Jos tiettyjä puuttuu kyseisen vaiheessa, sitten, jotka auttavat osoittamaan aiheuttavan ongelma.

## <a name="determining-whether-there-is-enough-memory"></a>Selvitettäessä, onko tarpeeksi muistia

Voit selvittää, onko tarpeeksi muistia kapasiteetin suorittamiseen sen kuormituksia, Power BI-järjestelmänvalvoja voi viitata **kuluttaa muistia prosenttiosuudet** visualisointia **tietojoukkoja** sovelluksen-välilehdessä. **Kaikki** (yhteensä) muistin edustaa tietojoukkoja ladataan muistiin, riippumatta siitä, ovatko ne aktiivisesti kyselyitä tai käsitellä kuluttaa muistia. **Aktiivinen** muistin edustaa tietojoukkoja, jotka aktiivisesti käsitellään kuluttaa muistia.

Kunnossa olevaa kapasiteettia visualisointi näyttää tämän, näytetään kaikki (yhteensä) välille välin ja aktiivinen:

![Kunnossa olevaa kapasiteettia näyttää kaikki (yhteensä) välille välin ja aktiivinen](media/service-premium-capacity-scenarios/memory-healthy-capacity.png)

Muistipainetta ilmenee kapasiteettia samaan visualisointiin näkyvät selvästi, aktiivisen muistin ja muistin kokonaismäärä Yhtyvä, mikä tarkoittaa, että se on mahdotonta muita tietojoukkojen lataaminen muistiin sitten. Tässä tapauksessa Power BI-järjestelmänvalvojan napsauttamalla **kapasiteetin uudelleen** (- **lisäasetukset** hallintaportaalin kapasiteetin asetukset-alueen). Käynnistetään uudelleen kapasiteetin tulokset kaikki tietojoukot on tyhjentää muistista ja sallimalla uudelleen muistiin (jota kyselyitä tai tietojen päivitys).

![** Aktiivinen ** muistin Yhtyvä kanssa ** kaikki ** muisti](media/service-premium-capacity-scenarios/memory-unhealthy-capacity.png)

## <a name="determining-whether-there-is-enough-cpu"></a>Selvitettäessä, onko tarpeeksi Suoritin

Yleensä ostat kapasiteettia keskimääräinen suorittimen käyttöaste pitäisi pysyä 80 prosentin alla. Suurempi kuin tämä arvo tarkoittaa kapasiteetin lähestyy suorittimen kylläisyys.

Suorittimen kylläisyys vaikutukset ilmaistaan kauemmin niiden pitäisi vuoksi tiedoillesi monta suorittimen kontekstit valitsinta, kun se yrittää käsitellä kaikki toiminnot kapasiteetin toiminnot. Premium-kapasiteetissa, jonka samanaikaisten kyselyiden määrä Tämä ilmaisee suuren kyselyn Odota kertaa. Suuren kyselyn Odota kertaa seurausta on tavallista hitaammin reagoinnin. Power BI-järjestelmänvalvojan muistat helposti, kun suorittimen on tyydyttyneet tarkastelemalla **tunneittain kyselyn Odota aika jaot** visualisoinnin. Kyselyn kausittaisten päät määrät ilmaista mahdollisen suorittimen kylläisyys odotusaika.

![Kyselyn kausittaisten päät odotusaika määrät ilmaista mahdollisen suorittimen kylläisyys](media/service-premium-capacity-scenarios/peak-query-wait-times.png)

Samanlaisen kuvion joskus voidaan tunnistaa taustan toiminnot, jos ne osallistua suorittimen kylläisyys. Power BI-järjestelmänvalvoja voi etsiä kausittaisten huipussaan päivitysajat, määritetyn tietojoukon, mikä voi ilmaista suorittimen kylläisyys aikaan (todennäköisesti vuoksi muita jatkuvan tietojoukkosi päivittyy ja/tai vuorovaikutteisia kyselyitä). Tässä esiintymässä, viittaavat **järjestelmän** näkymä sovelluksen eivät saa välttämättä paljastaa, että Suoritin on 100 prosenttia. **Järjestelmän** näkymä näyttää tunneittain keskiarvot, mutta Suoritin voi tulla tyydyttyneet muutaman minuutin ajan raskas toiminnoista, joka näkyy kuin piikkarit Odota kertaa.

On lisätietoja erityispiirteensä vaikutusta suorittimen kylläisyys tarkastelua. Odota kyselyiden määrä on tärkeää, kyselyn odotusaika aina tapahtuu jossain määrin aiheuttamatta discernable kansiohierarkiassa. Jotkin tietojoukot (jonka unohtui keskimääräinen kyselyn kertaa, joka ilmaisee monimutkaisuutta tai koko) on enemmän jotka altistuvat paketin suorittimen kylläisyys vaikutukset kuin muut. Tunnistamisessa nämä tietojoukot, Power BI-järjestelmänvalvoja voi hakea muutosten väri palkkien **tunneittain Odota aika jakelu** visualisoinnin. Jälkeen spotting harha palkki näyttää tietojoukoille, jotka oli kyselyn odottaa tänä aikana ne myös verrattuna keskimääräinen kesto kyselyn kyselyiden keskimääräinen odotusaika seurantaan. Kun nämä kaksi tiedot ovat samassa moninkertaisesti ja tietojoukon kyselyn kuormitus on muu kuin yksinkertainen, todennäköisesti tilauksista tietojoukko ei ole tarpeeksi suorittimen mukaan.

Tämä voi olla erityisen selviä, kun tietojoukko on kulutettu lyhyt bursts tiheän käyttövälin kyselyiden useat käyttäjät (esimerkiksi-koulutus istunnossa) tuloksena suorittimen kylläisyys kunkin jaksopyyntöjen aikana. Tässä tapauksessa merkittäviä kyselyn Odota kertaa tälle tietojoukolle voi kohtasi sekä vaikutuksia-kapasiteetti (Meluisa naapuri vaikutus) muihin tietojoukkoihin.

Joissakin tapauksissa Power BI-järjestelmänvalvoja voi myös pyytää, että tietojoukon omistajat luoda pienempi muuttuvia kyselyn kuormituksen luomalla raportin sijasta (välimuistiin ruutujen Päivitä kyselyt säännöllisesti kaikkien niiden tietojoukkojen kanssa) koontinäytön. Tämä estää piikkarit koontinäytön lataamisen yhteydessä. Tämä ratkaisu ei aina ole mahdollista, että annettu liiketoimintavaatimusten, mutta se voi olla tehokas tapa välttää suorittimen kylläisyys tekemättä muuttaminen tietojoukkoon.

## <a name="acknowledgements"></a>Kuittaussanomien

Tämä artikkeli koskee Peter Myers, tietojen Platform MVP ja riippumattoman BI asiantuntijan kanssa [Bitwise ratkaisuja](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
> [Valvo sovelluksen Premium-kapasiteetteja](service-admin-premium-monitor-capacity.md)    
> [!div class="nextstepaction"]
> [Valvo kapasiteettien hallintaportaalissa](service-admin-premium-monitor-portal.md)   

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

||||||