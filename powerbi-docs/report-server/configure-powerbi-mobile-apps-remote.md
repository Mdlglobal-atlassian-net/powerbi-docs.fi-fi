---
title: Raporttipalvelimen käyttöoikeuksien etämäärittäminen Power BI -iOS-mobiilisovellukselle
description: Lue, miten voit etämäärittää iOS-mobiilisovelluksen raporttipalvelimelle.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2018
ms.author: maggies
ms.openlocfilehash: bbade67c9510b8d316364d991c09444712309514
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34722174"
---
# <a name="configure-power-bi-ios-mobile-app-access-to-a-report-server-remotely"></a>Raporttipalvelimen käyttöoikeuksien etämäärittäminen Power BI -iOS-mobiilisovellukselle

Tässä artikkelissa kerrotaan, miten voit käyttää organisaatiosi ydintietojen hallintatyökalua määrittääksesi raporttipalvelimen käyttöoikeudet Power BI -iOS-mobiilisovellukselle. Tämän määrittämiseksi IT-järjestelmänvalvojat voivat luoda sovellusten määrityskäytännön, joka lähettää vaaditut tiedot sovellukseen. 

 Tämän jälkeen Power BI:n iOS-mobiilisovelluksen käyttäjät voivat muodostaa yhteyden organisaationsa raporttipalvelimeen entistä helpommin, koska raporttipalvelimen yhteys on jo määritetty. 


## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>Sovelluksen määrityskäytännön luominen MDM-työkalussa 

Järjestelmänvalvojat voivat luoda sovelluksen määrityskäytännön Microsoft Intunessa seuraavilla vaiheilla. Vaiheet ja sovelluksen määrityskäytännön luominen saattavat olla erilaisia muissa ydintietojen hallintatyökaluissa. 

1. Yhdistä ydintietojen hallintatyökalu. 
2. Luo ja nimeä uusi sovelluksen määrityskäytäntö. 
3. Valitse käyttäjät, joille haluat jakaa tämän sovelluksen määrityskäytännön. 
4. Luo avain-arvoparit. 

Parit on havainnollistettu seuraavassa taulukossa.

|Avain  |Tyyppi  |Kuvaus  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | Merkkijono | Raporttipalvelimen URL-osoite </br> Tulee alkaa merkkijonolla http tai https |
| com.microsoft.powerbi.mobile.ServerUsername | Merkkijono | [valinnainen] </br> Käyttäjänimi, jota käytetään muodostettaessa yhteyttä palvelimeen. </br> Jos sellaista ei ole, sovellus pyytää käyttäjää antamaan käyttäjänimen yhteyden muodostamista varten.| 
| com.microsoft.powerbi.mobile.ServerDisplayName | Merkkijono | [valinnainen] </br> Oletusarvo on ”Raporttipalvelin” </br> Kutsumanimi, joka edustaa palvelinta sovelluksessa | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | Totuusarvo | Oletusarvo on Tosi (True) </br> Jos arvo on ”Tosi”, tämä asetus ohittaa mobiililaitteella olevat raporttipalvelimen määritelmät (aiemmin määritetyt palvelimet poistetaan). </br> Ohituksen Tosi-arvo estää käyttäjää poistamista kyseistä määritystä. </br> Epätosi-arvo lisää lähetetyt arvot poistamatta olemassa olevia asetuksia. </br> Jos sama palvelimen URL-osoite on jo määritetty mobiilisovelluksessa, sovellus jättää sen määrityksen ennalleen eikä pyydä käyttäjän todentamista uudelleen kyseisen palvelimen tapauksessa. |

Tässä on esimerkki määrityskäytännön asettamisesta Intunen avulla.

![Intunen määritysasetukset](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-a-report-server"></a>Käyttäjät, jotka muodostavat yhteyttä raporttipalvelimeen

Sovelluksen määrityskäytännön julkaisemisen jälkeen käyttäjät ja laitteet, jotka kuuluvat kyseisessä käytännössä määritettyyn jakeluluetteloon, saavat seuraavan käyttökokemuksen käynnistäessään Power BI:n iOS-mobiilisovelluksen. 

1. Sanomassa ilmoitetaan mobiilisovelluksen olevan määritetty raporttipalvelimen kanssa. Käyttäjä voi **kirjautua sisään** napauttamalla.

    ![Kirjaudu sisään raporttipalvelimelle](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  **Muodosta yhteys palvelimeen** -sivulla raporttipalvelimen tiedot on valmiiksi täytetty. Käyttäjä napauttaa **Yhdistä**.

    ![Raporttipalvelimen tiedot esitäytettynä](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. Käyttäjä todennetaan salasanalla, minkä jälkeen hän napauttaa **Kirjaudu sisään**. 

    ![Raporttipalvelimen tiedot esitäytettynä](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

Nyt käyttäjä voi tarkastella ja käsitellä raporttipalvelimeen tallennettuja suorituskykyilmaisimia ja Power BI -raportteja.

## <a name="next-steps"></a>Seuraavat vaiheet
[Järjestelmänvalvojan yleiskatsaus](admin-handbook-overview.md)  
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

