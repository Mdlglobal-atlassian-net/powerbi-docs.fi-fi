---
title: Yhteyden muodostaminen Amazon Redshift -tietokantaan Power BI Desktopissa
description: Helppo yhteyden muodostaminen Amazon Redshift -tietokantaan Power BI Desktopissa ja tietokannan käyttäminen
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c303bbd3fe229ea48dbad3da9d003851f7441956
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/09/2020
ms.locfileid: "75761630"
---
# <a name="connect-to-an-amazon-redshift-database-in-power-bi-desktop"></a>Amazon Redshift -tietokantaan yhdistäminen Power BI Desktopissa
**Power BI Desktopissa** voi muodostaa yhteyden **Amazon Redshift** ‑tietokantaan ja käyttää sen tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa.

## <a name="connect-to-an-amazon-redshift-database"></a>Yhteyden muodostaminen Amazon Redshift-tietokantaan
Jos haluat muodostaa yhteyden **Amazon Redshift** ‑tietokantaan, valitse Power BI Desktopissa **Aloitus**-valintanauhasta **Nouda tiedot**. Valitse näkymän vasemmasta laidasta **Tietokanta**, ja näkyviin tulee **Amazon Redshift**.

![](media/desktop-connect-redshift/connect_redshift_3.png)

Kirjoita tai liitä näytölle avautuvan **Amazon Redshift** -ikkunan tekstikenttään halutun **Amazon Redshift** ‑palvelimen ja tietokannan nimi. Käyttäjät voivat *Palvelin*-kentän osana määrittää portin seuraavassa muodossa: *ServerURL:Port*

![](media/desktop-connect-redshift/connect_redshift_4.png)

Kirjoita käyttäjänimesi ja salasanasi pyydettäessä. Käytä palvelimella virheiden välttämiseksi nimeä, joka vastaa tarkasti SSL-varmennetta. 

![](media/desktop-connect-redshift/connect_redshift_5.png)

Kun yhteyden muodostaminen onnistuu, näyttöön avautuu **Siirtymistoiminto**-ikkuna, jossa näet palvelimella käytettävissä olevat tiedot. Voit valita ikkunasta yhden tai useita elementtejä tuotavaksi **Power BI Desktopiin**.

![](media/desktop-connect-redshift/connect_redshift_6.png)

Kun olet tehnyt haluamasi valinnat **Siirtymistoiminto**-ikkunassa, voit joko **Lataa** tiedot tai **Muokkaa** tietoja.

* Jos valitset **Lataa**, sinua pyydetään käyttämään joko *Tuo*- tai *DirectQuery*-tilaa. Lisätietoja saat tästä [DirectQueryn toiminnasta kertovasta artikkelista](desktop-use-directquery.md).
* Jos valitset **Muokkaa**, näytölle avautuu **Kyselyeditori**, jossa voit soveltaa tietoihin erilaisia muuntoja ja suodattimia. Monia niistä sovelletaan suoraan taustalla olevaan **Amazon Redshift** ‑tietokantaan (jos tuettu).

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

