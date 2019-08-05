---
title: Analytiikkaruutu
description: Dynaamisten viiteviivojen luominen Power BI:n visualisoinneissa
author: Guy-Moses
ms.author: guymos
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b3b50f8dbcf40a3923e86422e24f8ed020894445
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425524"
---
# <a name="analytics-pane-in-power-bi-visuals"></a>Analytiikkaruutu Power BI:n visualisoinneissa

**Analytiikkaruutu** [otettiin käyttöön alkuperäisissä visualisoinneissa](https://docs.microsoft.com/power-bi/desktop-analytics-pane) marraskuussa 2018.
Mukautetut visualisoinnit, joissa on ohjelmointirajapinta v2.5.0, voivat esittää ja hallita ominaisuuksiaan **analytiikkaruudussa**.

![Analytiikkaruutu](./media/visualization-pane-analytics-tab.png)

Sitä käsitellään samalla tavalla kuin [ominaisuuksien hallintaa Muotoilu-ruudussa](https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial-format-options) määrittämällä objekti visualisoinnin capabilities.json-tiedostossa. 

Erot ovat seuraavat:

1. Lisää `object`-kohteen määritykseen `objectCategory`-kenttä, jonka arvo on 2.

    > [!NOTE]
    > `objectCategory`-kenttä on ohjelmointirajapinta 2.5.0:ssa käyttöön otettu valinnainen kenttä. Se määrittää visualisoinnin aspektin, jota objekti valvoo (1 = muotoilu, 2 = analytiikka). Muotoilua käytetään esimerkiksi ulkoasussa, väreissä, akseleissa ja otsikoissa. Analytiikkaa käytetään esimerkiksi ennusteissa, trendiviivoissa, viiteriveillä ja muodoissa.
    >
    > `objectCategory`-kentän oletusarvona on Muotoilu, jos arvoa ei määritetä.

2. Objektilla on oltava seuraavat kaksi ominaisuutta:
    1. `show` tyyppiä totuusarvo, oletusarvona on epätosi.
    2. `displayName` tyyppiä teksti. Valitsemastasi oletusarvosta tulee esiintymän ensimmäinen näyttönimi.

```json
{
  "objects": {
    "YourAnalyticsPropertiesCard": {
      "displayName": "Your analytics properties card's name",
      "objectCategory": 2,
      "properties": {
        "show": {
          "type": {
            "bool": true
          }
        },
        "displayName": {
          "type": {
            "text": true
          }
        },
      ... //any other properties for your Analytics card
      }
    }
  ...
  }
}
```

Muut ominaisuudet voidaan määrittää samalla tavalla kuin Muotoilu-objekteille. Objektien luettelointi tehdään täsmälleen samalla tavalla kuin **Muotoilu-ruudussa**.

***Tunnetut rajoitukset ja ongelmat***

  1. Ei vielä usean esiintymän tukea. Objekteilla ei voi olla muuta [valitsinta](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties/#selector) staattinen (eli ”valitsin”: tyhjäarvo), eikä mukautetuilla visualisoinneilla voi olla käyttäjän määrittämiä useita esiintymiä kortista.
  2. `integer`-tyyppisiä ominaisuuksia ei näytetä oikein. Voit kiertää ongelman käyttämällä sen sijaan `numeric`-tyyppiä.

> [!NOTE]
> Käytä Analytiikka-ruutua vain objekteille, jotka lisäävät uusia tietoja tai kertovat enemmän esitetyistä tiedoista. Tällaisia ovat esimerkiksi dynaamiset viiterivit, jotka kuvaavat tärkeitä trendejä.
> Kaikki asetukset, jotka ohjaavat visualisoinnin ulkoasua eli siis muotoilua, on säilytettävä Muotoilu-ruudussa.
