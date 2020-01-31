---
title: Johdanto Power BI -visualisoinnin muotoilun apuohjelmien käyttöön
description: Tässä artikkelissa kuvataan, miten voit käyttää muotoilun apuohjelmia Power BI -visualisoinnin arvojen muotoiluun ja lokalisointiin
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 425a872c395df1b69297ae799e7059de687f8fb0
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700336"
---
# <a name="formatting-utils"></a>Muotoilun apuohjelmat

Muotoilun apuohjelmat sisältävät luokkia, liittymiä ja menetelmiä arvojen muotoilemista varten. Se sisältää myös laajennusmenetelmiä merkkijonojen käsittelemiseen ja tekstin koon mittaamiseen SVG/HTML-tiedostossa.

## <a name="text-measurement-service"></a>Tekstin mittauspalvelu

Moduuli sisältää seuraavat funktiot ja liittymät:

### <a name="textproperties-interface"></a>TextProperties-liittymä

Tämä liittymä kuvaa tekstin yleisiä ominaisuuksia.

```typescript
interface TextProperties {
    text?: string;
    fontFamily: string;
    fontSize: string;
    fontWeight?: string;
    fontStyle?: string;
    fontVariant?: string;
    whiteSpace?: string;
}
```

### <a name="measuresvgtextwidth"></a>measureSvgTextWidth

Tämä funktio mittaa tekstin leveyttä annetuilla SVG-tekstiominaisuuksilla.

```typescript
function measureSvgTextWidth(textProperties: TextProperties, text?: string): number;
```

Esimerkki `measureSvgTextWidth`-funktion käytöstä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextWidth(textProperties);

// returns: 194.71875
```

### <a name="measuresvgtextrect"></a>measureSvgTextRect

Tämä funktio palauttaa rect-arvon annetuilla SVG-tekstiominaisuuksilla.

```typescript
function measureSvgTextRect(textProperties: TextProperties, text?: string): SVGRect;
```

Esimerkki `measureSvgTextRect`-funktion käytöstä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextRect(textProperties);

// returns: { x: 0, y: -22, width: 194.71875, height: 27 }
```

### <a name="measuresvgtextheight"></a>measureSvgTextHeight

Tämä funktio mittaa tekstin korkeutta annetuilla SVG-tekstiominaisuuksilla.

```typescript
function measureSvgTextHeight(textProperties: TextProperties, text?: string): number;
```

Esimerkki `measureSvgTextHeight`-funktion käytöstä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...


let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextHeight(textProperties);

// returns: 27
```

### <a name="estimatesvgtextbaselinedelta"></a>estimateSvgTextBaselineDelta

Tämä funktio palauttaa perusarvon annetuilla SVG-tekstiominaisuuksilla.

```typescript
function estimateSvgTextBaselineDelta(textProperties: TextProperties): number;
```

Esimerkki:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.estimateSvgTextBaselineDelta(textProperties);

// returns: 5
```

### <a name="estimatesvgtextheight"></a>estimateSvgTextHeight

Tämä funktio arvioi tekstin korkeutta annetuilla SVG-tekstiominaisuuksilla.

```typescript
function estimateSvgTextHeight(textProperties: TextProperties, tightFightForNumeric?: boolean): number;
```

Esimerkki `estimateSvgTextHeight`-funktion käytöstä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.estimateSvgTextHeight(textProperties);

// returns: 27
```

Voit tutustua mukautetun visualisoinnin esimerkkikoodiin [täällä](https://github.com/Microsoft/powerbi-visuals-sankey/blob/4d544ea145b4e15006083a3610dfead3da5f61a4/src/visual.ts#L372).

### <a name="measuresvgtextelementwidth"></a>measureSvgTextElementWidth

Tämä funktio mittaa svgElement-elementin leveyden.

```typescript
function measureSvgTextElementWidth(svgElement: SVGTextElement): number;
```

Esimerkki measureSvgTextElementWidth-funktion käyttämisestä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: D3.Selection = d3.select("body").append("svg");

svg.append("text")
    .text("Microsoft PowerBI")
    .attr({
        "x": 25,
        "y": 25
    })
    .style({
        "font-family": "sans-serif",
        "font-size": "24px"
    });

let textElement: D3.Selection = svg.select("text");

textMeasurementService.measureSvgTextElementWidth(textElement.node());

// returns: 194.71875
```

### <a name="getmeasurementproperties"></a>getMeasurementProperties

Tämä funktio hakee annetun DOM-elementin tekstin mittaominaisuudet.

```typescript
function getMeasurementProperties(element: Element): TextProperties;
```

Esimerkki `getMeasurementProperties`-funktion käytöstä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let element: JQuery = $(document.createElement("div"));

element.text("Microsoft PowerBI");

element.css({
    "width": 500,
    "height": 500,
    "font-family": "sans-serif",
    "font-size": "32em",
    "font-weight": "bold",
    "font-style": "italic",
    "white-space": "nowrap"
});

textMeasurementService.getMeasurementProperties(element.get(0));

/* returns: {
    fontFamily:"sans-serif",
    fontSize: "32em",
    fontStyle: "italic",
    fontVariant: "",
    fontWeight: "bold",
    text: "Microsoft PowerBI",
    whiteSpace: "nowrap"
}*/
```

### <a name="getsvgmeasurementproperties"></a>getSvgMeasurementProperties

Tämä funktio hakee annetun SVG-elementin tekstin mittaominaisuudet.

```typescript
function getSvgMeasurementProperties(svgElement: SVGTextElement): TextProperties;
```

Esimerkki `getSvgMeasurementProperties`-funktion käytöstä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: D3.Selection = d3.select("body").append("svg");

let textElement: D3.Selection = svg.append("text")
    .text("Microsoft PowerBI")
    .attr({
        "x": 25,
        "y": 25
    })
    .style({
        "font-family": "sans-serif",
        "font-size": "24px"
    });

textMeasurementService.getSvgMeasurementProperties(textElement.node());

/* returns: {
    "text": "Microsoft PowerBI",
    "fontFamily": "sans-serif",
    "fontSize": "24px",
    "fontWeight": "normal",
    "fontStyle": "normal",
    "fontVariant": "normal",
    "whiteSpace": "nowrap"
}*/
```

## <a name="getdivelementwidth"></a>getDivElementWidth

Tämä funktio palauttaa div-elementin leveyden.

```typescript
function getDivElementWidth(element: JQuery): string;
```

Esimerkki `getDivElementWidth`-funktion käytöstä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: Element = d3.select("body")
    .append("div")
    .style({
        "width": "150px",
        "height": "150px"
    })
    .node();

textMeasurementService.getDivElementWidth(svg)

// returns: 150px
```

### <a name="gettailoredtextordefault"></a>getTailoredTextOrDefault

Vertaa otsikoiden tekstin kokoa käytettävissä olevaan kokoon ja näyttää kolme pistettä, jos käytettävissä oleva koko on pienempi.

```typescript
function getTailoredTextOrDefault(textProperties: TextProperties, maxWidth: number): string;
```

Esimerkki `getTailoredTextOrDefault`-funktion käytöstä:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI!",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.getTailoredTextOrDefault(textProperties, 100);

// returns: Micros...
```

## <a name="string-extensions"></a>Merkkijonotunnisteet

Moduuli sisältää seuraavat funktiot:

## <a name="endswith"></a>endsWith

Tämä funktio tarkistaa päättyykö merkkijono alimerkkijonoon.

```typescript
function endsWith(str: string, suffix: string): boolean;
```

Esimerkki `endsWith`-funktion käytöstä:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.endsWith("Power BI", "BI");

// returns: true
```

### <a name="equalignorecase"></a>equalIgnoreCase

Tämä funktio vertaa merkkijonoja huomioimatta kirjainkokoa.

```typescript
function equalIgnoreCase(a: string, b: string): boolean;
```

Esimerkki `equalIgnoreCase`-funktion käytöstä:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.equalIgnoreCase("Power BI", "power bi");

// returns: true
```

### <a name="startswith"></a>startsWith

Tämä funktio tarkistaa alkaako merkkijono alimerkkijonolla.

```typescript
function startsWith(a: string, b: string): boolean;
```

Esimerkki `startsWith`-funktion käytöstä:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.startsWith("Power BI", "Power");

// returns: true
```

### <a name="contains"></a>sisältää

Tämä funktio tarkistaa sisältääkö merkkijono määritetyn alimerkkijonon.

```typescript
function contains(source: string, substring: string): boolean;
```

Esimerkki `contains`-menetelmän käytöstä:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.contains("Microsoft Power BI Visuals", "Power BI");

// returns: true
```

### <a name="isnullorempty"></a>isNullOrEmpty

Tarkistaa, onko merkkijono tyhjäarvoinen, määrittämätön tai tyhjä.

```typescript
function isNullOrEmpty(value: string): boolean;
```

Esimerkki `isNullOrEmpty`-menetelmän käytöstä:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.isNullOrEmpty(null);

// returns: true
```

## <a name="value-formatter"></a>Arvon muotoilu

Moduuli sisältää seuraavat funktiot, liittymät ja luokat:

## <a name="ivalueformatter"></a>IValueFormatter

Tämä liittymä kuvaa muotoilumoduulin julkisia menetelmiä ja ominaisuuksia.

```typescript
interface IValueFormatter {
    format(value: any): string;
    displayUnit?: DisplayUnit;
    options?: ValueFormatterOptions;
}
```

### <a name="ivalueformatterformat"></a>IValueFormatter.format

Tämä menetelmä muotoilee annetun arvon.

```typescript
function format(value: any, format?: string, allowFormatBeautification?: boolean): string;
```

Esimerkkejä `IValueFormatter.format`-menetelmän käytöstä:

#### <a name="the-thousand-formats"></a>Tuhat-muotoilut

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1001 });

iValueFormatter.format(5678);

// returns: "5.68K"
```

#### <a name="the-million-formats"></a>Miljoona-muotoilut

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e6 });

iValueFormatter.format(1234567890);

// returns: "1234.57M"
```

#### <a name="the-billion-formats"></a>Miljardi-muotoilut

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e9 });

iValueFormatter.format(1234567891236);

// returns: 1234.57bn
```

#### <a name="the-trillion-format"></a>Biljoona-muotoilu

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e12 });

iValueFormatter.format(1234567891236);

// returns: 1.23T
```

#### <a name="the-exponent-format"></a>Eksponentti-muotoilu

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ format: "E" });

iValueFormatter.format(1234567891236);

// returns: 1.234568E+012
```

### <a name="the-culture-selector"></a>Kulttuurivalitsin

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let valueFormatterUK = valueFormatter.create({ cultureSelector: "en-GB" });

valueFormatterUK.format(new Date(2007, 2, 3, 17, 42, 42));

// returns: 03/03/2007 17:42:42

let valueFormatterUSA = valueFormatter.create({ cultureSelector: "en-US" });

valueFormatterUSA.format(new Date(2007, 2, 3, 17, 42, 42));

// returns: 3/3/2007 5:42:42 PM
```

#### <a name="the-percentage-format"></a>Prosenttilukumuotoilu

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ format: "0.00 %;-0.00 %;0.00 %" });

iValueFormatter.format(0.54);

// returns: 54.00 %
```

#### <a name="the-dates-format"></a>Päivämäärien muotoilu

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let date = new Date(2016, 10, 28, 15, 36, 0),
    iValueFormatter = valueFormatter.create({});

iValueFormatter.format(date);

// returns: 11/28/2016 3:36:00 PM
```

#### <a name="the-boolean-format"></a>Totuusarvon muotoilu

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({});

iValueFormatter.format(true);

// returns: True
```

#### <a name="the-customized-precision"></a>Mukautettu tarkkuus

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 0, precision: 3 });

iValueFormatter.format(3.141592653589793);

// returns: 3.142
```

Voit tutustua mukautetun visualisoinnin esimerkkikoodiin [täällä](https://github.com/Microsoft/powerbi-visuals-sankey/blob/4d544ea145b4e15006083a3610dfead3da5f61a4/src/visual.ts#L359).

## <a name="valueformatteroptions"></a>ValueFormatterOptions

Tämä liittymä kuvaa IValueFormatter-liittymän `options`-vaihtoehtoja ja create-funktion vaihtoehtoja.

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
import ValueFormatterOptions = valueFormatter.ValueFormatterOptions;

interface ValueFormatterOptions {
    /** The format string to use. */
    format?: string;
    /** The data value. */
    value?: any;
    /** The data value. */
    value2?: any;
    /** The number of ticks. */
    tickCount?: any;
    /** The display unit system to use */
    displayUnitSystemType?: DisplayUnitSystemType;
    /** True if we are formatting single values in isolation (e.g. card), as opposed to multiple values with a common base (e.g. chart axes) */
    formatSingleValues?: boolean;
    /** True if we want to trim off unnecessary zeroes after the decimal and remove a space before the % symbol */
    allowFormatBeautification?: boolean;
    /** Specifies the maximum number of decimal places to show*/
    precision?: number;
    /** Detect axis precision based on value */
    detectAxisPrecision?: boolean;
    /** Specifies the column type of the data value */
    columnType?: ValueTypeDescriptor;
    /** Specifies the culture */
    cultureSelector?: string;
}
```

## <a name="create"></a>luo

Tämä menetelmä luo IValueFormatter-esiintymän.

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
import create = valueFormatter.create;

function create(options: ValueFormatterOptions): IValueFormatter;
```

### <a name="example-of-using-create"></a>Esimerkki create-funktion käytöstä

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

valueFormatter.create({});

// returns: an instance of IValueFormatter.
```

## <a name="next-steps"></a>Seuraavat vaiheet

[Lokalisointien lisääminen mukautettuun Power BI -visualisointiin](localization.md)  
