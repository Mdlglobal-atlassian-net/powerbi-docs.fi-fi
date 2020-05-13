---
title: Power BI -raporttipalvelimen ja Power BI -palvelun vertailu
description: Tässä artikkelissa verrataan Power BI -raporttipalvelimen ja Power BI -palvelun ominaisuuksia.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
ms.date: 03/04/2020
ms.openlocfilehash: 18ca1b58d37fedb2c8246b91dc765168002e163e
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83275934"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Power BI -raporttipalvelimen ja Power BI -palvelun vertailu

Power BI -raporttipalvelimessa ja Power BI -palvelussa on monia samankaltaisuuksia ja joitain oleellisia eroja. Tässä taulukossa kerrotaan niistä lisää.

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Power BI -raporttipalvelimen ja Power BI -palvelun ominaisuudet

| Ominaisuudet | Power BI -raporttipalvelin | Power BI -palvelu | Huomautukset |
|---------|---------|---------|---------|
| Käyttöönotto | Paikallisesti tai pilvipalvelussa | Pilvi | Power BI -raporttipalvelin voidaan ottaa käyttöön Azure-näennäiskoneissa (pilvipalvelussa), mikäli käytössä on Power BI Premium -käyttöoikeus tai SQL Server Enterprise ja Software Assurance|
| Lähdetiedot | Pilvipalvelu ja/tai paikallinen | Pilvipalvelu ja/tai paikallinen |  |
| Käyttöoikeus | Power BI Premium tai SQL Server EE ja SA-ylläpito | Power BI Pro ja/tai Power BI Premium | |  
| Elinkaari | Moderni elinkaarikäytäntö | Täysin hallittu palvelu |  |
| Julkaisuaikataulu | Kolme kertaa vuodessa (tammikuu, toukokuu, syyskuu) | Kerran kuukaudessa | Uusimmat ominaisuudet ja korjaukset julkaistaan ensin Power BI -palvelussa. Power BI -raporttipalvelimeen tulee jokaisen julkaisuversion myötä koonti Power BI Desktopin julkaisuversion ominaisuuksista; suurin osa muista ominaisuuksista on tarkoitettu vain Power BI -palveluun. |
| Luo Power BI -raportteja Power BI Desktopissa | Yes | Yes |  |
| Luo Power BI -raportteja selaimessa | No | Yes |  |
| Kutsu ja yhdistä Power BI:n jaettuihin tietojoukkoihin | No | Yes | [Johdanto tietojoukkojen käyttöön eri työtiloissa ](../connect-data/service-datasets-across-workspaces.md) |
| Yhdyskäytävä tarvitaan | No | Kyllä (paikalliset tietolähteet) |  |
| Reaaliaikainen virtauttaminen | No | Yes | [Reaaliaikainen virtauttaminen Power BI:ssä](../connect-data/service-real-time-streaming.md) |
| koontinäytöt | No | Yes | [Raporttinäkymät Power BI -palvelussa](../consumer/end-user-dashboards.md) |
| Raporttiryhmien jakaminen sovellusten avulla | No | Yes | [Raporttinäkymiä ja raportteja sisältävien sovellusten luominen ja julkaiseminen](../collaborate-share/service-create-distribute-apps.md) |
| Sisältöpaketit | No | Yes | [Organisaation sisältöpaketit: johdanto](../collaborate-share/service-organizational-content-pack-introduction.md) |
| Yhteyden muodostaminen palveluihin (mm. Salesforce) | Yes | Yes | [Muodosta yhteys palveluihin, joita käytät](../connect-data/service-connect-to-services.md) sisältöpakettien avulla Power BI -palvelussa. Muodosta yhteys palveluihin sertifioitujen liittimien avulla Power BI -raporttipalvelimessa. Katso lisätietoja artikkelista [Power BI -raportin tietolähteet Power BI -raporttipalvelimessa](data-sources.md). |
| Kysymykset ja vastaukset | No | Yes | [Q&A Power BI -palvelussa ja Power BI Desktopissa](../create-reports/power-bi-tutorial-q-and-a.md) 
| Nopeat merkitykselliset tiedot | No | Yes | [Merkityksellisten tietojen automaattinen luominen Power BI:llä](../consumer/end-user-insights.md) |
| Analysoi Excelissä | No | Yes | [Analysoi Excelissä](../collaborate-share/service-analyze-in-excel.md) 
| Sivutetut raportit | Yes | Yes | [Sivutetut raportit ovat käytettävissä Power BI -palvelussa](../paginated-reports/paginated-reports-report-builder-power-bi.md) esikatselutilassa Premium-kapasiteetissa |
| Power BI -mobiilisovellukset | Yes | Yes | [Power BI -mobiilisovellusten yleiskuva](../consumer/mobile/mobile-apps-for-mobile-devices.md) |
| ArcGIS Maps | No | Yes | [Esri ArcGIS Maps Power BI -palvelussa ja Power BI Desktopissa](../visuals/power-bi-visualization-arcgis.md) |
| Power BI -raporttien sähköpostitilaukset | No | Yes | Power BI -palvelun raporttien tai koontinäyttöjen [tilaaminen itsellesi ja muille](../collaborate-share/service-report-subscribe.md) |
| Sivutettujen raporttien sähköpostitilaukset | Yes | Yes | [Power BI -palvelun sivutettujen raporttien tilaaminen itsellesi ja muille](../consumer/paginated-reports-subscriptions.md)<br><br>[Sähköpostitoimitus Reporting Servicesissä](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal)  |
| Tietoilmoitukset | No | Yes | [Tietoilmoitukset](../create-reports/service-set-data-alerts.md) Power BI -palvelussa
| Rivitason suojaus (RLS) | Yes | Yes | Käytettävissä sekä DirectQuery- (tietolähde) että tuontitilassa <br><br>Rivitason suojaus [Power BI -palvelussa](../admin/service-admin-rls.md) <br><br>Rivitason suojaus [Power BI -raporttipalvelimessa](row-level-security-report-server.md) |
| Koko näytön tila | No | Yes | [Koko näytön tila](../consumer/end-user-focus.md) Power BI -palvelussa |
| Edistynyt Office 365 -yhteistyö | No | Yes | [Yhteistyö työtilassa](../collaborate-share/service-collaborate-power-bi-workspace.md) Office 365:n kautta |
| R-visualisoinnit | No | Yes | [Luo R-visualisoinnit](../create-reports/desktop-r-visuals.md) Power BI Desktopissa ja julkaise ne Power BI -palvelussa. Et voi tallentaa Power BI -raportteja R-visualisointien kanssa Power BI -raporttipalvelimeen.  |
| Esikatselutoiminnot | No | Yes | [Power BI:n esikatseluominaisuuksien käyttäminen](../consumer/end-user-preview-features.md) |
| Power BI:n visualisoinnit | Yes | Yes | [Power BI -visualisoinnit](../developer/visuals/power-bi-custom-visuals.md) |
| Yhdistelmämallit | No | Yes |
| Power BI Desktop | Raporttipalvelimelle optimoitu versio, ladattavissa raporttipalvelimen kanssa | Power BI -palvelulle optimoitu versio, saatavilla Windows-kaupasta | [Power BI Desktop raporttipalvelimelle](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop Power BI -palvelulle](https://aka.ms/pbidesktopstore) |

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI -raporttipalvelimen asentaminen](install-report-server.md)






