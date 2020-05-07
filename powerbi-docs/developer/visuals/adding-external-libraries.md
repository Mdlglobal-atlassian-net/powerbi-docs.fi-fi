---
title: Ulkoisten kirjastojen lisääminen Power BI -visualisointeihin
description: Tässä artikkelissa kuvataan ulkoisten kirjastojen lisääminen Power BI -visualisointeihin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 02/24/2020
ms.openlocfilehash: 9df111e7545c43fe9b75784b1a95df4f37fd01e7
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80114125"
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
