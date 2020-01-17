---
title: Power BI -tietolähde-edellytykset
description: Power BI -tietolähde-edellytykset
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: d118cae8cd4b6fbd95066b15819b1e798c8bbe0f
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/09/2020
ms.locfileid: "75761314"
---
# <a name="power-bi-data-source-prerequisites"></a>Power BI -tietolähde-edellytykset
Power BI tukee objektien tietyn palvelun versiota jokaisella tietopalvelulla. Jos haluat lisätietoja Power BI:ssä käytettävistä tietolähteistä, tutustu ohjeartikkeliin [Tietolähteet](desktop-data-sources.md). Seuraavassa taulukossa kuvataan nämä vaatimukset.

| Tietolähde | Palvelu | Palvelun vähimmäisversio | Tietolähteen vähimmäisversio | Tuetut tietolähdeobjektit | Latauslinkki |
| --- | --- | --- | --- | --- | --- |
| SQL Server |ADO.net (sisältyy .Net Frameworkiin) |.NET Framework 3.5 (ainoastaan) |SQL Server 2005+ |Taulukot/näkymät, skalaarifunktiot, taulukkofunktiot |Sisältyy .NET Framework 3.5:een tai uudempaan |
| Käyttöoikeudet |Microsoft Access -tietokantamoduuli (ACE) |ACE 2010 SP1 |Ei rajoitusta |Taulukot/näkymät |[Latauslinkki](https://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Excel (vain .xls-tiedosto) (katso huomautus 1) |Microsoft Access -tietokantamoduuli (ACE) |ACE 2010 SP1 |Ei rajoitusta |Taulukot, laskentataulukot |[Latauslinkki](https://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Oracle (katso huomautus 2) |ODP.NET |ODAC 11.2 Release 5 (11.2.0.3.20) |9.x+ |Taulukot/näkymät |[Latauslinkki](https://go.microsoft.com/fwlink/?linkid=272376&clcid=0x409) |
| | System.Data.OracleClient (sisältyy .NET Frameworkiin) |.NET Framework 3.5 |9.x+ |Taulukot/näkymät |Sisältyy .NET Framework 3.5:een tai uudempaan |
| IBM DB2 |IBM:n ADO.Net-asiakasohjelma (osa IBM:n tietopalvelimen ohjainpakettia) |10.1 |9.1+ |Taulukot/näkymät |[Latauslinkki](https://go.microsoft.com/fwlink/?linkid=274911&clcid=0x409) |
| MySQL |Connector/Net |6.6.5 |5.1 |Taulukot/näkymät, skalaarifunktiot |[Latauslinkki](https://go.microsoft.com/fwlink/?linkid=278885&clcid=0x409) |
| PostgreSQL |NPGSQL ADO.NET -palvelu |2.0.12 |7.4 |Taulukot/näkymät |[Latauslinkki](https://go.microsoft.com/fwlink/?linkid=282716&clcid=0x409) |
| Teradata |Teradatan .NET-tietopalvelu |14+ |12+ |Taulukot/näkymät |[Latauslinkki](https://go.microsoft.com/fwlink/?linkid=278886&clcid=0x409) |
| SAP Sybase SQL Anywhere |iAnywhere.Data.SQLAnywhere for .NET 3.5 |16+ |16+ |Taulukot/näkymät |[Latauslinkki](https://go.microsoft.com/fwlink/?linkid=324846) |

>[!NOTE]
>Erillistä palveluasennusta ei tarvita Excel-tiedostoille, joilla on .xlsx-tunniste.

>[!NOTE]
>Oracle-palvelut edellyttävät myös Oracle-asiakasohjelmistoa (versio 8.1.7+).
> 
> 

