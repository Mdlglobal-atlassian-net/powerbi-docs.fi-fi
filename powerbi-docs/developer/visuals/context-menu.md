---
title: Power BI:n visualisointien toiminnot ja ominaisuudet
description: Tässä artikkelissa kuvataan Power BI:n visualisointien toiminnot ja ominaisuudet.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7d24ea77fd73ca6a83176d1b8560c88fa98a8d6b
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819188"
---
# <a name="add-context-menu-to-power-bi-visual"></a>Pikavalikon lisääminen Power BI -visualisointiin

Käytettävissä ovat `selectionManager.showContextMenu()` sekä parametrit `selectionId` ja sijainti (`{x:, y:}` objektina), jos haluat Power BI:n näyttävän pikavalikon visualisointia varten.

> [!IMPORTANT]
> `selectionManager.showContextMenu()` otettiin käyttöön visualisointien ohjelmointirajapinnassa 2.2.0.

Yleensä se lisätään hiiren kakkospainikkeen tapahtumana (tai kosketuslaitteilla pitkän painalluksen tapahtumana) Pikavalikko lisättiin malli-pylväskaavioon viitteeksi:

```typescript
    public update(options: VisualUpdateOptions) {
        //...
        //handle context menu
        this.svg.on('contextmenu', () => {
            const mouseEvent: MouseEvent = d3.event as MouseEvent;
            const eventTarget: EventTarget = mouseEvent.target;
            let dataPoint = d3.select(eventTarget).datum();
            this.selectionManager.showContextMenu(dataPoint? dataPoint.selectionId : {}, {
                x: mouseEvent.clientX,
                y: mouseEvent.clientY
            });
            mouseEvent.preventDefault();
        });
```
