---
title: Numeerisen alueen osittajan käyttö Power BI:ssä
description: Opi käyttämään osittajaa numeerisiin alueisiin rajaamiseksi Power BI:ssä.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: zIZPA0UrJyA
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 51bc2f7e3069302fd4ba7a652ee4350bceb8b7e6
ms.sourcegitcommit: a199dda2ab50184ce25f7c9a01e7ada382a88d2c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/06/2020
ms.locfileid: "82866698"
---
# <a name="use-the-numeric-range-slicer-in-power-bi"></a>Numeerisen alueen osittajan käyttö Power BI:ssä

[!INCLUDE [applies-to](includes/applies-to.md)] [!INCLUDE [yes-desktop](includes/yes-desktop.md)] [!INCLUDE [yes-service](includes/yes-service.md)]

Numeerisen alueen osittajan avulla voit käyttää kaikenlaisia suodattimia mihin tahansa tietomallisi numeeriseen sarakkeeseen. Numeeristen tietojen suodattamiseen on kolme vaihtoehtoa: lukujen välillä, pienempi tai yhtä suuri kuin luku ja suurempi tai yhtä suuri kuin luku. Tämä yksinkertainen tekniikka on tehokas tapa suodattaa tietojasi.

![Numeerisen alueen osittajan visualisointi](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="video"></a>Video

Tässä videossa Will esittelee numeerisen alueen osittajan luomisen.

> [!NOTE]
> Tässä videossa käytetään Power BI Desktopin vanhempaa versiota.

<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe> 


## <a name="add-a-numeric-range-slicer"></a>Numeerisen alueen osittajan lisääminen

Voit käyttää numeerisen alueen osittajaa kuten mitä tahansa muuta osittajaa. Luo vain **osittajan** visualisointi raportillesi ja valitse sitten numeerinen arvo **kentän** arvoksi. Seuraavassa kuvassa valittuna on **LineTotal**-kenttä.

![Numeerisen alueen osittajan luominen](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Valitse numeerisen alueen osittajan oikeassa yläkulmassa oleva alanuoli, jolloin esiin tulee valikko.

![Numeerisen alueen osittaja -valikko](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

Numeerisen alueen osalta voit valita seuraavista kolmesta vaihtoehdosta:

* **Välillä**
* **Pienempi tai yhtä suuri kuin**
* **Suurempi tai yhtä suuri kuin**

Kun valitset valikosta **Välillä**-vaihtoehdon, näkyviin tulee liukusäädin. Voit valita liukusäätimen avulla lukujen väliin jäävät numeroarvot. Joskus osittajapalkin siirtämisen askelväli vaikeuttaa osumista täsmälleen haluttuun lukuun. Voit myös käyttää liukusäädintä ja antaa haluamasi arvot napsauttamalla jompaakumpaa ruutua. Tämä vaihtoehto on kätevä, kun haluat osittaa tietyt luvut.

Seuraavassa kuvassa raporttisivu on suodatettu **LineTotal**-arvoilla, jotka ovat välillä 2500,00–6000,00.

![Numeerisen alueen osittaja Välillä-asetuksella](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

Kun valitaan **Pienempi tai yhtä suuri kuin**, liukusäätimen vasemmalla oleva (pienempää arvoa osoittava) kahva katoaa ja vain liukusäätimen ylärajaa voidaan säätää. Seuraavassa kuvassa liukusäätimen enimmäisarvoksi asetetaan 5928,19.

![Numeerisen alueen osittaja Pienempi kuin -asetuksella](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Jos valitset lopuksi **suurempi tai yhtä suuri kuin**, liukusäätimen oikealla oleva (suurempaa arvoa osoittava) kahva häviää. Voit sitten säätää liukusäätimen alarajaa seuraavan kuvan mukaisesti. Nyt raporttisivun visualisoinneissa näytetään vain kohteet, joiden **LineTotal**-arvo on suurempi tai yhtä suuri kuin 4902,99.

![Numeerisen alueen osittaja Suurempi kuin -asetuksella](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Kokonaislukuihin kohdistaminen numeerisen alueen osittajalla

Numeerisen alueen osittaja kohdistuu kokonaislukuihin, jos pohjana olevan kentän tietotyyppi on *kokonaisluku*. Tämän ominaisuuden ansiosta osittaja voi tasata siististi kokonaislukuihin. *Desimaaliluku*-kenttien avulla voit syöttää tai valita murtolukuja. Tekstiruudun muotoilu vastaa kentässä määritettyä muotoilua, vaikka voit kirjoittaa tai valita tarkempia lukuja.

## <a name="display-formatting-with-the-date-range-slicer"></a>Muotoilun näyttäminen päivämääräalueen osittajan avulla

Kun käytät osittajaa päivämääräalueiden näyttämiseen tai asettamiseen, päivämäärät näkyvät *Lyhyt päivämäärä* -muodossa. Käyttäjän selaimen tai käyttöjärjestelmän aluekohtaiset asetukset määräävät päivämäärämuodon. Näin ollen se on näyttömuoto riippumatta siitä, mitkä tietotyypin asetukset on asetettu pohjana oleville tiedoille tai mallille.

Pohjana olevassa tietotyypissä voi olla esimerkiksi pitkä päivämäärämuoto. Tässä tapauksessa esimerkiksi päivämäärämuoto *pppp, KKKK p, vvvv* muotoilee päivämäärän muissa visualisoinneissa tai tilanteissa muotoon *Keskiviikko 14. maaliskuuta 2001*. Päivämäärän osittajassa kyseinen päivämäärä näkyy kuitenkin muodossa *03/14/2001*.

Näyttämällä osittajassa lyhyen päivämäärän muodon varmistat, että merkkijonon pituus säilyy aina johdonmukaisena ja lyhyenä osittajassa.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioon otettavat seikat

Numeerisen alueen osittajaa koskevat seuraavat rajoitukset ja huomioon otettavat seikat:

* Numeerisen alueen osittaja suodattaa kaikki tietojen pohjana olevat rivit eikä koostettuja arvoja. Oletetaan esimerkiksi, että käytät kenttää *Myynnin määrä*. Osittaja suodattaa sen jälkeen kunkin tapahtuman myynnin määrän mukaan sen sijaan, että se käyttäisi myynnin määrän summaa visualisoinnin kussakin arvopisteessä.
* Osittaja ei tällä hetkellä toimi mittarien kanssa.
* Voit kirjoittaa minkä tahansa luvun numeeriseen osittajaan, vaikka luku olisi pohjana olevan sarakkeen arvojen alueen ulkopuolella. Tämän vaihtoehdon avulla voit määrittää suodattimia, jos tiedät, että tiedot voivat muuttua tulevaisuudessa.
