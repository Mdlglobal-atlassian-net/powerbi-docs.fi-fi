---
title: Raportin suodattaminen maantieteellisen sijainnin mukaan Power BI ‑mobiilisovelluksessa
description: Lue lisää siitä, miten raportti voidaan suodattaa maantieteellisen sijainnin mukaan Microsoft Power BI ‑mobiilisovelluksissa, jos raportin omistaja on määrittänyt maantieteelliset tunnisteet.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/09/2018
ms.author: maggies
ms.openlocfilehash: 90d6e6f80be49e8d1c2a9605558a57834e24e285
ms.sourcegitcommit: ad9bd4e52471b1179f46f847960d5ed79c0c0761
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/11/2018
ms.locfileid: "30973582"
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>Raportin suodattaminen maantieteellisen sijainnin mukaan Power BI ‑mobiilisovelluksessa
Koskee seuraavia:

| ![iPhone](media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![iPad](media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![Android-puhelin](media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![Android-tabletti](media/mobile-apps-geographic-filtering/android-tablet-logo-50-px.png) | ![Android-tabletti](media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |Windows 10 ‑puhelimet |

Kun tarkastelet Power BI ‑raporttia mobiililaitteelta, näetkö oikeassa yläkulmassa pienen nuppineulakuvakkeen? Jos näet, voit suodattaa raportin oman maantieteellisen sijaintisi mukaan.

> [!NOTE]
> Voit suodattaa sijainnin mukaan ainoastaan, jos raportin maantieteelliset nimet ovat englanniksi &#150; esimerkiksi ”New York City” tai ”Germany”. Windows 10 ‑tabletit ja ‑tietokoneet eivät tue maantieteellistä suodatusta, mutta Windows 10 ‑puhelimet tukevat.
> 
> 

## <a name="filter-your-report-by-your-geographic-location"></a>Raportin suodattaminen maantieteellisen sijaintisi mukaan
1. Avaa mobiililaitteellasi raportti Power BI ‑mobiilisovelluksessa.
2. Jos raportissa on maantieteellisiä tietoja, näyttöön tulee sanoma, jossa kysytään, saako Power BI käyttää sijaintiasi. Valitse **Salli** ja napauta sitten uudelleen **Salli**.
3. Napauta nuppineulakuvaketta ![Nuppineulakuvake](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png). Raportin ominaisuuksista riippuen voit suodattaa tiedot joko kaupungin mukaan, osavaltion/provinssin mukaan tai maan/alueen mukaan. Suodatin näyttää vain asetukset, jotka vastaavat senhetkistä sijaintiasi.
   
    ![Nuppineulasuodatin](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>Miksi en näe raportissa sijaintitunnisteita?
Jotta näkisit sijaintitunnisteet, kaikkien kolmen ehdon on täytyttävä: 

* Power BI Desktopissa raportin luonut henkilö [on luokitellut maantieteellisiä tietoja](desktop-mobile-geofiltering.md), kuten kaupunki, osavaltio tai maa/alue, vähintään yhteen sarakkeeseen.
* Olet sellaisessa paikassa, josta on tietoja kyseisessä sarakkeessa.
* Käytät jotakin seuraavista mobiililaitteista:
  * iOS (iPad, iPhone, iPod)
  * Android-puhelin tai ‑tabletti
  * Windows 10 ‑puhelin (muut Windows 10 ‑laitteet, kuten pöytäkoneet ja tabletit, eivät tue maantieteellistä suodatusta).

Lue lisää [maantieteellisen suodatuksen määrittämisestä](desktop-mobile-geofiltering.md) Power BI Desktopissa.

### <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI:n yhdistäminen reaalimaailman tietoihin](mobile-apps-data-in-real-world-context.md) mobiilisovellusten avulla
* [Tietojen luokittelu Power BI Desktopissa](desktop-data-categorization.md) 
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

