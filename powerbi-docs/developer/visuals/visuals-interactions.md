---
title: Visuaaliset vuorovaikutukset Power BI:n visualisoinneissa
description: Tässä artikkelissa kerrotaan, miten voit tarkistaa, sallitaanko Power BI:n visualisoinneille visuaalisia vuorovaikutuksia.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b8b1a1a59ee9fae5a1c248548a14c5f91438edc9
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79378934"
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
