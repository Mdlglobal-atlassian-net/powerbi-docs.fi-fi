---
title: Numeerisen alueen osittajan käyttö Power BI Desktopissa
description: Opi käyttämään osittajaa numeerisiin alueisiin rajaamiseksi Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 68467894850248d6acb841dc2ed651f595f19b95
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54287044"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Numeerisen alueen osittajan käyttö Power BI Desktopissa
**Numeerisen alueen osittajan** avulla voit käyttää kaikenlaisia suodattimia mihin tahansa tietomallisi numeeriseen sarakkeeseen. Voit myös suodattaa ehdoilla lukujen **välillä**, **pienempi tai yhtä suuri** kuin luku tai **suurempi tai yhtä suuri** kuin luku. Tämä voi kuulostaa yksinkertaiselta, mutta se on hyvin tehokas tapa suodattaa tietojasi.

![Numeerisen alueen osittajan visualisointi](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="using-the-numeric-range-slicer"></a>Numeerisen alueen osittajan käyttö
Voit käyttää numeerisen alueen osittajaa kuten mitä tahansa muuta osittajaa. Laadi **osittajan** visualisointi raportillesi ja valitse sitten numeerinen arvo **kentän** arvoksi. Seuraavassa kuvassa valittuna on *LineTotal*-kenttä.

![Numeerisen alueen osittajan luominen](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Valitse **numeerisen alueen osittajan** oikeassa yläkulmassa oleva alanuoli, jolloin esiin tulee valikko.

![Numeerisen alueen osittaja -valikko](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

Numeerisen alueen osalta voit valita seuraavista kolmesta vaihtoehdosta:

* Välillä
* Pienempi tai yhtä suuri kuin
* Suurempi tai yhtä suuri kuin

Kun valitset valikosta vaihtoehdon **Välillä**, näkyviin tulee liukusäädin, ja voit suodattaa lukujen välille osuvia numeerisia arvoja. Varsinaisen liukusäätimen käytön lisäksi voit napsauttaa kummasta ruudusta tahansa ja syöttää arvot. Tämä on kätevää, kun haluat osittaa tietyillä luvuilla, mutta osituspalkin siirtämisen askelvälit tekevät täsmälleen kyseiseen lukuun päätymisestä hankalaa.

Seuraavassa kuvassa raporttisivu on suodatettu *LineTotal*-arvoilla, jotka ovat välillä 2500,00–6000,00.

![Numeerisen alueen osittaja Välillä-asetuksella](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

Kun valitaan **Pienempi tai yhtä suuri kuin**, liukusäätimen vasemmalla oleva (pienempää arvoa osoittava) kahva katoaa ja vain liukusäätimen ylärajaa voidaan säätää. Seuraavassa kuvassa liukusäätimen enimmäisarvoksi asetetaan 5928,19.

![Numeerisen alueen osittaja Pienempi kuin -asetuksella](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Jos taas valitaan **Suurempi tai yhtä suuri kuin**, liukusäätimen oikea (suurinta arvoa osoittava) kahva katoaa ja pienempää arvoa voidaan säätää seuraavassa kuvassa osoitetulla tavalla. Nyt raporttisivun visualisoinneissa näytetään vain kohteet, joiden *LineTotal*-arvo on suurempi tai yhtä suuri kuin 4902,99.

![Numeerisen alueen osittaja Suurempi kuin -asetuksella](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Kokonaislukuihin kohdistaminen numeerisen alueen osittajalla

Numeerisen alueen osittaja kohdistuu kokonaislukuihin, jos pohjana olevan kentän tietotyyppi on **kokonaisluku**. Näin osittaja voi tasata siististi kokonaislukuihin. **Desimaaliluku**-tyyppisten kenttien avulla voit syöttää tai valita murtolukuja. Tekstiruudun muotoilu vastaa kentässä määritettyä muotoilua, vaikka voit kirjoittaa tai valita tarkempia lukuja.

## <a name="display-formatting-with-the-date-range-slicer"></a>Muotoilun näyttäminen päivämääräalueen osittajan avulla

Kun käytät osittajaa näyttämään tai määrittämään päivämääräalueen, päivämäärän muoto näkyy aina **lyhyen päivämäärän** muodossa käyttäjän selaimen tai käyttöjärjestelmän aluekohtaisten asetusten mukaan. Tämä näyttömuoto on aina sama pohjana olevien tietojen tai mallin tietotyyppiasetuksista huolimatta. 

Sinulla voi esimerkiksi olla pitkä päivämäärämuoto pohjana olevalle tietotyypille (kuten *pppp, p KKKK, vvvv*, joka voi muodostaa päivämäärän muissa visualisoinneissa tai tilanteissa, kuten *keskiviikko, 14. maaliskuuta 2001*), mutta päivämääräosittajassa tämä päivämäärä näytetään osittajassa muodossa *14.3.2001*.

Näyttämällä osittajassa **lyhyen päivämäärän** muodon varmistat, että merkkijonon pituus säilyy aina johdonmukaisena ja lyhyenä osittajassa. 


## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat
**Numeerisen alueen osittajaa** koskevat tällä hetkellä seuraavat rajoitukset ja huomioon otettavat seikat:

* **Numeerisen alueen osittaja** suodattaa tällä hetkellä kaikki tietojen pohjana olevat rivit eikä koostettuja arvoja. Esimerkiksi jos käytetään kenttää *Myynnin määrä*, suodatetaan jokainen kenttään *Myynnin määrä* pohjautuva tapahtuma eikä summaa, joka saadaan visualisoinnin kunkin arvopisteen *Myynnin määrä* -kentistä.
* Osittaja ei tällä hetkellä toimi mittayksiköiden kanssa.
* Voit kirjoittaa minkä tahansa luvun tekstiruutuun numeerisessa osittajassa, vaikka luku olisi pohjana olevan sarakkeen arvojen alueen ulkopuolella. Tämän avulla voit määrittää suodattimia, jos tiedät, että tiedot voivat muuttua tulevaisuudessa.
