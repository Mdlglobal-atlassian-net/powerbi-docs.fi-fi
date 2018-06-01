---
title: Yleiskatsaus kehittäjien oppaaseen, Power BI -raporttipalvelin
description: Tervetuloa käyttämään Microsoft Power BI -raporttipalvelimen kehittäjän opasta. Power BI -raporttipalvelin on raporttien paikallinen tallennustila, jonka kautta voit hallita Power BI- ja mobiiliraportteja sekä sivutettuja raportteja.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 93cc5b5566816b1b9ce8295cf7c0b727b07571df
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
ms.locfileid: "30973187"
---
# <a name="developer-handbook-overview-power-bi-report-server"></a>Yleiskatsaus kehittäjien oppaaseen, Power BI -raporttipalvelin
Tervetuloa käyttämään Microsoft Power BI -raporttipalvelimen kehittäjän opasta. Power BI -raporttipalvelin on raporttien paikallinen tallennustila, jonka kautta voit hallita Power BI- ja mobiiliraportteja sekä sivutettuja raportteja.

![](media/developer-handbook-overview/admin-handbook.png)

Oppaassa kuvataan, millaisia vaihtoehtoja sinulla on kehittäjänä käyttäessäsi Power BI -raporttipalvelinta.

## <a name="embedding"></a>Upottaminen
Voit upottaa minkä tahansa Power BI -raporttipalvelimella olevan raportin iFrameen lisäämällä URL-osoitteeseen kyselymerkkijonon parametrin `?rs:Embed=true`. Se toimii niin Power BI ‑raporteissa kuin muunkin tyyppisissä raporteissa.

### <a name="report-viewer-control"></a>Raporttien katseluohjelman ohjausobjekti
Voit hyödyntää sivutetuissa raporteissa raporttien katseluohjelman ohjausobjektia. Ohjausobjektin voi sijoittaa .NET-ikkunoihin tai verkkosovelluksiin. Lisätietoja on artikkelissa [Raporttien katseluohjelman ohjausobjektin käytön aloittaminen](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

## <a name="apis"></a>Ohjelmointirajapinnat
Power BI -raporttipalvelimen kanssa vuorovaikuttamiseen on käytettävissä useita eri ohjelmointirajapintoja. Ne on esitetty seuraavassa luettelossa.

* [REST-ohjelmointirajapinnat](rest-api.md)
* [URL-yhteys](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)
* [WMI-palvelu](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

Lisäksi voit hallita raporttipalvelinta käyttämällä avoimen lähdekoodin [PowerShell-apuohjelmia](https://github.com/Microsoft/ReportingServicesTools).

> [!NOTE]
> PowerShell-apuohjelmat eivät tällä hetkellä tue Power BI Desktop ‑tiedostoja (.pbix).
> 
> 

## <a name="custom-extensions"></a>Mukautetut laajennukset
Laajennuskirjasto on Power BI -raporttipalvelimeen sisältyvä joukko luokkia, liittymiä ja arvotyyppejä. Kirjasto mahdollistaa järjestelmän toiminnallisuuksien käytön, ja se on suunniteltu toimimaan perustana, jolta Microsoft.NET Framework ‑sovelluksia voidaan käyttää Microsoft Power BI -raporttipalvelimen osien laajentamiseen.

Voit luoda useita erilaisia laajennustyyppejä.

* Tietojen käsittelylaajennukset
* Toimituslaajennukset
* Sivutettujen raporttien hahmontamislaajennukset
* Suojauslaajennukset

Lisätietoja on artikkelissa [Laajennuskirjasto](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library).

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttien katseluohjelman ohjausobjektin käytön aloittaminen](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)  
[Sovellusten luominen käyttämällä verkkopalveluita ja .NET Frameworkia](https://docs.microsoft.com/sql/reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework)  
[URL-yhteys](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)  
[Laajennuskirjasto](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library)  
[WMI-palvelu](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

