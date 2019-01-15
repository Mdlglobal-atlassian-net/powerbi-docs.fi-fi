---
title: PDF-tiedostoon yhdistäminen Power BI Desktopissa (esikatselu)
description: PDF-tiedostojen tietoihin yhdistäminen ja tietojen käyttäminen helposti Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: ff61c4d2cc8ec3570e7eee45b7e43ec81f8f7161
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54275107"
---
# <a name="connect-to-a-pdf-file-in-power-bi-desktop-preview"></a>PDF-tiedostoon yhdistäminen Power BI Desktopissa (esikatselu)
Power BI Desktopissa voi muodostaa yhteyden **PDF-tiedostoon** ja käyttää sen sisältämiä tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa.

![PDF-tiedostojen tietoihin yhdistäminen](media/desktop-connect-pdf/connect-pdf_04.png)

Seuraavissa osioissa kuvataan, miten voit muodostaa yhteyden **PDF-tiedostoon**, valita tiedot ja tuoda ne **Power BI Desktopiin**.

## <a name="enable-the-pdf-connector"></a>PDF-liittimen käyttöönotto
PDF-liitin on esikatselutilassa **Power BI Desktopissa**, ja se on otettava käyttöön. Ota PDF-liitin käyttöön valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset > Esikatselutoiminnot**. Valitse sitten **Hae tiedot PDF-tiedostoista** -valintaruutu. 

![Ota PDF-liitin käyttöön valitsemalla Asetukset > Esikatselutoiminnot](media/desktop-connect-pdf/connect-pdf_01.png)

Sinun täytyy käynnistää **Power BI Desktop** uudelleen tämän jälkeen.

Kun käytät **PDF-liitintä (beeta)** ensimmäistä kertaa, saat varoituksen siitä, että PDF-liitin on vielä kehitteillä, ja se voi muuttua myöhemmin. Käytä liitintä valitsemalla **Jatka**.

Suosittelemme aina päivittämään **Power BI Desktopin** uusimpaan versioon, jonka saat [Hae Power BI Desktop](desktop-get-the-desktop.md) -linkistä. 

## <a name="connect-to-a-pdf-file"></a>PDF-tiedostoon yhdistäminen
Jos haluat muodostaa yhteyden **PDF**-tiedostoon, valitse Power BI Desktopissa **Aloitus**-valintanauhasta **Nouda tiedot**. Valitse vasemmalla näkyvistä luokista **Tiedosto**, jolloin näkyviin tulee **PDF (beeta)**.

![Valitse PDF Nouda tiedot -kohdassa](media/desktop-connect-pdf/connect-pdf_01.png)

Sinua pyydetään antamaan käytettävän PDF-tiedoston sijainti. Kun olet antanut tiedoston sijainnin ja PDF-tiedosto ladataan, näyttöön avautuu **Siirtymistoiminto**-ikkuna, jossa näet tiedostossa käytettävissä olevat tiedot. Voit valita ikkunasta yhden tai useita elementtejä tuotavaksi **Power BI Desktopiin**.

![PDF-tiedostojen tietoihin yhdistäminen](media/desktop-connect-pdf/connect-pdf_04.png)

Kun valitset PDF-tiedostosta löydettyjen elementtien vieressä olevan valintaruudun, ne näkyvät oikeanpuoleisessa ruudussa. Kun olet valmis tuomaan, tuo tiedot **Power BI Desktopiin** napsauttamalla **Lataa** -painiketta.

**Power BI Desktopin** marraskuun 2018 julkaisusta alkaen voit määrittää **aloitussivun** ja **päätössivun** PDF-yhteyden valinnaisina parametreina. Voit myös määrittää nämä parametrit M-kaavan kielellä seuraavassa muodossa:

`Pdf.Tables(File.Contents("c:\sample.pdf"), [StartPage=10, EndPage=11])`


## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

