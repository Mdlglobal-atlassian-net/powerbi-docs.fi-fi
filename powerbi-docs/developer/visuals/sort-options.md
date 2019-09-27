---
title: Power BI -visualisointien lajitteluasetukset
description: Tässä artikkelissa käsitellään Power BI:n visualisointien lajittelutoiminnon oletusasetuksia.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: a360f619428a01c4e7a30481374d042b8e368682
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193905"
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
