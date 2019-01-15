---
title: Muuttujien visualisointi Entä jos -parametrien avulla
description: Luo oma Entä jos -muuttujasi, jolla voit kuvitella ja visualisoida muuttujia Power BI -raporteissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: def3655d446f48d4dd0746e5544d8da618e09fcc
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295932"
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>Entä jos -parametrin luominen ja käyttäminen muuttujien visualisointiin Power BI Desktopissa
Elokuussa 2018 julkaistusta **Power BI Desktop** -versiosta lähtien voit luoda raportteihin **Entä jos** -muuttujia, käsitellä muuttujaa osittajana sekä visualisoida ja kvantifioida eri avainarvoja raporteissasi.

![](media/desktop-what-if/what-if_01.png)

**Entä jos** -parametri on **Power BI Desktopin** **Mallinnus**-välilehdessä. Sen valitsemisen myötä näyttöön tulee valintaikkuna, jossa voit määrittää parametrin.

## <a name="creating-a-what-if-parameter"></a>Entä jos -parametrin luominen
Voit luoda **Entä jos** -parametrin **Power BI Desktopin** **Mallinnus**-välilehdessä sijaitsevalla **Entä jos** -painikkeella. Seuraavassa kuvassa on luotu *Alennusprosentti*-parametri, jonka tietotyypiksi on määritetty *Desimaaliluku.* *Pienin* arvo on nolla, *suurin* taas 0,50 (viisikymmentä prosenttia). *Lisäykseksi* on määritetty 0,05 eli viisi prosenttia. Tämän arvon verran parametria säädetään, kun sitä käsitellään raportissa.

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> Kun käytät desimaalilukuja, varmista, että ne alkavat nollalla. Kirjoita siis 0,50 äläkä vain .50. Muussa tapauksessa lukua ei voida vahvistaa eikä **OK**-painike ole valittavissa.
> 
> 

**Entä jos** -parametrin mukainen osittaja lisätään automaattisesti nykyiseen raporttisivuun, kun valitset **Lisää osittaja tähän sivuun** -valintaruudun.

![](media/desktop-what-if/what-if_03.png)

Kun **Entä jos** -parametri luodaan, luodaan itse parametrin lisäksi myös mittari, jonka avulla voit visualisoida **Entä jos** -parametrin nykyisen arvon.

![](media/desktop-what-if/what-if_04.png)

On tärkeää ja hyödyllistä tietää, että **Entä jos** -parametrin luomisen jälkeen sekä parametrista että mittarista tulee osa malliasi. Ne ovat siis käytettävissä koko raportissa, ja niitä voi käyttää raportin muilla sivuilla. Koska ne ovat osa mallia, voit poistaa osittajan raporttisivulta ja saat sen helposti takaisin halutessasi. Voit palauttaa parametrin raporttiin tarttumalla **Entä jos** -parametriin **Kentät**-luettelossa ja vetämällä sen pohjaan (muuta visualisointi tämän jälkeen osittajaksi).

## <a name="using-a-what-if-parameter"></a>Entä jos -parametrin käyttäminen
Luodaan seuraavaksi yksinkertainen esimerkki **Entä jos** -parametrin käyttämisestä. Edellisessä osiossa loimme **Entä jos** -parametrin, ja nyt otamme sen käyttöön luomalla uuden mittarin, jonka arvoa säädetään liukusäätimellä. Teemme tämän luomalla uuden mittarin.

![](media/desktop-what-if/what-if_05.png)

Uusi mittari on yksinkertaisesti myynnin kokonaismäärä, jossa huomioidaan alennusprosentti. Voit tietenkin luoda monimutkaisia ja mielenkiintoisia mittareita, joiden avulla raporttiesi käyttäjät voivat visualisoida **Entä jos** -parametrin muuttujan. Voit esimerkiksi luoda raportin, joka kertoo myyntihenkilöstölle, mikä heidän kompensaationsa on, jos tietyt myyntitavoitteet tai -prosentit täyttyvät, tai tarkastella myynnin lisääntymisen ja suurempien alennusten suhdetta.

Kun mittarin kaava on kirjoitettu kaavariville ja sille on annettu nimeksi **Myynti alennuksen jälkeen**, lopputulos näyttää tältä:

![](media/desktop-what-if/what-if_06.png)

Seuraavaksi luomme pylväskaavion, jonka akseliksi valitaan *Tilauspäivä* ja arvoiksi sekä *Myynnin määrä* että juuri luomamme mittari *Myynti alennuksen jälkeen*.

![](media/desktop-what-if/what-if_07.png)

Kun liukusäädintä siirretään, *Myynti alennuksen jälkeen* -pylväs osoittaa myynnin määrän kyseistä alennusta käytettäessä.

![](media/desktop-what-if/what-if_08.png)

Siinä kaikki. Voit käyttää **Entä jos** -parametreja kaikenlaisissa tilanteissa, kun haluat antaa raporttien käyttäjille mahdollisuuden tutkia raportteihin luomiasi erilaisia skenaarioita.

