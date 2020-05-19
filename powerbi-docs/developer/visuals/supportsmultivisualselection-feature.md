---
title: supportsMultiVisualSelection-ominaisuus
description: Tässä artikkelissa kuvataan, miten supportsMultiVisualSelection-ominaisuutta käytetään Power BI -visualisoinneissa sekä siihen kohdistuvat vaatimukset.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: 6ad986308fb82f8191829d29654bb96b55d0fbd0
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83272691"
---
# <a name="use-the-supportsmultivisualselection-feature"></a>supportsMultiVisualSelection-ominaisuuden käyttö

`supportsMultiVisualSelection`-ominaisuuden avulla voit käyttää valintaa raportin useissa visualisoinneissa.

## <a name="example"></a>Esimerkki

Jos raportissa on useampi kuin yksi visualisointi, valitse kaksi arvoa, jotta nämä arvot voidaan ottaa käyttöön muissa visualisoinneissa. Valitse esimerkiksi kohdasta [Jälleenmyyntianalyysimalli](../../create-reports/sample-retail-analysis.md)**Fashions Direct** yhdessä visualisoinneista. Valitse Ctrl ja sitten **Jan** toisessa visualisoinnissa. Raportissa tekemäsi valinnat koskevat muita visualisointeja, jotka tukevat tämän ominaisuuden käyttöä. Muiden visualisointien laajuus on nyt **Fashions Direct** ja **Jan**.

## <a name="requirements"></a>Vaatimukset

Tämän ominaisuuden edellytys on API v3.2.0 tai uudempi.

Tätä ominaisuutta ei voi käyttää kuvan visualisointeihin. Et voi käyttää sitä tiettyihin edistyksellisiin visualisointeihin, kuten tärkeimpiin vaikuttajiin, hajotuspuuhun, Q&A-visualisointeihin, tekstiruutuun ja mittarikaavioihin.

## <a name="usage"></a>Käyttö

Jos haluat käyttää `supportsMultiVisualSelection`-ominaisuutta, lisää seuraava koodi visualisoinnin `capabilities.json`-tiedostoon.

```json
    {   
            ...
        "supportsMultiVisualSelection": true
            ...
    }
```

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja Power BI -käsitteistä on kohdassa [Power BI -visualisoinnit](power-bi-visuals-concept.md).

Jos haluat kokeilla Power BI -kehitystä, tutustu kohtaan [Power BI -visualisoinnin kehittäminen](custom-visual-develop-tutorial.md).
