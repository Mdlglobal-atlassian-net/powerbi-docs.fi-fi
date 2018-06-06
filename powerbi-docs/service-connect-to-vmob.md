---
title: VMobiin yhdistäminen Power BI:n avulla
description: VMob Power BI:lle.
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
ms.openlocfilehash: 89d1a4cecb7c62dffe71524353bcd48957245594
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815244"
---
# <a name="connect-to-vmob-with-power-bi"></a>VMobiin yhdistäminen Power BI:n avulla
VMob-tietojen seuranta ja analysointi on helppoa Power BI-ja VMob-sisältöpaketin avulla. Power BI noutaa seuraavat tiedot: käyttäjätilastot koko ajalta ja viimeisten 30 päivältä, vähittäismyynnin suorituskykyilmaisimet viimeisten 30 päivän ajalta ja kampanjan tuottavuus viimeisten 30 päivän ajalta.

Muodosta yhteys [VMob-sisältöpakettiin](https://app.powerbi.com/getdata/services/vmob) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
    ![](media/service-connect-to-vmob/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-vmob/services.png)
3. Valitse **VMob** \> **Nouda**.
   
   ![](media/service-connect-to-vmob/vmob.png)
4. Anna pyydettäessä VMob URL-osoite ja valitse Seuraava-painike. Tämän URL-osoitteen antaa VMob erikseen.
   
    ![](media/service-connect-to-vmob/params.png)
5. Valitse **Basic** todentamismenetelmäksi avattavasta valikosta, kirjoita VMob-käyttäjänimesi ja salasanasi ja valitse **Kirjaudu sisään**.
   
    ![](media/service-connect-to-vmob/creds.png)
6. Tuontiprosessin alkaa automaattisesti, ja Power BI noutaa VMob-tiedot valmiin koontinäytön ja raportin luomiseksi.
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md)
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

