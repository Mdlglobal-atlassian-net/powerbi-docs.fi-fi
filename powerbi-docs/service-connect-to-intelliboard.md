---
title: Yhteyden muodostaminen IntelliBoardiin Power BI:llä
description: IntelliBoard Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 06fc561d3fbe07cbf553be63c7b19de3ab11992e
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/30/2019
ms.locfileid: "73060955"
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Yhteyden muodostaminen IntelliBoardiin Power BI:llä
IntelliBoard tarjoaa yksinkertaistetun pääsyn oppimisen hallintajärjestelmäsi Moodlen tietoihin raportointipalveluiden avulla. IntelliBoard-sisältöpaketti Power BI:lle tarjoaa lisäanalytiikkaa, mukaan luettuina kursseja, rekisteröityjä käyttäjiä, yleistä suorituskykyä ja LMS:n toimintaa koskevia arvoja.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

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
[Mikä on Power BI?](fundamentals/power-bi-overview.md)

[Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

