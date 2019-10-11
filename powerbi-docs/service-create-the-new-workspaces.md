---
title: Uusien työtilojen luominen ̶ Power BI
description: Lue, miten voit luoda uusia työtiloja, raporttinäkymien kokoelmia, raportteja ja sivutettuja raportteja, joiden avulla voit kuvata organisaatiosi keskeisiä mittalukuja.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/10/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5c50ec38da65573e085d9e27b0e31524256ac009
ms.sourcegitcommit: d04b9e1426b8544ce16ef25864269cc43c2d9f7b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "71715540"
---
# <a name="create-the-new-workspaces-in-power-bi"></a>Uusien työtilojen luominen Power BI:ssä

Power BI:ssä esitellään uusi työtilakokemus. Työtilat ovat edelleen paikkoja, joissa voit yhdessä työtovereiden kanssa luoda raporttinäkymien, raporttien ja sivutettujen raporttien kokoelmia. Sen jälkeen voit niputtaa ne yhteen *sovellukseksi* ja jakaa sen koko organisaatiolle tai tietyille henkilöille tai ryhmille. 

Seuraavat asiat ovat muuttuneet. Uusissa työtiloissa voit:

- Työtilan roolien määrittäminen käyttäjäryhmille: käyttöoikeusryhmät, jakeluluettelot, Office 365 -ryhmiä ja henkilöt.
- Työtilan luominen Power BI:ssä luomatta Office 365 -ryhmää.
- Tarkempien työtilaroolien käyttäminen oikeuksien määrittämiseksi työtilassa entistä joustavammin.

> [!NOTE]
> Jos haluat pakottaa rivitason suojauksen (RLS) käyttöön työtilan sisältöä selaaville Power BI Pro -käyttäjille, määritä käyttäjille Katselija-rooli.

Katso lisätietoja artikkelista [Uudet työtilat](service-new-workspaces.md).

## <a name="create-one-of-the-new-workspaces"></a>Uuden työtilan luominen

1. Aloita luomalla työtila. Valitse **Työtilat** > **Luo työtila**.
   
     ![Työtilan luominen](media/service-create-the-new-workspaces/power-bi-workspace-create.png)

2. Sinulle luodaan oletuksena uudenlainen työtila, ellet halua **palata perinteisen** työtilan käyttöön.
   
     ![Uusi työtilakokemus](media/service-create-the-new-workspaces/power-bi-new-workspace.png)
     
     Jos valitset **Palaa perinteiseen**, luot [Office 365 -ryhmään perustuvan työtilan](service-create-workspaces.md). 

2. Anna työtilalle nimi. Jos nimi ei ole käytettävissä, muokkaa nimi yksilölliseksi.
   
     Työtilan sovelluksella on oltava sama nimi ja kuvake kuin työtilalla.
   
1. Tässä on joitain valinnaisia kohteita, joita voit asettaa työtilaasi:

    Lataa **Työtilan kuva** palvelimeen. Tiedostot voivat olla .png- tai .jpg-muotoisia. Tiedostokoon on oltava alle 45 kt.
    
    [Lisää **Yhteystietoluettelo**](#workspace-contact-list). Työtilan järjestelmänvalvojat ovat oletusarvoisia yhteyshenkilöitä. 
    
    [Määritä **työtilan OneDrive**](#workspace-onedrive) kirjoittamalla olemassa olevan Office 365 -ryhmän nimi (ei URL-osoite). Nyt tämä työtila voi käyttää Office 365 -ryhmän tiedostosäilön sijaintia. 

    ![OneDrive-sijainnin määrittäminen](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

    Valitse **Erillinen kapasiteetti** **Premium**-välilehdeltä, jotta voit määrittää työtilan **Erilliseen kapasiteettiin**.
     
    ![Varattu kapasiteetti](media/service-create-the-new-workspaces/power-bi-workspace-premium.png)

1. Valitse **Tallenna**.

    Power BI luo työtilan ja avaa sen. Näet sen niiden työtilojen luettelossa, joiden jäsen olet. 

## <a name="workspace-contact-list"></a>Työtilan yhteystietoluettelo

Uuden yhteystietoluettelon avulla voit määrittää käyttäjät, joille ilmoitetaan työtilassa esiintyneistä ongelmista. Oletusarvon mukaan ilmoitus annetaan kaikille käyttäjille tai ryhmille, jotka on määritetty työtilan järjestelmänvalvojiksi, mutta voit mukauttaa luetteloa. Yhteystietoluettelossa luetellut käyttäjät tai ryhmät näytetään käyttöliittymässä (UI), jotta käyttäjät saavat työtilaa koskevaa apua.

1. Pääset uuteen **Yhteystietoluettelo**-asetukseen kahdella tavalla:

    **Luo työtila** -ruudusta, kun luot sen ensimmäisen kerran.

    Valitse vasemmassa siirtymisruudussa **Työtilat**-kohdan vieressä oleva nuoli. Valitse pistekuvake (...) työtilan nimen vieressä ja valitse **Työtilan asetukset**. **Asetukset**-ruutu avautuu.

    ![Työtilan asetukset](media/service-create-the-new-workspaces/power-bi-workspace-new-settings.png)

2. Hyväksy **Lisäasetukset** > **Yhteystietoluettelo**-kohdan oletusasetus (**Työtilan järjestelmänvalvojat**) tai lisää oma **tiettyjen käyttäjien tai ryhmien** luettelo. 
3. Valitse **Tallenna**.

## <a name="workspace-onedrive"></a>Työtilan OneDrive

Työtilan OneDrive -ominaisuuden avulla voit määrittää Office 365 -ryhmän, jonka SharePoint-tiedostokirjaston tiedostosäilö on työtilan käyttäjien käytettävissä. Luot ryhmän ensin Power BI:n ulkopuolella. 

Power BI ei synkronoi niiden käyttäjien tai ryhmien käyttöoikeuksia, joille on määritetty työtilan käyttöoikeus Office 365 -ryhmän jäsenyyden yhteydessä. Paras käytäntö on antaa Office 365 -ryhmälle, jonka tiedostosäilön määritit tämän asetuksen Office 365 -ryhmässä, samat [työtilan käyttöoikeudet](#give-access-to-your-workspace). Hallitse työtilan käyttöoikeuksia Office 365 -ryhmän jäsenyyksien kautta. 

1. Voit käyttää uuden **työtilan OneDriven** asetusta kahdella tavalla:

    **Luo työtila** -ruudusta, kun luot sen ensimmäisen kerran.

    Valitse vasemmassa siirtymisruudussa **Työtilat**-kohdan vieressä oleva nuoli. Valitse pistekuvake (...) työtilan nimen vieressä ja valitse **Työtilan asetukset**. **Asetukset**-ruutu avautuu.

    ![Työtilan asetukset](media/service-create-the-new-workspaces/power-bi-workspace-new-settings.png)

2. Kirjoita **Lisäasetukset** > **Työtilan OneDrive** -kohtaan aiemmin luomasi Office 365 -ryhmän nimi. Power BI valitsee automaattisesti ryhmän OneDriven.

    ![OneDrive-sijainnin määrittäminen](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

3. Valitse **Tallenna**.

### <a name="access-the-workspace-onedrive-location"></a>Työtilan OneDrive-sijaintiin pääseminen

Kun olet määrittänyt OneDrive-sijainnin, voit päästä siihen muutamista työtilan eri paikoista:

- Valitse **Työtilat** > *työtilan nimi* > pistevalikko ( **...** ) > **Tiedostot**. 

    ![Työtilan tiedostojen sijainti](media/service-new-workspaces/power-bi-new-workspace-files.png)

- Valitse pistevalikko ( **...** ) työtilan oikeasta yläkulmasta > **Tiedostot**.

    ![Työtilan tiedostojen sijainti](media/service-create-the-new-workspaces/power-bi-new-workspace-files-ellipsis.png)
    
- **Nouda tiedot** > **Tiedostot**-käyttökokemuksen kautta. **OneDrive – Business** -kirjaus viittaa omaan OneDrive for Business -palveluusi. Toinen OneDrive on se, jonka lisäsit.

    ![Työtilan tiedostojen sijainti ̶ tietojen noutaminen](media/service-create-the-new-workspaces/power-bi-new-workspace-get-data-onedrive.png)

## <a name="add-content-to-your-workspace"></a>Sisällön lisääminen työtilaan

Kun olet luonut uuden käyttökokemuksen mukaisen työtilan, voit alkaa lisätä siihen sisältöä. Sisällön lisääminen toimii uusissa ja perinteisissä työtiloissa samalla tavalla. Lisää sisältöä työtilaasi Luo-painikkeen tai Nouda tiedot -toiminnon avulla.

1. Voit lisätä tietoja uuden työtilasi **Tervetuloa**-näytön kautta. 

    ![Uuden työtilan Tervetuloa-näyttö](media/service-create-the-new-workspaces/power-bi-workspace-get-data.png)

1. Valitse esimerkiksi **Mallit** > **Asiakkaan tuottavuuden malli**.

> [!NOTE]
> Et voi lisätä organisaation sisältöpaketteja tai kolmansien osapuolten sisältöpaketteja uusiin työtiloihin. Sovellukset ovat käytettävissä useissa aiemmin käyttämissäsi kolmansien osapuolten sisältöpaketeissa. Käytä perinteisiä työtiloja, jos sinun on käytettävä sisältöpaketteja. Sisältöpaketit on poistettu käytöstä, joten on parempi käyttää sen sijaan sovelluksia.

Kun sisältöä tarkastellaan työtilan sisältöluettelossa, työtilan nimenä näkyy omistajan nimi.

### <a name="connecting-to-third-party-services-in-new-workspaces"></a>Kolmannen osapuolen palveluihin yhdistäminen uusissa työtiloissa

Keskitymme uusien työtilojen kokemuksessa *sovelluksiin*. Kolmannen osapuolen palveluille tarkoitettujen sovellusten avulla käyttäjät voivat helposti noutaa tietoja käyttämistään palveluista, kuten Microsoft Dynamics CRM:stä, Salesforcesta tai Google Analyticsista.

Et voi luoda tai käyttää organisaation sisältöpaketteja uudenlaisissa työtiloissa. Voit sen sijaan käyttää saatavilla olevia sovelluksia ja muodostaa yhteyden kolmannen osapuolen palveluihin tai pyytää sisäisiä ryhmiä tarjoamaan sovellukset tällä hetkellä käytössäsi oleviin sisältöpaketteihin. 

## <a name="give-access-to-your-workspace"></a>Työtilan käyttöoikeuksien antaminen

1. Järjestelmänvalvojat näkevät työtilan sisältöluettelossa uuden toiminnon, **Käyttöoikeudet**.

    ![Työtilojen sisältöluettelo](media/service-create-the-new-workspaces/power-bi-new-workspace-files-ellipsis.png)

1. Valitse **Käyttö**.

1. Lisää käyttöoikeusryhmiä, jakeluluetteloita, Office 365 -ryhmiä tai henkilöitä näihin työtiloihin jäseninä, osallistujina tai järjestelmänvalvojina. Eri roolien tarkempi kuvaus on [Roolit uusissa työtiloissa](service-new-workspaces.md#roles-in-the-new-workspaces) -kohdassa.

    ![Jäsenten, järjestelmänvalvojien ja osallistujien lisääminen työtiloihin](media/service-create-the-new-workspaces/power-bi-workspace-add-members.png)

9. Valitse **Lisää** > **Sulje**.


## <a name="distribute-an-app"></a>Sovelluksen jakaminen

Jos haluat levittää virallista sisältöä suurelle yleisölle organisaatiossasi, voit julkaista sovelluksen työtilasta.  Kun sisältö on valmis, valitse julkaistaviksi haluamasi raporttinäkymät ja raportit ja julkaise se *sovelluksena*. Voit luoda yhden sovelluksen kustakin työtilasta.

Lisätietoja [sovelluksen julkaisemisesta uuden työtilan kautta](service-create-distribute-apps.md)

## <a name="next-steps"></a>Seuraavat vaiheet
* Lue [työn järjestämisestä uusissa työtiloissa Power BI:ssä](service-new-workspaces.md)
* [Perinteisten työtilojen luominen](service-create-workspaces.md)
* [Sovelluksen julkaiseminen uusista työtiloista Power BI:ssä](service-create-distribute-apps.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
