---
title: Impala-tietokantaan yhdistäminen Power BI Desktopissa
description: Impala-tietokantaan yhdistäminen ja tietokannan käyttäminen helposti Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 781e9f6813fee63b7c5d83a2e7e60e1ed1eeedc0
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2018
ms.locfileid: "39326989"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Impala-tietokantaan yhdistäminen Power BI Desktopissa
Power BI Desktopissa voi muodostaa yhteyden **Impala**‑tietokantaan ja käyttää sen tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa.

## <a name="connect-to-an-impala-database"></a>Impala-tietokantaan yhdistäminen
Jos haluat muodostaa yhteyden **Impala**‑tietokantaan, valitse Power BI Desktopissa **Aloitus**-valintanauhasta **Nouda tiedot**. Valitse vasemmalla näkyvistä luokista **Tietokanta**, jolloin näkyviin tulee **Impala**.

![](media/desktop-connect-impala/connect_impala_2.png)

Kirjoita tai liitä Impala-palvelimen nimi avautuvan **Impala**-ikkunan ruutuun ja valitse **OK**. Huomaa, että voit **tuoda** tiedot suoraan Power BI:hin tai käyttää **DirectQueryä**. Lue lisätietoja [DirectQueryn käyttämisestä](desktop-use-directquery.md).

![](media/desktop-connect-impala/connect_impala_3a.png)

Kirjoita pyydettäessä tunnistetiedot tai muodosta yhteys anonyymisti. Impala-liitin tukee anonyymiä todentamista, perustodentamista (käyttäjänimi ja salasana) sekä Windows-todentamista.

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Kun annat tietyn **Impala**-palvelimen käyttäjänimen ja salasanan, Power BI Desktop käyttää samoja tunnistetietoja, kun yhteyttä yritetään muodostaa seuraavan kerran. Voit muokata näitä tunnistetietoja valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Tietolähdeasetukset**.
> 
> 

Kun yhteyden muodostaminen onnistuu, näyttöön avautuu **Siirtymistoiminto**-ikkuna, jossa näet palvelimella käytettävissä olevat tiedot. Voit valita ikkunasta yhden tai useita elementtejä tuotavaksi **Power BI Desktopiin**.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset
Seuraavat **Impala**-liittimeen liittyvät rajoitukset ja tärkeät seikat on syytä huomioida:

* Impala-liitintä tuetaan paikallisessa tietoyhdyskäytävässä, kun käytetään mitä tahansa kolmesta tuetusta todentamistavasta.

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

