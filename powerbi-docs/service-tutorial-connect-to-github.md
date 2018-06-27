---
title: 'Opetusohjelma: Yhteyden muodostaminen GitHub-otokseen Power BI:llä'
description: Tässä opetusohjelmassa yhdistät Power BI:n GitHub-palvelun oikeisiin tietoihin, jolloin Power BI luo automaattisesti koontinäyttöjä ja raportteja.
author: maggiesMSFT
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.component: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 05/17/2018
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 1c2579f4250914933fd0459668fb55e4ba339f90
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34310103"
---
# <a name="tutorial-connect-to-a-github-sample-with-power-bi"></a>Opetusohjelma: Yhteyden muodostaminen GitHub-otokseen Power BI:llä
Tässä opetusohjelmassa yhdistät Power BI:n GitHub-palvelun oikeisiin tietoihin, jolloin Power BI luo automaattisesti koontinäyttöjä ja raportteja. Muodostat yhteyden Power BI:n sisällön julkiseen säilöön (eli *säilöön*) ja näet seuraavia tietoja: kuinka moni henkilö osallistuu Power BI:n julkiseen sisältöön? Kuka osallistuu eniten? Minä viikonpäivänä on eniten osallistumisia? Lisäksi näet vastauksia muihin kysymyksiin. 

![GitHub-raportti Power BI:ssä](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-punch-card.png)

Tässä opetusohjelmassa käyt läpi seuraavat vaiheet:

> [!div class="checklist"]
> * Rekisteröi GitHub-tili, jos sinulla ei ole sellaista vielä 
> * Kirjaudu sisään Power BI -tilillesi tai rekisteröi tili, jos sinulla ei ole sellaista vielä
> * Avaa Power BI -palvelu
> * Etsi GitHub-sovellus
> * Anna Power BI:n julkisen GitHub-säilön tiedot
> * Tarkastele GitHub-tietojen koontinäyttöä ja raporttia
> * Tyhjennä resursseja poistamalla sovellus

Jos et ole rekisteröitynyt Power BI:hin, [rekisteröidy ilmaiseen kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

Tarvitset tämän opetusohjelman suorittamiseen GitHub-tilin, jos sinulla ei ole vielä sellaista. 

- Rekisteröi [GitHub-tili](https://docs.microsoft.com/contribute/get-started-setup-github)


## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Kirjaudu sisään Power BI -palveluun (http://powerbi.com). 
2. Valitse vasemmassa siirtymisruudussa **Sovellukset** ja **Hanki sovelluksia**.
   
   ![Power BI Hanki sovelluksia](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. Valitse **Sovellukset**, kirjoita **github** hakuruutuun > **Hanki se nyt**.
   
   ![Power BI Hanki GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-get-it-now.png) 

4. Kirjoita säilön nimi ja omistaja. Tämän säilön URL-osoite on https://github.com/MicrosoftDocs/powerbi-docs, joten **Säilön omistaja** on **MicrosoftDocs** ja **Säilö** on **powerbi-docs**. 
   
    ![Power BI GitHub-säilön nimi](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-repo-name.png)

5. Anna luomasi GitHub-tunnistetiedot. Power BI saattaa ohittaa tämän vaiheen, jos olet jo kirjautuneena GitHubiin selaimessa. 

6. Valitse **todennusmenetelmäksi** **oAuth2** \> **Kirjaudu sisään**.

7. Noudata GitHubin todennusnäyttöjä. Anna Power BI:lle GitHub-tietojen käyttöoikeus.
   
   Nyt Power BI voi muodostaa yhteyden GitHubiin ja tietoihin.  Tiedot päivitetään kerran päivässä.

8. Kun Power BI on tuonut tiedot, näkyviin tulee uusi GitHub-ruutu. 
 
   ![Power BI GitHub-ruutu](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tile.png) 

8. Pienennä vasen siirtymisruutu valitsemalla yleinen siirtymiskuvake, jotta saat enemmän tilaa.

    ![Yleinen siirtymiskuvake](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. Valitse GitHub-ruutu vaiheesta 8. 
    
    GitHub-koontinäyttö avautuu. Nämä ovat reaaliaikaisia tietoja, joten näkemäsi arvot voivat olla erilaisia.

    ![GitHub-koontinäyttö Power BI:ssä](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-dashboard.png)

    

## <a name="ask-a-question"></a>Esitä kysymys

11. Siirrä kohdistin **Esitä tietojasi koskeva kysymys** -kohtaan ja valitse sitten **noutopyynnöt**. 

    ![Power BI Esitä tietojasi koskeva kysymys](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-ask-question.png)

12. Kirjoita **kuukauden mukaan**.
 
    ![Noutopyynnöt kuukauden mukaan](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-ask-question-by-month.png)

     Power BI luo palkkikaavion, joka näyttää noutopyyntöjen määrän kuukautta kohti.

13. Valitse **Poistu Q&A:sta**.

## <a name="view-the-github-report"></a>GitHub-raportin tarkasteleminen 

1. Avaa raportti valitsemalla GitHub-koontinäytössä yhdistetty sarake- ja rivikaavio **Noutopyynnöt kuukauden mukaan**.

    ![Noutopyynnöt kuukauden mukaan -yhdistelmäkaavio](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-pull-requests-combo-chart.png)

2. Valitse käyttäjänimi **Noutopyynnöt yhteensä käyttäjän mukaan** -kaaviosta ja katso tämän esimerkin mukaisesti, että keskimääräinen tuntimäärä on suurempi kuin keskimääräinen kokonaismäärä maaliskuussa.

    ![Power BI GitHub-raportin korostaminen](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-report-highlight.png)

3. Näytä raportin seuraava sivu valitsemalla **Pistekortti**-välilehti. 
 
    ![Power BI GitHub-raportin Pistekortti](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    Ilmeisesti tiistai kello 15 on yleisin viikonpäivä ja aika *vahvistuksille*, kun käyttäjät kuittaavat työnsä.

## <a name="clean-up-resources"></a>Resurssien tyhjentäminen

Nyt kun olet suorittanut opetusohjelman, voit poistaa GitHub-sovelluksen. 

1. Valitse vasemmassa siirtymispalkissa **Sovellukset**.
2. Siirrä hiiren osoitin GitHub-ruudun päälle ja valitse **Poista**-roskakori.

    ![Poista GitHub-sovellus](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa olet muodostanut yhteyden GitHubin julkiseen säilöön ja saanut tiedot, jotka Power BI on muotoillut koontinäytöksi ja raportiksi. Olet vastannut joihinkin tietoja koskeviin kysymyksiin tutkimalla koontinäyttöä ja raporttia. Nyt voi lukea lisää yhteyden muodostamisesta muihin palveluihin, kuten Salesforceen, Microsoft Dynamicsiin ja Google Analyticsiin. 
 
> [!div class="nextstepaction"]
> [Käyttämiisi verkkopalveluihin yhdistäminen](./service-connect-to-services.md)


