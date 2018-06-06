---
title: Yhteyden muodostaminen Azure-hakuun Power BI:n avulla
description: Azure-hakuun Power BI:lle
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
ms.openlocfilehash: d868c50a69381c1ef95a8b3a69590223eb066e90
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815254"
---
# <a name="connect-to-azure-search-with-power-bi"></a>Yhteyden muodostaminen Azure-hakuun Power BI:n avulla
Azure Search-hakuliikenteen analysoinnin avulla voit valvoa ja ymmärtää liikennettä Azure hakupalvelussa. Azure Search sisältöpaketti Power BI:lle tarjoaa yksityiskohtaisia tietoja haun tiedoista kuten Haku ja Indeksointi, Palvelutilastot ka Viive viimeisten 30 päivän ajalta. Lisätietoja löytyy [Azure-blogikirjoituksesta](https://azure.microsoft.com/en-us/blog/analyzing-your-azure-search-traffic/).

Muodosta yhteys [Azure Search -sisältöpakettiin](https://app.powerbi.com/getdata/services/azure-search) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-azure-search/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-azure-search/pbi_getservices.png) 
3. Valitse **Azure Search** \> **Nouda**.
   
   ![](media/service-connect-to-azure-search/azuresearch.png)
4. Anna nimi taulukon tallennustilille, jonne Azure Search -analyysi tallennetaan.
   
   ![](media/service-connect-to-azure-search/params.png)
5. Valitse **Avain** todennusmekanismiksi ja anna tilin tallennusavain. Valitse **Kirjaudu sisään** ja aloita lataaminen.
   
   ![](media/service-connect-to-azure-search/creds.png)
6. Kun lataus on valmis, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
    ![](media/service-connect-to-azure-search/dashboard2.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md)
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements"></a>Järjestelmävaatimukset
Azure Search -sisältöpaketti edellyttää Azure Search -liikenteen analyysin käyttöön ottoa tilillä.

## <a name="troubleshooting"></a>Vianmääritys
Varmista, että tallennustilin nimi on oikein annettu ja että käytössä ovat täydet oikeudet. Tallennustilin nimen tulee vastata Azure Search -liikenteen analyysiin määritettyä tiliä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

