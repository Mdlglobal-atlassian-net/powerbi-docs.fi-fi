---
title: Raportin käsittelyasetusten määrittäminen
description: Tutustu siihen, miten voit ohittaa raporttien oletusarvoiset käsittelyasetukset.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 01/21/2020
ms.author: painbar
ms.openlocfilehash: fee89c65328b70e1f312b39fbad75d7148bd92f2
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2020
ms.locfileid: "76542285"
---
# <a name="configure-report-interaction-settings"></a>Raportin käsittelyasetusten määrittäminen

## <a name="overview"></a>Yleiskatsaus

Power BI -mobiilisovelluksessa on useita määritettävissä olevia käsittelyasetuksia, joiden avulla voit hallita sitä, miten tietojasi käsitellään, ja määrittää, miten jotkin Power BI -mobiilisovelluksen osat toimivat. Tällä hetkellä asetukset koskevat seuraavia:
* [Käsitteleminen yhdellä napsautuksella tai kaksoisnapsautuksella raportin visualisoinneissa](#single-tap)
* [Kiinnitetty tai dynaaminen raportin alatunniste](#docked-report-footer-android-phones) (Android)
* [Päivittäminen painikkeella tai päivittäminen vetämällä](#report-refresh-android-phones) (Android)

Saat vuorovaikutusasetukset näkyviin avaamalla [sivupaneelin](./mobile-apps-home-page.md#header) napauttamalla profiilikuvaasi, valitsemalla **Asetukset** ja etsimällä **Vuorovaikutus**-osan.

![Käsittelyasetukset](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-section.png)

>[!NOTE]
>Päivityspainikkeen ja raportin alatunnisteen käsittelyasetuksilla ei tällä hetkellä ole vaikutusta raporttipalvelimen raportteihin. Tämä kuitenkin muuttuu raporttipalvelimen tammikuun 2020 julkaisun myötä.

## <a name="interaction-settings"></a>Käsittelyasetukset

### <a name="single-tap"></a>Napautus
Kun lataat Power BI -mobiilisovelluksen, se on määritetty käsittelyyn yhdellä napsautuksella. Tämä tarkoittaa sitä, että kun napautat visualisointia osittajatoiminnon, ristiinkorostamisen, linkin tai painikkeen napsauttamisen tai muun toiminnon suorittamista varten, napautus sekä valitsee visualisoinnin että suorittaa haluamasi toiminnon.

Halutessasi voit poistaa käytöstä käsittelyn yhdellä napautuksella. Sen jälkeen käsittelyssä käytetään kaksoisnapautusta. Kun käsittely kaksoisnapsautuksella on käytössä, valitset visualisoinnin ensin napauttamalla sitä ja suoritat sitten haluamasi toiminnon napauttamalla visualisointia uudelleen.

### <a name="docked-report-footer-android-phones"></a>Kiinnitetty raportin alatunniste (Android-puhelimet)

Kiinnitetyn raportin alatunnisteen asetus määrittää, pysyykö raportin alatunniste kiinnitettynä (eli kiinteänä ja aina näkyvissä) raportin alaosassa, vai piilotetaanko se ja tuodaanko se uudelleen näkyviin sen mukaan, mitä toimintoja (kuten vieritystä) raportissa käytetään.

Android-puhelimissa raportin kiinnitetyn alatunnisteen asetus on oletusarvoisesti **käytössä**, mikä tarkoittaa, että raportin alatunniste on kiinnitetty ja aina näkyvissä raportin alaosassa. Voit vaihtaa asetukseksi **ei käytössä**, jos haluat raporttiin mieluummin dynaamisen alatunnisteen, joka tulee näkyviin ja katoaa sen mukaan, mitä toimintoja käytät raportissa.

### <a name="report-refresh-android-phones"></a>Raportin päivitys (Android-puhelimet)

Raportin päivitysasetus määrittää, miten raporttien päivitykset aloitetaan. Voit valita, onko kaikkien raporttien ylätunnisteessa päivityspainike, vai päivitetäänkö raportti vetämällä raporttisivulla hieman ylhäältä alas. Seuraava kuva havainnollistaa näitä kahta vaihtoehtoa. 

![Päivityspainike ja päivittäminen vetämällä](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-refresh-button-versus-pull.png)

Android-puhelimissa päivityspainike lisätään oletusarvoisesti.

Jos haluat muuttaa raportin päivitysasetusta, siirry käsittelyasetuksissa raportin päivitysasetukseen. Käytössä oleva asetus on näkyvissä. Napauta arvoa, niin näkyviin tulee ponnahdusikkuna, jossa voit valita uuden arvon.

![Päivityksen asettaminen](./media/mobile-app-interaction-settings/powerbi-mobile-app-interactions-set-refresh.png)

## <a name="remote-configuration"></a>Etämääritys

Järjestelmänvalvoja voi määrittää käsittelyasetukset myös etäyhteydellä mobiililaitteiden hallinnan työkalun ja sovellusmääritystiedoston avulla. Näin raporttien käsittelykokemus voidaan standardoida koko organisaatiota tai organisaation tiettyjä käyttäjäryhmiä varten. Lisätietoja on artikkelissa [Käsittelyn määrittäminen mobiililaitteiden hallinnan avulla](./mobile-app-configuration.md).


## <a name="next-steps"></a>Seuraavat vaiheet
* [Raporttien käsitteleminen](./mobile-reports-in-the-mobile-apps.md#interact-with-reports)
* [Käsittelyn määrittäminen mobiililaitteiden hallinnan avulla](./mobile-app-configuration.md)
