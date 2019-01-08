---
title: Zendeskiin yhdistäminen Power BI:n avulla
description: Zendesk Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 72b934357ec4208fa07266143b08af861659e465
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008323"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Zendeskiin yhdistäminen Power BI:n avulla
Zendesk-sisältöpaketti tarjoaa Power BI -koontinäytön ja sarjan Power BI -raportteja, jotka tarjoavat merkityksellisiä tietoja lippujesi määrästä ja agentin suorituskyvystä. Voit käyttää annettua raporttinäkymää ja raportteja tai mukauttaa niitä, jotta niissä korostuvat itseäsi eniten kiinnostavat tiedot.  Tiedot päivitetään automaattisesti kerran päivässä. 

Muodosta yhteys [Zendesk-sisältöpakettiin](https://app.powerbi.com/getdata/services/zendesk) tai lue lisää Power Bi:n [Zendesk-integroinnista](https://powerbi.microsoft.com/integrations/zendesk).

>[!NOTE]
>Yhteyden muodostaminen edellyttää Zendesk-järjestelmänvalvojan tiliä. Lisätietoja [vaatimuksista](#Requirements) on alla.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-zendesk/pbi_getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-zendesk/pbi_getservices.png) 
3. Valitse **Zendesk** \> **Nouda.**
   
   ![](media/service-connect-to-zendesk/zendesk.png)
4. Anna tiliisi liitetty URL-osoite. Tämä on muodossa **https://company.zendesk.com**. Tiedot [parametrien hakuun](#FindingParams) löytyvät alta.
   
   ![](media/service-connect-to-zendesk/pbi_zendeskconnect.png)
5. Anna pyydettäessä Zendesk-tunnistetiedot.  Valitse todennusmenetelmäksi **oAuth 2** ja valitse **Kirjaudu sisään**. Noudata Zendesk-todennuksen työnkulkua. Jos olet jo kirjautunut Zendeskiin selaimessa, tunnistetietoja ei välttämättä pyydetä.
   
   > [!NOTE]
   > Tämä sisältöpaketti edellyttää, että muodostat yhteyden Zendesk-järjestelmänvalvojan tililtä. 
   > 
   > 
   
   ![](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. Napsauta **Salli** salliaksesi Power BI:lle Zendesk-tilisi käyttöoikeudet.
   
   ![](media/service-connect-to-zendesk/zendesk2.jpg)
7. Aloita tuontiprosessi valitsemalla **Yhdistä**. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Uudet kohteet on merkitty keltaisella tähdellä \*.
   
   ![](media/service-connect-to-zendesk/pbi_zendeskdash.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Power BI -sisältöpaketti sisältää tietoja seuraavista:  

* Käyttäjät (loppukäyttäjät ja agentit)  
* Organisaatiot  
* Ryhmät  
* Liput  

On myös olemassa joukko mittareita, jotka on laskettu, kuten keskimääräinen odotusaika ja ratkaissut tukipyynnöt viimeisten 7 päivän aikana. Täydellinen luettelo sisältyy sisältöpakettiin.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Järjestelmävaatimukset
Zendesk-sisältöpaketti edellyttää Zendesk- järjestelmänvalvojan tiliä. Jos olet agentti tai loppukäyttäjä ja olet kiinnostunut Zendesk-tietojen tarkastelemisesta, lisää ehdotus ja tarkista Zendesk-yhdistin [Power BI Desktopista](desktop-connect-to-data.md).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Zendeskin URL-osoite on sama kuin URL-osoite, jota käytät kirjautuessasi Zendesk-tilillesi. Jos et ole varma Zendesk URL-osoitteesta, voit käyttää Zendesk [kirjautumisapua](https://www.zendesk.com/login/).

## <a name="troubleshooting"></a>Vianmääritys
Jos sinulla on ongelmia yhteyden kanssa, tarkista Zendeskin URL-osoite ja varmista, että käytät Zendesk-järjestelmänvalvojatiliä.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Mikä on Power BI?](power-bi-overview.md)
* [Nouda tiedot](service-get-data.md)

