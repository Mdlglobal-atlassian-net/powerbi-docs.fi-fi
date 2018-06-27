---
title: 'Project Online: tietoihin yhdistäminen Power BI Desktopilla'
description: 'Project Online: tietoihin yhdistäminen Power BI Desktopilla'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6cae9bdfbb89e8c3a11e8ee3fec45327296319b3
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34288908"
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: tietoihin yhdistäminen Power BI Desktopilla
Voit muodostaa Power BI Desktopilla yhteyden Project Onlinessa oleviin tietoihin.

### <a name="step-1-download-power-bi-desktop"></a>Vaihe 1: Power BI Desktopin lataaminen
1. Hanki **Power BI Desktop** tietokoneellesi [lataamalla Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521662) ja suorittamalla sen asennusohjelma.

### <a name="step-2-connect-to-project-online-with-odata"></a>Vaihe 2: Yhteyden muodostaminen Project Onlineen ODatan kautta
1. Käynnistä **Power BI Desktop**.
2. Valitse *aloitusnäytöstä* toiminto **Nouda tiedot**.
3. Valitse **OData-syöte** ja valitse **Yhdistä**.
4. Kirjoita osoite URL-kenttään OData-syötteesi osoite ja valitse sitten OK.
   
   Jos Project Web App ‑sivustosi osoite on muotoa https://\<vuokraajannimi\>.sharepoint.com/sites/pwa, niin OData-syötteen annettava osoite on muotoa https://\<vuokraajannimi\>.sharepoint.com/sites/pwa/\_api/Projectdata.
   
   Tässä esimerkissä käytetään osoitetta https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop kehottaa sinua todentamaan itsesi Office 365 ‑tilin avulla. Valitse organisaation tili ja anna tunnistetietosi.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

Huomaa, että tilillä, jota käytät yhteyden muodostamiseksi OData-syötteeseen, on oltava Project Web App ‑sivustolle vähintään yksi Portfolion katselutoiminto ‑käyttöoikeus. 

Tästä näkymästä voit valita mihin taulukoihin haluat muodostaa yhteyden ja luoda kyselyn.  Haluatko käsityksen siitä, miten pääset alkuun?  Seuraavassa blogikirjoituksessa kerrotaan, miten Project Online ‑tiedoista voidaan luoda edistymiskäyrä.  Blogikirjoituksessa puhutaan Power Queryn käyttämisestä yhteyden muodostamiseksi Project Onlineen, mutta sama koskee Power BI Desktopiakin.

[Edistymiskäyrien luominen projektille Power Pivot’n ja Power Queryn avulla](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

