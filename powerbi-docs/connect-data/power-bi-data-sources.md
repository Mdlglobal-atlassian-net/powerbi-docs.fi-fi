---
title: Power BI -tietolähteet
description: Tässä artikkelissa luetellaan Power BI:n tukemat tietolähteet ja annetaan tietoja DirectQuerysta ja paikallisesta tietoyhdyskäytävästä.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/10/2020
ms.author: kfollis
ms.openlocfilehash: a29dcd8c89d064678e558d5ebfee7ccb3cc8a8e0
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83330102"
---
# <a name="power-bi-data-sources"></a>Power BI -tietolähteet

Seuraavassa taulukossa esitetään Power BI:n tukemat tietolähteet tietojoukoille ja annetaan tietoja DirectQuerysta ja paikallisesta tietoyhdyskäytävästä. Lisätietoja tietovoista on kohdassa [Yhteyden muodostaminen Power BI -tietovoiden tietolähteisiin](../transform-model/service-dataflows-data-sources.md).

> [!NOTE]
> Power BI Desktopille on useita tietoliittimiä, jotka edellyttävät todentamista Internet Explorer 10:llä (tai uudemmalla versiolla). 


| Tietolähde | Muodosta Desktopista | Muodosta yhteys ja päivitä palvelusta | DirectQuery/live-yhteys | Yhdyskäytävä (tuettu) | Yhdyskäytävä (pakollinen) |
|---|---|---|---|---|---|---|---|
| Access-tietokanta | Yes | Yes | No | Kyllä <sup>1</sup> | Yes |
| ActiveDirectory | Yes | Yes | No | Yes | Yes |
| Adobe Analytics | Yes | Yes | No | No | No |
| Amazon Redshift | Yes | Yes | Yes | Yes | No |
| appFigures | Yes | Yes | No | No | No |
| AtScale-kuutiot | Yes | Yes | Yes | Yes | No |
| Azure Analysis Services | Yes | Yes | Yes | Kyllä <sup>2</sup> | No |
| Azure Blob Storage | Yes | Yes | No | Yes | No |
| Azure Cosmos DB | Yes | Yes | No | No | No |
| Azure Cost Management | Yes | Yes | No | No | No |
| Azure Data Explorer (kusto) | Yes | Yes | Yes | No | No |
| Azure Data Lake Storage Gen1 | Yes | Yes | No | No | No |
| Azure Data Lake Storage Gen2 | Yes | Yes | No | Yes | No |
| Azure DevOps | Yes | Yes | No | No | No |
| Azure DevOps Server | Yes | Yes | No | Yes | Yes |
| Azure HDInsight (HDFS) | Yes | Yes | No | No | No |
| Azure HDInsight Spark | Yes | Yes | Yes | No | No |
| Azure SQL Database | Yes | Yes | Yes | Kyllä <sup>2</sup> | No |
| Azure SQL -tietovarasto | Yes | Yes | Yes | Kyllä <sup>2</sup> | No |
| Azure Table Storage | Yes | Yes | No | Yes | No |
| BI-liitin | Yes | Yes | Yes | Yes | Yes |
| BI360 – budjetointi ja talousraportointi | Yes | Yes | No | No | No |
| Common Data Service | Yes | Yes | No | No | No |
| Data.World – nouda tietojoukko | Yes | Yes | No | No | No |
| Denodo | Yes | Yes | Yes | Yes | Yes |
| Dremio | Yes | Yes | Yes | Yes | Yes |
| Dynamics 365 (online) | Yes | Yes | No | No | No |
| Dynamics 365 Business Central | Yes | Yes | No | No | No |
| Dynamics 365 Business Central (paikallinen) | Yes | Yes | No | No | No |
| Dynamics 365 Customer Insights | Yes | Yes | No | No | No |
| Dynamics NAV | Yes | Yes | No | No | No |
| Emigo-tietolähde | Yes | Yes | No | No | No |
| Entersoft Business Suite | Yes | Yes | No | No | No |
| Essbase | Yes | Yes | Yes | Yes | Yes |
| Exasol | Yes | Yes | Yes | Yes | Yes |
| Excel | Kyllä <sup>3</sup> | Kyllä <sup>3</sup> | No | Kyllä <sup>3</sup> | Ei <sup>4</sup> |
| Facebook | Yes | Yes | No | No | No |
| tiedosto | Yes | Yes | No | Yes | Yes |
| Kansio | Yes | Yes | No | Yes | Yes |
| GitHub | Yes | Yes | No | No | No |
| Google Analytics | Yes | Yes | No | No | No |
| Google BigQuery | Yes | Yes | No | No | No |
| Hadoop-tiedosto (HDFS) | Yes | No | No | No | No |
| HDInsight Interactive Query | Yes | Yes | Yes | No | No |
| IBM DB2 | Yes | Yes | Yes | Yes | No |
| IBM Informix -tietokanta | Yes | Yes | No | Yes | No |
| IBM Netezza | Yes | Yes | Yes | Yes | Yes |
| Impala | Yes | Yes | Yes | Yes | Yes |
| Indexima | Yes | Yes | Yes | Yes | Yes |
| App Store teollisuuskäyttöön | Yes | Yes | No | No | No |
| Tietoruudukko | Yes | Yes | No | No | No |
| Intersystems IRIS | Yes | Yes | Yes | Yes | Yes |
| Intune-tietovarasto | Yes | Yes | No | No | No |
| Jethro ODBC | Yes | Yes | Yes | Yes | Yes |
| JSON | Yes | Yes | No | Kyllä** | Ei <sup>4</sup> |
| Kyligence Enterprise | Yes | Yes | Yes | Yes | Yes |
| MailChimp | Yes | Yes | No | No | No |
| Marketo | Yes | Yes | No | No | No |
| MarkLogic ODBC | Yes | Yes | Yes | Yes | Yes |
| Microsoft Azure Consumption Insights | Yes | Yes | No | No | No |
| Microsoft Exchange | Yes | Yes | No | Yes | No |
| Microsoft Exchange Online | Yes | Yes | No | No | No |
| Microsoft Graph Security | Yes | Yes | No | Yes | No |
| Mixpanel | Yes | Yes | No | No | No |
| MySQL | Yes | Yes | No | Yes | Yes |
| OData | Yes | Yes | No | Yes | No |
| ODBC | Yes | Yes | No | Yes | Yes |
| OleDb | Yes | Yes | No | Yes | Yes |
| Oracle | Yes | Yes | Yes | Yes | Yes |
| Paxata | Yes | Yes | No | Yes | No |
| PDF | Yes | Yes | No | Yes | Ei <sup>4</sup> |
| Planview Enterprise One – CTM | Yes | Yes | No | No | No |
| Planview Enterprise One – PRM | Yes | Yes | No | No | No |
| Planview Projectplace | Yes | Yes | No | No | No |
| PostgreSQL | Yes | Yes | Yes | Yes | No |
| Power BI -tietovuot | Yes | Yes | No | No | No |
| Power BI -tietojoukot | Yes | Yes | Yes | No | No |
| Power Platform -tietovuot | Yes | Yes | No | No | No |
| Python-komentosarja | Yes | Kyllä <sup>5</sup> | No | Kyllä <sup>5</sup> | Yes |
| QubolePresto | Yes | Yes | Yes | Yes | Yes |
| Quick Base | Yes | Yes | No | Yes | Yes |
| QuickBooks Online | Yes | Yes | No | No | No |
| R-komentosarja | Yes | Kyllä <sup>5</sup> | No | Kyllä <sup>5</sup> | No |
| Roamler | Yes | Yes | No | Yes | No |
| Salesforce-objektit | Yes | Yes | No | No | No |
| Salesforce-raportit | Yes | Yes | No | No | No |
| SAP Business Warehouse -viestipalvelin | Yes | Yes | Yes | Yes | Yes |
| SAP Business Warehouse -palvelin | Yes | Yes | Yes | Yes | Yes |
| SAP HANA. | Yes | Yes | Yes | Yes | Yes |
| SharePoint-kansio | Yes | Yes | No | Yes | Ei <sup>4</sup> |
| SharePoint List | Yes | Yes | No | Yes | Ei <sup>4</sup> |
| SharePoint Online -luettelo | Yes | Yes | No | Kyllä <sup>2</sup> | No |
| Smartsheet | Yes | Yes | No | No | No |
| Snowflake | Yes | Yes | Yes | Yes | No |
| Spark | Yes | Yes | Yes | Yes | No |
| SparkPost | Yes | Yes | No | No | No |
| SQL Server | Yes | Yes | Yes | Yes | Yes |
| SQL Server Analysis Services | Yes | Yes | Yes | Yes | Yes |
| Stripe | Yes | Yes | No | No | No |
| SurveyMonkey | Yes | Yes | No | Yes | No |
| SweetIQ | Yes | Yes | No | No | No |
| Sybase | Yes | Yes | No | Yes | Yes |
| TeamDesk | Yes | Yes | No | Yes | No |
| Tenforce | Yes | Yes | No | No | No |
| Teradata | Yes | Yes | Yes | Yes | Yes |
| Teksti/CSV | Yes | Yes | No | Yes | Ei <sup>4</sup> |
| Twilio | Yes | Yes | No | No | No |
| tyGraph | Yes | Yes | No | No | No |
| Vertica | Yes | Yes | Yes | Yes | Yes |
| Verkko | Yes | Yes | No | Yes | Kyllä <sup>6</sup> |
| Webtrends | Yes | Yes | No | No | No |
| Työvoiman dimensiot | Yes | Yes | No | Yes | No |
| XML | Yes | Yes | No | Yes | Ei <sup>4</sup> |
| Zendesk | Yes | Yes | No | No | No |
| | | | | | | | |

<sup>1</sup> Tuetaan [ACE OLEDB -palvelun kanssa](https://www.microsoft.com/download/details.aspx?id=54920), asennettuna samaan koneeseen kuin yhdyskäytävä.

<sup>2</sup> Tuettu samalla M-funktiolla kuin paikallisessa versiossa, mikä aiheuttaa rajoitetut todennusvalinnat (yhdyskäytävä ei tue OAuthia).

<sup>3</sup> Excel 1997–2003 -tiedostot (.xls) edellyttävät [ACE OLEDB -palvelua](https://www.microsoft.com/download/details.aspx?id=54920).

<sup>4</sup> Edellytetään tekniikan paikallisessa versiossa.

<sup>5</sup> Tuetaan vain [henkilökohtaisen yhdyskäytävän](service-gateway-personal-mode.md) kanssa.

<sup>6</sup> Pakollinen .html-, .xls- ja Access-tietokannoille

## <a name="single-sign-on-sso-for-directquery-sources"></a>DirectQuery-lähteiden kertakirjautuminen

Kun kertakirjautumisasetus on käytössä ja käyttäjät käyttävät raportteja, jotka on luotu tietolähteeseen, Power BI lähettää todennetut Azure AD -tunnistetiedot kyselyissä taustalla olevaan tietokantaan. Näin Power BI voi noudattaa tietoturva-asetuksia, jotka on määritetty tietolähteen tasolla.
Kertakirjautumisen asetus tulee voimaan kaikissa tietojoukoissa, jotka käyttävät tätä tietolähdettä. Se ei vaikuta tuontitilanteissa käytettyihin todentamismenetelmiin. Seuraavat tietolähteet tukevat DirectQueryn kertakirjautumisyhteyksiä:

- Azure SQL Database
- Azure SQL -tietovarasto
- Impala
- SAP HANA.
- SAP BW
- SAP BW Message Server
- Snowflake
- Spark
- SQL Server
- Teradata

> [!Note]
> Azure Multi-Factor Authenticationia (MFA) ei tueta. Käyttäjät, jotka haluavat käyttää kertakirjautumista DirectQueryn kanssa, täytyy vapauttaa MFA:n käytöstä.

## <a name="next-steps"></a>Seuraavat vaiheet

[Tietoihin yhdistäminen Power BI Desktopissa](desktop-quickstart-connect-to-data.md)  
[DirectQueryn käyttäminen Power BI:ssä](desktop-directquery-about.md)  
[SQL Server Analysis Servicesin reaaliaikaiset tiedot Power BI:ssä](sql-server-analysis-services-tabular-data.md)  
[Mikä paikallinen tietoyhdyskäytävä on?](service-gateway-onprem.md)  
