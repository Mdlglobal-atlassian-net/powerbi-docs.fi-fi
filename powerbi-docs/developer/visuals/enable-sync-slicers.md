---
title: Osittajien synkronoinnin käyttöönotto
description: Synkronoi osittajat -toiminnon lisääminen Power BI:n visualisointeihin
author: EugeneElkin
ms.author: v-evelk
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9966475e8bcaccad2090451b47ef09ef0a9af125
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425018"
---
# <a name="sync-slicers"></a>Synkronoi osittajat

Tukeakseen [osittajien synkronointia](https://docs.microsoft.com/power-bi/desktop-slicers) mukautetun osittajan visualisoinnin on käytettävä ohjelmointirajapintaa 1.13 tai uudempaa.

Käytössä pitää olla myös asetus `capabilities.json` (katso alla oleva malli).

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

Kun olet tehnyt muutoksia kohtaan `capabilities.json`, näet Synkronoi osittajat -asetuspaneelin, kun napsautat mukautettua osittajan visualisointia.

> [!NOTE]
> Jos osittajassa on useampi kuin yksi kenttä (luokka tai mittari), ominaisuus poistetaan käytöstä, koska osittajien synkronointi ei tue useita kenttiä.

![Synkronoi osittajat -paneeli](./media/sync-slicers-panel.png)

Paneelissa näkyy, että osittajan näkyvyys ja suodatus voidaan ottaa käyttöön useille raporttisivuille.
