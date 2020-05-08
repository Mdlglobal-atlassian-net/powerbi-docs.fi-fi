---
title: Suuren kontrastin tila Power BI:n visualisoinneissa
description: Tässä artikkelissa kuvataan suuren kontrastin tilan tuen lisääminen Power BI:n visualisointeihin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9372187ae1fdfac27f6b3e7267a1c0622c063464
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80114332"
---
# <a name="high-contrast-mode-support-in-power-bi-visuals"></a>Suuren kontrastin tila Power BI:n visualisoinneissa

Windowsin *suuren kontrastin* asetus helpottaa tekstin ja sovellusten näkemistä käyttämällä selkeämpiä värejä. Tässä artikkelissa kuvataan suuren kontrastin tilan tuen lisääminen Power BI:n visualisointeihin. Lisätietoja on artikkelissa [suuren kontrastin tuki Power BI:ssä](https://powerbi.microsoft.com/blog/power-bi-desktop-june-2018-feature-summary/#highContrast).

Jos haluat tarkastella suuren kontrastin tuen toteutusta, siirry [PowerBI-visuals-sampleBarChart-visualisoinnin säilöön](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/61011c82b66ca0d3321868f1d089c65101ca42e6).

## <a name="on-initialization"></a>Valmistelusta

`options.host`-objektin ColorPalette-jäsenellä on useita ominaisuuksia suuren kontrastin tilassa. Näiden ominaisuuksien avulla voit määrittää, onko suuren kontrastin tila aktiivinen, ja jos on, mitä värejä käytetään.

### <a name="detect-that-power-bi-is-in-high-contrast-mode"></a>Tunnista, että Power BI on suuren kontrastin tilassa

Jos `host.colorPalette.isHighContrast`-objektin arvona on `true`, suuren kontrastin tila on aktiivinen ja visualisoinnin pitäisi piirtää itsensä sen mukaisesti.

### <a name="get-high-contrast-colors"></a>Hanki suuren kontrastin värejä

Suuren kontrastin tilassa visualisoinnin tulee rajoittua seuraaviin asetuksiin:

* **Edustan** värillä piirretään viivoja, kuvakkeita, tekstiä, ääriviivoja tai täytetään muotoja.
* **Taustan** väriä käytetään taustassa ja korostettujen muotojen täyttövärinä.
* **Edusta – valittu** -väriä käytetään osoittamaan valittua tai aktiivista elementtiä.
* **Hyperlinkin** väriä käytetään vain hyperlinkkitekstissä.

> [!NOTE]
> Jos toissijaista väriä tarvitaan, edustan väriä voidaan käyttää pienellä peittävyydellä (Power BI:n alkuperäisissä visualisoinneissa peittävyys on 40 %). Käytä tätä säästeliäästi, jotta visualisoinnin tiedot on helppo nähdä.

Voit valmistelun aikana tallentaa seuraavat arvot:

```typescript
private isHighContrast: boolean;

private foregroundColor: string;
private backgroundColor: string;
private foregroundSelectedColor: string;
private hyperlinkColor: string;
//...

constructor(options: VisualConstructorOptions) {
    this.host = options.host;
    let colorPalette: ISandboxExtendedColorPalette = host.colorPalette;
    //...
    this.isHighContrast = colorPalette.isHighContrast;
    if (this.isHighContrast) {
        this.foregroundColor = colorPalette.foreground.value;
        this.backgroundColor = colorPalette.background.value;
        this.foregroundSelectedColor = colorPalette.foregroundSelected.value;
        this.hyperlinkColor = colorPalette.hyperlink.value;
    }
```

Voit myös tallentaa `host`-objektin alustuksen aikana ja käyttää asianmukaisia `colorPalette`-ominaisuuksia päivityksen aikana.

## <a name="on-update"></a>Päivityksen yhteydessä

Suuren kontrastin tuen tarkat toteutukset vaihtelevat visualisoinnista toiseen ja riippuvat graafisen suunnittelun yksityiskohdista. Suuren kontrastin tila vaatii yleensä oletusmallista hieman poikkeavan mallin, jotta tärkeät tiedot on helppo erottaa rajoitetuilla väreillä.

Power BI:n alkuperäiset visualisoinnit noudattavat näitä ohjeita:

* Kaikissa arvopisteissä käytetään samaa väriä (edusta).
* Esimerkiksi kaikki tekstit, akselit, nuolet ja viivat käyttävät edustaväriä.
* Paksut muodot piirretään ääriviivoina, ja niissä on paksut viivat (vähintään kaksi kuvapistettä) ja taustavärin täyttö.
* Tarvittaessa arvopisteet erotetaan toisistaan erilaisilla merkintämuodoilla ja tietoviivat erilaisilla viivoilla.
* Kun tietoelementti korostetaan, kaikkien muiden elementtien peittävyydeksi tulee 40 %.
* Osittajien kohdalla aktiiviset suodatuselementit käyttävät edustavalittua väriä.

Seuraavassa esimerkkipalkkikaaviossa kaikki palkit on piirretty käyttäen kahden kuvapisteen paksuista edustan ääriviivaa ja taustan täyttöä. Vertaa sen ulkoasua, kun käytössä ovat oletusvärit sekä muutama suuren kontrastin teema:

![Esimerkkipalkkikaavio vakioväreillä](media/high-contrast-support/hc-samplebarchart-standard.png)
![Esimerkkipalkkikaavio *Tumma 2* -väriteemalla](media/high-contrast-support/hc-samplebarchart-dark2.png)
![Esimerkkipalkkikaavio *Valkoinen*-väriteemalla](media/high-contrast-support/hc-samplebarchart-white.png)

Seuraavassa osassa näkyy yksi kohta `visualTransform`-toiminnossa, joka on muutettu tukemaan suurta kontrastia. Sitä kutsutaan osana hahmonnusta päivityksen aikana.

### <a name="before"></a>Ennen

```typescript
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    let defaultColor: Fill = {
        solid: {
            color: colorPalette.getColor(category.values[i] + '').value
        }
    };

    barChartDataPoints.push({
        category: category.values[i] + '',
        value: dataValue.values[i],
        color: getCategoricalObjectValue<Fill>(category, i, 'colorSelector', 'fill', defaultColor).solid.color,
        selectionId: host.createSelectionIdBuilder()
            .withCategory(category, i)
            .createSelectionId()
    });
}
```

### <a name="after"></a>Jälkeen

```typescript
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    const color: string = getColumnColorByIndex(category, i, colorPalette);

    const selectionId: ISelectionId = host.createSelectionIdBuilder()
        .withCategory(category, i)
        .createSelectionId();

    barChartDataPoints.push({
        color,
        strokeColor,
        strokeWidth,
        selectionId,
        value: dataValue.values[i],
        category: `${category.values[i]}`,
    });
}

//...

function getColumnColorByIndex(
    category: DataViewCategoryColumn,
    index: number,
    colorPalette: ISandboxExtendedColorPalette,
): string {
    if (colorPalette.isHighContrast) {
        return colorPalette.background.value;
    }

    const defaultColor: Fill = {
        solid: {
            color: colorPalette.getColor(`${category.values[index]}`).value,
        }
    };

    return getCategoricalObjectValue<Fill>(category, index, 'colorSelector', 'fill', defaultColor).solid.color;
}
```
