---
title: Lithiumiin yhdistäminen Power BI:n avulla
description: Power BI:n Lithium
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9029d5b6268cacf17fc862a4c0a3d19f440f7de1
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007924"
---
# <a name="connect-to-lithium-with-power-bi"></a>Lithiumiin yhdistäminen Power BI:n avulla
Lithium rakentaa luotettuja suhteita maailman parhaiden tuotemerkkien ja niiden asiakkaiden välille auttaen ihmisiä saamaan vastauksia ja jakamaan kokemuksiaan. Yhdistämällä Lithium-sisältöpaketin Power BI:hin voit mitata tärkeitä tietoja verkkoyhteisöstäsi auttaen lisäämään myyntiä, pienentämään palvelukustannuksia ja lisäämään uskollisuutta. 

Yhdistä Power BI:n [Lithium-sisältöpakettiin](https://app.powerbi.com/getdata/services/lithium).

>[!NOTE]
>Power BI -sisältöpaketti käyttää Lithium-ohjelmointirajapintaa. Jos ohjelmointirajapintaan lähetetään liian paljon kutsuja, Lithiumin käytöstä saatetaan veloittaa lisämaksuja. Varmista asia Lithium-järjestelmänvalvojalta.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. Valitse **Lithium** \> **Nouda**.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Anna Lithium-yhteisön URL-osoite. Sen muoto on *https://community.yoursite.com*.
   
   ![](media/service-connect-to-lithium/params.png)
5. Anna pyydettäessä Lithium-tunnistetiedot. Valitse todennusmenetelmäksi **oAuth 2**, napsauta **Kirjaudu sisään** ja noudata Lithium-todentamisen vaiheita.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. Kun kirjautuminen on valmis, tuonti alkaa. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements"></a>Järjestelmävaatimukset
Lithium-sisältöpaketti edellyttää Lithium-yhteisön versiota 15.9 tai sitä uudempaa. Varmista asia Lithium-järjestelmänvalvojalta.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Power BI:n peruskäsitteet](consumer/end-user-basic-concepts.md)

