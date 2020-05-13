---
title: Power BI Desktopin tiedostojen (binaaritiedostot) yhdistäminen
description: Tiedostojen (binaarinen) helppo yhdistäminen tietolähteisiin Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/13/2020
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 7840894d123fae1f7e760b15f4756796ef2af16a
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348639"
---
# <a name="combine-files-binaries-in-power-bi-desktop"></a>Power BI Desktopin tiedostojen (binaaritiedostot) yhdistäminen

Tässä on tehokas tapa tuoda tietoja **Power BI Desktopiin**: Jos sinulla on useita tiedostoja, joilla on sama rakenne, yhdistä ne yhdeksi loogiseksi taulukoksi. Tästä suositusta tekniikasta on tehty entistä kätevämpi ja laajempi.

Aloita tiedostojen yhdistäminen samasta kansiosta valitsemalla **Nouda tiedot**, valitse **Tiedosto** > **Kansio** ja valitse sitten **Yhdistä**.

![Kansiotiedostoon yhdistäminen, Hanki tiedot -valintaikkuna, Power BI Desktop](media/desktop-combine-binaries/combine-binaries_1.png)

Anna kansion polku, valitse **OK** ja valitse sitten **Muunna tiedot**, niin näet kansion tiedostot Power Query -editorissa.

## <a name="combine-files-behavior"></a>Yhdistettyjen tiedostojen toiminta

Jos haluat yhdistää binääritiedostoja Power Query -editorissa, valitse **Sisältö** (ensimmäisen sarakkeen nimi) ja valitse **Aloitus** > **Yhdistä tiedostot**. Tai voit vain valita **Yhdistä tiedostot** -kuvakkeen kohteen **Sisältö** vieressä.

![Yhdistä tiedostot -komento, Power Query -editori, Power BI Desktop](media/desktop-combine-binaries/combine-binaries_2a.png)

*Yhdistä tiedostot* toimii seuraavasti:

* Yhdistä tiedostot -toiminto analysoi kunkin syötetiedoston ja määrittää oikean tiedostomuodon, kuten *teksti*, *Excel-työkirja* tai *JSON-tiedosto*.
* Muunnos antaa valita tietyn objektin ensimmäisestä tiedostosta, kuten Excel-työkirjan, poimittavaksi.
  
  ![Yhdistä tiedostot -valintaikkuna, Power Query -editori, Power BI Desktop](media/desktop-combine-binaries/combine-binaries_3.png)
* Yhdistä tiedostot -muunnos suorittaa sitten automaattisesti seuraavat toimet:
  
  * Luo esimerkkikyselyn, joka suorittaa kaikki tarvittavat poimintavaiheet yhteen tiedostoon.
  * Luo *funktiokyselykyselyn*, joka parametrisoi tiedoston/binäärisyötteen *esimerkkikyselyyn*. Esimerkkikysely ja funktiokysely on linkitetty, jotta esimerkkikyselyyn tehdyt muutokset näkyvät funktiokyselyssä.
  * Soveltaa *toimintokyselyä* alkuperäiseen binaarisyötteelliseen kyselyyn, kuten *Kansio*-kyselyyn. Se soveltaa toimintokyselyä kunkin rivin binäärisyötteisiin ja laajentaa tuloksena saatavat tietopoiminnat ylimmän tason sarakkeiksi.

    ![Yhdistä tiedostot -muunnoksen tulokset, Power Query -editori, Power BI Desktop](media/desktop-combine-binaries/combine-binaries_4.png)

> [!NOTE]
> Excel-työkirjan valitun alueen koko vaikuttaa yhdistettävien binaaritiedostojen toimintaa. Voit esimerkiksi valita yhdistettäväksi tietyn laskentataulukon tai valita päätason, jos haluat yhdistää koko tiedoston. Kansion valitseminen yhdistää kansiossa olevat tiedostot. 

Tiedostojen yhdistämiskäyttäytymisen avulla voit helposti yhdistää kaikki tiedostot tietyn kansion sisällä, jos niillä on sama tiedostotyyppi ja rakenne (esimerkiksi sama määrä sarakkeita).

Lisäksi voit helposti käyttää lisämuunnos- tai poimintavaiheita muokkaamalla automaattisesti luotua esimerkkikyselyä, eikä sinun tarvitse huolehtia uusien funktiokyselyn vaiheiden muokkaamisesta tai luomisesta. Tehdyt muutokset esimerkkikyselyyn luodaan automaattisesti linkitetyssä funktiokyselyssä.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit muodostaa yhteyden kaikenlaisiin tietoihin käyttämällä Power BI Desktopia. Lisätietoja näistä tietolähteistä saat perehtymällä seuraaviin resursseihin:

* [Mikä on Power BI Desktop?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](../connect-data/desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](../connect-data/desktop-shape-and-combine-data.md)
* [CSV-tiedostoihin yhdistäminen Power BI Desktopissa](../connect-data/desktop-connect-csv.md)
* [Tietojen antaminen suoraan Power BI Desktopiin](../connect-data/desktop-enter-data-directly-into-desktop.md)
