---
title: Mikä on Power BI -raporttipalvelin?
description: Tutustu Power BI -raporttipalvelimeen ja sen käyttöön SQL Server Reporting Servicesin (SSRS) ja muiden Power BI -ominaisuuksien kanssa.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 05/22/2019
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 37751117853c8bca686585992108c006c6c76b70
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187469"
---
# <a name="what-is-power-bi-report-server"></a>Mikä on Power BI -raporttipalvelin?

Power BI -raporttipalvelin on verkkoportaalilla varustettu paikallinen raporttipalvelin, jossa voit tarkastella ja hallinnoida raportteja ja suorituskykyilmaisimia. Se sisältää myös Power BI -raporttien, sivutettujen raporttien, mobiiliraporttien ja suorituskykyilmaisinten luomistyökalut. Käyttäjät voivat käyttää näitä raportteja eri tavoilla: niitä voidaan tarkastella verkkoselaimessa tai mobiililaitteessa tai sähköpostiviesteinä.

![Power BI -raporttipalvelimen verkkoportaali](media/get-started/power-bi-report-server-overview.png)

## <a name="comparing-power-bi-report-server"></a>Power BI -raporttipalvelimen vertailu 
Power BI -raporttipalvelin on vastaava kuin SQL Server Reporting Services ja Power BI -verkkopalvelu, mutta se toimii eri tavoilla. Power BI-palvelun tavoin Power BI-raporttipalvelin isännöi Power BI-raportteja (. PBIX) Excel-tiedostoja ja Sivutettujen raporttien (. RDL). Reporting Servicesin tavoin Power BI-raporttipalvelin on paikallisesti. Power BI-raporttipalvelimen ominaisuudet ovat Reporting Servicesin yläjoukko: kaikki Reporting Servicesin, voit tehdä Power BI-raporttipalvelimen ja tuki-Power BI-raporttien. Katso lisätietoja kohdasta [Power BI -raporttipalvelimen ja Power BI -palvelun vertailu](compare-report-server-service.md).

## <a name="licensing-power-bi-report-server"></a>Power BI -raporttipalvelimen käyttöoikeus
Power BI -raporttipalvelin on saatavana kahdella eri käyttöoikeudella: [Power BI Premium](../service-premium-what-is.md) ja [SQL Server Enterprise Edition](https://www.microsoft.com/sql-server/sql-server-2017-editions), jossa on SA-ylläpito. Power BI Premium -käyttöoikeudella voit luoda hybridiratkaisun, jossa yhdistyvät pilvi- ja paikallispalvelut.  

> [!NOTE]
> Power BI Premiumin osalta Power BI -raporttipalvelin sisältyy vain P-varastointiyksiköihin. Se ei sisälly EM-varastointiyksiköihin.

## <a name="web-portal"></a>Verkkoportaali
Power BI -raporttipalvelimen käyttöliittymä on nykyaikainen verkkoportaali, jota voit tarkastella missä tahansa nykyaikaisessa selaimessa. Täällä voit käyttää kaikkia raportteja ja suorituskykyilmaisimia. Verkkoportaalin sisältö on järjestetty perinteiseen kansiohierarkiaan. Kansioissa sisältö on ryhmitelty tyypin mukaan: Power BI -raportit, mobiiliraportit, sivutetut raportit, suorituskykyilmaisimet ja Excel-työkirjat. Jaetut tietojoukot ja jaetut tietolähteet ovat omissa kansioissaan, joissa niitä voidaan käyttää apuna raporttien luomisessa. Voit merkitä suosikkisi ja tarkastella niitä yhdessä kansiossa. Lisäksi voit luoda suorituskykyilmaisimia suoraan verkkoportaalista. 

![Power BI -raporttipalvelimen verkkoportaali](media/get-started/web-portal.png)

Käyttöoikeuksiesi mukaan voit hallita sisältöä verkkoportaalissa. Voit ajastaa raporttien käsittelyn, käyttää raportteja pyynnöstä sekä tilata julkaistut raportit itsellesi. Voit myös käyttää verkkoportaalissa omia mukautettuja [brändejäsi](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal). 

Lisätietoja [Power BI -raporttipalvelimen verkkoportaalista](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).

## <a name="power-bi-reports"></a>Power BI -raportit
Voit luoda Power BI -raportteja (.PBIX) raporttipalvelimelle optimoidulla Power BI Desktop -versiolla. Sitten voit julkaista ne ja tarkastella niitä verkkoportaalissa omassa ympäristössäsi.

![Power BI -raportit Power BI -raporttipalvelimella](media/get-started/powerbi-reports.png)

Power BI -raportti on usean perspektiivin tietomallinäkymä, jonka visualisoinnit edustavat eri havaintoja ja merkityksellisiä tietoja tietomallista.  Raportilla voi olla yksittäinen visualisointi tai sivuja, jotka ovat täynnä visualisointeja. Roolisi mukaan voit lukea ja tutkia raportteja, tai voit luoda muille raportteja.

Lue [Microsoft Power BI Desktop asennetaan](install-powerbi-desktop.md).

## <a name="paginated-reports"></a>Sivutetut raportit
Sivutetut raportit (.RDL)ovat asiakirjatyylisiä, visualisointeja sisältäviä raportteja, joissa taulukot laajentuvat vaaka- ja pystysuunnassa kaikkien tietojen näyttämiseksi, sivulta toiselle jatkuen tarpeen mukaan. Ne sopivat erinomaisesti pikselintarkasti täydellisesti aseteltuihin kiinteisiin raportteihin, jotka on optimoitu tulostettavaksi esimerkiksi PDF- tai Word-tiedostoina. 

![Sivutetut raportit Power BI -raporttipalvelimella](media/get-started/paginated-reports.png)

Voit luoda sivutettuja raportteja käyttämällä [raportin muodostimen](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) tai Report Designer- [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt).

## <a name="reporting-services-mobile-reports"></a>Reporting Servicesin mobiiliraportit
Mobiiliraportit yhdistyvät paikallisiin tietoihin ja niiden reagoiva asettelu sopeutuu eri laitteille ja näytön suunnan mukaisesti. Voit luoda ne SQL Serverin mobiiliraportin julkaisijalla.

Lisätietoa [Reporting Servicesin mobiiliraporteista](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher). 

## <a name="report-server-programming-features"></a>Raporttipalvelimen ohjelmointiominaisuudet
Hyödynnä Power BI -raporttipalvelimen ohjelmointiominaisuudet, joiden avulla voit laajentaa ja mukauttaa raportteja. Ohjelmointirajapintojen kautta voit integroida niitä mukautettuihin sovelluksiin sekä laajentaa tietojen ja raporttien käsittelyä sovelluksissa.

Lisää [ohjeita raporttipalvelinkehittäjälle](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  
[Raportin muodostimen lataaminen](https://www.microsoft.com/download/details.aspx?id=53613)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)


