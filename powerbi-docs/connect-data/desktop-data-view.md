---
title: Tietonäkymä Power BI Desktopissa
description: Tietonäkymä Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/05/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 9311facac78a21568206843c026c8330960c9d33
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83347512"
---
# <a name="work-with-data-view-in-power-bi-desktop"></a>Tieto-näkymän käsittely Power BI Desktopissa

*Tiedot-näkymän* avulla voit tarkastaa *Power BI Desktop* -mallin tiedot, tutustua niihin ja ymmärtää niitä. Se poikkeaa taulukoiden, sarakkeiden ja tietojen tarkastelusta *Power Query -editorissa*. Tiedot-näkymässä tarkastelet tietojasi sen *jälkeen*, kun ne on ladattu tietomalliin.

> [!NOTE]
> Koska tietonäkymä näyttää tiedot sen jälkeen kun ne on ladattu malliin, Tietonäkymä-kuvaketta ei näy, jos kaikki tietolähteet perustuvat DirectQueryyn. 

Kun mallinnat tietojasi, haluat ehkä nähdä, mitä taulukossa tai sarakkeessa todella on ilman visualisoinnin luomista raporttipohjaan. Haluat ehkä nähdä aivan rivitasolle asti. Tämä ominaisuus on hyödyksi erityisesti silloin, kun luot mittareita ja laskettuja sarakkeita tai kun sinun on tunnistettava tietotyyppi tai tietoluokka.

Seuraavaksi katsotaan tarkemmin joitakin Tietonäkymän elementtejä.

![Tietonäkymä Power BI Desktopissa](media/desktop-data-view/dataview_fullscreen.png)

1. **Tietonäkymäkuvake**. Valitse tämä kuvake, kun haluat siirtyä Tietonäkymään.

2. **Tietoruudukko**. Tämä alue näyttää valitun taulukon ja sen sarakkeet ja rivit. *Raportti-näkymässä* piilotetut sarakkeet näytetään harmaina. Voit napsauttaa saraketta hiiren kakkospainikkeella tuodaksesi esiin valinnaiset tiedot.

3. **Mallinnusnauha**. Tässä voit hallinnoida suhteita, luoda laskelmia, muuttaa tietotyyppiä, muokata sarakkeen tietoluokkaa.

4. **Kaavarivi**. Syötä DAX-kaavoja Mittarit- ja Lasketut-sarakkeita varten.

5. **Haku**. Hae mallistasi taulukkoa tai saraketta.

6. **Kentät-luettelo**. Valitse taulukko tai sarake tarkasteltavaksi tietoruudukossa.

## <a name="filtering-in-data-view"></a>Suodattaminen tietonäkymässä

Voit myös suodattaa ja lajitella tietoja Tietonäkymässä. Jokaisessa sarakkeessa näkyy kuvake, joka tunnistaa lajittelusuunnan, jos sellainen on käytössä.

![Power BI Desktopin tietonäkymässä lajitteleminen ja suodattaminen](media/desktop-data-view/dataview_sort-and-filter.png)

Voit suodattaa yksittäisiä arvoja tai käyttää sarakkeen tietoihin perustuvaa lisäsuodatusta.

> [!NOTE]
> Kun Power BI -malli luodaan maa-asetukselle, joka eroaa senhetkisestä käyttöliittymästä, hakuruutu ei näy käyttöliittymän tietonäkymässä muissa kuin tekstikentissä. Tämä koskee esimerkiksi amerikanenglanniksi luotua mallia, jota tarkastelet espanjaksi.


## <a name="next-steps"></a>Seuraavat vaiheet

Power BI Desktopilla voit tehdä kaikenlaista. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Mikä on Power BI Desktop?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktopin kyselyjen yleiskatsaus](../transform-model/desktop-query-overview.md)
* [Tietotyypit Power BI Desktopissa](desktop-data-types.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](../transform-model/desktop-common-query-tasks.md)
