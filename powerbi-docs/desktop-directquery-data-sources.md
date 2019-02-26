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
ms.date: 11/01/2018
LocalizationGroup: Connect to data
ms.openlocfilehash: 84e40e9fbce07716a2250a58bfcbd396a40d2842
ms.sourcegitcommit: 796bf513bf8669676e2a44627b56221b1629a6a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/26/2019
ms.locfileid: "56826556"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>{0}DirectQueryn tukemat tietolähteet Power BI:ssä

**Power BI Desktop** ja **Power BI -palvelu** sisältävät useita eri tietolähteitä, joihin voit yhdistää ja joiden tietoja voit päästä käyttämään. Tässä artikkelissa kuvataan, mitkä Power BI -tietolähteet tukevat yhteystapaa, joka tunnetaan nimellä **DirectQuery**. Katso lisätietoja DirectQuerystä kohdasta [ **DirectQuery Power BI:ssä**](desktop-directquery-about.md).

Seuraavat tietolähteet tukevat DirectQueryä Power BI:ssä:

* Amazon Redshift
* Azure HDInsight Spark (beeta)
* Azure SQL -tietokanta
* Azure SQL Data Warehouse
* Google BigQuery (beeta)
* IBM DB2 -tietokanta
* IBM Netezza (beeta)
* Impala (versio 2.x)
* Oracle-tietokanta (versio 12 tai uudempi versio)
* SAP Business Warehouse -sovelluspalvelin
* SAP Business Warehouse -viestipalvelin (beeta)
* SAP HANA
* Snowflake
* Spark (beeta) (versio 0.9 tai uudempi versio)
* SQL Server
* Teradata-tietokanta
* Vertica (beeta)

Tietolähteet, joiden nimien perässä on **(beeta)** tai **(esikatselu)**, voivat muuttua, eikä niiden tuotantokäyttöä tueta. Niitä ei myöskään välttämättä tueta raportin julkaisemisen jälkeen **Power BI -palveluun**, mikä tarkoittaa sitä, että julkaistun raportin avaaminen tai tietojoukon tutkiminen voi aiheuttaa virheen.

Ainoa ero **(beeta)**- ja **(esikatselu)**-tietolähteiden välillä on se, että **(esikatselu)**-merkittyjen lähteiden on oltava käytössä esikatselutoimintoja, ennen kuin ne tulevat saataville käyttöä varten. Ota käyttöön **(esikatselu)**-tietoyhdistin **Power BI Desktopissa** valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset** ja valitsemalla sitten **Esikatselutoiminnot**.

> [!NOTE]
> SQL Serverille lähetettyjen DirectQuery-kyselyjen käyttö edellyttävää todennusta senhetkisillä Windows-todennuksen tunnistetiedoilla tai tietokannan tunnistetiedoilla. Vaihtoehtoisten tunnistetietojen käyttöä ei tueta.
>

## <a name="on-premises-gateway-requirements"></a>Paikallisen yhdyskäytävän vaatimukset
Seuraavassa taulukossa on määritetty, onko **Paikallinen tietoyhdyskäytävä** pakollinen muodostettaessa yhteys määritettyyn tietolähteeseen, raportin julkaisemisen jälkeen **Power BI -palveluun**.

| Lähde | Yhdyskäytävä tarvitaan? |
| --- | --- |
| SQL Server |Kyllä |
| Azure SQL -tietokanta |Ei |
| Azure SQL Data Warehouse |Ei |
| SAP HANA |Kyllä |
| Oracle-tietokanta |Kyllä |
| Teradata-tietokanta |Kyllä |
| Amazon Redshift |Ei |
| Impala (versio 2.x) |Kyllä |
| Snowflake |Kyllä |
| Spark (beeta), versio 0.9 tai uudempi versio |Kyllä |
| Azure HDInsight Spark (beeta) |Ei |
| IBM Netezza |Kyllä |
| SAP Business Warehouse -sovelluspalvelin |Kyllä |
| SAP Business Warehouse -viestipalvelin |Ei vielä tueta **Power BI -palvelussa** |
| Google BigQuery |Ei |


## <a name="next-steps"></a>Seuraavat vaiheet
Saat lisätietoja DirectQuerystä seuraavista resursseista:

* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)

