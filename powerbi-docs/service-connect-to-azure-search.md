---
title: Yhteyden muodostaminen Azure-hakuun Power BI:n avulla
description: Azure-hakuun Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: c6794fd08255dc3d63381549e7ee068631d49697
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008944"
---
# <a name="connect-to-azure-search-with-power-bi"></a>Yhteyden muodostaminen Azure-hakuun Power BI:n avulla
Azure Search-hakuliikenteen analysoinnin avulla voit valvoa ja ymmärtää liikennettä Azure hakupalvelussa. Azure Search sisältöpaketti Power BI:lle tarjoaa yksityiskohtaisia tietoja haun tiedoista kuten Haku ja Indeksointi, Palvelutilastot ka Viive viimeisten 30 päivän ajalta. Lisätietoja löytyy [Azure-blogikirjoituksesta](https://azure.microsoft.com/blog/analyzing-your-azure-search-traffic/).

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

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements"></a>Järjestelmävaatimukset
Azure Search -sisältöpaketti edellyttää Azure Search -liikenteen analyysin käyttöön ottoa tilillä.

## <a name="troubleshooting"></a>Vianmääritys
Varmista, että tallennustilin nimi on oikein annettu ja että käytössä ovat täydet oikeudet. Tallennustilin nimen tulee vastata Azure Search -liikenteen analyysiin määritettyä tiliä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Power BI:n peruskäsitteet](consumer/end-user-basic-concepts.md)

