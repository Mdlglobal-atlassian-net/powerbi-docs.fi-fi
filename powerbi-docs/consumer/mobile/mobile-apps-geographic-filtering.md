---
title: Raportin suodattaminen maantieteellisen sijainnin mukaan Power BI ‑mobiilisovelluksessa
description: Lue lisää siitä, miten raportti voidaan suodattaa maantieteellisen sijainnin mukaan Microsoft Power BI ‑mobiilisovelluksissa, jos raportin omistaja on määrittänyt maantieteelliset tunnisteet.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: painbar
ms.openlocfilehash: 7ee8887752f6a5161e0046e4aac1711f2ce64922
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276210"
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>Raportin suodattaminen maantieteellisen sijainnin mukaan Power BI ‑mobiilisovelluksessa
Koskee seuraavia:

| ![iPhone](./media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![iPad](./media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![Android-puhelin](./media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![Android-tabletti](./media/mobile-apps-view-dashboard/android-tablet-logo-50-px.png) | ![Windows Phone](./media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |Windows 10 -puhelimet |

Kun tarkastelet Power BI ‑raporttia mobiililaitteelta, näetkö oikeassa yläkulmassa pienen nuppineulakuvakkeen? Jos näet, voit suodattaa raportin oman maantieteellisen sijaintisi mukaan.

> [!NOTE]
> Voit suodattaa sijainnin mukaan ainoastaan, jos raportin maantieteelliset nimet ovat englanniksi; esimerkiksi ”New York City” tai ”Germany”. Windows 10 ‑tabletit ja ‑tietokoneet eivät tue maantieteellistä suodatusta, mutta Windows 10 ‑puhelimet tukevat.

>[!NOTE]
>Power BI -mobiilisovellustuki **Windows 10 Mobilea käyttäville puhelimille** lopetetaan 16. maaliskuuta 2021. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=2121400)

## <a name="filter-your-report-by-your-geographic-location"></a>Raportin suodattaminen maantieteellisen sijaintisi mukaan
1. Avaa mobiililaitteellasi raportti Power BI ‑mobiilisovelluksessa.
2. Jos raportissa on maantieteellisiä tietoja, näyttöön tulee sanoma, jossa kysytään, saako Power BI käyttää sijaintiasi. Valitse **Salli** ja napauta sitten uudelleen **Salli**.
3. Napauta nuppineulakuvaketta ![Nuppineulakuvake](./media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png). Raportin ominaisuuksista riippuen voit suodattaa tiedot joko kaupungin mukaan, osavaltion/provinssin mukaan tai maan/alueen mukaan. Suodatin näyttää vain asetukset, jotka vastaavat senhetkistä sijaintiasi.
   
    ![Nuppineulasuodatin](./media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>Miksi en näe raportissa sijaintitunnisteita?
Jotta näkisit sijaintitunnisteet, kaikkien alla mainitun kolmen ehdon on täytyttävä. 

* Power BI Desktopissa raportin luoneen henkilön [on pitänyt luokitella maantieteellisiä tietoja](../../transform-model/desktop-mobile-geofiltering.md), kuten kaupunki, osavaltio tai maa/alue, vähintään yhteen sarakkeeseen.
* Olet sellaisessa paikassa, josta on tietoja kyseisessä sarakkeessa.
* Käytät jotakin seuraavista mobiililaitteista:
  * iOS (iPad, iPhone, iPod)
  * Android (puhelin ja tabletti).
  * Windows 10 ‑puhelin (muut Windows 10 ‑laitteet, kuten pöytäkoneet ja tabletit, eivät tue maantieteellistä suodatusta).

Lue lisää [maantieteellisen suodatuksen määrittämisestä](../../transform-model/desktop-mobile-geofiltering.md) Power BI Desktopissa.

### <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI:n yhdistäminen reaalimaailman tietoihin](mobile-apps-data-in-real-world-context.md) mobiilisovellusten avulla
* [Tietojen luokittelu Power BI Desktopissa](../../transform-model/desktop-data-categorization.md) 
* Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
