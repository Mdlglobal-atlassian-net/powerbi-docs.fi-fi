---
title: Lisätietojen noutaminen
description: Suurten tietojoukkojen segmentoidun noudon ottaminen käyttöön Power BI:n visualisoinneille
author: AviSander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: bc8ff673927fd66bf44164e4e9950c279b98c6c1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425064"
---
# <a name="fetch-more-data-from-power-bi"></a>Nouda enemmän tietoja Power BI:stä

Tietojen lisääminen ohjelmointirajapintaan on ylittänyt 30 000 arvopisteen kiinteän rajan. Se tuo tiedot lohkoina. Lohkon koko on määritettävissä suorituskyvyn parantamiseksi käyttötapauksen mukaan.  

## <a name="enable-segmented-fetch-of-large-datasets"></a>Suurten tietojoukkojen segmentoidun noudon ottaminen käyttöön

Määritä `dataview`-segmenttitilassa dataReductionAlgorithm-ikkuna visualisoinnin `capabilities.json`-tiedostossa vaaditulle dataViewMapping-määritykselle.
`count` määrittää ikkunan koon, joka rajoittaa `dataview`-kohteeseen liitettyjen uusien tietorivien määrää kussakin päivityksessä.

Lisätään capabilities.json-tiedostoon

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

## <a name="usage-in-the-custom-visual"></a>Käyttö mukautetussa visualisoinnissa

Merkintätietojen olemassaolo voidaan määrittää tarkistamalla, onko `dataView.metadata.segment` olemassa:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

On myös mahdollista tarkistaa, onko kyseessä ensimmäinen vai myöhempi päivitys, tarkistamalla `options.operationKind`.

`VisualDataChangeOperationKind.Create` tarkoittaa ensimmäistä segmenttiä ja `VisualDataChangeOperationKind.Append` tarkoittaa seuraavia segmenttejä.

Esimerkki toteutuksesta on alla olevassa koodikatkelmassa:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subesquent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

`fetchMoreData`-menetelmä voidaan käynnistää myös käyttöliittymän tapahtumakäsittelijästä

```typescript
btn_click(){
{
    // check if more data is expected for the current dataview
    if (dataView.metadata.segment) {
        //request for more data if available, as resopnce Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example when the 100 MB limit has been reached
        }
    }
}
```

Power BI kutsuu visualisoinnin `update`-menetelmän uudella tietosegmentillä vastauksena `this.host.fetchMoreData`-menetelmän kutsuun.

> [!NOTE]
> Noudettavien tietojen kokonaismäärän rajoituksena Power BI:ssä on tällä hetkellä **100 Mt** asiakkaan muistirajoitteiden välttämiseksi. Huomaat tämän rajan saavuttamisen, kun fetchMoreData() palauttaa arvon 'epätosi'.*
