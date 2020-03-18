---
title: Power BI:n visualisointien objektit ja ominaisuudet
description: Tässä artikkelissa kuvataan Power BI:n visualisoinnin mukautettavat ominaisuudet.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ae548abd0d579414a69b0d970213ff9d69ff2f08
ms.sourcegitcommit: 7e845812874b3347bcf87ca642c66bed298b244a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/13/2020
ms.locfileid: "79205868"
---
# <a name="objects-and-properties-of-power-bi-visuals"></a>Power BI:n visualisointien objektit ja ominaisuudet

Objektit kuvailevat visualisointiin liittyviä mukautettavia ominaisuuksia. Objektilla voi olla useita ominaisuuksia, ja jokaiseen ominaisuuteen liittyy tyyppi, joka kuvaa, mikä ominaisuus on. Tässä artikkelissa on tietoja objekteista ja ominaisuustyypeistä.

`myCustomObject` on sisäinen nimi, jota käytetään viittaamaan objektiin `dataView`- ja `enumerateObjectInstances`-kohteen sisällä.

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

Ominaisuustyyppejä on kaksi: `ValueTypeDescriptor` ja `StructuralTypeDescriptor`.

#### <a name="value-type-descriptor"></a>Arvotyyppikuvaaja

`ValueTypeDescriptor`-tyypit ovat enimmäkseen primitiivisiä, ja niitä käytetään yleensä staattisena objektina.

Seuraavassa on joitakin yleisiä `ValueTypeDescriptor`-elementtejä:

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>Rakennetyyppikuvaaja

`StructuralTypeDescriptor`-tyyppejä käytetään useimmiten tietoihin sidottuihin objekteihin.
Yleisin `StructuralTypeDescriptor` tyyppi on *fill*.

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>Liukuväriominaisuus

Liukuväriominaisuus on ominaisuus, jota ei voi määrittää vakio-ominaisuudeksi. Sen sijaan sinun on asetettava sääntö värinvalitsinominaisuuden (*täyttö*tyyppi) korvaamista varten.

Seuraavassa koodissa näkyy esimerkki:

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

Kiinnitä huomiota *fill*- ja *fillRule*-ominaisuuksiin. Ensimmäinen on värinvalitsin, toinen on liukuvärin korvaussääntö, joka korvaa *fill-ominaisuuden*, `visually`, kun säännön ehdot täyttyvät.

Tämä yhteys *fill*-ominaisuuden ja korvaussäännön välillä on määritetty *fillRule*-ominaisuuden `"rule"`>`"output"`-osassa.

`"Rule"`>`"InputRole"`-ominaisuus määrittää, mikä tietorooli käynnistää säännön (ehto). Tässä esimerkissä sääntö otetaan käyttöön `"fill"`-ominaisuudelle, jos tietorooli `"Gradient"` sisältää tietoja.

Seuraavassa koodissa esimerkki tietoroolista, joka käynnistää täyttösäännön (`the last item`):

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

## <a name="the-enumerateobjectinstances-method"></a>EnumerateObjectInstances-menetelmä

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

Funktion `enumerateObjectInstances` ominaisuudet vastaavat toiminnoille määrittämiäsi ominaisuuksia. Tämän artikkelin lopussa on esimerkki.

### <a name="objects-selector"></a>Objektien valitsin

Funktion `enumerateObjectInstances` valitsin määrittää, mihin jokainen objekti sidotaan dataView-kohteessa. Eri vaihtoehtoja on neljä.

#### <a name="static"></a>staattinen

Tämä objekti on sidottu metatietoihin `dataviews[index].metadata.objects`, kuten tässä on esitetty.

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

Tämä objekti on sidottu siihen elementtiin, jolle on luotu `selectionID`. Tässä esimerkissä oletetaan, että joillekin dataPoints-kohteille on luotu `selectionID`-tunnukset, ja niitä käydään läpi.

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>Alueen identiteetti

Tämä objekti sidotaan tiettyihin arvoihin ryhmien leikkauskohdassa. Jos sinulla on esimerkiksi luokat `["Jan", "Feb", "March", ...]` ja sarja `["Small", "Medium", "Large"]`, voit halutessasi sijoittaa objektin ehtoja `Feb` ja `Large` vastaavien arvojen leikkauskohtaan. Saat sen ottamalla molempien sarakkeista kohteen `DataViewScopeIdentity`, työntämällä ne muuttujaan `identities` ja käyttämällä tätä syntaksia valitsimen kanssa.

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>Esimerkki

Tässä esimerkissä näkyy, miltä yksi objectEnumeration näyttää, kun kyseessä on customColor-objekti, jossa on yksi ominaisuus *täyttö*. Haluamme, että tämä objekti sidotaan staattisesti kohteeseen `dataViews[index].metadata.objects` seuraavasti:

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
