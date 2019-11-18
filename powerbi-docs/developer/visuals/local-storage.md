---
title: Paikallisen tallennustilan ohjelmointirajapinta Power BI -visualisoinneissa
description: Artikkelissa kuvataan, miten pääset käyttämään selaimen paikallista tallennustilaa Power BI -visualisointien ohjelmointirajapinnan avulla
author: uve
ms.author: v-grniki
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 10/31/2019
ms.openlocfilehash: 3b6746b611a41ddfb471008f5aefa4f7dc391456
ms.sourcegitcommit: 8cc2b7510aae76c0334df6f495752e143a5851c4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/01/2019
ms.locfileid: "73432860"
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

Paikallisen tallennuksen ohjelmointirajapinta ei ole oletusarvoisesti aktivoitu mukautetuille visualisoinneille. Jos haluat aktivoida sen mukautetulle visualisoinnille, lähetä pyyntö Power BI:n mukautettujen visualisointien tukeen `pbicvsupport@microsoft.com`
