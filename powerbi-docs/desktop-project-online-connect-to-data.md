---
title: 'Project Online: tietoihin yhdistäminen Power BI Desktopilla'
description: 'Project Online: tietoihin yhdistäminen Power BI Desktopilla'
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e3bb5f3527da11f781892fae23ae369edfe4676b
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "73878010"
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: tietoihin yhdistäminen Power BI Desktopilla
Voit muodostaa Power BI Desktopilla yhteyden Project Onlinessa oleviin tietoihin.

## <a name="step-1-download-power-bi-desktop"></a>Vaihe 1: Power BI Desktopin lataaminen
1. Hanki **Power BI Desktop** tietokoneellesi [lataamalla Power BI Desktop](https://go.microsoft.com/fwlink/?LinkID=521662) ja suorittamalla sen asennusohjelma.

## <a name="step-2-connect-to-project-online-with-odata"></a>Vaihe 2: Yhteyden muodostaminen Project Onlineen ODatan kautta
1. Käynnistä **Power BI Desktop**.
2. Valitse *aloitusnäytöstä* toiminto **Nouda tiedot**.
3. Valitse **OData-syöte** ja valitse **Yhdistä**.
4. Kirjoita osoite URL-kenttään OData-syötteesi osoite ja valitse sitten OK.
   
   Jos Project Web App ‑sivustosi osoite on muotoa *https://\<vuokraajannimi\>.sharepoint.com/sites/pwa*, niin OData-syötteen annettava osoite on muotoa *https://\<vuokraajannimi\>.sharepoint.com/sites/pwa/\_api/Projectdata*.
   
   Tässä esimerkissä käytetään osoitetta https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop kehottaa sinua todentamaan itsesi Office 365 ‑tilin avulla. Valitse organisaation tili ja anna tunnistetietosi.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

Tilillä, jota käytät yhteyden muodostamiseksi OData-syötteeseen, on oltava Project Web App ‑sivustolle vähintään yksi Portfolion katselutoiminto ‑käyttöoikeus. 

Tästä näkymästä voit valita mihin taulukoihin haluat muodostaa yhteyden ja luoda kyselyn.  Haluatko käsityksen siitä, miten pääset alkuun?  Seuraavassa blogikirjoituksessa kerrotaan, miten Project Online ‑tiedoista voidaan luoda edistymiskäyrä.  Blogikirjoituksessa puhutaan Power Queryn käyttämisestä yhteyden muodostamiseksi Project Onlineen, mutta sama koskee Power BI Desktopiakin.

[Edistymiskäyrien luominen projektille Power Pivot’n ja Power Queryn avulla](https://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

