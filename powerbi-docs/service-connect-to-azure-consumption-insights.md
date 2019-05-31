---
title: Yhteyden muodostaminen Microsoft Azure Consumption Insightsiin Power BI:n avulla
description: Microsoft Azure Consumption Insightsiin for Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 089f8c31a0b1eb11f6871268f2f848949be95d9b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222138"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Yhteyden muodostaminen Microsoft Azure Consumption Insightsiin Power BI:n avulla
Tutki ja valvo Microsoft Azure Enterprise -kulutustietojasi Power BI:ssä Power BI -sisältöpaketin avulla. Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys Power BI:lle suunniteltuun [Microsoft Azure Consumption Insights -sisältöpakettiin](https://app.powerbi.com/getdata/services/azureconsumption).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Valitse **Microsoft Azure Consumption Insights** \> **hanki se nyt**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Valitse, kuinka monen kuukauden tiedot haluat tuoda, ja anna Azure Enterprise -rekisteröintinumerosi. Lisätietoja [näiden parametrien löytämisestä](#FindingParams) on alla.
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Anna Tiliavaimesi yhteyden muodostamista varten. Rekisteröinnin avain löytyy Azure EA-portaalissa. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Tuontiprosessi alkaa automaattisesti. Kun lataus on valmis, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Kun tietojoukko on ajoitettu päivittymään päivittäin, voit muuttaa päivitysaikataulua tai kokeilla päivittämistä haluamanasi **Päivitä nyt**

## <a name="whats-included"></a>Paketin sisältö
Microsoft Azure Consumption Insights-sisältöpaketti sisältää kuukausittaiset raporttitiedot sille annettu muodostettaessa kuukauden alueen. Alue on liikkuva aikaväli, joten ajanjaksoon sisältyvät päivämäärät päivittyvät sitä mukaa kuin tietojoukko päivittyy.

## <a name="system-requirements"></a>Järjestelmävaatimukset
Sisältöpaketti edellyttää pääsyä Azure-portaalin yritysominaisuuksiin. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Power BI-raportointi on käytettävissä EA Directille, kumppaneille ja Välillisille asiakkaille, jotka voivat tarkastella laskutustietoja. Lue lisätietoja siitä, miten kunkin arvon yhteyden työnkulku odottaa.

**Kuukausien määrä**

* Kuukausien numerot (1 – 36) tästä päivästä haluat tuoda tietoja.

**Rekisteröintinumero**

* Sovelluksesi Azure Enterprise-rekisteröintinumerosi, joka on [Azure Enterprise Portalista](https://ea.azure.com/) aloitusnäyttöön kohdassa **rekisteröintitiedot**.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Käyttöavain**

* Löydät tiliavaimesi Azure Enterprise Portalista kohdasta **Lataa käyttö** > **Ohjelmointirajapinnan Käyttöavain**.
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Lisäapua**

* Saat lisäohjeita määrittämisestä Azure Enterprise Power BI-sisältöpaketti on kirjautumalla Azure Enterprise Portal-portaaliin ja tarkastella olevaa Ohjelmointirajapinnan ohjetiedostoa **auttaa**. Voit myös etsiä lisäohjeita kohdassa **raporttien** -> **Lataa käyttö** -> **Ohjelmointirajapinnan Käyttöavain**.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

