---
title: Zendeskiin yhdistäminen Power BI:n avulla
description: Zendesk Power BI:lle
author: paulinbar
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 17d65296246100180f722dfccacb31ee9ebeade7
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83327158"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Zendeskiin yhdistäminen Power BI:n avulla

Tässä artikkelissa kerrotaan tietojen hakemisesta Zendesk-tililtäsi Power BI -mallisovelluksella. Zendesk-sovellus tarjoaa Power BI -koontinäytön ja sarjan Power BI -raportteja, jotka tarjoavat merkityksellisiä tietoja lippujesi määrästä ja agentin suorituskyvystä. Tiedot päivitetään automaattisesti kerran päivässä. 

Kun olet asentanut mallisovelluksen, voit mukauttaa koontinäyttöä ja raporttia niin, että sinulle tärkeimmät tiedot korostetaan. Sen jälkeen voit jakaa sen sovelluksena työtovereille organisaatiossasi.

Muodosta yhteys [Zendesk-mallisovellukseen](https://app.powerbi.com/getdata/services/zendesk) tai lue lisää Power Bi:n [Zendesk-integroinnista](https://powerbi.microsoft.com/integrations/zendesk).

Kun olet asentanut mallisovelluksen, voit muuttaa koontinäyttöä ja raporttia. Sen jälkeen voit jakaa sen sovelluksena työtovereille organisaatiossasi.

>[!NOTE]
>Yhteyden muodostamiseen tarvitaan Zendesk-järjestelmänvalvojan tili. Lisätietoja [vaatimuksista](#system-requirements) on alla.

## <a name="how-to-connect"></a>Yhteyden muodostaminen

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. Valitse **Zendesk** \> **Hanki se nyt**.
4. Valitse **Asennetaanko tämä Power BI -sovellus?** -kohdassa **Asenna**.
4. Valitse **Sovellukset**-ruudussa **Zendesk**-ruutu.

    ![Power BI Zendesk -sovellusruutu](media/service-connect-to-zendesk/power-bi-zendesk-tile.png)

6. Valitse **Aloita uuden sovelluksesi käyttö** -kohdassa **Yhdistä tiedot**.

    ![Aloita uuden sovelluksesi käyttö](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. Anna tiliisi liitetty URL-osoite. URL-osoite on muodossa **https://company.zendesk.com** . Lisätietoja [näiden parametrien löytämisestä](#finding-parameters) on alla.
   
   ![Muodosta yhteys Zendeskiin](media/service-connect-to-zendesk/pbi_zendeskconnect.png)

5. Anna pyydettäessä Zendesk-tunnistetiedot.  Valitse todennusmenetelmäksi **oAuth 2** ja valitse **Kirjaudu sisään**. Noudata Zendesk-todennuksen työnkulkua. (Jos olet jo kirjautunut Zendeskiin selaimessa, tunnistetietoja ei välttämättä pyydetä.)
   
   > [!NOTE]
   > Tämä mallisovellus edellyttää, että muodostat yhteyden Zendesk-järjestelmänvalvojan tililtä. 
   > 
   
   ![oAuth2-kirjautumisen käyttäminen](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. Napsauta **Salli** salliaksesi Power BI:lle Zendesk-tilisi käyttöoikeudet.
   
   ![Napsauta Salli](media/service-connect-to-zendesk/zendesk2.jpg)
7. Aloita tuontiprosessi valitsemalla **Yhdistä**. 
8. Kun Power BI on tuonut tiedot, Zendesk-sovelluksen sisältöluettelo tulee näkyviin: uusi koontinäyttö, raportti ja tietojoukko.
9. Aloita etsintäprosessi valitsemalla koontinäyttö.

    ![Zendesk-koontinäyttö](media/service-connect-to-zendesk/power-bi-zendesk-dashboard.png)
   
## <a name="modify-and-distribute-your-app"></a>Sovelluksen muokkaaminen ja jakaminen

Olet asentanut Zendesk-mallisovelluksen. Tämä tarkoittaa, että olet myös luonut Zendesk-työtilan. Työtilassa voit muuttaa raporttia ja koontinäyttöä ja sitten jakaa sitä *sovelluksena* työtovereille organisaatiossasi. 

1. Jos haluat nähdä uuden Zendesk-työtilasi sisällön, valitse siirtymisruudussa **Työtilat** > **Zendesk**. 

    ![Zendesk-työtila siirtymisruudussa](media/service-connect-to-zendesk/power-bi-zendesk-workspace-left-nav.png)

    Tämä näkymä on työtilan sisältöluettelo. Oikeassa yläkulmassa on kohta **Päivitä sovellus**. Kun olet valmis jakamaan sovelluksesi työtovereillesi, aloita siitä. 

    ![Zendesk-sisältöluettelo](media/service-connect-to-zendesk/power-bi-zendesk-content-list.png)

2. Valitsemalla **Raportit** ja **Tietojoukot** voit tarkastella muita työtilan elementtejä.

    Lue tietoja [sovellusten jakamisesta](../collaborate-share/service-create-distribute-apps.md) työtovereille.

## <a name="system-requirements"></a>Järjestelmävaatimukset
Zendesk-mallisovellus edellyttää Zendesk- järjestelmänvalvojan tiliä. Jos olet agentti tai loppukäyttäjä ja olet kiinnostunut Zendesk-tietojen tarkastelemisesta, lisää ehdotus ja tarkista Zendesk-yhdistin [Power BI Desktopista](desktop-connect-to-data.md).

## <a name="finding-parameters"></a>Parametrien löytäminen
Zendeskin URL-osoite on sama kuin URL-osoite, jota käytät kirjautuessasi Zendesk-tilillesi. Jos et ole varma Zendesk URL-osoitteesta, voit käyttää Zendesk [kirjautumisapua](https://www.zendesk.com/login/).

## <a name="troubleshooting"></a>Vianmääritys
Jos sinulla on ongelmia yhteyden kanssa, tarkista Zendeskin URL-osoite ja varmista, että käytät Zendesk-järjestelmänvalvojatiliä.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Luo uusia työtiloja Power BI:ssä](../collaborate-share/service-create-the-new-workspaces.md)
* [Asenna ja käytä sovelluksia Power BI:ssä](../consumer/end-user-apps.md)
* [Yhteyden muodostaminen Power BI -sovelluksiin ulkoisille palveluille](service-connect-to-services.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
