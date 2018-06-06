---
title: Lithiumiin yhdistäminen Power BI:n avulla
description: Power BI:n Lithium
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
ms.openlocfilehash: 501395503ef3c4b3bde8e6d7f0ae732af5a4cc6a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815344"
---
# <a name="connect-to-lithium-with-power-bi"></a>Lithiumiin yhdistäminen Power BI:n avulla
Lithium rakentaa luotettuja suhteita maailman parhaiden tuotemerkkien ja niiden asiakkaiden välille auttaen ihmisiä saamaan vastauksia ja jakamaan kokemuksiaan. Yhdistämällä Lithium-sisältöpaketin Power BI:hin voit mitata tärkeitä tietoja verkkoyhteisöstäsi auttaen lisäämään myyntiä, pienentämään palvelukustannuksia ja lisäämään uskollisuutta. 

Yhdistä Power BI:n [Lithium-sisältöpakettiin](https://app.powerbi.com/getdata/services/lithium).

>[!NOTE]
>Power BI -sisältöpaketti käyttää Lithium-ohjelmointirajapintaa. Jos ohjelmointirajapintaan lähetetään liian paljon kutsuja, Lithiumin käytöstä saatetaan veloittaa lisämaksuja. Varmista asia Lithium-järjestelmänvalvojalta.

## <a name="how-to-connect"></a>Yhdistäminen
1. Valitse vasemman siirtymisruudun alareunassa **Hae tiedot**.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudusta **Nouda**.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. Valitse **Lithium** \> **Nouda**.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Anna Lithium-yhteisön URL-osoite. Osoite on muodossa *https://community.yoursite.com*.
   
   ![](media/service-connect-to-lithium/params.png)
5. Anna pyydettäessä Lithium-tunnistetiedot. Valitse todennusmenetelmäksi **oAuth 2**, napsauta **Kirjaudu sisään** ja noudata Lithium-todentamisen vaiheita.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. Kun kirjautuminen on valmis, tuonti alkaa. Kun tuonti on valmis, uusi koontinäyttö, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla koontinäytön.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

## <a name="system-requirements"></a>Järjestelmävaatimukset
Lithium-sisältöpaketti edellyttää Lithium-yhteisön versiota 15.9 tai sitä uudempaa. Varmista asia Lithium-järjestelmänvalvojalta.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

