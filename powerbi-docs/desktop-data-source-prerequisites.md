---
title: Power BI -tietolähde-edellytykset
description: Power BI -tietolähde-edellytykset
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 5a95607c2328115df7b4485756f40340a8cb7b0f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65454394"
---
# <a name="power-bi-data-source-prerequisites"></a>Power BI -tietolähde-edellytykset
Power BI tukee objektien tietyn palvelun versiota jokaisella tietopalvelulla. Lisätietoja Power BI:ssä käytettävistä tietolähteistä on ohjeaiheessa [Tietolähteet](desktop-data-sources.md). Seuraavassa taulukossa kuvataan nämä vaatimukset.

| Tietolähde | Palvelu | Palvelun vähimmäisversio | Tietolähteen vähimmäisversio | Tuetut tietolähdeobjektit | Latauslinkki |
| --- | --- | --- | --- | --- | --- |
| SQL Server |ADO.net (sisältyy .Net Frameworkiin) |.NET Framework 3.5 (ainoastaan) |SQL Server 2005+ |Taulukot/näkymät, skalaarifunktiot, taulukkofunktiot |Sisältyy .NET Framework 3.5:een tai uudempaan |
| Access |Microsoft Access -tietokantamoduuli (ACE) |ACE 2010 SP1 |Ei rajoitusta |Taulukot/näkymät |[Latauslinkki](http://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Excel (vain .xls-tiedosto) (katso huomautus 1) |Microsoft Access -tietokantamoduuli (ACE) |ACE 2010 SP1 |Ei rajoitusta |Taulukot, laskentataulukot |[Latauslinkki](http://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Oracle (katso huomautus 2) |ODP.NET |ODAC 11.2 Release 5 (11.2.0.3.20) |9.x+ |Taulukot/näkymät |[Latauslinkki](http://go.microsoft.com/fwlink/?linkid=272376&clcid=0x409) |
| | System.Data.OracleClient (sisältyy .NET Frameworkiin) |.NET Framework 3.5 |9.x+ |Taulukot/näkymät |Sisältyy .NET Framework 3.5:een tai uudempaan |
| IBM DB2 |IBM:n ADO.Net-asiakasohjelma (osa IBM:n tietopalvelimen ohjainpakettia) |10.1 |9.1+ |Taulukot/näkymät |[Latauslinkki](http://go.microsoft.com/fwlink/?linkid=274911&clcid=0x409) |
| MySQL |Connector/Net |6.6.5 |5.1 |Taulukot/näkymät, skalaarifunktiot |[Latauslinkki](http://go.microsoft.com/fwlink/?linkid=278885&clcid=0x409) |
| PostgreSQL |NPGSQL ADO.NET -palvelu |2.0.12 |7.4 |Taulukot/näkymät |[Latauslinkki](http://go.microsoft.com/fwlink/?linkid=282716&clcid=0x409) |
| Teradata |Teradatan .NET-tietopalvelu |14+ |12+ |Taulukot/näkymät |[Latauslinkki](http://go.microsoft.com/fwlink/?linkid=278886&clcid=0x409) |
| SAP Sybase SQL Anywhere |iAnywhere.Data.SQLAnywhere for .NET 3.5 |16+ |16+ |Taulukot/näkymät |[Latauslinkki](http://go.microsoft.com/fwlink/?linkid=324846) |

>[!NOTE]
>Erillistä palveluasennusta ei tarvita Excel-tiedostoille, joilla on .xlsx-tunniste.

>[!NOTE]
>Oracle-palvelut edellyttävät myös Oracle-asiakasohjelmistoa (versio 8.1.7+).
> 
> 

