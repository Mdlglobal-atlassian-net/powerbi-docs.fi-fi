---
title: Numeerisen alueen osittajan käyttö Power BI Desktopissa
description: Opi käyttämään osittajaa numeerisiin alueisiin rajaamiseksi Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1e380a6821db7207d14e719fa5e070af38196b97
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34286930"
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

Numeerisen alueen osittaja kohdistuu kokonaislukuihin, ellei se ole desimaalialue. Näin osittaja voi tasata siististi kokonaislukuihin. 


## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat
**Numeerisen alueen osittajaa** koskevat tällä hetkellä seuraavat rajoitukset ja huomioon otettavat seikat:

* **Numeerisen alueen osittaja** suodattaa tällä hetkellä kaikki tietojen pohjana olevat rivit eikä koostettuja arvoja. Esimerkiksi jos käytetään kenttää *Myynnin määrä*, suodatetaan jokainen kenttään *Myynnin määrä* pohjautuva tapahtuma eikä summaa, joka saadaan visualisoinnin kunkin arvopisteen *Myynnin määrä* -kentistä.
* Osittaja ei tällä hetkellä toimi mittayksiköiden kanssa.
