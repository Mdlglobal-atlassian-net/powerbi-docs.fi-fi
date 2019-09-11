---
title: Synkronoi osittajat -toiminnon ottaminen käyttöön Power BI:n visualisoinneissa
description: Tässä artikkelissa kuvataan Synkronoi osittajat -toiminnon lisääminen Power BI:n visualisointeihin.
author: EugeneElkin
ms.author: v-evelk
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 4d7b73a5d06f34fd197464d4444d0e19d6c1c026
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/03/2019
ms.locfileid: "70237198"
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

![Synkronoi osittajat -ruutu](./media/sync-slicers-panel.png)

**Synkronoi osittajat** -ruudussa näkyy, että osittajan näkyvyys ja suodatus voidaan ottaa käyttöön useille raporttisivuille.
