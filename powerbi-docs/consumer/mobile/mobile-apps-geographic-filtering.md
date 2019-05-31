---
title: Raportin suodattaminen maantieteellisen sijainnin mukaan Power BI ‑mobiilisovelluksessa
description: Lue lisää siitä, miten raportti voidaan suodattaa maantieteellisen sijainnin mukaan Microsoft Power BI ‑mobiilisovelluksissa, jos raportin omistaja on määrittänyt maantieteelliset tunnisteet.
author: mshenhav
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 02/09/2018
ms.author: mshenhav
ms.openlocfilehash: 828dcb4aeb8b7c5e69292685470f112a2d85cb71
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61349490"
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>Raportin suodattaminen maantieteellisen sijainnin mukaan Power BI ‑mobiilisovelluksessa
Koskee seuraavia:

| ![iPhone](./media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![iPad](./media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![Android-puhelin](./media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![Android-tabletti](./media/mobile-apps-geographic-filtering/android-tablet-logo-50-px.png) | ![Android-tabletti](./media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
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
3. Napauta nuppineulakuvaketta ![Nuppineulakuvake](./media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png). Raportin ominaisuuksista riippuen voit suodattaa tiedot joko kaupungin mukaan, osavaltion/provinssin mukaan tai maan/alueen mukaan. Suodatin näyttää vain asetukset, jotka vastaavat senhetkistä sijaintiasi.
   
    ![Nuppineulasuodatin](./media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>Miksi en näe raportissa sijaintitunnisteita?
Jotta näkisit sijaintitunnisteet, kaikkien kolmen ehdon on täytyttävä: 

* Power BI Desktopissa raportin luonut henkilö [on luokitellut maantieteellisiä tietoja](../../desktop-mobile-geofiltering.md), kuten kaupunki, osavaltio tai maa/alue, vähintään yhteen sarakkeeseen.
* Olet sellaisessa paikassa, josta on tietoja kyseisessä sarakkeessa.
* Käytät jotakin seuraavista mobiililaitteista:
  * iOS (iPad, iPhone, iPod)
  * Android-puhelin tai ‑tabletti
  * Windows 10 ‑puhelin (muut Windows 10 ‑laitteet, kuten pöytäkoneet ja tabletit, eivät tue maantieteellistä suodatusta).

Lue lisää [maantieteellisen suodatuksen määrittämisestä](../../desktop-mobile-geofiltering.md) Power BI Desktopissa.

### <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI:n yhdistäminen reaalimaailman tietoihin](mobile-apps-data-in-real-world-context.md) mobiilisovellusten avulla
* [Tietojen luokittelu Power BI Desktopissa](../../desktop-data-categorization.md) 
* Ilmenikö kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

