---
title: 'Opetusohjelma: Yhteyden muodostaminen GitHub-säilöön Power BI:llä'
description: Tässä opetusohjelmassa yhdistät Power BI:n GitHub-palvelun oikeisiin tietoihin, jolloin Power BI luo automaattisesti koontinäyttöjä ja raportteja.
author: maggiesMSFT
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 08/07/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: a3c87a700df1c35596b6520cc64d9b580ccb74eb
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83332310"
---
# <a name="tutorial-connect-to-a-github-repo-with-power-bi"></a>Opetusohjelma: Yhteyden muodostaminen GitHub-säilöön Power BI:llä
Tässä opetusohjelmassa yhdistät Power BI:n GitHub-palvelun oikeisiin tietoihin, jolloin Power BI luo automaattisesti koontinäyttöjä ja raportteja. Muodostat yhteyden Power BI:n sisällön julkiseen säilöön (eli *säilöön*) ja näet vastauksen seuraavanlaisiin kysymyksiin: kuinka moni henkilö osallistuu Power BI:n julkiseen sisältöön? Kuka osallistuu eniten? Minä viikonpäivänä on eniten osallistumisia? Ja muita kysymyksiä. 

![GitHub-raportti Power BI:ssä](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-punch-card.png)

Tässä opetusohjelmassa käyt läpi seuraavat vaiheet:

> [!div class="checklist"]
> * Rekisteröi GitHub-tili, jos sinulla ei ole sellaista vielä 
> * Kirjaudu sisään Power BI -tilillesi tai rekisteröi tili, jos sinulla ei ole sellaista vielä
> * Avaa Power BI -palvelu
> * Etsi GitHub-sovellus
> * Anna Power BI:n julkisen GitHub-säilön tiedot
> * Tarkastele GitHub-tiedot sisältävää koontinäyttöä ja raporttia
> * Tyhjennä resursseja poistamalla sovellus

Jos et ole rekisteröitynyt Power BI:hin, [rekisteröidy ilmaiseen kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

Tarvitset tämän opetusohjelman suorittamiseen GitHub-tilin, jos sinulla ei ole vielä sellaista. 

- Rekisteröi [GitHub-tili](https://docs.microsoft.com/contribute/get-started-setup-github).


## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Kirjaudu sisään Power BI -palveluun (`https://app.powerbi.com`). 
2. Valitse siirtymisruudussa **Sovellukset** ja sitten **Hanki sovelluksia**.
   
   ![Power BI Hanki sovelluksia](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. Valitse **Sovellukset**, kirjoita **GitHub** hakuruutuun > **Hanki se nyt**.
   
   ![Power BI Hanki GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-app-source.png) 

4. Valitse **Asennetaanko tämä Power BI -sovellus?** -kohdassa **Asenna**.
5. Valitse **Siirry sovellukseen** kohdassa **Uusi sovelluksesi on valmis**.
6. Valitse **Aloita uuden sovelluksesi käyttö** -kohdassa **Yhdistä tiedot**.

    ![Aloita uuden sovelluksesi käyttö](media/service-tutorial-connect-to-github/power-bi-new-app-connect-get-started.png)

7. Kirjoita säilön nimi ja omistaja. Tämän säilön URL-osoite on https://github.com/MicrosoftDocs/powerbi-docs, joten **Säilön omistaja** on **MicrosoftDocs** ja **Säilö** on **powerbi-docs**. 
   
    ![Power BI GitHub-säilön nimi](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. Anna luomasi GitHub-tunnistetiedot. Power BI saattaa ohittaa tämän vaiheen, jos olet jo kirjautuneena GitHubiin selaimessa. 

6. Pidä valittuna **todennusmenetelmänä** **oAuth2** ja\> **Kirjaudu sisään**.

7. Noudata GitHubin todennusnäyttöjä. Anna Power BI:lle GitHub-tietojen käyttöoikeus.
   
   Nyt Power BI voi muodostaa yhteyden GitHubiin ja tietoihin.  Tiedot päivitetään kerran päivässä.

8. Kun Power BI on tuonut tiedot, näet uuden GitHub-työtilasi sisällön. 
9. Valitse siirtymisruudussa työtilan nimen vieressä oleva nuoli. Näet, että työtila sisältää koontinäytön ja raportin. 

    ![Sovellus siirtymisruudussa](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

10. Valitse **Enemmän vaihtoehtoja** (...) koontinäytön nimen vierestä > **Nimeä uudelleen** > kirjoita **GitHub-koontinäyttö**.
 
    ![Power BI GitHub-ruutu](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav.png) 

8. Pienennä siirtymisruutu valitsemalla yleinen siirtymiskuvake, jotta saat enemmän tilaa.

    ![Yleinen siirtymiskuvake](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. Valitse GitHub-koontinäyttösi.
    
    GitHub-koontinäyttö sisältää reaaliaikaisia tietoja, joten näkemäsi arvot voivat olla erilaisia.

    ![GitHub-koontinäyttö Power BI:ssä](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

    

## <a name="ask-a-question"></a>Esitä kysymys

1. Siirrä kohdistin **Esitä tietojasi koskeva kysymys** -kohtaan. Power BI tarjoaa **Kysymyksiä, joiden avulla pääset alkuun**. 

1. Valitse, **kuinka monta käyttäjää on olemassa**.
 
    ![Kuinka monta käyttäjää on olemassa](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-users.png)

13. Kirjoita **noutopyyntöä** **kuinka monta** ja **käyttäjää kohden on**. 

     Power BI luo palkkikaavion, joka näyttää noutopyyntöjen määrän henkilöä kohden.

    ![Kuinka monta noutopyyntöä käyttäjää kohden on](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-prs.png)


13. Kiinnitä se koontinäyttöösi valitsemalla PIN-tunnus ja **Sulje UKK.**

## <a name="view-the-github-report"></a>GitHub-raportin tarkasteleminen 

1. Avaa raportti valitsemalla GitHub-koontinäytössä sarakekaavio **Noutopyynnöt kuukauden mukaan**.

    ![Noutopyynnöt kuukauden mukaan -sarakekaavio](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-column-chart.png)

2. Valitse käyttäjänimi **Noutopyyntöjen kokonaismäärä käyttäjää kohden** -kaaviosta. Tässä esimerkissä näemme suurimman osa heidän työtunneistaan helmikuussa.

    ![Power BI GitHub-raportin korostaminen](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-cross-filter-total-prs.png)

3. Näytä raportin seuraava sivu valitsemalla **Pistekortti**-välilehti. 
 
    ![Power BI GitHub-raportin Pistekortti](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    Ilmeisesti tiistai kello 15 on yleisin viikonpäivä ja aika *vahvistuksille*, kun käyttäjät kuittaavat työnsä.

## <a name="clean-up-resources"></a>Puhdista resurssit

Nyt kun olet suorittanut opetusohjelman, voit poistaa GitHub-sovelluksen. 

1. Valitse siirtymisruudussa **Sovellukset**.
2. Siirrä hiiren osoitin GitHub-ruudun päälle ja valitse **Poista**-roskakori.

    ![Poista GitHub-sovellus](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa olet muodostanut yhteyden GitHubin julkiseen säilöön ja saanut tiedot, jotka Power BI on muotoillut koontinäytöksi ja raportiksi. Olet vastannut joihinkin tietoja koskeviin kysymyksiin tutkimalla koontinäyttöä ja raporttia. Nyt voi lukea lisää yhteyden muodostamisesta muihin palveluihin, kuten Salesforceen, Microsoft Dynamicsiin ja Google Analyticsiin. 
 
> [!div class="nextstepaction"]
> [Käyttämiisi verkkopalveluihin yhdistäminen](service-connect-to-services.md)


