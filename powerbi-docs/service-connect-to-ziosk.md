---
title: Yhteyden muodostaminen Ziosk-kyselyn analysointiin Power BI:lla
description: Ziosk Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 3308abbb3fbc1ceadb78b83d13d69d014de1bff1
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34238545"
---
# <a name="connect-to-ziosk-survey-analytics-with-power-bi"></a>Yhteyden muodostaminen Ziosk-kyselyn analysointiin Power BI:lla
Ziosk Survey Analytics -sisältöpaketti Power BI:lle tarjoaa Ziosk-tabletteja käyttäville ravintoloille ennennäkemättömän pääsyn Zioskin tutkimustietoihin mukaan lukien päiväkohtainen segmentointi, sijainti, työntekijä ja paljon muuta.

Muodosta yhteys Power BI:n [Ziosk Survey Analytics -sisältöpakettiin](https://app.powerbi.com/getdata/services/ziosk-survey-analytics).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.  
   
    ![](media/service-connect-to-ziosk/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.  
   
    ![](media/service-connect-to-ziosk/services.png)
3. Valitse **Ziosk Survey Analytics**, ja valitse sitten **Nouda**.  
   
    ![](media/service-connect-to-ziosk/ziosk.png)
4. Valitse **OAuth 2** ja sitten **Kirjaudu sisään**. Anna pyydettäessä Ziosk-tunnistetietosi.
   
    ![](media/service-connect-to-ziosk/creds.png)
   
    ![](media/service-connect-to-ziosk/creds2.png)
5. Kun yhteys on muodostettu, koontinäyttö, raportti ja tietojoukko ladataan automaattisesti. Tämän jälkeen ruudut päivitetään Ziosk-tilisi tiedoilla.
   
    ![](media/service-connect-to-ziosk/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Sisältöpaketti sisältää tietoja seuraavista taulukoista:  

    - Alkoholiluokka  
    - Alkupalaluokka  
    - CommentKeywords  
    - Date  
    - Daypart  
    - Jälkiruoat-luokka  
    - Vapaamuotoinen  
    - Lapset-luokka  
    - Viestit  
    - Premium-sisältöluokka  
    - Kysymys  
    - Myymälä  
    - Tutkimukset  
    - Arkipäivä  


## <a name="system-requirements"></a>Järjestelmävaatimukset
Ziosk-tili, jolla on edellä mainittujen taulukoiden käyttöoikeudet, on edellytys tämän sisältöpaketin alustamiselle.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

