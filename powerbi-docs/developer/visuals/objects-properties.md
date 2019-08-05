---
title: Objekti ja ominaisuudet
description: Power BI:n visualisoinnin mukautettavat ominaisuudet
author: MrMeison
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: c22a1cfb281c9902d490e2320b85c2f6bbb63468
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424604"
---
# <a name="object-and-properties"></a>Objekti ja ominaisuudet

Objektit kuvailevat visualisointiin liittyviä mukautettavia ominaisuuksia.
Kullakin objektilla voi olla useita ominaisuuksia, ja kuhunkin ominaisuuteen liittyy tyyppi.
Tyypit viittaavat siihen, mikä ominaisuus on. Alla on lisätietoja tyypeistä.

`myCustomObject` on sisäinen nimi, jota käytetään viittaamaan objektiin `dataView`- ja `enumerateObjectInstances`-kohteen sisällä

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

## <a name="display-name"></a>Näyttönimi

`displayName` on nimi, joka näytetään ominaisuusruudussa.

## <a name="properties"></a>Ominaisuudet

`properties` on kehittäjän määrittämien ominaisuuksien kartta.

```json
"properties": {
    "myFirstProperty": {
        "displayName": "firstPropertyName",
        "type": ValueTypeDescriptor | StructuralTypeDescriptor
    }
}
```

> [!NOTE]
> `show` on erityinen ominaisuus, jonka avulla valitsin voi vaihtaa objektin.

Esimerkki:

```json
"properties": {
    "show": {
        "displayName": "My Property Switch",
        "type": {"bool": true}
    }
}
```

### <a name="property-types"></a>Ominaisuustyypit

Ominaisuustyyppejä on kahdentyyppisiä: `ValueTypeDescriptor` ja `StructuralTypeDescriptor`.

#### <a name="value-type-descriptor"></a>Arvotyyppikuvaaja

`ValueTypeDescriptor`-kuvaajat ovat enimmäkseen primitiivityyppiä, ja niitä käytetään yleensä staattisena objektina.
Seuraavassa on joitakin yleisiä `ValueTypeDescriptor`-kuvaajia

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>Rakennetyyppikuvaaja

`StructuralTypeDescriptor`-kuvaajia käytetään useimmiten tietoihin sidottuihin objekteihin.
Täyttö on yleisin `StructuralTypeDescriptor`

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>Liukuväriominaisuus

Liukuväriominaisuus on ominaisuus, jota ei voi määrittää vakio-ominaisuudeksi. Sen sijaan sinun on asetettava sääntö värinvalitsinominaisuuden (täyttötyyppi) korvaamista varten.
Katso alla olevaa esimerkkiä:

```json
"properties": {
    "showAllDataPoints": {
        "displayName": "Show all",
        "displayNameKey": "Visual_DataPoint_Show_All",
        "type": {
            "bool": true
        }
    },
    "fill": {
        "displayName": "Fill",
        "displayNameKey": "Visual_Fill",
        "type": {
            "fill": {
                "solid": {
                    "color": true
                }
            }
        }
    },
    "fillRule": {
        "displayName": "Color saturation",
        "displayNameKey": "Visual_ColorSaturation",
        "type": {
            "fillRule": {}
        },
        "rule": {
            "inputRole": "Gradient",
            "output": {
                "property": "fill",
                    "selector": [
                        "Category"
                    ]
            }
        }
    }
}
```

Kiinnitä huomiota `"fill"`-ja `"fillRule"`-ominaisuuksiin. Ensimmäinen on värinvalitsin, toinen on liukuvärin korvaussääntö, joka korvaa Fill-ominaisuuden `visually`, kun säännön ehdot täyttyvät.

Tämä yhteys Fill-ominaisuuden ja korvaussäännön välillä on määritetty `"fillRule"`-ominaisuuden `"rule"`->`"output"`-osassa.

`"Rule"`->`"InputRole"` määrittää, mikä tietorooli käynnistää säännön (ehto). Tässä esimerkissä sääntö otetaan käyttöön `"fill"`-ominaisuudelle, jos tietorooli `"Gradient"` sisältää tietoja.

Alla näkyy esimerkki tietoroolista, joka käynnistää täyttösäännön (`the last item`).

```json
{
    "dataRoles": [
            {
                "name": "Category",
                "kind": "Grouping",
                "displayName": "Details",
                "displayNameKey": "Role_DisplayName_Details"
            },
            {
                "name": "Series",
                "kind": "Grouping",
                "displayName": "Legend",
                "displayNameKey": "Role_DisplayName_Legend"
            },
            {
                "name": "Gradient",
                "kind": "Measure",
                "displayName": "Color saturation",
                "displayNameKey": "Role_DisplayName_Gradient"
            }
    ]
}
```

## <a name="enumerateobjectinstances-method"></a>`enumerateObjectInstances`-menetelmä

Jotta voit käyttää objekteja tehokkaasti, tarvitset mukautettuun visualisointiisi funktion nimeltä `enumerateObjectInstances`. Tämä funktio täyttää ominaisuusruudun objekteilla, ja se myös määrää, minne objektit sidotaan dataView-kohteessa.  

Tyypillinen asetus näyttää tältä:

```typescript
public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
    let objectName: string = options.objectName;
    let objectEnumeration: VisualObjectInstance[] = [];

    switch( objectName ) {
        case 'myCustomObject':
            objectEnumeration.push({
                objectName: objectName,
                properties: { ... },
                selector: { ... }
            });
            break;
    };

    return objectEnumeration;
}
```

### <a name="properties"></a>Ominaisuudet

Funktion `enumerateObjectInstances` ominaisuudet vastaavat toiminnoille määrittämiäsi ominaisuuksia. Katso sivun alalaidan esimerkki.

### <a name="objects-selector"></a>Objektien valitsin

Funktion `enumerateObjectInstances` valitsin määrittää, mihin kukin objekti sidotaan dataView-kohteessa. Eri vaihtoehtoja on neljä.

#### <a name="static"></a>staattinen

Tämä objekti sidotaan metatietoihin `dataviews[index].metadata.objects`

```typescript
selector: null
```

#### <a name="columns"></a>sarakkeet

Tämä objekti sidotaan sarakkeisiin, joilla on vastaava `QueryName`.

```typescript
selector: {
    metadata: 'QueryName'
}
```

#### <a name="selector"></a>valitsin

Tämä objekti on sidottu siihen elementtiin, jolle on luotu `selectionID`. Tässä esimerkissä oletamme, että olemme luoneet `selectionID`-tunnukset joillekin dataPoints-kohteille ja käymme niitä läpi.

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>Alueen identiteetti

Tämä objekti sidotaan tiettyihin arvoihin ryhmien leikkauskohdassa. Jos minulla on esimerkiksi luokat `["Jan", "Feb", "March", ...]` ja sarja `["Small", "Medium", "Large"]`, voin haluta objektin arvojen `Feb` ja `Large` leikkauskohtaan. Saan sen ottamalla molempien sarakkeista kohteen `DataViewScopeIdentity`, työntämällä ne muuttujaan `identities` ja käyttämällä tätä syntaksia valitsimen kanssa.

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>Esimerkki

Tässä esimerkissä näytämme, miltä yksi objectEnumeration näyttää, kun kyseessä on customColor-objekti, jossa on yksi ominaisuus `fill`. Haluamme, että tämä objekti sidotaan staattisesti kohteeseen `dataViews[index].metadata.objects`

```typescript
objectEnumeration.push({
    objectName: "customColor",
    displayName: "Custom Color",
    properties: {
        fill: {
            solid: {
                color: dataPoint.color
            }
        }
    },
    selector: null
});
```
