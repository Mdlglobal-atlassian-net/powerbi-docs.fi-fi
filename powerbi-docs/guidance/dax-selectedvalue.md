---
title: 'DAX: Käytä SELECTEDVALUE-arvoa arvojen sijaan'
description: Lue ohjeet SELECTEDVALUE-funktioiden käyttöön.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: v-pemyer
ms.openlocfilehash: 6aef2c06cc62668ea7dea9fe404e294d1a5faa93
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/04/2020
ms.locfileid: "74700474"
---
# <a name="dax-use-selectedvalue-instead-of-values"></a>DAX: Käytä SELECTEDVALUE-arvoa arvojen sijaan

Tietomallintajana saatat joskus joutua kirjoittamaan DAX-lausekkeen, joka testaa, suodatetaanko sarake tietyllä arvolla.

Aikaisemmissa DAX-versioissa tämä vaatimus saavutettiin turvallisesti käyttämällä kolmea DAX-funktiota koskevaa kaavaa. Funktiot ovat [IF](/dax/if-function-dax), [HASONEVALUE](/dax/hasonevalue-function-dax) ja [VALUES](/dax/values-function-dax). Seuraavassa mittarimäärityksessä esitetään esimerkki. Se laskee arvonlisä veron summan, mutta vain australialaisille asiakkaille tehtyjen myyntien osalta.

```dax
Australian Sales Tax =
IF(
    HASONEVALUE(Customer[Country-Region]),
    IF(
        VALUES(Customer[Country-Region]) = "Australia",
        [Sales] * 0.10
    )
)
```

Esimerkissä HASONEVALUE-funktio palauttaa arvon TRUE vain, kun yksittäinen arvo suodattaa **maa-alue**-sarakkeen. Kun arvo on TRUE, VALUES-funktiolla verrataan kirjaimellisesti tekstiin "Australia". Kun VALUES-funktio palauttaa arvon TRUE, **Sales**-mittari kerrotaan luvulla 0,10 (osuus on 10 %). Jos HASONEVALUE-funktio palauttaa arvon FALSE, koska useampi kuin yksi arvo suodattaa sarakkeen, ensimmäinen IF-funktio palauttaa tyhjän tuloksen.

HASONEVALUE-kohteen käyttö on puolustava tekniikka. Se on pakollista, koska useat arvot suodattavat **maa-alue**-sarakkeen. Tässä tapauksessa VALUES-funktio palauttaa useiden rivien taulukon. Useiden rivien taulukon vertaaminen skalaariarvoon johtaa virheeseen.

## <a name="recommendation"></a>Suositus

Suosittelemme, että käytät [SELECTEDVALUE](/dax/selectedvalue-function)-funktiota. Sen tulos on sama kuin tässä artikkelissa kuvattu ohje, mutta saavutat tuloksen tehokkaammin ja tyylikkäämmin.

SELECTEDVALUE-funktiolla esimerkki mittarimäärityksestä kirjoitetaan nyt uudelleen.

```dax
Australian Sales Tax =
IF(
    SELECTEDVALUE(Customer[Country-Region]) = "Australia",
    [Sales] * 0.10
)
```

> [!TIP]
> On mahdollista välittää _vaihtoehtoinen tulos_ -arvo SELECTEDVALUE-funktioon. Vaihtoehtoinen tulos -arvo palautetaan, jos sarakkeeseen ei käytetä suodattimia tai jos sarakkeeseen käytetään useita suodattimia.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
