---
title: Lisäävää päivitys Power BI Premiumissa
description: Opi ottamaan käyttöön erittäin suuria tietojoukkoja Power BI Premium -palvelussa.
author: christianwade
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 04/30/2018
ms.author: chwade
LocalizationGroup: Premium
ms.openlocfilehash: 1b6a3c35abeff33e2fb1e0fecdc5c2a5c88e1530
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2018
---
# <a name="incremental-refresh-in-power-bi-premium"></a>Lisäävää päivitys Power BI Premiumissa

Lisäävä päivitys mahdollistaa erittäin suurien tietojoukkojen käytön Power BI Premium -palvelussa tarjoamalla seuraavat edut:

- **Päivitykset ovat entistä nopeampia.** Vain muuttuneet tiedot on päivitettävä. Päivitä esimerkiksi vain viimeiset 5 päivää 10 vuoden tietojoukosta.

- **Päivitykset ovat entistä luotettavampia.** Ei ole esimerkiksi tarpeen säilyttää pitkäkestoisia yhteyksiä lyhytkestoisiin lähdejärjestelmiin.

- **Resurssien kulutus on vähäisempää.** Kun päivitettäviä tietoja on vähemmän, muistin ja muiden resurssien yleinen kulutus on pienempi.

## <a name="how-to-use-incremental-refresh"></a>Lisäävän päivityksen käyttäminen

Lisäävän päivityksen käytännöt määritellään Power BI Desktopissa, ja ne otetaan käyttöön, kun ne on julkaistu Power BI -palvelussa.

Aloita ottamalla käyttöön lisäävän päivityksen esiversio-ominaisuudet.

![Asetukset – esiversiotoiminnot](media/service-premium-incremental-refresh/preview-features.png)

### <a name="filter-large-datasets-in-power-bi-desktop"></a>Suurien tietojoukkojen suodattaminen Power BI Desktopissa

Mahdollisesti miljardeja rivejä sisältävät suuret tietojoukot eivät välttämättä mahdu Power BI Desktopiin, koska normaalisti käyttäjän pöytätietokoneessa käytettävissä olevat resurssit rajoittavat sitä. Siksi tällaisia tietojoukkoja yleensä suodatetaan tuonnin yhteydessä, jotta ne mahtuvat Power BI Desktopiin. Näin on riippumatta siitä, käytetäänkö lisäävää päivitystä vai ei.

#### <a name="rangestart-and-rangeend-parameters"></a>RangeStart- ja RangeEnd-parametrit

Jos haluat hyödyntää lisäävää päivitystä Power BI -palvelussa, suodatuksessa on käytettävä Power Queryn päivämäärä/aika-parametreja siihen varatuilla, kirjainkooltaan merkitsevillä nimillä **RangeStart** ja **RangeEnd**.

Valitse Power Query -editorissa **Parametrien hallinta** ja määritä parametrit oletusarvoilla.

![Parametrien hallinta](media/service-premium-incremental-refresh/manage-parameters.png)

Kun parametrit on määritetty, voit käyttää suodatinta valitsemalla **Mukautettu suodatin** -valikkovaihtoehdon sarakkeessa.

![Mukautettu suodatin](media/service-premium-incremental-refresh/custom-filter.png)

Varmista, että rivit suodatetaan, kun sarakkeen arvo *on suurempi tai yhtä suuri kuin* **RangeStart** ja *pienempi kuin* **RangeEnd**.

![Rivien suodattaminen](media/service-premium-incremental-refresh/filter-rows.png)

> [!TIP]
> Vaikka parametrien tietotyypin on oltava päivämäärä/aika, ne on mahdollista muuntaa vastaamaan tietolähteen vaatimuksia. Esimerkiksi seuraava Power Query -funktio muuntaa päivämäärän/ajan arvon muistuttamaan tietovarastoissa yleisen muodon *vvvvkkpp* kokonaisluvun korvaavaa avainta. Funktio voidaan kutsua suodattimen vaiheen mukaan.
>
> `(x as datetime) => Date.Year(x)*10000 + Date.Month(x)*100 + Date.Day(x)`

Valitse **Sulje ja ota käyttöön** Power Query -editorissa. Sinulla pitäisi olla tietojoukon alijoukko Power BI Desktopissa.

> [!NOTE]
> Julkaisun jälkeen Power BI -palvelu ohittaa parametrin arvot automaattisesti. Niitä ei tarvitse määrittää ne tietojoukon asetuksissa.

### <a name="define-the-refresh-policy"></a>Päivityskäytännön määrittäminen

Lisäävä päivitys on käytettävissä taulukoiden pikavalikossa lukuun ottamatta reaaliaikaisen yhteyden malleja.

![Päivityskäytäntö](media/service-premium-incremental-refresh/refresh-policy.png)

#### <a name="incremental-refresh-dialog"></a>Lisäävä päivitys -valintaikkuna

Lisäävä päivitys -valintaikkuna tulee näkyviin. Ota valintaikkuna käyttöön vaihtopainikkeella.

![Päivitystiedot](media/service-premium-incremental-refresh/refresh-details.png)

> [!NOTE]
> Jos taulukon Power Query -lauseke ei viittaa parametreihin, joilla on varatut nimet, vaihtopainike on poistettu käytöstä.

Otsikkoteksti kertoo seuraavaa:

-   Lisäävää päivitystä tuetaan vain Premium-kapasiteetin työtiloissa. Päivityskäytännöt määritetään Power BI Desktopissa; palvelun päivitystoiminnot käyttävät niitä.

-   Jos et pysty lataamaan lisäävän päivityskäytännön sisältävää PBIX-tiedostoa Power BI-palvelusta, se ei avaudu Power BI Desktopissa. Pian et voi ladata sitä ollenkaan. Vaikka tätä saatetaan tukea tulevaisuudessa, huomaa, että tietojoukot voivat kasvaa niin suuriksi, että niitä on hankala ladata ja avata tavallisella pöytätietokoneella.

#### <a name="refresh-ranges"></a>Päivitysalueet

Seuraavassa esimerkissä määritetään päivityskäytäntö tallentamaan yhteensä 5 vuoden tiedot ja päivittämään asteittain 10 päivän tiedot. Jos tietojoukko päivitetään päivittäin, kunkin päivitystoiminnon osalta suoritetaan seuraavat.

-   Lisää uusi tietopäivä.

-   Päivitä 10 päivää nykyiseen päivämäärään saakka.

-   Poista kalenterivuodet, jotka ovat aikaisempia kuin 5 vuotta ennen nykyistä päivämäärää. Esimerkiksi jos nykyinen päivämäärä on 1.1.2019, vuosi 2013 poistetaan.

Power BI -palvelun ensimmäinen päivitys saattaa kestää kauemmin kaikkien viiden vuoden tuomiseksi. Myöhemmät päivitykset saattavat viedä vain hetken.

![Päivitysalueet](media/service-premium-incremental-refresh/refresh-ranges.png)

**Alueiden määritys saattaa olla ainoa asia, mitä sinun tarvitsee tehdä, jolloin voit siirtyä suoraan alla olevaan julkaisuvaiheeseen. Muut avattavat valikot on tarkoitettu kehittyneille ominaisuuksille.**

#### <a name="detect-data-changes"></a>Tietojen muutosten havaitseminen

10 päivän lisäävä päivitys on luonnollisesti paljon tehokkaampi kuin 5 vuoden koko päivitys. Tehokkuutta on kuitenkin mahdollista lisätä entisestään. Jos valitset **Havaitse tietojen muutokset** -valintaruudun, voit valita päivämäärä/aika-sarakkeen, jonka avulla tunnistetaan ja päivitetään vain päivät, joiden tiedot ovat muuttunut. Tällöin oletetaan, että lähdejärjestelmässä on kyseinen sarake, joka on yleensä valvontaa varten. Tämän sarakkeen suurin arvo lasketaan jokaisen lisäävän alueen ajanjakson osalta. Jos arvo ei ole muuttunut viimeisen päivityksen jälkeen, ajanjaksoa ei tarvitse päivittää. Esimerkissä asteittain päivitettävien päivien määrä voisi vähentyä kymmenestä ehkä kahteen.

![Muutosten havaitseminen](media/service-premium-incremental-refresh/detect-changes.png)

> [!TIP]
> Nykyinen rakenne edellyttää, että sarake on pysyvä ja tallennettu välimuistiin tietojen muutosten havaitsemiseksi. Kannattaa harkita jotakin seuraavista tekniikoista kardinaliteetin ja muistin kulutuksen vähentämiseksi.
>
> Säilytä vain sarakkeen suurin arvo päivityshetkellä mahdollisesti Power Query -funktion avulla.
>
> Vähennä tarkkuus tasolle, joka on hyväksyttävä päivitystaajuutta koskevien vaatimustesi mukaisesti.
>
> Mukautettujen kyselyjen määrittäminen tietojen muutosten havaitsemiseksi aiotaan sallia myöhemmin. Tällöin voidaan välttää kaikkien sarakkeen arvojen säilyttäminen.

#### <a name="only-refresh-complete-periods"></a>Vain täysien jaksojen päivittäminen

Oletetaan, että päivitys on ajoitettu suoritettavaksi klo 4.00 joka aamu. Jos lähdejärjestelmässä esiintyy tietoja kyseisten neljän tunnin aikana, et ehkä halua ottaa niitä huomioon. Jotkin liiketoiminnan mittarit – esimerkiksi barrelit päivässä öljy- ja kaasunalalla – eivät ole mielekkäitä, kun kyseessä ovat osittaiset päivät.

Toinen esimerkki on taloushallinnon järjestelmän tietojen päivittäminen, kun edellisen kuukauden tiedot hyväksytään kuun 12. päivänä. Voit määrittää lisäävän alueen yhdelle kuukaudelle ja ajoittaa päivityksen suoritettavaksi kuukauden 12. päivänä. Kun tämä vaihtoehto on valittuna, esimerkiksi tammikuun tiedot päivitettäisiin 12. helmikuuta.

![Täydet jaksot](media/service-premium-incremental-refresh/complete-periods.png)

> [!NOTE]
> Palvelun päivitystoiminnot suoritetaan UTC-ajan mukaan. Tämä voi määrittää voimaantulopäivän ja vaikuttaa täysiin jaksoihin. Mahdollisuus ohittaa päivitystoiminnon voimaantulopäivä aiotaan lisätä.

## <a name="publish-to-the-service"></a>Palveluun julkaiseminen

Koska lisäävä päivitys on vain Premium-kapasiteetin ominaisuus, Julkaise-valintaikkunassa voidaan valita vain Premium-kapasiteetin työtila.

![Palveluun julkaiseminen](media/service-premium-incremental-refresh/publish.png)

Voit nyt päivittää mallin. Ensimmäinen päivitys saattaa kestää kauemmin historiatietojen tuomisen vuoksi. Myöhemmät päivitykset voivat olla paljon nopeampia, koska niissä käytetään lisäävää päivitystä.

## <a name="query-timeouts"></a>Kyselyn aikakatkaisut

[Vianmäärityksen päivitys](https://docs.microsoft.com/power-bi/refresh-troubleshooting-refresh-scenarios) -artikkelissa kerrotaan, että Power BI -palvelussa päivitystoiminnot voidaan aikakatkaista. Tietolähteen oletusaikakatkaisu voi myös rajoittaa kyselyjä. Useimmat suhteelliset lähteet sallivat aikakatkaisujen ohittamisen M-lausekkeessa. Esimerkiksi alla olevassa lausekkeessa sen kestoksi määritetään kaksi tuntia [SQL Serverin tietojen käytön funktion](https://msdn.microsoft.com/query-bi/m/sql-database) avulla. Kukin käytäntöalueiden määrittämä jakso lähettää kyselyn, joka noudattaa komennon aikakatkaisua.

```
let
    Source = Sql.Database("myserver.database.windows.net", "AdventureWorks", [CommandTimeout=#duration(0, 2, 0, 0)]),
    dbo_Fact = Source{[Schema="dbo",Item="FactInternetSales"]}[Data],
    #"Filtered Rows" = Table.SelectRows(dbo_Fact, each [OrderDate] >= RangeStart and [OrderDate] < RangeEnd)
in
    #"Filtered Rows"
```
