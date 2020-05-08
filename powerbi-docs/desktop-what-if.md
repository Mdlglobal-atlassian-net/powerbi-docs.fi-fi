---
title: Muuttujien visualisointi Entä jos -parametrien avulla
description: Luo oma Entä jos -muuttujasi, jolla voit kuvitella ja visualisoida muuttujia Power BI -raporteissa
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/21/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 8a72bc43bcceae6e676728934ceec81c8cb27d04
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "76539385"
---
# <a name="create-and-use-what-if-parameters-to-visualize-variables-in-power-bi-desktop"></a>Entä jos -parametrien luominen ja käyttäminen muuttujien visualisointiin Power BI Desktopissa

Elokuussa 2018 julkaistusta *Power BI Desktop* -versiosta lähtien voit luoda raportteihin *Entä jos* -muuttujia, käsitellä muuttujaa osittajana sekä visualisoida ja kvantifioida eri avainarvoja raporteissasi.

![Uusi parametri -asetus](media/desktop-what-if/what-if_01.png)

Luo *Entä jos* -parametri Power BI Desktopin **Mallinnus**-välilehdessä. Kun valitset sen, näyttöön tulee valintaikkuna, jossa voit määrittää parametrin.

## <a name="creating-a-what-if-parameter"></a>Entä jos -parametrin luominen

Luo Entä jos -parametri valitsemalla **Uusi parametri** Power BI Desktopin **Mallinnus**-välilehdessä. Seuraavassa kuvassa on luotu *Alennusprosentti*-parametri, jonka tietotyypiksi on määritetty **Desimaaliluku**. **Pienin** arvo on nolla. **Suurin** arvo on 0,50 (50 prosenttia). **Lisäykseksi** on määritetty 0,05 eli viisi prosenttia. Tämän arvon verran parametria säädetään, kun sitä käsitellään raportissa.

![Entä jos -parametriarvot](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> Kun käytät desimaalilukuja, varmista, että ne alkavat nollalla. Kirjoita siis 0,50 äläkä vain .50. Muussa tapauksessa lukua ei voida vahvistaa eikä **OK**-painike ole valittavissa.
> 
> 

Entä jos -parametrin mukainen osittaja lisätään automaattisesti nykyiseen raporttisivuun, kun valitset **Lisää osittaja tähän sivuun** -valintaruudun.

![Uusi osittaja nykyiseen raporttisivuun](media/desktop-what-if/what-if_03.png)

Kun Entä jos -parametri luodaan, luodaan itse parametrin lisäksi myös mittari, jonka avulla voit visualisoida Entä jos -parametrin nykyisen arvon.

![Entä jos -parametrille luotu mittari](media/desktop-what-if/what-if_04.png)

On tärkeää ja hyödyllistä huomioida, että Entä jos -parametrin luomisen jälkeen sekä parametrista että mittarista tulee osa malliasi. Ne ovat siis käytettävissä koko raportissa, ja niitä voi käyttää raportin muilla sivuilla. Ne ovat osa mallia, joten voit poistaa osittajan raporttisivulta. Jos haluat sen takaisin, tartu Entä jos -parametriin **Kentät**-luettelossa ja vedä se pohjaan, ja muuta visualisointi tämän jälkeen osittajaksi.

## <a name="using-a-what-if-parameter"></a>Entä jos -parametrin käyttäminen

Luodaan seuraavaksi yksinkertainen esimerkki Entä jos -parametrin käyttämisestä. Loimme Entä jos -parametrin edellisessä osiossa. Nyt otamme sen käyttöön luomalla uuden mittarin, jonka arvoa säädetään liukusäätimellä.

![Lisää uusi mittari parametrin kanssa käytettäväksi](media/desktop-what-if/what-if_05.png)

Uusi mittari on yksinkertaisesti myynnin kokonaismäärä, jossa huomioidaan alennusprosentti. Voit luoda monimutkaisia ja mielenkiintoisia mittareita, joiden avulla raporttiesi käyttäjät voivat visualisoida Entä jos -parametrin muuttujan. Voit esimerkiksi luoda raportin, joka kertoo myyntihenkilöstölle, mikä heidän kompensaationsa on, jos tietyt myyntitavoitteet tai -prosentit täyttyvät, tai tarkastella myynnin lisääntymisen ja suurempien alennusten suhdetta.

Kirjoita mittarin kaava kaavariville, ja anna kaavan nimeksi *Myynti alennuksen jälkeen*.

![Myynti alennuksen jälkeen -määritelmä](media/desktop-what-if/what-if_06.png)

Seuraavaksi luomme pylväskaavion, jonka akseliksi valitaan **Tilauspäivä** ja arvoiksi sekä **Myynnin määrä** että juuri luomamme mittari **Myynti alennuksen jälkeen**.

![Myynnin määrän visualisointi](media/desktop-what-if/what-if_07.png)

Kun liukusäädintä siirretään, **Myynti alennuksen jälkeen** -pylväs osoittaa myynnin määrän kyseistä alennusta käytettäessä.

![Liukusäädin vaikuttaa visualisointiin](media/desktop-what-if/what-if_08.png)

Siinä kaikki. Voit käyttää Entä jos -parametreja kaikenlaisissa tilanteissa. Näiden parametrien avulla raporttien käyttäjät voivat tutkia raportteihin luomiasi erilaisia skenaarioita.
