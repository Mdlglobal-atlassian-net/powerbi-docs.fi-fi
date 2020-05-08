---
title: Power BI -raporttien tietolähteet Power BI -raporttipalvelimessa
description: Power BI -raportit voivat muodostaa yhteyden useisiin tietolähteisiin. Käytettävissä on eri tietolähteitä riippuen siitä, miten tietoja käytetään.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 04/08/2020
ms.author: maggies
ms.openlocfilehash: 166f72a717c99457e1d6b8e9a1f30535a9b4686f
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80979841"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Power BI -raporttien tietolähteet Power BI -raporttipalvelimessa
Power BI -raportit voivat muodostaa yhteyden useisiin tietolähteisiin. Käytettävissä on eri tietolähteitä riippuen siitä, miten tietoja käytetään. Tiedot voidaan tuoda tai tiedoille voidaan tehdä kyselyitä suoraan DirectQuerylla tai reaaliaikaisella SQL Server Analysis Services -yhteydellä.

Nämä tietotyypit koskevat Power BI -raportteja, joita käytetään Power BI -raporttipalvelimessa. Jos haluat lisätietoja tietolähteistä, joita tuetaan sivutetuissa raporteissa (.rdl), tutustu ohjeartikkeliin [Reporting Servicesin tukemat tietolähteet](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Kaikkien Power BI Desktop -raportin tietolähteiden on tuettava ajoitetun päivityksen määrittämistä.
>  

## <a name="list-of-supported-data-sources"></a>Luettelo tuetuista tietolähteistä

Muutkin tietolähteet saattavat toimia, vaikka ne eivät olekaan tuettujen luettelossa.

| **Tietolähde-** | **Välimuistiin tallennetut tiedot** | **Ajoitettu päivitys** | **Reaaliaikainen yhteys / DirectQuery** |
| --- | --- | --- | --- |
| SQL Server -tietokanta |Yes |Yes |Yes |
| SQL Server Analysis Services |Yes |Yes |Yes |
| Azure SQL Database |Yes |Yes |Yes |
| Azure SQL -tietovarasto |Yes |Yes |Yes |
| Excel |Yes |Yes |No |
| Access-tietokanta |Yes |Yes |No |
| Active Directory |Yes |Yes |No |
| Amazon Redshift |Yes |No |No |
| Azure Blob Storage |Yes |Yes |No |
| Azure Data Lake Store |Yes |No |No |
| Azure HDInsight (HDFS) |Yes |No |No |
| Azure HDInsight (Spark) |Yes |No |No |
| Azure Table Storage |Yes |Yes |No |
| Dynamics 365 (online) |Yes |No |No |
| Facebook |Yes |No |No |
| Kansio |Yes |Yes |No |
| Google Analytics |Yes |No |No |
| Hadoop-tiedosto (HDFS) |Yes |No |No |
| IBM DB2 -tietokanta |Yes |Yes |No |
| Impala |Yes |No |No |
| JSON |Yes |Yes |No |
| Microsoft Exchange |Yes |No |No |
| Microsoft Exchange Online |Yes |No |No |
| MySQL-tietokanta |Yes |Yes |No |
| OData-syöte |Yes |Yes |No |
| ODBC |Yes |Yes |No |
| OLE DB |Yes |Yes |No |
| Oracle-tietokanta |Yes |Yes |Yes |
| PostgreSQL-tietokanta |Yes |Yes |No |
| Power BI -palvelu |No |No |No |
| R-komentosarja |Yes |No |No |
| Salesforce-objektit |Yes |No |No |
| Salesforce-raportit |Yes |No |No |
| SAP Business Warehouse -palvelin |Yes |Yes |Yes |
| SAP HANA -tietokanta |Yes |Yes |Yes |
| SharePoint-kansio (paikallinen) |Yes |Yes |No |
| SharePoint-luettelo (paikallinen) |Yes |Yes |No |
| SharePoint Online -luettelo |Yes |No |No |
| Snowflake |Yes |No |No |
| Sybase-tietokanta |Yes |Yes |No |
| Teradata |Yes |Yes |Yes |
| Teksti/CSV |Yes |Yes |No |
| Verkko |Yes |Yes |No |
| XML |Yes |Yes |No |
| appFigures (beeta) |Yes |No |No |
| Azure Analysis Services -tietokanta |Yes |No |Yes |
| Azure Cosmos DB (beeta) |Yes |No |No |
| Azure HDInsight Spark (beeta) |Yes |No |No |
| Common Data Service (beeta) |Yes |No |No |
| comScore Digital Analytix (beeta) |Yes |No |No |
| Dynamics 365 for Customer Insights (beeta) |Yes |No |No |
| Dynamics 365 for Financials (beeta) |Yes |No |No |
| GitHub (beeta) |Yes |No |No |
| Google BigQuery (beeta) |Yes |No |No |
| IBM Informix -tietokanta (beeta) |Yes |No |No |
| IBM Netezza (beeta) |Yes |No |No |
| Kusto (beeta) |Yes |No |No |
| MailChimp (beeta) |Yes |No |No |
| Microsoft Azure Consumption Insights (beeta) |Yes |No |No |
| Mixpanel (beeta) |Yes |No |No |
| Planview Enterprise (beeta) |Yes |No |No |
| Projectplace (beeta) |Yes |No |No |
| QuickBooks Online (beeta) |Yes |No |No |
| Smartsheet |Yes |No |No |
| Spark (beeta) |Yes |No |No |
| SparkPost (beeta) |Yes |No |No |
| SQL Sentry (beeta) |Yes |No |No |
| Stripe (beeta) |Yes |No |No |
| SweetIQ (beeta) |Yes |No |No |
| Troux (beeta) |Yes |No |No |
| Twilio (beeta) |Yes |No |No |
| tyGraph (beeta) |Yes |No |No |
| Vertica (beeta) |Yes |No |No |
| Visual Studio Team Services (beeta) |Yes |No |No |
| Webtrends (beeta) |Yes |No |No |
| Zendesk (beeta) |Yes |No |No |

> [!IMPORTANT]
> Tietolähteessä määritetyn rivitason suojauksen pitäisi toimia tietyissä DirectQuery-yhteyksissä (SQL Server, Azure SQL -tietokanta, Oracle ja Teradata) sekä reaaliaikaisissa yhteyksissä, jos Kerberos on määritetty oikein ympäristössäsi.
> 
> 

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>Mallipäivityksen tukemat todennustavat

Power BI -raporttipalvelin ei tue OAuth-pohjaista todennusta mallipäivityksessä. Jotkin tietolähteet, esimerkiksi Excel ja Access-tietokannat, käyttävät ylimääräistä vaihetta tietoihin yhdistämisessä (esimerkiksi tiedosto- tai verkkovaihe).

| **Tietolähde-** | **Anonyymi todentaminen** | **Avaintodentaminen** | **Käyttäjänimi ja salasana** | **Windows-todentaminen** |
| --- | --- | --- | --- | --- |
| SQL Server -tietokanta |No |No |Yes |Yes |
| SQL Server Analysis Services |No |No |Yes |Yes |
| Verkko |Yes |No |Yes |Yes |
| Azure SQL Database |No |No |Yes |No |
| Azure SQL -tietovarasto |No |No |Yes |No |
| Active Directory |No |No |Yes |Yes |
| Amazon Redshift |No |No |No |No |
| Azure Blob Storage |Yes |Yes |No |No |
| Azure Data Lake Store |No |No |No |No |
| Azure HDInsight (HDFS) |No |No |No |No |
| Azure HDInsight (Spark) |No |No |No |No |
| Azure Table Storage |No |Yes |No |No |
| Dynamics 365 (online) |No |No |No |No |
| Facebook |No |No |No |No |
| Kansio |No |No |No |Yes |
| Google Analytics |No |No |No |No |
| Hadoop-tiedosto (HDFS) |No |No |No |No |
| IBM DB2 -tietokanta |No |No |Yes |Yes |
| Impala |No |No |No |No |
| Microsoft Exchange |No |No |No |No |
| Microsoft Exchange Online |No |No |No |No |
| MySQL-tietokanta |No |No |Yes |Yes |
| OData-syöte |Yes |Yes |Yes |Yes |
| ODBC |Yes |No |Yes |Yes |
| OLE DB |Yes |No |Yes |Yes |
| Oracle-tietokanta |No |No |Yes |Yes |
| PostgreSQL-tietokanta |No |No |Yes |No |
| Power BI -palvelu |No |No |No |No |
| R-komentosarja |No |No |No |No |
| Salesforce-objektit |No |No |No |No |
| Salesforce-raportit |No |No |No |No |
| SAP Business Warehouse -palvelin |No |No |Yes |No |
| SAP HANA -tietokanta |No |No |Yes |Yes |
| SharePoint-kansio (paikallinen) |Yes |No |No |Yes |
| SharePoint-luettelo (paikallinen) |Yes |No |No |Yes |
| SharePoint Online -luettelo |No |No |No |No |
| Snowflake |No |No |No |No |
| Sybase-tietokanta |No |No |Yes |Yes |
| Teradata |No |No |Yes |Kyllä** |
| appFigures (beeta) |No |No |No |No |
| Azure Analysis Services -tietokanta (beeta) |No |No |No |No |
| Azure Cosmos DB (beeta) |No |No |No |No |
| Azure HDInsight Spark (beeta) |No |No |No |No |
| Common Data Service (beeta) |No |No |No |No |
| comScore Digital Analytix (beeta) |No |No |No |No |
| Dynamics 365 for Customer Insights (beeta) |No |No |No |No |
| Dynamics 365 for Financials (beeta) |No |No |No |No |
| GitHub (beeta) |No |No |No |No |
| Google BigQuery (beeta) |No |No |No |No |
| IBM Informix -tietokanta (beeta) |No |No |No |No |
| IBM Netezza (beeta) |No |No |No |No |
| Kusto (beeta) |No |No |No |No |
| MailChimp (beeta) |No |No |No |No |
| Microsoft Azure Consumption Insights (beeta) |No |No |No |No |
| Mixpanel (beeta) |No |No |No |No |
| Planview Enterprise (beeta) |No |No |No |No |
| Projectplace (beeta) |No |No |No |No |
| QuickBooks Online (beeta) |No |No |No |No |
| Smartsheet |No |No |No |No |
| Spark (beeta) |No |No |No |No |
| SparkPost (beeta) |No |No |No |No |
| SQL Sentry (beeta) |No |No |No |No |
| Stripe (beeta) |No |No |No |No |
| SweetIQ (beeta) |No |No |No |No |
| Troux (beeta) |No |No |No |No |
| Twilio (beeta) |No |No |No |No |
| tyGraph (beeta) |No |No |No |No |
| Vertica (beeta) |No |No |No |No |
| Visual Studio Team Services (beeta) |No |No |No |No |
| Webtrends (beeta) |No |No |No |No |
| Zendesk (beeta) |No |No |No |No |

** LDAP-todentamisen käyttäminen Teradata-palvelun kanssa (otetaan käyttöön Power BI Desktopissa komentorivikomennolla 'setx PBI_EnableTeradataLdap true') ei tueta mallin päivityksessä.

## <a name="list-of-supported-authentication-methods-for-directquery"></a>DirectQueryn tukemat todennustavat

Power BI -raporttipalvelin ei tue OAuth-pohjaista todennusta DirectQuerylle.

| **Tietolähde-** | **Anonyymi todentaminen** | **Avaintodentaminen** | **Käyttäjänimi ja salasana** | **Windows-todentaminen** | **Integroitu Windows-todentaminen** |
| --- | --- | --- | --- | --- | --- |
| SQL Server -tietokanta |No |No |Yes |Yes |Yes |
| SQL Server Analysis Services |No |No |Yes |Yes |Yes |
| Azure SQL Database |No |No |Yes |No |No |
| Azure SQL -tietovarasto |No |No |Yes |No |No |
| Oracle-tietokanta |No |No |Yes |Yes |Yes |
| SAP Business Warehouse -palvelin |No |No |Yes |No |No |
| SAP HANA -tietokanta |No |No |Yes |Yes |Kyllä** |
| Teradata |No |No |Yes |Yes |Yes |

**SAP HANA tukee DirectQueryä integroidulla Windows-todentamisella vain, kun sitä käytetään relaatiotietokantana julkaistussa Power BI Desktop -tiedostossa (.pbix).

## <a name="next-steps"></a>Seuraavat vaiheet
Nyt kun olet muodostanut yhteyden tietolähteeseen, voit [luoda Power BI -raportin](quickstart-create-powerbi-report.md) sen tiedoista.

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
