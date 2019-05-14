---
title: Yhdyskäytävän suorituskyvyn valvonnan (julkinen esikatseluversio)
description: Tässä artikkelissa on tietoja toiminnan paikallisen tietojen yhdyskäytävän suorituskyvyn valvonnan.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 05/08/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 8c5f4170383f31ea465ebb7035aebfb53f551982
ms.sourcegitcommit: af2b2238fe77eaa1b2392a19a143a0250b8665cf
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/11/2019
ms.locfileid: "65535363"
---
# <a name="gateway-performance-monitoring-public-preview"></a>Yhdyskäytävän suorituskyvyn valvonnan (julkinen esikatseluversio)

Valvomaan suorituskyvyn yhdyskäytävän järjestelmänvalvojia on perinteisesti riippuvaisia valvonta manuaalisesti suorituskykylaskurit Windowsin suorituskyvyn valvonta-työkalulla. Tarjoamme nyt kyselyn kirjaaminen ja [yhdyskäytävän suorituskyky PBI-mallitiedosto](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) Visualisoi tulokset. Tämä ominaisuus tarjoaa uusia merkityksellisiä tietoja yhdyskäytävän käytöstä ja mahdollistaa hitaasti suoritettavien kyselyiden vianmääritys.

> [!NOTE]
> Tämä ominaisuus on tällä hetkellä käytettävissä vain paikallisen tietoyhdyskäytävän normaalissa tilassa, ei henkilökohtaista tilaa.

## <a name="enable-performance-logging"></a>Ota suorituskyvyn lokiin kirjaaminen käyttöön

Tämän ominaisuuden käyttöön, tee seuraavat muutokset *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* tiedoston ”\Program Files\On-paikallisen tietoyhdyskäytävän” kansio:

1. Päivitä **QueryExecutionReportOn** - _True_ käyttöön oleville kyselyille yhdyskäytävän lokiin. Tämän asetuksen ottaminen käyttöön Luo kyselyn suorittamisen raportin ja kyselyn suorittamisen koosteen raporttitiedot.

   ``` xml
   <setting name="QueryExecutionReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Päivitys **SystemCounterReportOn** - _True_ käyttöön muistin ja suorittimen järjestelmän laskurit lokiin. Tämän asetuksen ottaminen käyttöön Luo järjestelmän laskuri koosteen raportin-tiedoston.

   ```xml
   <setting name="SystemCounterReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Web.config-tiedosto, voit päivittää tarvittaessa ei muita arvoja.

    - **ReportFilePath**: Määrittää polun, johon kolme lokitiedostoja on tallennettu. Oletusarvon mukaan tämä polku on ”\Users\PBIEgwService\AppData\Local\Microsoft\On-premises tietojen gateway\Report” tai ”Windows\ServiceProfiles\PBIEgwService\AppData\Local\Microsoft\On-premises data gateway\Report”, käyttöjärjestelmän version mukaan. Jos käytät palvelutili yhdyskäytävän muu kuin _PBIEgwService_, korvaa tämä osa polun palvelutilin nimi.
    - **ReportFileCount**: Määrittää sen säilyttämään kunkin laji lokitiedostojen määrä. Oletusarvo on 10.
    - **ReportFileSizeInBytes**: Määrittää sen säilyttämään koon. Oletusarvo on 104857600.
    - **QuerExecutionAggregationTimeInMinutes**: Määrittää, jonka kyselyn suorittamisen tiedot koostetaan minuuttien määrä. Oletusarvo on 5.
    - **SystemCounterAggregationTimeInMinutes**: Määrittää, jonka järjestelmän laskurit koostetaan minuuttien määrä. Oletusarvo on 5.

1. Kun olet tehnyt muutoksia Web.config-tiedosto, Käynnistä nämä määritysarvoille voimaan yhdyskäytävä uudelleen. Nyt alkaa määritetystä sijainnista muodostetaan raporttitiedot näytetään **ReportFilePath**.

    > [!NOTE]
    > Voi kestää jopa 10 minuuttia ja määrittää, kuinka paljon **QuerExecutionAggregationTimeInMinutes** määritystiedostossa, ennen kuin tiedostot-Aloita kansion näkyvissä.

## <a name="understand-performance-logs"></a>Tutustu Resurssilokien

Voit ottaa tämän ominaisuuden käyttöön, kun Luomme kolme uusien lokitiedostojen:

- Kyselyn suorittaminen raportti
- Kyselyn suorittaminen koosteen raportti
- Järjestelmän laskuri koosteen raportti

Kyselyn suorittaminen raportti sisältää yksityiskohtaisia kyselyn suorittamisen tiedot. Olemme siepata seuraavat määritteet:

|Määrite |Kuvaus |
| ---- | ---- |
|**GatewayObjectId** |Yhdyskäytävän yksilöivä tunnus. |
|**RequestId** |Yhdyskäytävän pyynnön yksilöivä tunnus. Se voi olla sama useita kyselyjä. |
|**Tietolähde** |Sisältää tietolähteen tyyppi ja tietolähde. |
|**QueryTrackingId** |Kyselyn yksilöivä tunnus. |  
|**QueryExecutionEndTimeUTC** |Aika, kun kyselyn suorittaminen on valmis. |
|**QueryExecutionDuration**(ms) |Kyselyn suorittaminen kesto. |
|**QueryType** |Kirjoita kyselyn - esiintymän, välitetty kysely voi Power BI-päivitys/DirectQuery tai Powerappsin ja Microsoft Flow-kyselyt. |
|**DataProcessingEndTimeUTC** |Aika, kun tietojen käsittely toiminnot esimerkiksi taustatulostuksen, tietojen nouto, pakkaus, tietojenkäsittelyn ja niin edelleen suorittaa. |
|**DataProcessingDuration**(ms) |Kesto tietojenkäsittelyn toimintoihin, kuten taustatulostuksen, tietojen nouto, pakkaus, tietojenkäsittelyn ja niin edelleen. |
|**Onnistui** |Ilmaisee, jos kysely onnistui tai epäonnistui. |
|**ErrorMessage** |Jos kysely epäonnistui, ilmaisee virhesanoma. |
| | |

Kyselyn suorittaminen koosteen raportti sisältää kyselyn tietoja koostaa aikaväli mukaan **GatewayObjectId**, **DataSource**, **onnistui**, ja **QueryType**. Oletusarvo on 5 minuuttia, mutta voit muuttaa alla olevan mukaisesti. Olemme siepata seuraavat määritteet:

|Määrite |Kuvaus |
| ---- | ---- |
|**GatewayObjectId** |Yhdyskäytävän yksilöivä tunnus. |
|**AggregationStartTimeUTC** |Aikaikkunan, jolle kyselyn määritteet koostaa alku. |
|**AggregationEndTimeUTC** |Mitä kyselyn määritteet koostaa aikaikkunan loppu. |
|**Tietolähde** |Sisältää tietolähteen tyyppi ja tietolähde. |
|**Onnistui** |Ilmaisee, jos kysely onnistui tai epäonnistui. |
|**AverageQueryExecutionDuration**(ms) |Koosteen aika-ikkuna kyselyiden keskimääräinen suoritusaika. |
|**MaxQueryExecutionDuration**(ms) |Kyselysivun koosteen aikaikkunan suoritusaika. |
|**MinQueryExecutionDuration**(ms) |Pienin kyselyn koosteen aikaikkunan suoritusaika. |
|**QueryType** |Kirjoita kyselyn - esiintymän, välitetty kysely voi Power BI-päivitys/DirectQuery tai Powerappsin ja Microsoft Flow-kyselyt. |
|**AverageDataProcessingDuration**(ms) |Keskimääräinen aika tietojenkäsittelyn toimintoihin, kuten taustatulostuksen tietojen nouto pakkaus, tietojen käsittely-ja niin edelleen koosteen aikaikkunan. |
|**MaxDataProcessingDuration**(ms) |Enimmäisaika tietojenkäsittelyn toimintoihin, kuten taustatulostuksen, tietojen nouto, pakkaus, tietojenkäsittelyn ja niin edelleen koosteen aikaikkunan. |
|**MinDataProcessingDuration**(ms) |Vähimmäisaika tietojenkäsittelyn toimintoihin, kuten taustatulostuksen, tietojen nouto, pakkaus, tietojenkäsittelyn ja niin edelleen koosteen aikaikkunan. |
|**Määrä** |Kyselyiden määrä. |
| | |

Järjestelmän laskuri koosteen raportti sisältää järjestelmän laskuri arvot aikaväli koostaa. Oletusarvo on 5 minuuttia, mutta voit muuttaa alla olevan mukaisesti. Olemme siepata seuraavat määritteet:

|Määrite |Kuvaus |
| ---- | ---- |
|**GatewayObjectId** |Yhdyskäytävän yksilöivä tunnus. |
|**AggregationStartTimeUTC** |Jonka järjestelmän laskurit on poistettu koostaa aikaikkunan alku. |
|**AggregationEndTimeUTC** |Mitä järjestelmän laskurit on poistettu koostaa aikaikkunan loppu. |
|**CounterName** |Järjestelmän laskurit, mukaan lukien muistin ja suorittimen yhdyskäytävän kooste, ja yleisen mukaan tietokoneen joka isännöi yhdyskäytävää. |
|**Max** |Järjestelmän laskuri koosteen aikaikkunan enimmäisarvo. |
|**Min** |Järjestelmän laskuri koosteen aikaikkunan vähimmäisarvo. |
|**Keskiarvo** |Järjestelmän laskuri koosteen aikaikkunan keskiarvo. |
| | |

## <a name="visualize-gateway-performance"></a>Visualisoi yhdyskäytävän suorituskyky

Voit nyt visualisoida tietoja, jotka on lokitiedostoissa.

1. Lataa [yhdyskäytävän suorituskyky PBI-mallin](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) ja avaa se Power BI Desktopilla.

1. Tarkista tulevassa valintaikkunassa kansiopolku vastaa arvo **ReportFilePath**.

    ![Kansiopolku ponnahdusikkuna](media/service-gateway-performance-monitoring/gateway-folder-path-pop-up.png)

1. Valitse **lataaminen**, ja mallitiedosto alkaa Lokitiedostosi tiedot ladataan. Kaikkia visualisointeja tulee sitten voi täyttää tiedot raporteissa.

1. Voit myös tallentaa tämän tiedoston PBIX ja julkaise se Automaattiset päivitykset-palvelusi.

Lisäksi voit mukauttaa tätä mallitiedostoa omien tarpeidesi mukaan. Katso lisätietoja Power BI-mallit tämä [Microsoft Power BI-blogimerkintä](https://powerbi.microsoft.com/en-us/blog/deep-dive-into-query-parameters-and-power-bi-templates/).