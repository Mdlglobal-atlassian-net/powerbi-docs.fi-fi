---
title: Microsoft Flow:n Power BI -integrointi
description: Opi luomaan Power BI -tietoilmoitusten käynnistämiä työnkulkuja.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: YhmNstC39Mw
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: dc79282a5c221e85fae7838009f6cecf91cbfdb8
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34246823"
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow ja Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) on SaaS:in tarjoama työnkulun automatisoimiseen tarkoitettu palvelu, joka toimii yhä useamman yrityskäyttäjän luottaman sovelluksen ja SaaS-palveluiden kanssa. Työnkulun avulla voit automatisoida tehtäviä integroimalla suosikkisovelluksesi ja -palvelusi, (Power BI mukaan lukien) saadaksesi ilmoituksia, synkronoidaksesi tiedostoja, kerätäksesi tietoja ja paljon muuta. Toistuvista tehtävistä tulee helppoja työnkulun automatisoinnin ansiosta.

[Aloita Flow’n käyttö nyt.](https://flow.microsoft.com/documentation/getting-started)

Katso, miten Sirui luo työnkulun, joka lähettää yksityiskohtaisen sähköpostin kollegoille, kun Power BI -ilmoitus käynnistyy. Kokeile sitten itse noudattamalla videon alapuolella olevia vaiheittaisia ohjeita.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Power BI -tietoilmoitusten käynnistämän työnkulun luominen

### <a name="prerequisites"></a>Edellytykset
Tässä opetusohjelmassa kerrotaan, miten voit luoda kaksi erilaista työnkulkua; yhden mallin pohjalta ja toisen alusta alkaen. Seuraa ohjeita ja [luo tietoilmoitusta Power BI:ssä](service-set-data-alerts.md), Luo ilmainen Slack-tili sekä [rekisteröidy Microsoft Flow’hun](https://flow.microsoft.com/en-us/#home-signup) (Se on ilmaista!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Power BI -mallin mukaisen työnkulun luominen
Tässä tehtävässä käytämme mallia luodaksemme yksinkertaisen työnkulun, joka käynnistyy Power BI -tietoilmoituksesta.

1. Kirjaudu sisään Microsoft Flow’hun (flow.microsoft.com).
2. Valitse **Omat työnkulut**.
   
   ![Työnkulut-valikkorivi](media/service-flow-integration/power-bi-my-flows.png)
3. Valitse **Luo mallista**.
   
    ![Omat työnkulut -valikkorivi](media/service-flow-integration/power-bi-template.png)
4. Etsi Power BI-malleja hakuruudun avulla ja valitse **Lähetä sähköpostiviesti mille tahansa kohderyhmälle, kun Power BI-tietohälytys käynnistetään > Jatka**.
   
    ![hakutulokset](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Työnkulun muodostaminen
Tässä mallissa on yksi käynnistin (Power BI-tietohälytys Irlannin uusia olympiamitaleita varten) ja yksi toiminto (lähetä sähköpostiviesti). Valitessasi kentän, Flow näyttää siihen lisättävissä olevaa dynaamista sisältöä.  Tässä esimerkissä lisäämme ruutuarvon ja ruudun URL-osoitteen sanoman tekstiosaan.

![työnkulkumalli](media/service-flow-integration/power-bi-template1.png)

1. Valitse avattavasta valikosta käynnistimen, Power BI -tietoilmoitus. Valitse **Irlannin uudet mitalit**. Oppiaksesi luomaan ilmoituksen, katso [Tietoilmoitukset Power BI:ssä](service-set-data-alerts.md).
   
   ![ilmoitusten lajitteluvalikko](media/service-flow-integration/power-bi-trigger-flow.png)
2. Syötä yksi tai useampi kelvollinen sähköpostiosoite ja valitse sitten **Muokkaa** (alla) tai **Lisää dynaamista sisältöä**. 
   
   ![Lähetä sähköpostiviesti -ruutu](media/service-flow-integration/power-bi-flow-email.png)

3. Flow luo otsikon ja sanoman, jotka voit säilyttää sellaisenaan tai joita voit muokata. Kaikki Power BI -ilmoitusta luotaessa syötetyt arvot ovat käytettävissäsi -- aseta vain kohdistin niiden ylle ja valitse harmaalla korostettu alue. 

   ![Lähetä sähköpostiviesti -ruutu](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Jos luot esimerkiksi Power BI -ilmoituksen otsikolla **Voitimme uuden mitalin**, voit valita **Ilmoituksen otsikko** -kohdan, lisätäksesi kyseisen tekstin sähköpostiviestin Aihe-kenttään.

    ![luo sähköpostiviesti](media/service-flow-integration/power-bi-flow-message.png)

    Voit myös hyväksyä oletusarvoisen sähköpostiviestin tai luoda omasi. Yllä oleva esimerkki sisältää muutaman viestiin tehdyn muutoksen.

1. Kun olet valmis, valitse **Luo työnkulku** tai **Tallenna työnkulku**.  Työnkulku luodaan ja tarkastetaan.  Flow kertoo, jos siitä löydetään virheitä.
2. Jos virheitä löytyy, valitse **Muokkaa työnkulkua** korjataksesi ne tai valitse **Valmis** suorittaaksesi uuden työnkulun.
   
   ![onnistumisilmoitus](media/service-flow-integration/power-bi-flow-running.png)
5. Kun tietoilmoitus käynnistyy, lähetetään sähköpostiviesti antamiisi osoitteisiin.  
   
   ![ilmoituksen sähköpostiviesti](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Luo työnkulku, jota Power BI käyttää - alusta asti (tyhjä)
Seuraavaksi luomme yksinkertaisen työnkulun alusta alkaen, joka käynnistyy Power BI -tietoilmoituksella.

1. Kirjaudu sisään Microsoft Flow'hun.
2. Valitse **Omat työnkulut** > **Luo tyhjästä**.
   
   ![Flow’n yläreunan valikkorivi](media/service-flow-integration/power-bi-my-flows.png)
3. Käytä hakuruutua hakeaksesi Power BI -käynnistimiä ja valitse **Power BI - tietopohjaisen ilmoituksen käynnistyminen**.

### <a name="build-your-flow"></a>Työnkulun luominen
1. Valitse avattavasta valikosta ilmoituksesi nimi.  Oppiaksesi luomaan ilmoituksen, katso [Tietoilmoitukset Power BI:ssä](service-set-data-alerts.md).
   
    ![valitse ilmoituksen nimi](media/service-flow-integration/power-bi-totalstores2.png)
2. Valitse **Uusi vaihe** > **Lisää toiminto**.
   
   ![lisää uusi vaihe](media/service-flow-integration/power-bi-new-step.png)
3. Syötä hakuun **Outlook** ja valitse **Luo tapahtuma**.
   
   ![muodosta työnkulku](media/service-flow-integration/power-bi-create-event.png)
4. Täytä tapahtumakentät. Valitessasi kentän, Flow näyttää siihen lisättävissä olevaa dynaamista sisältöä.
   
   ![jatka työnkulun muodostamista](media/service-flow-integration/power-bi-flow-event.png)
5. Valitse **Luo työnkulku** kun olet valmis.  Flow tallentaa ja tarkastaa työnkulun. Jos virheitä ei löydetä, valitse **Valmis** ja voit suorittaa tämän työnkulun.  Uusi työnkulku lisätään **Omat työnkulut** -sivulle.
   
   ![Viimeistele työnkulku](media/service-flow-integration/power-bi-flow-running.png)
6. Kun Power BI -tietoilmoitus käynnistää työnkulun, näyttöön ilmestyvä Outlook -tapahtumailmoitus näyttää suunnilleen tältä.
   
    ![Flow käynnistää Outlook-ilmoituksen](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Aloita Microsoft Flow’n käyttö](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Määritä Power BI -palvelun tietoilmoitukset ](service-set-data-alerts.md)
* [Määritä tietoilmoitukset iPhonellasi](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Määritä tietoilmoitukset Power BI Windows 10 -mobiilisovelluksella](mobile-set-data-alerts-in-the-mobile-apps.md)
* Ilmenikö muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

