---
title: Kirjanmerkit
description: Kirjanmerkkien välillä siirtyminen Power BI -visualisoinnissa
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 90e3fc73cd49a5c84a5c2acc68a8cf5e0e4aa42b
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425501"
---
# <a name="add-bookmarks-support-for-power-bi-visuals"></a>Kirjanmerkkien tuen lisääminen Power BI -visualisoinneille

Power BI -raportin kirjanmerkit mahdollistavat raporttisivun määritetyn näkymän tallentamisen, valintatilan ja visualisoinnin suodatustilan. Kirjanmerkin tukeminen ja muutoksiin reagoiminen vaatii mukautetulta visualisoinnilta kuitenkin lisätoimia.

Lue lisää kirjanmerkeistä [dokumentaatiosta](https://docs.microsoft.com/power-bi/desktop-bookmarks)

## <a name="report-bookmarks-support-in-your-visual"></a>Raportin kirjanmerkkien tuki visualisoinnissa

Jos visualisointisi on vuorovaikutuksessa muiden visualisointien kanssa, valitsee arvopisteitä tai suodattaa muita visualisointeja, sinun on palautettava tila ominaisuuksista.

## <a name="how-to-add-report-bookmarks-support"></a>Raportin kirjanmerkkien tuen lisääminen

1. Asenna (tai päivitä) vaadittu apuohjelma: `powerbi-visuals-utils-interactivityutils`(https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) versio 3.0.0 tai uudempi). Se sisältää lisäluokkia, joita voi käsitellä tilanvalitsimen tai suodattimen avulla. Se vaaditaan suodatinvisualisointeihin ja mihin tahansa visualisointiin, jossa on käytössä `InteractivityService`.

2. Päivitä visualisoinnin ohjelmointirajapinta versioon 1.11.0, niin voit käyttää kohdetta `registerOnSelectCallback` esiintymässä `SelectionManager`. Se vaaditaan visualisoinneille, joissa ei ole suodattimia ja joissa on käytössä pelkkä `SelectionManager` eikä `InteractivityService`.

### <a name="how-custom-visuals-interact-with-power-bi-in-the-report-bookmarks-scenario"></a>Miten mukautetut visualisoinnit toimivat Power BI:n kanssa raportin kirjanmerkit-skenaariossa

Katsotaan seuraavaa esimerkkiä: Käyttäjä luo useita kirjanmerkkejä raporttisivulla, niin että jokaisessa kirjanmerkissä on eri valintatila.

Ensin käyttäjä valitsee visualisoinnissasi arvopisteen. Visualisointi on vuorovaikutuksessa Power BI:n ja muiden visualisointien kanssa välittämällä valinnat isännälle. Tämän jälkeen käyttäjä valitsee vaihtoehdon Lisää kohdassa `Bookmark panel` ja Power BI tallentaa uuden kirjanmerkin senhetkiset valinnat.

Tämä toistuu useasti, kun käyttäjä muuttaa valintaa ja lisää uusia kirjanmerkkejä.
Luotuaan kirjanmerkit käyttäjä voi vaihtaa niiden välillä.

Kun käyttäjät valitsevat kirjanmerkin, Power BI palauttaa tallennetun suodattimen tai valintatilan ja välittää ne visualisointeihin. Muut visualisoinnit korostetaan tai suodatetaan kirjanmerkkiin tallennetun tilan mukaan. Power BI -isäntä vastuussa toiminnoista. Visualisointisi on vastuussa siitä, että uusi valintatila ilmenee oikein (esimerkiksi hahmonnettujen arvopisteiden värin muuttuminen).

Uusi valintatila välitetään visualisoinnille `update`-menetelmän avulla. `options`-argumentti sisältää erikoisominaisuuden: `options.jsonFilters`. Se on JSONFilter, ominaisuus, jossa voi olla `Advanced Filter` ja `Tuple Filter`.

Visualisoinnin pitäisi palauttaa suodatinarvot näyttämään vastaavaa visualisoinnin tilaa valitulle kirjanmerkille.

Voit käyttää myös vastakutsufunktiota. Kutsu ISelectionManagerin rekisteröityä `registerOnSelectCallback`-menetelmää, jos visualisointi käyttää vain valintoja.

### <a name="visuals-with-selections"></a>Valintoja sisältävät visualisoinnit

Jos visualisointisi ovat vuorovaikutuksessa muiden visualisointien kanssa käyttämällä [valintoja](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md), voit lisätä kirjanmerkkejä kahdella tavalla.

* Voit käyttää `FilterManager.restoreSelectionIds`-menetelmää, jos visualisoinnin **käytössä ei aiemmin ollut [`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** .

* Jos visualisoinnissa on käytössä **[`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** valintojen hallintaan, käytä `applySelectionFromFilter`-menetelmää esiintymässä `InteractivityService`.

#### <a name="using-iselectionmanagerregisteronselectcallback"></a>Käytössä `ISelectionManager.registerOnSelectCallback`

Kun käyttäjä napsauttaa kirjanmerkkejä, Power BI kutsuu vastaavat valinnat sisältävän visualisoinnin `callback`-menetelmän. 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

Oletetaan, että sinulla on visualisoinnissasi [`'visualTransform'`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74)-menetelmällä luotu arvopiste.

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

Joten sinulla on arvopisteinäsi `visualDataPoints` ja `ids`-matriisi on välitetty `callback`-funktioon.

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

### <a name="using-interactivityservice-for-control-selections-in-the-visual"></a>`InteractivityService`-apuohjelman käyttö valintojen hallintaan visualisoinnissa

Jos visualisointisi käytössä on `InteractivityService`, et tarvitse lisätoimintoja visualisoinnin kirjanmerkkien tukemiseksi.

Apuohjelma käsittelee visualisoinnin valintatilan, kun käyttäjä valitsee kirjanmerkkejä.

### <a name="visuals-with-filter"></a>Suodattimen sisältämät visualisoinnit

Oletetaan, että visualisointi luo tietojen suodattimen päivämääräalueen mukaan. Alueen alussa on siis `startDate` ja lopussa `endDate`.
Visualisointi luo lisäsuodatuksen ja kutsuu isäntämenetelmää `applyJsonFilter` tietojen suodattamiseksi asiaankuuluvan ehdon mukaan.
`target` on suodatustaulukko.

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

Aina, kun käyttäjä napsauttaa kirjan merkkiä, mukautettu visualisointi saa `update`-kutsun.

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

Sen jälkeen visualisoinnin pitäisi muuttaa sisäistä tilaansa – arvopisteitä ja visualisoinnin objekteja (viivoja, suorakulmioita jne.) – vastaamaan voimassa olevia ehtoja.

> [!IMPORTANT]
> Raportin kirjanmerkit -skenaariossa visualisoinnin ei pitäisi kutsua kohdetta `applyJsonFilter` muiden visualisointien suodattamiseen – Power BI on jo suodattanut ne.

Aikajanan osittajan visualisointi muuttaa alueen valitsimen vastaamaan tietoalueita.

Jos haluat lisätietoja, tutustu [aikajanan osittajan säilöön.](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df)

### <a name="filter-state-to-save-visual-properties-in-bookmarks"></a>Suodatustila kirjanmerkkien visuaalisten ominaisuuksien tallentamista varten

`filterState`-ominaisuus tekee suodatuksen osasta ominaisuuden. Visualisointi voi tallentaa kirjanmerkkeihin eri arvoja.

Jos ominaisuuden arvo halutaan tallentaa suodatustilana, objektin ominaisuudeksi on merkittävä `"filterState": true` kohteessa `capabilities.json`.

Esimerkki: `Timeline Slicer` tallentaa `Granularity`-ominaisuusarvot suodattimeen. Sen avulla nykyistä askelväliä voi muuttaa käyttäjän muuttaessa kirjanmerkkejä.

Jos haluat lisätietoja, tutustu [aikajanan osittajan säilöön](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334);
