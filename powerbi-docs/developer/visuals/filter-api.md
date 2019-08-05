---
title: Visuaalisten suodattimien ohjelmointirajapinta
description: Miten Power BI -visualisoinnit voivat suodattaa muita visualisointeja
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 50e9601faf497675ebc3f24609a856a600e3bcb1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425041"
---
# <a name="power-bi-visual-filters-api"></a>Power BI:n visuaalisten suodattimien ohjelmointirajapinta

Suodatin-visualisointi sallii suodatustiedot. Suurin ero valintoihin verrattuna on se, että muut visualisoinnit suodatetaan millä tahansa tavalla, vaikka muu visualisointi tukisi korostuksia.

Visualisoinnin suodattamisen mahdollistamiseksi visualisoinnin tulee sisältää `filter`-objekti capabilities.json-sisällön `general`-osassa.

```json
"objects": {
        "general": {
            "displayName": "General",
            "displayNameKey": "formattingGeneral",
            "properties": {
                "filter": {
                    "type": {
                        "filter": true
                    }
                }
            }
        }
    }
```

Suodattimen ohjelmointirajapinnan käyttöliittymät ovat saatavilla [`powerbi-models`](https://www.npmjs.com/package/powerbi-models)-paketissa. Paketti sisältää myös luokkia, joilla luodaan suodatinesiintymiä.

```cmd
npm install powerbi-models --save
```

Jos käytät työkalujen vanhaa versiota (versio on varhaisempi kuin 3.x.x), sinun tulee sisällyttää `powerbi-models` visualisointipakettiin. [Lyhyt opas paketin sisällyttämiseen](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md)

Kaikki suodattimet laajentavat `IFilter`-liittymää.

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```

`target` - on tietolähteen taulukkosarake.

## <a name="basic-filter-api"></a>Perussuodattimen ohjelmointirajapinta

Perussuodatin liittymä on

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

`operator` - on luettelointi arvoilla "In", "NotIn", "All"

`values` - ovat ehdon arvot

Esimerkki perussuodattimesta:

```typescript
let basicFilter = {
    target: {
        column: "Col1"
    },
    operator: "In",
    values: [1,2,3]
}
```

Suodatin tarkoittaa: "Anna minulle kaikki rivit, joissa `col1` on yhtä suuri kuin yksi arvoista 1, 2 tai 3".

SQL-vastaava on

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

Voit luoda suodattimen käyttämällä BasicFilter-luokkaa kohteessa `powerbi-models`.

Jos käytät työkalujen vanhaa versiota, sinun pitäisi saada malliesiintymä window-objektissa kirjoittamalla `window['powerbi-models']`:

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

Visualisointi käynnistää suodattimen, joka käyttää menetelmää applyJsonFilter() isäntäliittymässä IVisualHost, joka on annettu visualisoinnille konstruktorissa.

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="advanced-filter-api"></a>Lisäsuodatuksen ohjelmointirajapinta

[Lisäsuodatuksen ohjelmointirajapinta](https://github.com/Microsoft/powerbi-models) mahdollistaa monimutkaiset visualisointien väliset arvopisteiden valinta- ja suodatuskyselyt useiden ehtojen perusteella (esimerkiksi "LessThan", "Contains", "Is", "IsBlank" ja niin edelleen).

Suodatin otettiin käyttöön visualisointien ohjelmointirajapinnassa 1.7.0.

Lisäsuodatuksen ohjelmointirajapinnan edellytyksenä ovat myös `target` ja `table` sekä `column`-nimi. Mutta lisäsuodatuksen ohjelmointirajapinnan operaattorit ovat `"And" | "Or"`. 

Lisäksi suodatin käyttää käyttöliittymässä ehtoja arvojen sijaan:

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

Ehto-operaattorit `operator`-parametrille ovat `"None" | "LessThan" | "LessThanOrEqual" | "GreaterThan" | "GreaterThanOrEqual" | "Contains" | "DoesNotContain" | "StartsWith" | "DoesNotStartWith" | "Is" | "IsNot" | "IsBlank" | "IsNotBlank"`

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')), // table
    column: categories.source.displayName // col1
};

let conditions: IAdvancedFilterCondition[] = [];

conditions.push({
    operator: "LessThan",
    value: 0
});

let filter: IAdvancedFilter = new window['powerbi-models'].AdvancedFilter(target, "And", conditions);

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

SQL-vastaava on

```sql
SELECT * FROM table WHERE col1 < 0;
```

Lisäsuodatuksen ohjelmointirajapinnan koko mallikoodi on [`Sampleslicer visual`-säilössä](https://github.com/Microsoft/powerbi-visuals-sampleslicer).

## <a name="tuple-filter-api-multi-column-filter"></a>Monikkosuodattimen ohjelmointirajapinta (monisarakesuodatin)

Monikkosuodattimen ohjelmointirajapinta otettiin käyttöön visualisointien ohjelmointirajapinnassa 2.3.0.

Monikkosuodattimen ohjelmointirajapinta muistuttaa perussuodatinta, mutta se sallii useiden sarakkeiden ja taulukoiden ehtojen määrittämisen.

Suodattimella on myös liittymä: 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

`target` on sarakematriisi, joissa on taulukon nimet:

```typescript
declare type ITupleFilterTarget = IFilterTarget[];
```

  Suodatin voi käsitellä eri taulukoista peräisin olevia sarakkeita.

`$schema` on "http://powerbi.com/product/schema#tuple"

`filterType` on `FilterType.Tuple`

`operator` sallii vain `"In"`-operaattorin käytön

`values` on arvomonikkojen matriisi, jossa kukin monikko edustaa yhtä sallittua kohdesarakearvojen yhdistelmää 

```typescript
declare type TupleValueType = ITupleElementValue[];

interface ITupleElementValue {
    value: PrimitiveValueType
}
```

Täydellinen esimerkki:

```typescript
let target: ITupleFilterTarget = [
    {
        table: "DataTable",
        column: "Team"
    },
    {
        table: "DataTable",
        column: "Value"
    }
];

let values = [
    [
        // the 1st column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for `Team` column of `DataTable` table
        },
        {
            value: 5 // the value for `Value` column of `DataTable` table
        }
    ],
    [
        // the 2nd column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "http://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

**Sarakkeiden nimien ja ehtoarvojen järjestys on merkitsevä.**

Vastaava SQL on

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restoring-json-filter-from-dataview"></a>JSON-suodattimen palautus DataView-kohteesta

Ohjelmointirajapinnasta 2.2 alkaen **JSON-suodattimet** voidaan palauttaa kohteesta **VisualUpdateOptions**

```typescript
export interface VisualUpdateOptions extends extensibility.VisualUpdateOptions {
    viewport: IViewport;
    dataViews: DataView[];
    type: VisualUpdateType;
    viewMode?: ViewMode;
    editMode?: EditMode;
    operationKind?: VisualDataChangeOperationKind;
    jsonFilters?: IFilter[];
}
```

Power BI kutsuu visualisoinnin `update`-menetelmän, kun käyttäjä vaihtaa kirjanmerkkejä ja visualisointi saa vastaavan `filter`-objektin.
[Lue lisää kirjanmerkkien tuesta](bookmarks-support.md)

### <a name="sample-json-filter"></a>Esimerkki JSON-suodattimesta

![Näyttökuva JSON-suodattimesta](./media/json-filter.png)

### <a name="clear-json-filter"></a>Tyhjennä JSON-suodatin

Suodattimen ohjelmointirajapinta hyväksyy nollaukseksi tai tyhjentämiseksi suodattimen `null`-arvon.

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```
