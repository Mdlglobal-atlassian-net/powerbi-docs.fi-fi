---
title: Yhteyden muodostaminen Ziosk-kyselyn analysointiin Power BI:lla
description: Ziosk Power BI:lle
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
ms.openlocfilehash: 48f4e18a2ad5c5acbc1265ac684857d85b4f5e8a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815854"
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

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md)
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Sisältöpaketti sisältää tietoja seuraavista taulukoista:  

    - Alkoholiluokka  
    - Alkupalaluokka  
    - CommentKeywords  
    - Päivämäärä  
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

