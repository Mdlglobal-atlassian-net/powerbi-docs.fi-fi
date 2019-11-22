---
title: Power BI -visualisointien vuorovaikutteisuuden apuohjelmat
description: Tässä artikkelissa kuvataan valintojen lisääminen Power BI:n visualisointeihin vuorovaikutteisuuden apuohjelmien avulla
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 8a9218085b0da655d1ce4b3ece0b2666c4826c86
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061864"
---
# <a name="microsoft-power-bi-visuals-interactivity-utils"></a>Microsoft Power BI -visualisointien vuorovaikutteisuuden apuohjelmat

Vuorovaikutteisuuden apuohjelmat (InteractivityUtils) on joukko funktioita ja luokkia, joiden avulla voidaan yksinkertaistaa mukautettujen Power BI -visualisointien ristiinvalintaa ja ristiinsuodatusta.

## <a name="installation"></a>Asennus

> [!NOTE]
> Jos jatkat vanhan powerbi-visuals-tools-version käyttämistä (versionumero alle 3.x.x), asenna työkalujen uusi versio (3.x.x).

> [!IMPORTANT]
> Vuorovaikutteisuuden apuohjelmien uudet päivitykset tukevat vain työkalujen viimeisintä versiota. [Lue lisätietoja siitä, kuinka visualisointikoodi päivitetään käytettäväksi uusimpien työkalujen kanssa](migrate-to-new-tools.md)

Paketin asentamista varten tulee suorittaa seuraava komento hakemistossa, joka sisältää nykyisen mukautetun visualisoinnin:

```bash
npm install powerbi-visuals-utils-interactivityutils --save
```

Versiosta 3.0 eteenpäin on lisäksi asennettava ```powerbi-models``` riippuvuuksien ratkaisemiseksi.

```bash
npm install powerbi-models --save
```

Käyttäjien vuorovaikutteisuuden apuohjelmiin on tuotava tarvittava komponentti visualisoinnin lähdekoodiin.

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
```

### <a name="including-css-artifacts-to-the-custom-visual"></a>CSS-artefaktien sisällyttäminen mukautettuun visualisointiin

Jos haluat käyttää pakettia mukautettujen visualisointiesi kanssa, tuo seuraava CSS-tiedosto `your.less`-tiedostoon:

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

Tuloksena on seuraava tiedostorakenne:

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

> [!NOTE]
> Tuo .css-tiedosto .less-tiedostona, koska Power BI Visuals Tools rivittää ulkoiset CSS-säännöt.

## <a name="usage"></a>Käyttö

### <a name="define-interface-for-data-points"></a>Määritä arvopisteiden käyttöliittymä

Yleensä arvopisteet sisältävät valintoja ja arvoja. Liittymä laajentaa `SelectableDataPoint`-liittymän. `SelectableDataPoint` sisältää jo ominaisuuksia:

```typescript
  /** Flag for identifying that data point was selected */
  selected: boolean;
  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;
  /**
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points should select based
   * only on series even if they exist as category/series intersections.
   */
  specificIdentity?: powerbi.extensibility.ISelectionId;
```

Vuorovaikutteisuuden apuohjelmien käyttämisen ensimmäisenä vaiheena on vuorovaikutteisuuden apuohjelmien ja tallentamisen objektin esiintymän tallentaminen visualisoinnin ominaisuutena.

```typescript
export class Visual implements IVisual {
  // ...
  private interactivity: interactivityBaseService.IInteractivityService<VisualDataPoint>;
  // ...
  constructor(options: VisualConstructorOptions) {
      // ...
      this.interactivity = interactivitySelectionService.createInteractivitySelectionService(this.host);
      // ...
  }
}
```

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}
```

Toinen vaihe on perustoimintaluokan laajentaminen:

> [!NOTE]
> BaseBehavior esiteltiin [vuorovaikutteisuuden apuohjelmien versiossa 5.6.x](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0). Jos käytät vanhaa versiota, luo käyttäytymisluokka alla olevasta mallista (`BaseBehavior`-luokka on sama):

Määritä toimintaluokan asetusten liittymä:

```typescript
import { SelectableDataPoint } from "./interactivitySelectionService";

import {
    IBehaviorOptions,
    BaseDataPoint
} from "./interactivityBaseService";

export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {
    /** D3 selection object of main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;
    /** D3 selection object of some element on backgroup to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
}
```

Määritä luokka kohteelle `visual behaviour`. Luokka, joka vastaa hiiren tapahtumista `click`, `contextmenu`.
Kun klikkauksia käytetään tietoelementteihin, visuaalisten kutsujen valintakäsittely valitsee arvopisteet. Tai tyhjennä valinta, jos käyttäjä napsauttaa visualisoinnin tausta-osaa. Ja luokalla on vastaavat metodit: `bindClick`, `bindClearCatcher`, `bindContextMenu`.

```typescript
export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {
    /** D3 selection object of main elements on the chart */
    protected options: BaseBehaviorOptions<SelectableDataPointType>;
    protected selectionHandler: ISelectionHandler;

    protected bindClick() {
      // ...
    }

    protected bindClearCatcher() {
      // ...
    }

    protected bindContextMenu() {
      // ...
    }

    public bindEvents(
        options: BaseBehaviorOptions<SelectableDataPointType>,
        selectionHandler: ISelectionHandler): void {
      // ...
    }

    public renderSelection(hasSelection: boolean): void {
      // ...
    }
}
```

tai voit laajentaa luokkaa `BaseBehavior`:

```typescript
import powerbi from "powerbi-visuals-api";
import { interactivitySelectionService, baseBehavior } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}

export class Behavior extends baseBehavior.BaseBehavior<VisualDataPoint> {
  // ...
}
```

Elementtien klikkauksien käsittelyä varten kutsu D3-valintaobjektin metodia `on` (myös kohteille elementsSelection ja clearCatcherSelection):

```typescript
protected bindClick() {
  const {
      elementsSelection
  } = this.options;

  elementsSelection.on("click", (datum) => {
      const mouseEvent: MouseEvent = getEvent() as MouseEvent || window.event as MouseEvent;
      mouseEvent && this.selectionHandler.handleSelection(
          datum,
          mouseEvent.ctrlKey);
  });
}
```

Lisää vastaava käsittelijä tapahtumalle `contextmenu`, jos haluat kutsua valintojen hallinnan metodia `showContextMenu`:

```typescript
protected bindContextMenu() {
    const {
        elementsSelection
    } = this.options;

    elementsSelection.on("contextmenu", (datum) => {
        const event: MouseEvent = (getEvent() as MouseEvent) || window.event as MouseEvent;
        if (event) {
            this.selectionHandler.handleContextMenu(
                datum,
                {
                    x: event.clientX,
                    y: event.clientY
                });
            event.preventDefault();
        }
    });
}
```

Vuorovaikutteisuuden apuohjelmat kutsuvat `bindEvents`-metodeita, joilla voidaan delegoida funktioita käsittelijöille sekä lisätä `bindClick`-, `bindClearCatcher`- ja `bindContextMenu`-kutsuja `bindEvents`-metodiin:

```typescript
  public bindEvents(
      options: BaseBehaviorOptions<SelectableDataPointType>,
      selectionHandler: ISelectionHandler): void {

      this.options = options;
      this.selectionHandler = selectionHandler;

      this.bindClick();
      this.bindClearCatcher();
      this.bindContextMenu();
  }
```

`renderSelection`-metodi on vastuussa kaavion elementtien visualisointien tilan päivittämisestä.

Malli toteutuksen `renderSelection`-metodista:

```typescript
public renderSelection(hasSelection: boolean): void {
    this.options.elementsSelection.style("opacity", (category: any) => {
        if (category.selected) {
            return 0.5;
        } else {
            return 1;
        }
    });
}
```

Viimeisessä vaiheessa luodaan `visual behavior` -esiintymä ja vuorovaikutteisuuden apuohjelmat -esiintymän `bind`-metodin kutsu:

```typescript
this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
    behavior: this.behavior,
    dataPoints: this.categories,
    clearCatcherSelection: select(this.target),
    elementsSelection: selectionMerge
});
```

* `selectionMerge` on D3-valintaobjekti, joka edustaa visualisoinnin kaikkia valittavissa olevia elementtejä.

* `select(this.target)` on D3-valintaobjekti, joka edustaa visualisoinnin DOM-pääelementtejä.

* `this.categories`-tiedot osoittavat elementeillä, ja liittymä on `VisualDataPoint` (tai `categories: VisualDataPoint[];`)

* `this.behavior` on uusi `visual behavior` -esiintymä

  luodaan visualisoinnin konstruktorissa:

  ```typescript
  export class Visual implements IVisual {
    // ...
    constructor(options: VisualConstructorOptions) {
        // ...
        this.behavior = new Behavior();
    }
    // ...
  }
  ```

Visualisointi on nyt valmis käsittelijän valintaan.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue, miten voit käsitellä valintoja kirjanmerkkejä vaihdettaessa](bookmarks-support.md#visuals-with-selection)

* [Lue, miten voit lisätä pikavalikon visualisointien arvopisteisiin](context-menu.md)

* [Lue, miten voit lisätä valintoja Power BI:n visualisointeihin valintojen hallinnan avulla](selection-api.md)
