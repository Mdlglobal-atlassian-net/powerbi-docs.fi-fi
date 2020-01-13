---
title: Johdanto Power BI -visualisoinnin kaavioapuohjelmien käyttöön
description: Tässä artikkelissa kerrotaan, miten voit piirtää akseleita ja selitteitä Power BI -visualisointeihin kaavioapuohjelmien avulla
author: vtkalek
ms.author: asander
manager: asander
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: e67b37f73b3cea097a296f313fbfc8922b7dd945
ms.sourcegitcommit: 4359baa43ca01b179d28ec59f4e61ba8c07ee288
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/20/2019
ms.locfileid: "75308567"
---
# <a name="chart-utils"></a>Kaavioapuohjelmat

Kaavioapuohjelmat ovat liittymiä ja menetelmiä, joiden avulla voi luoda akseleita, arvopisteiden otsikkoja ja selitteitä Power BI -visualisointeihin.

## <a name="installation"></a>Asennus

Paketin asentamista varten tulee suorittaa seuraava komento hakemistossa, joka sisältää nykyisen visualisoinnin:

```bash
npm install powerbi-visuals-utils-chartutils --save
```

## <a name="axis-helper"></a>Akselin aputoiminto

Akselin aputoiminto (apuohjelmien objekti `axis`) tarjoaa funktioita akseleiden käsittelyn helpottamiseen.

Moduuli sisältää seuraavat toiminnot ja liitynnät:

### <a name="getrecommendednumberofticksforxaxis"></a>getRecommendedNumberOfTicksForXAxis

Tämä funktio palauttaa suositellun määrän jakoviivoja kaavion leveyden mukaan.

```typescript
function getRecommendedNumberOfTicksForXAxis(availableWidth: number): number;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...
axis.getRecommendedNumberOfTicksForXAxis(1024);

// returns: 8
```

### <a name="getrecommendednumberofticksforyaxis"></a>getRecommendedNumberOfTicksForYAxis

Tämä funktio palauttaa suositellun määrän jakoviivoja kaavion korkeuden mukaan.

```typescript
function getRecommendedNumberOfTicksForYAxis(availableWidth: number);
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...
axis.getRecommendedNumberOfTicksForYAxis(100);

// returns: 3
```

### <a name="getbestnumberofticks"></a>getBestNumberOfTicks

Noutaa optimaalisen määrän jakoviivoja vähimmäisarvon, enimmäisarvon, mittauksen metatietojen ja jakoviivojen enimmäismäärän perusteella.

```typescript
function getBestNumberOfTicks(
  min: number,
  max: number,
  valuesMetadata: DataViewMetadataColumn[],
  maxTickCount: number,
  isDateTime?: boolean
): number;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...
var dataViewMetadataColumnWithIntegersOnly: powerbi.DataViewMetadataColumn[] = [
  {
    displayName: "col1",
    isMeasure: true,
    type: ValueType.fromDescriptor({ integer: true })
  },
  {
    displayName: "col2",
    isMeasure: true,
    type: ValueType.fromDescriptor({ integer: true })
  }
];
var actual = axis.getBestNumberOfTicks(
  0,
  3,
  dataViewMetadataColumnWithIntegersOnly,
  6
);

// returns: 4
```

### <a name="getticklabelmargins"></a>getTickLabelMargins

Tämä funktio palauttaa jakoviivojen otsikoiden reunukset.

```typescript
function getTickLabelMargins(
  viewport: IViewport,
  yMarginLimit: number,
  textWidthMeasurer: ITextAsSVGMeasurer,
  textHeightMeasurer: ITextAsSVGMeasurer,
  axes: CartesianAxisProperties,
  bottomMarginLimit: number,
  properties: TextProperties,
  scrollbarVisible?: boolean,
  showOnRight?: boolean,
  renderXAxis?: boolean,
  renderY1Axis?: boolean,
  renderY2Axis?: boolean
): TickLabelMargins;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

axis.getTickLabelMargins(
  plotArea,
  marginLimits.left,
  TextMeasurementService.measureSvgTextWidth,
  TextMeasurementService.estimateSvgTextHeight,
  axes,
  marginLimits.bottom,
  textProperties,
  /*scrolling*/ false,
  showY1OnRight,
  renderXAxis,
  renderY1Axis,
  renderY2Axis
);

// returns:  xMax, yLeft, yRight, stackHeigh;
```

### <a name="isordinal"></a>isOrdinal

Tarkistaa, onko merkki jono tyhjä arvo tai määrittämätön tai tyhjä.

```typescript
function isOrdinal(type: ValueTypeDescriptor): boolean;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...
let type = ValueType.fromDescriptor({ misc: { barcode: true } });
axis.isOrdinal(type);

// returns: true
```

### <a name="isdatetime"></a>isDateTime

Tarkistaa, onko arvon tyyppi päivämäärä/aika.

```typescript
function isDateTime(type: ValueTypeDescriptor): boolean;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

axis.isDateTime(ValueType.fromDescriptor({ dateTime: true }));

// returns: true
```

### <a name="getcategorythickness"></a>getCategoryThickness

Noutaa luokan todellisen paksuuden käyttämällä D3-asteikkoa.

```typescript
function getCategoryThickness(scale: any): number;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

let range = [0, 100];
let domain = [0, 10];
let scale = d3.scale
  .linear()
  .domain(domain)
  .range(range);
let actualThickness = axis.getCategoryThickness(scale);
```

### <a name="invertordinalscale"></a>invertOrdinalScale

Tämä funktio kääntää järjestyslukujen asteikon. Jos x < scale.range()[0], scale.domain()[0] palautetaan.
Muussa tapauksessa palautetaan suurin kohde kohdassa scale.domain() eli <= x.

```typescript
function invertOrdinalScale(scale: d3.scale.Ordinal<any, any>, x: number);
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

let domain: number[] = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9],
  pixelSpan: number = 100,
  ordinalScale: d3.scale.ordinal = axis.createOrdinalScale(
    pixelSpan,
    domain,
    0.4
  );

axis.invertOrdinalScale(ordinalScale, 49);

// returns: 4
```

### <a name="findclosestxaxisindex"></a>findClosestXAxisIndex

Tämä funktio etsii ja palauttaa lähimmän x-akselin indeksin.

```typescript
function findClosestXAxisIndex(
  categoryValue: number,
  categoryAxisValues: AxisHelperCategoryDataPoint[]
): number;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

/**
 * Finds the index of the category of the given x coordinate given.
 * pointX is in non-scaled screen-space, and offsetX is in render-space.
 * offsetX does not need any scaling adjustment.
 * @param {number} pointX The mouse coordinate in screen-space, without scaling applied
 * @param {number} offsetX Any left offset in d3.scale render-space
 * @return {number}
 */
private findIndex(pointX: number, offsetX?: number): number {
    // we are using mouse coordinates that do not know about any potential CSS transform scale
    let xScale = this.scaleDetector.getScale().x;
    if (!Double.equalWithPrecision(xScale, 1.0, 0.00001)) {
        pointX = pointX / xScale;
    }
    if (offsetX) {
        pointX += offsetX;
    }

    let index = axis.invertScale(this.xAxisProperties.scale, pointX);
    if (this.data.isScalar) {
        // When we have scalar data the inverted scale produces a category value, so we need to search for the closest index.
        index = axis.findClosestXAxisIndex(index, this.data.categoryData);
    }

    return index;
}
```

### <a name="diffscaled"></a>diffScaled

Tämä funktio laskee ja palauttaa asteikon arvojen erotuksen.

```typescript
function diffScaled(
  scale: d3.scale.Linear<any, any>,
  value1: any,
  value2: any
): number;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

var scale: d3.scale.Linear<number, number>,
    range = [0, 999],
    domain = [0, 1, 2, 3, 4, 5, 6, 7, 8, 999];

scale = d3.scale.linear()
    .range(range)
    .domain(domain);

return axis.diffScaled(scale, 0, 0));

// returns: 0
```

### <a name="createdomain"></a>createDomain

Tämä funktio luo akselin arvojen toimialueen.

```typescript
function createDomain(
  data: any[],
  axisType: ValueTypeDescriptor,
  isScalar: boolean,
  forcedScalarDomain: any[],
  ensureDomain?: NumberRange
): number[];
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

var cartesianSeries = [
  {
    data: [
      { categoryValue: 7, value: 11, categoryIndex: 0, seriesIndex: 0 },
      {
        categoryValue: 9,
        value: 9,
        categoryIndex: 1,
        seriesIndex: 0
      },
      {
        categoryValue: 15,
        value: 6,
        categoryIndex: 2,
        seriesIndex: 0
      },
      { categoryValue: 22, value: 7, categoryIndex: 3, seriesIndex: 0 }
    ]
  }
];

var domain = axis.createDomain(
  cartesianSeries,
  ValueType.fromDescriptor({ text: true }),
  false,
  []
);

// returns: [0, 1, 2, 3]
```

### <a name="getcategoryvaluetype"></a>getCategoryValueType

Tämä funktio hakee luokkasarakkeen kohdan `ValueType`. Oletusarvona on `Text`, jos tyyppiä ei ole.

```typescript
function getCategoryValueType(
  data: any[],
  axisType: ValueTypeDescriptor,
  isScalar: boolean,
  forcedScalarDomain: any[],
  ensureDomain?: NumberRange
): number[];
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

var cartesianSeries = [
  {
    data: [
      { categoryValue: 7, value: 11, categoryIndex: 0, seriesIndex: 0 },
      {
        categoryValue: 9,
        value: 9,
        categoryIndex: 1,
        seriesIndex: 0
      },
      {
        categoryValue: 15,
        value: 6,
        categoryIndex: 2,
        seriesIndex: 0
      },
      { categoryValue: 22, value: 7, categoryIndex: 3, seriesIndex: 0 }
    ]
  }
];

axis.getCategoryValueType(
  cartesianSeries,
  ValueType.fromDescriptor({ text: true }),
  false,
  []
);

// returns: [0, 1, 2, 3]
```

### <a name="createaxis"></a>createAxis

Tämä funktio luo D3-akselin asteikko mukaan lukien. Se voi olla pysty- tai vaakasuuntainen ja tyypiltään joko päivämäärä/aika, numeerinen tai teksti.

```typescript
function createAxis(options: CreateAxisOptions): IAxisProperties;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
// ...

var dataPercent = [0.0, 0.33, 0.49];

var formatStringProp: powerbi.DataViewObjectPropertyIdentifier = {
  objectName: "general",
  propertyName: "formatString"
};
let metaDataColumnPercent: powerbi.DataViewMetadataColumn = {
  displayName: "Column",
  type: ValueType.fromDescriptor({ numeric: true }),
  objects: {
    general: {
      formatString: "0 %"
    }
  }
};

var os = axis.createAxis({
  pixelSpan: 100,
  dataDomain: [dataPercent[0], dataPercent[2]],
  metaDataColumn: metaDataColumnPercent,
  formatString: valueFormatter.getFormatString(
    metaDataColumnPercent,
    formatStringProp
  ),
  outerPadding: 0.5,
  isScalar: true,
  isVertical: true
});
```

### <a name="applycustomizeddomain"></a>applyCustomizedDomain

Tämä funktio määrittää mukautetun toimialueen, mutta ei muutu, jos mitään ei ole määritetty.

```typescript
function applyCustomizedDomain(customizedDomain, forcedDomain: any[]): any[];
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

let customizedDomain = [undefined, 20],
  existingDomain = [0, 10];

axis.applyCustomizedDomain(customizedDomain, existingDomain);

// returns: {0:0, 1:20}
```

### <a name="combinedomain"></a>combineDomain

Tämä funktio yhdistää pakotetun toimialueen ja todellisen toimialueen, jos jokin arvoista on määritetty.
forcedDomain on ensisijainen. Laajentaa toimialueen, jos jokin viitepiste edellyttää sitä.

```typescript
function combineDomain(
  forcedDomain: any[],
  domain: any[],
  ensureDomain?: NumberRange
): any[];
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

let forcedYDomain = this.valueAxisProperties
  ? [this.valueAxisProperties["secStart"], this.valueAxisProperties["secEnd"]]
  : null;

let xDomain = [minX, maxX];

axis.combineDomain(forcedYDomain, xDomain, ensureXDomain);
```

### <a name="poweroften"></a>powerOfTen

Tämä funktio ilmaisee, onko luku kerrottu 10:llä.

```typescript
function powerOfTen(d: any): boolean;
```

Esimerkki:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

axis.powerOfTen(10);

// returns: true
```

## <a name="datalabelmanager"></a>DataLabelManager

`DataLabelManager` auttaa luomaan ja ylläpitämään otsikoita. Se järjestää otsikkoelementit käyttämällä ankkuripistettä tai suorakulmiota. Ristiriidat voidaan tunnistaa automaattisesti elementtien uudelleensijoittamiseksi tai piilottamiseksi.

Luokka `DataLabelManager` tarjoaa seuraavat menetelmät:

## <a name="hidecollidedlabels"></a>hideCollidedLabels

Tässä menetelmässä otsikoiden sijainti ja näkyvyys pohjalla järjestetään otsikoiden koon ja päällekkäisyyden mukaan.

```typescript
function hideCollidedLabels(
  viewport: IViewport,
  data: any[],
  layout: any,
  addTransform: boolean = false
): LabelEnabledDataPoint[];
```

Esimerkki:

```typescript
let dataLabelManager = new DataLabelManager();
let filteredData = dataLabelManager.hideCollidedLabels(
  this.viewport,
  values,
  labelLayout,
  true
);
```

## <a name="isvalid"></a>IsValid

Tämä staattinen menetelmä tarkistaa, onko annettu suorakulmio kelvollinen (onko sillä positiivinen leveys ja korkeus).

```typescript
function isValid(rect: IRect): boolean;
```

Esimerkki:

```typescript
let rectangle = {
  left: 150,
  top: 130,
  width: 120,
  height: 110
};

DataLabelManager.isValid(rectangle);

// returns: true
```

## <a name="datalabelutils"></a>DataLabelUtils

`DataLabelUtils` tarjoaa apuohjelmat arvopisteiden otsikoiden käsittelyyn.

Moduuli sisältää seuraavat toiminnot ja liitynnät ja luokat:

### <a name="getlabelprecision"></a>getLabelPrecision

Tämä funktio laskee annetun muodon tarkkuuden.

```typescript
function getLabelPrecision(precision: number, format: string): number;
```

### <a name="getlabelformattedtext"></a>getLabelFormattedText

Tämä funktio palauttaa annetun muodon tarkkuuden.

```typescript
function getLabelFormattedText(options: LabelFormattedTextOptions): string;
```

Esimerkki:

```typescript
import { dataLabelUtils } from "powerbi-visuals-utils-chartutils";
// ...

let options: LabelFormattedTextOptions = {
  text: "some text",
  fontFamily: "sans",
  fontSize: "15",
  fontWeight: "normal"
};

dataLabelUtils.getLabelFormattedText(options);
```

### <a name="enumeratedatalabels"></a>enumerateDataLabels

Tämä funktio palauttaa arvon VisualObjectInstance arvopisteiden otsikoille.

```typescript
function enumerateDataLabels(
  options: VisualDataLabelsSettingsOptions
): VisualObjectInstance;
```

### <a name="enumeratecategorylabels"></a>enumerateCategoryLabels

Tämä funktio lisää arvon VisualObjectInstance luokan arvopisteiden otsikoille objektien luetteloinniksi.

```typescript
function enumerateCategoryLabels(
  enumeration: VisualObjectInstanceEnumerationObject,
  dataLabelsSettings: VisualDataLabelsSettings,
  withFill: boolean,
  isShowCategory: boolean = false,
  fontSize?: number
): void;
```

### <a name="createcolumnformattercachemanager"></a>createColumnFormatterCacheManager

Tämä funktio palauttaa välimuistin hallinnan, jonka kautta pääsee nopeasti muotoiltuihin otsikoihin

```typescript
function createColumnFormatterCacheManager(): IColumnFormatterCacheManager;
```

Esimerkki:

```typescript
import { dataLabelUtils } from "powerbi-visuals-utils-chartutils";
// ...

let value: number = 200000;

labelSettings.displayUnits = 1000000;
labelSettings.precision = 1;

let formattersCache = DataLabelUtils.createColumnFormatterCacheManager();
let formatter = formattersCache.getOrCreate(null, labelSettings);
let formattedValue = formatter.format(value);

// formattedValue == "0.2M"
```

## <a name="legend-service"></a>Selitepalvelu

`Legend`palvelu tarjoaa apuliittymiä mukautettujen visualisointien PBI-selitteiden luomiseen ja hallintaan

Moduuli sisältää seuraavat toiminnot ja liitynnät:

### <a name="createlegend"></a>createLegend

Tämä apufunktio yksinkertaistaa Power BI:n mukautettujen visualisointien selitteiden luomista.

```typescript
function createLegend(
  legendParentElement: HTMLElement, // top visual element, container in which legend will be created
  interactive: boolean, // indicates that legend should be interactive
  interactivityService: IInteractivityService, // reference to IInteractivityService interface which need to create legend click events
  isScrollable: boolean = false, // indicates that legend could be scrollable or not
  legendPosition: LegendPosition = LegendPosition.Top // Position of the legend inside of legendParentElement container
): ILegend;
```

Esimerkki:

```typescript
public constructor(options: VisualConstructorOptions) {
    this.visualInitOptions = options;
    this.layers = [];

    var element = this.element = options.element;
    var viewport = this.currentViewport = options.viewport;
    var hostServices = options.host;

    //... some other init calls

    if (this.behavior) {
        this.interactivityService = createInteractivityService(hostServices);
    }
    this.legend = createLegend(
        element,
        options.interactivity && options.interactivity.isInteractiveLegend,
        this.interactivityService,
        true);
}
```

### <a name="ilegend"></a>ILegend

Tämä liittymä toteuttaa kaikki selitteen luonnissa tarvittavat menetelmät

```typescript
export interface ILegend {
  getMargins(): IViewport;
  isVisible(): boolean;
  changeOrientation(orientation: LegendPosition): void; // processing legend orientation
  getOrientation(): LegendPosition; // get information about current legend orientation
  drawLegend(data: LegendData, viewport: IViewport); // all legend rendering code is placing here
  /**
   * Reset the legend by clearing it
   */
  reset(): void;
}
```

### <a name="drawlegend"></a>drawLegend

Tämä ominaisuus mittaa tekstin korkeutta annetuilla SVG-tekstin ominaisuuksilla.

```typescript
function drawLegend(data: LegendData, viewport: IViewport): void;
```

Esimerkki:

```typescript
private renderLegend(): void {
    if (!this.isInteractive) {
        let legendObjectProperties = this.data.legendObjectProperties;
        if (legendObjectProperties) {
            let legendData = this.data.legendData;
            LegendData.update(legendData, legendObjectProperties);
            let position = <string>legendObjectProperties[legendProps.position];
            if (position)
                this.legend.changeOrientation(LegendPosition[position]);

            this.legend.drawLegend(legendData, this.parentViewport);
        } else {
            this.legend.changeOrientation(LegendPosition.Top);
            this.legend.drawLegend({ dataPoints: [] }, this.parentViewport);
        }
    }
}
```

## <a name="next-steps"></a>Seuraavat vaiheet

- [Lue, miten voit lisätä valintoja Power BI:n visualisointeihin InterActivityUtilsin avulla](utils-interactivity-selections.md)
