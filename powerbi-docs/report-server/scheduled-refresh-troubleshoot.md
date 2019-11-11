---
title: Ajoitetun päivityksen vianmääritys Power BI -raporttipalvelimessa
description: Tässä artikkelissa kerrotaan resursseista, joita on saatavilla ajoitetun päivityksen vianmääritykseen Power BI -raporttipalvelimessa.
author: mgblythe
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: troubleshooting
ms.date: 11/01/2017
ms.author: mblythe
ms.openlocfilehash: 37eb5c0e68a6895ac105cc7f12d3353c04641204
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874043"
---
# <a name="troubleshoot-scheduled-refresh-in-power-bi-report-server"></a>Ajoitetun päivityksen vianmääritys Power BI -raporttipalvelimessa
Tässä artikkelissa kerrotaan resursseista, joita on saatavilla ajoitetun päivityksen vianmääritykseen Power BI -raporttipalvelimessa.

Tätä artikkelia päivitetään hyödyllisillä tiedoilla sitä mukaa kuin ongelmia ilmenee.

## <a name="common-issues"></a>Yleisiä ongelmia
Seuraavat ovat yleisimpiä ongelmia, joita voit kohdata, kun yrität ajoittaa päivitystä raportille. 

### <a name="driver-related-problems"></a>Ohjaimeen liittyvät ongelmat
Yhdistäminen eri tietolähteisiin voi edellyttää kolmannen osapuolen ohjaimia, jotka on asennettava yhteyden onnistumiseksi. Sinun on asennettava ne laitteelle, jolla käytät Power BI Desktopia, mutta tämän lisäksi sinun on varmistettava, että ohjain on asennettu raporttipalvelimeen.

Ohjain voi olla 32-bittinen tai 64-bittinen. Varmista, että asennat 64-bittisen ohjaimen, sillä Power BI -raporttipalvelin on 64-bittinen.

Lisätietoja kolmansien osapuolten ohjainten asentamisesta ja määrittämisestä saat valmistajalta.

### <a name="memory-pressure"></a>Muistipaine
Muistipainetta voi ilmetä, kun raportit edellyttävät enemmän muistia käsittelyyn ja hahmontamiseen. Raporttien ajoitettu päivitys voi vaatia merkittävän määrän tietokoneen muistia. Erityisesti suurempien raporttien osalta. Muistipaine voi johtaa raporttivirheisiin sekä raporttipalvelimen itsensä mahdolliseen kaatumiseen.

Jos muistipainetta ilmenee jatkuvasti, voi olla tarpeen harkita raporttipalvelimen skaalattua käyttöönottoa resurssien kuormituksen jakamiseksi. Voit myös määrittää, että tiettyä raporttipalvelinta käytetään tietojen päivitykseen asetuksen `IsDataModelRefreshService` kanssa tiedostossa rsreportserver.config. Tällä asetuksella voit määrittää yhden tai useamman palvelimen edustapalvelimiksi, jotka käsittelevät raportteja pyydettäessä, ja pitää toisen palvelimien joukon pelkästään ajoitettujen päivitysten käytössä.

Lisätietoja Analysis Services -esiintymän seurannasta on kohdassa [Analysis Services -esiintymän seuranta](https://docs.microsoft.com/sql/analysis-services/instances/monitor-an-analysis-services-instance).

Katso Analysis Services -muistiasetuksia koskevia tietoja kohdasta [Muistin ominaisuudet](https://docs.microsoft.com/sql/analysis-services/server-properties/memory-properties).

### <a name="kerberos-configuration"></a>Kerberos-määritys
Tietolähteeseen yhdistäminen Windows-tunnistetiedoilla voi vaatia rajoitetun Kerberos-delegoinnin määrittämistä yhteyden onnistumiseksi. Katso lisätietoja rajoitetun Kerberos-delegoinnin määrittämisestä kohdasta [Määritä Kerberos Power BI -raporttien käyttöön](configure-kerberos-powerbi-reports.md).

## <a name="known-issues"></a>Tunnetut ongelmat
Tietoja tunnetuista ongelmista luetellaan tähän, kun niitä tulee saataville.

## <a name="configuration-settings"></a>Määritysasetukset
Seuraavien asetusten avulla voidaan vaikuttaa ajoitettuun päivitykseen. SQL Server Management Studiossa (SSMS) määritetyt asetukset koskevat kaikkia raporttipalvelimia skaalauskäyttöönotossa. Tiedostossa rsreportserver.config määritetyt asetukset koskevat tiettyä palvelinta, johon ne on määritetty.

**SSMS:n asetukset:**

| Asetus | Kuvaus |
| --- | --- |
| MaxFileSizeMb |Ladattujen raporttien suurin sallittu tiedostokoko. Oletus on 1 000 Mt (1 Gt). Suurin sallittu arvo on 2 000 Mt (2 Gt). |
| ModelCleanupCycleMinutes |Määrittää, kuinka usein malli tarkistetaan sen häätämiseksi muistista. Oletus on 15 minuuttia. |
| ModelExpirationMinutes |Määrittää ajan siihen, kunnes malli vanhenee viimeisimmän käyttöajan perusteella ja se häädetään. Oletus on 60 minuuttia. |
| ScheduleRefreshTimeoutMinutes |Määrittää, kuinka kauan tietojen päivitys voi kestää tilaa kohden. Oletus on 120 minuuttia. Ylärajaa ei ole. |

**Asetukset tiedostossa rsreportserver.config:**

```xml
<Configuration>
    <Service>
        <PollingInterval>10</PollingInterval>
        <IsDataModelRefreshService>false</IsDataModelRefreshService>
        <MaxQueueThreads>0</MaxQueueThreads>
    </Service>
</Configuration>
```

## <a name="tools-for-troubleshooting"></a>Työkalut vianmääritykseen
### <a name="logs-relevant-for-scheduled-refresh-of-power-bi-reports"></a>Power BI -raporttien ajoitetun päivityksen kannalta olennaiset lokit
Lokitiedostot, joissa on tietoja ajoitetusta päivityksestä, ovat RSPowerBI_ logs. Ne sijaitsevat raporttipalvelimesi asennussijainnin LogFiles-kansiossa. 

```
C:\Program Files\Microsoft Power BI Report Server\PBIRS\LogFiles\RSPowerBI_*.log
```

**Virhetilanne**

```
2017-10-20 02:00:09.5188|ERROR|744|Error Processing Data Model Refresh: SessionId: e960c25e-ddd4-4763-aa78-0e5dceb53472, Status: Error Model can not be refreshed because not all the data sources are embedded, Exception Microsoft.PowerBI.ReportServer.AsServer.InvalidDataSourceException: Model can not be refreshed because not all the data sources are embedde
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.CanModelRefresh(IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

***Onnistunut päivitys***

```
2017-10-25 15:23:41.9370|INFO|6|Handling event with data: TimeEntered: 10/25/2017 8:23:41 PM, Type: Event, SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, EventType: DataModelRefresh
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Data Refresh.
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Retrieving PBIX AsDatabaseInfo.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying all the data sources are embedded.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying connection strings are valid.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Streaming model to Analysis Server.
2017-10-25 15:23:42.7603|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Refreshing the model.
2017-10-25 15:23:51.5258|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Removing credentials from the model.
2017-10-25 15:23:51.6508|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Saving model to the catalog.
```

**Virheelliset tunnistetiedot**

```
2017-10-20 08:22:01.5595|INFO|302|Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Starting Refreshing the model.
2017-10-20 08:22:02.3758|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed to refresh the model, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.AnalysisServices.Tabular.Model.SaveChanges(SaveOptions saveOptions)
   at Microsoft.PowerBI.ReportServer.AsServer.TOMWrapper.RefreshModel(Database database)
   at Microsoft.PowerBI.ReportServer.AsServer.AnalysisServicesServer.RefreshDatabase(String databaseName, IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshDatabase(AsDatabaseInfo asDatabaseInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
2017-10-20 08:22:02.4588|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed Data Refresh, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.ExecuteActionWithLogging(Action methodToExecute, String description, String localizedDescription, String messageInFailure, RefreshInfo refreshInfo, DataAccessors dataAccessors, ReportEventType operation, Int64 size, Boolean isDataRetrieval, Boolean showInExecutionLog)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshData(RefreshInfo refreshInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

#### <a name="enabling-verbose-logging"></a>Yksityiskohtaisen kirjaamisen käyttöönotto
Yksityiskohtaisen kirjaamisen käyttöönotto Power BI -raporttipalvelimessa on sama kuin kohteessa SQL Server Reporting Services.

1. Avaa `<install directory>\PBIRS\ReportServer\bin\ReportingServicesService.exe.config`.
2. Kohdassa `<system.diagnostics>` muuta **DefaultTraceSwitch** seuraavaksi: **4**.
3. Kohdassa `<RStrace>` muuta **Osat** seuraavaksi: **all:4**. 

### <a name="executionlog"></a>ExecutionLog
Aina kun Power BI -raportti on hahmonnettu tai ajoitettua päivitystä koskeva suunnitelma on suoritettu, tietokannan suorituslokiin lisätään uusia merkintöjä. Nämä merkinnät ovat käytettävissä **ExecutionLog3**-näkymässä raporttipalvelimen luettelotietokannassa.

Power BI -raporttien suorituslokimerkinnät eroavat muuntyyppisten raporttien merkinnöistä.

* TimeRendering-sarakkeet ovat aina 0. Power BI -raporttien hahmontaminen tapahtuu selaimessa, ei palvelimessa.
* On 2 pyyntötyyppiä sekä niitä seuraavat kohdetoiminnot:
  * **Interactive**: aina, kun raporttia tarkastellaan.
    * **ASModelStream**: kun tietomalli virtautetaan luettelosta Analysis Servicesiin.
    * **ConceptualSchema**: kun käyttäjä napsauttaa raportin tarkastelua.
    * **QueryData**: aina, kun asiakkaalta pyydetään tietoja.
  * **Refresh Cache**: aina, kun ajoitettua päivitystä koskeva suunnitelma on suoritettu.
    * **ASModelStream**: aina, kun tietomalli virtautetaan luettelosta Analysis Servicesiin.
    * **DataRefresh**: aina, kun tietoja päivitetään yhdestä tai useammasta tietolähteestä.
    * **SaveToCatalog**: aina, kun tietomallia tallennetaan takaisin luetteloon.

## <a name="analysis-services"></a>Analysis Services
Haluat ehkä toisinaan muokata Analysis Servicesiä vianmääritystä varten tai säätää muistirajoituksia.

> [!IMPORTANT]
> Nämä asetukset palautetaan joka kerta, kun päivität raporttipalvelinta. Varmista, että säilytät kopion muutoksistasi, ja käytä niitä uudelleen tarvittaessa.
> 
> 

### <a name="install-location"></a>Asennuksen sijainti
Power BI -raporttipalvelimen ja Analysis Servicesin oletussijainti on seuraava.

`C:\Program Files\Microsoft Power BI Report Server\PBIRS\ASEngine`

### <a name="configuring-analysis-services-settings-msmdsrvini"></a>Analysis Services -asetusten (msmdsrv.ini) määrittäminen
Hakemistossa `<install directory>\PBIRS\ASEngine` on *msmdsrv.ini*-tiedosto, jonka avulla voit hallita erilaisia Analysis Services -asetuksia. Kun avaat tämän tiedoston, huomaat heti, ettei tässä tiedostossa ole kaikkia asetuksia, joita msmdsrv.ini-tiedostolta voisi odottaa. 

Tämä johtuu siitä, että todellinen Analysis Services -prosessi, jota Power BI -raporttipalvelin suorittaa, käynnistetään kohteessa `<install directory>\PBIRS\ASEngine\workspaces`. Kyseisessä kansiossa näet täydellisen *msmdsrv.ini*-tiedoston, johon olet tottunut. On tärkeää olla muokkaamatta tiedostoa työtilat-kansiossa, sillä se kirjoitetaan uudelleen aina, kun Analysis Services -prosessi käynnistyy. Jos haluat hallita jotakin asetusta, tee se muokkaamalla msmdsrv.ini-tiedostoa `<install directory>\PBIRS\ASEngine`-hakemistossa.

Seuraavat asetukset palautetaan aina, kun Analysis Services -prosessi käynnistetään. Kaikki niihin tekemäsi muutokset ohitetaan.

* ConfigurationSettings\PrivateProcess
* ConfigurationSettings\DataDir
* ConfigurationSettings\DataDir
* ConfigurationSettings\DataDir
* ConfigurationSettings\DataDir
* ConfigurationSettings\AllowedBrowsingFolders
* ConfigurationSettings\CrashReportsFolder
* ConfigurationSettings\DataDir
* ConfigurationSettings\Port
* ConfigurationSettings\DeploymentMode
* ConfigurationSettings\ServerLocation
* ConfigurationSettings\TMCompatabilitySKU
* ConfigurationSettings\FlightRecorder\TraceDefinitionFile

### <a name="profiling-the-local-analysis-services-process"></a>Paikallisen Analysis Services -prosessin profilointi
SQL-profiloinnin jäljitys voidaan suorittaa paikallisessa Analysis Services -prosessissa vianmääritystä varten. Voit muodostaa yhteyden paikalliseen Analysis Services -esiintymään toimimalla seuraavasti.

SQL Serverin profiloinnin jäljitys sisältyy [SQL Server Management Studion (SSMS) lataukseen](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms).

1. Aloita **SQL Serverin profilointi** järjestelmänvalvojana.
2. Valitse **Uusi jäljitys** -painike.
3. Valitse **Yhdistä palvelimeen** -valintaikkunassa **Analysis Services** ja syötä palvelimen nimeksi **localhost:5132**.
4. Valitse **Jäljitysominaisuudet**-valintaikkunassa tapahtumat, jotka haluat siepata, ja valitse **Suorita**.

## <a name="lock-pages-in-memory-windows-privilege"></a>Windows-oikeus Muistissa olevien sivujen lukitseminen
Jos huomaat, että et voi hahmontaa Power BI -raporttia, oikeuden **Muistissa olevien sivujen lukitseminen** myöntämisestä Power BI -raporttipalvelinta suorittavalle palvelutilille voi olla apua. Lisätietoja oikeuden **Muistissa olevien tietojen lukitseminen** määrittämisestä on kohdassa [Analysis Services -palvelutilille kohdistetut Windows-oikeudet](https://docs.microsoft.com/sql/analysis-services/instances/configure-service-accounts-analysis-services#bkmk_winpriv).

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

