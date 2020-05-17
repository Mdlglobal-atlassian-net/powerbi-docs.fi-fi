---
title: Visuaalisten suodattimien ohjelmointirajapinta Power BI:n visualisoinneissa
description: Tässä artikkelissa kerrotaan, miten Power BI:n visualisoinnit voivat suodattaa muita visualisointeja.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 95e661e81e7753d0a28806cca5d652f8e92666a8
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80114102"
---
# <a name="the-visual-filters-api-in-power-bi-visuals"></a>Visuaalisten suodattimien ohjelmointirajapinta Power BI:n visualisoinneissa

Visuaalisten suodattimien ohjelmointirajapinnan avulla voit suodattaa tietoja Power BI:n visualisoinneissa. Suurin ero muihin valintoihin verrattuna on se, että muut visualisoinnit suodatetaan millä tahansa tavalla, vaikka muu visualisointi tukisi korostuksia.

Visualisoinnin suodattamisen mahdollistamiseksi sen tulee sisältää `filter`-objekti *capabilities.json*-koodin `general`-osassa.

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

Visuaalisten suodattimien ohjelmointirajapinnat ovat käytettävissä [powerbi-models](https://www.npmjs.com/package/powerbi-models)-paketissa. Paketti sisältää myös luokkia, joilla luodaan suodatinesiintymiä.

```cmd
npm install powerbi-models --save
```

Jos käytät työkalujen vanhempaa versiota (aiempi kuin 3. x. x), sisällytä `powerbi-models` visualisointipakettiin. Lisätietoja on lyhyessä oppaassa [Adding the Advanced Filter API to the custom visual](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md).

Kaikki suodattimet laajentavat `IFilter`-liittymää seuraavassa koodissa esitetyllä tavalla:

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```
Jossa:
* `target` on taulukon sarake tietolähteessä.

## <a name="the-basic-filter-api"></a>Perussuodattimen ohjelmointirajapinta

Perussuodattimen liittymä näkyy seuraavassa koodissa:

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

Jossa:
* `operator` on luettelointi arvoilla *In*, *NotIn* ja *All*.
* `values` ovat ehdon arvoja.

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

Suodatin tarkoittaa: "Anna kaikki rivit, joissa `col1` on yhtä suuri kuin arvo 1, 2 tai 3".

Vastaava SQL on:

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

Voit luoda suodattimen käyttämällä BasicFilter-luokkaa kohteessa `powerbi-models`.

Jos käytät työkalun vanhempaa versiota, sinun pitäisi saada mallien esiintymä ikkunaobjektiin käyttämällä kohdetta `window['powerbi-models']` seuraavassa koodissa esitetyllä tavalla:

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

Visualisointi käynnistää suodattimen, joka käyttää applyJsonFilter()-menetelmää isäntäliittymässä IVisualHost, joka on annettu visualisoinnille konstruktorissa.

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="the-advanced-filter-api"></a>Lisäsuodattimen ohjelmointirajapinta

[Lisäsuodattimen ohjelmointirajapinta](https://github.com/Microsoft/powerbi-models) mahdollistaa monimutkaiset visualisointien väliset arvopisteiden valinta- ja suodatuskyselyt, jotka perustuvat useihin ehtoihin, kuten*LessThan*, *Contains*, *Is* ja *IsBlank*.

Suodatin otettiin käyttöön visualisointien ohjelmointirajapinnassa 1.7.0.

Lisäsuodattimen ohjelmointirajapinnan vaatimuksia ovat myös `target` ja `table` sekä `column`-nimi. Lisäsuodattimen ohjelmointirajapinnan operaattorit ovat kuitenkin *And* ja *Or*. 

Lisäksi suodatin käyttää käyttöliittymässä ehtoja arvojen sijaan:

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

`operator`-parametrin ehto-operaattorit ovat *None*, *LessThan*, *LessThanOrEqual*, *GreaterThan*, *GreaterThanOrEqual*, *Contains*, *DoesNotContain*, *StartsWith*, *DoesNotStartWith*, *Is*, *IsNot*, *IsBlank* ja "IsNotBlank"`

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

Vastaava SQL on:

```sql
SELECT * FROM table WHERE col1 < 0;
```

Jos haluat tarkastella lisäsuodattimen ohjelmointirajapinnan täydellistä mallikoodia, siirry [Sampleslicer-visualisointivarastoon](https://github.com/Microsoft/powerbi-visuals-sampleslicer).

## <a name="the-tuple-filter-api-multi-column-filter"></a>Monikkosuodattimen ohjelmointirajapinta (monisarakesuodatin)

Monikkosuodattimen ohjelmointirajapinta otettiin käyttöön visualisointien ohjelmointirajapinnassa 2.3.0. Se muistuttaa perussuodatinta, mutta se mahdollistaa useiden sarakkeiden ja taulukoiden ehtojen määrittämisen.

Suodattimen liittymä näkyy seuraavassa koodissa: 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

Jossa:
* `target` on sarakematriisi, joissa on taulukon nimet:

    ```typescript
    declare type ITupleFilterTarget = IFilterTarget[];
    ```

  Suodatin voi käsitellä eri taulukoista peräisin olevia sarakkeita.

* `$schema` on https://powerbi.com/product/schema#tuple.

* `filterType` on *FilterType.Tuple*.

* `operator` sallii käytön vain *In*-operaattorissa.

* `values` on arvomonikkojen matriisi, ja jokainen monikko edustaa yhtä sallittua kohdesarakearvojen yhdistelmää. 

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
        // the first column combination value (or the column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for the `Team` column of the `DataTable` table
        },
        {
            value: 5 // the value for the `Value` column of the `DataTable` table
        }
    ],
    [
        // the second column combination value (or the column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "https://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

> [!IMPORTANT]
> Sarakkeiden nimien ja ehto arvojen järjestys on merkitsevä.

Vastaava SQL on:

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restore-the-json-filter-from-the-data-view"></a>JSON-suodattimen palauttaminen tietonäkymästä

Ohjelmointirajapinnan versiosta 2.2 alkaen voit palauttaa JSON-suodattimen *VisualUpdateOptions*-kohteesta seuraavassa koodissa esitetyllä tavalla:

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

Kun vaihdat kirjanmerkkiä, Power BI kutsuu visualisoinnin `update`-menetelmän, ja visualisointi saa vastaavan `filter`-objektin. Lisätietoja on artikkelissa [Kirjanmerkkien tuen lisääminen Power BI -visualisoinneille](bookmarks-support.md).

### <a name="sample-json-filter"></a>Esimerkki JSON-suodattimesta

Seuraavassa kuvassa näkyy malli JSON-suodatinkoodista:

![JSON-suodattimen koodi](media/filter-api/json-filter.png)

### <a name="clear-the-json-filter"></a>Tyhjennä JSON-suodatin

Suodattimen ohjelmointirajapinta hyväksyy suodattimen `null`-arvon *nollaukseksi* tai *tyhjentämiseksi*.

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```
