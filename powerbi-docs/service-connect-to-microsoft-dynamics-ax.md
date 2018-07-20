---
title: Yhteyden muodostaminen Microsoft Dynamics AX -sisältöpakettiin Power BI:n avulla
description: Microsoft Dynamics AX -sisältöpaketti Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 2e84d52d9e26b23380b9fbc12fdaa4086a2ec7ed
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34239904"
---
# <a name="connect-to-microsoft-dynamics-ax-content-pack-with-power-bi"></a>Yhteyden muodostaminen Microsoft Dynamics AX -sisältöpakettiin Power BI:n avulla
Microsoft Dynamics AX sisältää kolme Power BI -sisältöpakettia, jotka on suunnattu eri yrityskäyttäjille. Erityisesti talousjohtajille suunniteltu Taloudellinen menestys -sisältöpaketti tarjoaa pääsyn organisaatiosi taloudellista suorituskykyä koskeviin merkityksellisiin tietoihin. Vähittäismyyntikanavan menestys -sisältöpaketti on suunnattu kanavajohtajille, ja se keskittyy myynnin suorituskykyyn trendien ennustamiseksi ja merkityksellisten tietojen tunnistamiseksi hyödyntämällä suoraan vähittäismyyntiä ja kauppaa koskevia tietoja. Kustannustenhallinta on suunniteltu operatiivisille johtajille ja talousjohtajille, ja se tarjoaa tietoja toiminnan suorituskyvystä.

Muodosta yhteys Microsoft Dynamics AX:n [Vähittäismyyntikanavan menestys](https://app.powerbi.com/getdata/services/dynamics-ax-retail-channel-performance)-, [Taloudellinen menestys](https://app.powerbi.com/getdata/services/dynamics-ax-financial-performance)- tai [Kustannustenhallinta](https://app.powerbi.com/getdata/services/dynamics-ax-cost-management) -sisältöpakettiin Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/services.png)
3. Valitse jokin Dynamics AX -sisältöpaketeista ja valitse **Nouda**.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/mdax.png)
4. Määritä Dynamics AX 7 -ympäristön URL-osoite. Lisätietoja [näiden parametrien löytämisestä](#FindingParams) on alla.
   
   ![](media/service-connect-to-microsoft-dynamics-ax/params.png)
5. Valitse **todennusmenetelmäksi** **oAuth2** \> **Kirjaudu sisään**. Kirjoita Dynamics AX -tunnistetietosi pyydettäessä.
   
    ![](media/service-connect-to-microsoft-dynamics-ax/creds.png)
   
    ![](media/service-connect-to-microsoft-dynamics-ax/creds2.png)
6. Hyväksymisen jälkeen tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
     ![](media/service-connect-to-microsoft-dynamics-ax/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajoitettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

## <a name="whats-included"></a>Paketin sisältö
Sisältöpaketti käyttää Dynamics AX 7 OData -syötettä vähittäismyyntikanavan menestykseen, taloudelliseen menestykseen ja kustannustenhallintaan liittyvien tietojen tuomiseen.

## <a name="system-requirements"></a>Järjestelmävaatimukset
Tämä sisältöpaketti edellyttää Dynamics AX 7 -ympäristön URL-osoitetta ja käyttäjällä on oltava OData-syötteen käyttöoikeus.

## <a name="finding-parameters"></a>Parametrien löytäminen
<a name="FindingParams"></a>

Dynamics AX 7 -ympäristön URL-osoite näkyy selaimessa, kun käyttäjä kirjautuu sisään. Kopioi vain Dynamics AX -pääympäristön URL-osoite Power BI -valintaikkunaan.

## <a name="troubleshooting"></a>Vianmääritys
Tietojen lataaminen voi kestää jonkin aikaa esiintymän koosta riippuen. Jos näet Power BI:ssä tyhjiä raportteja, vahvista, että sinulla raporttien edellyttämien OData-taulukoiden käyttöoikeus.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

