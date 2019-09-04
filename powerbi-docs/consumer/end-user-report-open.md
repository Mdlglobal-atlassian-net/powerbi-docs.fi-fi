---
title: Näytä raportti
description: Tässä aiheessa näytetään Power BI -kuluttajille ja -loppukäyttäjille, kuinka Power BI -raportti avataan ja näytetään.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 8/28/2018
ms.author: mihart
ms.openlocfilehash: 0896d397c7cc78ce36109cf1c975b34d081169a1
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/30/2019
ms.locfileid: "70184740"
---
# <a name="view-a-report-in-power-bi-service-for-consumers"></a>Näytä raportti Power BI -palvelussa *kuluttajille*
Raportti sisältää yhden tai useampia visualisointisivuja. Power BI:n *suunnittelijat* luovat raportit ja [jakavat *ne kuluttajille* suoraan](end-user-shared-with-me.md) tai [sovelluksen](end-user-apps.md) osana. 

Raportin voi avata monella eri tavalla ja näytämme nyt niistä kaksi, avaamisen aloitussivulta ja avaamisen koontinäytöstä. 

<!-- add art-->


## <a name="open-a-report-from-power-bi-home"></a>Raportin avaaminen Power BI -aloitussivulta
Avataan raportti, joka on jaettu suoraan sinulle, ja avataan sen jälkeen raportti, joka on jaettu sovelluksen osana.

   ![Aloitussivu](./media/end-user-report-open/power-bi-home-canvas.png)

### <a name="open-a-report-that-has-been-shared-with-you"></a>Sinulle jaetun raportin avaaminen
Power BI:n *suunnittelijat* voivat jakaa raportin suoraan kanssasi. Näin jaettu sisältö näkyy **Jaettu kanssani** -säilössä siirtymispalkissa ja aloitussivun **Jaettu kanssani** -osassa.

1. Avaa Power BI -palvelu (app.powerbi.com).

2. Siirry aloitussivulle valitsemalla siirtymispalkista **Aloitussivu**.  

   ![Aloitussivu](./media/end-user-report-open/power-bi-select-home-new.png)
   
3. Vieritä alaspäin, kunnes näet **Jaettu kanssani** -kohdan. Etsi raporttikuvake ![raporttikuvake](./media/end-user-report-open/power-bi-report-icon.png). Tässä näyttökuvassa on yksi koontinäyttö ja yksi raportti, jonka nimi on *Myynti- ja markkinointimalli*. 
   
   ![aloitussivun Jaettu kanssani -osa](./media/end-user-report-open/power-bi-shared-new.png)

4. Avaa raportti valitsemalla *raporttikortti*.

   ![raporttisivu](./media/end-user-report-open/power-bi-report-open.png)

5. Huomioi vasemmalla puolella olevat välilehdet.  Kukin välilehti edustaa yhtä raportti*sivua*. *Kasvumahdollisuus*-sivu on nyt avoinna. Avaa sen sijaan raporttisivu valitsemalla *Luokka vuoden alusta* -välilehti. 

   ![raporttisivun välilehdet](./media/end-user-report-open/power-bi-ytd.png)

6. Nyt näet koko raporttisivun. Jos haluat muuttaa sivun näyttöä (zoomausta), valitse avattava Näytä-valikko oikeasta yläkulmasta ( **>** ) ja valitse **Todellinen koko**.

   ![muuta zoomaus](./media/end-user-report-open/power-bi-fit-new.png)

   ![sovita sivulle](./media/end-user-report-open/power-bi-actual.png)

### <a name="open-a-report-that-is-part-of-an-app"></a>Sovelluksen osana jaetun raportin avaaminen
Jos olet saanut sovelluksia työtovereilta tai AppSourcesta, kyseiset sovellukset ovat käytettävissä aloitussivulla ja **Sovellukset**-säilössä siirtymispalkissa. [Sovellus](end-user-apps.md) on koontinäyttöjen ja raporttien nippu.

1. Palaa takaisin aloitussivulle valitsemalla **Aloitussivu** siirtymispalkista.

7. Vieritä alaspäin, kunnes näet **Omat sovellukset** -kohdan.

   ![Aloitussivu](./media/end-user-report-open/power-bi-my-apps.png)

8. Avaa sovellus valitsemalla se. Sovelluksen *suunnitteluohjelman* asetusten mukaan sovellus avaa joko koontinäytön, raportin tai sovelluksen sisältöluettelon. Jos sovellus:
    - avaa raportin, olet valmis.
    - avaa koontinäytön, katso alla oleva kohta ***Raportin avaaminen koontinäytöstä***.


## <a name="open-a-report-from-a-dashboard"></a>Raportin avaaminen koontinäytöstä
Raportit voidaan avata koontinäytöstä. Useimmat koontinäyttö[ruudut](end-user-tiles.md) on *kiinnitetty* raporteista. Ruudun valitseminen avaa raportin, jota on käytetty ruudun luomiseen. 

1. Valitse koontinäytöstä ruutu. Tässä esimerkissä olemme valinneet Yksiköitä yhteensä vuoden alusta -pylväskaavioruudun.

    ![koontinäyttö, jossa on ruutu valittuna](./media/end-user-report-open/power-bi-dashboard.png)

2.  Ruutuun liittyvä raportti avautuu. Huomaa, että olemme Vuoden alusta -luokan sivulla. Tämä raporttisivu sisältää koontinäytöstä valitun pylväskaavion.

    ![raportti avoinna lukunäkymässä](./media/end-user-report-open/power-bi-report-tabs.png)

> [!NOTE]
> Kaikki ruudut eivät johda raporttiin. Jos valitset ruudun, joka oli [luotu esittämällä kysymyksiä](end-user-q-and-a.md), QA-näyttö avautuu. Jos valitset ruudun, joka oli [luotu koontinäytön **Lisää ruutu** -pienoissovelluksella](../service-dashboard-add-widget.md), monia eri asioita voi tapahtua. Esimerkiksi video voidaan toistaa tai sivusto avata.  


##  <a name="still-more-ways-to-open-a-report"></a>Muita tapoja avata raportti
Kun pääset sinuiksi Power BI -palvelun kanssa, löydät itsellesi sopivimmat työnkulut. Tässä on vielä muita tapoja raporttien käyttämiseen:
- Valitsemalla siirtymispalkista **Suosikit** ja **Viimeisimmät**    
- Käyttämällä [Näytä aiheeseen liittyvät](end-user-related.md) -toimintoa    
- Sähköpostiviestistä, jonka joku on [jakanut kanssasi](../service-share-reports.md), tai kun [määrität ilmoituksen](end-user-alerts.md)    
- [Ilmoituskeskuksen](end-user-notification-center.md) kautta    
- ja muilla tavoilla

## <a name="next-steps"></a>Seuraavat vaiheet
[Raportteja voi käsitellä monella eri tavalla](end-user-reading-view.md).  Aloita tutustuminen valitsemalla jokainen välilehti raporttipohjan sivulta.

