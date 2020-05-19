---
title: Yhteyden muodostaminen Smartsheetiin Power BI:llä
description: Smartsheet Power BI:lle
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 4498557d1bd38ce457b2e79d637e713af11c945a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83325042"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Yhteyden muodostaminen Smartsheetiin Power BI:llä
Tässä artikkelissa kerrotaan tietojen hakemisesta Smartsheet-tililtäsi Power BI -mallisovelluksella. Smartsheet tarjoaa helpon alustan yhteiskäyttöön ja tiedostojen jakamiseen. Smartsheet-mallisovellus Power BI:lle sisältää koontinäytön, raportteja ja tietojoukon, joka näkyy Smartsheet-tilisi yleiskuvauksessa. Voit käyttää myös [Power BI Desktopia](desktop-connect-to-data.md) yhteyden muodostamiseen tilisi yksittäisiin laskentataulukoihin. 

Kun olet asentanut mallisovelluksen, voit muuttaa koontinäyttöä ja raporttia. Sen jälkeen voit jakaa sen sovelluksena työtovereille organisaatiossasi.

Muodosta yhteys [Smartsheet-mallisovellukseen](https://app.powerbi.com/groups/me/getapps/services/pbi-contentpacks.pbiapps-smartsheet) Power BI:lle.

>[!NOTE]
>Power BI -mallisovelluksen yhdistämisessä ja lataamisessa kannattaa käyttää Smartsheet-järjestelmänvalvojan tiliä, sillä se sisältää lisäoikeuksia.

## <a name="how-to-connect"></a>Yhteyden muodostaminen

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. Valitse **Smartsheet** \> **Hanki se nyt**.
4. Valitse **Asennetaanko tämä Power BI -sovellus?** -kohdassa **Asenna**.
4. Valitse **Sovellukset**-ruudussa **Smartsheet**-ruutu.

    ![Power BI:n Smartsheet-sovellus ruutu](media/service-connect-to-smartsheet/power-bi-smartsheet-tile.png)

6. Valitse **Aloita uuden sovelluksesi käyttö** -kohdassa **Yhdistä tiedot**.

    ![Aloita uuden sovelluksesi käyttö](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. Valitse todennusmenetelmäksi **oAuth2 \>Kirjaudu sisään**.
   
   Anna pyydettäessä Smartsheetin tunnistetiedot ja noudata todennusprosessia.
   
   ![Smartsheet-tunnistetiedot](media/service-connect-to-smartsheet/creds.png)
   
   ![Smartsheet-sisäänkirjautuminen](media/service-connect-to-smartsheet/creds2.png)

5. Kun Power BI on tuonut tiedot, Smartsheet-koontinäyttö avautuu.
   
   ![Smartsheet-koontinäyttö](media/service-connect-to-smartsheet/power-bi-smartsheet-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>Sovelluksen muokkaaminen ja jakaminen

Olet asentanut Smartsheet-mallisovelluksen. Tämä tarkoittaa, että olet myös luonut Smartsheet-työtilan. Työtilassa voit muuttaa raporttia ja koontinäyttöä ja sitten jakaa sitä *sovelluksena* työtovereille organisaatiossasi. 

1. Jos haluat nähdä uuden Smartsheet-työtilasi sisällön, valitse siirtymisruudussa **Työtilat** > **Smartsheet**. 

    ![Smartsheet-työtila siirtymisruudussa](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace.png)

    Tämä näkymä on työtilan sisältöluettelo. Oikeassa yläkulmassa on kohta **Päivitä sovellus**. Kun olet valmis jakamaan sovelluksesi työtovereillesi, aloita siitä. 

    ![Smartsheet-sisältöluettelo](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace-content.png)

2. Valitsemalla **Raportit** ja **Tietojoukot** voit tarkastella muita työtilan elementtejä.

    Lue tietoja [sovellusten jakamisesta](../collaborate-share/service-create-distribute-apps.md) työtovereille.

## <a name="whats-included"></a>Paketin sisältö
Smartsheet-mallisovellus Power BI:lle sisältää yleiskatsauksen Smartsheet-tilistäsi kuten työtiloista, raporteista ja työkirjoista, joita sinulla on, kun niitä esimerkiksi muokataan. Järjestelmänvalvojakäyttäjät näkevät myös tietoja omassa järjestelmässään olevista käyttäjistä, kuten parhaat taulukoiden laatijat.  

Voit käyttää myös [Power BI Desktopin](desktop-connect-to-data.md) Smartsheet-liitintä yhteyden muodostamiseen tiliisi yksittäisiin taulukoihin.  

## <a name="next-steps"></a>Seuraavat vaiheet

* [Luo uusia työtiloja Power BI:ssä](../collaborate-share/service-create-the-new-workspaces.md)
* [Asenna ja käytä sovelluksia Power BI:ssä](../consumer/end-user-apps.md)
* [Yhteyden muodostaminen Power BI -sovelluksiin ulkoisille palveluille](service-connect-to-services.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)