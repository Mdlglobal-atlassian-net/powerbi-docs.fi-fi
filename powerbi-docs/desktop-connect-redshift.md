---
title: Yhteyden muodostaminen Amazon Redshift -tietokantaan Power BI Desktopissa
description: Helppo yhteyden muodostaminen Amazon Redshift -tietokantaan Power BI Desktopissa ja tietokannan käyttäminen
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
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 5c58b05333084a7754187af6c3938914c1f88503
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/04/2018
---
# <a name="connect-to-amazon-redshift-in-power-bi-desktop"></a>Yhteyden muodostaminen Amazon Redshiftiin Power BI Desktopissa
**Power BI Desktopissa** voi muodostaa yhteyden **Amazon Redshift** ‑tietokantaan ja käyttää sen tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa.

## <a name="connect-to-an-amazon-redshift-database"></a>Yhteyden muodostaminen Amazon Redshift-tietokantaan
Jos haluat muodostaa yhteyden **Amazon Redshift** ‑tietokantaan, valitse Power BI Desktopissa **Aloitus**-valintanauhasta **Nouda tiedot**. Valitse näkymän vasemmasta laidasta **Tietokanta**, ja näkyviin tulee **Amazon Redshift**.

![](media/desktop-connect-redshift/connect_redshift_3.png)

Kirjoita tai liitä näytölle avautuvan **Amazon Redshift** -ikkunan tekstikenttään halutun **Amazon Redshift** ‑palvelimen ja tietokannan nimi. Käyttäjä voi määrittää *Palvelin*-kenttään haluamansa portin seuraavassa muodossa: *palvelinURL:portti*

![](media/desktop-connect-redshift/connect_redshift_4.png)

Kirjoita näytölle avautuvaan kehoteikkunaan käyttäjänimesi ja salasanasi.

![](media/desktop-connect-redshift/connect_redshift_5.png)

Kun yhteyden muodostaminen onnistuu, näytölle avautuu **Siirtymistoiminto**-ikkuna, jossa näet palvelimella käytettävissä olevat tiedot. Voit valita ikkunasta yhden tai useita elementtejä tuotavaksi **Power BI Desktopiin**.

![](media/desktop-connect-redshift/connect_redshift_6.png)

Kun olet tehnyt haluamasi valinnat **Siirtymistoiminto**-ikkunassa, voit joko **Lataa** tiedot tai **Muokkaa** tietoja.

* Jos valitset **Lataa**, sinua pyydetään käyttämään joko *Tuo*- tai *DirectQuery*-tilaa. Lisätietoja saat tästä [DirectQueryn toiminnasta kertovasta artikkelista](desktop-use-directquery.md).
* Jos valitset **Muokkaa**, näytölle avautuu **Kyselyeditori**, jossa voit soveltaa tietoihin erilaisia muuntoja ja suodattimia. Monia niistä sovelletaan suoraan taustalla olevaan **Amazon Redshift** ‑tietokantaan (jos tuettu).

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

