---
title: Power BI -raporttipalvelimen ja Power BI -palvelun vertailu
description: Tässä artikkelissa verrataan Power BI -raporttipalvelimen ja Power BI -palvelun ominaisuuksia.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 11/16/2018
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 95055f19ed4187124d940e0fe7f70068dffc71c5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54289758"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Power BI -raporttipalvelimen ja Power BI -palvelun vertailu

Power BI -raporttipalvelimessa ja Power BI -palvelussa on paljon samankaltaisuuksia ja oleellisia eroja. Tässä taulukossa kerrotaan niistä lisää.

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Power BI -raporttipalvelimen ja Power BI -palvelun ominaisuudet

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
| koontinäytöt | Ei | Kyllä | [Raporttinäkymät Power BI -palvelussa](../consumer/end-user-dashboards.md) 
| Raporttiryhmien jakaminen sovellusten avulla | Ei | Kyllä | [Raporttinäkymiä ja raportteja sisältävien sovellusten luominen ja julkaiseminen](../service-create-distribute-apps.md) 
| Sisältöpaketit | Ei | Kyllä | [Organisaation sisältöpaketit: Johdanto](../service-organizational-content-pack-introduction.md) 
| Yhteyden muodostaminen palveluihin (mm. Salesforce) | Kyllä | Kyllä | [Muodosta yhteys palveluihin, joita käytät](../service-connect-to-services.md) sisältöpakettien avulla Power BI -palvelussa. Muodosta yhteys palveluihin sertifioitujen liittimien avulla Power BI -raporttipalvelimessa. Katso lisätietoja artikkelista [Power BI -raportin tietolähteet Power BI -raporttipalvelimessa](data-sources.md).
| Q&A | Ei | Kyllä | [Q&A Power BI -palvelussa ja Power BI Desktopissa](../consumer/end-user-q-and-a.md) 
| Nopeat merkitykselliset tiedot | Ei | Kyllä | [Merkityksellisten tietojen automaattinen luominen Power BI:llä](../consumer/end-user-insights.md) 
| Analysoi Excelissä | Ei | Kyllä | [Analysoi Excelissä](../service-analyze-in-excel.md) 
| Sivutetut raportit | Kyllä | Kyllä | [Sivutetut raportit ovat käytettävissä Power BI -palvelussa](../paginated-reports-report-builder-power-bi.md) esikatselutilassa Premium-kapasiteetissa
| Power BI -mobiilisovellukset | Kyllä | Kyllä | [Power BI -mobiilisovellusten yleiskuva](../consumer/mobile/mobile-apps-for-mobile-devices.md) 
| ArcGIS Maps | Ei | Kyllä | [Esri ArcGIS Maps Power BI -palvelussa ja Power BI Desktopissa](../power-bi-visualization-arcgis.md)
| Power BI -raporttien sähköpostitilaukset | Ei | Kyllä | [Raportin tai raporttinäkymän tilaaminen](../consumer/end-user-subscribe.md) Power BI -palvelussa 
| Sivutettujen raporttien sähköpostitilaukset | Kyllä | Ei | [Sähköpostitoimitus Reporting Servicesissä](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| Tietoilmoitukset | Ei | Kyllä | [Tietoilmoitukset](../service-set-data-alerts.md) Power BI -palvelussa
| Rivitason suojaus | Vain tietolähteen kautta DirectQuery-tilassa | Käytettävissä sekä DirectQuery- (tietolähde) että tuontitilassa | [Rivitason suojaus (RLS)](../service-admin-rls.md) Power BI:ssä 
| Koko näytön tila | Ei | Kyllä | [Koko näytön tila](../consumer/end-user-focus.md) Power BI -palvelussa 
| Edistynyt Office 365 -yhteistyö | Ei | Kyllä | [Yhteistyö sovelluksen työtilassa](../service-collaborate-power-bi-workspace.md) Office 365:n kautta 
| R-visualisoinnit | Ei | Kyllä | [Luo R-visualisoinnit](../desktop-r-visuals.md) Power BI Desktopissa ja julkaise ne Power BI -palvelussa. Et voi tallentaa Power BI -raportteja R-visualisointien kanssa Power BI -raporttipalvelimeen.  
| Esikatselutoiminnot | Ei | Kyllä | [Power BI:n esikatseluominaisuuksien käyttäminen](../consumer/end-user-preview-features.md) 
| Mukautetut visualisoinnit | Kyllä | Kyllä | [Mukautetut visualisoinnit Power BI:ssä](../power-bi-custom-visuals.md) 
| Power BI Desktop | Raporttipalvelimelle optimoitu versio, ladattavissa raporttipalvelimen kanssa | Power BI -palvelulle optimoitu versio, saatavilla Windows-kaupasta | [Power BI Desktop raporttipalvelimelle](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop Power BI -palvelulle](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  



