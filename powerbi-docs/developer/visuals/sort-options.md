---
title: Lajittele
description: Power BI:n visualisoinnin oletusarvoiset lajittelutoiminnot.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f3d913e2bce34850dfae4c9486b2e43c78521a58
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424512"
---
# <a name="sorting-options"></a>Lajitteluasetukset

`Sorting` määrittää visualisoinnin oletusarvoiset lajitteluntoiminnot.
Ominaisuus edellyttää jonkin alla kuvatuista parametreista:

## <a name="default-sorting"></a>Oletuslajittelu

`default`-asetus on yksinkertaisin muoto. Sen avulla voidaan lajitella DataMappings-osassa esitettyjä tietoja.
Tämä vaihtoehdon myötä käyttäjällä on mahdollisuus lajitella DataMappings ja määrittää lajittelusuunta.

```json
    "sorting": {
        "default": {   }
    }
```

![Lajitteluasetukset pikavalikossa](./media/sorting.png)

## <a name="implicit-sorting"></a>Implisiittinen lajittelu

`implicit` on lajittelua matriisiparametrilla `clauses`, joka kuvailee kunkin tietoroolin lajittelun.
`implicit` tarkoittaa, että visualisoinnin käyttäjä ei voi muuttaa lajittelujärjestystä.
Power BI ei näytä lajitteluasetuksia visualisoinnin valikossa. Power BI kuitenkin lajittelee tiedot määritettyjen asetusten mukaan.

`clauses`-parametrit voivat sisältää useita objekteja, joilla on kaksi parametria:

- `role`-parametrilla lajittelulle määritetään `DataMapping`.

- `direction`-parametrilla lajittelulle määritetään suunta (1 = nouseva, 2 = laskeva).

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

`custom` tarkoittaa, että kehittäjä hallitsee lajittelua visualisoinnin koodin kautta.
