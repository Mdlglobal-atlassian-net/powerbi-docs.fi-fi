---
title: Power BI -visualisointien lajitteluasetukset
description: Tässä artikkelissa käsitellään Power BI:n visualisointien lajittelutoiminnon oletusasetuksia.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 3cb8f5af63960667dc46cab1d818ba48943fd582
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79378066"
---
# <a name="sorting-options-for-power-bi-visuals"></a>Power BI -visualisointien lajitteluasetukset

Tässä artikkelissa kuvataan, miten*lajittelu*asetukset määrittävät Power BI:n visualisointien lajittelun toiminnan. 

Lajittelutoiminto edellyttää jotakin seuraavista parametreista.

## <a name="default-sorting"></a>Oletuslajittelu

`default`-asetus on yksinkertaisin muoto. Sen avulla voidaan lajitella DataMappings-osassa esitettyjä tietoja. Tämän vaihtoehdon avulla käyttäjä voi lajitella tietojen yhdistämiset ja määrittää lajittelusuunnan.

```json
    "sorting": {
        "default": {   }
    }
```

![Lajitteluasetukset pikavalikossa](media/sort-options/sorting.png)

## <a name="implicit-sorting"></a>Implisiittinen lajittelu

Implisiittinen lajittelu on lajittelua matriisiparametrilla `clauses`, joka kuvailee jokaisen tietoroolin lajittelun. `implicit` tarkoittaa, että visualisoinnin käyttäjä ei voi muuttaa lajittelujärjestystä. Power BI ei näytä lajitteluasetuksia visualisoinnin valikossa. Power BI kuitenkin lajittelee tiedot määritettyjen asetusten mukaan.

`clauses`-parametrit voivat sisältää useita objekteja, joilla on kaksi parametria:

- `role`: lajittelulle määritetään `DataMapping`
- `direction`: lajittelulle määritetään suunta (1 = nouseva, 2 = laskeva)

```json
    "sorting": {
        "implicit": {
            "clauses": [
                {
                    "role": "category",
                    "direction": 1
                },
                {
                    "role": "measure",
                    "direction": 2
                }
            ]
        }
    }
```

## <a name="custom-sorting"></a>Mukautettu lajittelu

Mukautettu lajittelu tarkoittaa sitä, että kehittäjä hallitsee lajittelua visualisoinnin koodissa.
