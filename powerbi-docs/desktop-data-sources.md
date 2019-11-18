---
title: Power BI Desktopin tietolähteet
description: Power BI Desktopin tietolähteet
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/25/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c363e63a7354c2a8c66099a98cb441ce2c94becf
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878379"
---
# <a name="data-sources-in-power-bi-desktop"></a>Power BI Desktopin tietolähteet
Power BI Desktopin avulla voit yhdistää tietoja monista eri lähteistä. Täydellinen luettelo käytettävissä olevista tietolähteistä on tämän sivun alareunassa.

Muodosta yhteys tietoihin valitsemalla **Aloitus**-valintanauhassa **Nouda tiedot**. Jos valitset alanuolen tai **Nouda tiedot** -painikkeen, näyttöön tulee **yleisimpien** tietotyyppien valikko, joka näkyy seuraavassa kuvassa:

![Nouda tiedot Power BI Desktopissa](media/desktop-data-sources/data-sources-01.png)

Valitsemalla **Lisää...** **Yleisimmät**-valikossa saat **Nouda tiedot** -ikkunan näkyviin. Voit myös tuoda **Nouda tiedot** -ikkunan (ja ohittaa **Yleisimmät**-valikon) valitsemalla suoraan **Nouda tiedot** **-kuvakepainikkeen**.

![Nouda tiedot -painike](media/desktop-data-sources/data-sources-02.png)

> [!NOTE]
> Power BI -tiimi laajentaa jatkuvasti **Power BI Desktopin** ja **Power BI -palvelun** käytettävissä olevia tietolähteitä. Näet näin ollen usein keskeneräisten tietolähteiden varhaisia versioita, joissa on merkintä *beeta* tai *esikatselu*. Tietolähteen, jolla on merkintä *beeta* tai *esikatselu*, tuki ja toiminnallisuus ovat rajoitettua, eikä sitä tulisi käyttää tuotantoympäristössä. 

> Lisäksi mikään *Beeta-* tai *Esikatselu*-merkinnällä varustettu **Power BI Desktop** -sisältö ei ehkä ole käytettävissä **Power BI -palvelussa** tai muissa Microsoftin palveluissa ennen kuin tietolähde on yleisesti saatavana (GA).

## <a name="data-sources"></a>Tietolähteet
Kaikki tietotyypit on järjestelty seuraaviin luokkiin:

* Kaikki
* Tiedosto
* Tietokanta
* Power BI
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
* PDF
* SharePoint-kansio

Seuraavassa kuvassa näkyy **Tiedosto**-luokan **Nouda tiedot** -ikkuna.

![Nouda tiedot > Tiedosto](media/desktop-data-sources/data-sources-03.png)

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
* Teradata
* SAP HANA -tietokanta
* SAP Business Warehouse -sovelluspalvelin
* SAP Business Warehouse -viestipalvelin
* Amazon Redshift
* Impala
* Google BigQuery
* Vertica
* Snowflake
* Essbase
* AtScale-kuutiot (beeta)
* BI-liitin
* Dremio
* Exasol
* Indexima (beeta)
* InterSystems IRIS (beeta)
* Jethro (beeta)
* Kyligence Enterprise (beeta)
* MarkLogic (beeta)

> [!NOTE]
> Jotkin tietokannan yhdistimet edellyttävät, että otat ne käyttöön valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset** ja valitsemalla **Esikatselutoiminnot** ja ottamalla yhdistin käyttöön. Jos et näe joitakin edellä mainituista yhdistimistä ja haluat käyttää niitä, tarkista **Esikatselutoiminnot**-asetukset. Huomaa myös, että tietolähteen, jolla on merkintä *beeta* tai *esikatselu*, tuki ja toiminnallisuus ovat rajoitettua, eikä sitä tulisi käyttää tuotantoympäristössä.

Seuraavassa kuvassa näkyy **Tietokanta**-luokan **Nouda tiedot** -ikkuna.

![Nouda tiedot > Tietokannat](media/desktop-data-sources/data-sources-04.png)

**Power Platform** -luokka tarjoaa seuraavat tietoyhteydet:

* Power BI -tietojoukot
* Power BI -tietovuot
* Common Data Service
* Power Platform -tietovuo (beeta)

Seuraavassa kuvassa näkyy **Power Platform** -luokan **Nouda tiedot** -ikkuna.

![Nouda tiedot > Power BI](media/desktop-data-sources/data-sources-05.png)

**Azure**-luokka tarjoaa seuraavat tietoyhteydet:

* Azure SQL -tietokanta
* Azure SQL Data Warehouse
* Azure Analysis Services -tietokanta
* Azure Blob -säilö
* Azure-taulukkotallennus
* Azure Cosmos DB
* Azure Data Lake Storage Gen2 (beeta)
* Azure Data Lake Storage Gen1
* Azure HDInsight (HDFS)
* Azure HDInsight Spark
* HDInsight Interactive Query
* Azure Data Explorer (Kusto)
* Azure Cost Management (beeta)

Seuraavassa kuvassa näkyy **Azure**-luokan **Nouda tiedot** -ikkuna.

![Nouda tiedot > Azure](media/desktop-data-sources/data-sources-06.png)

**Online-palvelut**-luokka tarjoaa seuraavat tietoyhteydet:

* SharePoint Online -luettelo
* Microsoft Exchange Online
* Dynamics 365 (online)
* Dynamics NAV
* Dynamics 365 Business Central
* Dynamics 365 Business Central (paikallinen)
* Microsoft Azure Consumption Insights (beeta)
* Azure DevOps (beeta)
* Azure DevOps Server (beeta)
* Salesforce-objektit
* Salesforce-raportit
* Google Analytics
* Adobe Analytics
* appFigures (beeta)
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
* Dynamics 365 Customer Insights (beeta)
* Emigo-tietolähde (beeta)
* Entersoft Business Suite (beeta)
* App Store teollisuuskäyttöön
* Intune-tietovarasto (beeta)
* Microsoft Graph Security (beeta)
* Quick Base
* TeamDesk (beeta)


Seuraavassa kuvassa näkyy **Online-palvelut**-luokan **Nouda tiedot** -ikkuna.

![Nouda tiedot > Online-palvelut](media/desktop-data-sources/data-sources-07.png)

**Muut**-luokka tarjoaa seuraavat tietoyhteydet:

* Verkko
* SharePoint List
* OData-syöte
* Active Directory
* Microsoft Exchange
* Hadoop-tiedosto (HDFS)
* Spark
* R-komentosarja
* Python-komentosarja
* ODBC
* OLE DB
* BI360 – Budjetointi- ja talousraportointi (beeta)
* Denodo
* Tietoruudukko (beeta)
* Paxata 
* QubolePresto (beeta)
* Roamler (beeta)
* SurveyMonkey (beeta)
* Tenforce (Smart)List (beeta)
* Työvoiman dimensiot (beeta)
* Tyhjä kysely

Seuraavassa kuvassa näkyy **Muut**-luokan **Nouda tiedot** -ikkuna.

![Nouda tiedot > Muut](media/desktop-data-sources/data-sources-08.png)

> [!NOTE]
> Tällä hetkellä ei ole mahdollista muodostaa yhteyttä mukautettuihin tietolähteisiin, jotka suojattu Azure Active Directorylla.

## <a name="connecting-to-a-data-source"></a>Yhteyden muodostaminen tietolähteeseen
Jos haluat muodostaa yhteyden tietolähteeseen, valitse tietolähde **Nouda tiedot** -ikkunassa ja valitse **Muodosta yhteys**. Seuraavassa kuvassa **Muut**-tietoyhteysluokasta on valittu **WWW**.

![Yhdistä verkkoon](media/desktop-data-sources/data-sources-08.png)

Näyttöön tulee tietoyhteyden mukainen yhteysikkuna. Jos tunnistetietoja vaaditaan, sinua pyydetään antamaan ne. Seuraavassa kuvassa näytetään URL-osoitteen kirjoittaminen WWW-tietolähteeseen yhdistämistä varten.

![syötä URL-verkko-osoite](media/desktop-data-sources/datasources-fromwebbox.png)

Kun URL-osoite tai resurssiyhteyden tiedot on annettu, valitse **OK**. Power BI Desktop muodostaa yhteyden tietolähteeseen ja esittää saatavilla olevat tietolähteet **siirtymistoiminnossa**.

![Siirtymistoimintonäyttö](media/desktop-data-sources/datasources-fromnavigatordialog.png)

Voit joko ladata tiedot valitsemalla **Lataa**-painike **Siirtymistoiminto**-ruudun alareunassa tai muokata kyselyä ennen tietojen lataamista valitsemalla **Muokkaa**-painike.

Tietolähteisiin yhdistäminen Power BI Desktopissa ei muuta vaadi! Yritä muodostaa yhteys tietoihin kasvavassa tietolähteiden valikoimassa ja tarkista päivitetyt tiedot – kasvatamme tätä luetteloa koko ajan.

## <a name="using-pbids-files-to-get-data"></a>Tietojen hakeminen PBIDS-tiedostojen avulla

PBIDS-tiedostot ovat Power BI Desktop -tiedostoja, joilla on tietty rakenne ja joilla on .PBIDS-tiedostotunniste merkkinä siitä, että ne ovat Power BI -tietolähdetiedostoja.

Voit luoda .PBIDS-tiedoston tehostaaksesi **tietojen hakemista** organisaatiossasi raportteja luoville käyttäjille. On suositeltavaa, että järjestelmänvalvojat luovat nämä tiedostot yleisesti käytetyille yhteyksille. Tämä helpottaa PBIDS-tiedostojen käyttöä uusille raportin tekijöille. 

Kun tekijä avaa .PBIDS-tiedoston, Power BI Desktop avautuu ja kysyy käyttäjältä tunnistetietoja, joilla todennetaan ja muodostetaan yhteys tiedostossa määritettyyn tietolähteeseen. Näyttöön avautuu siirtymisikkuna, jossa käyttäjän täytyy valita tietolähteestä taulukot, jotka ladataan malliin. Käyttäjien on ehkä myös valittava tietokanta, jos sitä ei ole määritetty PBIDS-tiedostossa. 

Tämän jälkeen käyttäjä voi aloittaa visualisointien luomisen tai käydä uudelleen *Viimeaikaiset lähteet* -näkymässä lataamassa malliin uuden joukon taulukoita. 

Tällä hetkellä .PBIDS-tiedostot tukevat vain yhtä tietolähdettä yhdessä tiedostossa. Jos määrität useita tietolähteitä, tämä aiheuttaa virheen. 

Luodakseen .PBIDS-tiedoston järjestelmänvalvojan täytyy määrittää yhden yhteyden vaaditut annettavat tiedot sekä yhteystila. Se voi olla **DirectQuery**-tila tai **tuontitila**. Jos **tila** puuttuu tiedostosta tai on nolla-arvoinen, Power BI Desktopissa tiedoston avaavaa käyttäjää pyydetään valitsemaan joko DirectQuery-tila tai tuontitila. 

### <a name="pbids-file-examples"></a>Esimerkkejä PBIDS-tiedostoista

Tämä osio sisältää joitain esimerkkejä usein käytetyistä tietolähteistä. .PBIDS-tiedostotyyppi tukee vain tietoyhteyksiä, joita tuetaan myös Power BI Desktopissa, mutta tässä on kaksi poikkeusta: reaaliaikainen yhteys ja tyhjä kysely. 

.PBIDS-tiedosto *ei* sisällä todennustietoja, taulukkotietoja tai rakennetietoja.  

Alla on useita esimerkkejä .PBIDS-tiedostosta, mutta nämä ovat vain esimerkkejä, ei täydellinen luettelo. Jos käytät muita tietolähteitä, voit tarkistaa [Data Source Reference (DSR) -muodon protokolla- ja osoitetiedot](https://docs.microsoft.com/azure/data-catalog/data-catalog-dsr#data-source-reference-specification).

Nämä esimerkit on tarkoitettu vain malliksi. Tämä ei ole kattava luettelo eikä tämä sisällä kaikkia DSR-muodon tuettuja liittimiä. Järjestelmänvalvojat ja organisaatiot voivat luoda näiden esimerkkien pohjalta omia tietolähteitään, joista he voivat luoda omia tietolähdetiedostoja sekä tukea niitä. 


**Azure AS**
```
{ 
    "version": "0.1", 
    "connections": [ 
    { 
        "details": { 
        "protocol": "analysis-services", 
        "address": { 
            "server": "server-here" 
        }, 
        } 
    } 
    ] 
}
```


 

**Kansio**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "folder", 
        "address": { 
            "path": "folder-path-here" 
        } 
      } 
    } 
  ] 
} 
```

**OData**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "odata", 
        "address": { 
            "url": "URL-here" 
        } 
      } 
    } 
  ] 
} 
```
 
**SAP BW**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sap-bw-olap", 
        "address": { 
          "server": "server-name-here", 
          "systemNumber": "system-number-here", 
          "clientId": "client-id-here" 
        }, 
      } 
    } 
  ] 
} 
```
 
**SAP Hana**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sap-hana-sql", 
        "address": { 
          "server": "server-name-here:port-here" 
        }, 
      } 
    } 
  ] 
} 
```

**SharePoint-luettelo**

URL-osoitteen täytyy osoittaa itse SharePoint-sivustoon, ei luetteloon sivustossa. Käyttäjät saavat käyttöönsä siirtymistoiminnon, jossa he voivat valita luetteloita sivustosta. Näistä luetteloista tulee taulukoita mallissa. 
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sharepoint-list", 
        "address": { 
          "url": "URL-here" 
        }, 
       } 
    } 
  ] 
} 
```
 
 
**SQL Server**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "tds", 
        "address": { 
          "server": "server-name-here", 
          "database": "db-name-here (optional) "
        } 
      }, 
      "options": {}, 
      "mode": "DirectQuery" 
    } 
  ] 
} 
```
 

**Tekstitiedosto**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "file", 
        "address": { 
            "path": "path-here" 
        } 
      } 
    } 
  ] 
} 
```
 

**Verkko**
```
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "http", 
        "address": { 
            "url": "URL-here" 
        } 
      } 
    } 
  ] 
} 
```
 

**Tietovuo**
```
{
  "version": "0.1",
  "connections": [
    {
      "details": {
        "protocol": "powerbi-dataflows",
        "address": {
          "workspace":"workspace id (Guid)",
          "dataflow":"optional dataflow id (Guid)",
          "entity":"optional entity name"
        }
       }
    }
  ]
}
```


## <a name="next-steps"></a>Seuraavat vaiheet
Voit tehdä kaikenlaista Power BI Desktopilla. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](desktop-query-overview.md)
* [Tietotyypit Power BI Desktopissa](desktop-data-types.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)    
