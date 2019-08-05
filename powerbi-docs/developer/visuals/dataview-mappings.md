---
title: Tietonäkymän yhdistämismääritykset
description: Miten Power BI muuntaa tiedot ennen visualisointeihin välittämistä
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ff70b2f12921694617a736164484df1326471eea
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425179"
---
# <a name="data-view-mappings-in-power-bi-visuals"></a>Tietonäkymän yhdistämismääritykset Power BI -visualisoinneissa

`dataViewMappings` kuvaa, miten tietoroolit liittyvät toisiinsa, antaa sinun määrittää niille ehdollisia vaatimuksia.
Kullekin `dataMappings`-määritykselle on osio.

Jokainen kelvollinen yhdistäminen tuottaa `DataView`-näkymän, mutta tällä hetkellä tuemme vain yhden kyselyn suorittamista visualisointia kohden, joten useimmissa tilanteissa saat vain yhden `DataView`-näkymän. Voit kuitenkin antaa useita tietojen yhdistämismäärityksiä eri ehdoilla, mikä mahdollistaa seuraavan:

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "single": { ... },
        "table": { ... },
        "matrix": { ... }
    }
]
```

> [!NOTE]
> On tärkeää huomata, että Power BI luo DataView’n yhdistämismäärityksen, jos ja vain jos kelvollinen yhdistämismääritys on täytetty kohteessa `dataViewMappings`.

Toisin sanoen, jos `categorical` on määritetty kohteessa `dataViewMappings`, mutta muut yhdistämismääritykset, kuten `table`, `single` jne., eivät ole, kuten seuraavassa esimerkissä:
```json
"dataViewMappings": [
    {
        "categorical": { ... }
    }
]
```

Power BI:n tuotos on `DataView`, jolla on yksi `categorical`-yhdistämismääritys (`table` ja muut yhdistämismääritykset ovat `undefined`):
```javascript
{
    "categorical": {
        "categories": [ ... ],
        "values": [ ... ]
    },
    "metadata": { ... }
}
```

## <a name="conditions"></a>Ehdot

Kuvailee tietyn tietojen yhdistämismäärityksen ehdot. Voit antaa useita ehtojoukkoja, ja jos tiedot vastaavat jotakin kuvatuista ehtojoukoista, visualisointi hyväksyy tiedot kelvollisiksi.

Tällä hetkellä kullekin kentälle voidaan määrittää vähimmäis-ja enimmäisarvo. Se edustaa niiden kenttien määrää, jotka voidaan sitoa kyseiseen tietorooliin. 

> [!NOTE]
> Jos tietorooli jätetään pois ehdosta, sillä voi olla mikä tahansa määrä kenttiä.

### <a name="example-1"></a>Esimerkki: 1

Voit vetää useita kenttiä kuhunkin tietorooliin. Tässä esimerkissä rajoitamme luokan yhteen tietokenttään ja mittarin kahteen tietokenttään.

```json
"conditions": [
    { "category": { "max": 1 }, "y": { "max": 2 } },
]
```

### <a name="example-2"></a>Esimerkki 2

Tässä esimerkissä vaaditaan yksi kahdesta ehdosta. Joko täsmälleen yksi luokkatietokenttä ja täsmälleen kaksi mittaria tai täsmälleen kaksi luokkaa ja täsmälleen yksi mittari.

```json
"conditions": [
    { "category": { "min": 1, "max": 1 }, "measure": { "min": 2, "max": 2 } },
    { "category": { "min": 2, "max": 2 }, "measure": { "min": 1, "max": 1 } }
]
```

## <a name="single-data-mapping"></a>Yksittäistietojen yhdistäminen

Yksittäistietojen yhdistäminen on yksinkertaisin tietojen yhdistämisen muoto. Se hyväksyy yksittäisen mittarikentän ja antaa tulokseksi kokonaismäärän. Jos kenttä on numeerinen, saat tulokseksi summan. Muussa tapauksessa saat yksilöllisten arvojen määrän.

Jos haluat käyttää yksittäistietojen yhdistämistä, sinun on määritettävä sen tietoroolin nimi, jonka haluat yhdistää. Tämä yhdistäminen toimii vain yksittäisen mittarikentän kanssa. Jos toinen kenttä on määritetty, tietonäkymää ei muodosteta. Siksi kannattaa sisällyttää myös ehto, joka rajoittaa tiedot yhteen kenttään.

> [!NOTE]
> Tätä tietojen yhdistämistä ei voi käyttää yhdessä minkään muun tietojen yhdistämisen kanssa. Se on tarkoitettu muuttamaan tiedot yhdeksi numeeriseksi arvoksi.

### <a name="example-3"></a>Esimerkki 3

```json
"dataViewMappings": {
    "conditions": [
        { "Y": { "max": 1 } }
    ],
    "single": {
        "role": "Y"
    }
}  
```

Tuloksena saatava tietonäkymä sisältää yhä muita tyyppejä (table, categorical ja niin edelleen), mutta jokainen yhdistämismääritys sisältää vain single-arvon. Paras käytäntö on käyttää single-arvoa.

```JSON
{
    "dataView": [
        {
            "metadata": null,
            "categorical": null,
            "matrix": null,
            "table": null,
            "tree": null,
            "single": {
                "value": 94163140.3560001
            }
        }
    ]
}
```

## <a name="categorical-data-mapping"></a>Luokittainen tietojen yhdistäminen

Luokittaisen tietojen yhdistämisen avulla saadaan yksi tai kaksi riippumatonta tietoryhmittelyä.

### <a name="example-4"></a>Esimerkki 4

Tässä on edellisen DataRoles-esimerkkimme määritys.

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    }
]
```

Seuraavaksi yhdistäminen:

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "select": [
                { "bind": { "to": "measure" } }
            ]
        }
    }
}
```

Esimerkki on yksinkertainen. Selkeällä englannilla siinä lukee ”Map my `category` DataRole so that for every field I drag into `category`, its data is mapped to `categorical.categories`. Also map my `measure` DataRole to `categorical.values`” (Yhdistä category-DataRole niin, että jokainen kenttä, jonka vedän kohteeseen category, yhdistyy kohteeseen categorical values Yhdistä myös measure-DataRole kohteeseen categorical.values).

* **for...in** – Sisällytä kaikki tämän tietoroolin kohteet tietokyselyyn.
* **bind... to** – Tuottaa saman tuloksen kuin for...in, mutta odottaa, että DataRolella on ehto, joka rajoittaa sen yksittäiseen kenttään.

### <a name="example-5"></a>Esimerkki 5

Tässä esimerkissä käytämme kahta ensimmäistä DataRolea edellisestä esimerkistä ja lisäksi määritämme nimet `grouping` ja `measure2`.

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Grouping with",
        "name": "grouping",
        "kind": "Grouping"
    },
    {
        "displayName": "X Axis",
        "name": "measure2",
        "kind": "Grouping"
    }
]
```

Seuraavaksi yhdistämismääritys:

```json
"dataViewMappings":{
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "group": {
                "by": "grouping",
                "select":[
                    { "bind": { "to": "measure" } },
                    { "bind": { "to": "measure2" } }
                ]
            }
        }
    }
}
```

Tässä ero on siinä, miten categorical.values-yhdistämismääritys tehdään. Sanomme "Tee yhdistämismääritys tietorooleille `measure` ja `measure2`, niin että ne ryhmitellään tietoroolin `grouping` mukaan."

### <a name="example-6"></a>Esimerkki 6

Tässä on dataRoles.

```json
"dataRoles": [
    {
        "displayName": "Categories",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Measures",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Series",
        "name": "series",
        "kind": "Measure"
    }
]
```

Tässä on dataViewMapping.

```json
"dataViewMappings": [
    {
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "group": {
                    "by": "series",
                    "select": [{
                            "for": {
                                "in": "measure"
                            }
                        }
                    ]
                }
            }
        }
    }
]
```

Luokittainen `dataview` voidaan visualisoida näin.

| Luokittainen |  |  | | | |
|-----|-----|------|------|------|------|
| | Vuosi | 2013 | 2014 | 2015 | 2016 |
| Maa | | |
| Yhdysvallat | | x | x | 125 | 100 |
| Kanada | | x | 50 | 200 | x |
| Meksiko | | 300 | x | x | x |
| Iso-Britannia | | x | x | 75 | x |

Power BI luo sen sinulle luokittaisena tietonäkymänä. Se on luokkien joukko.

```JSON
{
    "categorical": {
        "categories": [
            {
                "source": {...},
                "values": [
                    "Canada",
                    "Mexico",
                    "UK",
                    "USA"
                ],
                "identity": [...],
                "identityFields": [...],
            }
        ]
    }
}
```

Jokainen luokka yhdistyy myös joukkoon arvoja. Jokainen näistä arvoista ryhmitellään sarjan, eli vuosien, mukaan.

Esimerkiksi Kanadan myynti vuonna 2013 on tyhjäarvo, Kanadan myynti 2014 on 50.

```JSON
{
    "values": [
        {
            "source": {...},
            "values": [
                null,
                300,
                null,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                50,
                null,
                150,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                200,
                null,
                null,
                125
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                null,
                null,
                null,
                100
            ],
            "identity": [...],
        }
    ]
}
```

## <a name="table-data-mapping"></a>Taulukkotietojen yhdistäminen

Taulukon tietonäkymä on yksinkertainen tietojen yhdistämismääritys. Pohjimmiltaan kyseessä on arvopisteiden luettelo, johon voidaan koota numeerisia arvopisteitä.

### <a name="example-7"></a>Esimerkki 7

Annetuilla ominaisuuksilla:

```json
"dataRoles": [
    {
        "displayName": "Values",
        "name": "values",
        "kind": "Measure"
    }
]
```

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                }
            }
        }
    }
]
```

Taulukko `dataview` voidaan visualisoida näin.  

| Maa| Vuosi | Myynti |
|-----|-----|------|
| Yhdysvallat | 2016 | 100 |
| Yhdysvallat | 2015 | 50 |
| Kanada | 2015 | 200 |
| Kanada | 2015 | 50 |
| Meksiko | 2013 | 300 |
| Iso-Britannia | 2014 | 150 |
| Yhdysvallat | 2015 | 75 |

Power BI luo sen sinulle taulukon tietonäkymänä. Älä oleta, että se on tietyssä järjestyksessä.

```JSON
{
    "table" : {
        "columns": [...],
        "rows": [
            [
                "Canada",
                2014,
                50
            ],
            [
                "Canada",
                2015,
                200
            ],
            [
                "Mexico",
                2013,
                300
            ],
            [
                "UK",
                2014,
                150
            ],
            [
                "USA",
                2015,
                100
            ],
            [
                "USA",
                2015,
                75
            ],
            [
                "USA",
                2016,
                100
            ]
        ]
    }
}
```

Tiedot voidaan koota valitsemalla haluttu kenttä ja napsauttamalla summaa.  

![Tietojen koostaminen](./media/data-aggregation.png)

## <a name="matrix-data-mapping"></a>Matriisitietojen yhdistäminen

Matriisitietojen yhdistäminen on samantapaista kuin taulukkotietojen yhdistäminen, mutta rivit esitetään hierarkkisesti. Yksi `dataRole`-arvoista voidaan käyttää sarakeotsikon arvona.

```json
{
    "dataRoles": [
        {
            "name": "Category",
            "displayName": "Category",
            "displayNameKey": "Visual_Category",
            "kind": "Grouping"
        },
        {
            "name": "Column",
            "displayName": "Column",
            "displayNameKey": "Visual_Column",
            "kind": "Grouping"
        },
        {
            "name": "Measure",
            "displayName": "Measure",
            "displayNameKey": "Visual_Values",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "matrix": {
                "rows": {
                    "for": {
                        "in": "Category"
                    }
                },
                "columns": {
                    "for": {
                        "in": "Column"
                    }
                },
                "values": {
                    "select": [
                        {
                            "for": {
                                "in": "Measure"
                            }
                        }
                    ]
                }
            }
        }
    ]
}
```

Power BI luo hierarkkisen tietorakenteen. Puun pääkansio sisältää tiedot ensimmäisestä `Category`-tietoroolin sarakkeesta ja lapset ovat tietoroolin toisesta sarakkeesta.

Tietojoukko:

| Vanhemmat | Lapset | Lapsenlapset | Sarakkeet | Arvot |
|-----|-----|------|-------|-------|
| Vanhempi1 | Lapsi1 | Lapsenlapsi1 | Sar1 | 5 |
| Vanhempi1 | Lapsi1 | Lapsenlapsi1 | Sar2 | 6 |
| Vanhempi1 | Lapsi1 | Lapsenlapsi2 | Sar1 | 7 |
| Vanhempi1 | Lapsi1 | Lapsenlapsi2 | Sar2 | 8 |
| Vanhempi1 | Lapsi2 | Lapsenlapsi3 | Sar1 | 5 |
| Vanhempi1 | Lapsi2 | Lapsenlapsi3 | Sar2 | 3 |
| Vanhempi1 | Lapsi2 | Lapsenlapsi4 | Sar1 | 4 |
| Vanhempi1 | Lapsi2 | Lapsenlapsi4 | Sar2 | 9 |
| Vanhempi1 | Lapsi2 | Lapsenlapsi5 | Sar1 | 3 |
| Vanhempi1 | Lapsi2 | Lapsenlapsi5 | Sar2 | 5 |
| Vanhempi2 | Lapsi3 | Lapsenlapsi6 | Sar1 | 1 |
| Vanhempi2 | Lapsi3 | Lapsenlapsi6 | Sar2 | 2 |
| Vanhempi2 | Lapsi3 | Lapsenlapsi7 | Sar1 | 7 |
| Vanhempi2 | Lapsi3 | Lapsenlapsi7 | Sar2 | 1 |
| Vanhempi2 | Lapsi3 | Lapsenlapsi8 | Sar1 | 10 |
| Vanhempi2 | Lapsi3 | Lapsenlapsi8 | Sar2 | 13 |

Power BI:n ydinmatriisivisualisointi hahmontaa sen kuin taulukon.

![Matriisivisualisointi](./media/matrix-visual-smaple.png)

Visualisointi saa tietorakenteen alla kuvatulla tavalla (vain kaksi ensimmäistä riviä esitetään):

```json
{
    "metadata": {...},
    "matrix": {
        "rows": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Parent1",
                        "identity": {...},
                        "childIdentityFields": [...],
                        "children": [
                            {
                                "level": 1,
                                "levelValues": [...],
                                "value": "Child1",
                                "identity": {...},
                                "childIdentityFields": [...],
                                "children": [
                                    {
                                        "level": 2,
                                        "levelValues": [...],
                                        "value": "Grand child1",
                                        "identity": {...},
                                        "values": {
                                            "0": {
                                                "value": 5 // value for Col1
                                            },
                                            "1": {
                                                "value": 6 // value for Col2
                                            }
                                        }
                                    },
                                    ...
                                ]
                            },
                            ...
                        ]
                    },
                    ...
                ]
            }
        },
        "columns": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col1",
                        "identity": {...}
                    },
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col2",
                        "identity": {...}
                    },
                    ...
                ]
            }
        },
        "valueSources": [...]
    }
}
```

## <a name="data-reduction-algorithm"></a>Tietojen vähentämisen algoritmi

`DataReductionAlgorithm` voidaan ottaa käyttöön, jos haluat hallita DataView-kohteessa vastaanotetun tiedon määrää.

Oletusarvon mukaan kaikissa mukautetuissa visualisoinneissa on käytössä top-DataReductionAlgorithm, jonka count-arvo on 1000 dataPoints. Se vastaa seuraavien ominaisuuksien määrittämistä kohteessa capabilities.json:

```json
"dataReductionAlgorithm": {
    "top": {
        "count": 1000
    }
}
```

Voit muokata count-arvoa mihin tahansa kokonaislukuarvoon, joka on enintään 30 000. R-pohjaiset mukautetut visualisoinnit voivat tukea enintään 150 000 riviä.

## <a name="data-reduction-algorithm-types"></a>Tietojen vähentämisen algoritmityypit

Käytössä on neljä erilaista `DataReductionAlgorithm`-asetusta:

* `top` – jos haluat rajoittaa tiedot arvoihin, jotka on otettu tietojoukon yläosasta. Tietojoukosta otetaan ylimmät ensimmäiset count-arvot.
* `bottom` – jos haluat rajoittaa tiedot arvoihin, jotka on otettu tietojoukon alaosasta. Tietojoukosta otetaan viimeiset count-arvot.
* `sample` -pienentää tietojoukkoa yksinkertaisella otanta-algoritmilla, joka on rajoitettu kohteiden count-luvun mukaan. Se tarkoittaa, että ensimmäiset ja viimeiset kohteet sisällytetään samoin kuin count-luvun suuruinen määrä kohteita, jotka esiintymisväli on tasainen.
Jos sinulla on esimerkiksi tietojoukko [0, 1, 2,... 100] ja `count: 9`, saat seuraavat arvot [0, 10, 20... 100]
* `window` - lataa kerrallaan yhden tietosarjan ”ikkunan”, joka sisältää count-elementtejä. Tällä hetkellä `top` ja `window` vastaavat toisiaan. Ikkunointiasetuksen täyteen tukeen tähtäävä työ on kesken.

## <a name="data-reduction-algorithm-usage"></a>Tietojen vähentämisen algoritmin käyttö

`DataReductionAlgorithm` voidaan käyttää luokittaisessa, taulukko-tai matriisi-`dataview`-yhdistämismäärityksessä.

Sille voidaan määrittää `categories` ja/tai `values`-ryhmäosalle luokittaista tietojen yhdistämistä varten.

### <a name="example-8"></a>Esimerkki 8

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" },
            "dataReductionAlgorithm": {
                "window": {
                    "count": 300
                }
            }  
        },
        "values": {
            "group": {
                "by": "series",
                "select": [{
                        "for": {
                            "in": "measure"
                        }
                    }
                ],
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 100
                    }
                }  
            }
        }
    }
}
```

Tietojen vähentämisen algoritmia voidaan käyttää taulukon `dataview`-yhdistämismäärityksen `rows`-osassa.

### <a name="example-9"></a>Esimerkki 9

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 2000
                    }
                } 
            }
        }
    }
]
```

Tietojen vähentämisen algoritmia voidaan käyttää `matrix` `dataview`-yhdistämismäärityksen `rows` ja/tai `columns`-osassa.
