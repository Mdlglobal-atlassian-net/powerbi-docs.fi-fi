---
title: Yhteyden muodostaminen Microsoft Azure Consumption Insightsiin Power BI:n avulla
description: Microsoft Azure Consumption Insightsiin for Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 8a8b6d930dcb5ded8c8913ca9e706fe50d16048f
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008208"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Yhteyden muodostaminen Microsoft Azure Consumption Insightsiin Power BI:n avulla
Tutki ja valvo Microsoft Azure Enterprise -kulutustietojasi Power BI:ssä Power BI -sisältöpaketin avulla. Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys Power BI:lle suunniteltuun [Microsoft Azure Consumption Insights -sisältöpakettiin](https://app.powerbi.com/getdata/services/azureconsumption).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Valitse **Microsoft Azure Consumption Insights** \> **Hanki**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Valitse, kuinka monen kuukauden tiedot haluat tuoda, ja anna Azure Enterprise -rekisteröintinumerosi. Lisätietoja [näiden parametrien löytämisestä](#FindingParams) on alla.
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Anna Tiliavaimesi yhteyden muodostamista varten. Rekisteröintisi avain on Azure EA -portaalissa. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Microsoft Azure Consumption Insights -sisältöpaketti sisältää kuukausittaiset raporttitiedot sille kuukausialueelle, jonka olet antanut yhteystyönkulun aikana. Alue on liikkuva aikaväli, joten alueeseen kuuluvat päivämäärät päivittyvät, kun tietojoukko päivittyy.

## <a name="system-requirements"></a>Järjestelmävaatimukset
Sisältöpaketti edellyttää yritysominaisuuksien käyttöoikeuksia Azure-portaalissa. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Power BI -raportointi on käytettävissä EA Directille, kumppaneille ja välillisille asiakkaille, jotka voivat tarkastella laskutustietoja. Lue seuraavat tiedot kunkin arvon etsimisestä, joita yhteyden työnkulku odottaa.

**Kuukausien määrä**

* Tämän on oltava luku välillä 1–36, joka edustaa niiden kuukausien lukumäärää (tästä päivästä lähtien), joiden tiedot haluat tuoda.

**Rekisteröintinumero**

* Tämä on Azure Enterprise -rekisteröintinumerosi, joka löytyy [Azure Enterprise Portalin](https://ea.azure.com/) aloitusnäytöstä kohdasta ”Rekisteröinnin tiedot”.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Käyttöavain**

* Avain löytyy Azure Enterprise Portalista kohdasta ”Lataa käyttö” > ”Ohjelmointirajapinnan käyttöavain”
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Lisäapua**

* Lisäapua Azure Enterprise Power BI -paketin määrittämisestä löytyy kirjautumalla Azure Enterprise Portaliin, jossa voidaan tarkastella ”Ohje”-kohdassa olevaa Ohjelmointirajapinnan ohjetiedostoa, ja lisäohjeita kohdassa Raportit -> Lataa käyttö -> Ohjelmointirajapinnan käyttöavain. 

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

