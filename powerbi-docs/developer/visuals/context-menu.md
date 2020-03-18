---
title: Power BI:n visualisointien toiminnot ja ominaisuudet
description: Tässä artikkelissa kuvataan Power BI:n visualisointien toiminnot ja ominaisuudet.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 1e2fbe3288e5dbb759a56ad1c299db2e277408b2
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380751"
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
