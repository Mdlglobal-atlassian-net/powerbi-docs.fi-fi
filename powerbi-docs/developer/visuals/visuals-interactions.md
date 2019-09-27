---
title: Visuaaliset vuorovaikutukset Power BI:n visualisoinneissa
description: Tässä artikkelissa kerrotaan, miten voit tarkistaa, sallitaanko Power BI:n visualisoinneille visuaalisia vuorovaikutuksia.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 0155f0fce1bc0fec5c96aef1c7e1dc9cf64b122f
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193897"
---
# <a name="visual-interactions-in-power-bi-visuals"></a>Visuaaliset vuorovaikutukset Power BI:n visualisoinneissa

Visualisoinnit voivat tehdä `allowInteractions`-merkinnän arvolle kyselyn, joka ilmaisee, tulisiko visualisoinnin sallia visualisointitoimet. Visualisoinnit ovat esimerkiksi vuorovaikutteisia raportin tarkastelun tai muokkaamisen aikana, mutta eivät silloin, kun niitä tarkastellaan koontinäytössä. Vuorovaikutteisia visualisointitoimia ovat esimerkiksi *napsautus*, *panorointi*, *zoomaus* ja *valinta*. 

> [!NOTE]
> Ota työkaluvihjeet käyttöön kaikissa skenaarioissa riippumatta siitä, mikä merkintä on olemassa.

`allowInteractions`-merkintä välitetään totuusarvona visualisoinnin valmistelun aikana IVisualHost-käyttöliittymän jäsenenä.

Missä tahansa Power BI -skenaariossa, joka edellyttää, että visualisoinnit eivät ole vuorovaikutteisia (esimerkiksi koontinäytön ruutu), `allowInteractions`-merkinnän arvo on epätosi (`false`). Muutoin (esimerkiksi raportissa), `allowInteractions`-merkinnän arvona on `true`.

Jos haluat lisätietoja, tutustu [SampleBarChart-visualisointisäilöön](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001).

```typescript
   ...
   let allowInteractions = options.host.allowInteractions;
   bars.on('click', function(d) {
       if (allowInteractions) {
           selectionManager.select(d.selectionId);
           ...
       }
   });
```
