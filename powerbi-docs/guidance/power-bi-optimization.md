---
title: Optimointiopas Power BI:hin
description: Optimointiopas Power BI:hin.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
ms.openlocfilehash: d718c9c7f627d735c083a46c1483815e3744faca
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79378865"
---
# <a name="optimization-guide-for-power-bi"></a>Optimointiopas Power BI:hin

Tässä artikkelissa olevien ohjeiden avulla kehittäjät ja järjestelmänvalvojat voivat tuottaa ja ylläpitää optimoituja Power BI -ratkaisuja. Voit optimoida ratkaisusi eri arkkitehtonisilla tasoilla. Tasoja ovat seuraavat:

- tietolähteet
- tietomalli
- visualisoinnit, mukaan lukien koontinäytöt, Power BI -raportit ja Power BI:n sivutetut raportit
- ympäristö, mukaan lukien kapasiteetit, tietoyhdyskäytävät ja verkko.

## <a name="optimizing-the-data-model"></a>Tietomallin optimointi

Tietomalli tukee koko visualisointikokemusta. Tietomallit ovat joko ulkoisesti isännöityjä tai sisäisesti isännöityjä, ja Power BI:ssä niitä kutsutaan _tietojoukoiksi_. On tärkeää ymmärtää toimintavaihtoehtosi ja valita ratkaisullesi sopiva tietojoukkotyyppi. Tietojoukkotiloja on kolme: Tuonti, DirectQuery ja Yhdistelmä. Lisätietoja on artikkeleissa [Tietojoukot Power BI -palvelussa](../service-datasets-understand.md) ja [Tietojoukkojen tilat Power BI -palvelussa](../service-dataset-modes-understand.md).

Jos haluat ohjeita tiettyä tietojoukkotilaa varten, katso seuraavia:

- [Tietojen vähentämisen tekniikat tuonnin mallinnusta varten](import-modeling-data-reduction.md)
- [Power BI Desktopin DirectQuery-mallin ohjeet](directquery-model-guidance.md)
- [Power BI Desktopin yhdistelmämallin ohjeet](composite-model-guidance.md)

## <a name="optimizing-visualizations"></a>Visualisointien optimointi

Power BI:n visualisoinnit voivat olla koontinäyttöjä, Power BI -raportteja tai Power BI:n sivutettuja raportteja. Jokaisella on eri arkkitehtuurinsa, joten jokaisella on myös omat ohjeensa. 

### <a name="dashboards"></a>Koontinäytöt

On tärkeää ymmärtää, että Power BI ylläpitää välimuistia koontinäytön ruutuja varten reaaliaikaisia raporttiruutuja ja suoratoistoruutuja lukuun ottamatta. Lisätietoja on artikkelissa [Tietojen päivitys Power BI:ssä (ruudun päivitys)](../refresh-data.md#tile-refresh). Jos tietojoukossasi käytetään dynaamista [rivitason suojausta (RLS)](../service-admin-rls.md), varmista, että ymmärrät sen vaikutuksen suorituskykyyn, sillä ruudut tallennetaan välimuistiin käyttäjäkohtaisesti.

Kun kiinnität reaaliaikaisia raporttiruutuja koontinäyttöön, välimuisti ei ole niiden syötteen lähteenä. Sen sijaan ne toimivat raporttien tavoin ja tekevät kyselyjä taustaytimiin lennossa.

Nimensä mukaisesti tietojen noutaminen välimuistista tarjoaa paremman ja yhdenmukaisemman suorituskyvyn kuin tietolähteen varassa oleminen. Yksi tapa hyödyntää tätä toimintoa on ottaa koontinäytöt käyttäjien ensimmäiseksi aloitussivuksi. Kiinnitä usein käytetyt ja usein pyydetyt visualisoinnit koontinäyttöihin. Näin koontinäytöistä tulee arvokas ”ensisijainen puolustautumiskeino”, joka tarjoaa tasaista suorituskykyä pienemmällä kapasiteetin kuormituksella. Käyttäjät voivat edelleen siirtyä raportin läpi napsauttamalla ja analysoida yksityiskohtia.

DirectQueryn ja reaaliaikaisen yhteyden kohdalla kyselyn välimuistia päivitetään säännöllisin väliajoin tekemällä kyselyjä tietolähteelle. Oletusarvoisesti tämä tapahtuu tunnin välein, mutta voit määrittää muun aikavälin tietojoukon asetuksissa. Jokainen välimuistipäivitys lähettää kyselyjä taustalla olevaan tietolähteeseen välimuistin päivittämistä varten. Tehtyjen kyselyiden määrä riippuu koontinäyttöön kiinnitettyjen ja kyseisestä tietolähteestä riippuvien visualisointien määrästä. Huomaa, että jos rivitason suojaus on käytössä, kyselyt luodaan kullekin eri suojauskontekstille. Ajattele esimerkiksi, että on olemassa kaksi eri roolia, jotka luokittelevat käyttäjiäsi, ja niillä on kaksi eri näkymää tietoihin. Kyselyvälimuistin päivittämisen aikana Power BI luo kaksi kyselyjoukkoa.

### <a name="power-bi-reports"></a>Power BI -raportit

Power BI -raporttirakenteiden optimointiin on useita suosituksia.

> [!NOTE]
> Kun raporttien pohjana on DirectQuery-tietojoukko, saat lisätietoja raporttirakenteiden optimoinnista artikkelista [DirectQuery-mallin ohjeet Power BI Desktopiin (raporttirakenteiden optimointi)](directquery-model-guidance.md#optimize-report-designs).

#### <a name="apply-the-most-restrictive-filters"></a>Rajoittavimpien suodattimien käyttäminen

Mitä enemmän tietoja visualisoinnissa on oltava näkyvissä, sitä hitaampaa on kyseisen visualisoinnin lataaminen. Vaikka tämä periaate tuntuu itsestäänselvältä, se voi kuitenkin helposti unohtua. Otetaan esimerkiksi tilanne, jossa sinulla on suuri tietojoukko. Laadit tietojoukon päälle raportin, jossa on taulukko. Loppukäyttäjät siirtyvät haluamilleen riveille käyttämällä sivulla olevia osittajia. Yleensä he ovat kiinnostuneita vain muutamista kymmenistä riveistä.

Yleinen virhe on, että taulukon oletusnäkymää ei ole suodatettu, eli siinä näkyvät kaikki yli 100 miljoonaa riviä. Näiden rivien tiedot ladataan muistiin ja puretaan jokaisen päivityksen yhteydessä. Tämä käsittely aiheuttaa huomattavia muistivaatimuksia. Ratkaisu tilanteeseen on vähentää taulukon näyttämää tietoyksiköiden enimmäismäärää käyttämällä ”Ylimmät N” -suodatinta. Tietoyksiköiden enimmäismäärä voi olla suurempi kuin mitä käyttäjät tarvitsisivat, esimerkiksi 10 000. Loppukäyttäjän käyttökokemus ei muutu, mutta muistin käyttö pienenee huomattavasti. Ja mikä tärkeintä, suorituskyky paranee.

Samaa edellä esitettyä suunnittelumenetelmää on suositeltavaa käyttää kaikkiin raportin visualisointeihin. Kysy itseltäsi, ovatko kaikki tiedot tässä visualisoinnissa tarpeellisia? Onko olemassa keinoja, joilla visualisoinnissa näytettyjen tietojen määrää voisi suodattaa niin, että vaikutus loppukäyttäjän kokemukseen olisi mahdollisimman pieni? Muista, että erityisesti taulukot voivat olla kalliita.

#### <a name="limit-visuals-on-report-pages"></a>Vähennä raporttisivujen visualisointeja

Edellä oleva periaate koskee myös raporttisivulle lisättävien visualisointien määrää. On erittäin suositeltavaa, että vähennät yksittäisellä raporttisivulla olevien visualisointien määrän vain siihen, mikä on tarpeellista. [Alirakennesivut](report-drillthrough.md) ja [raporttisivujen työkaluvihjeet](report-page-tooltips.md) ovat erinomainen keino antaa lisätietoja ilman tarvetta ahtaa lisää visualisointeja sivulle.

#### <a name="evaluate-custom-visual-performance"></a>Mukautetun visualisoinnin suorituskyvyn arvioiminen

Muista testata jokainen mukautettu visualisointi, jotta niiden hyvä suorituskyky voidaan varmistaa. Huonosti optimoidut Power BI -visualisoinnit voivat vaikuttaa kielteisesti koko raportin suorituskykyyn.

### <a name="power-bi-paginated-reports"></a>Power BI:n sivutetut raportit

Power BI:n sivutettuja raporttirakenteita voi optimoida käyttämällä parhaan käytännön rakennetta raportin tietojen noutamiseen. Lisätietoja on artikkelissa [Sivutettujen raporttien tietojen nouto-ohjeet](report-paginated-data-retrieval.md).

Varmista myös, että kapasiteetissa on tarpeeksi muistia varattuna [sivutettujen raporttien kuormitukseen](../service-admin-premium-workloads.md#paginated-reports).

## <a name="optimizing-the-environment"></a>Ympäristön optimointi

Voit optimoida Power BI -ympäristön määrittämällä kapasiteettiasetukset, määrittämällä tietoyhdyskäytävien koon ja pienentämällä verkkoviivettä.

### <a name="capacity-settings"></a>Kapasiteettiasetukset

Kun käytät varattuja kapasiteetteja (käytettävissä Power BI Premiumissa (P SKU:t) tai Power BI Embeddedissä (A SKU:t, A4–A6)), voit hallita kapasiteettiasetuksia. Katso lisätietoja artikkelista [Premium-kapasiteettien hallinta](../service-premium-capacity-manage.md). Ohjeita kapasiteetin optimoimiseen on artikkelissa [Premium-kapasiteettien optimointi](../service-premium-capacity-optimize.md).

### <a name="gateway-sizing"></a>Yhdyskäytävän koko

Yhdyskäytävää tarvitaan, kun Power BI:n on käytettävä tietoja, jotka eivät ole saatavilla suoraan Internetin kautta. Voit asentaa [paikallisen tietoyhdyskäytävän](../service-gateway-onprem.md) paikalliseen palvelimeen tai näennäiskoneen isännöimään infrastruktuuri palveluna (IaaS) -järjestelmään.

Jos haluat tietoja yhdyskäytävän kuormituksista ja kokosuosituksista, katso [Paikallisen tietoyhdyskäytävän koon määrittäminen](gateway-onprem-sizing.md).

### <a name="network-latency"></a>Verkon viive

Verkon viive voi vaikuttaa raportin suorituskykyyn kasvattamalla aikaa, jonka pyynnöt tarvitsevat saavuttaakseen Power BI -palvelun, ja vastausten toimitusaikaa. Vuokraajille nimetään Power BI:ssä tietty alue.

> [!TIP]
> Jos haluat tietää, missä -vuokraajasi sijaitsee, lue artikkeli [Missä Power BI -vuokraajani sijaitsee?](../service-admin-where-is-my-tenant-located.md).

Kun vuokraajan käyttäjät käyttävät Power BI -palvelua, heidän pyyntönsä reititetään aina tälle alueelle. Kun pyynnöt saavuttavat Power BI -palvelun, palvelu voi tämän jälkeen lähettää lisäpyyntöjä esimerkiksi taustalla olevaan tietolähteeseen tai tietoyhdyskäytävään, joita verkkoviive koskee myös.

Työkalut, kuten [Azure Speed Test](https://azurespeedtest.azurewebsites.net/), voivat osoittaa verkkoviiveen asiakkaan ja Azure-alueen välillä. Yleensä voit minimoida verkkoviiveen vaikutuksen pyrkimällä pitämään tietolähteet, yhdyskäytävät ja Power BI -klusterin mahdollisimman lähellä. Parasta on, jos ne sijaitsevat samalla alueella. Jos verkkoviive on ongelma, voit kokeilla yhdyskäytävien ja tietolähteiden sijoittamista lähemmäs Power BI -klusteria sijoittamalla ne pilvipalvelussa isännöitäviin näennäiskoneisiin.

## <a name="monitoring-performance"></a>Suorituskyvyn valvonta

Voit valvoa suorituskykyä pullonkaulojen tunnistamisesta varten. Hitaiden kyselyjen tai raporttien visualisointien tulee olla jatkuvan optimoinnin keskipisteessä. Valvonta voidaan tehdä suunnitteluvaiheessa Power BI Desktopissa tai Power BI Premium -kapasiteettien tuotantokuormituksissa. Lisätietoja on artikkelissa [Raporttien suorituskyvyn valvonta Power BI:ssä](monitor-report-performance.md).

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Power BI -ohjeet](index.yml)
- [Raportin suorituskyvyn valvominen](monitor-report-performance.md)
- Tekninen raportti: [Power BI:n yrityskäyttöönoton suunnitteleminen](https://go.microsoft.com/fwlink/?linkid=2057861)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
