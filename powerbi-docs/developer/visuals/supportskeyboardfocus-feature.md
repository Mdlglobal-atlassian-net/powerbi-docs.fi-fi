---
title: supportsKeyboardFocus-ominaisuus
description: Tässä artikkelissa kuvataan, miten supportsKeyboardFocus-ominaisuutta käytetään Power BI -visualisoinneissa sekä siihen kohdistuvat vaatimukset.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: c8cf0f4e896b8a44764d1c363c597182f55d30b3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276509"
---
# <a name="use-the-supportskeyboardfocus-feature"></a>supportsKeyboardFocus-ominaisuuden käyttö

Tässä artikkelissa kuvataan `supportsKeyboardFocus`-ominaisuuden lisääminen Power BI -visualisointeihin.
`supportsKeyboardFocus`-ominaisuus mahdollistaa visualisoinnin arvopisteiden navigoinnin vain näppäimistöä käyttämällä.

Lisätietoja visualisointien pikanäppäinten käyttämisestä on ohjeartikkelissa [Siirtyminen näppäimistöllä](../../create-reports/desktop-accessibility-consuming-tools.md#keyboard-navigation).

## <a name="example"></a>Esimerkki

Avaa visualisointi, joka käyttää `supportsKeyboardFocus`-ominaisuutta. Valitse mikä tahansa arvopiste visualisoinnin sisältä ja valitse välilehti. Kohdistus siirtyy seuraavaan arvopisteeseen aina, kun valitset välilehden. Valitse korostettu arvopiste valitsemalla ENTER.

![Tukee näppäimistön tarkennusesimerkkiä](./media/supportskeyboardfocus-feature/supports-keyboard-focus-example.png)

## <a name="requirements"></a>Vaatimukset

Tämän ominaisuuden edellytys on API v2.1.0 tai uudempi.

Tämä ominaisuus voidaan ottaa käyttöön kaikille visualisoinneille lukuun ottamatta kuvavisualisointeja.

## <a name="usage"></a>Käyttö

Jos haluat käyttää `supportsKeyboardFocus`-ominaisuutta, lisää seuraava koodi *capabilities.json*-tiedostoon.
Tämän ominaisuuden avulla visualisointi voi vastaanottaa kohdistuksen näppäimistöllä siirtymisen kautta.

```json
    {   
            ...
        "supportsKeyboardFocus": true
            ...
    }

```

## <a name="next-steps"></a>Seuraavat vaiheet

Jos haluat lisätietoja helppokäyttötoiminnoista, lue [Helppokäyttöisten Power BI -raporttien suunnittelu](../../create-reports/desktop-accessibility-creating-reports.md).

Jos haluat kokeilla Power BI -kehittämistä, tutustu kohtaan [Power BI -visualisoinnin kehittäminen](custom-visual-develop-tutorial.md).
