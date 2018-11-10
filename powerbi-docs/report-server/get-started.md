---
title: Mikä on Power BI -raporttipalvelin?
description: Tutustu Power BI -raporttipalvelimeen ja sen käyttöön SQL Server Reporting Servicesin (SSRS) ja muiden Power BI -ominaisuuksien kanssa.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 10/24/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 95a97c86ae7d17091b49fbf33cf5ec0d26053c3e
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/25/2018
ms.locfileid: "50101390"
---
# <a name="what-is-power-bi-report-server"></a>Mikä on Power BI -raporttipalvelin?

Power BI -raporttipalvelin on paikallinen raporttipalvelin, jonka verkkoportaalissa voit tarkastella ja hallita raportteja ja suorituskykyilmaisimia. Se tarjoaa myös työkalut, joilla voit luoda Power BI -raportteja, sivutettuja raportteja, mobiiliraportteja ja suorituskykyilmaisimia. Käyttäjät voivat käyttää näitä raportteja eri tavoilla: niitä voidaan tarkastella verkkoselaimessa tai mobiililaitteessa tai sähköpostiviesteinä.

![Power BI -raporttipalvelimen verkkoportaali](media/get-started/power-bi-report-server-overview.png)

## <a name="comparing-power-bi-report-server"></a>Power BI -raporttipalvelimen vertailu 
Power BI -raporttipalvelin on vastaava kuin SQL Server Reporting Services ja Power BI -verkkopalvelu, mutta se toimii eri tavoilla. Power BI -palvelun tavoin Power BI -raporttipalvelin isännöi Power BI -raportteja (.PBIX) ja Excel-tiedostoja. Reporting Servicesin tavoin Power BI -raporttipalvelin on paikallinen palvelin, joka isännöi sivutettuja raportteja (.RDL). Power BI -raporttipalvelin on Reporting Servicesin yläjoukko: kaikki Reporting Servicesin voidaan tehdä myös Power BI -raporttipalvelimessa, ja myös paljon muuta Power BI -raporttien tuen myötä. Katso lisätietoja kohdasta [Power BI -raporttipalvelimen ja Power BI -palvelun vertailu](compare-report-server-service.md).

## <a name="licensing-power-bi-report-server"></a>Power BI -raporttipalvelimen käyttöoikeus
Power BI -raporttipalvelin on saatavana kahdella eri käyttöoikeudella: [Power BI Premium](../service-premium.md) ja [SQL Server Enterprise Edition](https://www.microsoft.com/sql-server/sql-server-2017-editions), jossa on Software Assurance. Power BI Premium -käyttöoikeudella voit luoda hybridiratkaisun, jossa yhdistyvät pilvi- ja paikallispalvelut.  

> [!NOTE]
> Power BI Premiumin osalta Power BI -raporttipalvelin sisältyy vain P-varastointiyksiköihin. Se ei sisälly EM-varastointiyksiköihin.

## <a name="web-portal"></a>Verkkoportaali
Power BI -raporttipalvelimen käyttöliittymä on nykyaikainen verkkoportaali, jota voit tarkastella missä tahansa nykyaikaisessa selaimessa. Täällä voit käyttää kaikkia raportteja ja suorituskykyilmaisimia. Verkkoportaalin sisältö on järjestetty perinteiseen kansiohierarkiaan. Kansioiden sisältö on järjestetty tyypin mukaan: Power BI -raportit, mobiiliraportit, sivutetut raportit, suorituskykyilmaisimet ja Excel-työkirjat, sekä raporttien perustana toimivat jaetut tietojoukot ja jaetut tietolähteet. Voit merkitä suosikkisi ja tarkastella niitä yhdessä kansiossa. Lisäksi voit luoda suorituskykyilmaisimia suoraan verkkoportaalista. 

![Power BI -raporttipalvelimen verkkoportaali](media/get-started/web-portal.png)

Käyttöoikeuksiesi mukaan voit hallita sisältöä verkkoportaalissa. Voit ajastaa raporttien käsittelyn, käyttää raportteja pyynnöstä sekä tilata julkaistut raportit itsellesi. Voit myös käyttää verkkoportaalissa omia mukautettuja [brändejäsi](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal). 

Lisätietoja [Power BI -raporttipalvelimen verkkoportaalista](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).

## <a name="power-bi-reports"></a>Power BI -raportit
Voit luoda Power BI -raportteja (.PBIX) raporttipalvelimelle optimoidulla Power BI Desktop -versiolla. Sitten voit julkaista ne ja tarkastella niitä verkkoportaalissa omassa ympäristössäsi.

![Power BI -raportit Power BI -raporttipalvelimella](media/get-started/powerbi-reports.png)

Power BI -raportti on usean perspektiivin tietomallinäkymä, jonka visualisoinnit edustavat eri havaintoja ja merkityksellisiä tietoja tietomallista.  Raportilla voi olla yksittäinen visualisointi tai sivuja, jotka ovat täynnä visualisointeja. Roolisi mukaan voit lukea ja tutkia raportteja, tai voit luoda muille raportteja.

Asenna [Power BI Desktop (optimoitu Power BI -raporttipalvelimelle)](quickstart-create-powerbi-report.md).

## <a name="paginated-reports"></a>Sivutetut raportit
Sivutetut raportit (.RDL)ovat asiakirjatyylisiä, visualisointeja sisältäviä raportteja, joissa taulukot laajentuvat vaaka- ja pystysuunnassa kaikkien tietojen näyttämiseksi, sivulta toiselle jatkuen tarpeen mukaan. Ne sopivat erinomaisesti pikselintarkasti täydellisesti aseteltuihin kiinteisiin raportteihin, jotka on optimoitu tulostettavaksi esimerkiksi PDF- tai Word-tiedostoina.

![Sivutetut raportit Power BI -raporttipalvelimella](media/get-started/paginated-reports.png)

Voit luoda ulkoasultaan moderneja raportteja käyttämällä [raportin muodostinta](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) tai Report Designeria [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt) -työkaluista.

## <a name="reporting-services-mobile-reports"></a>Reporting Servicesin mobiiliraportit
Mobiiliraportit yhdistyvät paikallisiin tietoihin ja niiden reagoiva asettelu sopeutuu eri laitteille ja näytön suunnan mukaisesti. Voit luoda ne SQL Serverin mobiiliraportin julkaisijalla.

Lisätietoa [Reporting Servicesin mobiiliraporteista](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher). 

## <a name="report-server-programming-features"></a>Raporttipalvelimen ohjelmointiominaisuudet
Hyödynnä Power BI -raporttipalvelimen ohjelmointiominaisuudet, joiden avulla voit laajentaa ja mukauttaa raporttitoiminnallisuuksia. Ohjelmointirajapintojen kautta voit integroida niitä mukautettuihin sovelluksiin sekä laajentaa tietojen ja raporttien käsittelyä sovelluksissa.

Lisää [ohjeita raporttipalvelinkehittäjälle](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  
[Raportin muodostimen lataaminen](https://www.microsoft.com/download/details.aspx?id=53613)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)


