---
title: Ominaisuudet
description: Power BI:n visualisointien toiminnot ja ominaisuudet
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f6bb4293a44f98f2f8098fb197c7b406b618d211
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425455"
---
# <a name="power-bi-visual-capabilities"></a>Power BI:n visualisoinnin toiminnot

Toiminnot antavat tietoja visualisoinnistasi isännälle. Kaikki toimintomallin ominaisuudet ovat `optional`

Visualisoinnin toimintojen juuriobjektit ovat `dataRoles`, `dataViewMappings` ja niin edelleen.

```json
{
    "dataRoles": [ ... ],
    "dataViewMappings": [ ... ],
    "objects":  { ... },
    "supportsHighlight": true|false,
    "advancedEditModeSupport": 0|1|2,
    "sorting": { ... }
}

```

## <a name="define-the-data-fields-your-visual-expects---dataroles"></a>Määritä visualisoinnin odottamat tietokentät – `dataRoles`

Tietoihin sidottavien kenttien määrittämiseen käytössä on `dataRoles`, jossa on `DataViewRole`-objektimatriisi, joka määrittää kaikki tarvittavat ominaisuudet.

### <a name="properties"></a>Ominaisuudet

* **name** – tämän tietokentän sisäinen nimi (oltava yksilöivä)
* **kind** – kentän tyyppi:
    * `Grouping` -Mittarikenttien ryhmittelyssä käytettävät erilliset arvot
    * `Measure` – Numeeriset tietoarvot
    * `GroupingOrMeasure` – Voidaan käyttää joko ryhmittelynä tai mittarina
* **displayName** – nimi, joka näytetään käyttäjälle ominaisuudet-ruudussa
* **description** – kentän lyhyt kuvaus (valinnainen)
* **requiredTypes** – tämän tietoroolin vaadittu tietotyyppi. Kaikki arvot, jotka eivät täsmää, määritetään null-arvoisiksi (valinnainen)
* **preferredTypes** – tämän tietoroolin ensisijainen tietotyyppi (valinnainen)

### <a name="valid-data-types-in-requiredtypes-and-preferredtypes"></a>Kelvolliset tietotyypit kohteissa "requiredTypes" ja "preferredTypes"

* **bool** – totuusarvo
* **integer** – kokonaislukuarvo
* **numeric** – numeerinen arvo
* **text** – tekstiarvo
* **geography** – maantieteelliset tiedot

### <a name="example"></a>Esimerkki

```json
"dataRoles": [
    {
        "displayName": "My Category Data",
        "name": "myCategory",
        "kind": "Grouping",
        "requiredTypes": [
            {
                "text": true
            },
            {
                "numeric": true
            },
            {
                "integer": true
            }
        ],
        "preferredTypes": [
            {
                "text": true
            }
        ]
    },
    {
        "displayName": "My Measure Data",
        "name": "myMeasure",
        "kind": "Measure",
        "requiredTypes": [
            {
                "integer": true
            },
            {
                "numeric": true
            }
        ],
        "preferredTypes": [
            {
                "integer": true
            }
        ]
    },
    {
        "displayNameKey": "Visual_Location",
        "name": "Locations",
        "kind": "Measure",
        "displayName": "Locations",
        "requiredTypes": [
            {
                "geography": {
                    "address": true
                }
            },
            {
                "geography": {
                    "city": true
                }
            },
            {
                "geography": {
                    "continent": true
                }
            },
            {
                "geography": {
                    "country": true
                }
            },
            {
                "geography": {
                    "county": true
                }
            },
            {
                "geography": {
                    "place": true
                }
            },
            {
                "geography": {
                    "postalCode": true
                }
            },
            {
                "geography": {
                    "region": true
                }
            },
            {
                "geography": {
                    "stateOrProvince": true
                }
            }
        ]
    }
]
```

Yllä olevat tietoroolit luovat seuraavat kentät

![Tietorooli näkyvissä](./media/data-role-display.png)

## <a name="define-how-you-want-the-data-mapped---dataviewmappings"></a>Määritä, miten haluat yhdistää tiedot – `dataViewMappings`

DataViewMapping kuvaa, miten tietoroolit liittyvät toisiinsa, antaa sinun määrittää niille ehdollisia vaatimuksia.

Useimmat visualisoinnit tarjoavat yhden yhdistämismäärityksen, mutta voit tehdä useita dataViewMapping-määrityksiä. Jokainen kelvollinen yhdistämismääritys tuottaa DataView’n. 

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "table": { ... },
        "single": { ... },
        "matrix": { ... }
    }
]
```

[Lue lisätietoja DataViewMappings-määrityksistä](dataview-mappings.md)

## <a name="define-property-pane-options---objects"></a>Määritä ominaisuusruudun asetukset – `objects`

Objektit kuvailevat visualisointiin liittyviä mukautettavia ominaisuuksia.
Kullakin objektilla voi olla useita ominaisuuksia, ja kuhunkin ominaisuuteen liittyy tyyppi.
Tyypit viittaavat siihen, mikä ominaisuus on. Alla on lisätietoja tyypeistä.

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

[Lue lisätietoja objekteista](objects-properties.md)

## <a name="handle-partial-highlighting---supportshighlight"></a>Käsittele osittainen korostus – `supportsHighlight`

Oletusarvon mukaan tämä arvo on epätosi (false), mikä tarkoittaa, että "Values" suodatetaan automaattisesti, kun sivulla valitaan jotain, mikä puolestaan päivittää visualisoinnin näyttämään vain valitun arvon. Jos haluat näyttää täydelliset tiedot mutta korostaa vain valitut kohteet, sinun on asetettava `supportsHighlight`-arvoksi tosi (true) tiedostossa capabilities.json.

[Lue lisätietoja korostuksen käyttämisestä](highlight.md)

## <a name="handle-advanced-edit-mode---advancededitmodesupport"></a>Muokkaustilan lisäasetukset – `advancedEditModeSupport`

Visualisointi voi ilmaista tukensa muokkaustilan lisäasetuksia kohtaan.
Visualisointi ei oletusarvoisesti tue muokkaustilan lisäasetuksia, ellei tiedostossa capabilities.json ole toisin mainittu.

[Lue lisätietoja kohteesta advancedEditModeSupport](advanced-edit-mode.md)

## <a name="data-sorting-options-for-visual---sorting"></a>Visualisoinnin tietojen lajittelun asetukset – `sorting`

Visualisointi voi määrittää lajittelukäyttäytymisensä toimintojensa avulla.
Visualisointi ei oletusarvoisesti tue lajittelujärjestyksen muokkaamista, ellei tiedostossa capabilities.json ole toisin mainittu.

[Lisätietoja lajittelusta](sort-options.md)
