---
title: Maantieteellisten suodattimien määrittäminen Power BI Desktopissa mobiilisovelluksille
description: Kun määrität maantieteellisen suodatuksen Power BI Desktopissa olevassa mallissasi, voit suodattaa tietoja sijainnillesi automaattisesti Power BI -mobiilisovelluksissa.
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: 27c59fb550b608a7ae33cfcef1849f480d599b93
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83324352"
---
# <a name="set-geographic-filters-in-power-bi-desktop-for-use-in-the-mobile-app"></a>Maantieteellisten suodattimien määrittäminen Power BI Desktopissa käytettäviksi mobiilisovelluksissa
Power BI Desktopissa voit [luokitella maantieteellisiä tietoja](desktop-data-categorization.md) saraketta kohden, joten Power BI Desktop tietää, miten käsitellä raportin visualisoinnissa olevia arvoja. Toinen etu on, että kun sinä tai työtoverisi tarkastelevat kyseistä raporttia Power BI -mobiilisovelluksissa, Power BI tarjoaa automaattisesti sijaintianne vastaavat maantieteelliset suodattimet. 

Oletetaan esimerkiksi, että olet myyntipäällikkö matkalla tapaamaan asiakkaita, ja haluat suodattaa nopeasti kokonaismyynnin ja tuoton sen asiakkaan osalta, jonka aiot tavata. Haluat eritellä tämänhetkistä sijaintiasi koskevat tiedot joko osavaltion, kaupungin tai todellisen osoitteen mukaan. Myöhemmin, jos sinulla on aikaa jäljellä, haluat käydä muiden lähistöllä toimivien asiakkaiden luona. Voit [suodattaa raportin sijaintisi mukaan kyseisten asiakkaiden löytämiseksi](../consumer/mobile/mobile-apps-geographic-filtering.md).

> [!NOTE]
> Voit suodattaa mobiilisovelluksessa sijainnin mukaan ainoastaan, jos raportin maantieteelliset nimet ovat englanniksi &#150; esimerkiksi ”New York City” tai ”Germany”.
> 
> 

## <a name="identify-geographic-data-in-your-report"></a>Määritä raporttisi maantieteelliset tiedot
1. Siirry Power BI Desktopissa tietonäkymään ![Tietonäkymäkuvake](media/desktop-mobile-geofiltering/pbi_desktop_data_icon.png).
2. Valitse sarake, jossa on maantieteelliset tiedot &#151; esimerkiksi Kaupunki-sarake.
   
    ![Kaupunki-sarake](media/desktop-mobile-geofiltering/power-bi-desktop-geo-column.png)
3. Valitse **Mallinnus**-välilehdeltä **Tietoluokka** ja sitten oikea luokka &#151; tässä esimerkissä **Kaupunki**.
   
    ![Tietoluokkaruutu](media/desktop-mobile-geofiltering/power-bi-desktop-geo-category.png)
4. Jatka maantieteellisten tietojen luokkien määrittämistä muiden mallin kenttien osalta. 
   
   > [!NOTE]
   > Voit määrittää useita sarakkeita kullekin mallin tietoluokalle, mutta jos teet näin, malli ei voi suodattaa maantiedon mukaan Power BI -mobiilisovelluksessa. Voit käyttää maantieteellistä suodatusta mobiilisovelluksissa määrittämällä vain yhden sarakkeen kullekin tietoluokalle &#151; esimerkiksi vain yksi **Kaupunki**-sarake, yksi **Osavaltio tai Provinssi** -sarake ja yksi **Valtio**-sarake. 
   > 
   > 

## <a name="create-visuals-with-your-geographic-data"></a>Luo visualisointeja maantieteellisillä tiedoilla
1. Siirry raporttinäkymään ![Raporttinäkymän kuvake](media/desktop-mobile-geofiltering/power-bi-desktop-report-icon.png)ja luo visualisointeja, jotka käyttävät tietojesi maantieteellisiä kenttiä. 
   
    ![Raportti, jossa kartta](media/desktop-mobile-geofiltering/power-bi-desktop-geo-report.png)
   
    Tässä esimerkissä malli sisältää myös lasketun sarakkeen, joka yhdistää kaupungin ja osavaltion yhteen sarakkeeseen. Lue aiheesta [laskettujen sarakkeiden luominen Power BI Desktopissa](desktop-calculated-columns.md).
   
    ![Kaupunki + Osavaltio -kenttä](media/desktop-mobile-geofiltering/power-bi-desktop-city-state-column.png)
2. Julkaise raportti Power BI -palveluun.

## <a name="view-the-report-in-power-bi-mobile-app"></a>Tarkastele raporttia Power BI -mobiilisovelluksessa
1. Avaa raportti missä tahansa [Power BI -mobiilisovelluksessa](../consumer/mobile/mobile-apps-for-mobile-devices.md).
2. Jos olet maantieteellisessä sijainnissa, josta raportissa on tietoja, voit suodattaa sen automaattisesti sijaintiisi.
   
    ![Mobiilisovelluksen Geo-suodatin](media/desktop-mobile-geofiltering/power-bi-mobile-geo-map-set-filter.png)

Lue lisää aiheesta [raportin suodattaminen sijainnin mukaan Power BI -mobiilisovelluksissa](../consumer/mobile/mobile-apps-geographic-filtering.md).

## <a name="next-steps"></a>Seuraavat vaiheet
* [Tietojen luokittelu Power BI Desktopissa](desktop-data-categorization.md)  
* Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
