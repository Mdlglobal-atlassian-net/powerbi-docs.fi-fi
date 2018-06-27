---
title: Power BI -raporttipalvelimen ja Power BI -palvelun vertailu
description: Tässä artikkelissa verrataan Power BI -raporttipalvelimen ja Power BI -palvelun ominaisuuksia.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 05/07/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: c47722fda28fc45289858f082a0838f583b53dbb
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34296777"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Power BI -raporttipalvelimen ja Power BI -palvelun vertailu

Power BI -raporttipalvelimessa ja Power BI -palvelussa on paljon samankaltaisuuksia ja oleellisia eroja. Tässä taulukossa kerrotaan niistä lisää.

| Ominaisuudet | Power BI -raporttipalvelin | Power BI -palvelu | Huomautukset
|---------|---------|---------|---------|
| Käyttöönotto | Paikallisesti tai pilvipalvelussa | Pilvi | Power BI -raporttipalvelin voidaan ottaa käyttöön Azure-näennäiskoneissa (pilvipalvelussa), mikäli käytössä on Power BI Premium -käyttöoikeus
| Lähdetiedot | Pilvipalvelu ja/tai paikallinen | Pilvipalvelu ja/tai paikallinen |  
| Käyttöoikeus | Power BI Premium tai SQL Server EE SA:lla | Power BI Pro ja/tai Power BI Premium |  
| Elinkaari | Moderni elinkaarikäytäntö | Täysin hallittu palvelu |  
| Julkaisuaikataulu | 4 kuukauden välein | Kerran kuukaudessa | Uusimmat ominaisuudet ja korjaukset julkaistaan ensin Power BI -palvelussa. Useimmat ydintoiminnot julkaistaan Power BI -raporttipalvelimessa muutaman versiopäivityksen sisällä; eräät ominaisuudet on tarkoitettu vain Power BI -palveluun.
| Luo Power BI -raportteja Power BI Desktopissa | Kyllä | Kyllä |  
| Luo Power BI -raportteja selaimessa | Ei | Kyllä |  
| Yhdyskäytävä tarvitaan | Ei | Kyllä (paikalliset tietolähteet) |  
| Reaaliaikainen virtauttaminen | Ei | Kyllä | [Reaaliaikainen virtauttaminen Power BI:ssä](../service-real-time-streaming.md)
| Koontinäytöt | Ei | Kyllä | [Raporttinäkymät Power BI -palvelussa](../service-dashboards.md) 
| Raporttiryhmien jakaminen sovellusten avulla | Ei | Kyllä | [Raporttinäkymiä ja raportteja sisältävien sovellusten luominen ja julkaiseminen](../service-create-distribute-apps.md) 
| Sisältöpaketit | Ei | Kyllä | [Organisaation sisältöpaketit: johdanto](../service-organizational-content-pack-introduction.md) 
| Yhteyden muodostaminen palveluihin (mm. Salesforce) | Ei | Kyllä | [Käyttämiesi palveluiden yhdistäminen ](../service-connect-to-services.md) Power BI -palveluun
| Q&A | Ei | Kyllä | [Q&A Power BI -palvelussa ja Power BI Desktopissa](../power-bi-q-and-a.md) 
| Nopeat merkitykselliset tiedot | Ei | Kyllä | [Merkityksellisten tietojen automaattinen luominen Power BI:llä](../service-insights.md) 
| Analysoi Excelissä | Ei | Kyllä | [Analysoi Excelissä](../service-analyze-in-excel.md) 
| Sivutetut raportit | Kyllä | Ei | Sivutetut raportit eivät ole käytettävissä Power BI -palvelussa, mutta voit [kiinnittää sivutettuja raporttikohteita Power BI -raporttinäkymiin](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards)
| Power BI -mobiilisovellukset | Kyllä | Kyllä | [Power BI -mobiilisovellusten yleiskuva](../mobile-apps-for-mobile-devices.md) 
| ArcGIS Maps | Ei | Kyllä | [Esri ArcGIS Maps Power BI -palvelussa ja Power BI Desktopissa](../power-bi-visualization-arcgis.md)
| Power BI -raporttien sähköpostitilaukset | Ei | Kyllä | [Raportin tai raporttinäkymän tilaaminen](../service-report-subscribe.md) Power BI -palvelussa 
| Sivutettujen raporttien sähköpostitilaukset | Kyllä | Ei | [Sähköpostitoimitus Reporting Servicesissä](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| Tietoilmoitukset | Ei | Kyllä | [Tietoilmoitukset](../service-set-data-alerts.md) Power BI -palvelussa
| Rivitason suojaus | Vain tietolähteen kautta DirectQuery-tilassa | Käytettävissä sekä DirectQuery- (tietolähde) että tuontitilassa | [Rivitason suojaus (RLS)](../service-admin-rls.md) Power BI:ssä 
| Koko näytön tila | Ei | Kyllä | [Koko näytön tila](../service-fullscreen-mode.md) Power BI -palvelussa 
| Edistynyt Office 365 -yhteistyö | Ei | Kyllä | [Yhteistyö sovelluksen työtilassa](../service-collaborate-power-bi-workspace.md) Office 365:n kautta 
| R-visualisoinnit | Ei | Kyllä | [R-visualisointien luominen](../service-r-visuals.md) Power BI -palvelussa  
| Esikatselutoiminnot | Ei | Kyllä | [Power BI:n esikatseluominaisuuksien käyttäminen](../service-preview-features.md) 
| Mukautetut visualisoinnit | Kyllä | Kyllä | [Mukautetut visualisoinnit Power BI:ssä](../power-bi-custom-visuals.md) 
| Power BI Desktop | Raporttipalvelimelle optimoitu versio, ladattavissa raporttipalvelimen kanssa | Power BI -palvelulle optimoitu versio, saatavilla Windows-kaupasta | [Power BI Desktop raporttipalvelimelle](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop Power BI -palvelulle](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  



