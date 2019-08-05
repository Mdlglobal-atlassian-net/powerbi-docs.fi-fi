---
title: Tapahtumien hahmontaminen
description: Power BI:n visualisoinnit voivat ilmoittaa Power BI:lle, että ne ovat valmiita vientiin Power Pointiin/PDF-tiedostoon
author: Yarovinsky
ms.author: alexyar
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 46166b3503a770e033b98474fcf9240235296cc2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425087"
---
# <a name="event-service"></a>Tapahtumapalvelu

Uusi ohjelmointirajapinta koostuu kolmesta menetelmästä (aloitettu, valmis tai epäonnistunut), joita tulee kutsua hahmontamisen aikana.

Kun hahmontaminen aloitetaan, mukautettu visualisoinnin koodi kutsuu renderingStarted-menetelmää sen ilmaisemiseksi, että hahmontamisprosessi on alkanut.

Jos hahmontaminen on suoritettu onnistuneesti, mukautettu visualisoinnin koodi kutsuu välittömästi `renderingFinished`-menetelmää ilmoittaen kuuntelutoiminnoille (**ensisijaisesti Vie PDF-muotoon ja Vie PowerPointiin**), että visualisoinnin kuva on valmis.

Hahmontamisprosessin aikana saattoi ilmetä ongelma, joka estää mukautetun visualisoinnin suorittamisen onnistuneesti. Silloin mukautetun visualisoinnin koodin tulee kutsua `renderingFailed`-menetelmä ilmoittaen kuuntelutoiminnolle, että hahmontamisprosessi ei ole valmis. Tämä menetelmä tarjoaa myös valinnaisen merkkijonon virheen syylle.

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
     * Should be called just before the actual rendering was started. 
     * Usually at the very start of the update method.
     *
     * @param options - the visual update options received as update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Shoudl be called immediately after finishing successfull rendering.
     * 
     * @param options - the visual update options received as update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering failed with optional reason string
     * 
     * @param options - the visual update options received as update parameter
     * @param reason - the option failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="simple-sample-the-visual-hasnt-any-animations-on-rendering"></a>Yksinkertainen malli. Visualisoinnissa ei ole animaatioita hahmontamisen yhteydessä

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

### <a name="sample-the-visual-with-animation"></a>Malli. Animaation sisältävä visualisointi

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
            // read more https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>Tapahtumien hahmontaminen visuaalista sertifiointia varten

Visualisointitapahtumien hahmontamisen tuki on yksi visualisointien sertifioinnin edellytyksistä. Lue lisätietoja [sertifioinnin edellytyksistä](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements)
