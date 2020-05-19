---
title: Värien lisääminen Power BI -visualisointeihin
description: Tässä artikkelissa kerrotaan, miten voit lisätä värejä Power BI -visualisointeihin ja käsitellä arvopisteitä värejä sisältävässä visualisoinnissa.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 03/27/2020
ms.openlocfilehash: 3f3574545d82ac11c762b7011afdc49cbe855224
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141162"
---
# <a name="add-colors-to-your-power-bi-visuals"></a>Värien lisääminen Power BI -visualisointeihin

Tässä artikkelissa kerrotaan, miten voit lisätä värejä visualisointeihin ja käsitellä arvopisteitä värejä sisältävässä visualisoinnissa.

`IVisualHost` paljastaa värin yhtenä palveluistaan.
Tämän artikkelin esimerkkikoodi muokkaa [SampleBarChart-visualisointia](https://github.com/microsoft/PowerBI-visuals-sampleBarChart).
Lähdekoodi on kohdassa [barChart.ts](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts).

Jos haluat aloittaa visualisointien luomisen, tutustu kohtaan [Power BI -visualisoinnin kehittäminen](custom-visual-develop-tutorial.md).

## <a name="add-color-to-data-points"></a>Värin lisääminen arvopisteisiin

Eri väri edustaa kutakin arvopistettä.
Lisää väri `BarChartDataPoint`-liittymään seuraavan esimerkin mukaisesti:

```typescript
/**
 * Interface for BarChart data points.
 *
 * @interface
 * @property {number} value    - Data value for point.
 * @property {string} category - Corresponding category of data value.
 * @property {string} color    - Color corresponding to data point.
 */
interface BarChartDataPoint {
    value: number;
    category: string;
    color: string;
};
```

## <a name="use-the-color-palette-service"></a>Värivalikoimapalvelun käyttäminen

`colorPalette`-palvelu hallitsee visualisoinnissa käytettyjä värejä.
Palvelun esiintymä on käytettävissä kohdassa `IVisualHost`.

Määritä se `update`-menetelmässä.

```typescript
constructor(options: VisualConstructorOptions) {
        this.host = options.host; // host: IVisualHost
        ...
    }

public update(options: VisualUpdateOptions) {

    let colorPalette: IColorPalette = host.colorPalette;
    ...
}
```

## <a name="assigning-color-to-data-points"></a>Värin määrittäminen arvopisteisiin

Määritä seuraavaksi `dataPoints`.
Tässä esimerkissä jokainen `dataPoints` sisältää arvon, luokan ja värin.
`dataPoints` voi sisältää myös muita ominaisuuksia.

Kohdassa `SampleBarChart` `visualTransform`-menetelmä kiteyttää `dataPoints`-laskennan.
Tämä menetelmä on osa palkkikaavion näkymämallia.
Koska menetelmä iteroi `dataPoints`-laskennan läpi kohdassa `visualTransform`, se on ihanteellinen paikka värien määrittelemiselle, kuten seuraavassa koodissa:

```typescript

public update(options: VisualUpdateOptions) {
    ....
    let viewModel: BarChartViewModel = visualTransform(options, this.host);
    ....
}

function visualTransform(options: VisualUpdateOptions, host: IVisualHost): BarChartViewModel {
    let colorPalette: IColorPalette = host.colorPalette; // host: IVisualHost
    for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
        barChartDataPoints.push({
            category: category.values[i],
            value: dataValue.values[i],
            color: colorPalette.getColor(category.values[i]).value,
        });
    }
}
```

Käytä sitten tietoja kohteesta `dataPoints` [d3](https://d3js.org/)-valinnassa `barSelection` `update`-menetelmässä:

```typescript
// This code is actual for d3 v5
// in d3 v5 for this case we should use merge() after enter() and apply changes on barSelectionMerged
this.barSelection = this.barContainer
    .selectAll('.bar')
    .data(this.barDataPoints);

const barSelectionMerged = this.barSelection
    .enter()
    .append('rect')
    .merge(<any>this.barSelection);

barSelectionMerged.classed('bar', true);

barSelectionMerged
.attr("width", xScale.bandwidth())
.attr("height", d => height - yScale(<number>d.value))
.attr("y", d => yScale(<number>d.value))
.attr("x", d => xScale(d.category))
.style("fill", (dataPoint: BarChartDataPoint) => dataPoint.color)
.style("stroke", (dataPoint: BarChartDataPoint) => dataPoint.strokeColor)
.style("stroke-width", (dataPoint: BarChartDataPoint) => `${dataPoint.strokeWidth}px`);

this.barSelection
    .exit()
    .remove();
```

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja Power BI -visualisoinneista on artikkelissa [Power BI:n visualisointien toiminnot ja ominaisuudet](capabilities.md).

Lisätietoja Power BI -visualisointien kehittämisestä on kohdassa [Power BI -visualisointien virheenkorjaus](visuals-how-to-debug.md) ja [Power BI -visualisointien vianmääritys](power-bi-custom-visuals-troubleshoot.md).
