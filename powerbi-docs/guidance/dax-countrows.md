---
title: 'DAX: Käytä COUNTROWS-kohdetta COUNT-kohteen sijaan'
description: Ohjeita COUNTROWS-funktioiden käyttöön.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/23/2019
ms.author: v-pemyer
ms.openlocfilehash: fd3b50e9016298db8b692d6a2f3549b770f143e8
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "74700658"
---
# <a name="dax-use-countrows-instead-of-count"></a>DAX: Käytä COUNTROWS-kohdetta COUNT-kohteen sijaan

Tietojen mallintajana saatat joskus joutua kirjoittamaan DAX-lausekkeen, joka laskee taulukon rivejä. Taulukko voi olla mallitaulukko tai lauseke, joka palauttaa taulukon.

Vaatimuksesi voidaan saavuttaa kahdella tavalla. Voit käyttää [COUNT](/dax/count-function-dax)-funktiota sarakkeiden arvojen laskemiseen tai [COUNTROWS](/dax/countrows-function-dax)-funktiota taulukon rivien laskemiseen. Kumpikin funktio saavuttaa saman tuloksen, kunhan laskettu sarake ei sisällä tyhjiä kohtia.

Seuraavassa mittarimäärityksessä esitetään esimerkki. Se laskee **OrderDate**-sarakkeen arvojen määrän.

```dax
Sales Orders =
COUNT(Sales[OrderDate])
```

Jos **Sales**-taulukon askelväli on yksi rivi myyntitilausta kohti ja **OrderDate**-sarake ei sisällä tyhjiä kohtia, mittari palauttaa oikean tuloksen.

Seuraava määritys on kuitenkin parempi vaihtoehto.

```dax
Sales Orders =
COUNTROWS(Sales)
```

Toisen mittarin käyttö on parempi kolmesta syystä:

- Se on tehokkaampi, joten se toimii paremmin.
- Siinä ei huomioida mahdollisia tyhjiä kohtia taulukon sarakkeissa.
- Kaavan tarkoitus on selkeämpi, jopa itseään kuvaava.

## <a name="recommendation"></a>Suositus

Kun aiot laskea taulukon rivejä, suosittelemme aina käyttämään COUNTROWS-funktiota.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
