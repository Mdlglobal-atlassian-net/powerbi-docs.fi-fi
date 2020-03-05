---
title: Power BI -raporttien tietolähteet Power BI -raporttipalvelimessa
description: Power BI -raportit voivat muodostaa yhteyden useisiin tietolähteisiin. Käytettävissä on eri tietolähteitä riippuen siitä, miten tietoja käytetään.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 03/02/2020
ms.author: maggies
ms.openlocfilehash: 08eca8ecb9aa941c2670a801113bc711bff409b2
ms.sourcegitcommit: d65da4738f011beec8f4423085cbd483511cdfb0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/03/2020
ms.locfileid: "78237519"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Power BI -raporttien tietolähteet Power BI -raporttipalvelimessa
Power BI -raportit voivat muodostaa yhteyden useisiin tietolähteisiin. Käytettävissä on eri tietolähteitä riippuen siitä, miten tietoja käytetään. Tiedot voidaan tuoda tai tiedoille voidaan tehdä kyselyitä suoraan DirectQuerylla tai reaaliaikaisella SQL Server Analysis Services -yhteydellä.

Nämä tietotyypit koskevat Power BI -raportteja, joita käytetään Power BI -raporttipalvelimessa. Jos haluat lisätietoja tietolähteistä, joita tuetaan sivutetuissa raporteissa (.rdl), tutustu ohjeartikkeliin [Reporting Servicesin tukemat tietolähteet](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Kaikkien Power BI Desktop -raportin tietolähteiden on tuettava ajoitetun päivityksen määrittämistä.
>  

## <a name="list-of-supported-data-sources"></a>Luettelo tuetuista tietolähteistä

Muutkin tietolähteet saattavat toimia, vaikka ne eivät olekaan tuettujen luettelossa.

| **Tietolähde** | **Välimuistiin tallennetut tiedot** | **Ajoitettu päivitys** | **Reaaliaikainen yhteys / DirectQuery** |
| --- | --- | --- | --- |
| SQL Server -tietokanta |Kyllä |Kyllä |Kyllä |
| SQL Server Analysis Services |Kyllä |Kyllä |Kyllä |
| Azuren SQL-tietokanta |Kyllä |Kyllä |Kyllä |
| Azure SQL -tietovarasto |Kyllä |Kyllä |Kyllä |
| Excel |Kyllä |Kyllä |Ei |
| Access-tietokanta |Kyllä |Kyllä |Ei |
| Active Directory |Kyllä |Kyllä |Ei |
| Amazon Redshift |Kyllä |Ei |Ei |
| Azure-blob-objektitallennus |Kyllä |Kyllä |Ei |
| Azure Data Lake Store |Kyllä |Ei |Ei |
| Azure HDInsight (HDFS) |Kyllä |Ei |Ei |
| Azure HDInsight (Spark) |Kyllä |Ei |Ei |
| Azure-taulukkotallennus |Kyllä |Kyllä |Ei |
| Dynamics 365 (online) |Kyllä |Ei |Ei |
| Facebook |Kyllä |Ei |Ei |
| Kansio |Kyllä |Kyllä |Ei |
| Google Analytics |Kyllä |Ei |Ei |
| Hadoop-tiedosto (HDFS) |Kyllä |Ei |Ei |
| IBM DB2 -tietokanta |Kyllä |Kyllä |Ei |
| Impala |Kyllä |Ei |Ei |
| JSON |Kyllä |Kyllä |Ei |
| Microsoft Exchange |Kyllä |Ei |Ei |
| Microsoft Exchange Online |Kyllä |Ei |Ei |
| MySQL-tietokanta |Kyllä |Kyllä |Ei |
| OData-syöte |Kyllä |Kyllä |Ei |
| ODBC |Kyllä |Kyllä |Ei |
| OLE DB |Kyllä |Kyllä |Ei |
| Oracle-tietokanta |Kyllä |Kyllä |Kyllä |
| PostgreSQL-tietokanta |Kyllä |Kyllä |Ei |
| Power BI -palvelu |Ei |Ei |Ei |
| R-komentosarja |Kyllä |Ei |Ei |
| Salesforce-objektit |Kyllä |Ei |Ei |
| Salesforce-raportit |Kyllä |Ei |Ei |
| SAP Business Warehouse -palvelin |Kyllä |Kyllä |Kyllä |
| SAP HANA -tietokanta |Kyllä |Kyllä |Kyllä |
| SharePoint-kansio (paikallinen) |Kyllä |Kyllä |Ei |
| SharePoint-luettelo (paikallinen) |Kyllä |Kyllä |Ei |
| SharePoint Online -luettelo |Kyllä |Ei |Ei |
| Snowflake |Kyllä |Ei |Ei |
| Sybase-tietokanta |Kyllä |Kyllä |Ei |
| Teradata |Kyllä |Kyllä |Kyllä |
| Teksti- tai CSV-tiedosto |Kyllä |Kyllä |Ei |
| Verkko |Kyllä |Kyllä |Ei |
| XML |Kyllä |Kyllä |Ei |
| appFigures (beeta) |Kyllä |Ei |Ei |
| Azure Analysis Services -tietokanta |Kyllä |Ei |Kyllä |
| Azure Cosmos DB (beeta) |Kyllä |Ei |Ei |
| Azure HDInsight Spark (beeta) |Kyllä |Ei |Ei |
| Common Data Service (beeta) |Kyllä |Ei |Ei |
| comScore Digital Analytix (beeta) |Kyllä |Ei |Ei |
| Dynamics 365 for Customer Insights (beeta) |Kyllä |Ei |Ei |
| Dynamics 365 for Financials (beeta) |Kyllä |Ei |Ei |
| GitHub (beeta) |Kyllä |Ei |Ei |
| Google BigQuery (beeta) |Kyllä |Ei |Ei |
| IBM Informix -tietokanta (beeta) |Kyllä |Ei |Ei |
| IBM Netezza (beeta) |Kyllä |Ei |Ei |
| Kusto (beeta) |Kyllä |Ei |Ei |
| MailChimp (beeta) |Kyllä |Ei |Ei |
| Microsoft Azure Consumption Insights (beeta) |Kyllä |Ei |Ei |
| Mixpanel (beeta) |Kyllä |Ei |Ei |
| Planview Enterprise (beeta) |Kyllä |Ei |Ei |
| Projectplace (beeta) |Kyllä |Ei |Ei |
| QuickBooks Online (beeta) |Kyllä |Ei |Ei |
| Smartsheet |Kyllä |Ei |Ei |
| Spark (beeta) |Kyllä |Ei |Ei |
| SparkPost (beeta) |Kyllä |Ei |Ei |
| SQL Sentry (beeta) |Kyllä |Ei |Ei |
| Stripe (beeta) |Kyllä |Ei |Ei |
| SweetIQ (beeta) |Kyllä |Ei |Ei |
| Troux (beeta) |Kyllä |Ei |Ei |
| Twilio (beeta) |Kyllä |Ei |Ei |
| tyGraph (beeta) |Kyllä |Ei |Ei |
| Vertica (beeta) |Kyllä |Ei |Ei |
| Visual Studio Team Services (beeta) |Kyllä |Ei |Ei |
| Webtrends (beeta) |Kyllä |Ei |Ei |
| Zendesk (beeta) |Kyllä |Ei |Ei |

> [!IMPORTANT]
> Tietolähteessä määritetyn rivitason suojauksen pitäisi toimia tietyissä DirectQuery-yhteyksissä (SQL Server, Azure SQL -tietokanta, Oracle ja Teradata) sekä reaaliaikaisissa yhteyksissä, jos Kerberos on määritetty oikein ympäristössäsi.
> 
> 

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>Mallipäivityksen tukemat todennustavat

Power BI -raporttipalvelin ei tue OAuth-pohjaista todennusta mallipäivityksessä. Jotkin tietolähteet, esimerkiksi Excel ja Access-tietokannat, käyttävät ylimääräistä vaihetta tietoihin yhdistämisessä (esimerkiksi tiedosto- tai verkkovaihe).

| **Tietolähde** | **Anonyymi todentaminen** | **Avaintodentaminen** | **Käyttäjänimi ja salasana** | **Windows-todentaminen** |
| --- | --- | --- | --- | --- |
| SQL Server -tietokanta |Ei |Ei |Kyllä |Kyllä |
| SQL Server Analysis Services |Ei |Ei |Kyllä |Kyllä |
| Verkko |Kyllä |Ei |Kyllä |Kyllä |
| Azuren SQL-tietokanta |Ei |Ei |Kyllä |Ei |
| Azure SQL Data Warehouse |Ei |Ei |Kyllä |Ei |
| Active Directory |Ei |Ei |Kyllä |Kyllä |
| Amazon Redshift |Ei |Ei |Ei |Ei |
| Azure-blob-objektitallennus |Kyllä |Kyllä |Ei |Ei |
| Azure Data Lake Store |Ei |Ei |Ei |Ei |
| Azure HDInsight (HDFS) |Ei |Ei |Ei |Ei |
| Azure HDInsight (Spark) |Ei |Ei |Ei |Ei |
| Azure-taulukkotallennus |Ei |Kyllä |Ei |Ei |
| Dynamics 365 (online) |Ei |Ei |Ei |Ei |
| Facebook |Ei |Ei |Ei |Ei |
| Kansio |Ei |Ei |Ei |Kyllä |
| Google Analytics |Ei |Ei |Ei |Ei |
| Hadoop-tiedosto (HDFS) |Ei |Ei |Ei |Ei |
| IBM DB2 -tietokanta |Ei |Ei |Kyllä |Kyllä |
| Impala |Ei |Ei |Ei |Ei |
| Microsoft Exchange |Ei |Ei |Ei |Ei |
| Microsoft Exchange Online |Ei |Ei |Ei |Ei |
| MySQL-tietokanta |Ei |Ei |Kyllä |Kyllä |
| OData-syöte |Kyllä |Kyllä |Kyllä |Kyllä |
| ODBC |Kyllä |Ei |Kyllä |Kyllä |
| OLE DB |Kyllä |Ei |Kyllä |Kyllä |
| Oracle-tietokanta |Ei |Ei |Kyllä |Kyllä |
| PostgreSQL-tietokanta |Ei |Ei |Kyllä |Ei |
| Power BI -palvelu |Ei |Ei |Ei |Ei |
| R-komentosarja |Ei |Ei |Ei |Ei |
| Salesforce-objektit |Ei |Ei |Ei |Ei |
| Salesforce-raportit |Ei |Ei |Ei |Ei |
| SAP Business Warehouse -palvelin |Ei |Ei |Kyllä |Ei |
| SAP HANA -tietokanta |Ei |Ei |Kyllä |Kyllä |
| SharePoint-kansio (paikallinen) |Kyllä |Ei |Ei |Kyllä |
| SharePoint-luettelo (paikallinen) |Kyllä |Ei |Ei |Kyllä |
| SharePoint Online -luettelo |Ei |Ei |Ei |Ei |
| Snowflake |Ei |Ei |Ei |Ei |
| Sybase-tietokanta |Ei |Ei |Kyllä |Kyllä |
| Teradata |Ei |Ei |Kyllä |Kyllä |
| appFigures (beeta) |Ei |Ei |Ei |Ei |
| Azure Analysis Services -tietokanta (beeta) |Ei |Ei |Ei |Ei |
| Azure Cosmos DB (beeta) |Ei |Ei |Ei |Ei |
| Azure HDInsight Spark (beeta) |Ei |Ei |Ei |Ei |
| Common Data Service (beeta) |Ei |Ei |Ei |Ei |
| comScore Digital Analytix (beeta) |Ei |Ei |Ei |Ei |
| Dynamics 365 for Customer Insights (beeta) |Ei |Ei |Ei |Ei |
| Dynamics 365 for Financials (beeta) |Ei |Ei |Ei |Ei |
| GitHub (beeta) |Ei |Ei |Ei |Ei |
| Google BigQuery (beeta) |Ei |Ei |Ei |Ei |
| IBM Informix -tietokanta (beeta) |Ei |Ei |Ei |Ei |
| IBM Netezza (beeta) |Ei |Ei |Ei |Ei |
| Kusto (beeta) |Ei |Ei |Ei |Ei |
| MailChimp (beeta) |Ei |Ei |Ei |Ei |
| Microsoft Azure Consumption Insights (beeta) |Ei |Ei |Ei |Ei |
| Mixpanel (beeta) |Ei |Ei |Ei |Ei |
| Planview Enterprise (beeta) |Ei |Ei |Ei |Ei |
| Projectplace (beeta) |Ei |Ei |Ei |Ei |
| QuickBooks Online (beeta) |Ei |Ei |Ei |Ei |
| Smartsheet |Ei |Ei |Ei |Ei |
| Spark (beeta) |Ei |Ei |Ei |Ei |
| SparkPost (beeta) |Ei |Ei |Ei |Ei |
| SQL Sentry (beeta) |Ei |Ei |Ei |Ei |
| Stripe (beeta) |Ei |Ei |Ei |Ei |
| SweetIQ (beeta) |Ei |Ei |Ei |Ei |
| Troux (beeta) |Ei |Ei |Ei |Ei |
| Twilio (beeta) |Ei |Ei |Ei |Ei |
| tyGraph (beeta) |Ei |Ei |Ei |Ei |
| Vertica (beeta) |Ei |Ei |Ei |Ei |
| Visual Studio Team Services (beeta) |Ei |Ei |Ei |Ei |
| Webtrends (beeta) |Ei |Ei |Ei |Ei |
| Zendesk (beeta) |Ei |Ei |Ei |Ei |

## <a name="list-of-supported-authentication-methods-for-directquery"></a>DirectQueryn tukemat todennustavat

Power BI -raporttipalvelin ei tue OAuth-pohjaista todennusta DirectQuerylle.

| **Tietolähde** | **Anonyymi todentaminen** | **Avaintodentaminen** | **Käyttäjänimi ja salasana** | **Windows-todentaminen** | **Integroitu Windows-todentaminen** |
| --- | --- | --- | --- | --- | --- |
| SQL Server -tietokanta |Ei |Ei |Kyllä |Kyllä |Kyllä |
| SQL Server Analysis Services |Ei |Ei |Kyllä |Kyllä |Kyllä |
| Azuren SQL-tietokanta |Ei |Ei |Kyllä |Ei |Ei |
| Azure SQL Data Warehouse |Ei |Ei |Kyllä |Ei |Ei |
| Oracle-tietokanta |Ei |Ei |Kyllä |Kyllä |Kyllä |
| SAP Business Warehouse -palvelin |Ei |Ei |Kyllä |Ei |Ei |
| SAP HANA -tietokanta |Ei |Ei |Kyllä |Kyllä |Kyllä** |
| Teradata |Ei |Ei |Kyllä |Kyllä |Kyllä |

**SAP HANA tukee DirectQueryä integroidulla Windows-todentamisella vain, kun sitä käytetään relaatiotietokantana julkaistussa Power BI Desktop -tiedostossa (.pbix).

## <a name="next-steps"></a>Seuraavat vaiheet
Nyt kun olet muodostanut yhteyden tietolähteeseen, voit [luoda Power BI -raportin](quickstart-create-powerbi-report.md) sen tiedoista.

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
