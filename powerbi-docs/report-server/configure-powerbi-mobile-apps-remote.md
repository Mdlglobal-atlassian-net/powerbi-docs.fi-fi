---
title: Mobiilisovelluksen käyttöoikeuksien etämäärittäminen raporttipalvelimelle
description: Lue, miten voit etämäärittää mobiilisovellukset raporttipalvelimelle.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/07/2019
ms.author: painbar
ms.openlocfilehash: b84d7a23cf947b18302c761ff5f78143bf3356aa
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "73925870"
---
# <a name="configure-power-bi-mobile-app-access-to-report-server-remotely"></a>Raporttipalvelimen käyttöoikeuksien etämäärittäminen Power BI -mobiilisovellukselle

Koskee seuraavia:

| ![iPhone](./media/configure-powerbi-mobile-apps-remote/ios-logo-40-px.png) | ![Android-puhelin](./media/configure-powerbi-mobile-apps-remote/android-logo-40-px.png) |
|:--- |:--- |
| iOS |Android |

Tässä artikkelissa kerrotaan, miten voit käyttää organisaatiosi ydintietojen hallintatyökalua määrittääksesi raporttipalvelimen käyttöoikeudet Power BI -mobiilisovellukselle. Tämän määrittämiseksi IT-järjestelmänvalvojat voivat luoda sovelluksen määrityskäytännön, joka lähettää vaaditut tiedot sovellukseen. 

 Power BI -mobiilisovelluksen käyttäjät voivat muodostaa yhteyden organisaationsa raporttipalvelimeen helpommin, koska raporttipalvelimen yhteys on jo määritetty. 

## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>Sovelluksen määrityskäytännön luominen MDM-työkalussa 

Järjestelmänvalvojat voivat luoda sovelluksen määrityskäytännön Microsoft Intunessa seuraavien vaiheiden mukaisesti. Vaiheet ja sovelluksen määrityskäytännön luominen saattavat olla erilaisia muissa ydintietojen hallintatyökaluissa. 

1. Yhdistä ydintietojen hallintatyökalu. 
2. Luo ja nimeä uusi sovelluksen määrityskäytäntö. 
3. Valitse käyttäjät, joille haluat jakaa tämän sovelluksen määrityskäytännön. 
4. Luo avain-arvoparit. 

Parit on havainnollistettu seuraavassa taulukossa.

|Avain  |Tyyppi.  |Description  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | Merkkijono | Raporttipalvelimen URL-osoite <br> Tulee alkaa merkkijonolla http tai https |
| com.microsoft.powerbi.mobile.ServerUsername | Merkkijono | [valinnainen] <br> Käyttäjänimi, jota käytetään muodostettaessa yhteyttä palvelimeen. <br> Jos sellaista ei ole, sovellus pyytää käyttäjää antamaan käyttäjänimen yhteyden muodostamista varten.| 
| com.microsoft.powerbi.mobile.ServerDisplayName | Merkkijono | [valinnainen] <br> Oletusarvo on ”Raporttipalvelin” <br> Kutsumanimi, joka edustaa palvelinta sovelluksessa | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boolean | Oletusarvo on Tosi (True) <br>Kun arvoksi on määritetty Tosi, se ohittaa mobiililaitteessa jo olevat raporttipalvelimen määritelmät. Tässä yhteydessä poistetaan olemassa olevat palvelimet, jotka on jo määritetty. <br> Ohituksen Tosi-arvo estää käyttäjää poistamista kyseistä määritystä. <br> Epätosi-arvo lisää lähetetyt arvot poistamatta olemassa olevia asetuksia. <br> Jos sama palvelimen URL-osoite on jo määritetty mobiilisovelluksessa, sovellus jättää sen määrityksen ennalleen. Sovellus ei pyydä käyttäjää todentamaan uudelleen samalle palvelimelle. |

Tässä on esimerkki määrityskäytännön asettamisesta Intunen avulla.

![Intune-määritysasetukset](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-report-server"></a>Käyttäjät, jotka muodostavat yhteyttä raporttipalvelimeen

 Oletetaan, että julkaiset jakeluluettelon sovelluksen määrityskäytännön. Kun tässä jakeluluettelossa olevat käyttäjät ja laitteet käynnistävät mobiilisovelluksen, toimitaan seuraavasti. 

1. Sanomassa ilmoitetaan mobiilisovelluksen olevan määritetty raporttipalvelimen kanssa. Käyttäjä voi **kirjautua sisään** napauttamalla.

    ![Kirjaudu sisään raporttipalvelimeen](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  **Muodosta yhteys palvelimeen** -sivulla raporttipalvelimen tiedot on valmiiksi täytetty. Käyttäjä napauttaa **Yhdistä**.

    ![Raporttipalvelimen tiedot esitäytettynä](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. Käyttäjä todennetaan salasanalla, minkä jälkeen hän napauttaa **Kirjaudu sisään**. 

    ![Raporttipalvelimen tiedot esitäytettynä](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

Nyt käyttäjä voi tarkastella ja käsitellä raporttipalvelimeen tallennettuja suorituskykyilmaisimia ja Power BI -raportteja.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Power BI -mobiilisovelluksen etäkäytön käyttöönotto Azure Active Directory -sovellusvälityspalvelimen avulla](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-integrate-with-power-bi)
- [Järjestelmänvalvojan yleiskatsaus](admin-handbook-overview.md)  
- [Power BI -raporttipalvelimen asentaminen](install-report-server.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

