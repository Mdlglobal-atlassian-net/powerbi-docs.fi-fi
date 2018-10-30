---
title: Raportin tarkasteleminen Power BI -palvelussa kuluttajille.
description: Tässä aiheessa näytetään Power BI -kuluttajille ja -loppukäyttäjille, kuinka Power BI -raportti avataan ja näytetään.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/17/2018
ms.author: mihart
ms.openlocfilehash: 15259d472ad315eb0a6274e59ebb30b94f48a302
ms.sourcegitcommit: a3ce866caba24217bcdd011e892b9ea72f3d2400
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/18/2018
ms.locfileid: "49396930"
---
# <a name="view-a-report-in-power-bi-service-for-consumers"></a>Näytä raportti Power BI -palvelussa *kuluttajille*
Raportti sisältää yhden tai useampia visualisointisivuja. Raportit luodaan Power BI:n *raporttien suunnitteluohjelmassa* ja [jaetaan *kuluttajille* suoraan](end-user-shared-with-me.md) tai [sovelluksen](end-user-apps.md) osana. 

Raportin voi avata monella eri tavalla ja näytämme nyt niistä kaksi, avaamisen aloitussivulta ja avaamisen koontinäytöstä. 

<!-- add art-->


## <a name="open-a-report-from-your-home-page"></a>Raportin avaaminen aloitussivulta
Avataan raportti, joka on jaettu suoraan sinulle, ja avataan sen jälkeen raportti, joka on jaettu sovelluksen osana.

   ![Aloitussivu](./media/end-user-report-open/power-bi-home.png)

### <a name="open-a-report-that-has-been-shared-with-you"></a>Sinulle jaetun raportin avaaminen
Power BI:n *suunnitteluohjelmassa* raportin voi jakaa suoraan napsauttamalla ylävalikkopalkin **Jaa**-painiketta. Näin jaettu sisältö näkyy **Jaettu kanssani** -säilössä vasemmassa siirtymispalkissa ja aloitussivun **Jaettu kanssani** -osassa.

1. Avaa Power BI -palvelu (app.powerbi.com).

2. Avaa aloitussivu valitsemalla vasemmassa siirtymispalkissa **Aloitussivu (esikatselu)**.  

   ![Aloitussivu](./media/end-user-report-open/power-bi-select-home.png)
   
3. Vieritä alaspäin, kunnes näet **Jaettu kanssani** -kohdan. Etsi raporttikuvake ![raporttikuvake](./media/end-user-report-open/power-bi-report-icon.png). Tässä näyttökuvassa on kaksi raporttia: *Rahoitus* ja *Northwind*. 
   
   ![aloitussivun Jaettu kanssani -osa](./media/end-user-report-open/power-bi-shared.png)

4. Avaa raportti valitsemalla jokin *raporttikorteista*.

   ![raporttisivu](./media/end-user-report-open/power-bi-report1.png)

5. Huomioi alareunan välilehdet. Kukin välilehti edustaa yhtä raportti*sivua*. Meillä on nyt *IT-kulutrendi*-sivu avoinna. Avaa jokin toinen raporttisivu valitsemalla eri välilehti. 

   ![raporttisivun välilehdet](./media/end-user-report-open/power-bi-tabs.png)

6. Tällä hetkellä näemme vain osan raporttisivusta. Jos haluat muuttaa sivun näyttöä (zoomausta), valitse **Näytä** > **Sovita sivulle**.

   ![muuta zoomaus](./media/end-user-report-open/power-bi-fit.png)

   ![sovita sivulle](./media/end-user-report-open/power-bi-report2.png)

### <a name="open-a-report-that-is-part-of-an-app"></a>Sovelluksen osana jaetun raportin avaaminen
Jos olet saanut sovelluksia työtovereilta tai AppSourcesta, kyseiset sovellukset ovat käytettävissä aloitussivulla ja **Sovellukset**-säilössä vasemmassa siirtymispalkissa. [Sovellus](end-user-apps.md) on koontinäyttöjen ja raporttien nippu.

1. Palaa aloitussivulle valitsemalla vasemmassa siirtymispalkissa **Aloitussivu (esikatselu)**.

7. Vieritä alaspäin, kunnes näet **Omat sovellukset** -kohdan.

   ![Aloitussivu](./media/end-user-report-open/power-bi-my-apps.png)

8. Avaa sovellus valitsemalla se. Sovelluksen *suunnitteluohjelman* asetusten mukaan sovellus avaa joko koontinäytön, raportin tai sovelluksen sisältöluettelon. Jos sovellus:
    - avaa raportin, olet valmis.
    - avaa koontinäytön, katso alla oleva kohta [Raportin avaaminen koontinäytöstä](#Open-a-report-from-a-dashboard).
    - avaa sovelluksen sisältöluettelon kohtaan **Raportit**, avaa raportti valitsemalla se.


## <a name="open-a-report-from-a-dashboard"></a>Raportin avaaminen koontinäytöstä
Raportit voidaan avata koontinäytöstä. Useimmat koontinäyttöruudut on *kiinnitetty* raporteista. Ruudun valitseminen avaa raportin, jota on käytetty ruudun luomiseen. 

1. Valitse koontinäytöstä ruutu. Tässä esimerkissä olemme valinneet Yksiköitä yhteensä vuoden alusta -pylväskaavioruudun.

    ![koontinäyttö, jossa on ruutu valittuna](./media/end-user-report-open/power-bi-dashboard.png)

2.  Ruutuun liittyvä raportti avautuu. Huomaa, että olemme Vuoden alusta -luokan sivulla. Tämä raporttisivu sisältää koontinäytöstä valitun pylväskaavion.

    ![raportti avoinna lukunäkymässä](./media/end-user-report-open/power-bi-report-new.png)

> [!NOTE]
> Kaikki ruudut eivät johda raporttiin. Jos valitset ruudun, joka oli [luotu esittämällä kysymyksiä](end-user-q-and-a.md), QA-näyttö avautuu. Jos valitset ruudun, joka oli [luotu koontinäytön **Lisää ruutu** -pienoissovelluksella](../service-dashboard-add-widget.md), monia eri asioita voi tapahtua.  


##  <a name="still-more-ways-to-open-a-report"></a>Muita tapoja avata raportti
Kun pääset sinuiksi Power BI -palvelun kanssa, löydät itsellesi sopivimmat työnkulut. Tässä on vielä muita tapoja raporttien käyttämiseen:
- Valitsemalla vasemmasta siirtymisruudusta **Suosikit** ja **Viimeisimmät**    
- Käyttämällä [Näytä aiheeseen liittyvät](end-user-related.md) -toimintoa    
- Sähköpostiviestistä, jonka joku on [jakanut kanssasi](../service-share-reports.md), tai kun [määrität ilmoituksen](end-user-alerts.md)    
- [Ilmoituskeskuksen](end-user-notification-center.md) kautta    
- ja muilla tavoilla

## <a name="next-steps"></a>Seuraavat vaiheet
[Raportteja voi käsitellä monella eri tavalla](end-user-reading-view.md).  Aloita tutustuminen valitsemalla jokainen välilehti raporttipohjan alaosasta.

