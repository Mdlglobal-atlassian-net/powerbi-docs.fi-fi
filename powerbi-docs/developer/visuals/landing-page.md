---
title: Aloitussivun lisääminen Power BI:n visualisointeihin
description: Tässä artikkelissa kuvataan aloitussivun lisääminen Power BI:n visualisointeihin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: fdf9496c564372e385879b3e0a3feb392d10ff90
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879973"
---
# <a name="add-a-landing-page-to-your-power-bi-visuals"></a>Aloitussivun lisääminen Power BI:n visualisointeihin

Ohjelmointirajapinnan versiossa 2.3.0 voit lisätä aloitussivun Power BI:n visualisointeihin. Kun haluat tehdä sen, lisää ominaisuuksiin `supportsLandingPage` ja määritä sen arvoksi tosi (true). Tämä toiminto alustaa visualisoinnin ja päivittää sen, ennen kuin lisäät siihen tietoja. Koska visualisointi ei enää näytä vesileimaa, voit näyttää visualisoinnissa itse suunnittelemasi aloitussivun, kunhan sillä ei ole tietoja.

```typescript
export class BarChart implements IVisual {
    //...
    private element: HTMLElement;
    private isLandingPageOn: boolean;
    private LandingPageRemoved: boolean;
    private LandingPage: d3.Selection<any>;

    constructor(options: VisualConstructorOptions) {
            //...
            this.element = options.element;
            //...
    }

    public update(options: VisualUpdateOptions) {
    //...
        this.HandleLandingPage(options);
    }

    private HandleLandingPage(options: VisualUpdateOptions) {
        if(!options.dataViews || !options.dataViews.length) {
            if(!this.isLandingPageOn) {
                this.isLandingPageOn = true;
                const SampleLandingPage: Element = this.createSampleLandingPage(); //create a landing page
                this.element.appendChild(SampleLandingPage);
                this.LandingPage = d3.select(SampleLandingPage);
            }

        } else {
                if(this.isLandingPageOn && !this.LandingPageRemoved){
                    this.LandingPageRemoved = true;
                    this.LandingPage.remove();
                }
        }
    }
```

Seuraavassa kuvassa näkyy esimerkki aloitussivusta:

![näyttökuva aloitussivusta](./media/landing-page.png)
