---
title: 'DAX: Virhefunktioiden asianmukainen käyttö'
description: Lue ohjeet DAX-virhefunktioiden käyttöön.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: v-pemyer
ms.openlocfilehash: ae4e9081930b0f6934a557ba45afd99dd8dfc05d
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875630"
---
# <a name="dax-appropriate-use-of-error-functions"></a>DAX: Virhefunktioiden asianmukainen käyttö

Tämä artikkeli on tarkoitettu tietojen mallintajille, jotka määrittävät DAX-lausekkeita.

## <a name="background"></a>Tausta

Kun kirjoitat DAX-lauseketta, joka saattaa aiheuttaa arviointiaikavirheen, voit harkita kahden hyödyllisen DAX-funktion käyttämistä.

- [ISERROR](/dax/iserror-function-dax)-funktio palauttaa yksittäiselle lausekkeelle arvon TOSI, jos lauseke aiheuttaa virheen.
- [IFERROR](/dax/iferror-function-dax)-funktiota käytetään kahdelle lausekkeelle. Jos ensimmäisen lausekkeen tulos on virhe, palautetaan toisen lausekkeen arvo. Toisin sanoen se toimii optimoituna ISERROR-funktion upotuksena [IF](/dax/if-function-dax)-funktioon.

Vaikka näistä funktioista voi olla hyötyä ja ne voivat auttaa kirjoittamaan helposti ymmärrettäviä lausekkeita, ne voivat myös heikentää laskutoimitusten suoritustehoa merkittävästi. Tämä johtuu siitä, että nämä funktiot lisäävät tarvittavien säilömoduulitarkistusten määrää.

Huomaathan, että useimmat arviointiaikavirheet johtuvat odottamattomista tyhjistä arvoista tai nolla-arvoista tai virheellisestä tietotyyppimuunnosta.

## <a name="recommendations"></a>Suositukset

On parempi välttää ISERROR-ja IFERROR-funktioiden käyttöä. Käytä sen sijaan ennaltaehkäiseviä strategioita, kun kehität mallia ja kirjoitat lausekkeita. Näitä voivat olla seuraavat:

- **Varmista, että malliin ladatut tiedot ovat korkealaatuisia:** Power Query -muunnosten avulla voit poistaa tai korvata virheellisiä tai puuttuvia arvoja sekä määrittää oikeita tietotyyppejä. Power Query -muunnosta voidaan käyttää myös rivien suodattamiseen, kun virheet liittyvät esimerkiksi virheelliseen tietomuunnokseen.

    Tietojen laatua voidaan myös hallita asettamalla mallisarakkeen **Tukee tyhjäarvoja** -ominaisuus pois käytöstä, jolloin tietoja ei hyväksytä, jos niissä on tyhjiä arvoja. Huomaathan, että jos tämä virhe ilmenee, onnistuneen päivityksen tuloksena ladatut tiedot säilyvät taulukoissa.
- **IF-funktion käyttö:** IF-funktion loogisen testin lauseketta voidaan käyttää virhetuloksen esiintymisen selvittämiseen. Huomaathan, että ISERROR-ja IFERROR-funktioiden tapaan tämä funktio voi aiheuttaa lisää säilömoduulitarkistuksia, mutta se todennäköisesti toimii niitä paremmin, koska se ei vaadi virheilmoitusta.
- **Virhesietoisten funktioiden käyttö:** Jotkin DAX-Funktiot testaavat ja kompensoivat virhe-ehtoja. Näiden funktioiden avulla voit antaa vaihtoehtoisen tuloksen, joka palautetaan virheellisen sijaan. [DIVIDE](/dax/divide-function-dax)-funktio on esimerkki tästä. Saat lisäohjeita tästä funktiosta lukemalla artikkelin [DAX: DIVIDE-funktion ja jako-operaattorin (/) vertailu](dax-divide-function-operator.md).

## <a name="example"></a>Esimerkki

Seuraava mittarilauseke testaa virheiden esiintymistä. Se palauttaa tyhjän arvon tässä esiintymässä (kuten silloin, kun et anna IF-lausekkeelle arvo jos epätosi -lauseketta).
```dax
= IF(ISERROR([Profit] / [Sales]))
```
Tätä mittarilausekkeen seuraavaa versiota on parannettu käyttämällä IFERROR-funktiota IF-ja ISERROR-funktioiden sijaan.
```dax
= IFERROR([Profit] / [Sales], BLANK())
```
Tämä mittarilausekkeen lopullinen versio tuottaa saman tuloksen, mutta tehokkaammin ja tyylikkäämmin.
```dax
= DIVIDE([Profit], [Sales])
```