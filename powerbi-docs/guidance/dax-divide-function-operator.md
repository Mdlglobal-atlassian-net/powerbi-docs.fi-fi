---
title: 'DAX: JAKO-funktion ja jako-operaattorin (/) vertailu'
description: Lue ohjeet DAX DIVIDE -jakofunktion käyttöön.
author: guyinacube
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/05/2019
ms.author: v-pemyer
ms.openlocfilehash: d22491ee314ebcebd4479c4e57dbfdf7a6a1ffdb
ms.sourcegitcommit: c2197c3ad1d747b4ad490ab75771a0d32d0ae208
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/23/2019
ms.locfileid: "70010433"
---
# <a name="dax-divide-function-vs-divide-operator-"></a>DAX: JAKO-funktion ja jako-operaattorin (/) vertailu

Tämä artikkeli on tarkoitettu tietojen mallintajille, jotka määrittävät DAX-lausekkeita.

## <a name="background"></a>Tausta

Kun kirjoitat DAX-lauseketta, joka jakaa osoittajan nimittäjällä, voit käyttää [DIVIDE](/dax/divide-function-dax)-jakofunktiota tai jako-operaattoria (/-vinoviivaa).

Kun käytät DIVIDE-jakofunktiota, sinun on välitettävä osoittaja- ja nimittäjälausekkeet. Voit vaihtoehtoisesti välittää arvon, joka edustaa vaihtoehtoista tulosta.

```dax

DIVIDE(<numerator>, <denominator> [,<alternateresult>])

```

DIVIDE-jakofunktio on rakennettu siten, että se käsittelee automaattisesti tilanteet, joissa jakajana on nolla. Jos vaihtoehtoista tulosta ei välitetä ja nimittäjä on nolla tai tyhjä, funktio palauttaa tyhjän arvon. Jos vaihtoehtoinen tulos välitetään, se palautetaan tyhjän sijaan.

DIVIDE-jakofunktio on kätevä, koska siinä nimittäjäarvoa ei tarvitse testata ennen käyttöä. Funktio on lisäksi optimoitu paremmin nimittäjäarvon testaamiseen kuin [IF](/dax/if-function-dax)-funktio. DIVIDE-funktion käyttäminen tuottaa myös tarkemman ja siistimmän lausekkeen.

## <a name="example"></a>Esimerkki

Seuraava mittarilauseke tuottaa turvallisen jaon, mutta siihen liittyy kolmen DAX-funktion käyttäminen.

```dax

=IF(ISBLANK([Sales]) || [Sales] = 0, BLANK(), [Profit] / [Sales])

```

Tämä mittarilauseke tuottaa saman tuloksen, mutta tehokkaammin ja tyylikkäämmin.

```dax

=DIVIDE([Profit], [Sales])

```

## <a name="recommendations"></a>Suositukset

On suositeltavaa käyttää DIVIDE-jakofunktiota aina, kun nimittäjä on lauseke, joka _voi_ palauttaa nollan tai tyhjän.

Jos nimittäjä on vakioarvo, on suositeltavaa käyttää jako-operaattoria. Tässä tapauksessa jakaminen onnistuu varmasti, ja lauseke toimii paremmin, koska se ei sisällä tarpeettomia testauksia.

Harkitse tarkkaan, tuleeko DIVIDE-jakofunktion palauttaa vaihtoehtoinen arvo. Mittareissa rakenne on yleensä parempi, kun ne voivat palauttaa tyhjän. Tämä johtuu siitä, että raporttien visualisoinnit oletusarvoisesti poistavat ryhmittelyt, kun yhteenvedot ovat tyhjiä. Tämän ansiosta visualisoinnissa voidaan painottaa ryhmiä, joissa on tietoja. Voit tarvittaessa määrittää visualisoinnin näyttämään kaikki ryhmät (jotka palauttavat arvoja tai tyhjän) suodatinkontekstissa ottamalla käyttöön asetuksen Näytä kohteet, joilla ei ole tietoja.
