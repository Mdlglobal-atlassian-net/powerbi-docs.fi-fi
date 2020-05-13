---
title: Sarakkeen perusteella lajittelu Power BI Desktopissa
description: Voit muuttaa visualisoinnin ulkoasua Power BI:ssä lajittelemalla sen eri tietokenttien mukaan.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/30/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: db5bc2566e4711873629522d08a2d0c818071b81
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83334035"
---
# <a name="sort-by-column-in-power-bi-desktop"></a>Sarakkeen perusteella lajittelu Power BI Desktopissa
Voit muuttaa visualisoinnin ulkoasua Power BI Desktopissa ja Power BI -palvelussa lajittelemalla sen eri tietokenttien mukaan. Muuttamalla visualisoinnin lajittelua voit korostaa välitettäviä tietoja ja varmistaa, että visualisointi kuvastaa tätä trendiä (tai tietoa).

Voit lajitella visualisoinnit ja muokata niiden ulkoasua, olipa käytössä siten numeerisia tietoja (kuten myyntilukuja) tai tekstiä (kuten osavaltioiden nimiä). Power BI tarjoaa käyttöösi useita joustavia lajitteluvaihtoehtoja ja pikavalikoita. Voit lajitella minkä tahansa visualisoinnin valitsemalla sen **Lisää toimintoja** (...) ‑valikon, valitsemalla **Lajitteluperuste** ja valitsemalla sitten kentän, jota haluat käyttää lajitteluperusteena.

![Lisää asetuksia -valikko](media/desktop-sort-by-column/sortbycolumn_2.png)

## <a name="sorting-example"></a>Esimerkki lajittelusta
Otetaan seuraavaksi esimerkki, jossa on lisää syvyyttä, ja katsotaan, kuinka se toimii Power BI Desktopissa.

Seuraava visualisointi esittää kustannukset, määrät ja summat valmistajan nimen perusteella. Tässä on visualisointi sellaisena kuin se näkyy ennen lisälajittelua:

![Alkuperäinen visualisointi](media/desktop-sort-by-column/sortbycolumn_1.png)

Visualisointi lajitellaan tällä hetkellä **Myyntimäärät**-sarakkeen mukaan. Lajittelusarake voidaan päätellä vertaamalla nousevien palkkien väriä selitteeseen, mutta on myös parempi tapa: **Lisää toimintoja** ‑valikko, jonka voit avata valitsemalla kolme pistettä (...).

![Lisää asetuksia -valikko](media/desktop-sort-by-column/sortbycolumn_2.png)

Lajitteluvaihtoehdot ovat seuraavat:

* Nykyinen lajittelukenttä on **Myyntimäärät**, joka ilmenee lihavoidusta **Myyntimäärät**-kohdasta, jota edeltää keltainen palkki. 

* Nykyinen lajittelusuunta on nouseva, mikä ilmenee lihavoidusta **Lajittele nousevaan järjestykseen** ‑kohdasta, jota edeltää keltainen palkki.

Tarkastellaan lajittelukenttää ja lajittelun suuntaa seuraavissa kahdessa osassa.

## <a name="select-which-column-to-use-for-sorting"></a>Lajittelusarakkeen valitseminen
Huomasit **Myyntimäärät**-kohtaa edeltävän keltaisen palkin **Enemmän vaihtoehtoja** ‑valikossa. Palkki ilmaisee, että visualisointi on lajiteltu **Myyntimäärät**-sarakkeen mukaan. Toisen sarakkeen perusteella lajittelu on helppoa: valitse kolme pistettä (...) avataksesi **Lisää toimintoja** ‑valikon, valitse **Lajitteluperuste** ja valitse sitten eri sarake.

Seuraavassa kuvassa olemme valinneet **Alennuksen määrä** -sarakkeen lajitteluperusteeksi. Kyseinen sarake näkyy yhtenä visualisoinnin riveistä palkkien sijaan. 

![Lajittelu alennussumman mukaan](media/desktop-sort-by-column/sortbycolumn_3.png)

Huomaa, miten visualisointi on muuttunut. Arvot järjestetään nyt suurimmasta **alennuksen arvosta** eli Fabrikam Inc:sta alimpaan eli Northwind Tradersiin asti. 

Mutta entä jos haluamme lajittele tiedot nousevasti laskevan järjestyksen sijaan? Seuraavasta osasta näet, miten helppoa se on.

## <a name="select-the-sort-order"></a>Lajittelujärjestyksen valitseminen
Kun tarkastelemme edellisen kuvan **Lisää toimintoja** ‑valikkoa tarkemmin, huomaamme, että **Lajittele laskevaan järjestykseen** on lihavoitu ja että sitä edeltää keltainen palkki.

![Lajittele suurimmasta pienimpään](media/desktop-sort-by-column/sortbycolumn_4.png)

Kun **Lajittele laskevaan järjestykseen** on näkyvissä, se tarkoittaa, että visualisointi on lajiteltu valitun sarakkeen mukaan suurimmasta arvosta pienimpään arvoon. Haluatko muuttaa sen? Ei hätää. Valitse **Lajittele nousevaan järjestykseen**, niin valitun sarakkeen lajittelujärjestys muuttuu pienimmästä suurimpaan arvoon.

Tässä on sama visualisointi sen jälkeen, kun **Alennuksen arvon** järjestys on muutettu. Huomaa, että Northwind Traders on nyt luettelossa ensimmäinen valmistaja ja Fabrikam Inc. on viimeinen, toisin kuin aiemmassa lajittelussa.

![Lajittele pienimmästä suurimpaan](media/desktop-sort-by-column/sortbycolumn_5.png)

Voit lajitella visualisoinnin minkä tahansa sarakkeen mukaan. Olisimme voineet helposti esimerkiksi valita lajittelusarakkeeksi **Myyntimäärät**-sarakkeen, jolloin eniten myyneet valmistajat näkyvät ensimmäisinä. Muut sarakkeet säilyvät mukana visualisoinnissa valmistajaa koskevien arvojen mukaan. Tältä visualisointi näyttää näillä asetuksilla.

![Lajittele myyntimäärien mukaan](media/desktop-sort-by-column/sortbycolumn_6.png)

## <a name="sort-using-the-sort-by-column-button"></a>Lajittelu Lajittele sarakkeen mukaan -painikkeella
Tiedot voidaan lajitella myös käyttämällä **Lajittele sarakkeen mukaan** -painiketta **Mallinnus**-valintanauhassa.

![Lajittele sarakkeen mukaan -painike](media/desktop-sort-by-column/sortbycolumn_8.png)

Tämä tapa edellyttää, että valitset ensin sarakkeen (kentän) **Kentät**-ruudusta ja lajittelet visualisoinnin valitsemalla sitten **Mallinnus** > **Lajittele sarakkeen mukaan**. Jos et valitse saraketta, **Lajittele sarakkeen mukaan** ‑painike ei ole aktiivinen.

Katsotaan yleistä esimerkkiä. Sinulla on tietoja jokaiselta kuukaudelta ja haluat lajitella ne aikajärjestyksessä. Seuraavissa vaiheissa esitellään, miten se on mahdollista:

1. Huomaa, että kun visualisointi on valittuna, mutta mitään saraketta ei ole valittu **Kentät**-ruudussa, **Lajittele sarakkeen mukaan** -painike ei ole käytössä (painike näkyy harmaana).
   
   ![Lajittele sarakkeen mukaan -painike ei aktiivinen](media/desktop-sort-by-column/sortbycolumn_9.png)

2. Kun valitsemme lajiteltavan sarakkeen **Kentät**-ruudussa, **Lajittele sarakkeen mukaan** -painike muuttuu aktiiviseksi.
   
   ![Lajittele sarakkeen mukaan -painike on aktiivinen](media/desktop-sort-by-column/sortbycolumn_10.png)
3. Nyt kun visualisointi on valittuna, voimme valita **Kuukausi**-vaihtoehdon oletusarvon **Kuukauden nimi** sijaan, jolloin visualisointi lajitellaan haluamassamme järjestyksessä eli kuukauden mukaan.
   
   ![Lajittele sarakkeen mukaan -valikko](media/desktop-sort-by-column/sortbycolumn_11.png)


<!---
This functionality is no longer active. Jan 2020

## Getting back to default column for sorting
You can sort by any column you'd like, but there may be times when you want the visual to return to its default sorting column. No problem. For a visual that has a sort column selected, open the **More options** menu and select that column again, and the visualization returns to its default sort column.

For example, here's our previous chart:

![Initial visualization](media/desktop-sort-by-column/sortbycolumn_6.png)

When we go back to the menu and select **SalesQuantity** again, the visual defaults to being ordered alphabetically by **Manufacturer**, as shown in the following image.

![Default sort order](media/desktop-sort-by-column/sortbycolumn_7.png)

With so many options for sorting your visuals, creating just the chart or image you want is easy.
--->

## <a name="next-steps"></a>Seuraavat vaiheet

Voit olla kiinnostunut myös seuraavista artikkeleista:

* [Raporttien välillä porautumisen käyttäminen Power BI Desktopissa](desktop-cross-report-drill-through.md)
* [Osittajat Power BI:ssä](../visuals/power-bi-visualization-slicers.md)
