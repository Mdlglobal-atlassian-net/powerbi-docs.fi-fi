---
title: Snowflake Computing -varastoon yhdistäminen Power BI Desktopissa
description: Voit yhdistää Snowflake Computing -varastoon ja käyttää sitä helposti Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e7534fd0da2039a2dafaf3ca80ee6957fa8d8754
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464297"
---
# <a name="connect-to-a-snowflake-computing-warehouse-in-power-bi-desktop"></a>Snowflake Computing -varastoon yhdistäminen Power BI Desktopissa
Voit muodostaa Power BI Desktopissa yhteyden **Snowflake Computing** -varastoon ja käyttää sen tietoja samaan tapaan kuin muita tietolähteitä käytetään Power BI Desktopissa. 

> [!NOTE]
> Sinun *täytyy* myös asentaa **Snowflaken ODBC-ohjain** tietokoneisiin, joissa käytetään **Snowflake**-liitintä, käyttämällä arkkitehtuuria, joka vastaa **Power BI Desktopin** versiota, joko 32- tai 64-bittistä. Käytä seuraavaa linkkiä ja [lataa sopiva Snowflaken ODBC-ohjain](https://go.microsoft.com/fwlink/?LinkID=823762).
> 
> 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Snowflake Computing -varastoon yhdistäminen
Jos haluat muodostaa yhteyden **Snowflake Computing** ‑varastoon, valitse Power BI Desktopin **Aloitus**-valintanauhasta **Nouda tiedot**. Valitse vasemmalla näkyvistä luokista **Tietokanta**, jolloin näkyviin tulee **Snowflake**.

![](media/desktop-connect-snowflake/connect-snowflake-2b.png)

Kirjoita tai liitä näkyviin tulevan **Snowflake**-ikkunan ruutuun Snowflake Computing -varastosi nimi ja valitse **OK**. Huomaa, että voit **tuoda** tiedot suoraan Power BI:hin tai käyttää **DirectQueryä**. Lue lisätietoja [DirectQueryn käyttämisestä](desktop-use-directquery.md). Huomaa, että AAD SSO tukee vain DirectQueryä.

![](media/desktop-connect-snowflake/connect-snowflake-3.png)

Kirjoita käyttäjänimesi ja salasanasi pyydettäessä.

![](media/desktop-connect-snowflake/connect-snowflake-4.png)

> [!NOTE]
> Kun annat tietyn **Snowflake**-palvelimen käyttäjänimen ja salasanan, Power BI Desktop käyttää samoja tunnistetietoja, kun yhteyttä yritetään muodostaa seuraavan kerran. Voit muokata näitä tunnistetietoja valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Tietolähdeasetukset**.
> 
> 

Jos haluat käyttää Microsoft-tilin asetusta, Snowflaken AAD-integraatio on määritettävä Snowflaken puolella. Voit tehdä tämän lukemalla [aihetta koskevat Snowflake-ohjeet](https://docs.snowflake.net/manuals/user-guide/oauth-powerbi.html#power-bi-sso-to-snowflake).

![Microsoft-tilin todennustyyppi Snowflake-liittimessä.](media/desktop-connect-snowflake/connect-snowflake-6.png)


Kun yhteyden muodostaminen onnistuu, näyttöön avautuu **Siirtymistoiminto**-ikkuna, jossa näet palvelimella käytettävissä olevat tiedot. Voit valita ikkunasta yhden tai useita elementtejä tuotavaksi **Power BI Desktopiin**.

![ODBC-virhe 28000 aiheuttaa yhteysvirheen.](media/desktop-connect-snowflake/connect-snowflake-5.png)

Voit **ladata** valitun taulukon, jolloin koko taulukko tuodaan **Power BI Desktopiin**, tai voit **muokata** kyselyä, joka avautuu **kyselyeditoriin**. Näin voit suodattaa ja tarkentaa käytettävää tietojoukkoa ja ladata sitten tarkennetun tietojoukon **Power BI Desktopiin**.

## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

