---
title: Johdanto Power BI -visualisoinnin testiapuohjelmien käyttöön
description: Tässä artikkelissa kuvataan, miten testiapuohjelmien avulla yksinkertaistetaan testejä ja tiettyjen menetelmien käyttöä Power BI -visualisointien yksikkötestauksessa
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 02/14/2020
ms.openlocfilehash: c50ad894b2e1f5eb838abdd4442f473f8bcbbb10
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82196602"
---
# <a name="power-bi-visuals-test-utils"></a>Power BI -visualisointien testiapuohjelmat

Tämän artikkelin avulla voit asentaa, tuoda ja käyttää Power BI -visualisointien testiapuohjelmia. Näitä testiapuohjelmia voidaan käyttää yksikkötestaukseen, ja ne sisältävät testejä ja menetelmiä esimerkiksi tietonäkymiä, valintoja ja värirakenteita varten.

## <a name="requirements"></a>Vaatimukset

Jos haluat käyttää tätä pakettia, sinun on asennettava seuraavat:

* [node.js](https://nodejs.org), on suositeltavaa käyttää LTS-versiota
* [npm](https://www.npmjs.com/), versio 3.0.0 tai uudempi
* [PowerBI-visuals-tools](https://github.com/Microsoft/PowerBI-visuals-tools)-työkalupaketti

## <a name="installation"></a>Asennus

Kun haluat asentaa testiapuohjelmat ja lisätä niiden riippuvuussuhteet *package.json*-tiedostoon, suorita seuraava komento Power BI -visualisointien hakemistosta:

```bash
npm install powerbi-visuals-utils-testutils --save
```

Seuraavassa on testiapuohjelmien julkisen ohjelmointirajapinnan kuvaukset ja esimerkkejä niistä.

## <a name="visualbuilderbase"></a>VisualBuilderBase

**VisualBuilder** käyttää tätä yksikkötesteissä useimmin käytettyjen menetelmien `build`, `update`ja `updateRenderTimeout` kanssa. 

`build`-menetelmä palauttaa visualisoinnin luodun esiintymän.

`enumerateObjectInstances`- ja `updateEnumerateObjectInstancesRenderTimeout`-menetelmiä tarvitaan säilö- ja muotoiluasetusten muutosten tarkistamiseen.

```typescript
abstract class VisualBuilderBase<T extends IVisual> {
    element: JQuery;
    viewport: IViewport;
    visualHost: IVisualHost;
    protected visual: T;
    constructor(width?: number, height?: number, guid?: string, element?: JQuery);
    protected abstract build(options: VisualConstructorOptions): T;
     nit(): void;
    destroy(): void;
    update(dataView: DataView[] | DataView): void;
    updateRenderTimeout(dataViews: DataView[] | DataView, fn: Function, timeout?: number): number;
    updateEnumerateObjectInstancesRenderTimeout(dataViews: DataView[] | DataView, options: EnumerateVisualObjectInstancesOptions, fn: (enumeration: VisualObjectInstance[]) => void, timeout?: number): number;
    updateFlushAllD3Transitions(dataViews: DataView[] | DataView): void;
    updateflushAllD3TransitionsRenderTimeout(dataViews: DataView[] | DataView, fn: Function, timeout?: number): number;
    enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstance[];
}
```

> [!NOTE]
> Lisäesimerkkejä on kohdassa [VisualBuilderBase-yksikkötestien kirjoittaminen](./unit-tests-introduction.md#create-a-visual-instance-builder) ja [VisualBuilderBase-skenaarion todellisessa käyttöesimerkissä](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/test/visualBuilder.ts).

## <a name="dataviewbuilder"></a>DataViewBuilder

**TestDataViewBuilder** käyttää tätä moduulia, joka sisältää `createCategoricalDataViewBuilder`-menetelmässä käytettävän **CategoricalDataViewBuilder**-luokan. Se määrittää myös käyttöliittymät ja menetelmät, joita tarvitaan testattavan **DataView**-kohteen yksikkötesteissä.

* `withValues` lisää staattiset sarjasarakkeet, ja `withGroupedValues` lisää dynaamiset sarjasarakkeet

  Älä käytä sekä dynaamista sarjaa että staattista sarjaa **DataViewCategorical**-visualisoinnissa. Voit käyttää niitä molempia vain **DataViewCategorical**-kyselyssä, jossa **DataViewTransform**-toiminto jakaa ne erillisiin **DataViewCategorical**-visualisointiobjekteihin.

* `build` palauttaa DataView-kohteen, jossa on metatiedot ja DataViewCategorical

  `build` palauttaa **Määrittämätön**-arvon, jos parametrien yhdistelmä on virheellinen, kuten sekä dynaamisen että staattisen sarjan mukaanotto, kun **DataView**-visualisointi luodaan.

```typescript
class CategoricalDataViewBuilder implements IDataViewBuilderCategorical {
    withCategory(options: DataViewBuilderCategoryColumnOptions): IDataViewBuilderCategorical;
    withCategories(categories: DataViewCategoryColumn[]): IDataViewBuilderCategorical;
    withValues(options: DataViewBuilderValuesOptions): IDataViewBuilderCategorical;
    withGroupedValues(options: DataViewBuilderGroupedValuesOptions): IDataViewBuilderCategorical;
    build(): DataView;
}

function createCategoricalDataViewBuilder(): IDataViewBuilderCategorical;
```

## <a name="testdataviewbuilder"></a>TestDataViewBuilder

Käytetään **VisualData**-kohteen luomiseen yksikkötesteissä. Kun tietoja sijoitetaan tietokenttäsäilöihin, Power BI tuottaa tietoihin perustuvan luokittaisen **DataView**-objektin. **TestDataViewBuilder** auttaa simuloimaan luokittaisen **DataView**-kohteen luontia.

```typescript
abstract class TestDataViewBuilder {
    static DataViewName: string;
    private aggregateFunction;
    static setDefaultQueryName(source: DataViewMetadataColumn): DataViewMetadataColumn;
    static getDataViewBuilderColumnIdentitySources(options: TestDataViewBuilderColumnOptions[] | TestDataViewBuilderColumnOptions): DataViewBuilderColumnIdentitySource[];
    static getValuesTable(categories?: DataViewCategoryColumn[], values?: DataViewValueColumn[]): any[][];
    static createDataViewBuilderColumnOptions(categoriesColumns: (TestDataViewBuilderCategoryColumnOptions | TestDataViewBuilderCategoryColumnOptions[])[], valuesColumns: (DataViewBuilderValuesColumnOptions | DataViewBuilderValuesColumnOptions[])[], filter?: (options: TestDataViewBuilderColumnOptions) => boolean, customizeColumns?: CustomizeColumnFn): DataViewBuilderAllColumnOptions;
    static setUpDataViewBuilderColumnOptions(options: DataViewBuilderAllColumnOptions, aggregateFunction: (array: number[]) => number): DataViewBuilderAllColumnOptions;
    static setUpDataView(dataView: DataView, options: DataViewBuilderAllColumnOptions): DataView;
    protected createCategoricalDataViewBuilder(categoriesColumns: (TestDataViewBuilderCategoryColumnOptions | TestDataViewBuilderCategoryColumnOptions[])[], valuesColumns: (DataViewBuilderValuesColumnOptions | DataViewBuilderValuesColumnOptions[])[], columnNames: string[], customizeColumns?: CustomizeColumnFn): IDataViewBuilderCategorical;
    abstract getDataView(columnNames?: string[]): DataView;
}
```

  Seuraavassa on luettelo käyttöliittymistä, joita käytetään useimmin `testDataView`-kohteen luonnissa:

  ```typescript
  interface TestDataViewBuilderColumnOptions extends DataViewBuilderColumnOptions {
      values: any[];
  }

  interface TestDataViewBuilderCategoryColumnOptions extends TestDataViewBuilderColumnOptions {
      objects?: DataViewObjects[];
      isGroup?: boolean;
  }

  interface DataViewBuilderColumnOptions {
      source: DataViewMetadataColumn;
  }

  interface DataViewBuilderSeriesData {
      values: PrimitiveValue[];
      highlights?: PrimitiveValue[];
      /** Client-computed maximum value for a column. */
      maxLocal?: any;
      /** Client-computed maximum value for a column. */
      minLocal?: any;
  }

  interface DataViewBuilderColumnIdentitySource {
      fields: any[];
      identities?: CustomVisualOpaqueIdentity[];
  }
  ```
   
> [!NOTE]
> Lisäesimerkkejä on kohdassa [TestDataViewBuilder-yksikkötestien kirjoittaminen](./unit-tests-introduction.md#how-to-add-static-data-for-unit-tests) ja [TestDataViewBuilder-skenaarion todellisessa käyttöesimerkissä](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/test/visualData.ts).

## <a name="mocks"></a>Testit

### <a name="mockivisualhost"></a>MockIVisualHost

Toteuttaa **IVisualHost**-toiminnon Power BI -visualisointien testaamisessa ilman ulkoisia riippuvuuksia, kuten Power BI -sovelluskehystä.

Hyödyllisiä menetelmiä ovat `createSelectionIdBuilder`-, `createSelectionManager`-, `createLocalizationManager`- ja getter-ominaisuudet.

```typescript
import powerbi from "powerbi-visuals-api";

import VisualObjectInstancesToPersist = powerbi.VisualObjectInstancesToPersist;
import ISelectionIdBuilder = powerbi.visuals.ISelectionIdBuilder;
import ISelectionManager = powerbi.extensibility.ISelectionManager;
import IColorPalette = powerbi.extensibility.IColorPalette;
import IVisualEventService = powerbi.extensibility.IVisualEventService;
import ITooltipService = powerbi.extensibility.ITooltipService;
import IVisualHost = powerbi.extensibility.visual.IVisualHost;

class MockIVisualHost implements IVisualHost {
      constructor(
          colorPalette?: IColorPalette,
          selectionManager?: ISelectionManager,
          tooltipServiceInstance?: ITooltipService,
          localeInstance?: MockILocale,
          allowInteractionsInstance?: MockIAllowInteractions,
          localizationManager?: powerbi.extensibility.ILocalizationManager,
          telemetryService?: powerbi.extensibility.ITelemetryService,
          authService?: powerbi.extensibility.IAuthenticationService,
          storageService?: ILocalVisualStorageService,
          eventService?: IVisualEventService);
      createSelectionIdBuilder(): ISelectionIdBuilder;
      createSelectionManager(): ISelectionManager;
      createLocalizationManager(): ILocalizationManager;
      colorPalette: IColorPalette;
      locale: string;
      telemetry: ITelemetryService;
      tooltipService: ITooltipService;
      allowInteractios: boolean;
      storageService: ILocalVisualStorageService;
      eventService: IVisualEventService;
      persistProperties(changes: VisualObjectInstancesToPersist): void;
}
```
   
- `createVisualHost` luo ja palauttaa **IVisualHost**-esiintymän, itse asiassa **MockIVisualHost**-esiintymän
  ```typescript
  function createVisualHost(locale?: Object, allowInteractions?: boolean, colors?: IColorInfo[], isEnabled?: boolean, displayNames?: any, token?: string): IVisualHost;
  ```

    Esimerkki
    ```typescript
    import { createVisualHost } from "powerbi-visuals-utils-testutils"

    let host: IVisualHost = createVisualHost();
    ```

> [!IMPORTANT]
> **MockIVisualHost** on **IVisualHost**-kohteen valetoteutus, ja sitä tulee käyttää vain yksikkötesteissä.

### <a name="mockicolorpalette"></a>MockIColorPalette

Toteuttaa **IColorPalette**-toiminnon Power BI -visualisointien testaamisessa ilman ulkoisia riippuvuuksia, kuten Power BI -sovelluskehystä.

**MockIColorPalette** sisältää hyödyllisiä värirakenteen tai suurikontrastisen tilan tarkistamiseen yksikkötesteissä.

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import IColorPalette = powerbi.extensibility.ISandboxExtendedColorPalette;
  import IColorInfo = powerbi.IColorInfo;

  class MockIColorPalette implements IColorPalette {
      constructor(colors?: IColorInfo[]);
      getColor(key: string): IColorInfo;
      reset(): IColorPalette;
      isHighContrastMode: boolean;
      foreground: {value: string};
      foregroundLight: {value: string};
      ...
      background: {value: string};
      backgroundLight: {value: string};
      ...
      shapeStroke: {value: string};
  }
  ```
  - `createColorPalette` luo ja palauttaa **IColorPalette**-esiintymän, itse asiassa **MockIColorPalette**-esiintymän
    ```typescript
    function createColorPalette(colors?: IColorInfo[]): IColorPalette;
    ```

    Esimerkki
    ```typescript
    import { createColorPalette } from "powerbi-visuals-utils-testutils"

    let colorPalette: IColorPalette = createColorPalette();
    ```
    
> [!IMPORTANT]
> **MockIColorPalette** on **IColorPalette**-kohteen valetoteutus, ja sitä tulee käyttää vain yksikkötesteissä.

### <a name="mockiselectionid"></a>MockISelectionId

Toteuttaa **ISelectionId**-toiminnon Power BI -visualisointien testaamisessa ilman ulkoisia riippuvuuksia, kuten Power BI -sovelluskehystä.

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import Selector = powerbi.data.Selector;
  import ISelectionId = powerbi.visuals.ISelectionId;

  class MockISelectionId implements ISelectionId {
      constructor(key: string);
      equals(other: ISelectionId): boolean;
      includes(other: ISelectionId, ignoreHighlight?: boolean): boolean;
      getKey(): string;
      getSelector(): Selector;
      getSelectorsByColumn(): Selector;
      hasIdentity(): boolean;
  }
  ```

  - `createSelectionId` luo ja palauttaa **ISelectionId-** -esiintymän, itse asiassa **MockISelectionId**-esiintymän
    ```typescript
    function createSelectionId(key?: string): ISelectionId;
    ```

    Esimerkki
    ```typescript
    import { createColorPalette } from "powerbi-visuals-utils-testutils"

    let selectionId: ISelectionId = createSelectionId();
    ```
    
> [!NOTE]
> **MockISelectionId** on **ISelectionId**-kohteen valetoteutus, ja sitä tulee käyttää vain yksikkötesteissä.

### <a name="mockiselectionidbuilder"></a>MockISelectionIdBuilder

Toteuttaa **ISelectionIdBuilder**-toiminnon Power BI -visualisointien testaamisessa ilman ulkoisia riippuvuuksia, kuten Power BI -sovelluskehystä. 

  ```typescript
  import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
  import DataViewValueColumn = powerbi.DataViewValueColumn;
  import DataViewValueColumnGroup = powerbi.DataViewValueColumnGroup;
  import DataViewValueColumns = powerbi.DataViewValueColumns;
  import ISelectionIdBuilder = powerbi.visuals.ISelectionIdBuilder;
  import ISelectionId = powerbi.visuals.ISelectionId;

  class MockISelectionIdBuilder implements ISelectionIdBuilder {
      withCategory(categoryColumn: DataViewCategoryColumn, index: number): this;
      withSeries(seriesColumn: DataViewValueColumns, valueColumn: DataViewValueColumn | DataViewValueColumnGroup): this;
      withMeasure(measureId: string): this;
      createSelectionId(): ISelectionId;
      withMatrixNode(matrixNode: DataViewMatrixNode, levels: DataViewHierarchyLevel[]): this;
      withTable(table: DataViewTable, rowIndex: number): this;
  }
  ```

  - `createSelectionIdBuilder` luo ja palauttaa **ISelectionIdBuilder-** -esiintymän, itse asiassa **MockISelectionIdBuilder**-esiintymän
    ```typescript
    function createSelectionIdBuilder(): ISelectionIdBuilder;
    ```

    Esimerkki
    ```typescript
    import { selectionIdBuilder } from "powerbi-visuals-utils-testutils";

    let selectionIdBuilder = createSelectionIdBuilder();
    ```

> [!NOTE]
> **MockISelectionIdBuilder** on **ISelectionIdBuilder**-kohteen valetoteutus, ja sitä tulee käyttää vain yksikkötesteissä.

### <a name="mockiselectionmanager"></a>MockISelectionManager

Toteuttaa **ISelectionManager**-toiminnon Power BI -visualisointien testaamisessa ilman ulkoisia riippuvuuksia, kuten Power BI -sovelluskehystä. 

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import IPromise = powerbi.IPromise;
  import ISelectionId = powerbi.visuals.ISelectionId;
  import ISelectionManager = powerbi.extensibility.ISelectionManager;

  class MockISelectionManager implements ISelectionManager {
      select(selectionId: ISelectionId | ISelectionId[], multiSelect?: boolean): IPromise<ISelectionId[]>;
      hasSelection(): boolean;
      clear(): IPromise<{}>;
      getSelectionIds(): ISelectionId[];
      containsSelection(id: ISelectionId): boolean;
      showContextMenu(selectionId: ISelectionId, position: IPoint): IPromise<{}>;
      registerOnSelectCallback(callback: (ids: ISelectionId[]) => void): void;
      simutateSelection(selections: ISelectionId[]): void;
  }
  ```

  - `createSelectionManager` luo ja palauttaa **ISelectionManager-** -esiintymän, itse asiassa **MockISelectionManager**-esiintymän
    ```typescript
    function createSelectionManager(): ISelectionManager
    ```

    Esimerkki
    ```typescript
    import { createSelectionManager } from "powerbi-visuals-utils-testutils";

    let selectionManager: ISelectionManager = createSelectionManager();
    ```

> [!NOTE]
> **MockISelectionManager** on **ISelectionManager**-kohteen valetoteutus, ja sitä tulee käyttää vain yksikkötesteissä.

### <a name="mockilocale"></a>MockILocale

  Määrittää aluekohtaiset asetukset ja muuttaa niitä tarpeitasi varten yksikkötestausprosessin aikana.
  ```typescript
  class MockILocale {
      constructor(locales?: Object): void; // Default locales are en-US and ru-RU 
      locale(key: string): void;// setter property
      locale(): string; // getter property
  }
  ```
  - `createLocale` luo ja palauttaa **MockILocale**-esiintymän
    ```typescript
    funciton createLocale(locales?: Object): MockILocale;
    ```

### <a name="mockitooltipservice"></a><a id="mockitooltipservice"></a> MockITooltipService
Simuloi `TooltipService`-toimintoa ja kutsuu sitä tarpeen mukaan yksikkötestausprosessin aikana.
  ```typescript
  class MockITooltipService implements ITooltipService {
      constructor(isEnabled: boolean = true);
      enabled(): boolean;
      show(options: TooltipShowOptions): void;
      move(options: TooltipMoveOptions): void;
      hide(options: TooltipHideOptions): void;
  }
  ```
  - `createTooltipService` luo ja palauttaa **MockITooltipService**-esiintymän
    ```typescript
    function createTooltipService(isEnabled?: boolean): ITooltipService;
    ```

### <a name="mockiallowinteractions"></a>MockIAllowInteractions

```typescript
export class MockIAllowInteractions {
    constructor(public isEnabled?: boolean); // false by default
}
```
  - `createAllowInteractions` luo ja palauttaa **MockIAllowInteractions**-esiintymän
    ```typescript
    function createAllowInteractions(isEnabled?: boolean): MockIAllowInteractions;
    ```

### <a name="mockilocalizationmanager"></a><a id="mockilocalizationmanager"></a> MockILocalizationManager
Sisältää **LocalizationManager**-perusominaisuudet, joita tarvitaan yksikkötestauksessa.
```typescript
class MockILocalizationManager implements ILocalizationManager {
    constructor(displayNames: {[key: string]: string});
    getDisplayName(key: string): string; // returns default or setted displayNames for localized elements
}
```
  - `createLocalizationManager` luo ja palauttaa **ILocalizationManager-** -esiintymän, itse asiassa **MockILocalizationManager**-esiintymän
    ```typescript
    function createLocalizationManager(displayNames?: any): ILocalizationManager;
    ```

    Esimerkki
    ```typescript
    import { createLocalizationManager } from "powerbi-visuals-utils-testutils";
    let localizationManagerMock: ILocalizationManager = createLocalizationManager();
    ```

### <a name="mockitelemetryservice"></a>MockITelemetryService
Simuloi **TelemetryService**-toiminnon käyttöä.
```typescript
class MockITelemetryService implements ITelemetryService {
    instanceId: string;
    trace(veType: powerbi.VisualEventType, payload?: string) {
    }
}
```
  `MockITelemetryService`-kohteen luominen
    ```typescript
    function createTelemetryService(): ITelemetryService;
    ```
### <a name="mockiauthenticationservice"></a>MockIAuthenticationService
Simuloi **AuthenticationService**-toimintoa tuottamalla testi-AAD-tunnuksen.
```typescript
class MockIAuthenticationService implements IAuthenticationService  {
    constructor(token: string);
    getAADToken(visualId?: string): powerbi.IPromise<string>
}
```
  - `createAuthenticationService` luo ja palauttaa **IAuthenticationService-** -esiintymän, itse asiassa **MockIAuthenticationService**
    ```typescript
    function createAuthenticationService(token?: string): IAuthenticationService;
    ```

### <a name="mockistorageservice"></a>MockIStorageService
Sallii sinun käyttää **ILocalVisualStorageService**-toimintoa samoin kuin **LocalStorage**-toimintoa.
```typescript
class MockIStorageService implements ILocalVisualStorageService {
  get(key: string): IPromise<string>;
  set(key: string, data: string): IPromise<number>;
  remove(key: string): void;
}
```
  - `createStorageService` luo ja palauttaa **ILocalVisualStorageService**-esiintymän, itse asiassa **MockIStorageService**-esiintymän
    ```typescript
    function createStorageService(): ILocalVisualStorageService;
    ```

### <a name="mockieventservice"></a>MockIEventService
```typescript
import powerbi from "powerbi-visuals-api";
import IVisualEventService = powerbi.extensibility.IVisualEventService;
import VisualUpdateOptions = powerbi.extensibility.VisualUpdateOptions;

class MockIEventService implements IVisualEventService {
      renderingStarted(options: VisualUpdateOptions): void;
      renderingFinished(options: VisualUpdateOptions): void;
      renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```
  - `createEventService` luo ja palauttaa **IVisualEventService**-esiintymän, itse asiassa **MockIEventService**-esiintymän
    ```typescript
    function createEventService(): IVisualEventService;
    ```

## <a name="utils"></a>Utils

Sisältää apumenetelmiä Power BI -visualisointien yksikkötestaukseen, kuten lukien väreihin, lukuihin ja tapahtumiin liittyviä apumenetelmiä.

- `renderTimeout` palauttaa aikakatkaisun
  ```typescript
  function renderTimeout(fn: Function, timeout: number = DefaultWaitForRender): number
  ```

- `testDom` auttaa asettamaan testauskehikon yksikkötesteissä
  ```typescript
  function testDom(height: number | string, width: number | string): JQuery
  ```
  Esimerkki
  ```typescript
  import { testDom }  from "powerbi-visuals-utils-testutils";
  describe("testDom", () => {
      it("should return an element", () => {
          let element: JQuery = testDom(500, 500);
          expect(element.get(0)).toBeDefined();
      });
  });
  ```

### <a name="color-related-helper-methods"></a>Väreihin liittyvät apumenetelmät

- `getSolidColorStructuralObject`
  ```typescript
  function getSolidColorStructuralObject(color: string): any
  ```
  Palauttaa seuraavan rakenteen:

  ```json
  { solid: { color: color } }
  ```

- `assertColorsMatch` vertaa syötemerkkijonosta jäsennettyjä **RgbColor**-objekteja
  ```typescript
  function assertColorsMatch(actual: string, expected: string, invert: boolean = false): boolean
  ```

- `parseColorString` jäsentää värin syötemerkkijonosta ja palauttaa sen määritettyyn liittymän **RgbColor**-objektiin
  ```typescript
  function parseColorString(color: string): RgbColor
  ```

### <a name="number-related-helper-methods"></a>Lukuihin liittyvät apumenetelmät

- `getRandomNumbers` luo satunnaisluvun minimi- ja maksimiarvojen avulla. Voit määrittää `exceptionList`-kohteen ja antaa funktion tuloksen muutosta varten.
  ```typescript
  function getRandomNumber(
      min: number,
      max: number,
      exceptionList?: number[],
      changeResult: (value: any) => number = x => x): number
  ```

- `getRandomNumbers` tuottaa satunnaislukujen taulukon, joka on muodostettu `getRandomNumber`-menetelmällä määritettyjen minimi- ja maksimiarvojen avulla
  ```typescript
  function getRandomNumbers(count: number, min: number = 0, max: number = 1): number[]
  ```

### <a name="event-related-helper-methods"></a>Tapahtumiin liittyvät apumenetelmät
Seuraavat menetelmät kirjoitetaan yksikkötesteissä tehtäviä verkkosivun tapahtumasimulointeja varten.

- `clickElement` simuloi määritetyn elementin napsauttamista
  ```typescript
  function clickElement(element: JQuery, ctrlKey: boolean = false): void
  ```

- `createTouch` palauttaa **Touch**-objektin kosketustapahtuman simulointia varten
  ```typescript
  function createTouch(x: number, y: number, element: JQuery, id: number = 0): Touch
  ```

- `createTouchesList` palauttaa luettelon simuloiduista **Touch**-tapahtumista
  ```typescript
  function createTouchesList(touches: Touch[]): TouchList
  ```

- `createContextMenuEvent` palauttaa **MouseEvent**-esiintymän
  ```typescript
  function createContextMenuEvent(x: number, y: number): MouseEvent
  ```

- `createMouseEvent` luo ja palauttaa **MouseEvent**-esiintymän
  ```typescript
  function createMouseEvent(
      mouseEventType: MouseEventType,
      eventType: ClickEventType,
      x: number,
      y: number,
      button: number = 0): MouseEvent
  ```

- `createTouchEndEvent`
  ```typescript
  function createTouchEndEvent(touchList?: TouchList): UIEvent
  ```

- `createTouchMoveEvent`
  ```typescript
  function createTouchMoveEvent(touchList?: TouchList): UIEvent
  ```

- `createTouchStartEvent`
  ```typescript
  function createTouchStartEvent(touchList?: TouchList): UIEvent
  ```

### <a name="d3-event-related-helper-methods"></a>D3-tapahtumaan liittyvät aputoiminto menetelmät

Seuraavia menetelmiä käytetään yksikkötesteissä D3-tapahtumien simulointiin.

- `flushAllD3Transitions` pakottaa kaikki D3-siirtymät suoritettaviksi loppuun

  ```typescript
  function flushAllD3Transitions()
  ```
  
  > [!NOTE]
  > Yleensä viiveettömät siirtymät suoritetaan välittömän viiveen (alle 10 ms) jälkeen, mutta tämä voi aiheuttaa lyhyen vilkkumisen, jos selain hahmontaa sivun kahdesti. Kerran ensimmäisen tapahtumasilmukan lopussa ja uudelleen heti ensimmäisen ajastimen takaisinkutsun yhteydessä.
  >
  > Välkkyminen näkyy selvimmin IE:ssä ja monissa verkkonäkymissä, eikä tätä suositella iOS:ään.
  > 
  > Tyhjentämällä ajastinjonon ensimmäisen tapahtumasilmukan lopussa voit suorittaa kaikki viiveettömät siirtymät heti ja välttää välkkymisen.

Seuraavat menetelmät ovat myös mukana:
```typescript
function d3Click(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseUp(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseDown(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseOver(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseMove(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseOut(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3KeyEvent(element: JQuery, typeArg: string, keyArg: string, keyCode: number): void
function d3TouchStart(element: JQuery, touchList?: TouchList): void
function d3TouchMove(element: JQuery, touchList?: TouchList): void
function d3TouchEnd(element: JQuery, touchList?: TouchList): void
function d3ContextMenu(element: JQuery, x: number, y: number): void
```

### <a name="helper-interfaces"></a>Aputoiminnon käyttöliittymät
Aputoiminnossa käytetään seuraavaa käyttöliittymää ja luettelointeja.

```typescript
interface RgbColor {
    R: number;
    G: number;
    B: number;
    A?: number; 
}

enum ClickEventType {
    Default = 0,
    CtrlKey = 1,
    AltKey = 2,
    ShiftKey = 4,
    MetaKey = 8,
}

enum MouseEventType {
    click,
    mousedown,
    mouseup,
    mouseover,
    mousemove,
    mouseout,
}
```

## <a name="next-steps"></a>Seuraavat vaiheet

Kun haluat kirjoittaa yksikkötestit Webpack-pohjaisia Power BI -visualisointeja varten ja yksikkötestin `karma`n ja `jasmine`n avulla, katso esimerkiksi [Opetusohjelma: Yksikkötestien lisääminen Power BI:n visualisointiprojekteihin](./unit-tests-introduction.md).
