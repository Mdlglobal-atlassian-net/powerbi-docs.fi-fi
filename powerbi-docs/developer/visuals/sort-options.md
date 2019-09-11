---
title: Power BI -visualisointien lajitteluasetukset
description: Tässä artikkelissa käsitellään Power BI:n visualisointien lajittelutoiminnon oletusasetuksia.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: cecec80dc9fe8570535cbd1e0c1e7114363472d8
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236669"
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

![Lajitteluasetukset pikavalikossa](./media/sorting.png)

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
