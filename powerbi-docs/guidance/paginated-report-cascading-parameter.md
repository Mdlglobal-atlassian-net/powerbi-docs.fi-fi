---
title: Johdannaisparametrien käyttö sivutetuissa raporteissa
description: Ohjeita sivutettujen raporttien suunnitteluun johdannaisparametrien avulla.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: v-pemyer
ms.openlocfilehash: 90f501b257313c48cbef13517747ff83cd9ea9d1
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "78920777"
---
# <a name="use-cascading-parameters-in-paginated-reports"></a>Johdannaisparametrien käyttö sivutetuissa raporteissa

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee Power BI:n [sivutettuja raportteja](../paginated-reports/paginated-reports-report-builder-power-bi.md). Se tarjoaa skenaarioita johdannaisparametrien suunnittelemiseksi. Johdannaisparametrit ovat raportin parametreja, joilla on riippuvuussuhteita. Kun raportin käyttäjä valitsee parametrin arvon (tai arvot), sen avulla voidaan määrittää toisen parametrin käytettävissä olevat arvot.

> [!NOTE]
> Tässä artikkelissa ei esitellä johdannaisparametreja eikä niiden määrittämistä. Jos et ole tutustunut hyvin johdannaisparametreihin, suosittelemme, että luet ensin artikkelin [Johdannaisparametrien lisääminen raporttiin (Raportin muodostin ja SSRS)](/sql/reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs).

## <a name="design-scenarios"></a>Suunnitteluskenaariot

Johdannaisparametrien käyttämiseen on kaksi suunnitteluskenaariota. Niitä voidaan käyttää tehokkaasti:

- _suurien kohdejoukkojen_ suodattamiseen,
- _olennaisten_ kohteiden esittämiseen.

### <a name="example-database"></a>Esimerkki tietokannasta

Tämän artikkelin esimerkit perustuvat Azuren SQL -tietokantaan. Tietokanta kirjaa myyntitoiminnot ja sisältää erilaisia taulukoita, jotka tallentavat jälleenmyyjiä, tuotteita ja myyntitilauksia.

Taulukko nimeltä **Reseller** tallentaa kullekin jälleenmyyjälle yhden tietueen ja sisältää useita tuhansia tietueita. **Reseller**-taulukossa on seuraavat sarakkeet:

- ResellerCode (kokonaisluku)
- ResellerName
- Maa tai alue
- State-Province
- Kaupunki
- Postinumero

Löydät täältä myös **Sales**-nimisen sarakkeen. Se tallentaa myyntitilaustietueet ja sillä on viiteavainsuhde **Reseller**-taulukkoon **ResellerCode**-sarakkeessa.

### <a name="example-requirement"></a>Esimerkki vaatimuksesta

Jälleenmyyjän profiilia käsittelevän raportin laatimista vaaditaan. Raportti on suunniteltava siten, että se näyttää yksittäisen jälleenmyyjän tiedot. Ei ole asianmukaista, että raportin käyttäjä syöttää jälleenmyyjän koodin, koska hän harvoin muistaa sitä.

## <a name="filter-large-sets-of-items"></a>Suurien kohdejoukkojen suodattaminen

Tarkastellaanpa kolmea esimerkkiä, joiden avulla voit rajoittaa suurten käytettävissä olevien kohteiden joukkoa, kuten jälleenmyyjiä. Ne ovat seuraavat:

- [Suodata aiheeseen liittyvien sarakkeiden mukaan](#filter-by-related-columns)
- [Suodata ryhmittelysarakkeen mukaan](#filter-by-a-grouping-column)
- [Suodata hakumallin mukaan](#filter-by-search-pattern)

### <a name="filter-by-related-columns"></a>Suodata aiheeseen liittyvien sarakkeiden mukaan

Tässä esimerkissä raportin käyttäjä soveltaa viittä raportin parametria. Käyttäjän on valittava maa tai alue, osavaltio tai maakunta, kaupunki ja postinumero. Viimeisessä parametrissa luetellaan jälleenmyyjät, jotka asuvat kyseisessä maantieteellisessä sijainnissa.

![Kuvassa näytetään viisi raportin parametria: Country-region, State-province, City, Postal Code ja Reseller. Ensimmäisissä neljässä parametrissa on määritetyt arvot, ja jälleenmyyntiluettelo suodatetaan vain neljään kohteeseen.](media/paginated-report-cascading-parameter/filter-by-related-columns-example.png)

Voit kehittää johdannaisparametreja seuraavasti:

1. Luo viisi raportin parametria, jotka on asetettu oikeaan järjestykseen.
2. Luo **CountryRegion**-tietojoukko, joka hakee erilliset maa- tai aluearvot, käyttämällä seuraavaa kyselylauseketta:

    ```sql
    SELECT DISTINCT
      [Country-Region]
    FROM
      [Reseller]
    ORDER BY
      [Country-Region]
    ```

3. Luo **StateProvince**-tietojoukko, joka hakee valitun maan tai alueen erilliset osavaltio- tai maakunta-arvot, käyttämällä seuraavaa kyselylauseketta:

    ```sql
    SELECT DISTINCT
      [State-Province]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
    ORDER BY
      [State-Province]
    ```

4. Luo **City**-tietojoukko, joka hakee valitun maan tai alueen erilliset kaupunkiarvot, käyttämällä seuraavaa kyselylauseketta:

    ```sql
    SELECT DISTINCT
      [City]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
      AND [State-Province] = @StateProvince
    ORDER BY
      [City]
    ```

5. Luo saman mallin avulla **PostalCode**-tietojoukko.
6. Luo **Reseller**-tietojoukko, jotta voit hakea valittujen maantieteellisten arvojen kaikki jälleenmyyjät, käyttämällä seuraavaa kyselylauseketta:

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      [Country-Region] = @CountryRegion
      AND [State-Province] = @StateProvince
      AND [City] = @City
      AND [PostalCode] = @PostalCode
    ORDER BY
      [ResellerName]
    ```

7. Määritä kullekin tietojoukolle ensimmäistä lukuun ottamatta kyselyparametrit vastaaville raportin parametreille.

> [!NOTE]
> Kaikki näissä esimerkeissä näytetyt kyselyparametrit (edessä @-symboli) voidaan upottaa SELECT-lausekkeisiin tai välittää tallennettuihin toimintosarjoihin.
>
> Yleensä suunnittelussa kannattaa käyttää tallennettuja toimintosarjoja. Se johtuu siitä, että niiden kyselysuunnitelmat on tallennettu välimuistiin nopeampaa suoritusta varten, ja voit niiden avulla kehittää edistyneempää logiikkaa tarvittaessa. Niitä ei kuitenkaan tällä hetkellä tueta yhdyskäytävään liittyviä tietolähteitä (SQL Server, Oracle ja Teradata) varten.
>
> Lopuksi on aina varmistettava, että käytössä on sopivat indeksit, jotta tiedot haetaan tehokkaasti. Muuten raportin parametrien täyttäminen voi olla hidasta, ja tietokanta voi ylikuormittua. Lisätietoja SQL Server -indeksoinnista on kohdassa [SQL Server -indeksin arkkitehtuuri- ja suunnitteluopas](/sql/relational-databases/sql-server-index-design-guide?view=sql-server-2017).

### <a name="filter-by-a-grouping-column"></a>Suodata ryhmittelysarakkeen mukaan

Tässä esimerkissä raportin käyttäjä soveltaa raportin parametria jälleenmyyjän ensimmäisen kirjaimen valitsemiseksi. Toinen parametri luettelee sitten jälleenmyyjät, kun nimi alkaa valitulla kirjaimella.

![Kuvassa näytetään kaksi raportin parametria: Group ja Reseller. Ensimmäisen parametrin arvoksi on määritetty kirjain A, ja Reseller-luettelo on suodatettu moneen kohteeseen, jotka alkavat tällä kirjaimella.](media/paginated-report-cascading-parameter/filter-by-grouping-column-example.png)

Voit kehittää johdannaisparametreja seuraavasti:

1. Luo **ReportGroup**- ja **Reseller**-raportin parametrit, jotka on asetettu oikeaan järjestykseen.
2. Luo **ReportGroup**-tietojoukko, jotta voit hakea kaikkien jälleenmyyjien käyttämät ensimmäiset kirjaimet, käyttämällä seuraavaa kyselylauseketta:

    ```sql
    SELECT DISTINCT
      LEFT([ResellerName], 1) AS [ReportGroup]
    FROM
      [Reseller]
    ORDER BY
      [ReportGroup]
    ```

3. Luo **Reseller**-tietojoukko, jotta voit hakea valitulla kirjaimella alkavat kaikki jälleenmyyjät, käyttämällä seuraavaa kyselylauseketta:

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      LEFT([ResellerName], 1) = @ReportGroup
    ORDER BY
      [ResellerName]
    ```

4. Yhdistä **Reseller**-tietojoukon kyselyparametri vastaavaan raportin parametriin.

Ryhmittelysarake kannattaa lisätä **Reseller**-taulukkoon. Kun se on jatkuva ja indeksoitu, se tuottaa parhaan tuloksen. Jos haluat lisätietoja, lue artikkeli [Määritä lasketut sarakkeet taulukossa](/sql/relational-databases/tables/specify-computed-columns-in-a-table).

```sql
ALTER TABLE [Reseller]
ADD [ReportGroup] AS LEFT([ResellerName], 1) PERSISTED
```

Tämä tekniikka voi tarjota vieläkin parempia tuloksia. Harkitse seuraavaa komentosarjaa, joka lisää uuden ryhmittelysarakkeen jälleenmyyjien suodattamiseksi _esimääritettyjen kirjainjoukkojen mukaan_. Se luo myös indeksin, joka hakee tehokkaasti raportin parametrien edellyttämät tiedot.

```sql
ALTER TABLE [Reseller]
ADD [ReportGroup2] AS CASE
  WHEN [ResellerName] LIKE '[A-C]%' THEN 'A-C'
  WHEN [ResellerName] LIKE '[D-H]%' THEN 'D-H'
  WHEN [ResellerName] LIKE '[I-M]%' THEN 'I-M'
  WHEN [ResellerName] LIKE '[N-S]%' THEN 'N-S'
  WHEN [ResellerName] LIKE '[T-Z]%' THEN 'T-Z'
  ELSE '[Other]'
END PERSISTED
GO

CREATE NONCLUSTERED INDEX [Reseller_ReportGroup2]
ON [Reseller] ([ReportGroup2]) INCLUDE ([ResellerCode], [ResellerName])
GO
```

### <a name="filter-by-search-pattern"></a>Suodata hakumallin mukaan

Tässä esimerkissä raportin käyttäjä soveltaa raportin parametria hakumallin syöttämiseksi. Toinen parametri luettelee sitten jälleenmyyjät, kun nimi sisältää mallin.

![Kuvassa näytetään kaksi raportin parametria: Search ja Reseller. Ensimmäisen parametrin arvoksi on määritetty teksti ”red” ja Reseller-luettelo on suodatettu moneen kohteeseen, jotka sisältävät tämän tekstin.](media/paginated-report-cascading-parameter/filter-by-search-pattern-example.png)

Voit kehittää johdannaisparametreja seuraavasti:

1. Luo **Search**- ja **Reseller**-raportin parametrit, jotka on asetettu oikeaan järjestykseen.
2. Luo **Reseller**-tietojoukko, jotta voit hakea hakutekstin sisältävät kaikki jälleenmyyjät, käyttämällä seuraavaa kyselylauseketta:

    ```sql
    SELECT
      [ResellerCode],
      [ResellerName]
    FROM
      [Reseller]
    WHERE
      [ResellerName] LIKE '%' + @Search + '%'
    ORDER BY
      [ResellerName]
    ```

3. Yhdistä **Reseller**-tietojoukon kyselyparametri vastaavaan raportin parametriin.

> [!TIP]
> Tämän mallin avulla voit tarjota raportin käyttäjille parempia hallintatyökaluja. Sen avulla he voivat määrittää arvon täsmäyttämistä koskevan oman mallinsa. Esimerkiksi hakuarvo ”red%” suodattaa jälleenmyyjiin, joiden nimet _alkavat_ merkeillä ”red”.
>
> Lisätietoja on kohdassa [LIKE (Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql?view=sql-server-ver15#using-the--wildcard-character).

Voit näin antaa raportin käyttäjien määrittää oman mallinsa.

```sql
WHERE
  [ResellerName] LIKE @Search
```

Monet käyttäjät, jotka eivät ole tietokanta-ammattilaisia, eivät kuitenkaan tunne prosenttiosuuden (%) yleismerkkiä vaan sen sijaan tähtimerkin (*). Muokkaamalla WHERE-lausetta mahdollistat sen, että he voivat käyttää tätä merkkiä.

```sql
WHERE
  [ResellerName] LIKE SUBSTITUTE(@Search, '%', '*')
```

## <a name="present-relevant-items"></a>Olennaisten kohteiden esittäminen

Tässä skenaariossa voit käyttää faktatietoja käytettävissä olevien arvojen rajaamiseen. Raportin käyttäjille esitetään kohteet, joissa toiminta on tallennettu.

Tässä esimerkissä raportin käyttäjä soveltaa kolmea raportin parametria. Kaksi ensimmäistä joukkoa määrittää myyntitilausten päivämäärien päivämääräalueen. Kolmas parametri luettelee jälleenmyyjät, jotka ovat tehneet tilauksia kyseisenä aikajaksona.

![Kuvassa näytetään kolme raportin parametria: Start Order Date, End Order Date ja Reseller. Kaksi päivämääräparametria on määritetty tammikuulle 2020 ja Reseller-luettelo suodatetaan useisiin kohteisiin. Ne edustavat jälleenmyyjiä, jotka ovat tehneet tilauksia tämän kuukauden aikana.](media/paginated-report-cascading-parameter/filter-relevant-items-example.png)

Voit kehittää johdannaisparametreja seuraavasti:

1. Luo **OrderDateStart**-, **OrderDateEnd**- ja **Reseller**-raportin parametrit, jotka on asetettu oikeaan järjestykseen.
2. Luo **Reseller**-tietojoukko, jotta voit hakea kaikki jälleenmyyjät, jotka loivat tilauksia päivämääräjaksolla, käyttämällä seuraavaa kyselylauseketta:

    ```sql
    SELECT DISTINCT
      [r].[ResellerCode],
      [r].[ResellerName]
    FROM
      [Reseller] AS [r]
    INNER JOIN [Sales] AS [s]
      ON [s].[ResellerCode] = [r].[ResellerCode]
    WHERE
      [s].[OrderDate] >= @OrderDateStart
      AND [s].[OrderDate] < DATEADD(DAY, 1, @OrderDateEnd)
    ORDER BY
      [r].[ResellerName]
    ```

## <a name="recommendations"></a>Suositukset

Suosittelemme, että suunnittelet raportit johdannaisparametrien avulla aina kun se on mahdollista. Tämä johtuu siitä, että:

- takaat näin raportin käyttäjille intuitiivisia ja hyödyllisiä kokemuksia,
- parametrit ovat tehokkaita, koska ne hakevat pienempiä käytettävissä olevien arvojen joukkoja.

Varmista, että optimoit tietolähteesi:

- käyttämällä tallennettuja toimintosarjoja aina kun se on mahdollista,
- lisäämällä asianmukaiset indeksit tietojen tehokkaaksi hakemiseksi,
- materialisoimalla sarakkeiden arvot – ja jopa rivit – kalliiden kyselyaika-arviointien välttämiseksi.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Raportin parametrit Power BI:n Raportin muodostimessa](../paginated-reports/report-builder-parameters.md)
- [Johdannaisparametrien lisääminen raporttiin (Raportin muodostin ja SSRS)](/sql/reporting-services/report-design/add-cascading-parameters-to-a-report-report-builder-and-ssrs)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com)
