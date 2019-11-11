---
title: Sidottujen hierarkiaselitteiden käyttö Power BI Desktopissa
description: Sidottujen hierarkiaselitteiden käyttö Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: db86fee2303759d30b2ff64dc59b56314f220474
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73867346"
---
# <a name="use-inline-hierarchy-labels-in-power-bi-desktop"></a>Sidottujen hierarkiaselitteiden käyttö Power BI Desktopissa
**Power BI Desktop** tukee **sidottuja hierarkiaselitteitä**, joka on ensimmäinen kahdesta ominaisuudesta, joiden tarkoituksena on parantaa hierarkkista porautumista. Toisen ominaisuus, joka on tällä hetkellä kehityksen alla, on mahdollisuus käyttää sisäkkäisiä hierarkiaselitteitä (pysy kuulolla, sillä päivityksiä tehdään usein).   

## <a name="how-inline-hierarchy-labels-work"></a>Sidottujen hierarkiaselitteiden toiminta
Sidottujen hierarkiaselitteiden avulla näet hierarkiaselitteet laajentaessasi visualisointeja **Laajenna kaikki** -ominaisuudella. Yksi hieno etu hierarkiaselitteiden näyttämisessä on se, että voit myös halutessasi **lajitella** näiden eri hierarkiaselitteiden mukaan laajentaessasi hierarkkisia tietoja.

### <a name="using-the-built-in-expand-feature-without-sorting-by-hierarchy-labels"></a>Sisäisen Laajenna-ominaisuuden käyttäminen (ilman lajittelua hierarkiaselitteiden perusteella)
Ennen kuin tarkastelemme sidottuja hierarkiaselitteitä toiminnassa, tutustumme siihen, miten oletusarvoinen **Laajenna seuraavalle tasolle** -ominaisuus toimii. Tämä auttaa ymmärtämään (ja arvostamaan) sitä, miten hyödyllisiä sidotut hierarkiaselitteet voivat olla.

Seuraavassa kuvassa näkyy palkkikaavion visualisointi vuosittaiselle myynnille. Kun napsautat palkissa hiiren kakkospainikkeella, voit valita **Laajenna seuraavalle tasolle** -vaihtoehdon.

![Laajenna-pikavalikko](media/desktop-inline-hierarchy-labels/desktop-inline-hierarchy-labels-menu.png)

> [!NOTE]
> Vaihtoehtona palkin napsauttamiselle hiiren kakkospainikkeella voit valita *Laajenna*-painikkeen visualisoinnin vasemmassa yläkulmassa.

  ![Laajenna-painike](media/desktop-inline-hierarchy-labels/desktop-inline-hierarchy-labels-expand-button-finger.png)


Kun **Laajenna seuraavalle tasolle** on valittuna, visualisointi laajentaa päivämäärän hierarkian *vuodesta* *vuosineljännekseen* seuraavassa kuvassa esitetyllä tavalla.

![Visualisointi laajennettuna vuoteen ja vuosineljännekseen](media/desktop-inline-hierarchy-labels/desktop-inline-hierarchy-labels-qty-year-quarter.png)

Huomaa, että *Vuosi*- ja *Vuosineljännes*-otsikot näkyvät sidottuina yhdessä – tämä seliterakenne jatkuu, kun valitset **Laajenna kaikki** hierarkian alareunaan saakka.

![Visualisointi laajennettuna vuoteen, vuosineljännekseen ja kuukauteen](media/desktop-inline-hierarchy-labels/desktop-inline-hierarchy-labels-qty-year-quarter-month.png)

Näin käyttäytyy sisäinen *Päivämäärä*-hierarkia, joka liittyy kenttiin, joiden tietotyyppinä on *päivämäärä/kellonaika*. Siirrytään sitten seuraavaan osaan ja katsotaan, miten uusi sidottujen hierarkiaselitteiden ominaisuus on erilainen.

### <a name="using-inline-hierarchy-labels"></a>Sidottujen hierarkiaselitteiden käyttäminen
Tutustutaan nyt eri kaavioon - käyttämällä tietoja, joissa on epämuodollisia hierarkioita. Seuraavassa visualisoinnissa on pylväskaavio, jossa esitetään **Määrä** ja akselina on *TuotteenNimi*. Näissä tiedoissa *TuotteenNimi* ja *Toimitusmaa* muodostavat epäviralliset hierarkian. Täältä voit valita uudelleen *Laajenna seuraavalle tasolle* -vaihtoehdon porautuaksesi hierarkiaan.

![Kaavio, jossa on epämuodollinen hierarkia](media/desktop-inline-hierarchy-labels/desktop-inline-hierarchy-labels-informal-top-expand.png)

Valitsemalla **Laajenna seuraavalle tasolle** -vaihtoehdon voit näyttää seuraavan tason sidotuilla hierarkiaselitteillä. Oletusarvon mukaan sidotut hierarkiat lajitellaan mittariarvon mukaan – tässä tapauksessa se on **Määrä**. Kun sidotut hierarkiaselitteet ovat käytössä, voit lajitella nämä tiedot myös hierarkian perusteella valitsemalla oikeassa yläkulmassa kolme pistettä ( **...** ) ja valitsemalla sitten **Lajitteluperuste TuotteenNimi Toimitusmaa** seuraavassa kuvassa esitetyllä tavalla.

![Kaavio, jossa on oletusarvoisesti lajiteltu epämuodollinen hierarkia](media/desktop-inline-hierarchy-labels/desktop-inline-hierarchy-labels-informal-sort-quantity.png)

Kun **Toimitusmaa** on valittuna, tiedot lajitellaan epämuodollisen hierarkiavalinnan perusteella seuraavassa kuvassa esitetyllä tavalla.

![Kaavio, jossa on epämuodollisen hierarkian mukaan lajiteltu epämuodollinen hierarkia](media/desktop-inline-hierarchy-labels/desktop-inline-hierarchy-labels-informal-sorted.png)

> [!NOTE]
> Sidotun hierarkiaselitteen ominaisuus ei vielä salli sisäisen aikahierarkian lajittelua arvon perusteella, ainoastaan hierarkiajärjestyksen perusteella.
> 
> 

## <a name="troubleshooting"></a>Vianmääritys
On mahdollista, että visualisoinnit jäävät jumiin laajennetun sidotun hierarkiatason tilaan. Joissakin tapauksissa saatat huomata, että jotkin visualisoinnit ovat jumissa tilassa, jossa ne laajennettiin, jolloin porautuminen ylöspäin ei toimi. Näin voi käydä, jos suoritit seuraavat vaiheet (korjaava toimenpide on näiden vaiheiden *alla*):

Vaiheet, joilla visualisoinnit saattavat jäädä jumiin laajennetussa tilassa:

1. Otat käyttöön **sidotun hierarkiaselitteen** ominaisuuden
2. Luot visualisointeja hierarkioita käyttämällä
3. Sitten valitset **Laajenna kaikki** ja tallennat tiedoston
4. Sen jälkeen *poistat käytöstä* **sidotun hierarkiaselitteen** toiminnon ja käynnistät Power BI Desktopin uudelleen
5. Sitten avaat tiedoston uudelleen

Jos suoritat nämä vaiheet ja visualisoinnit ovat jumissa laajennetussa tilassa, voit suorittaa vianmäärityksen seuraavalla tavalla:

1. Ota uudelleen käyttöön **sidotun hierarkiaselitteen** toiminto ja käynnistä Power BI Desktop uudelleen
2. Avaa tiedosto uudelleen ja poraudu takaisin alkuun asianomaisissa visualisoinneissa
3. Tallenna tiedosto
4. Poista **sidotun hierarkiaselitteen** toiminto käytöstä ja käynnistä Power BI Desktop uudelleen
5. Avaa tiedosto uudelleen

Vaihtoehtoisesti voit poistaa visualisoinnin ja luoda sen uudelleen.

