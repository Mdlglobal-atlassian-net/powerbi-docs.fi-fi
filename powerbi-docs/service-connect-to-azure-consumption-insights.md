---
title: Yhteyden muodostaminen Microsoft Azure Consumption Insightsiin Power BI:n avulla
description: Microsoft Azure Consumption Insightsiin for Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 09/25/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e51f936e44e8c8ee3442aedfb2389675774c0a47
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020424"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Yhteyden muodostaminen Microsoft Azure Consumption Insightsiin Power BI:n avulla
Tutki ja valvo Microsoft Azure Enterprise -kulutustietojasi Power BI -palvelussa Power BI -sisältöpaketin avulla. Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys Power BI -palvelulle suunniteltuun [Microsoft Azure Consumption Insights -sisältöpakettiin](https://app.powerbi.com/getdata/services/azureconsumption).

> [!NOTE]
> Jos haluat mukautetumpia määrityksiä, kokeile [Azure Consumption Insights -liittimen](desktop-connect-azure-consumption-insights.md) käyttöä Power BI Desktopissa.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse Power BI -palvelun vasemman siirtymisruudun alareunasta **Nouda tiedot**.
   
    ![Nouda tiedot](media/service-connect-to-azure-consumption-insights/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![Nouda palvelut](media/service-connect-to-azure-consumption-insights/services.png)
3. Valitse **Microsoft Azure Consumption Insights** \> **Hanki nyt**. 
   
   ![Hanki se nyt](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Valitse, kuinka monen kuukauden tiedot haluat tuoda, ja anna Azure Enterprise -rekisteröintinumerosi. Lisätietoja [näiden parametrien löytämisestä](#FindingParams) on alla.
   
    ![Muodosta yhteys Microsoft Azure Consumption Insightsiin](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Anna Tiliavaimesi yhteyden muodostamista varten. Löydät rekisteröintiavaimen Azure EA -portaalista. 
   
    ![Microsoft Azure Consumption Insights: avain](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi koontinäyttö, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
   ![Microsoft Azure Consumption Insights -koontinäyttö](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla

## <a name="whats-included"></a>Paketin sisältö
Microsoft Azure Consumption Insights -sisältöpaketti sisältää kuukausittaiset raporttitiedot sille kuukausialueelle, jonka olet antanut yhdistettäessä. Alue on liikkuva aikaväli, joten alueeseen kuuluvat päivämäärät päivitetään, kun tietojoukko päivittyy.

## <a name="system-requirements"></a>Järjestelmävaatimukset
Sisältöpaketti edellyttää Enterprise-ominaisuuksien käyttöoikeuksia Azure-portaalissa. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Power BI -raportointi on käytettävissä EA Directille, kumppaneille ja välillisille asiakkaille, jotka voivat tarkastella laskutustietoja. Lue seuraavat tiedot yhteyden työnkulun vaatimien arvojen etsimisestä.

**Kuukausien määrä**

* Kuukausien määrä (1–36) joiden tiedot haluat tuoda.

**Rekisteröintinumero**

* Azure Enterprise -rekisteröintinumerosi, joka löytyy [Azure Enterprise Portalin](https://ea.azure.com/) aloitusnäytöstä kohdasta **Rekisteröinnin tiedot**.
  
    ![Rekisteröintinumero](media/service-connect-to-azure-consumption-insights/params2.png)

**Käyttöavain**

* Käyttöavain löytyy Azure Enterprise Portalista kohdasta **Lataa käyttö** > **Ohjelmointirajapinnan käyttöavain**.
  
    ![Käyttöavain](media/service-connect-to-azure-consumption-insights/creds2.png)

**Lisäapua**

* Saat lisätietoja Azure Enterprise Power BI -paketin määrittämisestä kirjautumalla Azure Enterprise Portaliin ja tarkastelemalla ohjelmointirajapinta-ohjetta kohdassa **Ohjeet**. Lisäohjeita löytyy myös kohdasta **Raportit** -> **Lataa käytön** -> **API-käyttöavain**.
* Jos haluat mukautetumpia määrityksiä, kokeile [Azure Consumption Insights -liittimen](desktop-connect-azure-consumption-insights.md) käyttöä Power BI Desktopissa.

## <a name="next-steps"></a>Seuraavat vaiheet

[Azure Consumption Insights -liitin](desktop-connect-azure-consumption-insights.md) Power BI Desktopissa

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

