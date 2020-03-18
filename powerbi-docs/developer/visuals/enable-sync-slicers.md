---
title: Synkronoi osittajat -toiminnon ottaminen käyttöön Power BI:n visualisoinneissa
description: Tässä artikkelissa kuvataan Synkronoi osittajat -toiminnon lisääminen Power BI:n visualisointeihin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 88e7e4b83f303f2b366f276b5020194f55f21f25
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380711"
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
