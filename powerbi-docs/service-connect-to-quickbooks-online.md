---
title: Yhteyden muodostaminen QuickBooks Onlineen Power BI:llä
description: Power BI:n QuickBooks Online
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
ms.openlocfilehash: 770daa9965f44d655fb60b8b723f83e260daccb6
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815639"
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Yhteyden muodostaminen QuickBooks Onlineen Power BI:llä
Kun muodostat yhteyden QuickBooks Onlinen tietoihin Power BI:stä, saat heti Power BI:n koontinäytön ja Power BI:n raportit, jotka antavat merkityksellisiä tietoja muun muassa yrityksesi kassavirrasta, kannattavuudesta ja asiakkaista. Voit käyttää koontinäyttöä ja raportteja sellaisinaan tai mukauttaa niitä, jotta niissä korostuvat itseäsi eniten kiinnostavat tiedot. Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys [QuickBooks Online -sisältöpakettiin](https://dxt.powerbi.com/getdata/services/quickbooks-online) Power BI:tä varten.

>[!NOTE]
>Jos haluat tuoda QuickBooks Online -tietosi Power BI:hin, sinun on oltava järjestelmänvalvoja QuickBooks Online -tilissäsi ja kirjauduttava sisään järjestelmänvalvojan tilin tunnistetiedoilla.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunasta **Nouda tiedot**.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-quickbooks-online/pbi_getservices.png) 
3. Valitse **QuickBooks Online** ja valitse sitten **Nouda**.
   
   ![](media/service-connect-to-quickbooks-online/qbo.png)
4. Valitse todennusmenetelmäksi **oAuth2** ja valitse sitten **Kirjaudu sisään**. 
5. Anna pyydettäessä QuickBooks Onlinen tunnistetietosi ja noudata QuickBooks Onlinen todennusprosessia. Jos olet jo kirjautunut QuickBooks Onlineen selaimessa, tunnistetietoja ei välttämättä pyydetä.
   >[!NOTE]
   >Tarvitset QuickBooks Online -tilisi järjestelmänvalvojan tunnistetiedot.
6. Valitse seuraavassa näytössä yritys, jonka haluat yhdistää Power BI:hin.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)
7. Aloita tuontiprosessi valitsemalla seuraavassa ruudussa **Valtuuta**. Tämä voi kestää muutaman minuutin yrityksen tietojen koon mukaan. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
   Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Uudet kohteet on merkitty keltaisella tähdellä \*.
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_leftnavnew.png)
8. Valitse QuickBooks Onlinen koontinäyttö. Tämä on koontinäyttö, jonka Power BI on luonut automaattisesti tuotujen tietojen näyttämistä varten. Voit muokata tätä koontinäyttöä, jotta näet tiedot juuri haluamallasi tavalla. 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_dash.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

## <a name="troubleshooting"></a>Vianmääritys
**Oho! Havaittiin virhe.**

Jos saat tämän sanoman sen jälkeen kun valitsit **Valtuuta**:

Oho! Havaittiin virhe. Sulje tämä ikkuna ja yritä uudelleen.

Tämä sovellus on jo tilattu toiselle yrityksen käyttäjälle. Voit tehdä muutoksia tähän tilaukseen ottamalla yhteyttä osoitteeseen [järjestelmänvalvojan sähköpostiosoite].

![](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

... Tämä tarkoittaa, että yrityksesi toinen järjestelmänvalvoja on jo yhdistänyt yrityksen tiedot Power BI:hin. Pyydä, että kyseinen järjestelmänvalvoja jakaa koontinäytön kanssasi. Tällä hetkellä vain yksi järjestelmänvalvojakäyttäjä voi yhdistää tietyn QuickBooks Online -yrityksen tietojoukon Power BI:hin. Kun Power BI on luonut koontinäytön, järjestelmänvalvoja voi jakaa sen useille työtovereilleen samoissa Power BI -vuokraajissa.

**"Tätä sovellusta ei ole määritetty sallimaan yhteyksiä maastasi"**

Power BI tukee tällä hetkellä vain QuickBooks Onlinen Yhdysvaltojen versioita. 

![](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)
