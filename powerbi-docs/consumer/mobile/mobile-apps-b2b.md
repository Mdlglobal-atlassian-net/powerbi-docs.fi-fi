---
title: Power BI -sisällön tarkasteleminen ulkopuolisena vieraskäyttäjänä (Azure AD B2B)
description: Power BI -mobiilisovellusten avulla voit tarkastella sisältöä, joka on jaettu kanssasi ulkoisesta organisaatiosta.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 12/09/2019
ms.author: painbar
ms.openlocfilehash: c5e1e0b90f24a81940edab46633f49df41d25fdc
ms.sourcegitcommit: 02b05932a119527f255e1eacc745a257044e392f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/19/2019
ms.locfileid: "75219852"
---
# <a name="view-power-bi-content-shared-with-you-from-an-external-organization"></a>Kanssasi ulkoisesta organisaatiosta jaetun Power BI -sisällön tarkasteleminen

Power BI on integroitu Azure Active Directory Business-to-Businessin (Azure AD B2B) kanssa, jotta Power BI -sisältöä voidaan jakaa turvallisesti organisaation ulkopuolisten vierailevien käyttäjien kanssa. Ulkoiset vieraskäyttäjät voivat käyttää Power BI -mobiilisovellusta ja käyttää jaettua Power BI -sisältöä sen avulla. 


Koskee seuraavia:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android-puhelin](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android-tabletti](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |

## <a name="accessing-shared-content"></a>Jaetun sisällön käyttäminen

**Tarvitset ensin ulkoisesta organisaatiosta henkilön, joka jakaa kohteen kanssasi.** Kun joku [jakaa kohteen kanssasi](../../service-share-dashboards.md), joko samasta organisaatiosta tai ulkoisesta organisaatiosta, saat sähköpostiviestin, jossa on linkki kyseiseen jaettuun kohteeseen. Kun avaat linkin mobiililaitteessasi, Power BI -mobiilisovellus avautuu. Jos sovellus tunnistaa, että kohde on jaettu ulkoisesta organisaatiosta, sovellus muodostaa yhteyden kyseiseen organisaatioon käyttäjätietojesi avulla. Sovellus lataa sitten kaikki kohteet, jotka on jaettu kanssasi kyseisestä organisaatiosta.

![Power BI avaa jaetun kohteen sähköpostista ](./media/mobile-apps-b2b/mobile-b2b-open-item-email-new.png)

> [!NOTE]
> Jos tämä on ensimmäinen kohde, joka on jaettu kanssasi ulkoisena vieraskäyttäjänä, sinun on lunastettava kutsu selaimessa. Et voi lunastaa kutsua Power BI -sovelluksessa.

Kun olet yhteydessä ulkoiseen organisaatioon, sovelluksessa näkyy musta ylätunniste. Tämä ylätunniste ilmaisee, että et ole muodostanut yhteyttä kotiorganisaatioosi. Jos haluat muodostaa yhteyden takaisin kotiorganisaatioosi, poistu vierastilasta.

![Power BI:n vieraskäyttäjän otsikko](./media/mobile-apps-b2b/mobile-b2b-exit-home-new.png)

Vaikka sinulla on oltava Power BI:n artefaktin linkki ulkoiseen organisaatioon yhdistämistä varten, voit käyttää kaikkia kanssasi jaettuja kohteita (ei vain sähköpostista avaamaasi kohdetta) sovelluksen siirtymisen jälkeen. Jos haluat nähdä kaikki kohteet, joita voit käyttää ulkoisessa organisaatiossa, siirry sovellusvalikkoon ja valitse **Jaettu kanssani**. **Sovellukset**-kohdasta löydät sovelluksia, joita voit myös käyttää.

![Power BI -sovellusvalikko vieraana ulkoisena käyttäjänä](./media/mobile-apps-b2b/mobile-b2b-menu-new.png)

## <a name="limitations"></a>Rajoitukset

- Käyttäjillä on oltava aktiivinen Power BI -tili ja aloitusvuokraaja.
- Käyttäjien on oltava kirjautuneina Power BI -aloitusvuokraajaan, ennen kuin he voivat käyttää sisältöä, joka on jaettu heidän kanssaan ulkoisesta vuokraajasta.
- Ehdollista käyttöä ja muita Intune-käytäntöjä ei tueta Azure AD B2B:ssä ja Power BI -mobiilisovelluksessa. Tämä tarkoittaa sitä, että sovellus valvoo vain kotiorganisaation käytäntöjä, jos sellaisia on.
- Palveluilmoitukset vastaanotetaan vain kotiorganisaation sivustolta (silloinkin, kun käyttäjä on yhdistetty vieraana ulkoiseen organisaatioon). Ilmoituksen avaaminen yhdistää sovelluksen uudelleen käyttäjän kotiorganisaation sivustoon.
- Jos käyttäjä sulkee sovelluksen, sovellus muodostaa automaattisesti yhteyden käyttäjän kotiorganisaatioon, kun sovellus avataan uudelleen.
- Kun yhteys ulkoiseen organisaatioon on muodostettu, seuraavat toiminnot on poistettu käytöstä: suosikkikohteet, tietoilmoitukset, kommentointi ja jakaminen.
- Offline-tiedot eivät ole käytettävissä, kun yhteys on muodostettu ulkoiseen organisaatioon.
- Jos sinulla on Yritysportaali-sovellus asennettuna laitteeseesi, laitteen on oltava rekisteröity.
