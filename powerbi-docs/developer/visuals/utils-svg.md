---
title: Johdanto Power BI -visualisoinnin SVG-apuohjelmien käyttöön
description: Tässä artikkelissa kuvataan, miten SVG-apuohjelmien avulla voit yksinkertaistaa SVG-käsittelytoimintoja Power BI:n mukautetuissa visualisoinneissa
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 612c253e53cdaec5819387548354595c8bd94fa0
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819303"
---
# <a name="svg-utils"></a>SVG-apuohjelmat

SVGUtils on joukko toimintoja ja luokkia, jotka yksinkertaistavat SVG-käsittelyä Power BI:n mukautetuissa visualisoinneissa

## <a name="installation"></a>Asennus

Paketin asentamista varten tulee suorittaa seuraava komento hakemistossa, joka sisältää nykyisen visualisoinnin:

```bash
npm install powerbi-visuals-utils-svgutils --save
```

## <a name="cssconstants"></a>CssConstants

`CssConstants`-moduuli tarjoaa erikoistoiminnot ja liittymän luokan valitsimien kanssa työskentelyä varten.

`powerbi.extensibility.utils.svg.CssConstants`-moduuli sisältää seuraavan toiminnon ja liittymän:

## <a name="classandselector"></a>ClassAndSelector

Tämä liittymä kuvaa luokan valitsimen yleisiä ominaisuuksia.

```typescript
interface ClassAndSelector {
  class: string;
  selector: string;
}
```

### <a name="createclassandselector"></a>createClassAndSelector

Tämä funktio luo ClassAndSelector-esiintymän annetulla luokan nimellä.

```typescript
function createClassAndSelector(className: string): ClassAndSelector;
```

Esimerkki:

```typescript
import { CssConstants } from "powerbi-visuals-utils-svgutils";
import createClassAndSelector = CssConstants.createClassAndSelector;
import ClassAndSelector = CssConstants.ClassAndSelector;

let divSelector: ClassAndSelector = createClassAndSelector("sample-block");

divSelector.selector === ".sample-block"; // returns: true
divSelector.class === "sample-block"; // returns: true
```

## <a name="manipulation"></a>manipulation

`manipulation` sisältää joitakin erikoisfunktioita, joilla luodaan merkkijonoja SVG-muunnosominaisuudessa käyttämistä varten.

Moduuli sisältää seuraavat funktiot:

### <a name="translate"></a>translate

Tämä toiminto luo käännösmerkkijonon käytettäväksi SVG-muunnosominaisuuden kanssa.

```typescript
function translate(x: number, y: number): string;
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translate(100, 100);

// returns: translate(100,100)
```

### <a name="translatexwithpixels"></a>translateXWithPixels

Tämä toiminto luo translateX-merkkijonon käytettäväksi SVG-muunnosominaisuuden kanssa.

```typescript
function translateXWithPixels(x: number): string;
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateXWithPixels(100);

// returns: translateX(100px)
```

### <a name="translatewithpixels"></a>translateWithPixels

Tämä toiminto luo käännösmerkkijonon käytettäväksi SVG-muunnosominaisuuden kanssa.

```typescript
function translateWithPixels(x: number, y: number): string;
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateWithPixels(100, 100);

// returns: translate(100px,100px)
```

### <a name="translateandrotate"></a>translateAndRotate

Tämä toiminto luo käännös- ja kiertomerkkijonon käytettäväksi SVG-muunnosominaisuuden kanssa.

```typescript
function translateAndRotate(
  x: number,
  y: number,
  px: number,
  py: number,
  angle: number
): string;
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateAndRotate(100, 100, 50, 50, 35);

// returns: translate(100,100) rotate(35,50,50)
```

### <a name="scale"></a>scale

Tämä toiminto luo skaalausmerkkijonon käytettäväksi CSS-muunnosominaisuudessa.

```typescript
function scale(scale: number): string;
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.scale(50);

// returns: scale(50)
```

### <a name="transformorigin"></a>transformOrigin

Tämä toiminto luo transform-origin-merkkijonon käytettäväksi CSS:n muunna alkuperä -ominaisuudessa.

```typescript
function transformOrigin(xOffset: string, yOffset: string): string;
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.transformOrigin(5, 5);

// returns: 5 5
```

### <a name="flushalld3transitions"></a>flushAllD3Transitions

Tämä ominaisuus pakottaa kaikki D3-siirtymät valmistumaan.

```typescript
function flushAllD3Transitions(): void;
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.flushAllD3Transitions();

// forces every transition of D3 to complete
```

### <a name="parsetranslatetransform"></a>parseTranslateTransform

Tämä toiminto jäsentää muunnosmerkkijonon arvolla "translate(x,y)".

```typescript
function parseTranslateTransform(input: string): { x: string; y: string };
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.parseTranslateTransform("translate(100px,100px)");

// returns: { "x":"100px", "y":"100px" }
```

### <a name="createarrow"></a>createArrow

Tämä funktio luo nuolen.

```typescript
function createArrow(
  width: number,
  height: number,
  rotate: number
): { path: string; transform: string };
```

Esimerkki:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.createArrow(10, 20, 5);

/* returns: {
    "path": "M0 0L0 20L10 10 Z",
    "transform": "rotate(5 5 10)"
}*/
```

## <a name="rect"></a>Rect

`Rect`-moduuli tarjoaa erikoisfunktioita suorakulmioiden käsittelyä varten.

Moduuli sisältää seuraavat funktiot:

### <a name="getoffset"></a>getOffset

Tämä funktio palauttaa suorakulmion poikkeaman.

```typescript
function getOffset(rect: IRect): IPoint;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getOffset({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    x: 25,
    y: 25
}*/
```

### <a name="getsize"></a>getSize

Tämä funktio palauttaa suorakulmion koon.

```typescript
function getSize(rect: IRect): ISize;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getSize({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    width: 100,
    height: 100
}*/
```

### <a name="setsize"></a>setSize

Tämä funktio muuttaa suorakulmion kokoa.

```typescript
function setSize(rect: IRect, value: ISize): void;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

let rectangle = { left: 25, top: 25, width: 100, height: 100 };

Rect.setSize(rectangle, { width: 250, height: 250 });

// rectangle === { left: 25, top: 25, width: 250, height: 250 }
```

### <a name="right"></a>right

Tämä funktio palauttaa suorakulmion oikean reunan sijainnin.

```typescript
function right(rect: IRect): number;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.right({ left: 25, top: 25, width: 100, height: 100 });

// returns: 125
```

### <a name="bottom"></a>bottom

Tämä funktio palauttaa suorakulmion alareunan sijainnin.

```typescript
function bottom(rect: IRect): number;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottom({ left: 25, top: 25, width: 100, height: 100 });

// returns: 125
```

### <a name="topleft"></a>topLeft

Tämä funktio palauttaa suorakulmion vasemman yläreunan sijainnin.

```typescript
function topLeft(rect: IRect): IPoint;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.topLeft({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 25, y: 25 }
```

### <a name="topright"></a>topRight

Tämä funktio palauttaa suorakulmion oikean yläreunan sijainnin.

```typescript
function topRight(rect: IRect): IPoint;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.topRight({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 125, y: 25 }
```

### <a name="bottomleft"></a>bottomLeft

Tämä funktio palauttaa suorakulmion vasemman alareunan sijainnin.

```typescript
function bottomLeft(rect: IRect): IPoint;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottomLeft({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 25, y: 125 }
```

### <a name="bottomright"></a>bottomRight

Tämä funktio palauttaa suorakulmion oikean alareunan sijainnin.

```typescript
function bottomRight(rect: IRect): IPoint;
```

### <a name="example"></a>Esimerkki

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottomRight({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 125, y: 125 }
```

### <a name="clone"></a>clone

Tämä funktio luo suorakulmiosta kopion.

```typescript
function clone(rect: IRect): IRect;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.clone({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    left: 25, top: 25, width: 100, height: 100}
*/
```

### <a name="tostring"></a>toString

Tämä funktio muuntaa suorakulmion merkkijonoksi.

```typescript
function toString(rect: IRect): string;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.toString({ left: 25, top: 25, width: 100, height: 100 });

// returns: {left:25, top:25, width:100, height:100}
```

### <a name="offset"></a>offset

Tämä funktio käyttää suorakulmiossa annettua siirtymää.

```typescript
function offset(rect: IRect, offsetX: number, offsetY: number): IRect;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.offset({ left: 25, top: 25, width: 100, height: 100 }, 50, 50);

/* returns: {
    left: 75,
    top: 75,
    width: 100,
    height: 100
}*/
```

### <a name="add"></a>add

Tämä funktio lisää ensimmäisen suorakulmion toiseen suorakulmioon.

```typescript
function add(rect: IRect, rect2: IRect): IRect;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.add(
  { left: 25, top: 25, width: 100, height: 100 },
  { left: 50, top: 50, width: 75, height: 75 }
);

/* returns: {
    left: 75,
    top: 75,
    height: 175,
    width: 175
}*/
```

### <a name="getclosestpoint"></a>getClosestPoint

Tämä funktio palauttaa suorakulmion lähimmän pisteen määritettyyn pisteeseen verrattuna.

```typescript
function getClosestPoint(rect: IRect, x: number, y: number): IPoint;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getClosestPoint({ left: 0, top: 0, width: 100, height: 100 }, 50, 50);

/* returns: {
    x: 50,
    y: 50
}*/
```

### <a name="equal"></a>equal

Tämä funktio vertaa suorakulmioita ja palauttaa arvon tosi, jos ne ovat samat.

```typescript
function equal(rect1: IRect, rect2: IRect): boolean;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.equal(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 50, top: 50, width: 100, height: 100 }
);

// returns: false
```

### <a name="equalwithprecision"></a>equalWithPrecision

Tämä funktio vertaa suorakulmioita tarkastelemalla arvojen tarkkuutta.

```typescript
function equalWithPrecision(rect1: IRect, rect2: IRect): boolean;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.equalWithPrecision(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 50, top: 50, width: 100, height: 100 }
);

// returns: false
```

### <a name="isempty"></a>isEmpty

Tämä funktio tarkistaa, onko suorakulmio tyhjä.

```typescript
function isEmpty(rect: IRect): boolean;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.isEmpty({ left: 0, top: 0, width: 0, height: 0 });

// returns: true
```

### <a name="containspoint"></a>containsPoint

Tämä funktio tarkistaa, onko suorakulmiossa piste.

```typescript
function containsPoint(rect: IRect, point: IPoint): boolean;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.containsPoint(
  { left: 0, top: 0, width: 100, height: 100 },
  { x: 50, y: 50 }
);

// returns: true
```

### <a name="isintersecting"></a>isIntersecting

Tämä funktio tarkistaa, leikkaavatko suorakulmiot toisensa.

```typescript
function isIntersecting(rect1: IRect, rect2: IRect): boolean;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.isIntersecting(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 50 }
);

// returns: true
```

### <a name="intersect"></a>intersect

Tämä funktio palauttaa suorakulmioiden leikkauskohdan.

```typescript
function intersect(rect1: IRect, rect2: IRect): IRect;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.intersect(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 50 }
);

/* returns: {
    left: 0,
    top: 0,
    width: 50,
    height: 50
}*/
```

### <a name="combine"></a>combine

Tämä funktio yhdistää suorakulmiot.

```typescript
function combine(rect1: IRect, rect2: IRect): IRect;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.combine(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 120 }
);

/* returns: {
    left: 0,
    top: 0,
    width: 100,
    height: 120
}*/
```

### <a name="getcentroid"></a>getCentroid

Tämä funktio palauttaa suorakulmion keskipisteen.

```typescript
function getCentroid(rect: IRect): IPoint;
```

Esimerkki:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getCentroid({ left: 0, top: 0, width: 100, height: 100 });

/* returns: {
    x: 50,
    y: 50
}*/
```

## <a name="pointer"></a>pointer

`pointer`-moduuli sisältää erikoisfunktion osoittimen sijainnin saamista varten.

Moduuli sisältää seuraavan toiminnon:

### <a name="getcoordinates"></a>getCoordinates

Tämä funktio palauttaa osoittimen sijainnin.

```typescript
function getCoordinates(rootNode: Element, isPointerEvent: boolean): number[];
```

Esimerkki:

```typescript
import { pointer } from "powerbi-visuals-utils-svgutils";

let bodySelection = d3.select("body");

bodySelection
  .append("div")
  .style({
    width: "100px",
    height: "100px",
    "background-color": "green"
  })
  .on("click", () => {
    pointer.getCoordinates(bodySelection.node(), true);
  });

// click element, after that you will get position of the pointer
```
