---
title: Muuttujien visualisointi Entä jos -parametrien avulla Power BI Desktopissa
description: Luo oma Entä jos -muuttujasi, jolla voit kuvitella ja visualisoida muuttujia Power BI -raporteissa
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 5222b6ba99c9e61d1070f66115b90aa29099fd8d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30974337"
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>Entä jos -parametrin luominen ja käyttäminen muuttujien visualisointiin Power BI Desktopissa
Elokuussa 2017 julkaistusta **Power BI Desktop** -versiosta lähtien voit luoda raportteihin **Entä jos** -muuttujia, käsitellä muuttujaa osittajana ja näin visualisoida ja kvantifioida eri avainarvoja raporteissasi.

![](media/desktop-what-if/what-if_01.png)

**Entä jos** -parametrin voi valita **Power BI Desktopin** **Mallinnus**-välilehdessä. Tällöin näyttöön tulee valintaikkuna, jossa voit määrittää parametrin.

## <a name="creating-a-what-if-parameter"></a>Entä jos -parametrin luominen
Voit luoda **Entä jos** -parametrin **Power BI Desktopin** **Mallinnus**-välilehdessä sijaitsevalla **Entä jos** -painikkeella. Seuraavassa kuvassa on luotu *Alennusprosentti*-parametri, jonka tietotyypiksi on määritetty *Desimaaliluku.* *Pienin* arvo on nolla, *suurin* taas 0,50 (viisikymmentä prosenttia). *Lisäykseksi* on määritetty 0,05 eli viisi prosenttia. Tämän arvon verran parametria säädetään, kun sitä käsitellään raportissa.

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> Kun käytät desimaalilukuja, varmista, että ne alkavat nollalla. Kirjoita siis ruutuun 0,50 äläkä vain .50. Muussa tapauksessa lukua ei voida vahvistaa eikä **OK**-painike ole valittavissa.
> 
> 

**Entä jos** -parametrin mukainen osittaja lisätään automaattisesti nykyiseen raporttisivuun, kun valitset **Lisää osittaja tähän sivuun** -valintaruudun.

![](media/desktop-what-if/what-if_03.png)

Kun **Entä jos** -parametri luodaan, luodaan itse parametrin lisäksi myös mittari, jonka avulla voit visualisoida **Entä jos** -parametrin nykyisen arvon.

![](media/desktop-what-if/what-if_04.png)

On tärkeää ja hyödyllistä tietää, että **Entä jos** -parametrin luomisen jälkeen sekä parametrista että mittarista tulee osa malliasi. Ne ovat siis käytettävissä koko raportissa, ja niitä voi käyttää raportin muilla sivuilla. Koska ne ovat osa mallia, voit poistaa osittajan raporttisivulta ja saat sen helposti takaisin halutessasi. Voit palauttaa **Entä jos** -parametrin raporttiin tarttumalla **Entä jos** -parametriin **Kentät**-luettelossa ja vetämällä sen pohjaan (muuta visualisointi tämän jälkeen osittajaksi).

## <a name="using-a-what-if-parameter"></a>Entä jos -parametrin käyttäminen
Luodaan seuraavaksi yksinkertainen esimerkki **Entä jos** -parametrin käyttämisestä. Edellisessä osiossa loimme **Entä jos** -parametrin, ja nyt otamme sen käyttöön luomalla uuden mittarin, jonka arvoa säädetään liukusäätimellä. Teemme tämän luomalla uuden mittarin.

![](media/desktop-what-if/what-if_05.png)

Uusi mittari on yksinkertaisesti myynnin kokonaismäärä, jossa huomioidaan alennusprosentti. Voit tietenkin luoda monimutkaisia ja mielenkiintoisia mittareita, joiden avulla raporttiesi käyttäjät voivat visualisoida **Entä jos** -parametrin muuttujan. Voit esimerkiksi luoda raportin, joka kertoo myyntihenkilöstölle, mikä heidän kompensaationsa on, jos tietyt myyntitavoitteet tai -prosentit täyttyvät, tai tarkastella myynnin lisääntymisen ja suurempien alennusten suhdetta.

Kun mittarin kaava on kirjoitettu kaavariville ja sille on annettu nimeksi **Myynti alennuksen jälkeen**, lopputulos näyttää tältä:

![](media/desktop-what-if/what-if_06.png)

Seuraavaksi luomme pylväskaavion, jonka akseliksi valitaan *OrderDate* ja arvoiksi sekä *SalesAmount* että juuri luomamme mittari *Myynti alennuksen jälkeen*.

![](media/desktop-what-if/what-if_07.png)

Kun liukusäädintä siirretään, *Myynti alennuksen jälkeen* -pylväs osoittaa myynnin määrän kyseistä alennusta käytettäessä.

![](media/desktop-what-if/what-if_08.png)

Siinä kaikki. Voit käyttää **Entä jos** -parametreja kaikenlaisissa tilanteissa, kun haluat antaa raporttien käyttäjille mahdollisuuden tutkia raportteihin luomiasi erilaisia skenaarioita.

