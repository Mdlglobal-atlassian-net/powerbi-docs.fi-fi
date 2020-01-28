---
title: 'DAX: Vältä FILTER-arvon käyttämistä suodatinargumenttina'
description: Ohjeita FILTER-toiminnon käyttämiseen suodatinargumenttina.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/30/2019
ms.author: v-pemyer
ms.openlocfilehash: 6abcb77e3eb534e8b5d20c1d5567c117cbb97ffe
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/17/2020
ms.locfileid: "76161428"
---
# <a name="dax-avoid-using-filter-as-a-filter-argument"></a>DAX: Vältä FILTER-arvon käyttämistä suodatinargumenttina

Tietomallintajana kirjoitat usein DAX-lausekkeita, jotka on arvioitava muokatussa suodatinkontekstista. Voit esimerkiksi kirjoittaa mittarimäärittelyn, jolla lasketaan "suuren myyntikatteen tuotteiden" myynti. Tämä laskutoimitus kuvaillaan myöhemmin tässä artikkelissa.

> [!NOTE]
> Tämä artikkeli koskee erityisesti mallilaskelmia, jotka käyttävät suodattimia taulukoiden tuomiseen.

[CALCULATE](/dax/calculate-function-dax)- ja [CALCULATETABLE](/dax/calculatetable-function-dax)-DAX-funktiot ovat tärkeitä ja hyödyllisiä funktioita. Niiden avulla voit kirjoittaa laskutoimituksia, jotka poistavat tai lisäävät suodattimia tai muokkaavat suhdepolkuja. Se tehdään välittämällä suodatinargumentteja, jotka ovat joko totuusarvolausekkeita, taulukkolausekkeita tai erityisiä suodatinfunktioita. Käsittelemme tässä artikkelissa vain totuusarvo- ja taulukkolausekkeita.

Tarkastele seuraavaa mittarimääritystä, joka laskee punaisten tuotteiden myynnin taulukkolausekkeen avulla. Se korvaa kaikki suodattimet, joita voidaan käyttää **Product**-taulukossa.

```dax
Red Sales =
CALCULATE(
    [Sales],
    FILTER('Product', 'Product'[Color] = "Red")
)
```

CALCULATE-funktio hyväksyy [FILTER](/dax/filter-function-dax)-DAX-funktion palauttaman taulukkolausekkeen, joka arvioi sen suodatuslausekkeen kullekin **Product**-taulukon riville. Se saa oikean tuloksen – punaisten tuotteiden myyntituloksen. Tulos voidaan kuitenkin saada paljon tehokkaammin käyttämällä totuusarvolauseketta.

Tässä on parannettu mittarimääritys, joka käyttää totuuslauseketta taulukkolausekkeen sijaan. [KEEPFILTERS](/dax/keepfilters-function-dax) DAX -funktio varmistaa, että **Color**-sarakkeeseen sovellettavat kaikki olemassa olevat suodattimet säilytetään, eikä niitä korvata.

```dax
Red Sales =
CALCULATE(
    [Sales],
    KEEPFILTERS('Product'[Color] = "Red")
)
```

Suosittelemme välittämään suodatinargumentit totuusarvolausekkeiksi aina, kun se on mahdollista. Tämä johtuu siitä, että tuontimallitaulukot ovat muistissa olevia sarakesäilöjä. Ne on nimenomaisesti optimoitu suodattamaan sarakkeet tehokkaasti tällä tavalla.

Totuusarvolausekkeisiin sovelletaan kuitenkin rajoituksia, kun niitä käytetään suodatinargumentteina. Ne

- eivät voi verrata sarakkeita muihin sarakkeisiin
- eivät voi viitata mittariin
- eivät voi käyttää sisäkkäisiä CALCULATE-funktioita
- eivät voi käyttää funktioita, jotka skannaavat tai palauttavat taulukon

Tämä tarkoittaa, että sinun on käytettävä monimutkaisempiin suodatinvaatimuksiin taulukkolausekkeita.

Tarkastele nyt eri mittarimääritystä.

```dax
High Margin Product Sales =
CALCULATE(
    [Sales],
    FILTER(
        'Product',
        'Product'[ListPrice] > 'Product'[StandardCost] * 2
    )
)
```

_Suuren katteen tuote_ määritellään tuotteeksi, jonka luettelohinta on yli kaksinkertainen vakiokustannukseensa nähden. Tässä esimerkissä pitää käyttää FILTER-funktiota. Tämä johtuu siitä, että suodatinlauseke on liian monimutkainen totuusarvolausekkeelle.

Tässä vielä yksi esimerkki. Tällä kertaa vaatimuksena on laskea myynti, mutta vain kuukausille, jotka ovat olleet voitollisia.

```dax
Sales for Profitable Months =
CALCULATE(
    [Sales],
    FILTER(
        VALUES('Date'[Month]),
        [Profit] > 0)
    )
)
```

Tässä esimerkissä pitää myös käyttää FILTER-funktiota. Tämä johtuu siitä, että siinä edellytetään **Tuotto**-mittarin laskemista niiden kuukausien poistamiseksi, jotka eivät ole tuottaneet voittoa. Mittaria ei voi käyttää totuusarvolausekkeessa, kun sitä käytetään suodatinargumenttina.

## <a name="recommendations"></a>Suositukset

Parhaan suorituskyvyn takaamiseksi suosittelemme, että käytät totuusarvolausekkeita suodatinargumentteina aina, kun se on mahdollista.

Siksi FILTER-funktioita tulee käyttää vain tarvittaessa. Sen avulla voit suodattaa monimutkaisia sarakevertailuja. Nämä sarakevertailut voivat koskea seuraavia:

- Mittarit
- Muut sarakkeet
- [OR](/dax/or-function-dax)-DAX-funktiolla tai OR- loogisella operaattorilla (||)

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- [Suodatinfunktiot (DAX)](/dax/filter-function-dax)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
