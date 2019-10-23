---
title: DirectQueryn tukemat tietolähteet Power BI:ssä
description: Hanki luettelo tietolähteistä, jotka voivat käyttää DirectQueryä.
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/16/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: a9e8d2aaab7c0b3ed1daea32486260d09bc6f6a2
ms.sourcegitcommit: 83e1e162a037f352e542bd5c198a3c98f5db23c7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/17/2019
ms.locfileid: "72511646"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>{0}DirectQueryn tukemat tietolähteet Power BI:ssä

**Power BI Desktop** ja **Power BI -palvelu** sisältävät useita eri tietolähteitä, joihin voit yhdistää ja joiden tietoja voit päästä käyttämään. Tässä artikkelissa kuvataan, mitkä Power BI -tietolähteet tukevat yhteystapaa, joka tunnetaan nimellä **DirectQuery**. Katso lisätietoja DirectQuerystä kohdasta [ **DirectQuery Power BI:ssä**](desktop-directquery-about.md).

Seuraavat tietolähteet tukevat DirectQueryä Power BI:ssä:

* Amazon Redshift
* AtScale (Beta)
* Azure Data Explorer
* Azure HDInsight Spark
* [Azure SQL -tietokanta](service-azure-sql-database-with-direct-connect.md)
* [Azure SQL Data Warehouse](service-azure-sql-data-warehouse-with-direct-connect.md)
* Denodo
* Google BigQuery
* HDInsight Interactive Query
* IBM DB2 (Microsoft-palvelu)
* IBM Netezza
* Impala (versio 2.x)
* MarkLogic
* Oracle-tietokanta (versio 12 tai uudempi versio)
* Oracle Essbase
* PostgreSQL
* SAP Business Warehouse -sovelluspalvelin
* SAP Business Warehouse -viestipalvelin
* SAP HANA
* Snowflake
* Spark (versio 0.9 ja tätä uudemmat)
* SQL Server
* Teradata
* Vertica

Tietolähteet, joiden nimien perässä on **(beeta)** tai **(esikatselu)** , voivat muuttua, eikä niiden tuotantokäyttöä tueta. Niitä ei myöskään välttämättä tueta raportin julkaisemisen jälkeen **Power BI -palveluun**, mikä tarkoittaa sitä, että julkaistun raportin avaaminen tai tietojoukon tutkiminen voi aiheuttaa virheen.

Ainoa ero **(beeta)** - ja **(esikatselu)** -tietolähteiden välillä on se, että **(esikatselu)** -merkittyjen lähteiden on oltava käytössä esikatselutoimintoja, ennen kuin ne tulevat saataville käyttöä varten. Ota käyttöön **(esikatselu)** -tietoyhdistin **Power BI Desktopissa** valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset** ja valitsemalla sitten **Esikatselutoiminnot**.

> [!NOTE]
> SQL Serverille lähetettyjen DirectQuery-kyselyjen käyttö edellyttävää todennusta senhetkisillä Windows-todennuksen tunnistetiedoilla tai tietokannan tunnistetiedoilla. Vaihtoehtoisten tunnistetietojen käyttöä ei tueta.
>

## <a name="on-premises-gateway-requirements"></a>Paikallisen yhdyskäytävän vaatimukset
Seuraavassa taulukossa on määritetty, onko **Paikallinen tietoyhdyskäytävä** pakollinen muodostettaessa yhteys määritettyyn tietolähteeseen, raportin julkaisemisen jälkeen **Power BI -palveluun**.

| Lähde | Yhdyskäytävä tarvitaan? |
| --- | --- |
| Amazon Redshift |Ei |
| Azure HDInsight Spark (beeta) |Ei |
| Azuren SQL-tietokanta |Ei |
| Azure SQL Data Warehouse |Ei |
| Google BigQuery |Ei |
| IBM Netezza |Kyllä |
| IBM DB2 (IBM-palvelu) |Kyllä |
| IBM DB2 (Microsoft -palvelu) |Ei |
| IBM Informix -tietokanta |Ei |
| Impala (versio 2.x) |Kyllä |
| MySQL |Kyllä |
| ODBC |Kyllä |
| Oracle-tietokanta |Kyllä |
| PostgreSQL |Kyllä |
| SAP Business Warehouse -sovelluspalvelin |Kyllä |
| SAP Business Warehouse -viestipalvelin |Kyllä |
| SAP HANA |Kyllä |
| Snowflake |Kyllä |
| Spark (beeta), versio 0.9 tai uudempi versio |Kyllä |
| SQL Server |Kyllä |
| Sybase |Kyllä |
| Teradata |Kyllä |
| Vertica |Kyllä |


## <a name="single-sign-on-sso-for-directquery-sources"></a>DirectQuery-lähteiden kertakirjautuminen

Kun kertakirjautumisasetus on käytössä ja käyttäjät käyttävät raportteja, jotka on luotu tietolähteeseen, Power BI lähettää todennetut Azure AD -tunnistetiedot kyselyissä taustalla olevaan tietokantaan. Näin Power BI voi noudattaa tietoturva-asetuksia, jotka on määritetty tietolähteen tasolla.

Kertakirjautumisen asetus tulee voimaan kaikissa tietojoukoissa, jotka käyttävät tätä tietolähdettä. Se ei vaikuta tuontitilanteissa käytettyihin todentamismenetelmiin. Seuraavat tietolähteet tukevat DirectQueryn kertakirjautumisyhteyksiä:

- Azuren SQL-tietokanta
- Azure SQL Data Warehouse
- Impala
- SAP HANA
- SAP BW
- SAP BW Message Server (esiversio)
- Spark
- SQL Server
- Teradata

> [!Note]
> Azure Multi-Factor Authenticationia (MFA) ei tueta. Käyttäjät, jotka haluavat käyttää kertakirjautumista DirectQueryn kanssa, täytyy vapauttaa MFA:n käytöstä.

## <a name="next-steps"></a>Seuraavat vaiheet
Saat lisätietoja DirectQuerystä seuraavista resursseista:

* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)

