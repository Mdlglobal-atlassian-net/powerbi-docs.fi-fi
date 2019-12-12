---
title: 'DAX: Käytä COUNTROWS-kohdetta COUNT-kohteen sijaan'
description: Lue ohjeet COUNTROWS-virhefunktioiden käyttöön.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/23/2019
ms.author: v-pemyer
ms.openlocfilehash: fd3b50e9016298db8b692d6a2f3549b770f143e8
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700658"
---
# <a name="dax-use-countrows-instead-of-count"></a>DAX: Käytä COUNTROWS-kohdetta COUNT-kohteen sijaan

Tietomallinnuksena saatat joskus joutua kirjoittamaan DAX-lausekkeen, joka laskee taulukon rivit. Taulukko voi olla mallitaulukko tai lauseke, joka palauttaa taulukon.

Vaatimuksesi voidaan saavuttaa kahdella tavalla. Voit käyttää [COUNT](/dax/count-function-dax)-funktiota sarakkeiden arvojen laskemiseen tai voit laskea taulukon rivit käyttämällä [COUNTROWS](/dax/countrows-function-dax)-funktiota. Kumpikin funktio saavuttaa saman tuloksen, kunhan laskettu sarake ei sisällä tyhjiä kohtia.

Seuraavassa mittarimäärityksessä esitetään esimerkki. Se laskee **OrderDate-** sarakearvojen määrän.

```dax
Sales Orders =
COUNT(Sales[OrderDate])
```

Jos **Sales**-taulukon askelväli on yksi rivi myyntitilausta kohti ja **OrderDate**-sarake ei sisällä tyhjiä arvoja, mittaus palauttaa oikean tuloksen.

Seuraava on kuitenkin parempi vaihto ehto.

```dax
Sales Orders =
COUNTROWS(Sales)
```

Toisen mittauksen käyttö on parempi kolmesta syystä:

- Se on tehokkaampaa, joten se toimii paremmin.
- Siinä ei huomioida taulukon sarakkeissa olevia tyhjiä kohtia.
- Kaavan tarkoitus on selkeämpi sen takia, että se on itsestään kuvaava.

## <a name="recommendation"></a>Suositus

Kun aiot laskea taulukon rivejä, suosittelemme, että käytät aina COUNTROWS-funktiota.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
