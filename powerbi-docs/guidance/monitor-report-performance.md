---
title: Raportin suorituskyvyn valvominen Power BI:ssä
description: Ohjeita raportin suorituskyvyn valvomiseen Power BI:ssä.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
ms.openlocfilehash: 9245dd6c25917b2c8c861ea5b83710cd8b52bb22
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279016"
---
# <a name="monitor-report-performance-in-power-bi"></a>Raportin suorituskyvyn valvominen Power BI:ssä

Valvo raportin suoritustehoa Power BI Desktopissa käyttämällä [Power BI Premium Metrics -sovellusta](../admin/service-premium-metrics-app.md), selvitä pullonkaulojen sijainti ja opi parantamaan raportin suorituskykyä.

Suorituskyvyn valvonta on oleellista seuraavissa tilanteissa:

- tietojen tuontimallin päivitys on hidasta
- DirectQueryn tai reaaliaikaisen yhteyden raportit ovat hitaita.
- mallin laskelmat ovat hitaita.

Hitaiden kyselyjen tai raporttien visualisointien tulee olla jatkuvan optimoinnin keskipisteessä.

## <a name="use-query-diagnostics"></a>Kyselydiagnostiikan käyttäminen

Käytä [kyselydiagnostiikkaa](/power-query/QueryDiagnostics) Power BI Desktopissa sen määrittämiseen, mitä Power Query tekee kyselyjen esikatselun tai käyttämisen aikana. Käytä lisäksi _Diagnosoi vaihe_ -toimintoa jokaisen vaiheen yksityiskohtaisten arviointitietojen tallentamiseen. Tulokset julkaistaan Power Queryssa, ja muunnoksia käyttämällä voit helpottaa kyselyn suorittamisen ymmärtämistä.

> [!NOTE]
> Kyselydiagnostiikka on tällä hetkellä esikatseluominaisuus, joten se on otettava käyttöön _Asetukset ja vaihtoehdot_ -toiminnolla. Kun se on käytössä, sen komennot ovat käytettävissä Power Query -editorin ikkunan **Työkalut**-valintanauhan väli lehdessä.

![Kuvassa näkyy Power Query -editorin Työkalut-valintanauhan välilehti. Valintanauhassa näkyy Diagnosoi vaihe -komento, Käynnistä diagnostiikka -komento ja Pysäytä diagnostiikka -komento.](media/monitor-report-performance/power-query-diagnotics.png)

## <a name="use-performance-analyzer"></a>Suorituskyvyn analysoinnin käyttäminen

Käyttämällä [Suorityskyvyn analysointia](../create-reports/desktop-performance-analyzer.md) Power BI Desktopissa voit selvittää, miten kaikki raporttielementit, kuten visualisoinnit ja DAX-kaavat, toimivat. On erityisen hyödyllistä määrittää, johtuvatko suorituskykyongelmat kyselystä vai visualisoinnin hahmonnuksesta.

## <a name="use-sql-server-profiler"></a>SQL Serverin profiloinnin käyttäminen

Voit tunnistaa hitaat kyselyt myös [SQL Serverin profilointi](/sql/tools/sql-server-profiler/sql-server-profiler) -käyttöliittymän avulla.

> [!NOTE]
> SQL Serverin profilointi on saatavilla osana [SQL Server Management Studio](/sql/ssms/download-sql-server-management-studio-ssms) -ympäristöä.

Käytä SQL Serverin profilointia, kun tietolähteesi on jokin seuraavista:

- SQL Server
- SQL Server Analysis Services
- Azure Analysis Services

> [!CAUTION]
> Power BI Desktop tukee diagnostiikkaporttiin yhdistämistä. Diagnostiikkaportti sallii yhteydenmuodostuksen muilla työkaluilla, ja sen avulla voidaan suorittaa jäljityksiä vianmääritystä varten. Muutosten tekemistä Power Desktop -tietomalliin ei tueta. Tietomalliin tehdyt muutokset saattavat johtaa vioittumiseen ja tietojen menettämiseen.

Voit luoda SQL Serverin profilointi -jäljityksen noudattamalla seuraavia ohjeita:

1. Avaa Power BI Desktop -raporttisi (jotta voit helposti paikantaa portin seuraavassa vaiheessa; sulje muut avoimet raportit).
1. Voit määrittää Power BI Desktopin käyttämän portin kirjoittamalla seuraavan komennon PowerShellissä (järjestelmänvalvojan oikeuksilla) tai komentokehotteessa:
    ```powershell
    netstat -b -n
    ```
    Tuloksena on luettelo sovelluksista ja niiden avoimista porteista. Etsi **msmdsrv.exe**-tiedoston käyttämä portti ja kirjoita se muistiin myöhempää käyttöä varten. Se on Power BI Desktop -esiintymäsi.
1. SQL Server Profilerin yhdistäminen Power BI Desktop -raporttiin:
    1. Avaa SQL Server Profiler.
    1. Valitse SQL Serverin profiloinnissa _Tiedosto_-valikosta _Uusi jäljitys_.
    1. Valitse **Palvelintyyppi**-kohdassa _Analyysipalvelut_.
    1. Anna **palvelimen nimelle**_localhost: [portti tallennettu aiemmin]_ .
    1. Napsauta _Suorita_. SQL Serverin profilointi -jäljitys on nyt käynnissä ja profiloi Power BI Desktop -kyselyjä aktiivisesti.
1. Kun Power BI Desktop kyselyt suoritetaan, niiden kestot ja suoritinajat ovat näkyvissä. Tietolähteen tyypin mukaan näkyviin voi tulla muita tapahtumia, jotka ilmaisevat kyselyn suoritustavan. Näiden tietojen avulla voit määrittää, mitkä kyselyt ovat pullonkauloja.

SQL Serverin profiloinnin käyttämisen etuna on, että SQL Serverin (relaatio)tieto kannan jäljitys voidaan tallentaa. Jäljityksestä voi tulla syöte [tietokantamoduulin säätötyökalulle](/sql/relational-databases/performance/start-and-use-the-database-engine-tuning-advisor). Näin voit saada suosituksia tietolähteen hienosäätämistä varten.

## <a name="monitor-premium-metrics"></a>Premium-mittareiden valvonta

Power BI Premium -kapasiteetteja varten voit käyttää **Power BI Premium Metrics -sovellusta** Power BI Premium -tilauksesi kunnon ja kapasiteetin hallitsemiseen. Lisätietoja on artikkelissa [Power BI Premium Metric -sovellus](../admin/service-premium-metrics-app.md).

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Kyselydiagnostiikka](/power-query/QueryDiagnostics)
- [Suorituskyvyn analysointi](../create-reports/desktop-performance-analyzer.md)
- [Raportin suorituskyvyn vianmääritys Power BI:ssä](report-performance-troubleshoot.md)
- [Power BI Premium Metrics -sovellus](../admin/service-premium-metrics-app.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
