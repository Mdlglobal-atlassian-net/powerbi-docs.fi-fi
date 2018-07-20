---
title: 'Opetusohjelma: Kysymysten esittäminen Q&A:n virtuaalisella analyytikolla iOS-sovelluksissa – Power BI'
description: Tässä opetusohjelmassa esitetään mallitietoja koskevia kysymyksiä omin sanoin käyttämällä Q&A:n virtuaalista analyytikkoa iOS-laitteen Power BI -mobiilisovelluksessa.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: tutorial
ms.date: 05/08/2018
ms.author: maggies
ms.openlocfilehash: 8cb9e78898228aa7dad82db76d1d7da1a7151702
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34561421"
---
# <a name="tutorial-ask-questions-about-your-data-with-the-qa-virtual-analyst-in-ios-apps---power-bi"></a>Opetusohjelma: Tietoja koskevien kysymysten esittäminen Q&A:n virtuaalisen analyytikon avulla iOS-sovelluksissa – Power BI

Helpoin tapa saada lisätietoja omista tiedoista on esittää kysymyksiä omin sanoin. Tässä opetusohjelmassa esitetään kysymyksiä ja tarkastellaan mallitietojen merkityksellisiä tietoja käyttämällä Q&A:n virtuaalista analyytikkoa iPadin, iPhonen ja iPod Touchin Microsoft Power BI -mobiilisovelluksessa. 

Koskee seuraavia:

| ![iPhone](media/tutorial-mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](media/tutorial-mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhonet |iPadit |

Q&A:n virtuaalinen analyytikko on keskustelumainen BI-käyttökokemus, joka käyttää taustalla olevia Q&A-tietoja Power BI -palvelussa [(https://powerbi.com)](https://powerbi.com). Se ehdottaa merkityksellisiä tietoja, ja voit esittää sille kysymyksiä joko kirjoittamalla tai puhumalla ääneen.

![Paras myynti Q&A:n virtuaalinen analyytikko](media/tutorial-mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-intro.png)

Tässä opetusohjelmassa tehdään seuraavat asiat:

> [!div class="checklist"]
> * Power BI -mobiilisovelluksen asentaminen iOS-laitteelle
> * Power BI -mallikoontinäytön ja -raportin lataaminen
> * Mobiilisovelluksen ehdottamien merkityksellisten tietojen tarkastelu

Jos et ole rekisteröitynyt Power BI:hin, [rekisteröidy ilmaiseen kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

### <a name="install-the-power-bi-for-ios-app"></a>Power BI:n iOS-sovelluksen asentaminen
[Lataa iOS-sovellus](http://go.microsoft.com/fwlink/?LinkId=522062 "Lataa iPhone-sovellus") iPadille, iPhonelle tai iPod Touchille Applen App Storesta.

Seuraavat versiot tukevat Power BI:n iOS-sovellusta:
- iPad, jossa on iOS 10 tai uudempi.
- iPhone 5 tai uudempi, jossa on iOS 10 tai uudempi. 
- iPod Touch, jossa on iOS 10 tai uudempi.

### <a name="download-the-opportunity-analysis-sample"></a>Mahdollisuusanalyysimallin lataaminen
Opetusohjelman ensimmäisessä vaiheessa ladataan mahdollisuusanalyysimalli Power BI -palvelussa.

1. Avaa Power BI -palvelu (app.powerbi.com) selaimessasi ja kirjaudu sisään.

1. Avaa vasen siirtymisruutu napsauttamalla yleistä siirtymiskuvaketta.

    ![yleinen siirtymiskuvake](media/tutorial-mobile-apps-ios-qna/power-bi-android-quickstart-global-nav-icon.png)

2. Valitse vasemmassa siirtymisruudussa **Työtilat** > **Oma työtila**.

    ![Oma työtila](media/tutorial-mobile-apps-ios-qna/power-bi-android-quickstart-my-workspace.png)

3. Valitse vasemmassa alakulmassa **Nouda tiedot**.
   
    ![Nouda tiedot](media/tutorial-mobile-apps-ios-qna/power-bi-get-data.png)

3. Valitse Nouda tiedot -sivulla **Mallit**-kuvake.
   
   ![Mallit-kuvake](media/tutorial-mobile-apps-ios-qna/power-bi-samples-icon.png)

4. Valitse **Mahdollisuusanalyysimalli**.
 
    ![Mahdollisuusanalyysimalli](media/tutorial-mobile-apps-ios-qna/power-bi-oa.png)
 
8. Valitse **Muodosta yhteys**.  
  
   ![Mahdollisuusanalyysimalli – Muodosta yhteys](media/tutorial-mobile-apps-ios-qna/opportunity-connect.png)
   
5. Power BI tuo mallin sekä lisää uuden koontinäytön, raportin ja tietojoukon omaan työtilaasi.
   
   ![Mahdollisuusanalyysimalli-koontinäyttö](media/tutorial-mobile-apps-ios-qna/power-bi-service-opportunity-sample.png)

Nyt voit siirtyä tarkastelemaan mallia iOS-laitteessa.

## <a name="try-featured-insights"></a>Kokeile esiteltyjä merkityksellisiä tietoja
1. Avaa Power BI -sovellus iPhonessa tai iPadissa ja kirjaudu sisään Power BI -tilisi tunnistetiedoilla, samoilla joita käytit selaimen Power BI-palvelussa.

1.  Napauta yleistä siirtymispainiketta ![Yleinen siirtymispainike](media/mobile-ipad-app-get-started/power-bi-iphone-global-nav-button.png) > **Työtilat** > **Oma työtila** ja avaa Mahdollisuusanalyysimalli-koontinäyttö.

2. Napauta Q&A:n virtuaalinen analyytikko -kuvaketta ![Q&A:n virtuaalinen analyytikko -kuvake](media/tutorial-mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) sivun alaosan (iPadissa sivun yläosassa) toimintovalikossa.

     ![Mahdollisuusanalyysimalli-koontinäyttö](media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-opportunity-analysis.png)

     Power BI Q&A:n virtuaalinen analyytikko antaa joitain ehdotuksia, joilla pääset alkuun.

     ![esitellyt merkitykselliset tiedot -painike](media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-suggest-insights.png)
3. Napauta **esitellyt merkitykselliset tiedot**.

     Q&A:n virtuaalinen analyytikko ehdottaa joitakin merkityksellisiä tietoja.
4. Vieritä oikealle ja napauta **Merkityksellinen tieto 2**.

    ![Merkityksellinen tieto 2 -painike](media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-suggest-insight-2.png)

     Q&A:n virtuaalinen analyytikko näyttää merkityksellisen tiedon 2.

    ![Merkityksellinen tieto 2](media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-show-insight-2.png)
5. Avaa kaavio kohdistustilassa napauttamalla sitä.

    ![Merkityksellinen tieto 2 -kaavio kohdistustilassa](media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-open-insight-2.png)
6. Siirry takaisin Q&A:n virtuaaliseen analyytikkoon napauttamalla vasemmassa yläkulmassa olevaa nuolta.

## <a name="clean-up-resources"></a>Resurssien tyhjentäminen

Kun olet suorittanut opetusohjelman, voit poistaa Mahdollisuusanalyysimalli-koontinäytön, -raportin ja -tietojoukon.

1. Avaa Power BI -palvelu (app.powerbi.com) ja kirjaudu sisään.

2. Valitse vasemmassa siirtymisruudussa **Työtilat** > **Oma työtila**.

3. Valitse **Koontinäytöt**-välilehdessä Mahdollisuusanalyysi-koontinäytön vieressä oleva **Poista**-roskakorikuvake.

    ![Mallikoontinäytön poistaminen](media/tutorial-mobile-apps-ios-qna/power-bi-service-delete-opportunity-sample.png)

4. Siirry **Raportit**-välilehdelle ja toimi samoin Mahdollisuusanalyysi-raportin kohdalla.

5. Siirry **Tietojoukot**-välilehdelle ja toimi samoin Mahdollisuusanalyysi-tietojoukon kohdalla.


## <a name="next-steps"></a>Seuraavat vaiheet

Olet kokeillut Q&A:n virtuaaliavustajaa iOS-laitteiden Power BI -mobiilisovelluksissa. Lue lisää Q&A:sta Power BI -palvelussa.
> [!div class="nextstepaction"]
> [Q&A Power BI -palvelussa](power-bi-q-and-a.md)

