---
title: PDF-tiedostoon yhdistäminen Power BI Desktopissa
description: PDF-tiedostojen tietoihin yhdistäminen ja tietojen käyttäminen helposti Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: d9d506052428e96ccaaed67e8b98733dd988d192
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73876382"
---
# <a name="connect-to-a-pdf-file-in-power-bi-desktop"></a>PDF-tiedostoon yhdistäminen Power BI Desktopissa
Power BI Desktopissa voi muodostaa yhteyden **PDF-tiedostoon** ja käyttää sen sisältämiä tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa.

![PDF-tiedostojen tietoihin yhdistäminen](media/desktop-connect-pdf/connect-pdf-04.png)

Seuraavissa osioissa kuvataan, miten voit muodostaa yhteyden **PDF-tiedostoon**, valita tiedot ja tuoda ne **Power BI Desktopiin**.

Suosittelemme aina päivittämään **Power BI Desktopin** uusimpaan versioon, jonka saat [Hae Power BI Desktop](desktop-get-the-desktop.md) -linkistä. 

## <a name="connect-to-a-pdf-file"></a>PDF-tiedostoon yhdistäminen
Jos haluat muodostaa yhteyden **PDF**-tiedostoon, valitse Power BI Desktopissa **Aloitus**-valintanauhasta **Nouda tiedot**. Valitse vasemmalla näkyvistä luokista **Tiedosto**, jolloin näkyviin tulee **PDF**.

![Valitse PDF Nouda tiedot -kohdassa](media/desktop-connect-pdf/connect-pdf-01.png)

Sinua pyydetään antamaan käytettävän PDF-tiedoston sijainti. Kun olet antanut tiedoston sijainnin ja PDF-tiedosto ladataan, näyttöön avautuu **Siirtymistoiminto**-ikkuna, jossa näet tiedostossa käytettävissä olevat tiedot. Voit valita ikkunasta yhden tai useita elementtejä tuotavaksi **Power BI Desktopiin**.

![PDF-tiedostojen tietoihin yhdistäminen](media/desktop-connect-pdf/connect-pdf-04.png)

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

