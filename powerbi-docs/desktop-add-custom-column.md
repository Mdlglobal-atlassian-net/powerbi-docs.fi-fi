---
title: Mukautettujen sarakkeiden lisääminen Power BI Desktopissa
description: Luo uusi mukautettu sarake nopeasti Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/18/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 443053bc973005d3e2a655b1222d049a4251e7d7
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878866"
---
# <a name="add-a-custom-column-in-power-bi-desktop"></a>Mukautettujen sarakkeiden lisääminen Power BI Desktopissa

Power BI Desktopissa voit helposti lisätä malliisi uuden mukautetun tietosarakkeen käyttämällä kyselyeditoria. Kyselyeditorin avulla voit luoda ja nimetä uudelleen mukautetun sarakkeen ja luoda näin [PowerQuery M -kaavakyselyitä](https://docs.microsoft.com/powerquery-m/quick-tour-of-the-power-query-m-formula-language) mukautetun sarakkeen määrittämistä varten. PowerQuery M -kaavakyselyillä on [kattava funktion viittauksen sisältöjoukko](https://docs.microsoft.com/powerquery-m/power-query-m-function-reference). 

Kun luot mukautetun sarakkeen kyselyeditorissa, Power BI Desktop lisää sen **käytössä olevaksi vaiheeksi** kyselyn **kyselyasetuksiin**. Sitä voidaan muuttaa, siirtää tai muokata milloin tahansa.

![Lisää mukautettu sarake -sivu](media/desktop-add-custom-column/add-custom-column_01.png)

## <a name="use-query-editor-to-add-a-custom-column"></a>Mukautetun sarakkeen lisääminen kyselyeditorin avulla

Jos haluat aloittaa mukautetun sarakkeen luomisen, toimi seuraavasti:

1. Käynnistä Power BI Desktop ja lataa joitakin tietoja.

2. Valitse valintanauhan **Aloitus**-välilehdestä **Muokkaa kyselyitä** ja valitse sitten valikosta **Muokkaa kyselyitä**.

   ![Valitse Muokkaa kyselyitä](media/desktop-add-custom-column/add-column-from-example_02.png)

   Näyttöön tulee **Kyselyeditori**-ikkuna. 

2. Valitse valintanauhan **Lisää sarake** -välilehdestä **Mukautettu sarake**.

   ![Valitse mukautettu sarake](media/desktop-add-custom-column/add-custom-column_02.png)

   Näyttöön tulee **Lisää mukautettu sarake** -ikkuna.

## <a name="the-add-custom-column-window"></a>Lisää mukautettu sarake -ikkuna

**Lisää mukautettu sarake** -ikkunassa on seuraavat ominaisuudet: 
- Käytettävissä olevat sarakkeet oikealla olevassa **Käytettävissä olevat sarakkeet** -luettelossa.

- Mukautetun sarakkeen alkuperäinen nimi **Uuden sarakkeen nimi** -ruudussa. Voit nimetä tämän sarakkeen uudelleen.

- [PowerQuery M -kaavakyselyt](https://docs.microsoft.com/powerquery-m/power-query-m-function-reference) **Mukautettu sarakekaava** -ruudussa. Voit luoda nämä kyselyt luomalla kaavan, johon uusi mukautettu sarakkeesi on määritetty. 

   ![Lisää mukautettu sarake -sivu](media/desktop-add-custom-column/add-custom-column_03.png)

## <a name="create-formulas-for-your-custom-column"></a>Mukautetun sarakkeen kaavojen luominen

1. Valitse oikealla olevasta **Käytettävissä olevat sarakkeet** -luettelosta sarake ja lisää se mukautetun sarakkeen kaavaan valitsemalla luettelon alapuolelta **Lisää**. Voit myös lisätä sarakkeen kaksoisnapsauttamalla sitä luettelossa.

2. Kun kirjoitat kaavan ja luot sarakkeesi, huomaa ilmaisin **Lisää mukautettu sarake** -ikkunan alaosassa. 

   Jos virheitä ei ole, näet vihreän valintamerkin ja viestin *Syntaksi virheitä ei ole havaittu*.

   ![Onnistunut syntaksin tarkistus Lisää mukautettu sarake -sivulla](media/desktop-add-custom-column/add-custom-column_04.png)

   Syntaksivirheen sattuessa näet keltaisen varoituskuvakkeen sekä linkin, joka ohjaa kaavan kohtaan, jossa virhe ilmeni.

   ![Virhe Lisää mukautettu sarake -sivulla](media/desktop-add-custom-column/add-custom-column_05.png)

3. Valitse **OK**. 

   Power BI Desktop lisää malliin mukautetun sarakkeen ja lisää **Lisätty mukautettu** -vaiheen kyselyn **Käytössä olevat vaiheet**-luetteloon kohdassa **Kyselyasetukset**.

   ![Kyselyasetuksiin lisätty mukautettu sarake](media/desktop-add-custom-column/add-custom-column_06.png)

4. Jos haluat muokata mukautettua saraketta, kaksoisnapsauta **Lisätty mukautettu** -vaihetta **Käytössä olevat vaiheet** -luettelossa. 

   **Lisää mukautettu sarake** -ikkuna, jossa on luomasi mukautettu sarakekaava.

## <a name="use-the-advanced-editor-for-custom-columns"></a>Laajennetun editorin käyttö mukautettuihin sarakkeisiin

Kun olet luonut kyselyn, voit myös muokata mitä tahansa kyselyn vaihetta **laajennetun editorin** avulla. Toimi seuraavasti:

1. Valitse **Kyselyeditori**-ikkunassa valintanauhan **Näytä**-välilehti. 

2. Valitse **Laajennettu editori**.

   Näyttöön tulee **Laajennettu editori** -sivu, joka antaa kyselyyn täydet oikeudet. 

   ![Laajennettu editori -sivu](media/desktop-add-custom-column/add-custom-column_07.png)

   
## <a name="next-steps"></a>Seuraavat vaiheet

- Voit luoda mukautetun sarakkeen myös muulla tavoin, mukaan lukien sarakkeen luominen niiden esimerkkien avulla, jotka annat kyselyeditoriin. Lisätietoja on kohdassa [Sarakkeen lisääminen esimerkistä Power BI Desktopissa](desktop-add-column-from-example.md).

- Voit lukea Power Query M -viitetiedoista kohdassa [Power Query M -funktion viite](/powerquery-m/power-query-m-function-reference).

