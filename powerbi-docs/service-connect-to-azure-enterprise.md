---
title: Muodosta yhteys Microsoft Azure Enterpriseen Power BI:llä
description: Microsoft Azure Enterprise Power BI:lle
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
ms.openlocfilehash: 60bcad86af5fcaa09d6b2fb16b581ec7c37264ae
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815259"
---
# <a name="connect-to-microsoft-azure-enterprise-with-power-bi"></a>Muodosta yhteys Microsoft Azure Enterpriseen Power BI:llä
Tutustu ja valvo Microsoft Azure Enterprise -tietojasi Power BI:ssä Power BI -sisältöpaketin avulla. Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys Power BI:n [Microsoft Azure Enterprise -sisältöpakettiin](https://app.powerbi.com/getdata/services/azure-enterprise).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
    ![](media/service-connect-to-azure-enterprise/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-azure-enterprise/services.png)
3. Valitse **Microsoft Azure Enterprise** \> **Nouda**.
   
   ![](media/service-connect-to-azure-enterprise/mazureenterprise.png)
4. Anna Azure-ympäristön URL-osoite ja monenko kuukauden tiedot haluat tuoda sekä Azure Enterprise -rekisteröintinumerosi. Azure-ympäristön URL-osoitteesi on `https://ea.azure.com` tai `https://ea.windowsazure.cn`. Lisätietoja [näiden parametrien löytämisestä](#FindingParams) on alla.
   
    ![](media/service-connect-to-azure-enterprise/params.png)
5. Anna Tiliavaimesi yhteyden muodostamista varten. Rekisteröintisi avain on Azure EA -portaalissa.
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. Tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md)
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajoitettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Azure Enterprise -sisältöpaketti sisältää kuukausittaiset raporttitiedot sille kuukausialueelle, jonka olet antanut yhteystyönkulun aikana. Alue on liikkuva ikkunassa, joten alueeseen kuuluvat päivämäärät päivittyvät, kun tietojoukko päivittyy.

## <a name="system-requirements"></a>Järjestelmävaatimukset
Sisältöpaketti edellyttää yritysominaisuuksien käyttöoikeuksia Azure-portaalissa.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Power BI -raportointi on käytettävissä EA Directille, kumppaneille ja välillisille asiakkaille, jotka voivat tarkastella laskutustietoja. Lue seuraavat tiedot kunkin arvon etsimisestä, joita yhteyden työnkulku odottaa.

**Azure-ympäristön URL-osoite**

* Tämä arvo on yleensä https://ea.azure.com, mutta voit tarkistaa URL-osoitteen, kun kirjaudut sisään vahvistamista varten.
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**Kuukausien määrä**

* Tämä on oltava luku välillä 1–36, joka edustaa niiden kuukausien lukumäärää (tästä päivästä), joiden tiedot haluat tuoda.

**Rekisteröintinumero**

* Tämä on Azure Enterprise -rekisteröintinumerosi, joka löytyy [Azure Enterprise Portalin](https://ea.azure.com/) aloitusnäytöstä kohdasta ”Rekisteröinnin tiedot”.
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**Käyttöavain**

* Avain löytyy Azure Enterprise Portalista kohdasta ”Lataa käyttö” > ”Ohjelmointirajapinnan käyttöavain”
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**Lisäapua**

* Lisäapua Azure Enterprise Power BI -paketin määrittämisestä löytyy kirjautumalla Azure Enterprise Portaliin, jossa voidaan tarkastella ”Ohje”-kohdassa olevaa Ohjelmointirajapinnan ohjetiedostoa, ja lisäohjeita kohdassa Raportit -> Lataa käyttö -> Ohjelmointirajapinnan käyttöavain.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

