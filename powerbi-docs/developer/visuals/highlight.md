---
title: Korostaminen
description: Arvopistevalintojen korostaminen Power BI:n visualisoinneissa
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 10/31/2019
ms.openlocfilehash: a472db6c6dcc1266a11e78d72ab8465df7682042
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80114148"
---
# <a name="highlight-data-points-in-power-bi-visuals"></a>Korosta arvopisteitä Power BI:n visualisoinneissa

Oletusarvon mukaan aina, kun elementti valitaan, `values`-matriisi `dataView`-objektissa suodatetaan vain valittuihin arvoihin. Se saa kaikki muut sivun visualisoinnit näyttämään vain valitut tiedot.

![`tietonäkymän` korostaminen oletustoiminta](media/highlight/highlight-dataview.png)

Jos määrität `supportsHighlight`-ominaisuuden arvoksi `true` kohteessa `capabilities.json`, saat täyden suodattamattoman `values`-matriisin sekä `highlights`-matriisin. `highlights`-matriisi on yhtä pitkä kuin arvomatriisi, ja valitsemattomat arvot asetetaan arvoon `null`. Kun tämä ominaisuus on käytössä, on visualisoinnin vastuulla korostaa asianmukaiset tiedot vertaamalla `values`-matriisia `highlights`-matriisiin.

![`tietonäkymä` tukee korostamista](media/highlight/highlight-dataview-supports.png)

Tässä esimerkissä huomaat, että 1-palkki on valittuna. Se on korostusmatriisin ainoa arvo. On myös tärkeää huomata, että käytössä voisi olla useita valintoja ja osittaisia korostuksia. Korostetut arvot esitetään tietonäkymässä.

> [!NOTE]
> Taulukon tietonäkymän yhdistämismääritys ei tue korostusominaisuutta.

## <a name="highlight-data-points-with-categorical-data-view-mapping"></a>Korosta arvopisteet luokittaisella tietonäkymän yhdistämismäärityksellä

Visualisoinneilla, joissa on luokittainen tietonäkymän yhdistämismääritys, on `capabilities.json` parametrilla `"supportsHighlight": true`. Esimerkiksi:

```json
{
    "dataRoles": [
        {
            "displayName": "Category",
            "name": "category",
            "kind": "Grouping"
        },
        {
            "displayName": "Value",
            "name": "value",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "categorical": {
                "categories": {
                    "for": {
                        "in": "category"
                    }
                },
                "values": {
                    "for": {
                        "in": "value"
                    }
                }
            }
        }
    ],
    "supportsHighlight": true
}
```

Kun tarpeeton koodi on poistettu, oletusarvoinen visualisoinnin lähdekoodi näyttää tältä:

```typescript
"use strict";

// ... default imports list

import DataViewCategorical = powerbi.DataViewCategorical;
import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
import PrimitiveValue = powerbi.PrimitiveValue;
import DataViewValueColumn = powerbi.DataViewValueColumn;

import { VisualSettings } from "./settings";

export class Visual implements IVisual {
    private target: HTMLElement;
    private settings: VisualSettings;

    constructor(options: VisualConstructorOptions) {
        console.log('Visual constructor', options);
        this.target = options.element;
        this.host = options.host;

    }

    public update(options: VisualUpdateOptions) {
        this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
        console.log('Visual update', options);

    }

    private static parseSettings(dataView: DataView): VisualSettings {
        return <VisualSettings>VisualSettings.parse(dataView);
    }

    /**
     * This function gets called for each of the objects defined in the capabilities files and allows you to select which of the
     * objects and properties you want to expose to the users in the property pane.
     *
     */
    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstance[] | VisualObjectInstanceEnumerationObject {
        return VisualSettings.enumerateObjectInstances(this.settings || VisualSettings.getDefault(), options);
    }
}
```

Tuo pakolliset liittymät Power BI:stä tietojen käsittelyä varten:

```typescript
import DataViewCategorical = powerbi.DataViewCategorical;
import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
import PrimitiveValue = powerbi.PrimitiveValue;
import DataViewValueColumn = powerbi.DataViewValueColumn;
```

Luo päätason `div`-elementti luokan arvoille:

```typescript
export class Visual implements IVisual {
    private target: HTMLElement;
    private settings: VisualSettings;

    private div: HTMLDivElement; // new property

    constructor(options: VisualConstructorOptions) {
        console.log('Visual constructor', options);
        this.target = options.element;
        this.host = options.host;

        // create div element
        this.div = document.createElement("div");
        this.div.classList.add("vertical");
        this.target.appendChild(this.div);

    }
    // ...
}
```

Poista div-elementtien sisältö ennen uusien tietojen hahmontamista:

```typescript
// ...
public update(options: VisualUpdateOptions) {
    this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
    console.log('Visual update', options);

    while (this.div.firstChild) {
        this.div.removeChild(this.div.firstChild);
    }
    // ...
}
```

Hae luokat ja mittariarvot objektista `dataView`:

```typescript
public update(options: VisualUpdateOptions) {
    this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
    console.log('Visual update', options);

    while (this.div.firstChild) {
        this.div.removeChild(this.div.firstChild);
    }

    const dataView: DataView = options.dataViews[0];
    const categoricalDataView: DataViewCategorical = dataView.categorical;
    const categories: DataViewCategoryColumn = categoricalDataView.categories[0];
    const categoryValues = categories.values;

    const measures: DataViewValueColumn = categoricalDataView.values[0];
    const measureValues = measures.values;
    const measureHighlights = measures.highlights;
    // ...
}
```

`categoryValues` on luokan arvojen matriisi, `measureValues` on mittareiden matriisi, ja `measureHighlights` korostetut arvojen osat.

> [!NOTE]
> Ominaisuuden `measureHighlights` arvot voivat olla pienempiä kuin ominaisuuden `categoryValues` arvot.
> Tämä tarkoittaa, että arvo korostettiin osittain.

Luettele `categoryValues`-matriisi ja hae vastaavat arvot ja korostukset:

```typescript
// ...
const measureHighlights = measures.highlights;

categoryValues.forEach((category: PrimitiveValue, index: number) => {
    const measureValue = measureValues[index];
    const measureHighlight = measureHighlights && measureHighlights[index] ? measureHighlights[index] : null;
    console.log(category, measureValue, measureHighlight);

});
```

Luo elementit `div` ja `p` näyttääksesi ja visualisoidaksesi tietonäkymän arvot visuaalisessa DOMissa:

```typescript
categoryValues.forEach((category: PrimitiveValue, index: number) => {
    const measureValue = measureValues[index];
    const measureHighlight = measureHighlights && measureHighlights[index] ? measureHighlights[index] : null;
    console.log(category, measureValue, measureHighlight);

    // div element. it contains elements to display values and visualize value as progress bar
    let div = document.createElement("div");
    div.classList.add("horizontal");
    this.div.appendChild(div);

    // div element to vizualize value of measure
    let barValue = document.createElement("div");
    barValue.style.width = +measureValue * 10 + "px";
    barValue.style.display = "flex";
    barValue.classList.add("value");

    // element to display category value
    let bp = document.createElement("p");
    bp.innerText = category.toString();

    // div element to vizualize highlight of measure
    let barHighlight = document.createElement("div");
    barHighlight.classList.add("highlight")
    barHighlight.style.backgroundColor = "blue";
    barHighlight.style.width = +measureHighlight * 10 + "px";

    // element to display highlighted value of measure
    let p = document.createElement("p");
    p.innerText = `${measureHighlight}/${measureValue}`;
    barHighlight.appendChild(bp);

    div.appendChild(barValue);

    barValue.appendChild(barHighlight);
    div.appendChild(p);
});
```

Ota pakolliset tyylit käyttöön elementeille käyttääksesi `flex box`-asettelua ja määritä värit div-elementeille:

```css
div.vertical {
    display: flex;
    flex-direction: column;
}

div.horizontal {
    display: flex;
    flex-direction: row;
}

div.highlight {
    background-color: blue
}

div.value {
    background-color: red;
    display: flex;
}
```

Tuloksena pitäisi olla seuraava visualisointinäkymä.

![Visualisoinnit, joissa on luokittainen tietonäkymän yhdistämismääritys ja korostus](media/highlight/dev-categorical-visual-highlight-demo.gif)

## <a name="highlight-data-points-with-matrix-data-view-mapping"></a>Korosta arvopisteet matriisitietonäkymän yhdistämismäärityksellä

Visualisoinneilla, joissa on matriisitietonäkymän yhdistämismääritys, on `capabilities.json` parametrilla `"supportsHighlight": true`. Esimerkiksi:

```json
{
    "dataRoles": [
        {
            "displayName": "Columns",
            "name": "columns",
            "kind": "Grouping"
        },
        {
            "displayName": "Rows",
            "name": "rows",
            "kind": "Grouping"
        },
        {
            "displayName": "Value",
            "name": "value",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "matrix": {
                "columns": {
                    "for": {
                        "in": "columns"
                    }
                },
                "rows": {
                    "for": {
                        "in": "rows"
                    }
                },
                "values": {
                    "for": {
                        "in": "value"
                    }
                }
            }
        }
    ],
    "supportsHighlight": true
}
```

Mallitiedot, joilla luodaan hierarkia matriisitietonäkymän yhdistämismääritykseen:

|   Rivi1   |   Rivi2   |   Rivi3   |   Sarake1   |   Sarake2   |   Column3   |   Arvot   |
|-----|-----|------|-------|-------|-------|-------|
|   R1   |   R11   |   R111   |   C1   |   C11   |   C111   |   1   |
|   R1   |   R11   |   R112   |   C1   |   C11   |   C112   |   2   |
|   R1   |   R11   |   R113   |   C1   |   C11   |   C113   |   3   |
|   R1   |   R12   |   R121   |   C1   |   C12   |   C121   |   4   |
|   R1   |   R12   |   R122   |   C1   |   C12   |   C122   |   5   |
|   R1   |   R12   |   R123   |   C1   |   C12   |   C123   |   6   |
|   R1   |   R13   |   R131   |   C1   |   C13   |   C131   |   7   |
|   R1   |   R13   |   R132   |   C1   |   C13   |   C132   |   8   |
|   R1   |   R13   |   R133   |   C1   |   C13   |   C133   |   9   |
|   R2   |   R21   |   R211   |   C2   |   C21   |   C211   |   10   |
|   R2   |   R21   |   R212   |   C2   |   C21   |   C212   |   11   |
|   R2   |   R21   |   R213   |   C2   |   C21   |   C213   |   12   |
|   R2   |   R22   |   R221   |   C2   |   C22   |   C221   |   13   |
|   R2   |   R22   |   R222   |   C2   |   C22   |   C222   |   14   |
|   R2   |   R22   |   R223   |   C2   |   C22   |   C223   |   16   |
|   R2   |   R23   |   R231   |   C2   |   C23   |   C231   |   17   |
|   R2   |   R23   |   R232   |   C2   |   C23   |   C232   |   18   |
|   R2   |   R23   |   R233   |   C2   |   C23   |   C233   |   19   |

Luo oletusarvoinen visualisointiprojekti ja käytä `capabilities.json`-tiedoston mallia.

Kun tarpeeton koodi on poistettu, oletusarvoinen visualisoinnin lähdekoodi näyttää tältä:

```typescript
"use strict";

// ... default imports

import { VisualSettings } from "./settings";

export class Visual implements IVisual {
    private target: HTMLElement;
    private settings: VisualSettings;


    constructor(options: VisualConstructorOptions) {
        console.log('Visual constructor', options);
        this.target = options.element;
        this.host = options.host;
    }

    public update(options: VisualUpdateOptions) {
        this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
        console.log('Visual update', options);

    }

    private static parseSettings(dataView: DataView): VisualSettings {
        return <VisualSettings>VisualSettings.parse(dataView);
    }

    /**
     * This function gets called for each of the objects defined in the capabilities files and allows you to select which of the
     * objects and properties you want to expose to the users in the property pane.
     *
     */
    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstance[] | VisualObjectInstanceEnumerationObject {
        return VisualSettings.enumerateObjectInstances(this.settings || VisualSettings.getDefault(), options);
    }
}
```

Tuo pakolliset liittymät Power BI:stä tietojen käsittelyä varten:

```typescript
import DataViewMatrix = powerbi.DataViewMatrix;
import DataViewMatrixNode = powerbi.DataViewMatrixNode;
import DataViewHierarchyLevel = powerbi.DataViewHierarchyLevel;
```

Luo kaksi `div`-elementtiä visualisoinnin asettelulle:

```typescript
constructor(options: VisualConstructorOptions) {
    // ...
    this.rowsDiv = document.createElement("div");
    this.target.appendChild(this.rowsDiv);

    this.colsDiv = document.createElement("div");
    this.target.appendChild(this.colsDiv);
    this.target.style.overflowY = "auto";
}
```

Tarkista `update`-menetelmän tiedot varmistaaksesi, että visualisointi saa tietoja:

```typescript
public update(options: VisualUpdateOptions) {
    this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
    console.log('Visual update', options);

    const dataView: DataView = options.dataViews[0];
    const matrixDataView: DataViewMatrix = dataView.matrix;

    if (!matrixDataView ||
        !matrixDataView.columns ||
        !matrixDataView.rows ) {
        return
    }
    // ...
}
```

Poista `div`-elementtien sisältö ennen uusien tietojen hahmontamista:

```typescript
public update(options: VisualUpdateOptions) {
    // ...

    // remove old elements
    // to better performance use D3js pattern:
    // https://d3js.org/#enter-exit
    while (this.rowsDiv.firstChild) {
        this.rowsDiv.removeChild(this.rowsDiv.firstChild);
    }
    const prow = document.createElement("p");
    prow.innerText = "Rows";
    this.rowsDiv.appendChild(prow);

    while (this.colsDiv.firstChild) {
        this.colsDiv.removeChild(this.colsDiv.firstChild);
    }
    const pcol = document.createElement("p");
    pcol.innerText = "Columns";
    this.colsDiv.appendChild(pcol);
    // ...
}
```

Luo `treeWalker`-funktio matriisitietorakenteen ohittamiseksi:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {

    }
    // ...
}
```

`matrixNode` on nykyinen solmu, `levels` edustaa tämän hierarkiatason metatietosarakkeita, `div` on HTML-alielementtien pääelementti.

`treeWalker` on rekursiivinen funktio, jolle on luotava `div`-elementti ja `p`-otsikko tekstille, ja solmun alielementit on kutsuttava funktiolla:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {
        // ...

        if (matrixNode.children) {
            const childDiv = document.createElement("div");
            childDiv.classList.add("vertical");
            div.appendChild(childDiv);

            const p = document.createElement("p");
            const level = levels[matrixNode.level]; // get current level column metadata from current node
            p.innerText = level.sources[level.sources.length - 1].displayName; // get column name from metadata

            childDiv.appendChild(p); // add paragraph element to div element
            matrixNode.children.forEach((node, index) => treeWalker(node, levels, childDiv, ++levelIndex));
        }
    }
    // ...
}
```

Kutsu matriisitietonäkymän rakenteen sarakkeen ja rivin pääelementit funktiolla:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {
        // ...
    }
    // ...
    // remove old elements
    // ...

    // ...
    const rowRoot: DataViewMatrixNode = matrixDataView.rows.root;
    rowRoot.children.forEach((node) => treeWalker(node, matrixDataView.rows.levels, this.rowsDiv));

    const colRoot = matrixDataView.columns.root;
    colRoot.children.forEach((node) => treeWalker(node, matrixDataView.columns.levels, this.colsDiv));
}
```

Muodosta solmujen selectionID ja luo painikkeita solmujen näyttämistä varten:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {
        const selectionID: ISelectionID = this.host.createSelectionIdBuilder()
            .withMatrixNode(matrixNode, levels)
            .createSelectionId();

        let nodeBlock = document.createElement("button");
        nodeBlock.innerText = matrixNode.value.toString();

        nodeBlock.addEventListener("click", (event) => {
            // call select method in the selection manager
            this.selectionManager.select(selectionID);
        });

        nodeBlock.addEventListener("contextmenu", (event) => {
            // call showContextMenu method to display context menu on the visual
            this.selectionManager.showContextMenu(selectionID, {
                x: event.clientX,
                y: event.clientY
            });
            event.preventDefault();
        });
        // ...
    }
    // ...
}
```

Korostuksen käyttämisen tärkein vaihe on ylimääräisen arvomatriisin käsitteleminen.

Jos tarkistat päätesolmun objektin, näet, että arvomatriisissa on kaksi ominaisuutta: arvo ja korostus:

```javascript
JSON.stringify(options.dataViews[0].matrix.rows.root.children[0].children[0].children[0], null, " ");
```

```json
{
 "level": 2,
 "levelValues": [
  {
   "value": "R233",
   "levelSourceIndex": 0
  }
 ],
 "value": "R233",
 "identity": {
  "identityIndex": 2
 },
 "values": {
  "0": {
   "value": null,
   "highlight": null
  },
  "1": {
   "value": 19,
   "highlight": 19
  }
 }
}
```

`value`-ominaisuus edustaa solmun arvoa ilman, että valinta otetaan käyttöön muusta visualisoinnista, ja korostusominaisuus ilmaisee, mikä osa tiedoista korostui.

> [!NOTE]
> Ominaisuuden `highlight` arvo voi olla pienempi kuin ominaisuuden `value` arvo.
> Tämä tarkoittaa, että arvo korostettiin osittain.

Lisää koodi solmun `values`-matriisin käsittelyä varten, jos se on esitetty:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {
        // ...

        if (matrixNode.values) {
            const sumOfValues = Object.keys(matrixNode.values) // get key property of object (value are 0 to N)
                .map(key => +matrixNode.values[key].value) // convert key property to number
                .reduce((prev, curr) => prev + curr) // sum of values

            let sumOfHighlights = sumOfValues;
            sumOfHighlights = Object.keys(matrixNode.values) // get key property of object (value are 0 to N)
                .map(key => matrixNode.values[key].highlight ? +matrixNode.values[key].highlight : null ) // convert key property to number if it exists
                .reduce((prev, curr) => curr ? prev + curr : null) // convert key property to number

            // create div container for value and highlighted value
            const vals = document.createElement("div");
            vals.classList.add("vertical")
            vals.classList.replace("vertical", "horizontal");
            // create paragraph element for label
            const highlighted = document.createElement("p");
            // Display complete value and highlighted value
            highlighted.innerText = `${sumOfHighlights}/${sumOfValues}`;

            // create div container for value
            const valueDiv = document.createElement("div");
            valueDiv.style.width = sumOfValues * 10 + "px";
            valueDiv.classList.add("value");

            // create div container for highlighted values
            const highlightsDiv = document.createElement("div");
            highlightsDiv.style.width = sumOfHighlights * 10 + "px";
            highlightsDiv.classList.add("highlight");
            valueDiv.appendChild(highlightsDiv);

            // append button and paragraph to div containers to parent div
            vals.appendChild(nodeBlock);
            vals.appendChild(valueDiv);
            vals.appendChild(highlighted);
            div.appendChild(vals);
        } else {
            div.appendChild(nodeBlock);
        }

        if (matrixNode.children) {
            // ...
        }
    }
    // ...
}
```

Tuloksena saat visualisoinnin, jossa on painikkeita ja arvot `highlighted value/default value`

![Visualisointi, jossa on matriisitietonäkymän yhdistämismääritykset ja korostus](media/highlight/dev-matrix-visual-highlight-demo.gif)

## <a name="next-steps"></a>Seuraavat vaiheet

* [Lue tietonäkymän yhdistämismäärityksistä](dataview-mappings.md#matrix-data-mapping)

* [Lue visualisoinnin ominaisuuksista](capabilities.md)
