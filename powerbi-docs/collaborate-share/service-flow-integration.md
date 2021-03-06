---
title: Power BI -integrointi Power Automaten kanssa
description: Opi luomaan Power BI -tietoilmoitusten käynnistämiä Power Automate -työnkulkuja.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: YhmNstC39Mw
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/25/2020
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 9e8f90465ab7b5b9545460de8d763061bf9bcf94
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83275014"
---
# <a name="power-automate-and-power-bi"></a>Power Automate ja Power BI

[Power Automate](https://docs.microsoft.com/power-automate/getting-started) on työnkulun automatisoimiseen tarkoitettu SaaS-palvelu, joka toimii yhä useamman yrityskäyttäjän luottaman sovelluksen ja SaaS-palveluiden kanssa. Power Automaten avulla voit automatisoida tehtäviä integroimalla suosikkisovelluksesi ja -palvelusi (Power BI mukaan lukien) esimerkiksi ilmoitusten saamista, tiedostojen synkronoimista ja tietojen keräämistä varten. Toistuvista tehtävistä tulee helppoja työnkulun automatisoinnin ansiosta.

[Aloita Power Automaten käyttö heti.](https://docs.microsoft.com/power-automate/getting-started)

Katso, miten Sirui luo Power Automate -työnkulun, joka lähettää yksityiskohtaisen sähköpostin kollegoille, kun Power BI -ilmoitus käynnistyy. Kokeile sitten itse noudattamalla videon alapuolella olevia vaiheittaisia ohjeita.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Power BI -tietoilmoitusten käynnistämän työnkulun luominen

### <a name="prerequisites"></a>Edellytykset
Tässä opetusohjelmassa kerrotaan, miten voit luoda kaksi erilaista työnkulkua; yhden mallin pohjalta ja toisen alusta alkaen. Jos haluat seurata ohjeita, [luo tietoilmoitus Power BI:ssä](../create-reports/service-set-data-alerts.md), luo maksuton Slack-tili sekä [rekisteröidy Power Automateen](https://flow.microsoft.com/#home-signup) (se on maksutonta).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Power BI -mallin mukaisen työnkulun luominen
Tässä tehtävässä käytämme mallia luodaksemme yksinkertaisen työnkulun, joka käynnistyy Power BI -tietoilmoituksesta.

1. Kirjaudu sisään Power Automateen (flow.microsoft.com).
2. Valitse **Omat työnkulut**.
   
   ![Power Automaten valikkorivi](media/service-flow-integration/power-bi-my-flows.png)
3. Valitse **Luo mallista**.
   
    ![Omat työnkulut -valikkorivi](media/service-flow-integration/power-bi-template.png)
4. Etsi Power BI-malleja hakuruudun avulla ja valitse **Lähetä sähköpostiviesti mille tahansa kohderyhmälle, kun Power BI-tietohälytys käynnistetään > Jatka**.
   
    ![hakutulokset](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Työnkulun muodostaminen
Tässä mallissa on yksi käynnistin (Power BI-tietohälytys Irlannin uusia olympiamitaleita varten) ja yksi toiminto (lähetä sähköpostiviesti). Valitessasi kentän Power Automate näyttää siihen lisättävissä olevaa dynaamista sisältöä.  Tässä esimerkissä lisäämme ruutuarvon ja ruudun URL-osoitteen sanoman tekstiosaan.

![työnkulkumalli](media/service-flow-integration/power-bi-template1.png)

1. Valitse avattavasta valikosta käynnistimen, Power BI -tietoilmoitus. Valitse **Irlannin uudet mitalit**. Oppiaksesi luomaan ilmoituksen, katso [Tietoilmoitukset Power BI:ssä](../create-reports/service-set-data-alerts.md).
   
   ![ilmoitusten lajitteluvalikko](media/service-flow-integration/power-bi-trigger-flow.png)
2. Syötä yksi tai useampi kelvollinen sähköpostiosoite ja valitse sitten **Muokkaa** (alla) tai **Lisää dynaamista sisältöä**. 
   
   ![Lähetä sähköpostiviesti -ruutu](media/service-flow-integration/power-bi-flow-email.png)

3. Power Automate luo otsikon ja sanoman, jotka voit säilyttää sellaisinaan tai joita voit muokata. Kaikki Power BI -ilmoitusta luotaessa syötetyt arvot ovat käytettävissäsi -- aseta vain kohdistin niiden ylle ja valitse harmaalla korostettu alue. 

   ![Lähetä sähköpostiviesti -ruutu](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Jos luot esimerkiksi Power BI -ilmoituksen otsikolla **Voitimme uuden mitalin**, voit valita **Ilmoituksen otsikko** -kohdan, lisätäksesi kyseisen tekstin sähköpostiviestin Aihe-kenttään.

    ![luo sähköpostiviesti](media/service-flow-integration/power-bi-flow-message.png)

    Voit myös hyväksyä oletusarvoisen sähköpostiviestin tai luoda omasi. Yllä oleva esimerkki sisältää muutaman viestiin tehdyn muutoksen.

1. Kun olet valmis, valitse **Luo työnkulku** tai **Tallenna työnkulku**.  Työnkulku luodaan ja tarkastetaan.  Power Automate kertoo, jos se löytää virheitä.
2. Jos virheitä löytyy, valitse **Muokkaa työnkulkua** korjataksesi ne tai valitse **Valmis** suorittaaksesi uuden työnkulun.
   
   ![onnistumissanoma](media/service-flow-integration/power-bi-flow-running.png)
5. Kun tietoilmoitus käynnistyy, lähetetään sähköpostiviesti antamiisi osoitteisiin.  
   
   ![ilmoituksen sähköpostiviesti](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-power-automate-that-uses-power-bi---from-scratch-blank"></a>Power BI:tä käyttävän Power Automate -työnkulun luominen – alusta alkaen (tyhjä)
Seuraavaksi luomme alusta alkaen yksinkertaisen työnkulun, joka käynnistyy Power BI -tietoilmoituksella.

1. Kirjaudu sisään Power Automateen.
2. Valitse **Omat työnkulut** > **Luo tyhjästä**.
   
   ![Power Automaten yläosan valikkorivi](media/service-flow-integration/power-bi-my-flows.png)
3. Käytä hakuruutua hakeaksesi Power BI -käynnistimiä ja valitse **Power BI - tietopohjaisen ilmoituksen käynnistyminen**.

### <a name="build-your-flow"></a>Muodosta työnkulkusi
1. Valitse avattavasta valikosta ilmoituksesi nimi.  Oppiaksesi luomaan ilmoituksen, katso [Tietoilmoitukset Power BI:ssä](../create-reports/service-set-data-alerts.md).
   
    ![valitse ilmoituksen nimi](media/service-flow-integration/power-bi-totalstores2.png)
2. Valitse **Uusi vaihe** > **Lisää toiminto**.
   
   ![lisää uusi vaihe](media/service-flow-integration/power-bi-new-step.png)
3. Syötä hakuun **Outlook** ja valitse **Luo tapahtuma**.
   
   ![muodosta työnkulku](media/service-flow-integration/power-bi-create-event.png)
4. Täytä tapahtumakentät. Valitessasi kentän Power Automate näyttää siihen lisättävissä olevaa dynaamista sisältöä.
   
   ![jatka työnkulun muodostamista](media/service-flow-integration/power-bi-flow-event.png)
5. Valitse **Luo työnkulku**, kun olet valmis.  Power Automate tallentaa ja arvioi työnkulun. Jos virheitä ei löydetä, valitse **Valmis** ja voit suorittaa tämän työnkulun.  Uusi työnkulku lisätään **Omat työnkulut** -sivulle.
   
   ![Työnkulun viimeisteleminen](media/service-flow-integration/power-bi-flow-running.png)
6. Kun Power BI -tietoilmoitus käynnistää työnkulun, näyttöön ilmestyvä Outlook -tapahtumailmoitus näyttää suunnilleen tältä.
   
    ![Power Automate käynnistää Outlook-ilmoituksen](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Power Automaten käytön aloittaminen](https://docs.microsoft.com/power-automate/getting-started/)
* [Määritä Power BI -palvelun tietoilmoitukset ](../create-reports/service-set-data-alerts.md)
* [Määritä tietoilmoitukset iPhonellasi](../consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* [Määritä tietoilmoitukset Power BI Windows 10 -mobiilisovelluksella](../consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
