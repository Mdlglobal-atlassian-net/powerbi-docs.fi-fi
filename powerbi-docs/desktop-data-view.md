---
title: Tietonäkymä Power BI Desktopissa
description: Tietonäkymä Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: c8a96918049f2f1898ab80a9368a8d2f0a8fe53a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54286133"
---
# <a name="data-view-in-power-bi-desktop"></a>Tietonäkymä Power BI Desktopissa
**Tiedot-näkymän** avulla voit tarkastaa **Power BI Desktop** -mallin tiedot, tutustua niihin ja ymmärtämää niitä. Se poikkeaa taulukoiden, sarakkeiden ja tietojen tarkastelusta **kyselyeditorissa**. Tiedot-näkymässä tarkastelet tietojasi sen *jälkeen*, kun ne on ladattu tietomalliin.

Kun mallinnat tietojasi, haluat ehkä nähdä, mitä taulukossa tai sarakkeessa todella on ilman visualisoinnin luomista raporttipohjaan, usein ihan rivitasolle asti. Tämä on hyödyksi erityisesti silloin, kun luot mittareita ja laskettuja sarakkeita tai kun sinun on tunnistettava tietotyyppi tai tietoluokka.

Seuraavaksi katsotaan tarkemmin joitakin **Tietonäkymän** elementtejä.

![Tietonäkymä Power BI Desktopissa](media/desktop-data-view/dataview_fullscreen.png)

1. **Tietonäkymäkuvake** – Valitse tämä siirtyäksesi tietonäkymään.

2. **Tietoruudukko** – Näyttää valitun taulukon ja sen sarakkeet ja rivit. **Raportti-näkymässä** piilotetut sarakkeet näkyvät harmaina. Voit napsauttaa saraketta hiiren kakkospainikkeella tuodaksesi esiin valinnaiset tiedot.

3. **Mallinnusnauha** – Hallinnoi suhteita, luo laskelmia, muuta tietotyyppiä, muokkaa, sarakkeen tietoluokka.

4. **Kaavarivi** – Syötä DAX-kaavoja Mittayksiköt- ja Lasketut-sarakkeita varten.

5. **Haku** – Hae mallistasi taulukkoa tai saraketta.

6. **Kentät-lista** – Valitse taulukko tai sarake selattavaksi tietoruudukossa.

## <a name="filtering-in-data-view"></a>Tietonäkymässä suodattaminen

Voit myös suodattaa ja lajitella tietoja **Tietonäkymässä**. Jokaisessa sarakkeessa näkyy kuvake, joka tunnistaa lajittelusuunnan (jos käytössä).

![Power BI Desktopin tietonäkymässä lajitteleminen ja suodattaminen](media/desktop-data-view/dataview_sort-and-filter.png)

Voit suodattaa yksittäisiä arvoja tai käyttää sarakkeen tietoihin perustuvaa lisäsuodatusta. 

> [!NOTE]
> Kun Power BI -malli luodaan maa-asetukselle, joka eroaa senhetkisestä käyttöliittymästä ( jos malli on esimerkiksi luotu amerikanenglantiin ja tarkastelet sitä Espanjankielisessä käyttöliittymässä) hakuruutu ei näy käyttöliittymän tietonäkymässä muissa kuin tekstikentissä.
