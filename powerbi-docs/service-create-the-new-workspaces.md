---
title: Uusien työtilojen luominen (esiversio) – Power BI
description: Lue, miten luodaan uusia työtiloja, jotka ovat raporttinäkymien ja raporttien kokoelmia, joiden avulla voit kuvata organisaatiosi keskeisiä mittalukuja.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/11/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: eba4e740f6fd08ffd60b95dfc437551dfb95e7b8
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54293696"
---
# <a name="create-the-new-workspaces-preview-in-power-bi"></a>Uusien työtilojen luominen (esiversio) Power BI:ssä

Power BI:ssä esitellään uusi työtilakokemus esiversiona. Työtilat ovat edelleen paikkoja, joissa voi yhteistyössä työtovereiden kanssa luoda kokoelmia raporttinäkymistä ja raporteista. Kokoelmat voi paketoida *sovelluksiksi* ja jakaa koko organisaatiolle tai tietyille henkilöille tai ryhmille. 

![Power BI:n uusien työtilojen esiversio](media/service-create-the-new-workspaces/power-bi-new-workspaces-preview.png)

Uusien työtilojen esikatselun avulla voit nyt suorittaa seuraavia toimintoja:

- Työtilan roolien määrittäminen käyttäjäryhmille: käyttöoikeusryhmät, jakeluluettelot, Office 365 -ryhmiä ja henkilöt.
- Työtilan luominen Power BI:ssä luomatta Office 365 -ryhmää.
- Tarkempien työtilaroolien käyttäminen oikeuksien määrittämiseksi työtilassa entistä joustavammin.

Katso lisätietoja artikkelista [Uudet työtilat (esikatselu)](service-new-workspaces.md).

## <a name="create-one-of-the-new-app-workspaces"></a>Uuden sovellustyötilan luominen

1. Aloita luomalla sovellustyötila. Valitse **Työtilat** > **Luo sovelluksen työtila**.
   
     ![Luo sovellustyötila](media/service-create-the-new-workspaces/power-bi-create-app-workspace.png)

2. Valitse **Esikatsele paranneltuja työtiloja** -kohdassa **Kokeile nyt**.
   
     ![Esikatsele paranneltuja työtiloja](media/service-create-the-new-workspaces/power-bi-preview-improved-workspaces.png)

2. Anna työtilalle nimi. Jos nimi ei ole käytettävissä, muokkaa nimeä niin, että saat yksilöllisen tunnuksen.
   
     Sovelluksella on sama nimi kuin työtilalla.
   
1. Lisää kuva, jos haluat. Tiedostokoon on oltava pienempi kuin 45 kt.
 
    ![Työtilan nimeäminen ja kuvan lisääminen](media/service-create-the-new-workspaces/power-bi-name-workspace.png)

1. Valitse **Tallenna**.

    Tässä on uuden työtilasi **Tervetuloa**-näyttö. Voit lisätä tietoja. 

    ![Uuden työtilan Tervetuloa-näyttö](media/service-create-the-new-workspaces/power-bi-workspace-welcome-screen.png)

1. Valitse esimerkiksi **Mallit** > **Asiakkaan tuottavuuden malli**.

    Näet työtilan sisältöluettelossa **uusien työtilojen esiversion**. Koska olet järjestelmänvalvoja, näet myös uuden toiminnon **Käyttö**.

    ![Työtilojen esiversion sisältöluettelo](media/service-create-the-new-workspaces/power-bi-workspaces-preview-content-list.png)

1. Valitse **Käyttö**.

1. Lisää käyttöoikeusryhmiä, jakeluluetteloita, Office 365 -ryhmiä tai henkilöitä näihin työtiloihin jäseninä, osallistujina tai järjestelmänvalvojina. Eri roolien tarkempi kuvaus on [Roolit uusissa työtiloissa](service-new-workspaces.md#roles-in-the-new-workspaces) -kohdassa.

    ![Jäsenten, järjestelmänvalvojien ja osallistujien lisääminen työtiloihin](media/service-create-the-new-workspaces/power-bi-access-add-members.png)

9. Valitse **Lisää** > **Sulje**.

1. Power BI luo työtilan ja avaa sen. Näet sen niiden työtilojen luettelossa, joiden jäsen olet. Järjestelmänvalvojana voit valita kolme pistettä (...) ja palata takaisin tekemään muutoksia työtilan asetuksiin, lisäämään uusia jäseniä ja muuttamaan jäsenten käyttöoikeuksia.

     ![Työtilan asetusten ja käyttöoikeuksien muokkaaminen](media/service-create-the-new-workspaces/power-bi-edit-workspace.png)

## <a name="add-content-to-your-app-workspace"></a>Sisällön lisääminen sovellustyötilaan

Kun olet luonut uutta tyyliä olevan sovellustyötilan, on aika lisätä siihen sisältöä. Sisällön lisääminen tapahtuu samankaltaisella tavalla uusissa ja vanhoissa työtiloissa yhdellä poikkeuksella. Ollessasi jommassakummassa sovelluksen työtilassa voit ladata tai muodostaa yhteyden tiedostoihin aivan samalla tavalla kuin tekisit Omassa työtilassa. Uusissa työtiloissa et voi muodostaa yhteyttä organisaation sisältöpaketteihin tai kolmannen osapuolen sisältöpaketteihin, kuten Microsoft Dynamics CRM:ään, Salesforceen tai Google Analyticsiin. Voit nykyisissä työtiloissa muodostaa yhteyden sisältöpaketteihin.

Kun sisältöä tarkastellaan sovellustyötilan sisältöluettelossa, sovellustyötilan nimenä näkyy omistajan nimi.

### <a name="connecting-to-third-party-services-in-new-workspaces-preview"></a>Kolmannen osapuolen palveluihin yhdistäminen uusissa työtiloissa (esiversio)

Keskitymme uusien työtilojen kokemuksessa *sovelluksiin*. Kolmannen osapuolen palveluille tarkoitettujen sovellusten avulla käyttäjät voivat helposti noutaa tietoja käyttämistään palveluista, kuten Microsoft Dynamics CRM:stä, Salesforcesta tai Google Analyticsista.
Organisaation sovellusten kautta käyttäjät pääsevät käyttämään tarvitsemiansa sisäisiä tietoja. Aiomme lisätä ominaisuuksia organisaation sovelluksiin, jotta käyttäjät voivat mukauttaa sovelluksista löytyvää sisältöä. Tämän toiminnon ansiosta sisältöpaketteja ei enää tarvita. 

Et voi luoda tai käyttää organisaation sisältöpaketteja uusien työtilojen esiversiossa. Voit sen sijaan käyttää saatavilla olevia sovelluksia ja muodostaa yhteyden kolmannen osapuolen palveluihin tai pyytää sisäisiä ryhmiä tarjoamaan sovellukset tällä hetkellä käytössäsi oleviin sisältöpaketteihin. 

## <a name="distribute-an-app"></a>Sovelluksen jakaminen

Kun sisältö on valmis, valitset, mitkä raporttinäkymät ja raportit haluat julkaista, ja sitten julkaiset sen *sovelluksena*. Voit luoda yhden sovelluksen kustakin työtilasta. Työtoverisi voivat saada sovelluksesi käyttöönsä eri tavoin. Voit asentaa sen automaattisesti työtovereittesi Power BI -tileille, jos Power BI -järjestelmänvalvojasi antaa sinulle luvan. Muussa tapauksessa he voivat hakea ja asentaa sovelluksesi Microsoft AppSourcesta tai voit lähettää heille suoran linkin. He saavat päivitykset automaattisesti, ja sinä voit määrittää, kuinka usein tiedot päivitetään. Lisätietoja on artikkelissa [Raporttinäkymiä ja raportteja sisältävien sovellusten julkaiseminen Power BI:ssä](service-create-distribute-apps.md).

## <a name="convert-old-app-workspaces-to-new-app-workspaces"></a>Vanhojen sovellustyötilojen muuntaminen uusiksi sovellustyötiloiksi

Esiversion aikana et voi muuntaa vanhoja sovellustyötiloja automaattisesti uusiksi. Voit kuitenkin luoda uuden sovellustyötilan ja julkaista sisältöä uudessa sijainnissa. 

Kun uudet työtilat ovat yleisesti käytettävissä (GA), voit siirtää vanhat työtilat automaattisesti. Jonkin aikaa GA:n jälkeen ne on siirrettävä.

## <a name="next-steps"></a>Seuraavat vaiheet
* Lue [työn järjestämisestä uusissa työtiloissa (esikatselu) Power BI:ssä](service-new-workspaces.md)
* [Nykyisten työtilojen luominen](service-create-workspaces.md)
* [Asenna ja käytä sovelluksia Power BI:ssä](service-create-distribute-apps.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
