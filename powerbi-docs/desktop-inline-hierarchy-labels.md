---
title: Sidottujen hierarkiaselitteiden käyttö Power BI Desktopissa
description: Sidottujen hierarkiaselitteiden käyttö Power BI Desktopissa
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 9d5675b17973839f52699c5af9bfad9c8714a58e
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973732"
---
# <a name="use-inline-hierarchy-labels-in-power-bi-desktop"></a>Sidottujen hierarkiaselitteiden käyttö Power BI Desktopissa
**Power BI Desktop** tukee **sidottuja hierarkiaselitteitä**, joka on ensimmäinen kahdesta ominaisuudesta, joiden tarkoituksena on parantaa hierarkkista porautumista. Toisen ominaisuus, joka on tällä hetkellä kehityksen alla, on mahdollisuus käyttää sisäkkäisiä hierarkiaselitteitä (pysy kuulolla, sillä päivityksiä tehdään usein).   

## <a name="how-inline-hierarchy-labels-work"></a>Sidottujen hierarkiaselitteiden toiminta
Sidottujen hierarkiaselitteiden avulla näet hierarkiaselitteet laajentaessasi visualisointeja **Laajenna kaikki** -ominaisuudella. Yksi hieno etu hierarkiaselitteiden näyttämisessä on se, että voit myös halutessasi **lajitella** näiden eri hierarkiaselitteiden mukaan laajentaessasi hierarkkisia tietoja.

### <a name="using-the-built-in-expand-all-feature-without-sorting-by-hierarchy-labels"></a>Sisäisen Laajenna kaikki -ominaisuuden käyttäminen (ilman lajittelua hierarkiaselitteiden perusteella)
Ennen kuin näemme sidotut hierarkiaselitteet toiminnassa, katsotaan, miten oletusarvoinen **Laajenna kaikki** -ominaisuus toimii. Tämä auttaa ymmärtämään (ja arvostamaan) sitä, miten hyödyllisiä sidotut hierarkiaselitteet voivat olla.

Seuraavassa kuvassa näkyy palkkikaavion visualisointi vuosittaiselle myynnille. Kun napsautat hiiren kakkospainikkeella, voit valita **Laajenna kaikki**.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_4.png)

Kun **Laajenna kaikki** on valittuna, visualisointi laajentaa päivämäärän hierarkian *vuodesta* *vuosineljännekseen* seuraavassa kuvassa esitetyllä tavalla.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_5.png)

Huomaa, että *Vuosi*- ja *Vuosineljännes*-otsikot näkyvät sidottuina yhdessä... tämä seliterakenne jatkuu, kun valitset **Laajenna kaikki** hierarkian alareunaan saakka.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_6.png)

Näin käyttäytyy sisäinen *Päivämäärä*-hierarkia, joka liittyy kenttiin, joiden tietotyyppinä on *päivämäärä/kellonaika*. Siirrytään sitten seuraavaan osaan ja katsotaan, miten uusi sidottujen hierarkiaselitteiden ominaisuus on erilainen.

### <a name="using-inline-hierarchy-labels"></a>Sidottujen hierarkiaselitteiden käyttäminen
Tutustutaan nyt eri kaavioon - käyttämällä tietoja, joissa on epämuodollisia hierarkioita. Seuraava visualisoinnissa on pylväskaavio, jossa on **Myynnin määrä**, ja akselina on *Väri*. Näissä tiedoissa *Väri* ja *Luokka* muodostavat epämuodollisen hierarkian. Täältä voit uudelleen valita *Laajenna kaikki*ja porautua hierarkiaan.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_7.png)

Valitsemalla **Laajenna kaikki** voit näyttää seuraavan tason sidotuilla hierarkiaselitteillä. Oletusarvon mukaan sidotut hierarkiat lajitellaan mittayksikköarvon mukaan – tässä tapauksessa se on **Myynnin määrä**. Kun sidotut hierarkiaselitteet ovat käytössä, voit lajitella nämä tiedot myös hierarkian perusteella valitsemalla oikeassa yläkulmassa kolme pistettä (**...**) ja valitsemalla sitten **Lajitteluperuste > Väriluokka** seuraavassa kuvassa esitetyllä tavalla.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_8.png)

Kun **Väriluokka** on valittuna, tiedot lajitellaan epämuodollisen hierarkiavalinnan perusteella seuraavassa kuvassa esitetyllä tavalla.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_9.png)

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

