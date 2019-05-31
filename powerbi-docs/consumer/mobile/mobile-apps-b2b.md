---
title: Tarkastele Power BI-sisällön ulkoisen Vieras käyttäjänä (Azure AD B2B)
description: Power BI-mobiilisovellusten avulla voit tarkastella ulkoisen organisaatiosta kanssasi jaettua sisältöä.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/27/2019
ms.author: mshenhav
ms.openlocfilehash: a15da4349ce97e34c8321909abc862e424b2839c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61338696"
---
# <a name="view-power-bi-content-shared-with-you-from-an-external-organization"></a>Näytä Power BI-sisältö on jaettu ulkoisen organisaatiosta

Power BI on integroitu Azure Active Directory business-to-Businessin (Azure AD B2B), jotta Power BI-sisältöä organisaatiosi ulkopuolisten vierailevien käyttäjien kanssa. Ja ulkoisen vierailevien käyttäjien käyttää Power BI-mobiilisovelluksen kyseisen Power BI-sisältöä, joka on jaettu heidän kanssaan. 


Koskee seuraavia:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android-puhelin](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android-tabletti](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |

## <a name="accessing-shared-content"></a>Käytettäessä jaettua sisältöä

**Ensin sinun täytyy joku jakaa kohteen kanssasi ulkoisen organisaatiosta.** Kun joku [kohde jakaa sinulle](../../service-share-dashboards.md), sama organisaatio tai ulkoinen organisaatio, saat sähköpostiviestin, jossa on linkki, joka on jaettu kohde. Seuraavan linkin mobiililaitteeseesi avautuu Power BI-mobiilisovelluksessa. Jos sovellus tunnistaa kohde on jaettu ulkoisen organisaatiosta, sovellus muodostaa kyseisen organisaation käyttäjätietojen yhteydessä. Sovelluksen lataa sitten kaikki kohteet, jotka jaettiin kanssasi organisaatioiden.

![Power BI Avaa jaetun kohteen sähköpostiviestistä ](./media/mobile-apps-b2b/mobile-b2b-open-item-email.png)

> [!NOTE]
> Jos tämä on jaettu ulkoisen Vieraskäyttäjä kuin ensimmäinen kohde, on lunasta kutsun selaimessa. Sinun ei voi käyttää kutsua Power BI-sovelluksessa.

Kun olet muodostanut yhteyden ulkoisen organisaation musta otsikko näkyy sovelluksessa. Tämä otsikko ilmaisee, että et ole muodostanut koti organisaatiollesi. Muodostaa koti organisaatioon Lopeta Vieras tilasta.

![Power BI Vieras käyttäjän otsikko](./media/mobile-apps-b2b/mobile-b2b-exit-home.png)

Vaikka sinulla on oltava Power BI artefaktin linkin muodostaa ulkoisen organisaatiolle, kun sovellus siirtyy, voit käyttää kaikki kohteet, jotka on jaettu (ei ainoastaan sähköpostiviestistä avata kohdetta). Voit tarkastella kaikkia kohteita, voit käyttää ulkoista organisaation sovelluksen valikosta ja valitsemalla **jaettu kanssani**. Valitse **sovelluksia** löydät sovelluksia, joita voit käyttää myös.

![Power BI sovelluksen valikosta Vieras ulkoisen käyttäjänä](./media/mobile-apps-b2b/mobile-b2b-menu.png)

## <a name="limitations"></a>Rajoitukset

- Ehdollisen käyttöoikeuden ja muut Intune-käytäntöjä ei tueta Azure AD B2B: n ja Power BI-mobiilisovelluksessa. Tämä tarkoittaa, että sovelluksen pakottaa vain koti organisaation käytäntöjä, jos ne ovat olemassa.
- Palveluilmoituksia vastaanotetaan sivustosta sovelluksiini vain (jopa kun käyttäjä on liitetty ulkoisen organisaatiolle vieraana). Käyttäjän sovelluksiini sivuston sovelluksen muodostaa uudelleen avaamalla ilmoitus.
- Jos käyttäjä sulkee sovelluksen, kun avata uudelleen sovelluksen muodostaa automaattisesti yhteyden käyttäjän sovelluksiini.
- Ulkoinen organisaatiolle yhteydessä joitakin toimintoja on poistettu käytöstä: suosikin kohdetta, Tietoilmoitukset, kommentoinnin ja jakaminen.
- Offline-tietoja ei ole käytettävissä yhdistettynä ulkoisen organisaatiolle.
- Jos sinulla on yritysportaali-sovellus on asennettu laitteeseesi, sitten laite täytyy rekisteröidä.
