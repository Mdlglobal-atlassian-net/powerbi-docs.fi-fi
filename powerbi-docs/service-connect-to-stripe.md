---
title: Yhteyden muodostaminen Stripeen Power BI:llä
description: Stripe Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 533a8ae7f0030c70ed5212c890215a2b43d8e870
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34246593"
---
# <a name="connect-to-stripe-with-power-bi"></a>Yhteyden muodostaminen Stripeen Power BI:llä
Visualisoi ja tutki Stripe-tietoja Power BI:ssä Power BI -sisältöpaketin avulla. Power BI Stripe -sisältöpaketti hakee tietoja asiakkaista, maksuista, tapahtumista ja laskuista. Tiedot sisältävät uusimmat kymmenen tuhatta tapahtumaa ja viisi tuhatta maksua viimeisten 30 päivän ajalta. Sisältö päivitetään automaattisesti kerran päivässä asettamasi aikataulun mukaisesti. 

Muodosta yhteys [Stripe-sisältöpakettiin](https://app.powerbi.com/getdata/services/stripe) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa Nouda tiedot.  
   
    ![](media/service-connect-to-stripe/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.  
   
    ![](media/service-connect-to-stripe/services.png)  
3. Valitse **Stripe** &gt; **Nouda**.  
   
    ![](media/service-connect-to-stripe/stripe.png)  
4. Anna oma Stripe [Ohjelmointirajapinta-avaimesi](https://dashboard.stripe.com/account/apikeys) yhteyden luomiseksi.  
   
    ![](media/service-connect-to-stripe/creds.png)
5. Tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa, joka on merkitty tähdellä. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
    ![](media/service-connect-to-stripe/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:hin](service-get-data.md)
