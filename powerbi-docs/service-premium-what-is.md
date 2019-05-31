---
title: Mikä on Microsoft Power BI Premium?
description: Power BI Premium tarjoaa varatun kapasiteettien organisaatiollesi, luotettavamman suorituskyvyn ja suuremmat tietomäärät ilman käyttäjäkohtaisten käyttöoikeuksien.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/22/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: e5ffa624bf69cf470aade076c80ac37028a55456
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565275"
---
# <a name="what-is-power-bi-premium"></a>Mikä on Power BI Premium?

Power BI Premium tarjoaa organisaatiollesi Power BI-palvelun erityinen ja parannettu resurssit. Esimerkki:

- Paremman skaalautuvuuden ja suorituskyvyn
- Voit käyttöoikeus-kapasiteetti
- Omatoiminen ja enterprise BI selkeyttää
- Laajenna paikallinen BI Power BI-raporttipalvelimen kanssa
- Tietojen tallennusta Saksassa vaatimukset tuki (monivalinta-Geo) alueen mukaan
- Jakaa tietoja kenen kanssa tahansa, ilman ostamisesta käyttäjäkohtainen käyttöoikeus

Tässä artikkelissa ei ole tarkoitettu on tarkempia tietoja kaikkia ominaisuuksia Power BI Premium - itse asiassa, se vain koskettaa pintaa. Tarvittaessa annetaan linkkejä artikkeleita tarkempia tietoja.

## <a name="subscriptions-and-licensing"></a>Tilaukset ja käyttöoikeudet

Power BI Premium on vuokraajatason Office 365: n tilaus saatavilla kaksi SKU (varastointiyksikkö) perheistä:

- **EM** (EM1 EM3) Varastointiyksiköt voit upottaa, jotka vaativat vuosittaista sitoutumista laskutetaan kuukausittain.
- **P** varastointiyksiköitä (P1 – P3) embedding- ja enterprise-, kuukausittaista tai vuosittaista sitoutumista, jotka vaativat laskutetaan kuukausittain, ja asenna paikallinen Power BI Report Server-käyttöoikeus sisältää.

Voit ostaa on vaihtoehtoinen menetelmä **Azure Power BI Embedded** tilaus, joka on yksi **A** (A1 – A6)-Varastointiyksikkö perheen upottaminen ja kapasiteetin testaukseen ilmoitusta. Ovat kaikki Varastointiyksiköt toimittaa v-ytimiä kapasiteettien luomiseen, mutta EM-Varastointiyksiköt on rajoitettu pienempi asteikon upottamista varten. EM1 ja EM2, A1 A2-varastointiyksiköiden, alle neljä v-ydintä ei suoriteta varattua infrastruktuurin.

Tässä artikkelissa keskitytään ollessa käytössä P-Varastointiyksiköt paljon on kuvattu koskee myös A-Varastointiyksikköjä. Toisin kuin Premium-tilauksen SKU-, Azure-Varastointiyksiköt eivät vaadi aika ei sitoutumista ja laskutetaan tunneittain. Ne toimittaa täysi joustavuus käyttöön skaalaus ylös, vieritettävä asteikon, keskeyttää, jatka ja poistaa. 

Azure Power BI Embedded on pitkälti tässä artikkelissa vaikutusalueen ulkopuolelle, mutta se on kuvattu [testaus lähestymistapoja](service-premium-capacity-optimize.md#testing-approaches) käytännön ja talous-asetusta, Testaa ja mitata kuormituksia optimointi Premium-kapasiteetteja-artikkelin osiossa. Saat lisätietoja Azure-Varastointiyksiköt [Azure Power BI Embedded-ohjeet](https://azure.microsoft.com/services/power-bi-embedded/).

### <a name="purchasing"></a>Ostaminen

Power BI Premium-tilaukset on ostettu järjestelmänvalvojat Microsoft 365-hallintakeskuksessa. Tarkemmin sanottuna vain Office 365: n Yleiset Järjestelmänvalvojat ja laskutuksen järjestelmänvalvojat voivat ostaa Varastointiyksiköt. Kun ostanut, Vuokraaja saa vastaavan määrän v-ytimiä kapasiteettien, jota kutsutaan liittäminen *v-ytimien rajoittaminen*. Esimerkiksi P3 SKU: n ostaminen antaa vuokraajan käyttöön 32 v-ydintä. Lisätietoja on artikkelissa [miten voit ostaa Power BI Premium](service-admin-premium-purchase.md).

## <a name="dedicated-capacities"></a>Varattua kapasiteettia

Saat Power BI Premium *järjestelmänvalvojalle kapasiteettien*. Jaettu kapasiteetti, jossa työnkulut suoritetaan jaetuissa Laskennallisissa muiden asiakkaiden kanssa, toisin kuin varattu kapasiteetti on yksinoikeudella organisaation. Se on eristetty varattua Laskennallisissa resursseja, jotka tasalaatuisen ja yhdenmukainen suorituskyky isännöity sisällölle. 

Työtilat sijaitsevat kapasiteettien. Power BI kullakin käyttäjällä on henkilökohtaista työtilaa, jota kutsutaan **oma työtila**. Lisää työtiloissa voi luoda yhteistyö- ja ota käyttöön ja näitä kutsutaan **Sovellustyötilat**. Työtilat, mukaan lukien Omat työtilat luodaan oletusarvoisesti jaetussa kapasiteetissa. Kun sinulla on Premium-kapasiteetteja, Omat työtilat ja sovelluksen työtilat voidaan määrittää Premium-kapasiteetteja.

### <a name="capacity-nodes"></a>Kapasiteetin solmut

Kuvatulla tavalla [tilauksia ja käyttöoikeuksien](#subscriptions-and-licensing) -osassa on kaksi Power BI Premium-SKU-perheissä: **EM** ja **P**. Kaikki Power BI Premium-SKU ovat käytettävissä kuin kapasiteetin *solmujen*, kukin resurssi edustaa tietyn määrän suorittimen, muistin ja tallennustilan resursseja. Sen lisäksi, että resurssit kunkin Varastointiyksikkö on toiminnalliset rajat Directqueryn ja Live-yhteyden yhteyksiä sekunnissa määrän ja parallel mallin määrä päivittää.

Käsittely on saavuttaa tietyn määrän v-ydintä, jakaa tasan taustapalvelu ja edustan välillä.

**Taustan v-ytimet** ovat vastuussa core Power BI-toimintoja, kuten kyselyn käsittelystä, välimuistin hallinnasta, R-palvelut, mallipäivityksen, luonnollisen kielen käsittelystä (Q & A) ja raporttien ja kuvien palvelinpuolen hahmontamisesta. Taustan v-ytimet määritetään tietty määrä muistia, jota käytetään pääasiassa isännän malleja, eli aktiivisia tietojoukkoja.

**Edustan v-ytimet** on vastuussa web verkkopalvelusta, koontinäytön ja raportin tiedostohallinnasta, käyttöoikeuksien hallinnasta, ajoituksista, API-liittymiä, lataa ja lataa ja yleisesti ottaen liittyvät käyttäjän käyttäjäkokemuksia varten.

Tallennustila on asetettu **100 TT: N kapasiteetin solmuun**.

Resursseja ja rajoitukset kunkin Premium-varastointiyksikön (ja mukauttaa näin A-Varastointiyksikkö) on kuvattu seuraavassa taulukossa:

| Kapasiteetin solmut | V-ytimiä yhteensä | Taustan v-ytimet | RAM (GB) | Edustan v-ytimet | Directqueryn/Live-yhteyden (sekunnissa) | Mallin uudelleen latauksen Parallellisointi |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0.5 | 2.5 | 0.5 | 3.75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7.5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| | | | | | | |

### <a name="capacity-workloads"></a>Kapasiteetin kuormituksia

Kapasiteetin kuormituksia ovat käyttäjien palveluita. Oletusarvon mukaan Premium ja Azure-kapasiteetit tukevat vain tietojoukon kuormituksen, liittyvä suoritettaessa Power BI-kyselyjä. Tietojoukon kuormituksen ei voi poistaa käytöstä. Lisää kuormituksia voidaan ottaa käyttöön [AI (kognitiiviset palvelut)](https://powerbi.microsoft.com/blog/easy-access-to-ai-in-power-bi-preview/), [Dataflows](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium), ja [sivutetut raportit](paginated-reports-save-to-power-bi-service.md). Nämä kuormituksia tuetaan vain Premium-tilaukset. 

Lisää jokainen kuormitus sallii muistin enimmäismäärän (yhteensä muistia prosenttilukuna), jonka avulla voidaan kuormituksen mukaan. SKU määritetään enimmäismuisti oletusarvot. Voit suurentaa-kapasiteetin käytettävissä olevat resurssit ottamalla vain ne muita kuormituksia, kun niitä käytetään. Ja voit muuttaa vain, kun olet määrittänyt oletusasetukset asetukset ovat ei täytä kapasiteetin resurssivaatimukset muistia. Kuormituksia käytössä- ja määrittää kapasiteettiin kapasiteetin järjestelmänvalvojille avulla **kapasiteettiasetukset** - [hallintaportaalissa](service-admin-portal.md) tai käyttämällä [kapasiteettien REST-ohjelmointirajapintoja](https://docs.microsoft.com/rest/api/power-bi/capacities).  

![Kuormitusten käyttöönotto](media/service-admin-premium-workloads/admin-portal-workloads.png)

Lisätietoja on artikkelissa [kuormituksia määrittäminen Premium-kapasiteetissa](service-admin-premium-workloads.md). 

### <a name="how-capacities-function"></a>Miten kapasiteettien-funktio

AT aina Power BI-palvelun avulla kapasiteetin resurssien optimaalisesti aikana enintään kapasiteetin rajoissa.

Kapasiteetin toiminnot luokitellaan joko *vuorovaikutteinen* tai *taustan*. Vuorovaikutteinen toimintoihin kuuluvat hahmontaminen pyynnöt ja niihin reagoiminen käyttäjän toimet (suodatusta, Q & A: n kyseltäessä jne.). Tuo mallin kyselyä on yleensä muistin paljon resursseja, suorittimen vaativia ollessa kyseltäessä DirectQuery- ja reaaliaikaisen yhteyden malleja. Taustan toiminnot sisältävät tietovirrassa ja tuo mallin päivitykset ja koontinäytön kyselyn välimuistiin.

On tärkeää ymmärtää, että vuorovaikutteisia toimintoja ovat aina täytynyt priorisoida taustan toiminnot varmistaaksesi, parhaan mahdollisen kokemuksen käyttäjälle kautta. Jos resurssit eivät riitä, tausta toiminnot lisätään jonoon, kun Vapauta resursseja. Taustan toimintoja, kuten tietojoukkosi päivittyy voi olla Keski prosessin Power BI-palvelu ja lisätään jonoon.

Tuontimalleille on oltava täysin ladataan muistiin, jotta he voivat tehdä kyselyitä tai päivittää. Power BI-palvelun hallitsee muistin käytön avulla kehittyneitä algoritmeja varmistamiseksi käytettävissä olevan muistin ja voi aiheuttaa vahvistettaessa perusteettomasti kapasiteetti: Kun se on mahdollista kapasiteetin tallentamiseen monta tuonti mallien (enintään 100 TT: N Premium-kapasiteettia kohti), kun niiden yhdistetyn levytallennustilaa ylittää tuetut muistia (ja lisämuistia tarvitaan kysely-ja päivitys), sitten ne kaikki voi ladata muistiin samalla kertaa.

Tuontimalleille vuoksi on ladattu ja poistaa muistin käytön mukaan. Tuonti-malli on ladattu, kun se on kysellyt (vuorovaikutteinen toiminto) ja vielä muistissa tai kun se on päivitettävä (tausta-toiminto).

Mallin muistista poistamista kutsutaan *häätäminen*. Se on Power BI voidaan suorittaa nopeasti mallit koosta riippuen toiminto. Jos kapasiteetti on ei mitään muisti on vähissä, mallit yksinkertaisesti ladataan muistiin ja pysyvät olemassa. Kuitenkin kun muisti ei riitä lataa mallia, Power BI-palvelun ensin on ilmainen ylös muistiin. Se vapauttaa muistia mukaan tunnistetaan malleilla, jotka on poistuvan pyrkimällä malleja, joita ei ole käytetty viimeisten kolmen minuutin \[ [1](#endnote-1)\], ja häätäen samalla ne. Jos ei malleja ei ole passiivinen häätämään, Power BI-palvelun pyritään mallit ladata taustan toimintoja. Auta 30 sekunnin jälkeen epäonnistuneiden yritysten määrä \[ [1](#endnote-1)\], on vuorovaikutteinen toiminto epäonnistuu. Tässä tapauksessa raportin käyttäjälle ilmoitetaan, ja yritä uudelleen pian ehdotus syyn. Joissakin tapauksissa mallit voi olla muistista, koska service toimintoja.

On tärkeää kuormituksen tietojoukon häätäminen on tavallinen ja odotettua toimintaa. Se pyrkii Suurenna muistinkäyttö lataamista ja purkaminen malleja, joiden yhdistetyn koot voi ylittää käytettävissä olevan muistin mukaan. Tämä on tarkoituksellista, ja täysin läpinäkyvä raportin käyttäjille. Suuren häätäminen hinnat ei välttämättä tarkoita kapasiteetin riittämättömästi niille. Ne kuitenkin tulla huolenaiheesta Jos kysely tai päivitys reagoinnin kärsimystä suuren häätäminen hinnat vuoksi.

Tuontimalleille päivitykset ovat aina vaatii paljon muistia, kuten mallit on ladattava muistiin. Lisämuistia tarvitaan käsittelyä varten. Täydellinen käyttää noin kaksinkertaisesti sen määrän muistia mallin vaatima. Näin voit varmistaa malli voidaan tehdä kyselyitä silloin, kun käsitellään, koska kyselyt lähetetään aiemmin luotua mallia, ennen kuin päivitys on valmis ja uusi Mallitiedot ovat käytettävissä. Lisäävä päivitys edellyttää vähemmän muistia onnistunut nopeammin ja niin huomattavasti pienentää kapasiteettia resursseille vähissä. Päivitykset voidaan myös suorittimen vaativia malleille, varsinkin monimutkaisia Power Query-muunnoksia tai lasketut taulukot tai sarakkeet, jotka ovat monimutkaisia tai suuren taulukoiden perusteella.

Päivitykset, kuten kyselyt edellyttävät mallin ladataan muistiin. Jos muisti ei riitä, Power BI-palvelu yrittää passiivinen mallit, ja jos tämä ei ole mahdollista (kaikki mallit ovat aktiivisia), päivitystyön jonoon. Päivitykset ovat yleensä suorittimen vaativia, jopa enemmän niin kuin kyselyitä. Tästä syystä on kapasiteettirajat samanaikaisten päivitykset, määritä taustan v-ydintä, pyöristettynä määrä 1,5 kertaa määrän. Jos on liian monta samanaikaista päivitykset, ajoitettu päivitys asetetaan jonoon. Kun nämä tilanteissa, kestää kauemmin päivityksen päättymistä. Pyydettäessä päivittää kuten käynnistämä käyttäjän pyynnöstä tai API-kutsu yrittää kolme kertaa \[ [1](#endnote-1)\]. Jos edelleen ei ole tarpeeksi resursseja, sitten päivitys epäonnistuu.

Osion Huomautuksia:   
<a name="endnote-1"></a>\[1\] voi muuttua.

### <a name="regional-support"></a>Alueellinen tuki

Kun luodaan uusi kapasiteetti, Office 365: n Yleiset Järjestelmänvalvojat ja Power BI-palvelun järjestelmänvalvojat voivat määrittää työtiloja lausekkeella kapasiteettiin alue tallennetaan. Tätä kutsutaan **useiden Geo**. Useiden – maantieteellisesti organisaatiot voit täyttää tietojen pisimpään vaatimukset ottamalla sisältöä tietyn alueen palvelinkeskuksiin vaikka se ei ole sama kuin alue, jossa Office 365-tilauksen on. Lisätietoja on artikkelissa [useiden Geo tuki Power BI Premium](service-admin-premium-multi-geo.md).

### <a name="capacity-management"></a>Kapasiteetin hallinta

Premium-Kapasiteettien hallinta liittyy luominen tai poistaminen kapasiteettien järjestelmänvalvojien määrittäminen määritetään työtiloja, määritetään kuormituksia, valvonnan ja muutosten kapasiteetin suorituskyvyn parantamiseksi. 

Office 365: n yleisen järjestelmänvalvojan rooli ja Power BI-palvelussa voit luoda Premium-kapasiteetteja käytettävissä olevat v-ytimet tai muokata olemassa Premium-kapasiteetteja. Kun kapasiteetti on luotu, kapasiteetin kokoa ja maantieteellisellä alueella on määritetty, ja vähintään yksi kapasiteetin järjestelmänvalvojan on määritetty. 

Useimmat hallintatehtävät valmistuneet luotaessa kapasiteetit [hallintaportaalissa](service-admin-portal.md).

![Hallintaportaali](media/service-premium-what-is/premium-admin-portal.png)

Kapasiteetin järjestelmänvalvojat voivat määrittää työtiloja kapasiteettiin käyttäjien käyttöoikeuksien hallinta ja määrittää muita järjestelmänvalvojia. Kapasiteetin järjestelmänvalvojat myös määrittää kuormituksia, säätäminen muistin estetään ja tarvittaessa uudelleen kapasiteettia, palautetaan toiminnot, jos kyseessä on kapasiteetin ylikuormitusta.

![Hallintaportaali](media/service-premium-what-is/premium-admin-portal-mgmt.png)

Kapasiteetin järjestelmänvalvojat voit myös varmistaa, että kapasiteetti on sujuvasti käynnissä. Ne valvoa kapasiteetin kunnon oikealle hallintaportaalissa tai Premium-kapasiteetin mittareita-sovelluksen avulla.

Saat lisätietoja kapasiteettien luomiseen, järjestelmänvalvojien määrittäminen, ja työtilojen määrittämisen [hallinta Premium-kapasiteetteja](service-premium-capacity-manage.md). Saat lisätietoja rooleista [Power BI liittyvät järjestelmänvalvojaroolit](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi).

### <a name="monitoring"></a>Valvonta

Premium-kapasiteetteja valvonta tarjoaa Järjestelmänvalvojat, joilla on käsitys siitä, miten kapasiteettien toimivat. Kapasiteettien voidaan valvoa käyttämällä hallintaportaalissa ja [Power BI Premium-kapasiteetin Mittaustietoihin sovelluksen](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics).

Nopean näyttämisen valvonta portaalissa antaa korkean tason mittareita, joka ilmaisee, lataa sijoitetaan ja resursseja, todentamistarkoituksiin kapasiteettisi keskiarvoa viimeisten seitsemän päivän aikana. 

![Hallintaportaali](media/service-premium-what-is/premium-admin-portal-health.png)

**Power BI Premium-kapasiteetin Mittaustietoihin** sovellus tarjoaa tietoja miten-kapasiteetit toimivat parhaiten tarkempia tietoja. Sovellus tarjoaa korkean tason koontinäytön ja tarkempia raportteja.

![Mittausarvosovelluksen koontinäyttö](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Sovelluksen koontinäytöstä napsauttamalla metrijärjestelmän solun tarkemmin raportin avaamiseksi. Raporteissa tarkemmin mittarit ja poraaminen tärkeimmät tiedot voit suodatusta mahdollisuus on säilytettävä-kapasiteetit sujuvasti käynnissä.

![Kyselyn kausittaisten päät odotusaika määrät ilmaista mahdollisen suorittimen kylläisyys](media/service-premium-capacity-scenarios/peak-query-wait-times.png)

Lue lisätietoja kapasiteettien valvonta on artikkelissa [valvonnan Power BI-hallintaportaalissa](service-admin-premium-monitor-portal.md) ja [valvonnan Power BI Premium-kapasiteetin Mittaustietoihin sovelluksessa](service-admin-premium-monitor-capacity.md).

### <a name="optimizing-capacities"></a>Kapasiteettien optimointi

Optimaalisesti kapasiteettiisi on kriittinen aihealueen käyttäjät get suorituskykyä ja saat tehokkaasti Premium-sijoituksen. Avainmittarit valvomalla järjestelmänvalvojat voivat määrittää, miten parhaiten vianmääritys pullonkaulojen ja tehdä tarvittavat toimet. Lisätietoja on artikkelissa [optimointi Premium-kapasiteetteja](service-premium-capacity-optimize.md) ja [Premium-kapasiteetin skenaarioita](service-premium-capacity-scenarios.md).

### <a name="capacities-rest-apis"></a>Kapasiteettien REST-Ohjelmointirajapinnat

Power BI REST-Ohjelmointirajapinnat ovat kokoelma [kapasiteettien ohjelmointirajapintoja](https://docs.microsoft.com/rest/api/power-bi/capacities). API järjestelmänvalvojat voivat hallita ohjelmallisesti monia Premium-kapasiteetteja, mukaan lukien ottamisesta käyttöön ja poistamisesta kuormituksia, työtilojen määrittäminen kapasiteettiin ja paljon muuta.

## <a name="large-datasets"></a>Suurten tietojoukkojen

Sen mukaan SKU, Power BI Premium tukee palvelimeen Power BI Desktop (.pbix)-mallitiedostot enintään **10 gt** koossa. Kun ladattu, malli voi julkaista työtilaan, joka on määritetty Premium-kapasiteettiin. Tietojoukko voidaan päivittää sitten ajan **12 Gigatavun** koossa.

### <a name="size-considerations"></a>Koon huomioon otettavia seikkoja

Suuret mallit voivat vaatia. Sinulla pitäisi olla vähintään P1 SKU: ta yli 1 Gigatavun malleille. Vaikka isojen mallien julkaiseminen työtilat tukee enintään A3 A-Varastointiyksikköjä voitu työ, ne päivitetään ei.

Seuraavassa taulukossa kuvataan suositellut varastointiyksiköt eri .pbix-koille:

   |SKU  |.pbix:n koko   |
   |---------|---------|
   |P1    | < 3 Gt        |
   |P2    | < 6 Gt        |
   |P3, P4, P5    | enintään 10 Gt   |

Power BI Embedded A4 -varastointiyksikkö vastaa P1-varastointiyksikköä, A5 = P2 ja A6 = P3. Huomaa, että suurten mallien julkaiseminen A- ja EM-varastointiyksiköihin voi palauttaa virheitä, jotka eivät liity erityisesti mallin kokorajoituksen virheeseen jaetussa kapasiteetissa. Suurten mallien päivitysvirheet A- ja EM-varastointiyksiköissä osoittavat todennäköisesti aikakatkaisuihin. 

.Pbix-tiedostot kuvaavat tietoja *pakattuja tila*. Tietoja laajennetaan todennäköisesti useita kertoja, kun ne ladataan muistiin, ja uudelleen useita kertoja tietojen päivittämisen aikana.

Suurten tietojoukkojen ajoitettu päivitys voi kestää kauan ja vaatia. On tärkeää Ajoita useita päivityksiä päällekkäin. On suositeltavaa [lisäävän päivityksen](service-premium-incremental-refresh.md) on määritetty, koska se on nopeampia ja luotettavampia ja kuluttaa vähemmän resursseja.

Suurten tietojoukkojen alkuperäisen raportin lataaminen voi kestää kauan, jos tietojoukon käytettiin kulunut aikaa aikaa on kulunut. Pitkään latautuvissa raporteissa latauksen edistyminen näkyy latauspalkissa.

Vaikka kyselykohtaiset muisti- ja aika-rajoitukset ovat paljon suuremmat Premium-kapasiteetissa, on suositeltavaa rajoittaa visualisoinnit näyttämään vain tarpeellinen suodattimia ja osittajia avulla.

## <a name="incremental-refresh"></a>Lisäävä päivitys

Lisäävä päivitys tarjoaa ottaa ja ylläpito suuria tietojoukkoja Power BI Premium olennainen osa. Lisäävä päivitys on monia etuja, esimerkiksi päivitykset ovat entistä nopeampia, koska vain tiedot, jotka on muutettu täytyy päivittää. Päivitykset ovat entistä luotettavampia, koska se on tarpeeton säilyttää pitkäkestoisia yhteyksiä muuttuvia tietolähteisiin. Resurssien kulutus on vähäisempää, koska päivitettäviä muistin ja muiden resurssien yleinen kulutus on vähemmän tietoja. Lisäävän päivityksen käytännöt määritellään **Power BI Desktop**, ja ottaa käyttöön, kun julkaistaan työtilan Premium-kapasiteettiin. 

![Päivitystiedot](media/service-premium-incremental-refresh/refresh-details.png)

Lisätietoja on artikkelissa [lisäävä päivitys on Power BI Premium](service-premium-incremental-refresh.md).

## <a name="paginated-reports"></a>Sivutetut raportit

Sivutettujen raporttien tuettu P1 – P3 ja A4_A6 Varastointiyksiköt perustuvat SQL Server Reporting Services-teknologian kielen RDL (Report Definition). Kun perusteella RDL tekniikkaa, se ei ole sama kuin Power BI Report Server, joka on ladattava reporting ympäristö, voit asentaa paikallisen, sisältyy myös Power BI Premium. Sivutetut raportit muotoillaan sopimaan hyvin sivun, joka tulostaa tai jaettu. Tiedot näytetään taulukossa, vaikka taulukon käsittää useita sivuja. Käyttämällä maksutonta [ **Power BI-raportin muodostimen** ](https://go.microsoft.com/fwlink/?linkid=2086513) työpöydän sovelluksen käyttäjien tekijä sivutetut raportit ja julkaise ne palveluun.

Power BI Premium-Paginated raportit ovat kuormituksen, joka on oltava käytössä kapasiteettia hallintaportaalissa käyttämällä. Kapasiteetin järjestelmänvalvojat voivat ottaa käyttöön ja määritä sitten kapasiteetin yleistä muistiresursseja prosenttilukuna muistin määrä. Toisin kuin kuormituksia Premium suoritetaan sivutetut raportit contained tilaa kapasiteetin sisällä. Tähän määritetty enimmäismuisti käytetään, onko kuormitus on aktiivinen. Oletusarvo on 20 prosenttia. 

Lisätietoja on artikkelissa [sivutetut raportit Power BI Premium](paginated-reports-report-builder-power-bi.md). Saat lisätietoja käyttöön Paginated raporttien kuormituksen [Määritä kuormituksia](service-admin-premium-workloads.md).

## <a name="power-bi-report-server"></a>Power BI -raporttipalvelin
 
Sisältyy Power BI Premium on Power BI-raporttipalvelin *paikallisen* raporttipalvelin, jonka verkkoportaalissa. Voit luoda-BI ympäristön paikallisen ja jaella raportteja organisaation palomuurin takana. Raporttipalvelimen avulla käyttäjät voivat käyttää monipuolista, vuorovaikutteinen, ja SQL Server Reporting Services-raportoinnin yritystoiminnot. Käyttäjät voivat tarkastella visualisoinnin tietoja ja löytää nopeasti mallien avulla päätösten paremmin, nopeammin. Raporttipalvelin tarjoaa hallinnon oman ehdot. Jos aika koittaa, Power BI-raporttipalvelimen avulla on helppo siirtymään pilveen, jossa organisaatiosi voi hyödyntää kaikkia Power BI Premium-toimintoja.

Lisätietoja on artikkelissa [Power BI-raporttipalvelimen](report-server/get-started.md).

## <a name="unlimited-content-sharing"></a>Rajoittamaton sisällön jakaminen

Premium kuka tahansa, olivatpa ne sitten sisällä tai ulkopuolella organisaatiosi tarkastella Power BI-sisältösi mukaan lukien sivutettuja ja vuorovaikutteisten raporttien ostamisesta yksittäisiä käyttöoikeuksia. 

![Sisällön jakaminen](media/service-premium-what-is/premium-sharing.png)

Premium mahdollistaa Pro-version käyttäjien luoman sisällön laaja-alaisen ilman, että Pro-käyttöoikeuksia vastaanottajille, jotka tarkastella sisältöä. Pro-käyttöoikeudet vaaditaan sisällöntekijöille. Luojat muodostaa yhteyden tietolähteisiin, mallitiedot, ja luoda raportteja ja koontinäyttöjä, jotka on paketoitu työtilan sovelluksina. 

Lisätietoja on artikkelissa [Power BI-käyttöoikeuksien](service-admin-licensing-organization.md).

## <a name="tool-connectivity-preview"></a>Työkalu yhteydet (esikatselu)

Käyttölupaa todetuilla Microsoft enterprise **Analysis Services Vertipaq-moduulia** jolle Power BI-tietojoukkoja. Analysis Services tarjoaa ohjelmoitavuusominaisuuden ja asiakassovelluksen ja työkalu tukee asiakaskirjastot ja ohjelmointirajapintoja, jotka tukevat Avaa standard XMLA-protokollaa. Power BI Premium-tietojoukkoja tuetaan tällä hetkellä *vain luku-* toiminnot Microsoftin ja kolmansien osapuolten sovelluksissa ja työkalujen kautta **XMLA-päätepisteiden**. 

Microsoft-työkaluja, kuten SQL Server Management Studio ja SQL Server Profiler ja kolmannen osapuolen sovelluksiin, kuten DAX Studio ja visualisoinnin sovelluksia, voit muodostamiseen ja Premium-tietojoukkoja käyttämällä XMLA, DAX, MDX, DMVs ja jäljitys tapahtumia. 

![SSMS: SSÄ](media/service-premium-what-is/connect-tools-ssms-dax.png)

Lisätietoja on artikkelissa [tietojoukkoja, joilla asiakassovellusten ja työkaluja, joilla yhdistäminen](service-premium-connect-tools.md).

## <a name="acknowledgements"></a>Kuittaussanomien

Peter Myers, tietojen Platform MVP ja riippumattoman BI asiantuntijan kanssa [Bitwise ratkaisuja](https://www.bitwisesolutions.com.au/), ja Microsoft Power BI asiakkaan neuvoa ryhmän (CAT) ovat merkittäviä osallistujia tähän artikkeliin.

## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
> [Premium-Kapasiteettien hallinta](service-premium-capacity-manage.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

||||||
