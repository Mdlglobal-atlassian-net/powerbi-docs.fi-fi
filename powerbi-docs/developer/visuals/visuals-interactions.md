---
title: Visualisointitoimet
description: Miten tarkistaa, että Power BI:n visualisointi sallii visualisointitoimet
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 739e59c6da3c1e464e0462a928bc4f33ea0d01f8
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424489"
---
# <a name="visuals-interactions"></a>Visualisointitoimet

Visualisoinnit voivat tehdä allowInteractions-lipun arvolle kyselyn, joka ilmaisee, tulisiko visualisoinnin sallia visualisointitoimet.
Visualisoinnit ovat esimerkiksi vuorovaikutteisia raportin tarkastelun tai muokkaamisen aikana mutta eivät silloin, kun niitä tarkastellaan koontinäytössä.
Vuorovaikutteisia visualisointitoimia ovat muun muassa napsautus, panorointi, zoomaus ja valinta.
Huomaa, että työkaluvihjeet tulee ottaa käyttöön kaikissa tilanteissa lipusta riippumatta.

AllowInteractions-lippu välitetään totuusarvona visualisoinnin valmistelun aikana IVisualHost-käyttöliittymän jäsenenä.

Missä tahansa Power BI -skenaariossa, joka edellyttää, että visualisoinnit eivät ole vuorovaikutteisia (esimerkiksi koontinäytön ruutu), allowInteractions-lipun on arvo on epätosi (false).
Muussa tapauksessa (esimerkiksi raportissa) allowInteractions-lipun arvoksi määritetään tosi (true).

Jos haluat lisätietoja, tutustu [SampleBarChart-visualisointisäilöön](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001)

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
