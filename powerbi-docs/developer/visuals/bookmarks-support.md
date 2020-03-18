---
title: Kirjanmerkkien tuen lisääminen Power BI -visualisoinneille
description: Kirjanmerkkien välillä siirtyminen Power BI -visualisoinnissa
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 5bf1c79aa411788fdb3275b938e7eaad7d6014a1
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380521"
---
# <a name="add-bookmark-support-for-power-bi-visuals"></a>Kirjanmerkkien tuen lisääminen Power BI -visualisoinneille

Power BI -raportin kirjanmerkit mahdollistavat raporttisivun määritetyn näkymän tallentamisen, valintatilan ja visualisoinnin suodatustilan. Kirjanmerkin tukeminen ja muutoksiin reagoiminen vaatii Power BI -visualisoinnilta kuitenkin lisätoimia.

Lisätietoja kirjanmerkeistä on artikkelissa [Merkityksellisten tietojen jakaminen ja tarinoiden luominen Power BI:ssä kirjanmerkkien avulla](https://docs.microsoft.com/power-bi/desktop-bookmarks).

## <a name="report-bookmarks-support-in-your-visual"></a>Raportin kirjanmerkkien tuki visualisoinnissa

Jos visualisointisi on vuorovaikutuksessa muiden visualisointien kanssa, valitsee arvopisteitä tai suodattaa muita visualisointeja, sinun on palautettava tila ominaisuuksista.

## <a name="add-report-bookmarks-support"></a>Raportin kirjanmerkkien tuen lisääminen

1. Asenna (tai päivitä) tarvittava apuohjelma [powerbi-visuals-utils-interactivityutils](https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/), versio 3.0.0 tai uudempi versio. Se sisältää lisäluokkia, joita voi käsitellä tilanvalitsimen tai suodattimen avulla. Se vaaditaan suodatinvisualisointeihin ja mihin tahansa visualisointiin, jossa on käytössä `InteractivityService`.

2. Päivitä visualisointien ohjelmointirajapinta versioon 1.11.0, jotta voit käyttää kohdetta `registerOnSelectCallback``SelectionManager`-esiintymässä. Se vaaditaan visualisoinneille, joissa ei ole suodattimia ja joissa on käytössä pelkkä `SelectionManager` eikä `InteractivityService`.

### <a name="how-power-bi-visuals-interact-with-power-bi-in-report-bookmarks"></a>Power BI -visualisointien vuorovaikutus Power BI:n kanssa raportin kirjanmerkeissä

Ajatellaanpa seuraavaa skenaariota: haluat luoda raporttisivulle useita kirjanmerkkejä, joista jokaisessa on eri valintatila.

Ensin valitset visualisoinnissasi arvopisteen. Visualisointi on vuorovaikutuksessa Power BI:n ja muiden visualisointien kanssa välittämällä valinnat isännälle. Tämän jälkeen valitset **Lisää**-vaihtoehdon **Kirjanmerkki**-ruudussa, jolloin Power BI tallentaa senhetkiset valinnat uutta kirjanmerkkiä varten.

Tämä toistuu useasti, kun muutat valintaa ja lisäät uusia kirjanmerkkejä. Kun olet luonut kirjanmerkit, voit siirtyä kirjanmerkistä toiseen.

Kun valitset kirjanmerkin, Power BI palauttaa tallennetun suodattimen tai valintatilan ja välittää ne visualisointeihin. Muut visualisoinnit korostetaan tai suodatetaan kirjanmerkkiin tallennetun tilan mukaan. Power BI -isäntä vastaa toiminnoista. Visualisointisi on vastuussa siitä, että uusi valintatila ilmenee oikein (esimerkiksi hahmonnettujen arvopisteiden värin muuttuminen).

Uusi valintatila välitetään visualisoinnille `update`-menetelmän avulla. `options`-argumentti sisältää erikoisominaisuuden: `options.jsonFilters`. Se on JSONFilter, ominaisuus, jossa voi olla `Advanced Filter` ja `Tuple Filter`.

Visualisoinnin pitäisi palauttaa suodatinarvot näyttämään vastaavaa visualisoinnin tilaa valitulle kirjanmerkille. Jos visualisointi käyttää vain valintoja, voit käyttää myös vastakutsufunktiota, joka on rekisteröity ISelectionManagerin `registerOnSelectCallback`-menetelmäksi.

### <a name="visuals-with-selection"></a>Valinnan sisältävät visualisoinnit

Jos visualisointi on vuoro vaikutuksessa muiden visualisointien kanssa [Valinta](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md)-toiminnon kautta, voit lisätä kirjanmerkkejä kahdella tavalla:

* Jos visualisointi ei ole jo käyttänyt [InteractivityService](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)-palvelua, voit käyttää `FilterManager.restoreSelectionIds`-menetelmää.

* Jos visualisointi käyttää jo [InteractivityService](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)-palvelua jo valintojen hallintaan, käytä `applySelectionFromFilter`-menetelmää `InteractivityService`-esiintymällä.

#### <a name="use-iselectionmanagerregisteronselectcallback"></a>Kohteen ISelectionManager.registerOnSelectCallback käyttäminen

Kun valitset kirjanmerkin, Power BI kutsuu vastaavat valinnat sisältävän visualisoinnin `callback`-menetelmän. 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

Oletetaan, että visualisoinnissasi on arvopiste, joka on luotu [visualistransform](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74)-menetelmällä.

Ja `datapoints` näyttää tältä:

```typescript
visualDataPoints.push({
    category: categorical.categories[0].values[i],
    color: getCategoricalObjectValue<Fill>(categorical.categories[0], i, 'colorSelector', 'fill', defaultColor).solid.color,
    selectionId: host.createSelectionIdBuilder()
        .withCategory(categorical.categories[0], i)
        .createSelectionId(),
    selected: false
});
```

Nyt sinulla on arvopisteinäsi `visualDataPoints`, ja `ids`-matriisi on välitetty `callback`-funktioon.

Tässä vaiheessa visualisoinnin pitäisi verrata `ISelectionId[]`-matriisia ja `visualDataPoints`-matriisisi valintoja sekä merkitä vastaavat arvopisteet valituiksi.

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        visualDataPoints.forEach(dataPoint => {
            ids.forEach(bookmarkSelection => {
                if (bookmarkSelection.equals(dataPoint.selectionId)) {
                    dataPoint.selected = true;
                }
            });
        });
    });
);
```

Arvopisteiden päivittämisen jälkeen ne kuvastavat `filter`-objektiin tallennettua nykyistä valintatilaa. Kun arvopisteet hahmonnetaan, mukautetun visualisoinnin valintatila vastaa kirjanmerkin tilaa.

### <a name="use-interactivityservice-for-control-selections-in-the-visual"></a>InteractivityService-palvelun käyttäminen valintojen hallintaan visualisoinnissa

Jos visualisointisi käytössä on `InteractivityService`, et tarvitse lisätoimintoja visualisoinnin kirjanmerkkien tukemiseksi.

Kun valitset kirjanmerkit, apuohjelma käsittelee visualisoinnin valintatilan.

### <a name="visuals-with-a-filter"></a>Suodattimen sisältämät visualisoinnit

Oletetaan, että visualisointi luo tietojen suodattimen päivämääräalueen mukaan. Sinulla on `startDate` ja `endDate` alueen alkamis-ja päättymispäivämäärinä.

Visualisointi luo lisäsuodattimen ja kutsuu isäntämenetelmää `applyJsonFilter` tietojen suodattamiseksi asiaankuuluvan ehdon mukaan.

Kohde on suodattamiseen käytettävä taulukko.

```typescript
import { AdvancedFilter } from "powerbi-models";

const filter: IAdvancedFilter = new AdvancedFilter(
    target,
    "And",
    {
        operator: "GreaterThanOrEqual",
        value: startDate
            ? startDate.toJSON()
            : null
    },
    {
        operator: "LessThanOrEqual",
        value: endDate
            ? endDate.toJSON()
            : null
    });

this.host.applyJsonFilter(
    filter,
    "general",
    "filter",
    (startDate && endDate)
        ? FilterAction.merge
        : FilterAction.remove
);
```

Aina, kun valitse kirjanmerkin, mukautettu visualisointi saa `update`-kutsun.

Mukautetun visualisoinnin pitäisi tarkistaa objektin suodatin:

```typescript
const filter: IAdvancedFilter = FilterManager.restoreFilter(
    && options.jsonFilters
    && options.jsonFilters[0] as any
) as IAdvancedFilter;
```

Jos `filter`-objektin arvo ei ole tyhjä, visualisoinnin pitäisi palauttaa suodatusehdot objektista:

```typescript
const jsonFilters: AdvancedFilter = this.options.jsonFilters as AdvancedFilter[];

if (jsonFilters
    && jsonFilters[0]
    && jsonFilters[0].conditions
    && jsonFilters[0].conditions[0]
    && jsonFilters[0].conditions[1]
) {
    const startDate: Date = new Date(`${jsonFilters[0].conditions[0].value}`);
    const endDate: Date = new Date(`${jsonFilters[0].conditions[1].value}`);

    // apply restored conditions
} else {
    // apply default settings
}
```

Sen jälkeen visualisoinnin tulee muuttaa sisäinen tilansa nykyisten ehtojen mukaiseksi. Sisäinen tila sisältää arvopisteet ja visualisointiobjektit (kuten viivat ja suorakulmiot).

> [!IMPORTANT]
> Raportin kirjanmerkit -skenaariossa visualisoinnin ei pitäisi kutsua kohdetta `applyJsonFilter` muiden visualisointien suodattamiseen. Power BI on jo suodattanut ne.

Aikajanan osittajan visualisointi muuttaa alueen valitsimen tietoalueita vastaavaksi.

Jos haluat lisätietoja, tutustu [aikajanan osittajan säilöön.](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df)

### <a name="filter-the-state-to-save-visual-properties-in-bookmarks"></a>Kirjanmerkkien visuaalisten ominaisuuksien tallentaminen tilan suodattamisen avulla

`filterState`-ominaisuus tekee suodatuksen osasta ominaisuuden. Visualisointi voi tallentaa kirjanmerkkeihin eri arvoja.

Jos haluat tallentaa ominaisuuden arvon suodatintilaksi, merkitse objektin ominaisuuden asetukseksi `"filterState": true` tiedostossa *capabilities.json*.

Esimerkiksi Aikajanan osittaja tallentaa `Granularity`-ominaisuuden arvot suodattimeen. Sen avulla nykyinen askelväli muuttuu, kun vaihdat kirjanmerkkejä.

Jos haluat lisätietoja, tutustu [aikajanan osittajan säilöön.](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334)
