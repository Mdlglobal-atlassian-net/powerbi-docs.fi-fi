---
title: Tapahtumien hahmontaminen Power BI:n visualisoinneissa
description: Power BI:n visualisoinnit voivat ilmoittaa Power BI:lle, että ne ovat valmiita vientiin Power Point- tai PDF-tiedostoon.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: c54aaa92f3463ce1102866c8d3b69532c8b25cf7
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380245"
---
# <a name="render-events-in-power-bi-visuals"></a>Tapahtumien hahmontaminen Power BI:n visualisoinneissa

Uusi ohjelmointirajapinta koostuu kolmesta menetelmästä (`started`, `finished` tai `failed`), joita tulee kutsua hahmontamisen aikana.

Kun hahmontaminen aloitetaan, Power BI:n visualisoinnin koodi kutsuu `renderingStarted`-menetelmää sen ilmaisemiseksi, että hahmontamisprosessi on alkanut.

Jos hahmontaminen on suoritettu onnistuneesti, Power BI:n visualisoinnin koodi kutsuu heti `renderingFinished`-menetelmää ilmoittaen kuuntelutoiminnoille (ensisijaisesti *Vie PDF-muotoon* ja *Vie PowerPointiin*), että visualisoinnin kuva on valmis vientiin.

Jos prosessin aikana ilmenee ongelma, Power BI:n visualisointia ei voida hahmontaa onnistuneesti. Silloin Power BI:n visualisoinnin koodin tulee kutsua `renderingFailed`-menetelmää ilmoittaen kuuntelutoiminnoille, että hahmontamisprosessi ei ole valmis. Tämä menetelmä tarjoaa myös valinnaisen merkkijonon virheen syyn ilmoittamista varten.

## <a name="usage"></a>Käyttö

```typescript
export interface IVisualHost extends extensibility.IVisualHost {
    eventService: IVisualEventService ;
}

/**
 * An interface for reporting rendering events
 */
export interface IVisualEventService {
    /**
     * Should be called just before the actual rendering starts, 
     * usually at the start of the update method
     *
     * @param options - the visual update options received as an update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Should be called immediately after rendering finishes successfully
     * 
     * @param options - the visual update options received as an update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering fails, with an optional reason string
     * 
     * @param options - the visual update options received as an update parameter
     * @param reason - the optional failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="sample-the-visual-displays-no-animations"></a>Malli: Visualisointi ei näytä animaatioita

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            this.events.renderingFinished(options);
        }
```

### <a name="sample-the-visual-displays-animations"></a>Malli: Visualisointi näyttää animaatioita

Jos visualisoinnissa on animaatioita tai asynkronisia funktioita hahmontamista varten, `renderingFinished`-menetelmä tulee kutsua animaation jälkeen tai asynkronisen funktion sisällä.

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        private element: HTMLElement;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            this.element = options.element;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            // Learn more at https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>Tapahtumien hahmontaminen visuaalista sertifiointia varten

Yksi visualisointien sertifioinnin edellytyksistä on visualisointitapahtumien hahmontamisen tuki. Lisätietoja on artikkelissa [Sertifioinnin edellytykset](power-bi-custom-visuals-certified.md#certification-requirements).