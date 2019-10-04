---
title: Power BI Desktopin tiedostojen (binaaritiedostot) yhdistäminen
description: Tiedostojen (binaarinen) helppo yhdistäminen tietolähteisiin Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 8a5b4c7cb484b296ccab395e18eb2b0089ffd5c7
ms.sourcegitcommit: e2c5d4561455c3a4806ace85defbc72e4d7573b4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/27/2019
ms.locfileid: "71327811"
---
# <a name="combine-files-binaries-in-power-bi-desktop"></a>Power BI Desktopin tiedostojen (binaaritiedostot) yhdistäminen
Yksi tehokas tapa tietojen tuomiseksi **Power BI Desktopiin** on yhdistää useita tiedostoja, joilla on sama rakenne ja yhdistää ne yhdeksi loogiseksi taulukoksi. Tämä kätevä ja suosittu lähestymistapa on entistä kätevämpi ja kattavampi, kuten tässä artikkelissa kerrotaan.

Aloita tiedostojen yhdistäminen samaan kansioon valitsemalla **Nouda tiedot > Tiedosto > Kansio**.

![](media/desktop-combine-binaries/combine-binaries_1.png)


## <a name="combine-files-behavior"></a>Yhdistettyjen tiedostojen toiminta
Voit **yhdistää tiedostoja (binaaritiedostoja)** valitsemalla **yhdistä tiedostot** joko **Aloitus**-valintanauhan välilehdestä **Kyselyeditorissa** tai itse sarakkeesta.

![](media/desktop-combine-binaries/combine-binaries_2a.png)

**Yhdistä tiedostot** toimii seuraavasti:

* **Yhdistä tiedostot** -toiminto analysoi kunkin syötetiedoston ja määrittää oikean tiedostomuodon, kuten *teksti* tai *Excel-työkirja* tai *JSON*-tiedosto.
* Muunnos antaa valita tietyn objektin ensimmäisestä tiedostosta, esimerkiksi *Excel-työkirjan*, poimittavaksi.
  
  ![](media/desktop-combine-binaries/combine-binaries_3.png)
* **Yhdistä tiedostot** suorittaa sitten seuraavat kyselyt automaattisesti:
  
  * Luo esimerkkikyselyn, joka suorittaa kaikki tarvittavat poimintavaiheet yhteen tiedostoon.
  * Luo *funktiokyselykyselyn*, joka parametrisoi tiedoston/binäärisyötteen *esimerkkikyselyyn*. Esimerkkikysely ja funktiokysely on linkitetty, jotta esimerkkikyselyyn tehdyt muutokset näkyvät funktiokyselyssä.
  * Koskee *funktiokyselyä* alkuperäiseen kyselyyn syötteen binaarein (esimerkiksi *Kansio* -kysely), joten se koskee funktiokyselyä jokaisella rivillä ja laajentaa sitten tuloksena saadut tiedot ylimmän tason sarakkeiksi.
    
    ![](media/desktop-combine-binaries/combine-binaries_4.png)

> [!NOTE]
> Excel-työkirjan valitun alueen koko vaikuttaa yhdistettävien binaaritiedostojen toimintaa. Voit esimerkiksi valita yhdistettäväksi tietyn laskentataulukon tai valita päätason, jos haluat yhdistää koko tiedoston. Kansion valitseminen yhdistää kansiossa olevat tiedostot. 


**Yhdistä tiedostot** -toiminnan avulla voit helposti yhdistää kaikki tiedostot kansion sisällä, kunhan niillä on sama tiedostotyyppi ja rakenne (esimerkiksi sama määrä sarakkeita).

Lisäksi voit helposti käyttää lisämuunnos- tai poimintavaiheita muokkaamalla automaattisesti luotua *esimerkkikyselyä*, eikä sinun tarvitse huolehtia uusien *funktiokyselyn* vaiheiden muokkaamisesta tai luomisesta. Tehdyt muutokset *esimerkkikyselyyn* luodaan automaattisesti linkitetyssä *funktiokyselyssä*.

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [CSV-tiedostoihin yhdistäminen Power BI Desktopissa](desktop-connect-csv.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

