---
title: Power BI:n visualisointien toiminnot ja ominaisuudet
description: Tässä artikkelissa kuvataan Power BI:n visualisointien toiminnot ja ominaisuudet.
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 206f1aec7c76b00b6f725d8469eb3e483a01c653
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061772"
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
