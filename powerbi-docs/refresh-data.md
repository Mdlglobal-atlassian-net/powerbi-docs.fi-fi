---
title: Tietojen päivittäminen Power BI:ssä
description: Tässä artikkelissa kuvataan Power BI:n tietojen päivitysominaisuuksia ja niiden riippuvuuksia käsitteellisellä tasolla.
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/14/2019
ms.author: mblythe
LocalizationGroup: Data refresh
ms.openlocfilehash: 948776a12af2d99da2d84d07c9298f9ec0558c7b
ms.sourcegitcommit: 2b7beec5237a597bab2da8eb6ffe69122a5d2ed9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442939"
---
# <a name="data-refresh-in-power-bi"></a>Tietojen päivittäminen Power BI:ssä

Power BI mahdollistaa nopeat siirtymät tietojen analysoimisesta toimiin, mutta samalla sinun on varmistettava, että Power BI -raporttien ja raporttinäkymien tiedot ovat tuoreita. Tietojen päivittämisen tunteminen on tarkkojen tulosten kannalta ensiarvoisen tärkeää.

Tässä artikkelissa kuvataan Power BI:n tietojen päivitysominaisuuksia ja niiden riippuvuuksia käsitteellisellä tasolla. Artikkelissa kuvataan myös parhaita käytäntöjä ja annetaan vinkkejä yleisten päivitysongelmien välttämiseksi. Sisältö auttaa sinua ymmärtämään tietojen päivityksen toiminnan perusteita. Kohdennetut, vaiheittaiset tietojen päivitysohjeet ovat artikkelin lopussa Seuraavat vaiheet -kohdassa luetteloiduissa opetusohjelmissa ja oppaissa.

## <a name="understanding-data-refresh"></a>Tietojen päivityksen ymmärtäminen

Kun päivität tiedot, Power BI:n on suoritettava kysely pohjana oleville tietolähteille ja mahdollisesti ladattava lähteenä olevat tiedot tietojoukkoon, minkä jälkeen Power BI:n on päivitettävä kaikki päivitetystä tietojoukosta riippuvien raporttien ja raporttinäkymien visualisoinnit. Prosessissa on useita vaiheita tietojoukkojesi tallentamisen tilasta riippuen. Tätä käsitellään seuraavissa osioissa.

Jotta voisit ymmärtää, miten Power BI päivittää tietojoukkoja, raportteja ja raporttinäkymiä, sinun on tiedostettava seuraavat käsitteet:

- **Tallennustilat ja tietojoukkojen tyypit**: Power BI:n tukemien tallennustilojen ja tietojoukkojen tyyppien päivitysvaatimukset vaihtelevat. Voit valita joko tietojen tuomisen takaisin Power BI:hin, jolloin näet kaikki muutokset, tai kyselyn suorittamisen suoraan lähteessä.
- **Power BI:n päivitystyypit**: Tietojoukon yksityiskohdista riippumatta eri päivitystyyppien tuntemus auttaa ymmärtämään, mitä Power BI tekee päivitystoiminnon aikana. Näiden tietojen yhdistäminen tallennustilan yksityiskohtiin auttaa ymmärtämään, mitä Power BI tarkalleen ottaen tekee, kun valitset tietojoukolle **Päivitä nyt**.

### <a name="storage-modes-and-dataset-types"></a>Tallennustilat ja tietojoukkojen tyypit

Power BI -tietojoukko voi toimia jossakin seuraavista tiloista käyttäessään useiden eri tietolähteiden tietoja. Lisätietoja on kohdassa [Tallennustila Power BI Desktopissa](desktop-storage-mode.md).

- Tuontitila
- DirectQuery-tila
- LiveConnect-tila
- Push-tila

Seuraavassa kaaviossa esitetään eri tietovuot tallennustilan perusteella. Tärkein huomio on, että vain tuontitilassa olevat tietojoukot edellyttävät tietolähteen päivittämistä. Ne edellyttävät päivitystä, koska vain tämäntyyppiset tietojoukot tuovat tietoja tietolähteistään ja koska tuodut tiedot saatetaan päivittää säännöllisesti tai ajoittain. DirectQuery-tietojoukot ja LiveConnect-tilassa olevat Analysis Services -tietojoukot eivät tuo tietoja, vaan ne lähettävät kyselyn taustalla olevalle tietolähteelle käyttäjän jokaisen toimen yhteydessä. Push-tilassa olevilla tietojoukoilla ei ole tietolähteiden suoria käyttöoikeuksia, vaan ne odottavat, että työnnät tiedot Power BI:hin. Tietojoukon päivittämisen vaatimukset vaihtelevat tallennustilan/tietojoukon tyypin mukaan.

![Tallennustilat ja tietojoukkojen tyypit](media/refresh-data/storage-modes-dataset-types-diagram.png)

#### <a name="datasets-in-import-mode"></a>Tietojoukot tuontitilassa

Power BI tuo tietoja alkuperäisistä tietolähteistä tietojoukkoon. Tietojoukolle lähetetyt Power BI:n raportti- ja raporttinäkymäkyselyt palauttavat tuloksia tuoduista taulukoista ja sarakkeista. Voit ajatella tällaisen tietojoukon olevan kopio tietystä hetkestä. Koska Power BI kopioi tiedot, tietojen noutaminen pohjana olevista tietolähteistä edellyttää tietojoukkojen päivittämistä.

Koska Power BI tallentaa tiedot välimuistiin, tietojoukkojen koko voi olla tuontitilassa merkittävän suuri. Katso seuraavasta taulukosta tietojoukkojen enimmäiskoko kapasiteettia kohti. Tietojoukot vaativat joskus päivitystoiminnon aikana enemmän resursseja kuin on saatavana. Voit välttää päivitysongelmat pitämällä tietojoukot reilusti enimmäiskokoa pienempinä.

| Kapasiteetin tyyppi | Suurin tietojoukon koko |
| --- | --- |
| Jaettu, A1 A2 tai A3 | 1 GT |
| A4 tai P1 | 3 Gt |
| A5 tai P2 | 6 Gt |
| A6 tai P3 | 10 Gt |
| | |

#### <a name="datasets-in-directqueryliveconnect-mode"></a>Tietojoukot DirectQuery-/LiveConnect-tilassa

Power BI tuo tietoja DirectQuery-/LiveConnect-tilassa olevien yhteyksien kautta. Sen sijaan tietojoukko palauttaa pohjana olevan tietolähteen tulokset, kun raportti tai raporttinäkymä lähettää tietojoukolle kyselyn. Power BI muuntaa kyselyt ja välittää ne tietolähteelle.

Vaikka DirectQuery- ja LiveConnect-tilat muistuttavat toisiaan siltä osin, että Power BI välittää kyselyt lähteelle, on tärkeää huomata, että Power BI:n ei tarvitse muuntaa kyselyitä LiveConnect-tilassa. Kyselyt lähetetään suoraan tietokannan Analysis Services -isäntäesiintymälle jaetun kapasiteetin tai Premium-kapasiteetin resursseja käyttämättä.

Koska Power BI ei tuo tietoja, sinun ei tarvitse päivittää tietoja. Power BI päivittää edelleen ruudut ja mahdollisesti muita raportin osia. Tästä kerrotaan tarkemmin seuraavassa osiossa. Ruutu on raporttinäkymään kiinnitetty raportin visualisointi. Raporttinäkymän ruudut päivitetään noin tunnin välein siten, että ruuduissa näytetään viimeaikaiset tulokset. Voit muuttaa aikataulua tietojoukon asetuksista alla olevan näyttökuvan mukaisesti. Voit myös pakottaa raporttinäkymän päivityksen manuaalisesti **Päivitä nyt** -vaihtoehdolla.

![Päivitysaikataulu](media/refresh-data/refresh-schedule.png)

> [!NOTE]
> **Tietojoukot**-välilehden **Ajoitettu välimuistin päivitys** -osio ei koske tietojoukkoja tuontitilassa. Nämä tietojoukot eivät edellytä erillistä ruudun päivitystä, koska Power BI päivittää ruudut automaattisesti jokaisen ajoitetun tai pyynnöstä toteutetun tietojen päivittämisen aikana.

#### <a name="push-datasets"></a>Push-tietojoukot

Push-tietojoukot eivät sisällä tietolähteen muodollista määritelmää, joten ne eivät edellytä tietojen päivittämistä Power BI:ssä. Voit päivittää ne työntämällä tietoja tietojoukkoon Azure Stream Analyticsin tai muun ulkoisen palvelun tai prosessin kautta. Tämä on yleinen tapa suorittaa reaaliaikainen analyysi Power BI:llä. Power BI suorittaa edelleen push-tietojoukon päällä käytettyjen ruutujen välimuistin päivitykset. Katso yksityiskohtaiset ohjeet [opetusohjelmasta: Stream Analytics ja Power BI: Reaaliaikainen analyysiraporttinäkymä tietovirroille](/azure/stream-analytics/stream-analytics-power-bi-dashboard).

> [!NOTE]
> Push-tilan toimintaan liittyy useita rajoituksia, jotka on kerrottu kohdassa [Power BI:n REST-ohjelmointirajapinnan rajoitukset](developer/api-rest-api-limitations.md).

### <a name="power-bi-refresh-types"></a>Power BI:n päivitystyypit

Power BI:n päivitystoiminto voi koostua useista päivitystyypeistä, mukaan lukien tietojen päivittämisestä, OneDrive-päivittämisestä, kyselyn välimuistien päivittämisestä, ruutujen päivittämisestä ja raportin visualisointien päivittämisestä. Power BI määrittää tietojoukon asianmukaiset päivitysvaiheet automaattisesti, mutta sinun on hyvä tietää, miten ne vaikuttavat päivitystoiminnon kestoon ja monimutkaisuuteen. Pikaopas on seuraavassa taulukossa.

| Tallennustilan tila | Tietojen uudelleenlataus | OneDrive-päivittäminen | Kysely välimuisteista | Ruudun päivitys | Raportin visualisoinnit |
| --- | --- | --- | --- | --- | --- |
| Tuo | Ajoitettu ja pyydettäessä | Kyllä, yhdistetyille tietojoukoille | Jos käytössä Premium-kapasiteetissa | Automaattisesti ja pyydettäessä | Ei |
| DirectQuery | Ei käytettävissä | Kyllä, yhdistetyille tietojoukoille | Jos käytössä Premium-kapasiteetissa | Automaattisesti ja pyydettäessä | Ei |
| LiveConnect | Ei käytettävissä | Kyllä, yhdistetyille tietojoukoille | Jos käytössä Premium-kapasiteetissa | Automaattisesti ja pyydettäessä | Kyllä |
| Push | Ei käytettävissä | Ei käytettävissä | Ei käytännöllinen | Automaattisesti ja pyydettäessä | Ei |
| | | | | | |

#### <a name="data-refresh"></a>Tietojen uudelleenlataus

Power BI -käyttäjille tietojen päivittäminen tarkoittaa yleensä tietojen tuomista alkuperäisistä tietolähteistä tietojoukkoon joko ajoitetun päivityksen perusteella tai pyydettäessä. Voit suorittaa useita tietojoukkojen päivityksiä päivittäin. Tämä saattaa olla tarpeen, jos pohjana olevat tiedot muuttuvat usein. Power BI:ssä jaettujen kapasiteettien tietojoukot voidaan päivittää päivän aikana enintään kahdeksan kertaa. Jos tietojoukko on Premium-kapasiteetissa, voit ajoittaa päivityksen enintään 48 kertaa päivässä tietojoukon asetuksissa. Katso lisätietoja Ajoitettu päivitys -kohdasta alempana tässä artikkelissa.

Huomaa, että päivittäisten päivitysten jaetun kapasiteetin rajoitus koskee ajoitettujen ja ohjelmointirajapintapäivitysten määrää yhteensä. Voit myös käynnistää pyydetyn päivityksen valitsemalla **Päivitä nyt** tietojoukon valikosta seuraavassa näyttökuvassa esitetyllä tavalla. Pyydetyt päivitykset eivät sisälly päivitysrajoitukseen. Huomaathan myös, että Premium-kapasiteetissa olevat tietojoukot eivät aseta rajoituksia ohjelmointirajapintapäivityksille. Jos olet kiinnostunut oman päivitysratkaisusi kehittämisestä Power BI REST API:n avulla, katso kohta [Tietojoukot – Tietojoukkojen päivittäminen](/rest/api/power-bi/datasets/refreshdataset).

![Päivitä nyt](media/refresh-data/refresh-now.png)

> [!NOTE]
> Tietojen päivityksen on oltava valmis kahden tunnin kuluessa jaetussa kapasiteetissa. Jos tietojoukkosi vaatii tätä pidempää päivitystoimintoa, harkitse tietojoukon siirtämistä Premium-kapasiteettiin. Premiumissa päivityksen enimmäiskesto on viisi tuntia.

#### <a name="onedrive-refresh"></a>OneDrive-päivittäminen

Jos loit tietojoukot ja raportit Power BI Desktop -tiedoston, Excel-työkirjan tai pilkuin eroteltuja arvoja sisältävän tiedoston (.csv) pohjalta OneDriveen tai SharePoint Onlineen, Power BI suorittaa toisentyyppisen päivityksen, jota kutsutaan OneDrive-päivittämiseksi. Katso lisätietoja kohdasta [Tietojen noutaminen tiedostoista Power BI:hin](service-get-data-from-files.md).

Toisin kuin tietojoukon päivityksessä, jolloin Power BI tuo tietoja tietolähteestä tietojoukkoon, OneDrive-päivittäminen synkronoi tietojoukot ja raportit niiden lähdetiedostojen kanssa. Oletusarvoisesti Power BI tarkistaa noin tunnin välein, edellyttääkö OneDrive- tai SharePoint-tiedostoon yhdistetty tietojoukko synkronointia. Voit tarkistaa aiemmat synkronointijaksot päivityshistorian OneDrive-välilehdeltä. Seuraavassa näyttökuvassa esitetään mallitietojoukon valmis synkronointijakso.

![Päivityshistoria](media/refresh-data/refresh-history.png)

Kuten yllä olevasta näyttökuvasta näkyy, Power BI tunnisti tämän OneDrive-päivityksen **ajoitetuksi** päivitykseksi, mutta päivitysvälin määrittäminen ei ole mahdollista. Voit ainoastaan poistaa OneDrive-päivityksen käytöstä tietojoukon asetuksista. Päivityksen käytöstä poistamisesta on hyötyä, jos et halua, että Power BI:n tietojoukot ja raportit noutavat muutoksia lähdetiedostoista automaattisesti.

Huomaa, että tietojoukon asetussivulla **OneDrive-tunnistetiedot** ja **OneDrive-päivitys**-osiot näkyvät vain, jos tietojoukko on yhdistetty tiedostoon, joka on OneDrivessa tai SharePoint Onlinessa, kuten näyttökuvassa alla. Tietojoukoissa, jotka eivät ole yhteydessä OneDrive- tai SharePoint Online -lähdetiedostoihin, ei näy näitä osioita.

![OneDrive-tunnistetiedot ja OneDrive-päivitys](media/refresh-data/onedrive-credentials-refresh.png)

Jos poistat tietojoukon OneDrive-päivityksen käytöstä, voit synkronoida tietojoukon pyydettäessä valitsemalla **Päivitä nyt** tietojoukkovalikosta. Pyydetyn päivityksen aikana Power BI tarkistaa, onko OneDrive- tai SharePoint Online -lähdetiedostosta saatavilla tietojoukkoa uudempi versio. Jos näin on, Power BI synkronoi tietojoukon. **Päivityshistoriassa** nämä toimet näkyvät pyydettyinä päivityksinä **OneDrive**-välilehdellä.

Huomaa, että OneDrive-päivitys ei nouda tietoja alkuperäisistä tietolähteistä. OneDrive-päivitys päivittää vain Power BI -resurssit .pbix-, .xlsx- ja .csv-tiedostojen metatiedoilla ja tiedoilla, kuten seuraavassa kaaviossa esitetään. Power BI käynnistää tietojen päivityksen osana pyydettyä päivitystä varmistaakseen, että tietojoukossa on tietolähteiden uusimmat tiedot. Voit tarkistaa tämän **Päivityshistorian** **Ajoitettu**-välilehdeltä.

![OneDrive-päivittämisen kaavio](media/refresh-data/onedrive-refresh-diagram.png)

Jos haluat suorittaa ajoitetun päivityksen ja OneDrive-päivittäminen on käytössä OneDriveen tai SharePoint Onlineen yhdistettyjen tietojoukkojen osalta, varmista, että määrität ajoituksen siten, että Power BI suorittaa tietojen päivittämisen OneDrive-päivittämisen jälkeen. Jos olet esimerkiksi luonut oman palvelun tai prosessin, joka päivittää OneDrivessa tai SharePoint Onlinessa olevan tietolähteen tiedoston joka yö kello 1, saatat haluta määrittää ajoitetun päivityksen kello 2.30, jotta Power BI:llä on riittävästi aikaa suorittaa OneDriven päivitysprosessi loppuun ennen tietojen päivittämistä.

#### <a name="refresh-of-query-caches"></a>Kyselyn välimuistien päivittäminen

Jos tietojoukkosi on Premium-kapasiteetissa, saatat ehkä voida parantaa kaikkien siihen liittyvien raporttien ja raporttinäkymien suorituskykyä ottamalla käyttöön kyselyn tallentamisen välimuistiin. Kyselyn tallentaminen välimuistiin ohjaa Premium-kapasiteetin käyttämään sen paikallista välimuistipalvelua kyselyn tulosten säilyttämiseen, jolloin pohjana oleva tietolähde ei käsittele tuloksia. Lisätietoja on kohdassa [Kyselyn tallentaminen välimuistiin Power BI Premiumissa](power-bi-query-caching.md).

![Kyselyn tallentaminen välimuistiin](media/refresh-data/query-caching.png)

Tietojen päivittämisen jälkeen aiemmat välimuistiin tallennetut kyselytulokset eivät enää ole kelvollisia. Power BI hylkää nämä välimuistiin tallennetut tulokset ja sinun on muodostettava ne uudelleen. Tästä syystä kyselyn tallentaminen välimuistiin ei ehkä ole yhtä hyödyllistä hyvin usein (esim. 48 kertaa päivässä) päivittämiesi raporttien ja raporttinäkymien tapauksessa.

#### <a name="tile-refresh"></a>Ruudun päivitys

Power BI ylläpitää jokaiselle ruudun visualisoinnille välimuistia raporttinäkymässäsi ja päivittää ruudun välimuistit ennakoivasti tietojen muuttuessa. Toisin sanoen ruutu päivitetään automaattisesti tietojen päivittämisen jälkeen. Tämä pätee sekä ajoitettuihin päivityksiin että pyydettyihin päivityksiin. Voit myös pakottaa ruudun päivityksen valitsemalla **Lisää vaihtoehtoja** (...) raporttinäkymän oikeasta yläkulmasta ja valitsemalla **Päivitä raporttinäkymän ruudut**.

![Päivitä koontinäytön ruudut](media/refresh-data/refresh-dashboard-tiles.png)

Koska päivitys tapahtuu automaattisesti, voit pitää ruudun päivitystä tietojen päivitykseen kuuluvana asiana. Saatat muun muassa huomata, että päivityksen kesto kasvaa ruutujen määrän kasvaessa. Ruutujen päivitys voi kestää.

Power BI ylläpitää oletusarvoisesti välimuistia jokaiselle ruudulle, mutta jos käytät dynaamista tietoturvaa, joka rajoittaa tietojen käyttöä roolien mukaan artikkelin [rivitason suojaus (RLS) Power BI:ssä](service-admin-rls.md) kuvaillulla tavalla, Power BI:n on ylläpidettävä jokaista roolia ja jokaista ruutua koskevaa välimuistia. Ruutuvälimuistien määrä kerrotaan roolien määrällä.

Tilanne mutkistuu entisestään, jos tietojoukossa käytetään reaaliaikaista yhteyttä rivintason suojauksella suojattuun Analysis Services -tietomalliin. Katso lisätiedot opetusohjelmasta [Dynaaminen rivitason suojaus Analysis Services -taulukkomallissa](desktop-tutorial-row-level-security-onprem-ssas-tabular.md). Tässä tilanteessa Power BI ylläpitää ja päivittää välimuistia jokaiselle ruudulle ja jokaiselle käyttäjälle, joka on koskaan katsellut kyseistä raporttinäkymää. On yleistä, että tällaisten tietojen ruutujen päivittäminen kestää kauemmin kuin tietojen noutaminen lähteestä. Lisätietoja ruutujen päivittämisestä on kohdassa [Ruutuvirheiden vianmääritys](refresh-troubleshooting-tile-errors.md).

#### <a name="refresh-of-report-visuals"></a>Raportin visualisointien päivittäminen

Tämä päivitysprosessi on vähemmän tärkeä, koska sitä käytetään vain Analysis Servicesin reaaliaikaisiin yhteyksiin. Näiden yhteyksien tapauksessa Power BI tallentaa raportin visualisointien viimeisimmän tilan välimuistiin niin, että kun tarkastelet raporttia uudelleen, Power BI:n ei tarvitse lähettää kyselyä Analysis Services -taulukkomallille. Kun käsittelet raporttia esimerkiksi muuttamalla raportin suodatinta, Power BI lähettää taulukkomallille kyselyn ja päivittää raportin visualisoinnit automaattisesti. Jos epäilet, että raportissa näytetään vanhentuneita tietoja, voit myös painaa raportin Päivitä-painiketta, jolloin raportin kaikki visualisoinnit päivitetään seuraavassa näyttökuvassa kuvatulla tavalla.

![Raportin visualisointien päivittäminen](media/refresh-data/refresh-report-visuals.png)

## <a name="review-data-infrastructure-dependencies"></a>Tietoinfrastruktuurin riippuvuuksien tarkistaminen

Tallennustilasta riippumatta tietojen päivittäminen ei voi onnistua, jos pohjana olevat tietolähteet eivät ole käytettävissä. Tietojen käyttötilanteita on kolmea päätyyppiä:

- Tietojoukko käyttää paikallisia tietolähteitä
- Tietojoukko käyttää tietolähteitä pilvipalvelussa
- Tietojoukko käyttää sekä paikallisia että pilvipalvelutietolähteitä

### <a name="connecting-to-on-premises-data-sources"></a>Yhdistäminen paikallisiin tietolähteisiin

Jos tietojoukossa käytetään tietolähdettä, johon Power BI:llä ei ole pääsyä suoran verkkoyhteyden kautta, sinun on määritettävä tietojoukon yhdyskäytäväyhteys, ennen kuin voit ottaa ajoitetun päivityksen käyttöön tai suorittaa tietojen päivityspyynnön. Katso lisätietoja tietoyhdyskäytävistä ja niiden toiminnasta kohdasta [Mitä ovat paikalliset tietoyhdyskäytävät?](service-gateway-onprem.md)

Käytettävissä on seuraavat vaihtoehdot:

- Valitse yrityksen tietoyhdyskäytävä vaaditulla tietolähteen määrityksellä
- Ota käyttöön henkilökohtainen tietoyhdyskäytävä

> [!NOTE]
> Voit hakea tietolähteen tyyppejä, jotka edellyttävät tietoyhdyskäytävää, artikkelista [Tietolähteen hallinta – tuonti/ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md).

#### <a name="using-an-enterprise-data-gateway"></a>Yrityksen tietoyhdyskäytävän käyttäminen

Microsoft suosittelee muodostamaan yhteyden paikalliseen tietolähteeseen yrityksen yhdyskäytävän avulla henkilökohtaisen yhdyskäytävän sijasta. Varmista, että yhdyskäytävä on määritetty oikein, mikä tarkoittaa sitä, että yhdyskäytävässä on oltava uusimmat päivitykset ja kaikki tarvittavat tietolähteen määritykset. Tietolähteen määritys tarjoaa Power BI:lle tietyn lähteen yhteyden tiedot, kuten yhteyden päätepisteen, todennustilan ja tunnistetietojen tiedot. Lisätietoja tietolähteiden hallinnasta yhdyskäytävässä on kohdassa [Tietolähteen hallinta – tuonti/ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md).

Tietojoukon yhdistäminen yrityksen yhdyskäytävään on yhdyskäytävän järjestelmänvalvojalle melko yksinkertaista. Järjestelmänvalvojan oikeuksilla voit päivittää yhdyskäytävän ja lisätä puuttuvat tietolähteet tarvittaessa nopeasti. Voit jopa lisätä puuttuvan tietolähteen yhdyskäytävään suoraan tietojoukon asetussivulta. Laajenna tietolähdenäkymä painamalla painiketta ja valitse sitten **Lisää yhdyskäytävään** -linkki seuraavassa näyttökuvassa esitetyllä tavalla. Jos sen sijaan et ole yhdyskäytävän järjestelmänvalvoja, sinun on otettava yhteyttä yhdyskäytävän järjestelmänvalvojaan, jotta voit lisätä tarvittavan tietolähteen määrityksen.

> [!NOTE]
> Vain yhdyskäytävän järjestelmänvalvojat voivat lisätä tietolähteitä yhdyskäytävään. Varmista myös, että yhdyskäytävän järjestelmänvalvoja lisää käyttäjätilisi luetteloon käyttäjistä, joilla on oikeudet käyttää tietolähdettä. Tietojoukon asetusten sivulla voit valita vain yritysyhdyskäytävän, jossa on vastaava tietolähde, johon sinulla on käyttöoikeus.

![Yhdyskäytävään lisääminen](media/refresh-data/add-to-gateway.png)

Varmista, että liität oikean tietolähteen määrityksen tietolähteeseen. Kuten edellä olevasta näyttökuvasta näkyy, yhdyskäytävän järjestelmänvalvojat voivat luoda yhteen yhdyskäytävään useita, samaan tietolähteeseen yhdistettyjä määrityksiä, joilla kullakin on eri tunnistetiedot. Tässä esimerkissä myyntiosaston tietojoukon omistaja valitsisi AdventureWorksProducts-Myynti-tietolähteen määrityksen, kun taas tukiosaston tietojoukon omistaja liittäisi tietojoukon AdventureWorksProducts-Tuki-tietolähteen määritykseen. Jos tietolähteen määrityksen nimet eivät ole intuitiivisia, kysy yhdyskäytävän järjestelmänvalvojalta, mikä määritys valitaan.

> [!NOTE]
> Tietojoukko voi käyttää vain yhtä yhdyskäytäväyhteyttä. Paikallista tietolähdettä ei siis voi käyttää useiden yhdyskäytäväyhteyksien kautta. Tästä syystä sinun on lisättävä kaikki tarvittavat tietolähteen määritykset samaan yhdyskäytävään.

#### <a name="deploying-a-personal-data-gateway"></a>Henkilökohtaisen tietoyhdyskäytävän käyttöönotto

Jos käytössäsi ei ole yrityksen tietoyhdyskäytävää ja olet ainoa tietojoukkoja hallitseva henkilö (sinun ei tarvitse jakaa tietolähteitä muiden kanssa), voit ottaa tietoyhdyskäytävän käyttöön henkilökohtaisessa tilassa. Valitse **Yhdyskäytäväyhteys**-osion **Sinulla ei ole asennettuja henkilökohtaisia yhdyskäytäviä** -kohdasta **Asenna nyt**. Henkilökohtaista tietoyhdyskäytävää koskevat useat rajoitukset, jotka voit katsoa kohdasta [Paikallinen tietoyhdyskäytävä (henkilökohtainen tila)](service-gateway-personal-mode.md).

Toisin kuin yrityksen tietoyhdyskäytävän tapauksessa, sinun ei tarvitse lisätä tietolähteen määrityksiä henkilökohtaiseen yhdyskäytävän. Sen sijaan voit hallita tietolähteen määrityksiä tietolähteen asetuksissa olevien **tietolähteen tunnistetietojen** avulla seuraavassa näyttökuvassa kuvatulla tavalla.

![Tietolähteen tunnistetietojen määrittäminen yhdyskäytävälle](media/refresh-data/configure-data-source-credentials-gateway.png)

> [!NOTE]
> Henkilökohtainen tietoyhdyskäytävä ei tue tietojoukkoja DirectQuery-/LiveConnect-tilassa. Tietojoukon asetussivu voi pyytää sinua asentamaan sen, mutta jos käytössäsi on pelkkä henkilökohtainen yhdyskäytävä, et pysty määrittämään yhdyskäytäväyhteyttä. Tällaisten tietojoukkojen tuki edellyttää yrityksen yhdyskäytävää.

### <a name="accessing-cloud-data-sources"></a>Pilvipalvelutietolähteiden käyttö

Pilvipalvelutietolähteitä, kuten Azure SQL DB:tä, hyödyntävät tietojoukot eivät edellytä tietoyhdyskäytävä, jos Power BI voi muodostaa suoran verkkoyhteyden lähteeseen. Voit siis hallita näiden tietolähteiden määrityksiä tietojoukon asetuksissa olevien **tietolähteen tunnistetietojen** avulla. Kuten seuraavasta näyttökuvasta ilmenee, sinun ei tarvitse määrittää yhdyskäytäväyhteyttä.

![Tietolähteen tunnistetietojen määrittäminen ilman yhdyskäytävää](media/refresh-data/configure-data-source-credentials.png)

### <a name="accessing-on-premises-and-cloud-sources-in-the-same-source-query"></a>Paikallisten ja pilvilähteiden käyttäminen samassa kyselyssä

Tietojoukko voi noutaa tietoja useista lähteistä, jotka voivat olla paikallisessa tai pilvitallennustilassa. Kuten edellä mainittiin, tietojoukko voi käyttää vain yhtä yhdyskäytäväyhteyttä. Pilvipalveluiden tietolähteet eivät välttämättä edellytä yhdyskäytävää, mutta yhdyskäytävä on pakollinen, jos tietojoukko muodostaa yhteyden sekä paikallisiin että pilvilähteisiin saman koostekyselyn kautta. Tällaisessa tilanteessa Power BI:n on käytettävä yhdyskäytävää myös yhdistäessään pilvitietolähteisiin. Seuraavassa kaaviossa esitetään, miten tällaiset tietojoukot käyttävät tietolähteitään.

![Paikalliset ja pilvitietolähteet](media/refresh-data/cloud-on-premises-data-sources-diagram.png)

> [!NOTE]
> Jos tietojoukossa käytetään erillisiä koostekyselyitä muodostettaessa yhteyttä paikallisiin ja pilvilähteisiin, Power BI muodostaa yhteyden paikallisiin lähteisiin yhdyskäytäväyhteyden ja pilvilähteisiin suoran verkkoyhteyden avulla. Jos koostekysely yhdistää tai liittää tietoja paikallisista ja pilvitietolähteistä, Power BI vaihtaa yhdyskäytäväyhteyteen myös pilvilähteiden osalta.

Power BI -tietojoukot noutavat ja käyttävät lähdetietoja Power Queryn avulla. Seuraavassa koosteluettelossa on perusesimerkki kyselystä, joka yhdistää paikallisen ja pilvilähteen tietoja.

```
Let

    OnPremSource = Sql.Database("on-premises-db", "AdventureWorks"),

    CloudSource = Sql.Databases("cloudsql.database.windows.net", "AdventureWorks"),

    TableData1 = OnPremSource{[Schema="Sales",Item="Customer"]}[Data],

    TableData2 = CloudSource {[Schema="Sales",Item="Customer"]}[Data],

    MergedData = Table.NestedJoin(TableData1, {"BusinessEntityID"}, TableData2, {"BusinessEntityID"}, "MergedData", JoinKind.Inner)

in

    MergedData
```

Voit tukea paikallisten ja pilvilähteiden tietojen yhdistämistä tai liittämistä määrittämällä tietoyhdyskäytävän jommallakummalla tavalla:

- Lisää yhdyskäytävälle paikallisten tietolähteiden lisäksi pilvitietolähteen määritys.
- Valitse **Salli käyttäjän pilvipalvelutietolähteiden päivittäminen tämän yhdyskäytäväklusterin kautta** -valintaruutu.

![Päivittäminen yhdyskäytäväklusterin kautta](media/refresh-data/refresh-gateway-cluster.png)

Jos valitset yllä olevan esimerkin mukaisesti yhdyskäytävän määrityksissä olevan **Salli käyttäjän pilvipalvelutietolähteiden päivittäminen tämän yhdyskäytäväklusterin kautta** -valintaruudun, Power BI käyttää pilvipalvelulähdettä, jonka käyttäjä on määrittänyt tietojoukon asetuksissa **Tietolähteen tunnistetiedot** -kohdassa. Tämä vähentää yhdyskäytävän määrityksen resurssivaatimuksia. Jos toisaalta haluat hallita yhdyskäytäväsi muodostamia yhteyksiä tarkemmin, älä valitse tätä valintaruutua. Tässä tapauksessa sinun on lisättävä yksiselitteinen tietolähteen määritys kullekin pilvilähteelle, jonka haluat tukevan yhdyskäytävääsi. Voit myös valita valintaruudun ja lisätä pilvilähteiden yksiselitteiset tietolähdemääritykset yhdyskäytävälle. Tässä tapauksessa yhdyskäytävässä käytetään kaikkien vastaavien lähteiden tietolähdemäärityksiä.

### <a name="configuring-query-parameters"></a>Kyselyparametrien määrittäminen

Power Querylla luomasi kooste- eli M-kyselyt voivat olla hyvin yksinkertaisia vaiheita, parametrisoituja rakenteita tai mitä tahansa siltä väliltä. Seuraavassa luettelossa on pieni näyte koostekyselystä, jossa on käytetty kahta parametria: _SchemaName_ ja _TableName_. Niiden avulla käytetään tiettyä AdventureWorks-tietokannassa olevaa taulukkoa.

```
let

    Source = Sql.Database("SqlServer01", "AdventureWorks"),

    TableData = Source{[Schema=SchemaName,Item=TableName]}[Data]

in

    TableData
```

> [!NOTE]
> Kyselyparametreja tuetaan vain tuontitilassa olevissa tietojoukoissa. DirectQuery-/LiveConnect-tila ei tue kyselyjen parametrimääritelmiä.

Määritä koostekyselyn parametrit tietojoukon asetuksista ja varmista näin, että parametrisoitu tietojoukko käyttää asianmukaisia tietoja. Voit myös päivittää parametrit ohjelmallisesti [Power BI:n REST-ohjelmointirajapinnan](/rest/api/power-bi/datasets/updateparametersingroup) avulla. Seuraavassa näyttökuvassa esitetään yllä kuvailtua koostekyselyä käyttävä tietojoukon kyselyparametrien määrittäminen käyttöliittymän kautta.

![Kyselyparametrien määrittäminen](media/refresh-data/configure-query-parameters.png)

> [!NOTE]
> Power BI ei tue parametrisoituja tietolähdemäärityksiä eli dynaamisia tietolähteitä. Et voi esimerkiksi parametrisoida tietojen käyttöfunktiota Sql.Database(”SqlServer01”, ”AdventureWorks”). Jos tietojoukossa käytetään dynaamisia tietolähteitä, Power BI ilmoittaa, että se havaitsi tuntemattoman tai tukemattoman tietolähteen. Sinun on korvattava tietojen käyttöfunktion parametrit staattisilla arvoilla, jotta Power BI voi tunnistaa tietolähteet ja muodostaa niihin yhteyden. Lisätietoja on kohdassa [Tukemattoman tietolähteen vianmääritys päivitystä varten](service-admin-troubleshoot-unsupported-data-source-for-refresh.md).

## <a name="configure-scheduled-refresh"></a>Ajoitetun päivityksen määrittäminen

Liitettävyyden määrittäminen Power BI:n ja tietolähteiden välillä on haastavin osa tietojen päivityksen määrittämistä. Jäljellä olevat vaiheet on melko yksinkertaista ja sisältävät päivitysaikataulun määrittämisen sekä päivitysten virheilmoitusten käyttöönottamisen. Katso vaiheittaiset ohjeet [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md) -oppaasta.

### <a name="setting-a-refresh-schedule"></a>Päivitysaikataulun määrittäminen

**Ajoitettu päivitys** -osiossa määritetään tietojoukon päivittämisen ajankohdat ja ajankohtien tiheys. Kuten aiemmin mainittiin, voit määrittää enintään kahdeksan päivittäistä ajankohtaa, jos tietojoukkosi on jaetussa kapasiteetissa, tai 48 ajankohtaa, jos tietojoukkosi on Power BI Premiumissa. Seuraavassa näyttökuvassa esitetään ajoitettu päivitys, jonka päivitysväli on 12 tuntia.

![Ajoitetun päivityksen määrittäminen](media/refresh-data/configure-scheduled-refresh.png)

Kun päivitysaikataulu on määritetty, tietojoukon asetussivulla kerrotaan seuraavan päivityksen ajankohta yllä olevan kuvan mukaisesti. Jos haluat päivittää tiedot tätä aiemmin esimerkiksi yhdyskäytävän ja tietolähteen määritteiden testaamista varten, suorita päivitys vasemman siirtymisruudun tietojoukko-valikossa olevalla **Päivitä nyt** -toiminnolla. Päivityspyynnöt eivät vaikuta seuraavan ajoitetun päivityksen ajankohtaan, mutta ne kuluttavat päivittäistä päivityskiintiötä. Tätä aihetta on käsitelty ylempänä tässä artikkelissa.

Huomaa myös, että määritetty päivityksen kellonaika ei ole ehdottoman tarkka. Power BI käynnistää ajoitetut päivitykset sopivimmalla hetkellä. Pyrimme siihen, että päivitys alkaa 15 minuutin sisällä suunnitellusta ajankohdasta, mutta viive voi venyä tunninkin mittaiseksi, jos tarvittavat resurssit eivät ole saatavilla aikaisemmin.

> [!NOTE]
> Power BI peruu päivitysaikataulusi aktivoinnin neljän peräkkäisen päivitysvirheen jälkeen tai havaitessaan vakavan, määritysten päivittämistä edellyttävän virheen, jota palvelu ei pysty ratkaisemaan itse. Esimerkiksi virheelliset tai vanhentuneet tunnistetiedot voivat aiheuttaa tällaisen tilanteen. Peräkkäisten päivitysvirheiden raja-arvoa ei voi muuttaa.

### <a name="getting-refresh-failure-notifications"></a>Päivityksen virheilmoitusten saaminen

Oletusarvoisesti Power BI lähettää virheistä sähköposti-ilmoituksen tietojoukon omistajalle niin, että omistaja voi reagoida päivitysongelmiin ajoissa. Power BI lähettää sinulle ilmoituksen myös silloin, kun palvelu poistaa aikataulusi käytöstä peräkkäisten virheiden vuoksi. Microsoft suosittelee, että pidät valintaruudun **Lähetä päivityksenvirheistä sähköposti-ilmoitus** valittuna.

On myös hyvä määrittää lisää vastaanottajia käyttämällä tekstiruutua **Lähetä sähköpostiviesti näille käyttäjille, kun päivitys epäonnistuu**. Määritetyt vastaanottajat saavat ilmoitukset päivitysvirheistä tietojoukon omistajan lisäksi. Tämä voi olla työtoveri, joka huolehtii tietojoukosta lomasi aikana. Se voi myös olla sähköpostialias tukiryhmään, joka hoitaa osastosi tai organisaatiosi päivitysongelmat. Päivitysvirheiden ilmoitusten lähettäminen muille tietojoukon omistajan lisäksi on hyödyllinen tapa varmistaa, että ongelmat huomataan ja käsitellään ajallaan.

Huomaa, että Power BI ei lähetä ainoastaan päivitysvirheistä koskevia ilmoituksia, vaan se ilmoittaa myös käyttämättömyydestä johtuvasta palvelun keskeytymisestä. Power BI pitää tietojoukkoa käyttämättömänä, kun yksikään käyttäjä ei ole käynyt raporttinäkymässä tai tietojoukosta koostetussa raportissa kahteen kuukauteen. Tällaisissa tilanteissa Power BI lähettää tietojoukon omistajalle sähköpostiviestin, jossa kerrotaan, että palvelu on pysäyttänyt tietojoukon päivitysaikataulun. Seuraavassa näyttökuvassa on esimerkki tällaisesta ilmoituksesta.

![Päivitysten keskeytymisestä ilmoittava sähköposti](media/refresh-data/email-paused-refresh.png)

Voit jatkaa ajoitettuja päivityksiä käymällä kyseisestä tietojoukosta koostetussa raportissa tai raporttinäkymässä tai päivittämällä tietojoukon manuaalisesti **Päivitä nyt** -vaihtoehdon avulla.

### <a name="checking-refresh-status-and-history"></a>Päivityksen tilan ja historian tarkistaminen

Virheilmoitusten lisäksi suosittelemme tarkistamaan tietojoukot säännöllisesti päivitysvirheiden varalta. Voit tehdä tämän nopeasti avaamalla työtilan tietojoukkojen luettelon. Virheitä palauttavat tietojoukot on merkitty pienellä varoituskuvakkeella. Voit katsoa lisätiedot valitsemalla varoituskuvakkeen seuraavassa näyttökuvassa esitetyllä tavalla. Lisätietoja päivitysvirheiden vianmäärityksestä on kohdassa [Päivitystilanteiden vianmääritys](refresh-troubleshooting-refresh-scenarios.md).

![Päivityksen tilan varoitus](media/refresh-data/refresh-status-warning.png)

Varoituskuvake ilmaisee tietojoukon senhetkiset ongelmat, mutta suosittelemme myös tarkistamaan päivityshistorian ajoittain. Nimensä mukaisesti päivityshistoria mahdollistaa viimeisimpien synkronointijaksojen onnistumisen tai epäonnistumisen tilan tarkistamisen. Yhdyskäytävän järjestelmänvalvoja on esimerkiksi saattanut päivittää vanhentuneet tietojoukon tunnistetiedot. Seuraavasta näyttökuvasta voit nähdä, että päivityshistoriasta ilmenee, milloin päivitysvirhe on korjattu.

![Päivityshistorian viestit](media/refresh-data/refresh-history-messages.png)

> [!NOTE]
> Linkin päivityshistoriaan on saatavana tietojoukon asetuksista. Voit myös noutaa päivityshistorian tiedot ohjelmallisesti [Power BI:n REST-ohjelmointirajapinnan](/rest/api/power-bi/datasets/getrefreshhistoryingroup) avulla. Mukautetun ratkaisun avulla voit valvoa useiden tietojoukkojen päivityshistoriaa keskitetysti.

## <a name="automatic-page-refresh"></a>Automaattinen sivun päivitys

Automaattinen sivun päivitys toimii raporttisivutasolla. Sen avulla raporttien tekijät voivat määrittää sivun visualisoinneille päivitysvälin, jota käytetään vain sivua käytettäessä. Automaattinen sivun päivitys on käytettävissä vain DirectQuery-tietolähteille. Pienin mahdollinen päivitysväli riippuu siitä, millaisessa työtilassa raportti julkaistaan, sekä Premium-työtilojen kapasiteettihallinta-asetuksista.

Lue lisätietoja [automaattisen sivun päivityksen](desktop-automatic-page-refresh.md) ohjeartikkelista.


## <a name="best-practices"></a>Parhaat käytännöt

Tarkistamalla tietojoukkojesi päivityshistorian säännöllisesti voit varmistaa, että raporteissa ja koontinäytöissä käytetään ajantasaisia tietoja. Tämä on parhaista käytännöistä tärkeimpiä. Jos havaitset ongelmia, korjaa ne pian ja ota tarvittaessa yhteys tietolähteiden omistajiin ja yhdyskäytävän järjestelmänvalvojiin.

Huomioi seuraavat suositukset, jotka koskevat tietojoukkojen luotettavan päivitysprosessin perustamista ja ylläpitoa:

- Ajoita päivitykset kiireettömiin kellonaikoihin, varsinkin jos tietojoukkosi ovat Power BI Premiumissa. Jos jaat tietojoukkojen päivitysjaksot laajemmalle aikavälille, pystyt välttämään rajallisten resurssien kuormitushuiput. Päivitysjakson käynnistysviiveet ovat merkki resurssien ylikuormituksesta. Jos kaikki Premium-kapasiteetti on käytössä, Power BI saattaa jopa ohittaa päivitysjaksoja.
- Pidä päivitysrajat mielessäsi. Jos tietolähde muuttuu usein tai jos tietomäärät ovat merkittäviä, tuontitilan sijaan kannattaa käyttää DirectQuery-/LiveConnect-tilaa, jos lähteen lisääntynyt kuormitus ja vaikutus kyselyjen suorituskykyyn on hyväksyttävä. Älä päivitä tuontitilassa olevaa tietojoukkoa koko ajan. DirectQuery-LiveConnect-tilaa koskevat kuitenkin useat rajoitukset, kuten palautettavien tietojen yhden miljoonan rivin raja ja vastausten 225 sekunnin määräaika kyselyjä suoritettaessa. Katso lisätiedot kohdasta [DirectQueryn käyttö Power BI Desktopissa](desktop-use-directquery.md). Nämä rajoitukset saattavat kuitenkin edellyttää tuontitilan käyttöä. Jos tietomäärä on erittäin suuri, harkitse [Power BI:n koosteiden](desktop-aggregations.md) käyttöä.
- Varmista, että tietojoukon päivitysaika ei ylitä päivityksen enimmäiskestoa. Tarkista päivityksen kesto Power BI Desktopin avulla. Jos päivitys kestää yli 2 tuntia, harkitse tietojoukon siirtämistä Power BI Premiumiin. Tietojoukkoa ei ehkä voida päivittää jaetulla kapasiteetilla. Harkitse myös sellaisten tietojoukkojen [asteittaista päivittämistä Power BI Premiumiin](service-premium-incremental-refresh.md), joiden koko on yli 1 Gt tai joiden päivittäminen kestää useita tunteja.
- Optimoi tietojoukkosi niin, että ne sisältävät vain sellaiset taulukot ja sarakkeet, joita käytetään raportissasi ja raporttinäkymässäsi. Optimoi koostekyselyt ja vältä mahdollisuuksien mukaan dynaamisten tietolähteiden määritykset ja kalliit DAX-laskennat. Vältä erityisesti DAX-funktioita, jotka testaavat taulukon jokaisen rivin. Näiden muistin kulutus ja tietojenkäsittelykustannukset ovat korkeat.
- Käytä samoja tietosuoja-asetuksia kuin Power BI Desktopissa. Näin voit varmistaa, että Power BI voi luoda tehokkaita lähdekyselyitä. Huomaa, että Power BI Desktop ei julkaise tietosuoja-asetuksia. Sinun on otettava nämä asetukset uudelleen käyttöön manuaalisesti tietolähteiden määrityksissä tietojoukon julkaisemisen jälkeen.
- Rajoita visualisoinnit koontinäyttösi, erityisesti jos käytät [rivitason suojausta (RLS)](service-admin-rls.md). Kuten aiemmin tässä artikkelissa kerrottiin, raporttinäkymän ruutujen liiallinen määrä voi vaikuttaa merkittävästi päivityksen kestoon.
- Yhdistä tietojoukot paikallisiin tietolähteisiin yrityksen luotettavan tietoyhdyskäytävän avulla. Jos huomaat yhdyskäytävään liittyviä päivityksen virheitä, kuten sellaisia, joiden mukaan yhdyskäytävä ei ole käytettävissä tai se on ylikuormittunut, ota yhteys yhdyskäytävän järjestelmänvalvojiin ja pyydä häntä lisäämään yhdyskäytäviä aiemmin luotuihin klustereihin tai ottamaan käyttöön uusia klustereita (skaalautuminen ylöspäin/vaakasuunnassa).
- Käytä erillisiä tietoyhdyskäytäviä tietojoukkojen tuomiseen sekä tietojoukkojen DirectQuery-/LiveConnect-yhteyksiin niin, että ajoitetun päivityksen aikana tuodut tiedot eivät vaikuta DirectQuery-/LiveConnect-tietojoukkojen päällä olevien raporttien ja raporttinäkymien suorituskykyyn. Tällaiset tietojoukot lähettävät tietolähteelleen kyselyn käyttäjän jokaisen toimen yhteydessä.
- Varmista, että Power BI voi lähettää päivityksen virheilmoituksia postilaatikkoosi. Roskapostisuodattimet saattaa estää sähköpostiviestejä tai siirtää ne eri kansioon jolloin et välttämättä huomaa niitä heti.


## <a name="next-steps"></a>Seuraavat vaiheet

[Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md)  
[Välineet päivitysongelmien vianmääritykseen](service-gateway-onprem-tshoot.md)  
[Päivitystilanteiden vianmääritys](refresh-troubleshooting-refresh-scenarios.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
