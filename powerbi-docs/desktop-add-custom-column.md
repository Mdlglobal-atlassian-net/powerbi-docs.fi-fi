---
title: Mukautettujen sarakkeiden lisääminen Power BI Desktopissa
description: Luo uusi mukautettu sarake nopeasti Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 3ea3aa22a2ab76df115c1b4784d74dedfdf7dbf0
ms.sourcegitcommit: 05303d3e0454f5627eccaa25721b2e0bad2cc781
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/28/2018
ms.locfileid: "52578654"
---
# <a name="add-a-custom-column-in-power-bi-desktop"></a>Mukautettujen sarakkeiden lisääminen Power BI Desktopissa
Voit helposti lisätä uuden mukautetun tietosarakkeen mallin avulla **Kyselyeditoria** - **Power BI Desktopia**. Voit luoda ja nimetä mukautetun sarakkeen helppokäyttöisten painikkeiden avulla käyttämällä [M-kaavoja](https://msdn.microsoft.com/library/mt270235.aspx) , joka määrittävät mukautetun sarakkeen. M-kaava on [kattavan funktion viittauksen sisältöjoukko](https://msdn.microsoft.com/library/mt779182.aspx). 

![](media/desktop-add-custom-column/add-custom-column_01.png)

Mukautetun sarakkeen luominen on toinen **käytetty vaihe** kyselyssä, jonka luot **Kyselyeditorissa**, mikä tarkoittaa, että sitä voidaan muuttaa, siirtää aiemmaksi tai myöhemmäksi tai muokata milloin tahansa.

## <a name="use-query-editor-to-add-a-new-custom-column"></a>Uuden mukautetun sarakkeen lisääminen kyselyeditorin avulla
Jos haluat luoda uuden mukautetun sarakkeen, käynnistä **Kyselyeditori**. Voit käynnistää Kyselyeditorin valitsemalla **Power BI Desktopin** **Aloitus**-valintanauhasta **Muokkaa kyselyitä**.

![](media/desktop-add-custom-column/add-column-from-example_02.png)

Kun **Kyselyeditori** on käynnistetty ja sinulla on joitakin ladattuja tietoja, voit lisätä mukautetun sarakkeen valitsemalla **Lisää sarake** -välilehti valintanauhasta ja valitsemalla sitten **Mukautettu sarake** .

![](media/desktop-add-custom-column/add-custom-column_02.png)

**Lisää mukautettu sarake** -ikkuna ilmestyy näkyviin. Se kuvaillaan seuraavassa osassa.

## <a name="the-add-custom-column-window"></a>Lisää mukautettu sarake -ikkuna
**Lisää mukautettu sarake** -ikkunassa näkyviin ruutuun oikealla ylhäällä tulee luettelo käytettävissä olevista kentistä (voit nimetä sen uudelleen kirjoittamalla uuden nimen kyseiseen tekstiruutuun), sekä [ **M** -kaava](https://msdn.microsoft.com/library/mt779182.aspx), jonka luot (tai kirjoitat) perusteena lisättävät kentät oikealla, lisäämällä operaattorit ja kehittämällä muulla tavoin kaavan, jolle uusi mukautettu sarake määritetään. 

![](media/desktop-add-custom-column/add-custom-column_03.png)

## <a name="create-formulas-for-your-custom-column"></a>Mukautetun sarakkeen kaavojen luominen
Voit valita kentän kohdasta **Käytettävissä olevat sarakkeet:** oikeanpuoleisesta luettelosta ja valita **<< Lisää** lisätäksesi ne mukautetun sarakkeen kaavan. Voit yksinkertaisesti kaksoisnapsauttaa luettelon saraketta sen lisäämiseksi.

Kun kirjoitat kaavaa ja muodostat sarakkeen, ikkunan alareunassa näkyy ilmaisin, joka kertoo reaaliaikaisesti (samalla kuin kirjoitat), onko syntaksivirheitä havaittu. Jos kaikki on kunnossa, esiin tulee vihreä valintamerkki.

![](media/desktop-add-custom-column/add-custom-column_04.png)

Jos syntaksissa on jonkinlainen virhe, näyttöön tulee keltainen varoituskuvake sekä havaittu virhe ja linkki, joka asettaa kohdistimen (kaavassa) kohtaan, jossa virhe havaitaan.

![](media/desktop-add-custom-column/add-custom-column_05.png)

Kun valitset **OK**, mukautettu sarake lisätään malliin ja **Lisätty mukautettu** -vaihe lisätään kyselyn **käytettyihin vaiheisiin**.

![](media/desktop-add-custom-column/add-custom-column_06.png)

Jos kaksoisnapsautat **Lisätty mukautettu** -vaihetta **Käytetyt vaiheet** -ruudussa, **Lisää mukautettu sarake** -ikkuna tulee uudelleen esiin jo ladatun luomasi mukautetun sarakkeen kaavan kanssa, ja voit muokata sitä tarvittaessa.

## <a name="using-the-advanced-editor-for-custom-columns"></a>Laajennetun editorin käyttö mukautettuihin sarakkeisiin
Voit myös luoda mukautetun sarakkeen (ja muokata mitä tahansa kyselysi vaihetta) käyttämällä **laajennettua editoria**. Valitse **Kyselyeditorissa** **Näkymä**-välilehti ja valitse sitten **Laajennettu editori** nähdäksesi **laajennetun editorin**.

![](media/desktop-add-custom-column/add-custom-column_07.png)

**Laajennettu editori** antaa kyselyyn täydet oikeudet.

## <a name="next-steps"></a>Seuraavat vaiheet
On olemassa myös muita tapoja luoda mukautettu sarake, mukaan lukien sarakkeen luominen niiden esimerkkien avulla, jotka annat **Kyselyeditoriin**. Katso seuraavasta artikkelista lisätietoja mukautettujen sarakkeiden luomisesta esimerkeistä:

* [Sarakkeen lisääminen esimerkistä Power BI Desktopissa](desktop-add-column-from-example.md)
* [Johdanto M-kaavan kieleen](https://msdn.microsoft.com/library/mt270235.aspx)
* [M-funktion viite](https://msdn.microsoft.com/library/mt779182.aspx)  

