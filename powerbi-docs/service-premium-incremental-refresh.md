---
title: Lisäävää päivitys Power BI:ssä
description: Opi ottamaan käyttöön erittäin suuria tietojoukkoja Power BI:ssä.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 03/27/2020
ms.author: davidi
LocalizationGroup: Premium
ms.openlocfilehash: 1208a598c08b87d0e479e4d8901f880a5dfa6900
ms.sourcegitcommit: dc18209dccb6e2097a92d87729b72ac950627473
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/27/2020
ms.locfileid: "80361817"
---
# <a name="incremental-refresh-in-power-bi"></a>Lisäävää päivitys Power BI:ssä

Lisäävä päivitys mahdollistaa erittäin suurien tietojoukkojen käytön Power BI:ssä tarjoamalla seuraavat edut:

> [!div class="checklist"]
> * **Päivitykset sujuvat nopeammin**: vain muutetut tiedot päivitetään. Voit esimerkiksi päivittää vain viimeiset viisi päivää 10 vuoden tietojoukosta.
> * **Päivitykset ovat luotettavampia**: sinun ei tarvitse enää säilyttää pitkäkestoisia yhteyksiä lyhytkestoisiin lähdejärjestelmiin.
> * **Resurssien kulutus on vähäisempää**: kun päivitettäviä tietoja on vähemmän, muistin ja muiden resurssien yleinen kulutus on pienempi.

> [!NOTE]
> Lisäävä päivitys on nyt käytettävissä Power BI Pro- ja Premium-versioissa sekä jaetuissa tilauksissa ja tietojoukoissa. 

## <a name="configure-incremental-refresh"></a>Lisäävän päivityksen määrittäminen

Lisäävän päivityksen käytännöt on määritetty Power BI Desktopissa, ja ne otetaan käyttöön, kun ne on julkaistu Power BI -palvelussa.


### <a name="filter-large-datasets-in-power-bi-desktop"></a>Suurien tietojoukkojen suodattaminen Power BI Desktopissa

Mahdollisesti miljardeja rivejä sisältävät suuret tietojoukot eivät ehkä mahdu Power BI Desktop -malliin, koska pöytätietokoneessa saatavilla olevat muistiresurssit rajoittavat PBIX-tiedostoa. Tällaisia tietojoukkoja suodatetaan siksi yleensä tuonnin yhteydessä. Tämäntyyppistä suodatusta sovelletaan siitä huolimatta, käytetäänkö lisäävää päivitystä vai ei. Lisäävän päivityksen suodatuksessa käytetään Power Queryn päivämäärä-/aikaparametreja.

#### <a name="rangestart-and-rangeend-parameters"></a>RangeStart- ja RangeEnd-parametrit

Jos haluat käyttää lisäävää päivitystä, tietojoukot suodatetaan Power Queryn päivämäärä/aikaparametrien avulla varatuilla, kirjainkooltaan merkitsevillä nimillä **RangeStart** ja **RangeEnd**. Näiden parametrien avulla tuodut tiedot suodatetaan Power BI Desktopiin ja tiedot jaetaan myös dynaamisesti alueisiin, kun ne on julkaistu Power BI -palvelussa. Palvelu korvaa parametriarvot kunkin osion suodattamiseksi. Niitä ei tarvitse määrittää palvelun tietojoukon asetuksissa. Julkaisun jälkeen Power BI -palvelu ohittaa parametrin arvot automaattisesti.

Voit määrittää parametreille oletusarvot valitsemalla Power Query -editorissa **Parametrien hallinta**.

![Parametrien hallinta](media/service-premium-incremental-refresh/manage-parameters.png)

Kun parametrit on määritetty, voit käyttää suodatinta valitsemalla **Mukautettu suodatin** -valikkovaihtoehdon sarakkeelle.

![Mukautettu suodatin](media/service-premium-incremental-refresh/custom-filter.png)

Varmista, että rivit suodatetaan, kun sarakkeen arvo *on suurempi tai yhtä suuri kuin* **RangeStart** ja *pienempi kuin* **RangeEnd**. Muilla suodatinyhdistelmillä rivit saatetaan laskea kahdesti.

![Rivien suodattaminen](media/service-premium-incremental-refresh/filter-rows.png)

> [!IMPORTANT]
> Varmista, että kyselyissä on yhtäsuuruusmerkki (=) joko **RangeStart**- tai **RangeEnd**-kohdassa, mutta ei niissä molemmissa. Jos kummassakin parametrissa on yhtäsuuruusmerkki (=), rivi voi täyttää kahden osion ehdot, mikä voi johtaa mallin tietojen kaksoiskappaleisiin. Esimerkiksi,  
> \#"Filtered Rows" = Table.SelectRows(dbo_Fact, kumpikin [OrderDate] **>= RangeStart** ja [OrderDate] **<= RangeEnd**) saattaa aiheuttaa tietojen kaksoiskappaleita.

> [!TIP]
> Vaikka parametrien tietotyypin on oltava päivämäärä/aika, se voidaan muuntaa vastaamaan tietolähteen vaatimuksia. Esimerkiksi seuraava Power Query -funktio muuntaa päivämäärän/ajan arvon muistuttamaan tietovarastoissa yleisen muodon *vvvvkkpp* kokonaisluvun korvaavaa avainta. Funktio voidaan kutsua suodattimen vaiheen mukaan.
>
> `(x as datetime) => Date.Year(x)*10000 + Date.Month(x)*100 + Date.Day(x)`

Valitse **Sulje ja ota käyttöön** Power Query -editorissa. Sinulla pitäisi olla tietojoukon alijoukko Power BI Desktopissa.

#### <a name="filter-date-column-updates"></a>Päivämääräsarakkeen päivitysten suodattaminen

Päivämääräsarakkeen suodatinta käytetään tietojen jakamiseen dynaamisesti alueisiin Power BI -palvelussa. Lisäävää päivitystä ei ole suunniteltu tukemaan tapauksia, joissa suodatettu päivämääräsarake on päivitetty lähdejärjestelmässä. Päivitys tulkitaan lisäämiseksi ja poistamiseksi (ei todelliseksi päivitykseksi). Jos poisto tehdään historialliselta alueelta eikä lisäävältä alueelta, sitä ei poimita. Tämä voi aiheuttaa tietojen päivittämisen virheitä osion avain -ristiriitojen vuoksi.

#### <a name="query-folding"></a>Kyselyn taittaminen

On tärkeää, että jakosuodattimet lähetetään lähdejärjestelmään, kun kyselyjä lähetetään päivitystoimintoja varten. Suodattimen lähettäminen edellyttää, että tietolähde tukee kyselyn taittamista. Useimmat tietolähteet, jotka tukevat SQL-kyselyitä, tukevat kyselyn taittamista. Kuitenkin tietolähteet, kuten tietuetiedostot, blob-objektit, verkko ja OData-syötteet, eivät yleensä tue sitä. Jos tietolähteen tausta ei tue suodatinta, suodatinta ei voi lähettää. Tässä tapauksessa koostemoduuli kompensoi ja ottaa suodattimen käyttöön paikallisesti, mikä saattaa edellyttää koko tietojoukon noutamista tietolähteestä. Tämä voi hidastaa lisäävää päivitystä merkittävästi, ja prosessi voi johtaa resurssien loppumiseen joko Power BI -palvelussa tai paikallisessa tietoyhdyskäytävässä.

Kun otetaan huomioon kunkin tietolähteen kyselyn taitostuen eri tasot, on suositeltavaa, että tarkistat suodatinlogiikan sisältyvän lähdekyselyihin. Tämän helpottamiseksi Power BI Desktop yrittää suorittaa tämän tarkistuksen puolestasi. Jos tarkistusta ei voida suorittaa, lisäävän päivityksen valintaikkunassa näkyy varoitus lisäävän päivityksen käytäntöä määritettäessä. SQL-pohjaiset tietolähteet, kuten SQL, Oracle ja Teradata, voivat käyttää tätä varoitusta. Muut lähteet eivät ehkä pysty suorittamaan tarkistusta ilman kyselyjen jäljitystä. Jos Power BI Desktop ei pysty suorittamaan tarkistusta, näyttöön tulee seuraava varoitus. Jos näet tämän varoituksen ja haluat tarkistaa, että tarvittava kyselyn taittaminen tapahtuu, voit käyttää Kyselydiagnostiikka-toimintoa tai jäljittää lähdetietokannan vastaanottamat kyselyt.

 ![Kyselyn taittaminen](media/service-premium-incremental-refresh/query-folding.png)

### <a name="define-the-refresh-policy"></a>Päivityskäytännön määrittäminen

Lisäävä päivitys on käytettävissä taulukoiden pikavalikossa lukuun ottamatta reaaliaikaisen yhteyden malleja.

![Päivityskäytäntö](media/service-premium-incremental-refresh/refresh-policy.png)

#### <a name="incremental-refresh-dialog"></a>Lisäävä päivitys -valintaikkuna

Lisäävä päivitys -valintaikkuna tulee näkyviin. Ota valintaikkuna käyttöön vaihtopainikkeella.

![Päivitystiedot](media/service-premium-incremental-refresh/refresh-details.png)

> [!NOTE]
> Jos taulukon Power Query -lauseke ei viittaa parametreihin, joilla on varatut nimet, vaihtopainike on poistettu käytöstä.

Otsikkoteksti kertoo seuraavaa:

- Päivityskäytännöt määritetään Power BI Desktopissa, ja palvelun päivitystoiminnot käyttävät niitä.

- Jos et pysty lataamaan lisäävän päivityskäytännön sisältävää PBIX-tiedostoa Power BI -palvelusta, se ei avaudu Power BI Desktopissa. Vaikka tätä saatetaan tukea tulevaisuudessa, huomaa, että nämä tietojoukot voivat kasvaa niin suuriksi, että niitä on hankala ladata ja avata tavallisella pöytätietokoneella.

#### <a name="refresh-ranges"></a>Päivitysalueet

Seuraavassa esimerkissä määritetään päivityskäytäntö tallentamaan tiedot viideksi kokonaiseksi kalenterivuodeksi sekä kuluvan vuoden tiedot nykyiseen päivämäärään saakka ja päivittämään asteittain 10 päivän tiedot. Ensimmäinen päivitystoiminto lataa historiatietoja. Myöhemmät päivitykset ovat lisääviä ja, jos ne ovat määritelty suoritettavaksi päivittäin, ne suorittavat seuraavat toiminnot:

- Lisää uusi tietopäivä.

- Päivitä 10 päivää nykyiseen päivämäärään saakka.

- Poista kalenterivuodet, jotka ovat aikaisempia kuin viisi vuotta ennen nykyistä päivämäärää. Esimerkiksi jos nykyinen päivämäärä on 1.1.2019, vuosi 2013 poistetaan.

Power BI -palvelun ensimmäinen päivitys saattaa kestää kauemmin kaikkien viiden koko kalenterivuoden tuomiseksi. Myöhemmät päivitykset saattavat viedä vain hetken.

![Päivitysalueet](media/service-premium-incremental-refresh/refresh-ranges.png)


#### <a name="current-date"></a>Nykyinen päivämäärä

*Nykyinen päivämäärä* perustuu järjestelmän päivämäärään päivityksen hetkellä. Jos ajoitettu päivitys on otettu käyttöön Power BI -palvelussa, valittu aikavyöhyke otetaan huomioon nykyistä päivämäärää määritettäessä. Sekä manuaalisesti käynnistetyt että ajoitetut päivitykset ottavat aikavyöhykkeen huomioon, jos se on käytettävissä. Esimerkiksi päivityksessä, joka tapahtuu 20.00 Tyynenmeren normaaliaikaa (Yhdysvallat ja Kanada) siten, että aikavyöhyke on määritetty, nykyinen päivämäärä määräytyy Tyynenmeren ajan mukaan eikä GMT:n mukaan (jolloin päivä olisi jo vaihtunut).

![Aikavyöhyke](media/service-premium-incremental-refresh/time-zone2.png)

> [!NOTE]
> Alueiden määritys saattaa olla ainoa asia, mitä sinun tarvitsee tehdä, jolloin voit siirtyä suoraan alla olevaan julkaisuvaiheeseen. Muut avattavat valikot on tarkoitettu kehittyneille ominaisuuksille.

### <a name="advanced-policy-options"></a>Lisäkäytäntöasetukset

#### <a name="detect-data-changes"></a>Havaitse tietojen muutokset

10 päivän lisäävä päivitys on paljon tehokkaampi kuin viiden vuoden koko päivitys. Voit kuitenkin tehostaa toimintaa vieläkin enemmän. Jos valitset **Havaitse tietojen muutokset** -valintaruudun, voit valita päivämäärä/aika-sarakkeen, jonka avulla tunnistetaan ja päivitetään vain päivät, joiden tiedot ovat muuttunut. Tällöin oletetaan, että lähdejärjestelmässä on kyseinen sarake, joka on yleensä valvontaa varten. **Tämä ei saa olla sama sarake kuin jota käytetään tietojen jakamiseen RangeStart- ja RangeEnd-parametreilla.** Tämän sarakkeen suurin arvo lasketaan jokaisen lisäävän alueen ajanjakson osalta. Jos arvo ei ole muuttunut viimeisen päivityksen jälkeen, ajanjaksoa ei tarvitse päivittää. Esimerkissä lisäävästi päivitettävien päivien määrä voisi vähentyä vielä kymmenestä noin kahteen.

![Muutosten havaitseminen](media/service-premium-incremental-refresh/detect-changes.png)

> [!TIP]
> Nykyinen rakenne edellyttää, että sarake on pysyvä ja tallennettu välimuistiin tietojen muutosten havaitsemiseksi. Kannattaa harkita jotakin seuraavista tekniikoista kardinaliteetin ja muistin kulutuksen vähentämiseksi.
>
> Säilytä vain sarakkeen suurin arvo päivityshetkellä mahdollisesti Power Query -funktion avulla.
>
> Vähennä tarkkuus tasolle, joka on hyväksyttävä päivitystaajuutta koskevien vaatimustesi mukaisesti.
>
> Määritä mukautettu kysely tietojen muutosten havaitsemiseksi XMLA-päätepisteen avulla ja vältä sarakearvon säilyttäminen kokonaan. Saat lisätietoja alla olevasta Tietojen muutosten havaitseminen mukautetuilla kyselyillä -kohdasta.

#### <a name="only-refresh-complete-periods"></a>Vain täysien jaksojen päivittäminen

Oletetaan, että päivitys on ajoitettu suoritettavaksi klo 4.00 joka aamu. Jos lähdejärjestelmässä esiintyy tietoja kyseisten neljän tunnin aikana, et ehkä halua ottaa niitä huomioon. Jotkin liiketoiminnan mittarit – esimerkiksi barrelit päivässä öljy- ja kaasunalalla – eivät ole mielekkäitä, kun kyseessä ovat osittaiset päivät.

Toinen esimerkki on taloushallinnon järjestelmän tietojen päivittäminen, kun edellisen kuukauden tiedot hyväksytään kuun 12. päivänä. Voit määrittää lisäävän alueen yhdelle kuukaudelle ja ajoittaa päivityksen suoritettavaksi kuukauden 12. päivänä. Kun tämä vaihtoehto on valittuna, esimerkiksi tammikuun tiedot päivitettäisiin 12. helmikuuta.

![Täydet jaksot](media/service-premium-incremental-refresh/complete-periods.png)

> [!NOTE]
> Palvelun päivitystoiminnot suoritetaan UTC-ajan mukaan. Tämä voi määrittää voimaantulopäivän ja vaikuttaa täysiin jaksoihin. Mahdollisuus ohittaa päivitystoiminnon voimaantulopäivä aiotaan lisätä.

## <a name="publish-to-the-service"></a>Palveluun julkaiseminen

Voit nyt päivittää mallin. Ensimmäinen päivitys saattaa kestää kauemmin historiatietojen tuomisen vuoksi. Myöhemmät päivitykset voivat olla paljon nopeampia, koska niissä käytetään lisäävää päivitystä.

## <a name="query-timeouts"></a>Kyselyn aikakatkaisut

[Vianmäärityksen päivitys](refresh-troubleshooting-refresh-scenarios.md) -artikkelissa kerrotaan, että Power BI -palvelussa päivitystoiminnot voidaan aikakatkaista. Tietolähteen oletusaikakatkaisu voi myös rajoittaa kyselyjä. Useimmat suhteelliset lähteet sallivat aikakatkaisujen ohittamisen M-lausekkeessa. Esimerkiksi alla olevassa lausekkeessa sen kestoksi määritetään kaksi tuntia [SQL Serverin tietojen käytön funktion](https://docs.microsoft.com/powerquery-m/sql-database) avulla. Kukin käytäntöalueiden määrittämä jakso lähettää kyselyn, joka noudattaa komennon aikakatkaisua.

```powerquery-m
let
    Source = Sql.Database("myserver.database.windows.net", "AdventureWorks", [CommandTimeout=#duration(0, 2, 0, 0)]),
    dbo_Fact = Source{[Schema="dbo",Item="FactInternetSales"]}[Data],
    #"Filtered Rows" = Table.SelectRows(dbo_Fact, each [OrderDate] >= RangeStart and [OrderDate] < RangeEnd)
in
    #"Filtered Rows"
```

## <a name="xmla-endpoint-benefits-for-incremental-refresh"></a>XLMA-päätepisteiden edut lisäävässä päivityksessä

Premium-kapasiteetin tietojoukkojen [XMLA-päätepisteessä](service-premium-connect-tools.md) voidaan ottaa käyttöön luku- ja kirjoitustoiminnot. Tämä voi tarjota merkittäviä etuja lisääville päivityksille. XMLA-päätepisteen kautta suoritettuja päivitystoimintoja ei ole rajoitettu [48 päivitykseen päivässä](refresh-data.md#data-refresh) eikä [ajoitettujen päivitysten aikakatkaisua](refresh-troubleshooting-refresh-scenarios.md#scheduled-refresh-timeout) käytetä. Tästä voi olla hyötyä lisäävien päivitysten tilanteissa.

### <a name="refresh-management-with-sql-server-management-studio-ssms"></a>Päivitysten hallinta SQL Server Management Studiolla (SSMS)

Kun XMLA-päätepisteen luku- ja kirjoitustoiminnot ovat käytössä, SSMS:llä voidaan tarkastella ja hallita osioita, jotka luodaan lisäävän päivityksen käytännöillä.

![Osiot SSMS:ssä](media/service-premium-incremental-refresh/ssms-partitions.png)

#### <a name="refresh-historical-partitions"></a>Päivitysten historialliset osiot

Tällä tavalla voidaan esimerkiksi päivittää tietty historiallinen osio, joka ei ole lisäävällä alueella. Näin voidaan suorittaa takautuvat päivitys ilman kaikkien historiallisten tietojen päivitystä.

#### <a name="override-incremental-refresh-behavior"></a>Lisäävän päivityksen toiminnan kumoaminen

SSMS:n avulla voit hallita paremmin, miten lisääviä päivityksiä kutsutaan [TMSL:n (taulukkomallin komentosarjakieli, Tabular Model Scripting Language)](https://docs.microsoft.com/analysis-services/tmsl/tabular-model-scripting-language-tmsl-reference?view=power-bi-premium-current) ja [TOM:n (taulukko-objektimalli, Tabular Object Model)](https://docs.microsoft.com/analysis-services/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo?view=power-bi-premium-current) avulla. Napsauta esimerkiksi SSMS:n Object Explorerissa taulukkoa hiiren kakkospainikkeella ja valitse sitten valikosta **Process Table**. Luo sitten TMSL-päivityskomento napsauttamalla **Script**-painiketta.

![Process Table -valintaikkunan Script-painike](media/service-premium-incremental-refresh/ssms-process-table.png)

Voit lisätä TMSL-päivityskomentoon seuraavat parametrit, joilla voit kumota lisäävän päivityksen oletustoiminnan.

- **applyRefreshPolicy**: Jos taulukolle on määritetty lisäävän päivityksen käytäntö, applyRefreshPolicy määrittää, käytetäänkö sitä vai ei. Jos käytäntöä ei käytetä, prosessin koko toiminto jättää osion määritelmät muuttumatta, jolloin taulukon kaikki osiot päivitetään täysin. Oletusarvo on true.

- **effectiveDate**: Jos lisäävän päivityksen käytäntöä käytetään, sen täytyy tietää nykyinen päivämäärä, jotta se voi tarkistaa muuttuvat aikavälit historiallisille aikaväleille ja lisäävän aikavälin. effectiveDate-parametrillä voit kumota nykyisen päivämäärän. Tästä on hyötyä testauksessa, demoissa ja käyttötarkoituksissa, joissa tietoja päivitetään lisäävästi tiettyyn menneeseen tai tulevaan päivään saakka (esimerkiksi tulevat budjetit). Oletusarvo on [nykyinen päivämäärä](#current-date).

```json
{ 
  "refresh": {
    "type": "full",

    "applyRefreshPolicy": true,
    "effectiveDate": "12/31/2013",

    "objects": [
      {
        "database": "IR_AdventureWorks", 
        "table": "FactInternetSales" 
      }
    ]
  }
}
```

### <a name="custom-queries-for-detect-data-changes"></a>Tietojen muutosten havaitseminen mukautetuilla kyselyillä

TMSL:n ja/tai TOM:n avulla voit kumota tunnistettujen tietomuutosten toiminnan. Tällä voit paitsi välttää säilyttämästä viimeisimmän päivityksen saraketta välimuistissa, mutta myös hyödyntää käyttötilanteita, joissa määritys tai ohjetaulukko valmistellaan ETL-prosesseilla merkitsemään vain ne osiot, jotka täytyy päivittää. Tällä tavalla voidaan luoda tehokkaampi lisäävän päivityksen prosessi, jossa vain vaadittavat jaksot päivitetään riippumatta siitä, kuinka pitkä aika tietojen päivittämisestä on.

pollingExpression-lausekkeen tulisi olla kevyt M-lauseke tai toisen M-kyselyn nimi. Sen täytyy palauttaa skalaariarvo ja se suoritetaan jokaiselle osiolle. Jos arvo palautti eri arvon kuin edellisen lisäävän päivityksen yhteydessä, osio merkitään täyttä käsittelyä varten.

Seuraava esimerkki kattaa kaikki 120 kuukautta historialliselta ajanjaksolta takautuville muutoksille. 120 kuukauden määrittäminen 10 vuoden asemesta tarkoittaa sitä, että tietojen pakkaus ei ole ehkä yhtä tehokasta, mutta tällä tavalla voidaan välttää koko historiallisen vuoden päivittäminen, mikä olisi työläämpää, kun yhden kuukauden päivittäminen riittää takautuvalle muutokselle.

```json
"refreshPolicy": {
    "policyType": "basic",
    "rollingWindowGranularity": "month",
    "rollingWindowPeriods": 120,
    "incrementalGranularity": "month",
    "incrementalPeriods": 120,
    "pollingExpression": "<M expression or name of custom polling query>",
    "sourceExpression": [
    "let ..."
    ]
}
```

## <a name="metadata-only-deployment"></a>Pelkkien metatietojen käyttöönotto

Kun julkaiset PBIX-tiedoston uuden version Power BI Desktopista Power BI -palvelun työtilaan ja samanniminen tietojoukko on jo olemassa, sinua kehotetaan korvaamaan olemassa oleva tietojoukko.

![Korvaa tietojoukko -kehote](media/service-premium-incremental-refresh/replace-dataset-prompt.png)

Joissakin tapauksissa et ehkä halua korvata tietojoukkoa, varsinkaan lisäävän päivityksen yhteydessä. Power BI Desktopin tietojoukko voi olla paljon pienempi kuin palvelussa. Jos palvelun tietojoukossa on käytössä lisäävän päivityksen käytäntö, se voi sisältää useiden vuosien historiallisia tietoja, jotka menetät, jos korvaat tietojoukon. Kaikkien historiallisten tietojen päivittäminen voi kestää tunteja ja aiheuttaa käyttäjille järjestelmän käyttökatkoja.

Sen sijaan on parempi suorittaa vain metatietojen käyttöönotto. Tällä tavalla voit ottaa käyttöön uudet objektit menettämättä historiallisia tietoja. Jos olet esimerkiksi lisännyt joitain mittareita, voit ottaa käyttöön vain ne ilman tietojen päivitystä, mikä säästää paljon aikaa.

Kun XMLA-päätepiste on määritetty kirjoitus- ja lukutoiminnoille, se tarjoaa yhteensopivuuden sellaisille työkaluille, joilla tämä on mahdollista. ALM Toolkit esimerkiksi on rakenne-eroavaisuustyökalu Power BI -tietojoukoille: sillä voit ottaa käyttöön pelkät metatiedot.

Lataa ja asenna ALM Toolkitin uusin versio [Analysis Services Git -säilöstä](https://github.com/microsoft/Analysis-Services/releases). Käyttöohjeiden linkit ja tiedot tuesta ovat saatavilla Ohje-valintanauhan kautta. Jos haluat suorittaa pelkkien metatietojen käyttöönoton, suorita vertailu ja valitse lähteeksi käynnissä oleva Power BI -esiintymä ja kohteeksi olemassa oleva tietojoukko palvelussa. Ota huomioon näytetyt erot ja ohita lisäävän päivityksen osiot sisältävän taulukon päivitys. Asetusten valintaikkunassa voit myös säilyttää osiot taulukkopäivityksille. Vahvista valinta ja varmista kohdemallin eheys. Suorita sitten päivitys.

![ALM Toolkit](media/service-premium-incremental-refresh/alm-toolkit.png)

## <a name="see-also"></a>Muuta aiheeseen liittyvää

[Tietojoukon liitettävyys XMLA-päätepisteeseen](service-premium-connect-tools.md)   
[Päivitystilanteiden vianmääritys](refresh-troubleshooting-refresh-scenarios.md)   
