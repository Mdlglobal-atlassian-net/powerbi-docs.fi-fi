---
title: Sivutetun raportin tietolähteet Power BI -raporttipalvelimessa
description: Lisätietoja tietolähteistä, joihin sivutetut raportit (.rdl) voivat muodostaa yhteyden Power BI -raporttipalvelimessa.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: maggies
ms.openlocfilehash: 7cb5772e6ccdc1e4036d70f65a3a28210a4f6df1
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "78260711"
---
# <a name="paginated-report-data-sources--in-power-bi-report-server"></a>Sivutetun raportin tietolähteet Power BI -raporttipalvelimessa
Reporting Servicesin sivutetut raportit Power BI -raporttipalvelimessa tukevat samoja tietolähteitä, joita tuetaan SQL Server Reporting Servicesissä. Lisätietoja on kohdassa [Reporting Services -palvelun tukemat tietolähteet](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

## <a name="connect-to-oracle-data-sources-with-useinstalleduiculture"></a>Yhteyden muodostaminen Oracle-tietolähteisiin UseInstalledUICulture-asetuksella

Power BI -raporttipalvelin muodostaa yhteyden Oracle-tietolähteisiin käyttämällä .NETin Oracle-tietopalvelua (ODP.NET), joka on NLS-riippumaton.

Oletusarvon mukaan raporttipalvelin käyttää ODP.NETin lataamiseen ensimmäisen asiakkaan UI-kulttuuria.  Näin ollen kaikki myöhemmät raporttipalvelimesta Oracleen muodostetut yhteydet käyttävät samaa käyttöliittymän maa-asetusta, kunnes palvelu käynnistetään uudelleen.  Tämä lähestymistapa voi aiheuttaa ongelmia raportin hahmontamisessa käyttöliittymän maa-asetusten muotoiluerojen vuoksi.

Power BI -raporttipalvelimen käyttökokemusta parantaaksemme olemme ottaneet käyttöön määritysasetuksen UseInstalledUICulture. Kun UseInstalledUICulture-asetuksen arvoksi on määritetty tosi, raporttipalvelin lataa aina ODP.NETin käyttämällä palvelimen käyttöliittymän maa-asetusta eikä ensimmäisen asiakkaan maa-asetusta.
Asetus on saatavilla Power BI -raporttipalvelimessa helmikuun palvelujulkaisusta alkaen.

Voit ottaa toiminnon käyttöön muokkaamalla ORACLE-laajennusmerkinnän rsreportserver.config-tiedostoa alla kuvatulla tavalla.
```xml
<Extension Name="ORACLE" Type="Microsoft.ReportingServices.DataExtensions.OracleClientConnectionWrapper,Microsoft.ReportingServices.DataExtensions">
    <Configuration>
        <UseInstalledUICulture>true</UseInstalledUICulture>
    </Configuration>
</Extension>
```

## <a name="next-steps"></a>Seuraavat vaiheet
Nyt kun olet yhdistänyt tietolähteeseen, [luo sivutettu raportti](quickstart-create-paginated-report.md).  


Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
