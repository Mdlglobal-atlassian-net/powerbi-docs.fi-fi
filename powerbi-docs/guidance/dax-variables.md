---
title: 'DAX: Kaavojen parantaminen muuttujien avulla'
description: Muuttujien käyttäminen DAX-lausekkeissa.
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

Tietojen mallintajana joidenkin DAX-laskelmien kirjoittaminen ja virheen korjaus voi olla haastavaa. On tavallista, että monitasoisiin laskuvaatimuksiin liittyy usein yhdistelmä- tai monitasoisia lausekkeita. Yhdistelmälausekkeisiin voi sisältyä useiden sisäkkäisten funktioiden käyttö ja mahdollisesti lausekelogiikan uudelleenkäyttö.

DAX-kaavojen muuttujien avulla voit kirjoittaa monimutkaisia ja tehokkaita laskutoimituksia. Muuttujat voivat:

- [Parantaa suorituskykyä](#improve-performance)
- [Parantaa luettavuutta](#improve-readability)
- [Yksinkertaistaa virheen korjausta](#simplify-debugging)
- [Vähentää monimutkaisuutta](#reduce-complexity)

Tässä artikkelissa esitellään kolme ensimmäistä etua käyttämällä esimerkkinä vuoden aikana tapahtuvaa myynninkasvua. (YoY Sales kasvukaava on: period sales _fewer sales samalle kaudelle viime vuonna, _jaettuna_ myynti samalle kaudelle viime vuonna.)

Aloitetaan seuraavasta mittayksikkömäärityksestä.

```dax
Sales YoY Growth % =
DIVIDE(
    ([Sales] - CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))),
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
)
```

Mittayksikkö tuottaa oikean tuloksen, mutta katsotaan nyt, miten sitä voidaan parantaa.

## <a name="improve-performance"></a>Parantaa suorituskykyä

Huomaa, että kaava toistaa lausekkeen, joka laskee "samana ajan jaksona viime vuonna". Tämä kaava on tehoton, koska se vaatii Power BI:n saman lausekkeen arvioimista kahdesti. Mittayksikkömääritystä voidaan tehostaa käyttämällä muuttujaa.

Seuraavassa mittayksikkömäärityksessä esitetään parannus. Se käyttää lauseketta, joka määrittää "saman jakson viime vuonna"-tuloksen muuttujalle nimeltä **SalesPriorYear**. Muuttujaa käytetään sitten kahdesti RETURN-lausekkeessa.

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
```

Mittayksikkö tuottaa edelleen oikean tuloksen ja käyttää noin puolet kyselyn ajasta.

## <a name="improve-readability"></a>Parantaa luettavuutta

Huomaa edellisessä mittayksikkö määrityksessä, miten muuttujan nimen valinta tekee paluulausekkeesta helpomman ymmärtää. Lauseke on lyhyt ja itsesään kuvaava.

## <a name="simplify-debugging"></a>Yksinkertaistaa virheen korjausta

Muuttujat voivat myös auttaa kaavan virheen korjaamisessa. Jos haluat testata muuttujalle määritettyä lauseketta, voit kirjoittaa paluulausekkeen tilapäisesti uudelleen, jos haluat tulostaa muuttujan.

Seuraava mittayksikkö palauttaa vain **SalesPriorYear**-muuttujan. Huomaa, miten se kommentoi aiottua RETURN-lauseketta. Tämän tekniikan avulla voit helposti palauttaa sen takaisin, kun virheenkorjaus on valmis.

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    --DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
    SalesPriorYear
```

## <a name="reduce-complexity"></a>Vähentää monimutkaisuutta

Aiemmissa DAX-versioissa muuttujia ei vielä tueta. Monimutkaisia lausekkeita, jotka ottivat käyttöön uusia suodatinkonteksteja, tarvittiin käyttämään [aiemmasta](/dax/earlier-function-dax) tai [AIKAISEMMASTA](/dax/earliest-function-dax) DAX-funktioista viittaus ulompaan suodatinkontekstiin. Valitettavasti tietojen mallintajat pitivät näitä funktiota vaikeina ymmärtää ja käyttää.

Muuttujia arvioidaan aina niiden suodattimien ulkopuolella, joita RETURN-lauseke koskee. Tästä syystä, kun käytät muuttujaa muokatun suodattimen yhteydessä, se saavuttaa saman tuloksen kuin VARHAISIMMASSA funktiossa. AIEMMAN tai AIKAISIMMAN funktion käyttöä voidaan siis välttää. Se tarkoittaa, että voit nyt kirjoittaa kaavoja, jotka ovat vähemmän monimutkaisia ja joita on helpompi ymmärtää.

Harkitse seuraavaa laskettua sarakemääritystä, joka lisättiin **aliluokan** taulukkoon. Se arvioi kunkin tuotteen alaluokan sijoituksen **aliluokan myynti**sarakearvojen perusteella.

```dax
Subcategory Sales Rank =
COUNTROWS(
    FILTER(
        Subcategory,
        EARLIER(Subcategory[Subcategory Sales]) < Subcategory[Subcategory Sales]
    )
) + 1
```

EARLIER-funktiolla viitataan **aliluokan myyntisarakkeen** arvoon _nykyisessä rivikontekstissa_.

Lasketun sarakkeen määritystä voidaan parantaa käyttämällä muuttujaa EARLIER -funktion sijaan. **CurrentSubcategorySales**-muuttuja tallentaa **aliluokan myynti-** sarakkeen arvon _nykyisessä rivikontekstissa_, ja palautuslauseke käyttää sitä muokatun suodatinkontekstin yhteydessä.

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

- [VAR](/dax/var-dax) DAX-artikkeli
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
