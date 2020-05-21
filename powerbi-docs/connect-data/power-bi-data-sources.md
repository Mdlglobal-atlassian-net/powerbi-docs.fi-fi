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
ms.openlocfilehash: 2aa12ec3d55e491535d12107fc70709f9d41c3f0
ms.sourcegitcommit: 6ba7cc9afaf91229f717374bc0c12f0b8201d15e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/16/2020
ms.locfileid: "83438081"
---
# <a name="power-bi-data-sources"></a>Power BI -tietolähteet

Seuraavassa taulukossa esitetään Power BI:n tukemat tietolähteet tietojoukoille ja annetaan tietoja DirectQuerysta ja paikallisesta tietoyhdyskäytävästä. Lisätietoja tietovoista on kohdassa [Yhteyden muodostaminen Power BI -tietovoiden tietolähteisiin](../transform-model/service-dataflows-data-sources.md).

> [!NOTE]
> Power BI Desktopille on useita tietoliittimiä, jotka edellyttävät todentamista Internet Explorer 10:llä (tai uudemmalla versiolla). 


| Tietolähde | Muodosta Desktopista | Muodosta yhteys ja päivitä palvelusta | DirectQuery/live-yhteys | Yhdyskäytävä (tuettu) | Yhdyskäytävä (pakollinen) |
|---|---|---|---|---|---|---|---|
| Access-tietokanta | Kyllä | Kyllä | Ei | Kyllä <sup>1</sup> | Kyllä |
| ActiveDirectory | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| Adobe Analytics | Kyllä | Kyllä | Ei | Ei | Ei |
| Amazon Redshift | Kyllä | Kyllä | Kyllä | Kyllä | Ei |
| appFigures | Kyllä | Kyllä | Ei | Ei | Ei |
| AtScale-kuutiot | Kyllä | Kyllä | Kyllä | Kyllä | Ei |
| Azure Analysis Services | Kyllä | Kyllä | Kyllä | Kyllä <sup>2</sup> | Ei |
| Azure-blob-objektitallennus | Kyllä | Kyllä | Ei | Kyllä | Ei |
| Azure Cosmos DB | Kyllä | Kyllä | Ei | Ei | Ei |
| Azure Cost Management | Kyllä | Kyllä | Ei | Ei | Ei |
| Azure Data Explorer (kusto) | Kyllä | Kyllä | Kyllä | Ei | Ei |
| Azure Data Lake Storage Gen1 | Kyllä | Kyllä | Ei | Ei | Ei |
| Azure Data Lake Storage Gen2 | Kyllä | Kyllä | Ei | Kyllä | Ei |
| Azure DevOps | Kyllä | Kyllä | Ei | Ei | Ei |
| Azure DevOps Server | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| Azure HDInsight (HDFS) | Kyllä | Kyllä | Ei | Ei | Ei |
| Azure HDInsight Spark | Kyllä | Kyllä | Kyllä | Ei | Ei |
| Azuren SQL-tietokanta | Kyllä | Kyllä | Kyllä | Kyllä <sup>2</sup> | Ei |
| Azure SQL Data Warehouse | Kyllä | Kyllä | Kyllä | Kyllä <sup>2</sup> | Ei |
| Azure-taulukkotallennus | Kyllä | Kyllä | Ei | Kyllä | Ei |
| BI-liitin | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| BI360 – budjetointi ja talousraportointi | Kyllä | Kyllä | Ei | Ei | Ei |
| Common Data Service | Kyllä | Kyllä | Ei | Ei | Ei |
| Data.World – nouda tietojoukko | Kyllä | Kyllä | Ei | Ei | Ei |
| Denodo | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Dremio | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Dynamics 365 (online) | Kyllä | Kyllä | Ei | Ei | Ei |
| Dynamics 365 Business Central | Kyllä | Kyllä | Ei | Ei | Ei |
| Dynamics 365 Business Central (paikallinen) | Kyllä | Kyllä | Ei | Ei | Ei |
| Dynamics 365 Customer Insights | Kyllä | Kyllä | Ei | Ei | Ei |
| Dynamics NAV | Kyllä | Kyllä | Ei | Ei | Ei |
| Emigo-tietolähde | Kyllä | Kyllä | Ei | Ei | Ei |
| Entersoft Business Suite | Kyllä | Kyllä | Ei | Ei | Ei |
| Essbase | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Exasol | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Excel | Kyllä <sup>3</sup> | Kyllä <sup>3</sup> | Ei | Kyllä <sup>3</sup> | Ei <sup>4</sup> |
| Facebook | Kyllä | Kyllä | Ei | Ei | Ei |
| Tiedosto | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| Kansio | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| GitHub | Kyllä | Kyllä | Ei | Ei | Ei |
| Google Analytics | Kyllä | Kyllä | Ei | Ei | Ei |
| Google BigQuery | Kyllä | Kyllä | Kyllä | Ei | Ei |
| Hadoop-tiedosto (HDFS) | Kyllä | Ei | Ei | Ei | Ei |
| HDInsight Interactive Query | Kyllä | Kyllä | Kyllä | Ei | Ei |
| IBM DB2 | Kyllä | Kyllä | Kyllä | Kyllä | Ei |
| IBM Informix -tietokanta | Kyllä | Kyllä | Ei | Kyllä | Ei |
| IBM Netezza | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Impala | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Indexima | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| App Store teollisuuskäyttöön | Kyllä | Kyllä | Ei | Ei | Ei |
| Tietoruudukko | Kyllä | Kyllä | Ei | Ei | Ei |
| Intersystems IRIS | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Intune-tietovarasto | Kyllä | Kyllä | Ei | Ei | Ei |
| Jethro ODBC | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| JSON | Kyllä | Kyllä | Ei | Kyllä** | Ei <sup>4</sup> |
| Kyligence Enterprise | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| MailChimp | Kyllä | Kyllä | Ei | Ei | Ei |
| Marketo | Kyllä | Kyllä | Ei | Ei | Ei |
| MarkLogic ODBC | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Microsoft Azure Consumption Insights | Kyllä | Kyllä | Ei | Ei | Ei |
| Microsoft Exchange | Kyllä | Kyllä | Ei | Kyllä | Ei |
| Microsoft Exchange Online | Kyllä | Kyllä | Ei | Ei | Ei |
| Microsoft Graph Security | Kyllä | Kyllä | Ei | Kyllä | Ei |
| Mixpanel | Kyllä | Kyllä | Ei | Ei | Ei |
| MySQL | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| OData | Kyllä | Kyllä | Ei | Kyllä | Ei |
| ODBC | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| OleDb | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| Oracle | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Paxata | Kyllä | Kyllä | Ei | Kyllä | Ei |
| PDF | Kyllä | Kyllä | Ei | Kyllä | Ei <sup>4</sup> |
| Planview Enterprise One – CTM | Kyllä | Kyllä | Ei | Ei | Ei |
| Planview Enterprise One – PRM | Kyllä | Kyllä | Ei | Ei | Ei |
| Planview Projectplace | Kyllä | Kyllä | Ei | Ei | Ei |
| PostgreSQL | Kyllä | Kyllä | Kyllä | Kyllä | Ei |
| Power BI -tietovuot | Kyllä | Kyllä | Ei | Ei | Ei |
| Power BI -tietojoukot | Kyllä | Kyllä | Kyllä | Ei | Ei |
| Power Platform -tietovuot | Kyllä | Kyllä | Ei | Ei | Ei |
| Python-komentosarja | Kyllä | Kyllä <sup>5</sup> | Ei | Kyllä <sup>5</sup> | Kyllä |
| QubolePresto | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Quick Base | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| QuickBooks Online | Kyllä | Kyllä | Ei | Ei | Ei |
| R-komentosarja | Kyllä | Kyllä <sup>5</sup> | Ei | Kyllä <sup>5</sup> | Ei |
| Roamler | Kyllä | Kyllä | Ei | Kyllä | Ei |
| Salesforce-objektit | Kyllä | Kyllä | Ei | Ei | Ei |
| Salesforce-raportit | Kyllä | Kyllä | Ei | Ei | Ei |
| SAP Business Warehouse -viestipalvelin | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| SAP Business Warehouse -palvelin | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| SAP HANA | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| SharePoint-kansio | Kyllä | Kyllä | Ei | Kyllä | Ei <sup>4</sup> |
| SharePoint List | Kyllä | Kyllä | Ei | Kyllä | Ei <sup>4</sup> |
| SharePoint Online -luettelo | Kyllä | Kyllä | Ei | Kyllä <sup>2</sup> | Ei |
| Smartsheet | Kyllä | Kyllä | Ei | Ei | Ei |
| Snowflake | Kyllä | Kyllä | Kyllä | Kyllä | Ei |
| Spark | Kyllä | Kyllä | Kyllä | Kyllä | Ei |
| SparkPost | Kyllä | Kyllä | Ei | Ei | Ei |
| SQL Server | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| SQL Server Analysis Services | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Stripe | Kyllä | Kyllä | Ei | Ei | Ei |
| SurveyMonkey | Kyllä | Kyllä | Ei | Kyllä | Ei |
| SweetIQ | Kyllä | Kyllä | Ei | Ei | Ei |
| Sybase | Kyllä | Kyllä | Ei | Kyllä | Kyllä |
| TeamDesk | Kyllä | Kyllä | Ei | Kyllä | Ei |
| Tenforce | Kyllä | Kyllä | Ei | Ei | Ei |
| Teradata | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Teksti- tai CSV-tiedosto | Kyllä | Kyllä | Ei | Kyllä | Ei <sup>4</sup> |
| Twilio | Kyllä | Kyllä | Ei | Ei | Ei |
| tyGraph | Kyllä | Kyllä | Ei | Ei | Ei |
| Vertica | Kyllä | Kyllä | Kyllä | Kyllä | Kyllä |
| Verkko | Kyllä | Kyllä | Ei | Kyllä | Kyllä <sup>6</sup> |
| Webtrends | Kyllä | Kyllä | Ei | Ei | Ei |
| Työvoiman dimensiot | Kyllä | Kyllä | Ei | Kyllä | Ei |
| XML | Kyllä | Kyllä | Ei | Kyllä | Ei <sup>4</sup> |
| Zendesk | Kyllä | Kyllä | Ei | Ei | Ei |
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

- Azuren SQL-tietokanta
- Azure SQL Data Warehouse
- Impala
- SAP HANA
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
