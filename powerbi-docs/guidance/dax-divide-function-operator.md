---
title: 'DAX: JAKO-funktion ja jako-operaattorin (/) vertailu'
description: Lue ohjeet DAX DIVIDE -jakofunktion käyttöön.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: v-pemyer
ms.openlocfilehash: c20a366ef657e851ef77a9649dbcc8b66b67dac0
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74695193"
---
# <a name="dax-divide-function-vs-divide-operator-"></a>DAX: JAKO-funktion ja jako-operaattorin (/) vertailu

Kun kirjoitat tietomallintajana DAX-lauseketta, joka jakaa osoittajan nimittäjällä, voit käyttää [DIVIDE](/dax/divide-function-dax)-jakofunktiota tai jako-operaattoria (/-vinoviivaa).

Kun käytät DIVIDE-jakofunktiota, sinun on välitettävä osoittaja- ja nimittäjälausekkeet. Voit vaihtoehtoisesti välittää arvon, joka edustaa _vaihtoehtoista tulosta_.

```dax
DIVIDE(<numerator>, <denominator> [,<alternateresult>])
```

DIVIDE-jakofunktio on rakennettu siten, että se käsittelee automaattisesti tilanteet, joissa jakajana on nolla. Jos vaihtoehtoista tulosta ei välitetä ja nimittäjä on nolla tai tyhjä, funktio palauttaa tyhjän arvon. Jos vaihtoehtoinen tulos välitetään, se palautetaan tyhjän sijaan.

DIVIDE-jakofunktio on kätevä, koska siinä nimittäjäarvoa ei tarvitse testata ennen käyttöä. Funktio on lisäksi optimoitu paremmin nimittäjäarvon testaamiseen kuin [IF](/dax/if-function-dax)-funktio. Suorituskyky paranee merkittävästi, koska nollalla jakamisen tarkistaminen on vaativaa. DIVIDE-funktion jatkokäyttö tuottaa myös tarkemman ja siistimmän lausekkeen.

## <a name="example"></a>Esimerkki

Seuraava mittarilauseke tuottaa turvallisen jaon, mutta siihen liittyy neljän DAX-funktion käyttäminen.

```dax
Profit Margin =
IF(
    OR(
        ISBLANK([Sales]),
        [Sales] == 0
    ),
    BLANK(),
    [Profit] / [Sales]
)
```

Tämä mittarilauseke tuottaa saman tuloksen, mutta tehokkaammin ja tyylikkäämmin.

```dax
Profit Margin =
DIVIDE([Profit], [Sales])
```

## <a name="recommendations"></a>Suositukset

On suositeltavaa käyttää DIVIDE-jakofunktiota aina, kun nimittäjä on lauseke, joka _voi_ palauttaa nollan tai tyhjän.

Jos nimittäjä on vakioarvo, on suositeltavaa käyttää jako-operaattoria. Tässä tapauksessa jakaminen onnistuu varmasti, ja lauseke toimii paremmin, koska se ei sisällä tarpeettomia testauksia.

Harkitse tarkkaan, tuleeko DIVIDE-jakofunktion palauttaa vaihtoehtoinen arvo. Mittarien osalta on yleensä parempi suunnitella ne palauttamaan tyhjän, jos merkityksellisiä tuloksia ei voida laskea. Lisätietoja on kohdassa [Vältä tyhjien tulosten muuntamista arvoiksi](dax-avoid-converting-blank.md).

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
