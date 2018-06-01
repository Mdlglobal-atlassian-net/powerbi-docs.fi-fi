---
title: Numeerisen alueen osittajan käyttö Power BI Desktopissa
description: Opi käyttämään osittajaa numeerisiin alueisiin rajaamiseksi Power BI Desktopissa
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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f6e0433e8862e2acb6f0e7a72a1293e37f2185eb
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973662"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Numeerisen alueen osittajan käyttö Power BI Desktopissa
**Numeerisen alueen osittajan** avulla voit käyttää kaikenlaisia suodattimia mihin tahansa tietomallisi numeeriseen sarakkeeseen. Voit myös suodattaa ehdoilla lukujen **välillä**, lukua **pienempi tai yhtä suuri** tai lukua **suurempi tai yhtä suuri**. Tämä voi kuulostaa yksinkertaiselta, mutta se on hyvin tehokas tapa suodattaa tietojasi.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_2.png)

## <a name="using-the-numeric-range-slicer"></a>Numeerisen alueen osittajan käyttö
Voit käyttää numeerisen alueen osittajaa kuten mitä tahansa muuta osittajaa. Laadi **osittajan** visualisointi raportillesi ja valitse sitten numeerinen arvo **kentän** arvoksi. Seuraavassa kuvassa valittuna on *UnitPrice*-kenttä.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_3.png)

Valitse **numeerisen alueen osittajan** oikeassa yläkulmassa oleva merkki, jolloin esiin tulee valikko.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_4.png)

Numeerisen alueen osalta voit valita seuraavista kolmesta vaihtoehdosta:

* Välillä
* Pienempi tai yhtä suuri kuin
* Suurempi tai yhtä suuri kuin

Kun valitset valikosta vaihtoehdon **Välillä**, näkyviin tulee liukusäädin, ja voit suodattaa lukujen välille osuvia numeerisia arvoja. Varsinaisen liukusäätimen käytön lisäksi voit napsauttaa kummasta ruudusta tahansa ja syöttää arvot. Tämä on kätevää, kun haluat osittaa tietyillä kokonaisluvuilla, mutta osituspalkin siirtämisen askelvälit tekevät täsmälleen kyseiseen lukuun päätymisestä hankalaa.

Seuraavassa kuvassa raporttisivu on suodatettu *UnitPrice*-arvoilla, jotka ovat välillä 500–1500.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_5.png)

Kun valitaan **Pienempi tai yhtä suuri kuin**, liukusäätimen vasemmalla oleva (pienempää arvoa osoittava) kahva katoaa ja vain liukusäätimen ylärajaa voidaan säätää. Seuraavassa kuvassa liukusäädin asetetaan arvoon 497,17.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_6.png)

Jos taas valitaan **Suurempi tai yhtä suuri kuin**, liukusäätimen oikea (suurinta arvoa osoittava) kahva katoaa ja pienempää arvoa voidaan säätää seuraavassa kuvassa osoitetulla tavalla. Nyt raporttisivun visualisoinneissa näytetään vain kohteet, joiden *UnitPrice* on suurempi tai yhtä suuri kuin 750,56.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_7.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer-preview"></a>Kokonaislukuihin kohdistaminen numeerisen alueen osittajalla (esikatselu)

**Power BI Desktopin** helmikuun 2018 versiosta alkaen numeerisen alueen osittaja kohdistuu kokonaislukuihin. Näin osittaja voi tasata siististi kokonaislukuihin. Kokonaislukuihin kohdistaminen ei koske desimaalisuodattimia.


## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioon otettavat seikat
**Numeerisen alueen osittajaa** koskevat tällä hetkellä seuraavat rajoitukset ja huomioon otettavat seikat

* **Numeerisen alueen osittaja** suodattaa tällä hetkellä kaikki tietojen pohjana olevat rivit eikä koostettuja arvoja. Esimerkiksi jos käytetään kenttää *Myynnin määrä*, suodatetaan jokainen kenttään *Myynnin määrä* pohjautuva tapahtuma eikä summaa, joka saadaan visualisoinnin kunkin arvopisteen *Myynnin määrä* -kentistä.
* Osittaja ei tällä hetkellä toimi Mittayksiköiden kanssa
* Tällä hetkellä **numeerisen alueen osittaja** on saatavilla vain **Power BI Desktopiin**. Jos **numeerista alueen osittajaa** käyttävä raportti on julkaistu **Power BI -palveluun**, suodatinta käytetään edelleen, mutta se näkyy luettelo-osittajana.

