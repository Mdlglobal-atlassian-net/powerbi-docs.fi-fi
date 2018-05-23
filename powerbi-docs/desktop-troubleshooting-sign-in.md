---
title: Power BI Desktopin kirjautumisongelmien vianmääritys
description: Ratkaisuja yleisiin Power BI Desktopin kirjautumisongelmiin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: dc3d7fc8e97876f3efb63c29261a5e9746b9ce8a
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/17/2018
---
# <a name="troubleshooting-sign-in-for-power-bi-desktop"></a>Power BI Desktopin kirjautumisongelmien vianmääritys
Saatat **Power BI Desktopiin** kirjautuessasi kohdata ongelmia. Kirjautumisongelmiin on kaksi yleistä syitä: **välityspalvelimen todennusvirheet** ja **ei-HTTPS-protokollan URL-osoitteen uudelleenohjausvirheet**. 

Ensimmäinen vaihe voit selvittää, mistä kirjautumisongelma johtuu. Ota yhteyttä järjestelmänvalvojaan ja anna diagnostiikkatiedot, jotta ongelman syy voidaan määrittää. Jäljittämällä kirjautumisongelmiin liittyvien ongelmien syyt järjestelmänvalvojat voivat määrittää, mitkä seuraavista virheistä koskevat sinua. 

Tutustutaan näihin ongelmiin vuorotellen. Tämän artikkelin lopussa on tietoa siitä, miten voit tallentaa vianmäärityksessä auttavan *jäljityksen* Power BI Desktopissa.


## <a name="proxy-authentication-required-error"></a>Välityspalvelimen todennus vaaditaan -virhe

Seuraavassa kuvassa näkyy *Välityspalvelimen todennus vaaditaan* -virhe.

![Välityspalvelimen todennus -virheen aiheuttama kirjautumisvirhe](media/desktop-troubleshooting-sign-in/desktop-tshoot-sign-in_01.png)

Seuraavat *Power BI Desktop* -jäljitystiedostojen poikkeukset koskevat tätä virhettä:

* *Microsoft.PowerBI.Client.Windows.Services.PowerBIWebException*
* *HttpStatusCode: ProxyAuthenticationRequired*

Tämän virheen todennäköisin syy on, että todennukseen käytettävä verkkosi välityspalvelin estää **Power BI Desktopin** lähettämät verkkopyynnöt. 

Jos verkkosi käyttää todennukseen välityspalvelinta, järjestelmänvalvojasi voi korjata tämän ongelman lisäämällä seuraavat toimialueet todennukseen käytettävän välityspalvelimen sallittujen luetteloon:

* app.powerbi.com
* api.powerbi.com
* toimialueet, jonka kuuluvat *. analysis.windows.net -nimitilaan

Jos asiakas kuuluu julkishallinnon pilvipalveluun, ongelma voidaan korjata lisäämällä seuraavat toimialueen todennukseen käytettävän välityspalvelimen sallittujen luetteloon:

* app.powerbigov.us
* api.powerbigov.us
* toimialueet, jotka kuuluvat *. analysis.usgovcloudapi.net -nimitilaan

## <a name="non-https-url-redirect-not-supported-error"></a>URL-uudelleenohjausta ei-HTTPS-protokollaan ei tueta -virhe

Nykyiset **Power BI Desktopin** versiot käyttävät Active Directory Authentication Library (ADAL) -kirjastoa, joka ei salli uudelleenohjausta suojaamattomiin (muihin kuin HTTPS-) URL-osoitteisiin. 

Seuraavat *Power BI Desktop* -jäljitystiedostojen poikkeukset koskevat tätä virhettä:

* *Microsoft.IdentityModel.Clients.ActiveDirectory.AdalServiceException: URL-uudelleenohjausta ei-HTTPS-protokollaan ei tueta verkkonäkymässä* 
* *ErrorCode: non_https_redirect_failed*

Jos saat *ErrorCode: non_https_redirect_failed* -virheilmoituksen, yksi tai useampi uudelleenohjaussivu tai uudelleenohjausketjun palveluntarjoaja ei ole suojattu HTTPS-päätepiste tai että yhden tai useamman uudelleenohjauksen varmenteen myöntäjä ei ole laitteen luotettujen pääkansioiden joukossa. Kaikkien sisäänkirjautumisen uudelleenohjausketjun palveluntarjoajien on käytettävä HTTPS-URL-osoitetta. Ota yhteyttä järjestelmänvalvojaan ja pyydä, että todennussivustoissa käytetään suojattuja URL-osoitteita. 

## <a name="how-to-collect-a-trace-in-power-bi-desktop"></a>Jäljityksen kerääminen Power BI Desktopissa

Voit kerätä jäljityksen **Power BI Desktopissa** seuraavasti:

1. Ota jäljitys käyttöön **Power BI Desktopissa** siirtymällä kohtaan **Tiedosto > Asetukset ja vaihtoehdot > Asetukset** ja valitse sitten **Diagnostiikka** vasemmanpuoleisen ruudun vaihtoehdoista. Valitse avautuvasta ruudusta **Ota jäljitys käyttöön** -kohdan vieressä oleva valintaruutu (ks. kuva). Sinua saatetaan pyytää käynnistämään **Power BI Desktop** uudelleen.
   
   ![Jäljityksen ottaminen käyttöön Power BI Desktopissa](media/desktop-troubleshooting-sign-in/desktop-tshoot-sign-in_02.png)

2. Toista sitten vaiheet, jotka aiheuttivat virhetilanteen. Kun näin tapahtuu, **Power BI Desktop** lisää tapahtumat jäljityslokiin, jota säilytetään paikallisessa tietokoneessa.

3. Siirry paikallisen tietokoneen jäljityskansioon. Voit etsiä kansion valitsemalla linkin **Diagnostiikka**-kohdasta, josta otit jäljityksen käyttöön. Kansio näkyy edellisessä kuvassa muodossa *Avaa kaatumisvedosten/jäljitysten kansio*. Kansio on tavallisesti seuraavassa sijainnissa paikallisessa tietokoneessa:

    `C:\Users/<user name>/AppData/Local/Microsoft/Power BI Desktop/Traces`

Kyseisessä kansiossa voi olla useita jäljitystiedostoja. Lähetä järjestelmänvalvojalle vain viimeisimmät tiedostot virheen tunnistamisen helpottamiseksi. 

