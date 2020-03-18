---
title: Ulkoisten kirjastojen lisääminen Power BI -visualisointeihin
description: Tässä artikkelissa kuvataan ulkoisten kirjastojen lisääminen Power BI -visualisointeihin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 02/24/2020
ms.openlocfilehash: 13d5f2ed62ddefb8ac99fe2c91c72fc599a15936
ms.sourcegitcommit: ced8c9d6c365cab6f63fbe8367fb33e6d827cb97
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/07/2020
ms.locfileid: "78922501"
---
# <a name="adding-external-libraries"></a>Ulkoisten kirjastojen lisääminen

Tässä artikkelissa kuvataan ulkoisten kirjastojen lisääminen Power BI -visualisointeihin. Se sisältää tietoja ulkoisten kirjastojen asentamisesta, tuomisesta ja kutsumisesta Power BI -visualisoinnin koodista.

## <a name="javascript-libraries"></a>JavaScript-kirjastot

1. Asenna ulkoinen JavaScript-kirjasto millä tahansa pakettihallintatyökalulla (esimerkiksi *npm* tai *yarn*).
2. Tuo vaaditut moduulit lähdetiedostoihin ulkoisen kirjaston avulla.

>[!NOTE]
>Jos haluat lisätä tyypit JavaScript-kirjastoosi ja hankkia IntelliSensen sekä kääntämisaikaisen suojauksen, varmista, että asennat oikean paketin.

### <a name="installing-the-d3-library"></a>d3-kirjaston asentaminen

Tässä esimerkissä asennetaan [d3-kirjasto](https://www.npmjs.com/package/d3) ja paketti [@types/d3](https://www.npmjs.com/package/@types/d3) [npm:llä](https://www.npmjs.com/).

Näet esimerkin kokonaisuudessaan [Power BI -visualisointien](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L29) koodin ohjeartikkelista.

1. Asenna paketit *d3* ja *d3 types*.

    ```powershell
    npm install d3@5 --save
    npm install @types/d3@5 --save
    ```

2. Tuo *d3*-kirjasto sitä käyttäviin tiedostoihin (esimerkiksi `visual.ts`).

    ```typescript
    import * as d3 from "d3";
    ```

## <a name="css-framework"></a>CSS-kehys

1. Asenna ulkoinen CSS-kehys millä tahansa pakettihallintatyökalulla (esimerkiksi *npm* tai *yarn*).
2. Sisällytä visualisoinnin tiedostoon `.less` lauseke `import`.

### <a name="installing-bootstrap"></a>Bootstrapin asentaminen

Tässä esimerkissä asennetaan [bootstrap](https://www.npmjs.com/package/bootstrap) [npm:llä](https://www.npmjs.com/).

Näet esimerkin kokonaisuudessaan [Power BI -visualisointien](https://github.com/Microsoft/powerbi-visuals-sankey/blob/c8200da56913cd8b253be949a35fad0f4472b6de/style/visual.less#L32) koodin ohjeartikkelista.

1. Asenna *bootstrap*-paketti.

    ```powershell
    npm install bootstrap --save
    ```

2. Sisällytä lauseke `import` kohteeseen `visual.less`.

    ```less
    @import (less) "node_modules/bootstrap/dist/css/bootstrap.css";
    ```
