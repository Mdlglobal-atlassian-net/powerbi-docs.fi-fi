---
title: Yhteyden muodostaminen Alpine Metrics Sales Predictions -sovellukseen Power BI:llä
description: Alpine Metrics Sales Predictions Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 497f3e76275f957599e80eadfd92b9073fca2ebb
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/30/2019
ms.locfileid: "70185561"
---
# <a name="connect-to-alpine-metrics-sales-predictions-with-power-bi"></a>Yhteyden muodostaminen Alpine Metrics Sales Predictions -sovellukseen Power BI:llä
Alpine Metrics tarjoaa huippuluokan ennakoivan myyntiprosessin optimoinnin pilvipalvelussa ja pyydettäessä suurille ja pienille myyntiorganisaatioille. Alpine Metrics Sales Predictions -sisältöpaketti Power BI:lle sisältää arvoja, kuten mahdolliset ja ennustetut myynnit ja riskit, ja sen ansiosta saat entistä syvemmän näkemyksen liiketoimintasi tulevaisuudesta. 

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

Muodosta yhteys [Alpine Metrics Sales Predictions -sisältöpakettiin](https://app.powerbi.com/getdata/services/alpine-metrics) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa Nouda tiedot.  
   
    ![](media/service-connect-to-alpine-metrics/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.  
   
    ![](media/service-connect-to-alpine-metrics/services.png)
3. Valitse **AlpineMetrics Sales Predictions** ja sitten **Nouda**.  
   
    ![](media/service-connect-to-alpine-metrics/alpine.png)
4. Valitse **OAuth 2** ja sitten **Kirjaudu sisään**. Anna pyydettäessä AlpineMetrics-tunnistetietosi.
   
    ![](media/service-connect-to-alpine-metrics/creds.png)
   
    ![](media/service-connect-to-alpine-metrics/creds2.png)
5. Kun yhteys on muodostettu, koontinäyttö, raportti ja tietojoukko ladataan automaattisesti. Tämän jälkeen ruudut päivitetään tilisi tiedoilla.
   
    ![](media/service-connect-to-alpine-metrics/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Sisältöpaketti sisältää tietoja seuraavista taulukoista:  

    - Tili    
    - Yritys    
    - Maa    
    - Ala    
    - Mahdollisuus  
    - Henkilö  
    - Ennuste    
    - Ennustehistoria    
    - Tuote  
    - Alue    

## <a name="system-requirements"></a>Järjestelmävaatimukset
Alpine Metrics -tili, jolla on edellä mainittujen taulukoiden käyttöoikeudet, on edellytys tämän sisältöpaketin alustamiselle.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

