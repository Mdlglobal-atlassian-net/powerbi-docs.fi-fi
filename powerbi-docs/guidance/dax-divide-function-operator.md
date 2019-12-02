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
ms.openlocfilehash: 91acaa3a2252250e2a10674bae0e9be81f142696
ms.sourcegitcommit: f1f57c5bc6ea3057007ed8636ede50188ed90ce1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/23/2019
ms.locfileid: "74410925"
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

Harkitse tarkkaan, tuleeko DIVIDE-jakofunktion palauttaa vaihtoehtoinen arvo. Mittareissa rakenne on yleensä parempi, kun ne voivat palauttaa tyhjän. Tyhjän palauttaminen parempaa, koska raporttien visualisoinnit oletusarvoisesti poistavat ryhmittelyt, kun yhteenvedot ovat tyhjiä. Tämän ansiosta visualisoinnissa voidaan painottaa ryhmiä, joissa on tietoja. Voit tarvittaessa määrittää visualisoinnin näyttämään kaikki ryhmät (jotka palauttavat arvoja tai tyhjän) suodatinkontekstissa ottamalla käyttöön asetuksen Näytä kohteet, joilla ei ole tietoja.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
