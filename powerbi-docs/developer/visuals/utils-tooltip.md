---
title: Johdanto työkaluvihjeiden apuohjelmien käyttöön Power BI -visualisoinnissa
description: Tässä artikkelissa kuvataan, miten työkaluvihjeiden mukauttamista voidaan yksinkertaistaa työkaluvihjeiden apuohjelmien avulla Power BI:n visualisoinneissa
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 02/14/2020
ms.openlocfilehash: 6f4aa276438d84825c4c7aba6872210b5f3a6564
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/04/2020
ms.locfileid: "78264216"
---
# <a name="tooltip-utils"></a>Työkaluvihjeiden apuohjelmat
Tämän artikkelin avulla voit asentaa, tuoda ja käyttää työkaluvihjeiden apuohjelmia. Tämä apuohjelma on hyödyllinen kaikkien työkaluvihjeiden mukauttamiseen Power BI:n visualisoinneissa.

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

> Käyttöopas kuvailee paketin julkisen ohjelmointirajapinnan. Löydät kuvauksen ja joitakin esimerkkejä paketin jokaisesta julkisesta liittymästä.

Tämä paketti sisältää `TooltipServiceWrapper`in luomistavan ja menetelmiä, jotka auttavat työkaluvihjetoimintojen käsittelemistä. Se käyttää työkaluvihjeliittymiä – `ITooltipServiceWrapper`, `TooltipEventArgs`, `TooltipEnabledDataPoint`. 

Se sisältää lisäksi tiettyjä menetelmiä (kosketustapahtumien käsittelijöitä), jotka liittyvät mobiilikehitykseen: `touchEndEventName`, `touchStartEventName`, `usePointerEvents`.

`TooltipServiceWrapper` tarjoaa helpoimman tavan työkaluvihjeiden käsittelemiseen.

Tämä moduuli sisältää seuraavan liittymän ja toiminnon:
* [ITooltipServiceWrapper](#itooltipservicewrapper)
  * [addTooltip](#itooltipservicewrapperaddtooltip)
  * [hide](#itooltipservicewrapperhide)

* [Liittymät](#interfaces)
  * [TooltipEventArgs](#tooltipeventargs)
  * [TooltipEnabledDataPoint](#tooltipenableddatapoint)
  * [TooltipServiceWrapperOptions](#tooltipservicewrapperoptions)
* [Kosketustapahtumat](#touch-events)

### `createTooltipServiceWrapper`
Tämä funktio luo ITooltipServiceWrapper-esiintymän.

```typescript
function createTooltipServiceWrapper(tooltipService: ITooltipService, rootElement: Element, handleTouchDelay?: number,  getEventMethod?: () => MouseEvent): ITooltipServiceWrapper;
```

```ITooltipService``` on käytettävissä [IVisualHost](https://github.com/microsoft/PowerBI-visuals-tools/blob/master/templates/visuals/.api/v2.6.0/PowerBI-visuals.d.ts#L1335)issa.

**Esimerkki**

```typescript
import { createTooltipServiceWrapper } from "powerbi-visuals-utils-tooltiputils";

export class YourVisual implements IVisual {
    // implementation of IVisual.

    constructor(options: VisualConstructorOptions) {
        createTooltipServiceWrapper(
            options.host.tooltipService,
            options.element);

        // returns: an instance of ITooltipServiceWrapper.
    }
}
```

Voit tutustua mukautetun visualisoinnin esimerkkikoodiin [täällä](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L391).

### `ITooltipServiceWrapper`
Tämä liittymä kuvaa TooltipServicen julkisia menetelmiä.

```typescript
interface ITooltipServiceWrapper {
    addTooltip<T>(selection: d3.Selection<any, any, any, any>, getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => powerbi.extensibility.VisualTooltipDataItem[], getDataPointIdentity?: (args: TooltipEventArgs<T>) => powerbi.visuals.ISelectionId, reloadTooltipDataOnMouseMove?: boolean): void;
    hide(): void;
}
```

#### `ITooltipServiceWrapper.addTooltip`

Tämä menetelmä lisää työkaluvihjeitä nykyiseen valintaan.

```typescript
addTooltip<T>(selection: d3.Selection<any>, getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => VisualTooltipDataItem[], getDataPointIdentity?: (args: TooltipEventArgs<T>) => ISelectionId, reloadTooltipDataOnMouseMove?: boolean): void;
```

**Esimerkki**

```typescript
import { createTooltipServiceWrapper, TooltipEventArgs, ITooltipServiceWrapper, TooltipEnabledDataPoint } from "powerbi-visuals-utils-tooltiputils";

let bodyElement = d3.select("body");

let element = bodyElement
    .append("div")
    .style({
        "background-color": "green",
        "width": "150px",
        "height": "150px"
    })
    .classed("visual", true)
    .data([{
        tooltipInfo: [{
            displayName: "Power BI",
            value: 2016
        }]
    }]);

let tooltipServiceWrapper: ITooltipServiceWrapper = createTooltipServiceWrapper(tooltipService, bodyElement.get(0)); // tooltipService is from the IVisualHost.

tooltipServiceWrapper.addTooltip<TooltipEnabledDataPoint>(element, (eventArgs: TooltipEventArgs<TooltipEnabledDataPoint>) => {
    return eventArgs.data.tooltipInfo;
});

// You will see a tooltip if you mouseover the element.
```

Voit tutustua mukautetun visualisoinnin esimerkkikoodiin [täällä](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L2931).

Huomioi myös seuraava esimerkki työkaluvihjeen mukauttamisesta mukautetussa Gantt-visualisoinnissa [täällä](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L573-L648)

### `ITooltipServiceWrapper.hide`

Tämä menetelmä piilottaa työkaluvihjeen.

```typescript
hide(): void;
```

**Esimerkki**

```typescript
import {createTooltipServiceWrapper} from "powerbi-visuals-utils-tooltiputils";

let tooltipServiceWrapper = createTooltipServiceWrapper(options.host.tooltipService, options.element); // options are from the VisualConstructorOptions.

tooltipServiceWrapper.hide();
```
### `Interfaces`
Näitä liittymiä käytetään TooltipServiceWrapperin luomiseen ja sen käyttämiseen. Ne mainittiin myös aiemman aiheen esimerkeissä [täällä](#itooltipservicewrapperaddtooltip).

#### `TooltipEventArgs`
```typescript
interface TooltipEventArgs<TData> {
    data: TData;
    coordinates: number[];
    elementCoordinates: number[];
    context: HTMLElement;
    isTouchEvent: boolean;
}
```

#### `TooltipEnabledDataPoint`
```typescript
interface TooltipEnabledDataPoint {
    tooltipInfo?: powerbi.extensibility.VisualTooltipDataItem[];
}
```

#### `TooltipServiceWrapperOptions`
```typescript
interface TooltipServiceWrapperOptions {
    tooltipService: ITooltipService;
    rootElement: Element;
    handleTouchDelay: number;
    getEventMethod?: () => MouseEvent;
```

### `Touch events`

Työkaluvihjeiden apuohjelmat pystyvät nyt käsittelemään useita mobiilikehityksen kannalta hyödyllisiä kosketustapahtumia.

#### `touchStartEventName`
```typescript
function touchStartEventName(): string
```
Tämä menetelmä palauttaa kosketuksen aloitustapahtuman nimen.

#### `touchEndEventName`
```typescript
function touchEndEventName(): string
```
Tämä menetelmä palauttaa kosketuksen aloitustapahtuman nimen.

#### `usePointerEvents`
```typescript
function usePointerEvents(): boolean
```
Tämä menetelmä palauttaa nykyisen touchStart-tapahtuman, joka voi liittyä tai olla liittymättä osoittimeen.
