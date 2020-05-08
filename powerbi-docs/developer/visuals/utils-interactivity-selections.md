---
title: Power BI -visualisointien vuorovaikutteisuuden apuohjelmat
description: Tässä artikkelissa kuvataan valintojen lisääminen Power BI:n visualisointeihin vuorovaikutteisuuden apuohjelmien avulla
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 02/24/2020
ms.openlocfilehash: f4d47347c98d19afdfbf07615842bfb4649dc1b9
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79379256"
---
# <a name="power-bi-visuals-interactivity-utils"></a>Power BI -visualisointien vuorovaikutteisuuden apuohjelmat

Vuorovaikutteisuuden apuohjelmat (`InteractivityUtils`) on joukko funktioita ja luokkia, joiden avulla voidaan yksinkertaistaa Power BI -visualisointien ristiinvalintaa ja ristiinsuodatusta.

> [!NOTE]
> Vuorovaikutteisuuden apuohjelmien uudet päivitykset tukevat vain työkalujen viimeisintä versiota (3.x.x ja uudemmat).

## <a name="installation"></a>Asennus

1. Jos haluat asentaa paketin. suorita seuraava komento hakemistossa, joka sisältää nykyisen Power BI -visualisointiprojektin.

    ```bash
    npm install powerbi-visuals-utils-interactivityutils --save
    ```

2. Jos käytät työkalun versiota 3.0 tai tätä uudempaa versiota, asenna `powerbi-models` riippuvuuksien ratkaisemiseksi.

    ```bash
    npm install powerbi-models --save
    ```

3. Jos haluat käyttää vuorovaikutteisuuden apuohjelmia, tuo tarvittava komponentti Power BI -visualisoinnin lähdekoodiin.

    ```typescript
    import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
    ```

### <a name="including-the-css-files"></a>CSS-tiedostojen sisällyttäminen

Jos haluat käyttää pakettia Power BI -visualisoinnissa, tuo seuraava CSS-tiedosto `.less`-tiedostoon.

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

Tuo CSS-tiedosto `.less`-tiedostona, koska Power BI -visualisointityökalu rivittää ulkoiset CSS-säännöt.

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

## <a name="selectabledatapoint-properties"></a>SelectableDataPoint-ominaisuudet

Yleensä arvopisteet sisältävät valintoja ja arvoja. Liittymä laajentaa `SelectableDataPoint`-liittymän.

`SelectableDataPoint` sisältää jo alla kuvatut ominaisuudet.

```typescript
  /** Flag for identifying that a data point was selected */
  selected: boolean;

  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;

  /*
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points select based
   * only on series, even if they exist as category/series intersections.
   */

  specificIdentity?: powerbi.extensibility.ISelectionId;
```

## <a name="defining-an-interface-for-data-points"></a>Arvopisteiden käyttöliittymän määrittäminen

1. Vuorovaikutteisuuden apuohjelmien esiintymän luominen ja esiintymän tallentaminen visualisoinnin ominaisuutena

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

2. Laajenna perustoimintaluokka.

    > [!NOTE]
    > `BaseBehavior` esiteltiin [vuorovaikutteisuuden apuohjelmien versiossa 5.6.x](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0). Jos käytät tätä vanhempaa versiota, luo käyttäytymisluokka alla olevasta mallista.

3. Määritä toimintaluokan asetusten liittymä.

    ```typescript
    import { SelectableDataPoint } from "./interactivitySelectionService";

    import {
        IBehaviorOptions,
        BaseDataPoint
    } from "./interactivityBaseService";

    export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {

    /** d3 selection object of the main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;

    /** d3 selection object of some elements on backgroup, to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
    }
    ```

4. Määritä luokka kohteelle `visual behavior`. Voit myös laajentaa luokan `BaseBehavior`.

    **Luokan määrittäminen kohteelle `visual behavior`**

    Luokka vastaa hiiren tapahtumista `click` ja `contextmenu`.

    Kun käyttäjä napsauttaa tietoelementtejä, visualisointi kutsuu valintakäsittelijää valitsemaan arvopisteet. Jos käyttäjä napsauttaa visualisoinnin taustaosaa, se kutsuu selkeää valintakäsittelijää.

    Luokalla on vastaavat menetelmät:
    * `bindClick`
    * `bindClearCatcher`
    * `bindContextMenu`.

    ```typescript
    export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {

        /** d3 selection object of main elements in the chart */
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

    **Luokan `BaseBehavior` laajentaminen**

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

5. Jos haluat käsitellä napsautuselementtejä, kutsu *d3*-valintaobjektin menetelmää `on`. Tämä koskee myös kohteita `elementsSelection` ja `clearCatcherSelection`.

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

6. Lisää vastaava käsittelijä tapahtumalle `contextmenu`, jos haluat kutsua valintojen hallinnan menetelmää `showContextMenu`.

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

7. Vuorovaikutteisuuden apuohjelmat kutsuvat menetelmää `bindEvents` määrittääkseen funktiot käsittelijöille. Lisää menetelmään `bindEvents` seuraavat kutsut:
    * `bindClick`
    * `bindClearCatcher`
    * `bindContextMenu`

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

8. `renderSelection`-menetelmä on vastuussa kaavion elementtien visualisointien tilan päivittämisestä. Tässä on esimerkki menetelmän `renderSelection` toteutuksesta.

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

9. Viimeisessä vaiheessa luodaan `visual behavior` -esiintymä ja kutsutaan vuorovaikutteisuuden apuohjelmien esiintymän menetelmää `bind`.

    ```typescript
    this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
        behavior: this.behavior,
        dataPoints: this.categories,
        clearCatcherSelection: select(this.target),
        elementsSelection: selectionMerge
    });
    ```

    * `selectionMerge` on *d3*-valintaobjekti, joka edustaa visualisoinnin kaikkia valittavissa olevia elementtejä.
    * `select(this.target)` on *d3*-valintaobjekti, joka edustaa visualisoinnin DOM-pääelementtejä.
    * `this.categories` ovat datapisteitä, joissa on elementtejä ja joissa liittymä on `VisualDataPoint` tai `categories: VisualDataPoint[];`.
    * `this.behavior` on uusi esiintymä kohteesta `visual behavior`, joka luodaan visualisoinnin konstruktorissa, kuten alla näytetään.

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
## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue, miten voit käsitellä valintoja kirjanmerkkejä vaihdettaessa](bookmarks-support.md#visuals-with-selection)

* [Lue, miten voit lisätä pikavalikon visualisointien arvopisteisiin](context-menu.md)

* [Lue, miten voit lisätä valintoja Power BI:n visualisointeihin valintojen hallinnan avulla](selection-api.md)
