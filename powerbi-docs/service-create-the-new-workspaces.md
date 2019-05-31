---
title: Luo uuden työtilakokemuksen - Power BI
description: Lue, miten voit luoda uuden työtilakokemuksen kokoelmia koontinäyttöjen, raporttien ja Sivutettujen raporttien, joiden avulla voit kuvata organisaatiosi keskeisiä mittalukuja.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d0c0781ea5d3864f1cf3627cd42d53cca632102d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61141948"
---
# <a name="create-the-new-workspaces-in-power-bi"></a>Luo uusi työtilat Power BI

Power BI on ottanut käyttöön työtilan uuden kokemuksen. Työtilat ovat edelleen paikassa, voit tehdä yhteistyötä työtovereiden kanssa kokoelmia koontinäyttöjen, raporttien ja Sivutettujen raporttien luomiseksi. Sitten voit niputtaa kyseisen sivustokokoelman *sovelluksen* ja jakaa sen koko organisaatiolle tai tietyille henkilöille tai ryhmille. 

Tässä on tietoja. Uuden työtilakokemuksen voit tehdä seuraavaa:

- Työtilan roolien määrittäminen käyttäjäryhmille: käyttöoikeusryhmät, jakeluluettelot, Office 365 -ryhmiä ja henkilöt.
- Työtilan luominen Power BI:ssä luomatta Office 365 -ryhmää.
- Tarkempien työtilaroolien käyttäminen oikeuksien määrittämiseksi työtilassa entistä joustavammin.

> [!NOTE]
> Jos haluat ottaa rivitason suojaus (RLS) Power BI Pro käyttäjille selaamalla sisältöä työtilassa, edelleen käyttää [perinteinen työtilat](service-create-workspaces.md). Valitse **jäsenet voivat vain tarkastella Power BI-sisältöä** vaihtoehto. Vaihtoehtoisesti julkaista Power BI-sovelluksen näille käyttäjille tai sisällön jakamisen avulla. Tulevan Viewer-roolin mahdollistaa tämän skenaarion tulevaisuudessa työtiloissa uusi työtilan käyttökokemuksen.

Katso lisätietoja tausta [uuden työtilakokemuksen](service-new-workspaces.md) artikkelissa.

## <a name="create-one-of-the-new-app-workspaces"></a>Uuden sovellustyötilan luominen

1. Aloita luomalla sovellustyötila. Valitse **Työtilat** > **Luo sovelluksen työtila**.
   
     ![Luo sovellustyötila](media/service-create-the-new-workspaces/power-bi-create-app-workspace.png)

2. Automaattisesti luot päivitetyn työtilassa, ellei annat **perinteinen palata**.
   
     ![Uusi työtila-käyttökokemus](media/service-create-the-new-workspaces/power-bi-new-workspace.png)
     
     Jos valitset **perinteinen palata**, luot työtila Office 365-ryhmän perusteella. Käytä tätä vaihtoehtoa, jos tarvitset **jäsenet voivat vain tarkastella Power BI-sisältöä** vaihtoehto, jos haluat ottaa rivitason suojaus (RLS) pakotetusti käyttöön työtilan jäseniä.

2. Anna työtilalle nimi. Jos nimi ei ole käytettävissä, Muokkaa nimeä niin, jolla on yksilöivä nimi.
   
     Sovelluksen työtilan on sama nimi ja kuvake työtila.
   
1. Tässä on joitakin valinnainen kohteita, voit määrittää työtilassa:

    Lataa **työtilan kuvan**. Tiedostoja voi olla .png tai .jpg-muodossa. Tiedostokoko on oltava alle 45 kt.
    
    [Lisää **yhteystietoluettelo**](#workspace-contact-list). Työtilan järjestelmänvalvojat ovat oletusarvoisesti yhteystiedot. 
    
    [Määritä **työtilan OneDrive** ](#workspace-onedrive) kirjoittamalla nimi olemassa oleva Office 365-ryhmä, ei URL-osoite. Tämän työtilan voit nyt käyttää kyseisen Office 365-ryhmän tallennustilan sijainti. 

    ![Määritä OneDrive sijainti](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

    Määrittää työtila **varattu kapasiteetti**, **Premium** välilehti ja valitse **varattu kapasiteetti**.
     
    ![Varattu kapasiteetti](media/service-create-the-new-workspaces/power-bi-workspace-premium.png)

1. Valitse **Tallenna**.

    Power BI luo työtilan ja avaa sen. Näet sen niiden työtilojen luettelossa, joiden jäsen olet. 

## <a name="workspace-contact-list"></a>Työtilan yhteystietoluettelon

Uusi työtila-yhteystietoluettelon avulla voit määrittää käyttäjät, jotka saat ilmoituksen kohteiden työtilan ongelmista. Oletusarvon mukaan kaikki käyttäjän tai ryhmän määritetty työtilan järjestelmänvalvojan ilmoitetaan, mutta voit mukauttaa luetteloa. Käyttäjille tai ryhmille, ota yhteyttä luettelossa näytetään käyttöliittymässä (UI), joiden avulla käyttäjät saavat työtilaan liittyviä ohjeita.

1. Käyttää uusi **yhteystietoluettelo** asetus kahdella eri tavalla:

    Tässä **Luo työtila** ruudussa, kun luot sen.

    Valitse vasemmassa siirtymisruudussa nuolta kohdan **työtilat**, valitse työtilan nimen vierestä kohdasta kolme pistettä (...) > **työtilan asetukset**. **Asetukset** ruutu avautuu.

    ![Työtilan asetukset](media/service-create-the-new-workspaces/power-bi-workspace-settings.png)

2. Valitse **lisäasetukset** > **yhteystietoluettelo**, hyväksyä oletusarvon **työtilan järjestelmänvalvojat**, tai lisätä omia luettelo **tietyille käyttäjille tai ryhmille**. 
3. Valitse **Tallenna**.

## <a name="workspace-onedrive"></a>Workspace OneDrive

Työtilan OneDrive-ominaisuuden avulla voit määrittää Office 365-ryhmä SharePoint-tiedostokirjastoon jonka tiedostosäilö on työtilan käyttäjien käytettävissä. Ryhmän ulkopuolella Power BI luo ensin. 

Power BI ei synkronoi käyttäjät tai ryhmät, jotka on määritetty työtila Office 365-ryhmän jäsenyys käytön käyttöoikeudet. Paras käytäntö on annettava sama Office 365-ryhmän, jonka määrität tämän asetuksen Office 365-ryhmän tiedostosäilö [työtilan käyttöoikeus](#give-access-to-your-workspace). Sitten voit hallita työtilan käyttöoikeus Office 365-ryhmän jäsenyyden hallinta. 

1. Käyttää uusi **työtilan OneDrive** asetus kahdella eri tavalla:

    Tässä **Luo työtila** ruudussa, kun luot sen.

    Valitse vasemmassa siirtymisruudussa nuolta kohdan **työtilat**, valitse työtilan nimen vierestä kohdasta kolme pistettä (...) > **työtilan asetukset**. **Asetukset** ruutu avautuu.

    ![Työtilan asetukset](media/service-create-the-new-workspaces/power-bi-workspace-settings.png)

2. Valitse **lisäasetukset** > **työtilan OneDrive**, Office 365-ryhmän luomasi käyttöoikeusjoukon nimi. Ryhmän OneDrive vastataan automaattisesti Power BI.

    ![Määritä OneDrive sijainti](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

3. Valitse **Tallenna**.

### <a name="access-the-workspace-onedrive-location"></a>Käyttää OneDrive-sijainti-työtila

Sen jälkeen, kun olet määrittänyt OneDrive-sijaintiin, pääset sen työtilaan joitakin eri paikoista:

- Valitse **työtilat** > *työtilan nimi* > kolme pistettä ( **...** ) valikko > **tiedostot**. 

    ![Työtilan sijainti](media/service-new-workspaces/power-bi-new-workspace-files.png)

- Valitse kolme pistettä ( **...** ) valikko työtilan oikeassa yläkulmassa > **tiedostot**.

    ![Työtilan sijainti](media/service-new-workspaces/power-bi-new-workspace-files-2.png)
    
- Tässä **Nouda tiedot** > **tiedostot** kohdata. **OneDrive – yritys** tapahtuma on oma OneDrive for Businessiin. Toinen OneDrive on lisätty.

    ![Työtilan sijainti - Nouda tiedot](media/service-new-workspaces/power-bi-new-workspace-get-data-onedrive.png)

## <a name="add-content-to-your-app-workspace"></a>Sisällön lisääminen sovellustyötilaan

Kun olet luonut uusi työtilan kokemus työtila, on aika sisällön lisäämiseen. Uudet ja perinteinen työtiloissa muistuttaa lisääminen sisältöä. Käytä Luo-painiketta tai lisätä sisältöä työtilassa Nouda tiedot.

1. Tässä **Tervetuloa** näytön uusi työtilassa voit lisätä sisältöä. 

    ![Uuden työtilan Tervetuloa-näyttö](media/service-create-the-new-workspaces/power-bi-workspace-welcome-screen.png)

1. Valitse esimerkiksi **Mallit** > **Asiakkaan tuottavuuden malli**.

> [!NOTE]
> Uusien työtilojen voi kuluttaa organisaation sisältöpakettien tai kolmannen osapuolen Sisältöpaketit. Sovellukset ovat käytettävissä kaikki kolmannen osapuolen sisältöpaketteja, voit käyttää aiemmin. Käytä perinteinen työtilat, jos haluat jatkaa Sisältöpaketit. Sisältöpaketit ovat vanhentuneet, joten Suosittelemme käyttämään sovelluksia.

Kun sisältöä tarkastellaan sovellustyötilan sisältöluettelossa, sovellustyötilan nimenä näkyy omistajan nimi.

### <a name="connecting-to-third-party-services-in-new-workspaces"></a>Uusi työtiloissa kolmannen osapuolen palveluihin yhdistäminen

Keskitymme uusien työtilojen kokemuksessa *sovelluksiin*. Kolmannen osapuolen palveluille tarkoitettujen sovellusten avulla käyttäjät voivat helposti noutaa tietoja käyttämistään palveluista, kuten Microsoft Dynamics CRM:stä, Salesforcesta tai Google Analyticsista.

Työtilan uuden kokemuksen ei voi luoda tai käyttää organisaation sisältöpaketteja. Voit sen sijaan käyttää saatavilla olevia sovelluksia ja muodostaa yhteyden kolmannen osapuolen palveluihin tai pyytää sisäisiä ryhmiä tarjoamaan sovellukset tällä hetkellä käytössäsi oleviin sisältöpaketteihin. 

## <a name="give-access-to-your-workspace"></a>Käyttöoikeuden myöntäminen työtilassa

1. Työtilan sisältöluettelosta, koska olet järjestelmänvalvoja näet uuden toiminnon **Access**.

    ![Työtilat sisältöluettelo](media/service-create-the-new-workspaces/power-bi-workspace-content-list.png)

1. Valitse **Käyttö**.

1. Lisää käyttöoikeusryhmiä, jakeluluetteloita, Office 365 -ryhmiä tai henkilöitä näihin työtiloihin jäseninä, osallistujina tai järjestelmänvalvojina. Eri roolien tarkempi kuvaus on [Roolit uusissa työtiloissa](service-new-workspaces.md#roles-in-the-new-workspaces) -kohdassa.

    ![Jäsenten, järjestelmänvalvojien ja osallistujien lisääminen työtiloihin](media/service-create-the-new-workspaces/power-bi-access-add-members.png)

9. Valitse **Lisää** > **Sulje**.


## <a name="distribute-an-app"></a>Sovelluksen jakaminen

Jos haluat virallinen sisältöä organisaation sisällä suuri yleisö, voit julkaista sovelluksen työtilasta.  Kun sisältö on valmis, valitse, mitkä koontinäytöt ja raportit haluat julkaista ja julkaise se *sovelluksen*. Voit luoda yhden sovelluksen kustakin työtilasta.

Lue [uuden työtilakokemuksen sovelluksen julkaiseminen](service-create-distribute-apps.md)

## <a name="next-steps"></a>Seuraavat vaiheet
* Lue [järjestäminen uuden työtilat-toiminnon Power BI: ssä](service-new-workspaces.md)
* [Perinteiset työtilan luominen](service-create-workspaces.md)
* [Julkaise Power BI-sovelluksen uuden työtilakokemuksen](service-create-distribute-apps.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
