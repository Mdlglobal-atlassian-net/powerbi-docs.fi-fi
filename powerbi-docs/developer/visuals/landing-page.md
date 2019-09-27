---
title: Aloitussivun lisääminen Power BI:n visualisointeihin
description: Tässä artikkelissa kuvataan aloitussivun lisääminen Power BI:n visualisointeihin.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 79e362796e0694022bceb38f111a62bb62ddbabd
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193958"
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
