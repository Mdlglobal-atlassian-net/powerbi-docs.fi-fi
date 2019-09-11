---
title: Nouda enemmän tietoja Power BI:stä
description: Tässä artikkelissa kuvataan suurten tietojoukkojen segmentoidun noudon ottaminen käyttöön Power BI:n visualisoinneille.
author: AviSander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7e5ecc0e317a21d10e76e9413926822ac4d6760b
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/03/2019
ms.locfileid: "70237150"
---
# <a name="fetch-more-data-from-power-bi"></a>Nouda enemmän tietoja Power BI:stä

Tässä artikkelissa kerrotaan, miten voit ladata lisää tietoja, jos haluat ohittaa arvopisteen kiinteän 30 kt:n rajan. Tämä menetelmä antaa tiedot lohkoina. Voit parantaa suorituskykyä määrittämällä lohkon koon käyttötapauksesi mukaiseksi.  

## <a name="enable-a-segmented-fetch-of-large-datasets"></a>Suurten tietojoukkojen segmentoidun noudon ottaminen käyttöön

`dataview`-segmenttitilaksi määritetään dataReductionAlgorithm-kohteen ikkunan koko visualisoinnin *capabilities.json* -tiedostoon vaadittua dataViewMapping-määritystä varten. `count` määrittää ikkunan koon, joka rajoittaa `dataview`-kohteeseen liitettävien uusien tietorivien määrää jokaisessa päivityksessä.

Lisää seuraava koodi *capabilities.json*-tiedostoon:

```typescript
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "window": {
                        "count": 100
                    }
                }
            }
    }
]
```

Uudet segmentit lisätään olemassa olevaan `dataview`-kohteeseen ja annetaan visualisoinnille `update`-kutsuna.

## <a name="usage-in-the-power-bi-visual"></a>Käyttö Power BI:n visualisoinnissa

Voit määrittää, onko tietoja olemassa, tarkistamalla, onko `dataView.metadata.segment` olemassa:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

Voit myös tarkistaa, onko kyseessä ensimmäinen päivitys vai myöhempi päivitys, tarkistamalla kohteen `options.operationKind`. Seuraavassa koodissa `VisualDataChangeOperationKind.Create` viittaa seuraavassa koodissa ensimmäiseen segmenttiin ja `VisualDataChangeOperationKind.Append` seuraaviin segmentteihin.

Malli toteutuksesta on seuraavassa koodikatkelmassa:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subsequent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

Voit myös käynnistää `fetchMoreData`-menetelmän käyttöliittymän tapahtumakäsittelijästä seuraavassa esitetyllä tavalla:

```typescript
btn_click(){
{
    // check if more data is expected for the current data view
    if (dataView.metadata.segment) {
        //request for more data if available; as a response, Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example, when the 100 MB limit has been reached
        }
    }
}
```

Vastauksena `this.host.fetchMoreData`-menetelmän kutsumiseen Power BI kutsuu visualisoinnin `update`-menetelmää uuden segmentin tiedoilla.

> [!NOTE]
> Asiakkaan muistirajoitteiden välttämiseksi noudettavien tietojen kokonaismäärän rajoituksena Power BI:ssä on tällä hetkellä 100 Mt. Huomaat, että enimmäismäärä on saavutettu, kun fetchMoreData () palauttaa arvon `false`.
