---
title: Johdanto Power BI -visualisoinnin väriapuohjelmien käyttöön
description: Tässä artikkelissa kerrotaan, miten voit käyttää väriapuohjelmia yksinkertaistamaan teemojen ja palettien käyttöä Power BI -visualisointien arvopisteissä
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 02/14/2020
ms.openlocfilehash: 8de530871739a18c1afc72cee3e0da5fc70ebb16
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79379348"
---
# <a name="color-utils"></a>Väriapuohjelmat
Tämän artikkelin avulla voit asentaa, tuoda ja käyttää väriapuohjelmia. Tässä artikkelissa kerrotaan, miten voit käyttää väriapuohjelmia yksinkertaistamaan teemojen ja palettien käyttöä Power BI -visualisointien arvopisteissä.

## <a name="requirements"></a>Vaatimukset
Jotta voit käyttää pakettia, sinulla tulee olla:
* [node.js](https://nodejs.org) (suosittelemme uusinta LTS:n versiota)
* [npm](https://www.npmjs.com/) (vanhin tuettu versio on 3.0.0)
* [PowerBI-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools)-työkalun luoma mukautettu visualisointi

## <a name="installation"></a>Asennus

Paketin asentamista varten tulee suorittaa seuraava komento hakemistossa, joka sisältää nykyisen visualisoinnin:

```bash
npm install powerbi-visuals-utils-colorutils --save
```
Tämä komento asentaa paketin ja lisää paketin riippuvuutena ```package.json```-tiedostoon

## <a name="usage"></a>Käyttö

Käyttäjien vuorovaikutteisuuden apuohjelmiin on tuotava tarvittava komponentti visualisoinnin lähdekoodiin.
```typescript
import { ColorHelper } from "powerbi-visuals-utils-colorutils";
```

Opi asentamaan väriapuohjelmat ja käyttämään niitä Power BI -visualisoinneissa:

* [Käyttöopas] Käyttöopas kuvailee paketin julkisen ohjelmointirajapinnan. Löydät kuvauksen ja joitakin esimerkkejä paketin jokaisesta julkisesta liittymästä.

Tämä paketti sisältää seuraavat luokat ja moduulit:
* [Väriapusovellus](#colorhelper) – auttaa luomaan eri värejä kaavion arvoille
* [Väriapuohjelmat](#colorutils) – auttaa muuntamaan värimuotoja

## `ColorHelper`
`ColorHelper`-luokka tarjoaa seuraavat toiminnot ja menetelmät:

### `getColorForSeriesValue` 
Tämä menetelmä hakee annetun sarjan arvon värin. Jos mitään tiettyä väriä tai oletusväriä ei ole määritetty, väri haetaan tämän sarjan väriskaalasta.
```typescript
getColorForSeriesValue(objects: IDataViewObjects, value: PrimitiveValue, themeColorName?: ThemeColorName): string;
```
#### <a name="example"></a>Esimerkki
```typescript
import powerbi from "powerbi-visuals-api";
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

import DataViewObjects = powerbi.DataViewObjects;

import DataViewValueColumns = powerbi.DataViewValueColumns;
import DataViewValueColumnGroup = powerbi.DataViewValueColumnGroup;
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;

import IVisual = powerbi.extensibility.visual.IVisual;
import IColorPalette = powerbi.extensibility.IColorPalette;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class YourVisual implements IVisual {
    // Implementation of IVisual

    private colorPalette: IColorPalette;

    constructor(options: VisualConstructorOptions) {
        this.colorPalette = options.host.colorPalette;
    }

    public update(visualUpdateOptions: VisualUpdateOptions): void {
        const valueColumns: DataViewValueColumns = visualUpdateOptions.dataViews[0].categorical.values,
            grouped: DataViewValueColumnGroup[] = valueColumns.grouped(),
            defaultDataPointColor: string = "green",
            fillProp: DataViewObjectPropertyIdentifier = {
                objectName: "objectName",
                propertyName: "propertyName"
            };

        let colorHelper: ColorHelper = new ColorHelper(
            this.colorPalette,
            fillProp,
            defaultDataPointColor);

        for (let i = 0; i < grouped.length; i++) {
            let grouping: DataViewValueColumnGroup = grouped[i];

            let color = colorHelper.getColorForSeriesValue(grouping.objects, grouping.name); // returns a color of the series
        }
    }
}
```

### `getColorForMeasure`
Tämä menetelmä hakee annetun mittarin värin.
```typescript
 getColorForMeasure(objects: IDataViewObjects, measureKey: any, themeColorName?: ThemeColorName): string;
```
#### <a name="example"></a>Esimerkki
```typescript
import powerbi from "powerbi-visuals-api";
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

import DataViewObjects = powerbi.DataViewObjects;
import IVisual = powerbi.extensibility.visual.IVisual;
import IColorPalette = powerbi.extensibility.IColorPalette;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class YourVisual implements IVisual {
    // Implementation of IVisual

    private colorPalette: IColorPalette;

    constructor(options: VisualConstructorOptions) {
        this.colorPalette = options.host.colorPalette;
    }

    public update(visualUpdateOptions: VisualUpdateOptions): void {
        const objects: DataViewObjects = visualUpdateOptions.dataViews[0].categorical.categories[0].objects[0],
            defaultDataPointColor: string = "green",
            fillProp: DataViewObjectPropertyIdentifier = {
                objectName: "objectName",
                propertyName: "propertyName"
            };

        let colorHelper: ColorHelper = new ColorHelper(
            this.colorPalette,
            fillProp,
            defaultDataPointColor);

        let color = colorHelper.getColorForMeasure(objects, ""); // returns a color
    }
}
```

### <a name="static-normalizeselector"></a>staattinen `normalizeSelector`
Tämä menetelmä palauttaa normalisoidun valitsimen
```typescript
static normalizeSelector(selector: Selector, isSingleSeries?: boolean): Selector;
```
#### <a name="example"></a>Esimerkki
```typescript
import ISelectionId = powerbi.visuals.ISelectionId;
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

let selectionId: ISelectionId = ...;
let selector = ColorHelper.normalizeSelector(selectionId.getSelector(), false);
```

Menetelmät `getThemeColor` ja `getHighContrastColor` liittyvät väriteeman väreihin.
`ColorHelper` sisältää myös `isHighContrast`-ominaisuuden, josta voi olla hyötyä.

### `getThemeColor`
Tämä menetelmä palauttaa teeman värin
```typescript
 getThemeColor(themeColorName?: ThemeColorName): string;
```
### `getHighContrastColor`
 Tämä menetelmä palauttaa värin suuren kontrastin tilaa varten
```typescript
getHighContrastColor(themeColorName?: ThemeColorName, defaultColor?: string): string;
```
#### <a name="example-related-to-high-contrast-mode-usage"></a>Suuren kontrastin tilan käyttöön liittyvä esimerkki:
```typescript

import { ColorHelper } from "powerbi-visuals-utils-colorutils";

export class MyVisual implements IVisual {
        private colorHelper: ColorHelper;

        private init(options: VisualConstructorOptions): void {
            this.colors = options.host.colorPalette;
            this.colorHelper = new ColorHelper(this.colors);
        } 

            private createViewport(element: HTMLElement): void {
                const fontColor: string = "#131aea";
                const axisBackgroundColor: string = this.colorHelper.getThemeColor();
                
                // some d3 code before
                d3ElementName.attr("fill", colorHelper.getHighContrastColor("foreground", fontColor);
            }
                
            public static parseSettings(dataView: DataView, colorHelper: ColorHelper): VisualSettings {
                // some code that should be applied on formatting settings
                if (colorHelper.isHighContrast) {
                        this.settings.fontColor = colorHelper.getHighContrastColor("foreground", this.settings.fontColor);
                    }
            }
}
```


## `ColorUtils`
 Moduuli sisältää seuraavat funktiot:

* [hexToRGBString](#hextorgbstring)
* [rotate](#rotate)
* [parseColorString](#parsecolorstring)
* [calculateHighlightColor](#calculatehighlightcolor)
* [createLinearColorScale](#createlinearcolorscale)
* [shadeColor](#shadecolor)
* [rgbBlend](#rgbblend)
* [channelBlend](#channelblend)
* [hexBlend](#hexblend)

### <a name="hextorgbstring"></a>hexToRGBString
Muuntaa heksadesimaalivärin RGB-merkkijonoksi.

```typescript
function hexToRGBString(hex: string, transparency?: number): string
```

#### <a name="example"></a>Esimerkki

```typescript
import  { hexToRGBString } from "powerbi-visuals-utils-colorutils";

hexToRGBString('#112233');

// returns: "rgb(17,34,51)"
```

### <a name="rotate"></a>rotate
Kiertää RGB-värin.

```typescript
function rotate(rgbString: string, rotateFactor: number): string
```

#### <a name="example"></a>Esimerkki

```typescript
import { rotate } from "powerbi-visuals-utils-colorutils";

rotate("#CC0000", 0.25); // returns: #66CC00
```

### <a name="parsecolorstring"></a>parseColorString
Jäsentää minkä tahansa värimerkkijonon RGB-muotoiseksi.

```typescript
function parseColorString(color: string): RgbColor
```

#### <a name="example"></a>Esimerkki

```typescript
import { parseColorString } from "powerbi-visuals-utils-colorutils";

parseColorString('#09f');
// returns: {R: 0, G: 153, B: 255 }

parseColorString('rgba(1, 2, 3, 1.0)');
// returns: {R: 1, G: 2, B: 3, A: 1.0 }
```

### <a name="calculatehighlightcolor"></a>calculateHighlightColor
Laske korostusväri rgbColor-kohteesta lumianceThreshold- ja delta-arvojen perusteella.

```typescript
function calculateHighlightColor(rgbColor: RgbColor, lumianceThreshold: number, delta: number): string
```

#### <a name="example"></a>Esimerkki

```typescript
import { calculateHighlightColor } from "powerbi-visuals-utils-colorutils";

let yellow = "#FFFF00",
    yellowRGB = parseColorString(yellow);

calculateHighlightColor(yellowRGB, 0.8, 0.2);

// returns: '#CCCC00'
```

### <a name="createlinearcolorscale"></a>createLinearColorScale
Palauttaa lineaarisen väriasteikon annetulle numeroalueelle.

```typescript
function createLinearColorScale(domain: number[], range: string[], clamp: boolean): LinearColorScale
```

#### <a name="example"></a>Esimerkki

```typescript
import { createLinearColorScale } from "powerbi-visuals-utils-colorutils";

let scale = ColorUtility.createLinearColorScale(
    [0, 1, 2, 3, 4],
    ["red", "green", "blue", "black", "yellow"],
    true);

scale(1); // returns: green
scale(10); // returns: yellow
```

### <a name="shadecolor"></a>shadeColor
Muuntaa merkkijonon heksalausekkeen luvuksi, laskee prosenttiluvun ja R-, G- ja B-kanavat.
Käyttää prosenttiosuutta kuhunkin kanavaan ja palauttaa heksadesimaaliarvon merkkijonona, jossa on ristikkomerkki.

```typescript
function shadeColor(color: string, percent: number): string
```

#### <a name="example"></a>Esimerkki

```typescript
import { shadeColor } from "powerbi-visuals-utils-colorutils";

shadeColor('#000000', 0.1); // returns '#1a1a1a'
shadeColor('#FFFFFF', -0.5); // returns '#808080'
shadeColor('#00B8AA', -0.25); // returns '#008a80'
shadeColor('#00B8AA', 0); // returns '#00b8aa'
```

### <a name="rgbblend"></a>rgbBlend
Lisää peittävän värin taustavärin päälle. Kaikki alfakanavat ohitetaan.

```typescript
function rgbBlend(foreColor: RgbColor, opacity: number, backColor: RgbColor): RgbColor
```

#### <a name="example"></a>Esimerkki

```typescript
import { rgbBlend} from "powerbi-visuals-utils-colorutils";

rgbBlend({R: 100, G: 100, B: 100}, 0.5, {R: 200, G: 200, B: 200});

// returns: {R: 150, G: 150, B: 150}
```

### <a name="channelblend"></a>channelBlend
Sekoittaa yhden kanavan kahdelle värille.

```typescript
function channelBlend(foreChannel: number, opacity: number, backChannel: number): number
```

#### <a name="example"></a>Esimerkki

```typescript
import { channelBlend} from "powerbi-visuals-utils-colorutils";

channelBlend(0, 1, 255); // returns: 0
channelBlend(128, 1, 255); // returns: 128
channelBlend(255, 0, 0); // returns: 0
channelBlend(88, 0, 88); // returns: 88
```

### <a name="hexblend"></a>hexBlend
Lisää peittävän värin taustavärin päälle.

```typescript
function hexBlend(foreColor: string, opacity: number, backColor: string): string
```

#### <a name="example"></a>Esimerkki

```typescript
import { hexBlend} from "powerbi-visuals-utils-colorutils";

let yellow = "#FFFF00",
    black = "#000000",
    white = "#FFFFFF";

hexBlend(yellow, 0.5, white); // returns: "#FFFF80"
hexBlend(white, 0.5, yellow); // returns: "#FFFF80"

hexBlend(yellow, 0.5, black); // returns: "#808000"
hexBlend(black, 0.5, yellow); // returns: "#808000"
```