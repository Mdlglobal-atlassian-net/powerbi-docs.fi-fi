---
title: Yhteyden muodostaminen Alpine Metrics Sales Predictions -sovellukseen Power BI:llä
description: Alpine Metrics Sales Predictions Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 7456a030dd5047642c4de9c7a289fed96fe390f1
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135969"
---
# <a name="connect-to-alpine-metrics-sales-predictions-with-power-bi"></a>Yhteyden muodostaminen Alpine Metrics Sales Predictions -sovellukseen Power BI:llä
Alpine Metrics tarjoaa huippuluokan ennakoivan myyntiprosessin optimoinnin pilvipalvelussa ja pyydettäessä suurille ja pienille myyntiorganisaatioille. Alpine Metrics Sales Predictions -sisältöpaketti Power BI:lle sisältää arvoja, kuten mahdolliset ja ennustetut myynnit ja riskit, ja sen ansiosta saat entistä syvemmän näkemyksen liiketoimintasi tulevaisuudesta. 

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

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
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

[Power BI:n peruskäsitteet](service-basic-concepts.md)

