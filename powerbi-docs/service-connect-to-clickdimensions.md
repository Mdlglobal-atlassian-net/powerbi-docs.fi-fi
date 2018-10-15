---
title: Yhteyden muodostaminen ClickDimensionsiin Power BI:n avulla
description: ClickDimensions Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 709dd5d1b5203e9c5bb790d69cb0537c03a17916
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/21/2018
ms.locfileid: "46543338"
---
# <a name="connect-to-clickdimensions-with-power-bi"></a>Yhteyden muodostaminen ClickDimensionsiin Power BI:n avulla
ClickDimensions-sisältöpaketti Power BI:lle antaa käyttäjien hyödyntää ClickDimensionsin markkinointidataa Power BI:ssa, jolloin johtotiimit saavat merkityksellistä tietoa myynti- ja markkinointiponnistelujen tehokkuudesta. Visualisoi ja analysoi sähköpostiviestintää, verkkokäyntejä ja lähetettyjä lomakkeita Power BI -koontinäyttöjen ja raporttien avulla.

Muodosta yhteys [Power BI:n ClickDimensions-sisältöpakettiin.](https://app.powerbi.com/getdata/services/click-dimensions)

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-clickdimensions/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-clickdimensions/services.png)
3. Valitse **ClickDimensions** \> **Nouda**.  
   
   ![](media/service-connect-to-clickdimensions/clickdimensions.png)
4. Anna palvelinkeskuksen sijaintitiedot (Yhdysvallat, EU tai AU) ja valitse **Seuraava**.
   
   ![](media/service-connect-to-clickdimensions/params.png)
5. Valitse **todennusmenetelmäksi** **Basic** \> **Kirjaudu sisään**. Kirjoita ClickDimensions-tunnistetietosi pyydettäessä. Lisätietoja [näiden parametrien löytämisestä](#FindingParams) on alla
   
    ![](media/service-connect-to-clickdimensions/creds.png)
6. Hyväksymisen jälkeen tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
     ![](media/service-connect-to-clickdimensions/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements"></a>Järjestelmävaatimukset
Yhteyden muodostamiseksi Power BI -sisältöpakettiin pitää antaa palvelinkeskus, joka vastaa tiliä ja kirjautumista ClickDimensions-tilille. Jos et ole varma, mikä palvelinkeskus pitää antaa, tarkista asia järjestelmänvalvojalta.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Tilin avain löytyy CRM asetuksista \> ClickDimensions -asetuksista. Kopioi tiliavaimesi ClickDimensions-asetuksista ja liitä se Käyttäjän nimi -kenttään.  

![](media/service-connect-to-clickdimensions/crm.png)  

Kopioi Power BI -tunnus ClickDimensions-asetuksista ja liitä se Salasana -kenttään. Power BI -tunnus löytyy CRM asetuksista \> ClickDimensions -asetuksista.  

![](media/service-connect-to-clickdimensions/crm2.png)  

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

