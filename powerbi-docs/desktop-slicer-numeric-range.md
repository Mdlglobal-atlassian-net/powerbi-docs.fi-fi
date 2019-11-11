---
title: Numeerisen alueen osittajan käyttö Power BI Desktopissa
description: Opi käyttämään osittajaa numeerisiin alueisiin rajaamiseksi Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/19/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 535dbe2b1765d788e59d928f7303ce4696aa163b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879685"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Numeerisen alueen osittajan käyttö Power BI Desktopissa
Numeerisen alueen osittajan avulla voit käyttää kaikenlaisia suodattimia mihin tahansa tietomallisi numeeriseen sarakkeeseen. Numeeristen tietojen suodattamiseen on kolme vaihtoehtoa: lukujen välillä, pienempi tai yhtä suuri kuin luku ja suurempi tai yhtä suuri kuin luku. Tämä voi kuulostaa yksinkertaiselta, mutta kyseessä on tehokas tietojen suodatustapa.

![Numeerisen alueen osittajan visualisointi](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="use-the-numeric-range-slicer"></a>Numeerisen alueen osittajan käyttö
Voit käyttää numeerisen alueen osittajaa kuten mitä tahansa muuta osittajaa. Laadi **osittajan** visualisointi raportillesi ja valitse sitten numeerinen arvo **kentän** arvoksi. Seuraavassa kuvassa valittuna on **LineTotal**-kenttä.

![Numeerisen alueen osittajan luominen](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Valitse **numeerisen alueen osittajan** oikeassa yläkulmassa oleva alanuoli, jolloin esiin tulee valikko.

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

Numeerisen alueen osittaja kohdistuu kokonaislukuihin, jos pohjana olevan kentän tietotyyppi on **kokonaisluku**. Tämän ominaisuuden ansiosta osittaja voi tasata siististi kokonaislukuihin. **Desimaaliluku**-kenttien avulla voit syöttää tai valita murtolukuja. Tekstiruudun muotoilu vastaa kentässä määritettyä muotoilua, vaikka voit kirjoittaa tai valita tarkempia lukuja.

## <a name="display-formatting-with-the-date-range-slicer"></a>Muotoilun näyttäminen päivämääräalueen osittajan avulla

Kun käytät osittajaa päivämääräalueiden näyttämiseen tai asettamiseen, päivämäärät näkyvät **Lyhyt päivämäärä** -muodossa. Käyttäjän selaimen tai käyttöjärjestelmän aluekohtaiset asetukset määräävät päivämäärämuodon. Näin ollen se on näyttömuoto riippumatta siitä, mitkä tietotyypin asetukset on asetettu pohjana oleville tiedoille tai mallille. 

Pohjana olevassa tietotyypissä voi olla esimerkiksi pitkä päivämäärämuoto. Tässä tapauksessa esimerkiksi päivämäärämuoto *pppp, KKKK p, vvvv* muotoilee päivämäärän muissa visualisoinneissa tai tilanteissa muotoon *Keskiviikko 14. maaliskuuta 2001*. Päivämäärän osittajassa kyseinen päivämäärä näkyy kuitenkin muodossa *03/14/2001*.

Näyttämällä osittajassa **lyhyen päivämäärän** muodon varmistat, että merkkijonon pituus säilyy aina johdonmukaisena ja lyhyenä osittajassa. 

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat
**Numeerisen alueen osittajaa** koskevat seuraavat rajoitukset ja huomioon otettavat seikat:

* **Numeerisen alueen osittaja** suodattaa kaikki tietojen pohjana olevat rivit eikä koostettuja arvoja. Oletetaan esimerkiksi, että käytät kenttää *Myynnin määrä*. Osittaja suodattaa sen jälkeen kunkin tapahtuman myynnin määrän mukaan sen sijaan, että se käyttäisi myynnin määrän summaa visualisoinnin kussakin arvopisteessä.
* Osittaja ei tällä hetkellä toimi mittarien kanssa.
* Voit kirjoittaa minkä tahansa luvun tekstiruutuun numeerisessa osittajassa, vaikka luku olisi pohjana olevan sarakkeen arvojen alueen ulkopuolella. Tämän vaihtoehdon avulla voit määrittää suodattimia, jos tiedät, että tiedot voivat muuttua tulevaisuudessa.
