---
title: Yhteyden muodostaminen IntelliBoardiin Power BI:llä
description: IntelliBoard Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 1eed656b768b7e05b8fc9d97557cb2a43755d336
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721139"
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

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

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
[Mikä on Power BI?](power-bi-overview.md)

[Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

