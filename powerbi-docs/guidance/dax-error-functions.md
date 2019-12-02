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
ms.openlocfilehash: 4730e835c511153232f79c193de5bbd56d63b963
ms.sourcegitcommit: f1f57c5bc6ea3057007ed8636ede50188ed90ce1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/23/2019
ms.locfileid: "74410915"
---
# <a name="dax-appropriate-use-of-error-functions"></a>DAX: Virhefunktioiden asianmukainen käyttö

Kun kirjoitat tietomallintajana DAX-lauseketta, joka saattaa aiheuttaa arviointiaikavirheen, voit harkita kahden hyödyllisen DAX-funktion käyttämistä.

- [ISERROR](/dax/iserror-function-dax)-funktio palauttaa yksittäiselle lausekkeelle arvon TOSI, jos lauseke aiheuttaa virheen.
- [IFERROR](/dax/iferror-function-dax)-funktiota käytetään kahdelle lausekkeelle. Jos ensimmäisen lausekkeen tulos on virhe, palautetaan toisen lausekkeen arvo. Toisin sanoen se toimii optimoituna ISERROR-funktion upotuksena [IF](/dax/if-function-dax)-funktioon.

Vaikka näistä funktioista voi olla hyötyä ja ne voivat auttaa kirjoittamaan helposti ymmärrettäviä lausekkeita, ne voivat myös heikentää laskutoimitusten suoritustehoa merkittävästi. Näin voi käydä, koska nämä funktiot lisäävät tarvittavien säilömoduulitarkistusten määrää.

Useimmat arviointiaikavirheet johtuvat odottamattomista tyhjistä arvoista tai nolla-arvoista tai virheellisestä tietotyyppimuunnosta.

## <a name="recommendations"></a>Suositukset

On parempi välttää ISERROR-ja IFERROR-funktioiden käyttöä. Käytä sen sijaan ennaltaehkäiseviä strategioita, kun kehität mallia ja kirjoitat lausekkeita. Strategioita voivat olla esimerkiksi seuraavat:

- **Varmista, että malliin ladatut tiedot ovat korkealaatuisia:** Power Query -muunnosten avulla voit poistaa tai korvata virheellisiä tai puuttuvia arvoja sekä määrittää oikeita tietotyyppejä. Power Query -muunnosta voidaan käyttää myös rivien suodattamiseen, kun virheet liittyvät esimerkiksi virheelliseen tietomuunnokseen.

    Tietojen laatua voidaan myös hallita asettamalla mallisarakkeen **Tukee tyhjäarvoja** -ominaisuus pois käytöstä, jolloin tietoja ei hyväksytä, jos niissä on tyhjiä arvoja. Jos tämä virhe ilmenee, onnistuneen päivityksen tuloksena ladatut tiedot säilyvät taulukoissa.
- **IF-funktion käyttö:** IF-funktion loogisen testin lausekkeella voidaan selvittää virhetuloksen esiintyminen. Huomaathan, että ISERROR-ja IFERROR-funktioiden tapaan tämä funktio voi aiheuttaa lisää säilömoduulitarkistuksia, mutta se todennäköisesti toimii niitä paremmin, koska se ei vaadi virheilmoitusta.
- **Virhesietoisten funktioiden käyttö:** Jotkin DAX-Funktiot testaavat ja kompensoivat virhe-ehtoja. Näiden funktioiden avulla voit antaa vaihtoehtoisen tuloksen, joka palautetaan virheellisen sijaan. [DIVIDE](/dax/divide-function-dax)-funktio on esimerkki tästä. Saat lisäohjeita tästä funktiosta lukemalla artikkelin [DAX: DIVIDE-funktion ja jako-operaattorin (/) vertailu](dax-divide-function-operator.md).

## <a name="example"></a>Esimerkki

Seuraava mittarilauseke testaa virheiden esiintymistä. Se palauttaa tyhjän arvon tässä esiintymässä (kuten silloin, kun et anna IF-lausekkeelle arvo jos epätosi -lauseketta).

```dax
Profit Margin
= IF(ISERROR([Profit] / [Sales]))
```

Tätä mittarilausekkeen seuraavaa versiota on parannettu käyttämällä IFERROR-funktiota IF-ja ISERROR-funktioiden sijaan.

```dax
Profit Margin
= IFERROR([Profit] / [Sales], BLANK())
```

Tämä mittarilausekkeen lopullinen versio tuottaa saman tuloksen, mutta tehokkaammin ja tyylikkäämmin.

```dax
Profit Margin
= DIVIDE([Profit], [Sales])
```

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Data Analysis Expressions (DAX) -viittaukset](/dax/)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
