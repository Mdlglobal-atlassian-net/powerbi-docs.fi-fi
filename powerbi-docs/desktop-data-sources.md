---
title: Power BI Desktopin tietolähteet
description: Power BI Desktopin tietolähteet
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: complete
qualitydate: 04/29/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 4bfdbaaa305f80195fd08155ecca744444495aeb
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2018
ms.locfileid: "30975472"
---
# <a name="data-sources-in-power-bi-desktop"></a>Power BI Desktopin tietolähteet
Power BI Desktopin avulla voit yhdistää tietoja monista eri lähteistä. Täydellinen luettelo käytettävissä olevista tietolähteistä on tämän sivun alareunassa.

Muodosta yhteys tietoihin valitsemalla **Aloitus**-valintanauhassa **Nouda tiedot**. Jos valitset alanuolen tai **Nouda tiedot** -painikkeen, näyttöön tulee **yleisimpien** tietotyyppien valikko, joka näkyy seuraavassa kuvassa:

![](media/desktop-data-sources/data-sources_1.png)

Valitsemalla **Lisää...** **Yleisimmät**-valikossa saat **Nouda tiedot** -ikkunan näkyviin. Voit myös tuoda **Nouda tiedot** -ikkunan (ja ohittaa **Yleisimmät**-valikon) valitsemalla suoraan **Nouda tiedot** **-kuvakepainikkeen**.

![](media/desktop-data-sources/data-sources_2.png)

> [!NOTE]
> Power BI -tiimi laajentaa jatkuvasti **Power BI Desktopin** ja **Power BI -palvelun** käytettävissä olevia tietolähteitä. Näet näin ollen usein keskeneräisten tietolähteiden varhaisia versioita, joissa on merkintä *beeta* tai *esikatselu*. Tietolähteen, jolla on merkintä *beeta* tai *esikatselu*, tuki ja toiminnallisuus ovat rajoitettua, eikä sitä tulisi käyttää tuotantoympäristössä.
> 
> 

## <a name="data-sources"></a>Tietolähteet
Kaikki tietotyypit on järjestelty seuraaviin luokkiin:

* Kaikki
* Tiedosto
* Tietokanta
* Azure
* Online-palvelut
* Muut

**Kaikki**-luokka sisältää kaikki tietoyhteystyypit kaikista luokista.

**Tiedosto**-luokka tarjoaa seuraavat tietoyhteydet:

* Excel
* Teksti/CSV
* XML
* JSON
* Kansio
* SharePoint-kansio

Seuraavassa kuvassa näkyy **Tiedosto**-luokan **Nouda tiedot** -ikkuna.

![](media/desktop-data-sources/data-sources_3.png)

> [!NOTE]
> Power BI Desktopin aiemmissa versioissa **CSV** ja **Teksti** olivat erillisiä tietoyhteystyyppejä. Nämä tietoyhdistimet on yhdistetty **CSV/teksti**-luokaksi.
> 
> 

**Tietokanta**-luokka tarjoaa seuraavat tietoyhteydet:

* SQL Server -tietokanta
* Access-tietokanta
* SQL Server Analysis Services -tietokanta
* Oracle-tietokanta
* IBM DB2 -tietokanta
* IBM Informix -tietokanta (beeta)
* IBM Netezza
* MySQL-tietokanta
* PostgreSQL-tietokanta
* Sybase-tietokanta
* Teradata-tietokanta
* SAP HANA -tietokanta
* SAP Business Warehouse -sovelluspalvelin
* SAP Business Warehouse -viestipalvelin (beeta)
* Amazon Redshift
* Impala
* Google BigQuery (beeta)
* Snowflake

> [!NOTE]
> Jotkin tietokannan yhdistimet edellyttävät, että otat ne käyttöön valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset** ja valitsemalla **Esikatselutoiminnot** ja ottamalla yhdistin käyttöön. Jos et näe joitakin edellä mainituista yhdistimistä ja haluat käyttää niitä, tarkista **Esikatselutoiminnot**-asetukset. Huomaa myös, että tietolähteen, jolla on merkintä *beeta* tai *esikatselu*, tuki ja toiminnallisuus ovat rajoitettua, eikä sitä tulisi käyttää tuotantoympäristössä.
> 
> 

Seuraavassa kuvassa näkyy **Tietokanta**-luokan **Nouda tiedot** -ikkuna.

![](media/desktop-data-sources/data-sources_4.png)

**Azure**-luokka tarjoaa seuraavat tietoyhteydet:

* Azure SQL -tietokanta
* Azure SQL Data Warehouse
* Azure Analysis Services -tietokanta
* Azure Blob -säilö
* Azure-taulukkosäilö
* Azure Cosmos DB (beeta)
* Azure Data Lake Store
* Azure HDInsight (HDFS)
* Azure HDInsight Spark (beeta)
* HDInsight Interactive Query (beeta)

Seuraavassa kuvassa näkyy **Azure**-luokan **Nouda tiedot** -ikkuna.

![](media/desktop-data-sources/data-sources_5.png)

**Online-palvelut**-luokka tarjoaa seuraavat tietoyhteydet:

* Power BI -palvelu
* SharePoint Online -luettelo
* Microsoft Exchange Online
* Dynamics 365 (online)
* Dynamics NAV (beeta)
* Dynamics 365 for Financials (beeta)
* Common Data Service (beeta)
* Microsoft Azure Consumption Insights (beeta)
* Visual Studio Team Services (beeta)
* Salesforce-objektit
* Salesforce-raportit
* Google Analytics
* Adobe Analytics
* appFigures (beeta)
* comScore Digital Analytix (beeta)
* Dynamics 365 for Customer Insights (beeta)
* Data.World – nouda tietojoukko (beeta)
* Facebook
* GitHub (beeta)
* MailChimp (beeta)
* Marketo (beeta)
* Mixpanel (beeta)
* Planview Enterprise One - PRM (beeta)
* Planview Projectplace (beeta)
* QuickBooks Online (beeta)
* Smartsheet
* SparkPost (beeta)
* Stripe (beeta)
* SweetIQ (beeta)
* Planview Enterprise One - CMT (beeta)
* Twilio (beeta)
* tyGraph (beeta)
* Webtrends (beeta)
* Zendesk (beeta)

Seuraavassa kuvassa näkyy **Online-palvelut**-luokan **Nouda tiedot** -ikkuna.

![](media/desktop-data-sources/data-sources_6b.png)

**Muut**-luokka tarjoaa seuraavat tietoyhteydet:

* Vertica (beeta)
* Kusto (beeta)
* Verkko
* SharePoint List
* OData-syöte
* Active Directory
* Microsoft Exchange
* Hadoop-tiedosto (HDFS)
* Spark (beeta)
* R-komentosarja
* ODBC
* OLE DB
* Tyhjä kysely

Seuraavassa kuvassa näkyy **Muut**-luokan **Nouda tiedot** -ikkuna.

![](media/desktop-data-sources/data-sources_7a.png)

> [!NOTE]
> Tällä hetkellä ei ole mahdollista muodostaa yhteyttä mukautettuihin tietolähteisiin, jotka suojattu Azure Active Directorylla.
> 
> 

## <a name="connecting-to-a-data-source"></a>Yhteyden muodostaminen tietolähteeseen
Jos haluat muodostaa yhteyden tietolähteeseen, valitse tietolähde **Nouda tiedot** -ikkunassa ja valitse **Muodosta yhteys**. Seuraavassa kuvassa **Muut**-tietoyhteysluokasta on valittu **WWW**.

![](media/desktop-data-sources/data-sources_7b.png)

Näyttöön tulee tietoyhteyden mukainen yhteysikkuna. Jos tunnistetietoja vaaditaan, sinua pyydetään antamaan ne. Seuraavassa kuvassa näytetään URL-osoitteen kirjoittaminen WWW-tietolähteeseen yhdistämistä varten.

![](media/desktop-data-sources/datasources_fromwebbox.png)

Kun URL-osoite tai resurssiyhteyden tiedot on annettu, valitse **OK**. Power BI Desktop muodostaa yhteyden tietolähteeseen ja esittää saatavilla olevat tietolähteet **siirtymistoiminnossa**.

![](media/desktop-data-sources/datasources_fromnavigatordialog.png)

Voit joko ladata tiedot valitsemalla **Lataa**-painike **Siirtymistoiminto**-ruudun alareunassa tai muokata kyselyä ennen tietojen lataamista valitsemalla **Muokkaa**-painike.

Tietolähteisiin yhdistäminen Power BI Desktopissa ei muuta vaadi! Yritä muodostaa yhteys tietoihin kasvavassa tietolähteiden valikoimassa ja tarkista päivitetyt tiedot – kasvatamme tätä luetteloa koko ajan.

## <a name="next-steps"></a>Seuraavat vaiheet
Voit tehdä kaikenlaista Power BI Desktopilla. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](desktop-query-overview.md)
* [Tietotyypit Power BI Desktopissa](desktop-data-types.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)    