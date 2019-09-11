---
title: Visuaaliset vuorovaikutukset Power BI:n visualisoinneissa
description: Tässä artikkelissa kerrotaan, miten voit tarkistaa, sallitaanko Power BI:n visualisoinneille visuaalisia vuorovaikutuksia.
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f2fb2d451deb63b5e9c08472654e28d0e1a469db
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236603"
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
