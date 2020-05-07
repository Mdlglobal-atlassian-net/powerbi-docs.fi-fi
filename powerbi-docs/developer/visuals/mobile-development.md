---
title: Mobiilikehitys
description: Mobiilikäyttöön sopivien Power BI -visualisointien luominen
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 03/12/2019
ms.openlocfilehash: 38e6ac3be143381304f1fdfc8e1427b91f398a9a
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82196625"
---
# <a name="how-to-create-mobile-friendly-power-bi-visuals"></a>Mobiilikäyttöön sopivien Power BI -visualisointien luominen
Mobiilikulutuksella on merkittävä rooli Power BI:ssä. Yksi sen vahvuuksista on, että voit olla yhteydessä tietoihisi missä ja milloin tahansa.

Power BI -visualisointeja luovan kehittäjän on ajateltava kaikkien mobiililaitteiden yksilöllisiä rajoitteita, jotta tavoitetaan mahdollisimman monia käyttäjiä ja tuotetaan mahdollisimman hyvä mobiilikäyttökokemus.

[Windowsin, iOS:n tai Androidin Power BI -sovelluksella](/power-bi/consumer/mobile/mobile-apps-for-mobile-devices) voit antaa yrityksesi käyttäjille kattavan näkymän heidän tietoihinsa heidän matkoillaan ja tuoda tiedot heidän sormenpäidensä ulottuville.

## <a name="requirements"></a>Vaatimukset

Seuraavat vaatimukset ovat välttämättömiä visualisointien mobiililaiteystävällisen kehityksen kannalta:

- Hahmonnus

  Power BI -visualisointisi on voitava hahmontaa kaikissa tuetuissa mobiililaitteissa, kuten tuetuissa selaimissa ja sovelluksissa, ilman virheitä raporteissa, koontinäytöissä tai **Tarkastelu**tilassa suoritettaessa. 

- Vuorovaikutteisuus

  Vuorovaikutteiset toiminnot on tarjottava samalla tavalla kuin työpöytälaitteissa. Mobiililaitteissa on tuettava kaikkia työpöytäselaimissa käsiteltäviä tapahtumia tai vastaavia tapahtumakäsittelijöitä.
  
  Esimerkiksi perussiirtymisessä ja arvopisteiden valinnassa tulee olla samat toiminnot kuin työpöytäselaimissa. Jos visualisointi tukee monivalintatoimintoa **Ctrl**-näppäimen avulla, kehittäjän on harkittava samanlaisen tapahtumakäsittelijän lisäämistä mobiililaitteita varten.

  Seuraavassa taulukossa on luettelo vastaavista tapahtumista mobiililaitteissa.

  | Hiiritapahtuman nimi | Kosketustapahtuman nimi |
  |:----------------:|:----------------:|
  | `click` | `click` |
  | `mousemove` | `touchmove` |
  | `mousedown` | `touchstart` |
  | `mouseup` | `touchend` |
  | `dblclick` | käytä ulkoista kirjastoa |
  | `contextmenu` | käytä ulkoista kirjastoa |
  | `mouseover` | `touchmove` |
  | `mouseout` | `touchmove` (tai ulkoinen kirjasto) |
  | `wheel` | `NaN` |

  > [!NOTE]
  > Kaikki mobiili- tai kosketusnäyttölaitteet eivät tue hiiritapahtumia (tai *hiiri*etuliitteisiä) tapahtumia. Käsittele tällaisissa tapauksissa sekä *hiiri*- että *kosketus*tapahtumat samalla kertaa.

## <a name="optional"></a>Valinnainen
Seuraavia pidetään valinnaisina tapahtumia, ja niitä käytetään käyttökokemuksen parantamiseen.

- Hahmonnus

  Jos haluat tukea pienempiä visualisointikokoja, kokeile lisätä muotoiluasetuksia, joita muuttamalla käyttäjä voi muuttaa jokaisen osan kokoa. Lisää esimerkiksi muotoiluasetuksia otsikoihin, joita käytetään raporteissa ja koontinäytöissä. Tämän avulla käyttäjät voivat mukauttaa visualisointia erityisesti omaa mobiililaitettaan varten.
  
  Visualisointeihin voidaan käyttää samoja asetuksia myös työpöytäselaimissa, ja tarvittaessa ne voidaan ohittaa, jotta visualisointi voidaan sovittaa pieniin näyttöihin.

  > [!NOTE]
  > Kun haluat optimoida visualisoinnin **Tarkastelu**-tilassa, sekä näytön pysty- että vaakasuunta vaativat harkintaa. Lue artikkeli [Sisällön näyttäminen Tarkastelutilassa](/power-bi/consumer/end-user-focus).

- Vuorovaikutteisuus

  Harkitse erityisesti mobiilikäyttöön tarkoitettujen tapahtumakäsittelijöiden, kuten vetämisen ja vierittämisen, lisäämistä.

- Vikasietoisuus

  Visualisoinnin tulee näyttää kuvaava virhesanoma, jos sitä ei voi hahmontaa mobiililaitteessa.

## <a name="supported-browsers-and-devices"></a>Tuetut selaimet ja laitteet
Power BI -visualisointi on voitava hahmontaa kaikissa Power BI -sovelluksia tukevissa laitteissa. Lisätietoja on kohdissa [Power BI:n tukemat selaimet](/power-bi/power-bi-browsers) ja [Power BI -mobiilisovellukset](/power-bi/consumer/mobile/mobile-apps-for-mobile-devices).

Kun testaus tehdään uusimmissa Windows-, iOS-ja Android-laitemalleissa, kehittäjän on otettava huomioon useimmat näistä laatunäkökohdista.

## <a name="next-steps"></a>Seuraavat vaiheet
Aloita katsomalla [Opetusohjelma: Power BI -visualisoinnin kehittäminen](/power-bi/developer/visuals/custom-visual-develop-tutorial).
