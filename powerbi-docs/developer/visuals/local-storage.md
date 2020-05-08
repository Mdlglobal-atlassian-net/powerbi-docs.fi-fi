---
title: Paikallisen tallennustilan ohjelmointirajapinta Power BI -visualisoinneissa
description: Artikkelissa kuvataan, miten pääset käyttämään selaimen paikallista tallennustilaa Power BI -visualisointien ohjelmointirajapinnan avulla
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 01/21/2019
ms.openlocfilehash: e2cb11ea9be85916e6b5557e7933f6a6b5a7159a
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380590"
---
# <a name="local-storage-api"></a>Paikallisen tallennustilan ohjelmointirajapinta

Paikallisen tallennustilan ohjelmointirajapinta on ohjelmointirajapinta, jonka avulla mukautettu visualisointi voi pyytää isäntää tallentamaan tai lataamaan tietoja laitteen tallennustilasta. Se on eristetty siinä mielessä, että tallennustilan käyttö on eriytetty eri visualisointityyppien välillä.

## <a name="sample"></a>Malli

Jos mukautetun visualisoinnin tulisi lisätä laskurin arvoa aina, kun päivitysmenetelmää kutsutaan, mutta laskurin arvon tulisi myös säilyä eikä nollautua aina visualisoinnin käynnistyessä:

```typescript
export class Visual implements IVisual {
        // ...
        private updateCountName: string = 'updateCount';
        private updateCount: number;
        private storage: ILocalVisualStorageService;
        // ...

        constructor(options: VisualConstructorOptions) {
            // ...
            this.storage = options.host.storageService;
            // ...

            this.storage.get(this.updateCountName).then(count =>
            {
                this.updateCount = +count;
            })
            .catch(() =>
            {
                this.updateCount = 0;
                this.storage.set(this.updateCountName, this.updateCount.toString());
            });
            // ...
        }

        public update(options: VisualUpdateOptions) {
            // ...
            this.updateCount++;
            this.storage.set(this.updateCountName, this.updateCount.toString());
            // ...
        }
}
```

## <a name="known-limitations-and-issues"></a>Tunnetut rajoitukset ja ongelmat

Paikallisen tallennuksen ohjelmointirajapinta ei ole oletusarvoisesti aktivoitu Power BI -visualisoinneille. Jos haluat aktivoida sen Power BI -visualisoinnissasi, lähetä pyyntö Power BI -visualisointien tukeen `pbicvsupport@microsoft.com`.  
**Huomaa, että visualisoinnin tulee olla käytettävissä [AppSourcessa](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) ja sen pitää olla [sertifioitu](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/).**
