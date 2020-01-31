---
title: 'DAX: Kaavojen parantaminen muuttujien avulla'
description: Ohjeita muuttujien käyttämiseen DAX-lausekkeissa.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/23/2019
ms.author: v-pemyer
ms.openlocfilehash: f352cbbd7c42aa54ae876e73c0ed821eccda59c8
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700704"
---
# <a name="dax-use-variables-to-improve-your-formulas"></a>DAX: Kaavojen parantaminen muuttujien avulla

Tietojen mallintajana joidenkin DAX-laskelmien kirjoittaminen ja virheenkorjaus voi olla haastavaa. On tavallista, että monitasoisiin laskuvaatimuksiin liittyy usein monitasoisia tai yhdistelmälausekkeita. Yhdistelmälausekkeisiin voi sisältyä useiden sisäkkäisten funktioiden käyttö ja mahdollisesti lausekelogiikan uudelleenkäyttö.

DAX-kaavojen muuttujien avulla voit kirjoittaa monimutkaisia ja tehokkaita laskutoimituksia. Muuttujat voivat

- [parantaa suorituskykyä](#improve-performance)
- [parantaa luettavuutta](#improve-readability)
- [yksinkertaistaa virheenkorjausta](#simplify-debugging)
- [vähentää monimutkaisuutta.](#reduce-complexity)

Tässä artikkelissa esitellään näistä kolme ensimmäistä käyttämällä esimerkkinä vuoden aikana tapahtunutta myynninkasvua. (tällaisen myynninkasvun kaava on: ajanjakson myynti _fewer myynti samana ajanjaksona viime vuonna _jaettuna_ viime vuoden saman ajanjakson myynnillä.)

Aloitetaan seuraavasta mittarimäärityksestä.

```dax
Sales YoY Growth % =
DIVIDE(
    ([Sales] - CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))),
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
)
```

Mittari tuottaa oikean tuloksen, mutta katsotaan nyt, miten sitä voidaan parantaa.

## <a name="improve-performance"></a>Suorituskyvyn parantaminen

Huomaa, että kaava toistaa lausekkeen, joka laskee "samana ajanjaksona viime vuonna". Tätä kaavaa ei ole kovin tehokas, koska Power BI:n on arvioitava sama lauseke kahdesti. Mittarimääritystä voidaan tehostaa käyttämällä muuttujaa.

Seuraavassa mittarimäärityksessä esitetään parannus. Se käyttää lauseketta, joka määrittää viime vuoden saman ajanjakson tuloksen muuttujaan nimeltä **SalesPriorYear**. Muuttujaa käytetään sitten kahdesti RETURN-lausekkeessa.

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
```

Mittari tuottaa edelleen oikean tuloksen, mutta noin kaksi kertaa nopeammin.

## <a name="improve-readability"></a>Luettavuuden parantaminen

Huomaa edellisessä mittarimäärityksessä, miten muuttujan nimen valinta tekee RETURN-lausekkeesta helpomman ymmärtää. Lauseke on lyhyt ja kuvaava.

## <a name="simplify-debugging"></a>Virheenkorjauksen yksinkertaistaminen

Muuttujat voivat myös auttaa kaavan virheiden korjauksessa. Jos haluat testata muuttujalle määritettyä lauseketta, voit kirjoittaa RETURN-lausekkeen tilapäisesti uudelleen tulostamaan muuttujan.

Seuraava mittarimääritys palauttaa vain **SalesPriorYear**-muuttujan. Huomaa, miten se kommentoi aiottua RETURN-lauseketta. Tämän tekniikan avulla voit helposti palauttaa sen takaisin virheenkorjauksen jälkeen.

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    --DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
    SalesPriorYear
```

## <a name="reduce-complexity"></a>Monimutkaisuuden vähentäminen

Aiemmissa DAX-versioissa muuttujia ei vielä tuettu. Monimutkaiset lausekkeet, jotka ottivat käyttöön uusia suodatinkonteksteja, edellyttivät [EARLIER](/dax/earlier-function-dax)- tai [EARLIEST](/dax/earliest-function-dax) -DAX-funktioiden käyttämistä viittaamaan ulkoisiin suodatinkonteksteihin. Valitettavasti tietojen mallintajat pitivät näitä funktiota vaikeina ymmärtää ja käyttää.

Muuttujia arvioidaan aina RETURN-lausekkeen suodattimien ulkopuolella. Tästä syystä muuttuja tuottaa saman tuloksen muokatun suodatinkontekstin yhteydessä kuin EARLIEST-funktio. EARLIER- tai EARLIEST-funktioiden käyttöä voidaan siis välttää. Tämä tarkoittaa, että voit nyt kirjoittaa yksinkertaisempia kaavoja, joita on helpompi ymmärtää.

Harkitse seuraavaa lasketun sarakkeen määritystä, joka lisättiin **Subcategory**-taulukkoon. Se arvioi kunkin tuotteen aliluokan sijoituksen **Subcategory Sales** -sarakkeen arvojen perusteella.

```dax
Subcategory Sales Rank =
COUNTROWS(
    FILTER(
        Subcategory,
        EARLIER(Subcategory[Subcategory Sales]) < Subcategory[Subcategory Sales]
    )
) + 1
```

EARLIER-funktiolla viitataan **Subcategory Sales** -sarakkeen arvoon _nykyisessä rivikontekstissa_.

Lasketun sarakkeen määritystä voidaan parantaa käyttämällä muuttujaa EARLIER-funktion sijaan. **CurrentSubcategorySales**-muuttuja tallentaa **Subcategory Sales** -sarakkeen arvon _nykyisessä rivikontekstissa_, ja RETURN-lauseke käyttää sitä muokatun suodatinkontekstin yhteydessä.

```dax
Subcategory Sales Rank =
VAR CurrentSubcategorySales = Subcategory[Subcategory Sales]
RETURN
    COUNTROWS(
        FILTER(
            Subcategory,
            CurrentSubcategorySales < Subcategory[Subcategory Sales]
        )
    ) + 1
```

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [VAR](/dax/var-dax) -DAX-artikkeli
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
