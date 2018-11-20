---
title: Laitteisto- ja ohjelmistovaatimukset Power BI -raporttipalvelimen asentamista varten
description: Tässä artikkelissa määritetään laitteiston ja ohjelmiston vähimmäisvaatimukset Power BI -raporttipalvelimen asentamista ja käyttämistä varten.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 11/08/2018
ms.author: maghan
ms.openlocfilehash: c8904f3025a0a60557b1d3efb54ea6bc18c20da4
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507902"
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Laitteisto- ja ohjelmistovaatimukset Power BI -raporttipalvelimen asentamista varten
Tässä artikkelissa määritetään laitteiston ja ohjelmiston vähimmäisvaatimukset Power BI -raporttipalvelimen asentamista ja käyttämistä varten.

## <a name="processor-memory-and-operating-system-requirements"></a>Suoritin, muisti ja käyttöjärjestelmävaatimukset

| Komponentti | Vaatimus |
| --- | --- |
| .NET Framework |4.6<br><br>Voit asentaa .NET Frameworkin manuaalisesti kohdasta [Microsoft .NET Framework 4.6 (Web Installer) for Windows](http://support.microsoft.com/kb/3045560).<br/><br/> Lisätietoja, suosituksia ja ohjeita .NET Framework 4.6:lle saa kohdasta [.NET Framework-käyttöönotto-opas kehittäjille](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).<br/><br/>Windows 8.1 ja Windows Server 2012 R2 edellyttävät [KB2919355:n](http://support.microsoft.com/kb/2919355) asentamista ennen kuin asennat .NET Framework 4.6:n. |
| Kiintolevy |Power BI -raporttipalvelin edellyttää vähintään 1 Gt käytettävissä olevaa kiintolevytilaa.<br><br>Lisätilaa tarvitaan tietokantapalvelimessa, joka isännöi raporttipalvelimen tietokantaa. |
| Muisti |**Vähintään:** 1 Gt<br/><br/> **Suositus:** vähintään 4 Gt |
| Suorittimen nopeus |**Vähintään:** x64 suoritin: 1,4 GHz<br/><br/> **Suositus:** 2,0 GHz:n suoritin |
| Suorittimen tyyppi |x64 suoritin: AMD Opteron, AMD Athlon 64, Intel Xeon ja Intel EM64T-tuki, Intel Pentium IV ja EM64T-tuki |
| Käyttöjärjestelmä |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> Power BI -raporttipalvelimen asennusta tuetaan vain x64 vain suorittimille.
> 
> 

## <a name="database-server-version-requirements"></a>Tietokantapalvelimen versiota koskevat vaatimukset
SQL Serveriä käytetään isännöimään raporttipalvelintietokantoja. SQL Server-tietokantamoduulin esiintymä voi olla paikallinen tai etä-esiintymä. Raporttipalvelintietokantoja isännöivän SQL Server-tietokantamoduulin tuetut versiot ovat seuraavat:

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012

Kun luot raporttipalvelimen tietokannan etätietokoneessa, sinun on määritettävä yhteys, jota käytetään verkkoyhteydellä varustetun toimialueen käyttäjätilin tai palvelutilin kanssa. Jos päätät käyttää SQL Server-etäesiintymää, kannattaa harkita huolellisesti, mitä tunnistetietoja raporttipalvelimen kannattaa käyttää SQL Server-esiintymään. Katso lisätietoja kohdasta [Raporttipalvelimen tietokantayhteyden määrittäminen](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager).

## <a name="considerations"></a>Huomioitavaa
Power BI -raporttipalvelin asentaa oletusarvot raporttipalvelimen ydinasetusten määrittämiseksi raporttipalvelimen toimintaa varten. Se sisältää seuraavat vaatimukset:

* SQL Server-tietokantamoduulin on oltava käytettävissä asennuksen jälkeen ja ennen kuin määrität raporttipalvelimen tietokannan. Tietokantamoduulin esiintymä isännöi raporttipalvelimen tietokantaa, jonka Reporting Services Configuration Manager luo. Tietokantamoduulia ei vaadita varsinaisessa asennusvaiheessa.
- Artikkelissa [SQL Serverin julkaisujen tukemat raportointipalveluominaisuudet](https://docs.microsoft.com/sql/reporting-services/reporting-services-features-supported-by-the-editions-of-sql-server-2016) mainitaan SQL Serverin julkaisujen erot.
* Käyttäjätilin, jossa asennus suoritetaan, on oltava paikallisen Järjestelmänvalvojat-ryhmän jäsen.
* Käyttäjätilillä, joka suorittaa Reporting Services Configuration Managerin, on oltava oikeus käyttää ja luoda tietokantoja tietokantamoduulin esiintymässä, joka isännöi raporttipalvelimen tietokantoja.
* Asennusohjelman on voitava käyttää oletusarvoja varaamaan URL-osoitteet, joiden avulla saadaan pääsy raporttipalvelimelle ja verkkoportaaliin. Nämä arvot ovat portti 80, vahva yleismerkki ja näennäishakemiston nimet muodossa **ReportServer** ja **Raportit**.

## <a name="read-only-domain-controller-rodc"></a>Read-Only Domain Controller (RODC)
 Voit asentaa raporttipalvelimen ympäristössä, jossa on Read-Only Domain Controller (RODC). Reporting Services tarvitsee kuitenkin käyttöoikeuden Read-Write Domain Controlleriin, jotta se toimii oikein. Jos Reporting Services sisältää vain RODC-käyttöoikeuden, voi tulla virheitä, kun yrität hallita palvelua.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Reaaliaikaisten Power BI -raporttien ja Analysis Services -yhteyksien käyttäminen
Voit käyttää reaaliaikaista yhteyttä taulukkomuotoisiin tai moniulotteisiin esiintymiin. Analysis Services -palvelimen version on oltava oikea, jotta se toimii oikein.

| **Palvelinversio** | **Pakollinen SKU** |
| --- | --- |
| 2012 SP1 CU4 tai uudempi versio |Business Intelligence- ja Enterprise SKU |
| 2014 |Business Intelligence- ja Enterprise SKU |
| 2016 tai uudemmat |Standard SKU tai uudempi versio |

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI -raporttipalvelin?](get-started.md)  
[Järjestelmänvalvojan yleiskatsaus](admin-handbook-overview.md)  
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  
[Raportin muodostimen lataaminen](https://www.microsoft.com/download/details.aspx?id=53613)  
[SQL Server Data Tools (SSDT) -työkalujen lataaminen](http://go.microsoft.com/fwlink/?LinkID=616714)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

