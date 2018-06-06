---
title: Impala-tietokantaan yhdistäminen Power BI Desktopissa
description: Impala-tietokantaan yhdistäminen ja tietokannan käyttäminen helposti Power BI Desktopissa
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 196974bedcace4fbe51b7e7ac551bd0923f7a891
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973687"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Impala-tietokantaan yhdistäminen Power BI Desktopissa
Power BI Desktopissa voi muodostaa yhteyden **Impala**‑tietokantaan ja käyttää sen tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa.

## <a name="connect-to-an-impala-database"></a>Impala-tietokantaan yhdistäminen
Jos haluat muodostaa yhteyden **Impala**‑tietokantaan, valitse Power BI Desktopissa **Aloitus**-valintanauhasta **Nouda tiedot**. Valitse vasemmalla näkyvistä luokista **Tietokanta**, jolloin näkyviin tulee **Impala**.

![](media/desktop-connect-impala/connect_impala_2.png)

Kirjoita tai liitä Impala-palvelimen nimi avautuvan **Impala**-ikkunan ruutuun ja valitse **OK**. Huomaa, että voit **tuoda** tiedot suoraan Power BI:hin tai käyttää **DirectQueryä**. Lue lisätietoja [DirectQueryn käyttämisestä](desktop-use-directquery.md).

![](media/desktop-connect-impala/connect_impala_3a.png)

Anna kehotettaessa käyttäjänimesi ja salasanasi tai muodosta yhteys anonyymisti. Kumpaakin vaihtoehtoa tuetaan.

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Kun annat tietyn **Impala**-palvelimen käyttäjänimen ja salasanan, Power BI Desktop käyttää samoja tunnistetietoja, kun yhteyttä yritetään muodostaa seuraavan kerran. Voit muokata näitä tunnistetietoja valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Tietolähdeasetukset**.
> 
> 

Kun yhteyden muodostaminen onnistuu, näyttöön avautuu **Siirtymistoiminto**-ikkuna, jossa näet palvelimella käytettävissä olevat tiedot. Voit valita ikkunasta yhden tai useita elementtejä tuotavaksi **Power BI Desktopiin**.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset
Seuraavat **Impala**-liittimeen liittyvät rajoitukset ja tärkeät seikat on syytä huomioida:

* Tulevat palvelupaketit sisältävät päivitystuen **Power BI Gatewayn** kautta.

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

