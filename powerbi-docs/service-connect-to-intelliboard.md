---
title: Yhteyden muodostaminen IntelliBoardiin Power BI:llä
description: IntelliBoard Power BI:lle
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: d73a02e754615263a155d3a7e31e47af4b740fd8
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815354"
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Yhteyden muodostaminen IntelliBoardiin Power BI:llä
IntelliBoard tarjoaa yksinkertaistetun pääsyn oppimisen hallintajärjestelmäsi Moodlen tietoihin raportointipalveluiden avulla. IntelliBoard-sisältöpaketti Power BI:lle tarjoaa lisäanalytiikkaa, mukaan luettuina kursseja, rekisteröityjä käyttäjiä, yleistä suorituskykyä ja LMS:n toimintaa koskevia arvoja.

Muodosta yhteys [IntelliBoard-sisältöpakettiin](https://app.powerbi.com/getdata/services/intelliboard) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.  
   
    ![](media/service-connect-to-intelliboard/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.  
   
    ![](media/service-connect-to-intelliboard/services.png)
3. Valitse **IntelliBoard** ja sitten **Nouda**.  
   
    ![](media/service-connect-to-intelliboard/intelliboard.png)
4. Valitse **OAuth 2** ja sitten **Kirjaudu sisään**. Anna pyydettäessä IntelliBoard-tunnistetietosi.
   
    ![](media/service-connect-to-intelliboard/creds.png)
   
    ![](media/service-connect-to-intelliboard/creds2.png)
5. Kun yhteys on muodostettu, koontinäyttö, raportti ja tietojoukko ladataan automaattisesti. Tämän jälkeen ruudut päivitetään IntelliBoard-tilisi tiedoilla.
   
    ![](media/service-connect-to-intelliboard/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä Q&A-ruudussa](power-bi-q-and-a.md) koontinäytön yläreunassa
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä haluamanasi ajankohtana toiminnolla **Päivitä nyt**

## <a name="whats-included"></a>Paketin sisältö
Sisältöpaketti sisältää tietoja seuraavista taulukoista:  

    - Toimi  
    - Agentit  
    - Todennus  
    - Maat  
    - Kurssien edistyminen  
    - Rekisteröitymiset
    - Kieli  
    - Ympäristö  
    - Summat  
    - Käyttäjien edistyminen    

## <a name="system-requirements"></a>Järjestelmävaatimukset
IntelliBoard-tili, jolla on edellä mainittujen taulukoiden käyttöoikeudet, on edellytys tämän sisältöpaketin alustamiselle.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

