---
title: Johdanto Power BI -visualisoinnin tyyppiapuohjelmien käyttöön
description: Tässä artikkelissa kuvataan, miten SVG-apuohjelmien avulla voit laajentaa Power BI:n visualisointien perustyyppejä
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 5a3cfb7ea9c9f398193b45652aa43c6b83c8f70b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79377991"
---
# <a name="type-utils"></a>Tyyppiapuohjelmat

TypeUtils on joukko funktioita ja luokkia, jotka laajentavat Power BI:n visualisointien perustyyppejä.

## <a name="installation"></a>Asennus

Paketin asentamista varten tulee suorittaa seuraava komento hakemistossa, joka sisältää nykyisen mukautetun visualisoinnin:

npm install powerbi-visuals-utils-typeutils --save Tämä komento asentaa paketin ja lisää paketin riippuvuudeksi omaan pakettiisi paketti.json

## <a name="double"></a>Double

`Double` tarjoaa mahdollisuudet käsitellä lukujen tarkkuutta.

Moduuli sisältää seuraavat funktiot:

### <a name="pow10"></a>pow10

Tämä funktio palauttaa potenssin 10.

```typescript
function pow10(exp: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.pow10(25);

// returns: 1e+25
```

### <a name="log10"></a>log10

Tämä funktio palauttaa luvun 10-kantaisen logaritmin.

```typescript
function log10(val: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.log10(25);

// returns: 1
```

## <a name="getprecision"></a>getPrecision

Tämä funktio palauttaa luvun tarkkuutta edustavan potenssin 10.

```typescript
function getPrecision(x: number, decimalDigits?: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.getPrecision(562344, 6);

// returns: 0.1
```

### <a name="equalwithprecision"></a>equalWithPrecision

Tämä funktio tarkistaa, onko kahden luvun välinen delta pienempi kuin annettu tarkkuus.

```typescript
function equalWithPrecision(x: number, y: number, precision?: number): boolean;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.equalWithPrecision(1, 1.005, 0.01);

// returns: true
```

### <a name="lesswithprecision"></a>lessWithPrecision

Tämä funktio tarkistaa, onko ensimmäinen arvo pienempi kuin toinen arvo.

```typescript
function lessWithPrecision(x: number, y: number, precision?: number): boolean;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.lessWithPrecision(0.995, 1, 0.001);

// returns: true
```

### <a name="lessorequalwithprecision"></a>lessOrEqualWithPrecision

Tämä funktio tarkistaa, onko ensimmäinen arvo pienempi tai yhtä suuri kuin toinen arvo.

```typescript
function lessOrEqualWithPrecision(x: number, y: number, precision?: number): boolean;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.lessOrEqualWithPrecision(1.005, 1, 0.01);

// returns: true
```

### <a name="greaterwithprecision"></a>greaterWithPrecision

Tämä funktio tarkistaa, onko ensimmäinen arvo suurempi kuin toinen arvo.

```typescript
function greaterWithPrecision(x: number, y: number, precision?: number): boolean;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.greaterWithPrecision(1, 0.995, 0.01);

// returns: false
```

### <a name="greaterorequalwithprecision"></a>greaterOrEqualWithPrecision

Tämä funktio tarkistaa, onko ensimmäinen arvo suurempi tai yhtä suuri kuin toinen arvo.

```typescript
function greaterOrEqualWithPrecision(x: number, y: number, precision?: number): boolean;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.greaterOrEqualWithPrecision(1, 1.005, 0.01);

// returns: true
```

### <a name="floorwithprecision"></a>floorWithPrecision

Tämä funktio määrittää luvun lattian annetulla tarkkuudella.

```typescript
function floorWithPrecision(x: number, precision?: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.floorWithPrecision(5.96, 0.001);

// returns: 5
```

### <a name="ceilwithprecision"></a>ceilWithPrecision

Tämä funktio `ceils` määrittää luvun lattian annetulla tarkkuudella.

```typescript
function ceilWithPrecision(x: number, precision?: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ceilWithPrecision(5.06, 0.001);

// returns: 6
```

### <a name="floortoprecision"></a>floorToPrecision

Tämä funktio määrittää luvun lattian annettuun tarkkuuteen.

```typescript
function floorToPrecision(x: number, precision?: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.floorToPrecision(5.96, 0.1);

// returns: 5.9
```

### <a name="ceiltoprecision"></a>ceilToPrecision

Tämä funktio `ceils` määrittää luvun lattian annettuun tarkkuuteen.

```typescript
function ceilToPrecision(x: number, precision?: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ceilToPrecision(-506, 10);

// returns: -500
```

### <a name="roundtoprecision"></a>roundToPrecision

Tämä funktio pyöristää luvun annettuun tarkkuuteen.

```typescript
function roundToPrecision(x: number, precision?: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.roundToPrecision(596, 10);

// returns: 600
```

### <a name="ensureinrange"></a>ensureInRange

Tämä funktio palauttaa luvun, joka on minimin ja maksimin välillä.

```typescript
function ensureInRange(x: number, min: number, max: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ensureInRange(-27.2, -10, -5);

// returns: -10
```

### <a name="round"></a>round

Tämä funktio pyöristää luvun.

```typescript
function round(x: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.round(27.45);

// returns: 27
```

### <a name="removedecimalnoise"></a>removeDecimalNoise

Tämä funktio poistaa desimaalikohinan.

```typescript
function removeDecimalNoise(value: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.removeDecimalNoise(21.493000000000002);

// returns: 21.493
```

### <a name="isinteger"></a>isInteger

Tämä funktio tarkistaa, onko luku kokonaisluku.

```typescript
function isInteger(value: number): boolean;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.isInteger(21.493000000000002);

// returns: false
```

### <a name="toincrement"></a>toIncrement

Tämä funktio kasvattaa lukua annetulla luvulla ja palauttaa pyöristetyn luvun.

```typescript
function toIncrement(value: number, increment: number): number;
```

Esimerkki:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.toIncrement(0.6383723, 0.05);

// returns: 0.65
```

## <a name="prototype"></a>Prototyyppi

`Prototype` sisältää mahdollisuuksia periä objekteja.

Moduuli sisältää seuraavat funktiot:

## <a name="inherit"></a>inherit

Tämä funktio palauttaa uuden objektin, jossa annettu objekti on prototyyppinä.

```typescript
function inherit<T>(obj: T, extension?: (inherited: T) => void): T;
```

Esimerkki:

```typescript
import { prototype } from "powerbi-visuals-utils-typeutils";
// ...

let base = { Microsoft: "Power BI" };

prototype.inherit(base);

/* returns: {
    __proto__: {
        Microsoft: "Power BI"
    }
}*/
```

## <a name="inheritsingle"></a>inheritSingle

Tämä funktio palauttaa uuden objektin, jossa annettu objekti on sen prototyyppinä, jos prototyyppiä ei ole määritetty.

```typescript
function inheritSingle<T>(obj: T): T;
```

Esimerkki:

```typescript
import { prototype } from "powerbi-visuals-utils-typeutils";
// ...

let base = { Microsoft: "Power BI" };

prototype.inheritSingle(base);

/* returns: {
    __proto__: {
        Microsoft: "Power BI"
    }
}*/
```

## <a name="pixelconverter"></a>PixelConverter

`PixelConverter` tarjoaa mahdollisuuden muuntaa kuvapisteet pisteiksi ja pisteet kuvapisteiksi.

Moduuli sisältää seuraavat funktiot:

## <a name="tostring"></a>toString

Tämä funktio muuntaa kuvapistearvon merkkijonoksi.

```typescript
function toString(px: number): string;
```

Esimerkki:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.toString(25);

// returns: 25px
```

## <a name="frompoint"></a>fromPoint

Tämä funktio muuntaa annetun pistearvon kuvapistearvoksi ja palauttaa merkkijonotulkinnan.

```typescript
function fromPoint(pt: number): string;
```

Esimerkki:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.fromPoint(8);

// returns: 33.33333333333333px
```

## <a name="frompointtopixel"></a>fromPointToPixel

Tämä funktio muuntaa annetun pistearvon kuvapistearvoksi.

```typescript
function fromPointToPixel(pt: number): number;
```

Esimerkki:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.fromPointToPixel(8);

// returns: 10.666666666666666
```

## <a name="topoint"></a>toPoint

Tämä funktio muuntaa annetun kuvapistearvon pistearvoksi.

```typescript
function toPoint(px: number): number;
```

Esimerkki:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.toPoint(8);

// returns: 6
```
