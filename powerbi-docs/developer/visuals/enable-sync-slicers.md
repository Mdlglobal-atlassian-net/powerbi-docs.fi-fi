---
title: Synkronoi osittajat -toiminnon ottaminen käyttöön Power BI:n visualisoinneissa
description: Tässä artikkelissa kuvataan Synkronoi osittajat -toiminnon lisääminen Power BI:n visualisointeihin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 345971384fff0e0b215d2898ee1684f4a5bac486
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80114309"
---
# <a name="sync-slicers-in-power-bi-visuals"></a>Synkronoi osittajat -toiminto Power BI:n visualisoinneissa

[Synkronoi osittajat](https://docs.microsoft.com/power-bi/desktop-slicers) -toiminnon tuki edellyttää, että mukautettu osittaja käyttää ohjelmointirajapinnan versiota 1,13 tai uudempaa versiota.

Lisäksi sinun on otettava asetus käyttöön *capabilities.json*-tiedostossa seuraavassa koodissa esitetyllä tavalla:

```json
{
    ...
    "supportsHighlight": true,
    "suppressDefaultTitle": true,
    "supportsSynchronizingFilterState": true,
    "sorting": {
        "default": {}
    }
}
```

Kun olet ladannut *capabilities.json*-tiedoston, voit tarkastella **Synkronoi osittajat** -asetusruutua, kun valitset mukautetun osittajan visualisoinnin.

> [!NOTE]
> Synkronoi osittajat -toiminto tukee enintään yhtä kenttää. Jos osittajassasi on vähintään kaksi kenttää (**Luokka** tai **Mittari**), toiminto on poissa käytöstä.

![Synkronoi osittajat -ruutu](media/enable-sync-slicers/sync-slicers-panel.png)

**Synkronoi osittajat** -ruudussa näkyy, että osittajan näkyvyys ja suodatus voidaan ottaa käyttöön useille raporttisivuille.
