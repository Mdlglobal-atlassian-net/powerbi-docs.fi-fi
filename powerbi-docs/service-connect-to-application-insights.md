---
title: Muodosta yhteys Application Insightsiin Yhdistä Power BI:hin
description: Application Insights Power BI:hin
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/10/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 3f0a23c2bdb97c6fbc75981c40cb92c529550b1b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61177148"
---
# <a name="connect-to-application-insights-with-power-bi"></a>Application Insightsin yhdistäminen Power BI:hin
Power BI:n avulla voit luoda tehokkaita mukautettuja raporttinäkymiä [Application Insights](/azure/application-insights/app-insights-overview/) -telemetriatiedoista. Näet sovellustelemetrian uusilla tavoilla. Yhdistä mittareita useista sovelluksista tai komponenttipalveluista yhteen raporttinäkymään. Power BI -sisältöpaketin ensimmäisessä Application Insights -julkaisussa on pienoissovelluksia yleisiä käyttöön liittyviä arvoja varten. Näitä ovat muun muassa aktiiviset käyttäjät, sivunäkymä, istunnot, selain- ja käyttöjärjestelmäversiot sekä käyttäjien maantieteellinen jakauma kartalla.

Muodosta yhteys [Application Insights -sisältöpakettiin Power BI:tä varten](https://app.powerbi.com/getdata/services/application-insights).

>[!NOTE]
>Tämä integrointimenetelmä on nyt **vanhentunut**. Jos haluat tutustua tarkemmin suositeltuun tapaan yhdistää Application Insights Power BI:hin, käytä [analyysikyselyn vientitoimintoa](https://docs.microsoft.com/azure/application-insights/app-insights-export-power-bi#export-analytics-queries).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunasta **Nouda tiedot**.
   
    ![Nouda tiedot -painike](media/service-connect-to-application-insights/pbi_getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
    ![Nouda palvelut -painike](media/service-connect-to-application-insights/pbi_getservices.png)
3. Valitse **Application Insights** > **Nouda**.
   
    ![Application Insights -sisältöpaketti](media/service-connect-to-application-insights/appinsights.png)
4. Anna tiedot sovelluksesta, johon haluat muodostaa yhteyden, mukaan lukien **Application Insights -resurssin nimi**, **resurssiryhmä** ja **tilaustunnus**. Lisätietoja on alla kohdassa [Application Insights -parametrien löytäminen](#FindingAppInsightsParams).
   
    ![Application Insights -yhteyden valintaikkuna](media/service-connect-to-application-insights/pbi_contpkappinsitconnectndialog.png)    
5. Valitse **Kirjaudu sisään** ja muodosta yhteys näytön ohjeiden mukaisesti.
   
    ![Application Insights -yhteyteen kirjautuminen](media/service-connect-to-application-insights/pbi_contpkappinsitconnectn2.png)
6. Tuontiprosessi alkaa automaattisesti. Kun se on valmis, näkyviin tulee ilmoitus. Uusi raporttinäkymä, raportti ja tietojoukko näkyvät siirtymisruudussa tähdellä merkittyinä.  Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
    ![Application Insights -raporttinäkymä](media/service-connect-to-application-insights/pbi_contpkappinsitdash.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Application Insights -sisältöpaketti sisältää seuraavat taulukot ja arvot:  

    ´´´
    - ApplicationDetails  
    - UniqueUsersLast7Days   
    - UniqueUsersLast30Days   
    - UniqueUsersDailyLast30Days  
    - UniqueUsersByCountryLast7Days  
    - UniqueUsersByCountryLast30Days   
    - PageViewsDailyLast30Days   
    - SessionsLast7Days   
    - SessionsLast30Days  
    - PageViewsByBrowserVersionDailyLast30Days   
    - UniqueUsersByOperatingSystemLast7Days   
    - UniqueUsersByOperatingSystemLast30Days    
    - SessionsDailyLast30Days   
    - SessionsByCountryLast7Days   
    - SessionsByCountryLast30Days   
    - PageViewsByCountryDailyLast30Days  
    ´´´ 

<a name="FindingAppInsightsParams"></a>

## <a name="finding-parameters"></a>Parametrien etsiminen
Resurssin nimi, resurssiryhmä ja tilaustunnus löytyvät kaikki Azure-portaalista. Kun valitset nimen, näkyviin tulee yksityiskohtainen näkymä. Löydät kaikki tarvittavat arvot avattavan Essentials-valikon kautta.

![Application Insights -parametrit](media/service-connect-to-application-insights/pbi_contpkappinsitparams.png)

Kopioi ja liitä nämä Power BI:n kenttiin:

![Application Insights -parametrit](media/service-connect-to-application-insights/pbi_contpkappinsitparam2.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

