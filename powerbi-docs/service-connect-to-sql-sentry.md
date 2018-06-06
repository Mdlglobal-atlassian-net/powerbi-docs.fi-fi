---
title: Yhteyden muodostaminen SQL Sentry -palveluun Power BI:llä
description: SQL Sentry Power BI:lle
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
ms.openlocfilehash: c73502381e99bf64a8e342ca46ee1bb7089b6825
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815279"
---
# <a name="connect-to-sql-sentry-with-power-bi"></a>Yhteyden muodostaminen SQL Sentry -palveluun Power BI:llä
SQL Sentryn keräämien suorituskykytietojen analysoiminen on helppoa Power BI:llä. Power BI noutaa tiedot ja laatii sitten oletuskoontinäytön ja siihen liittyvät raportit kyseisten tietojen perusteella.

Muodosta yhteys [SQL Sentry -sisältöpakettiin](https://app.powerbi.com/groups/me/getdata/services/sql-sentry) Power BI:tä varten.

>[!NOTE]
>Yhteyden muodostaminen edellyttää SQL Sentry-tilin käyttöä, jota käytät muodostettaessa yhteyttä http://cloud.sqlsentry.com -palveluun sekä tietokantatunnusta, jota itse valvot.  Ohjeet tietokantatunnuksen löytämiseen ovat alla.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-sql-sentry/pbi_getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-sql-sentry/pbi_getservices.png) 
3. Valitse **SQL Sentry \> Nouda**.
   
   ![](media/service-connect-to-sql-sentry/sqlsentry.png)
4. Anna **Tietokantatunnus** sille tietokannalle, jota haluat valvoa Power BI:ssä. Lisätietoja [sen löytämisestä](#FindingParams) on alla.
   
   ![](media/service-connect-to-sql-sentry/img2400.png)
5. Valitse todennusmenetelmäksi **oAuth2 \> Kirjaudu sisään**.
   
   Anna pyydettäessä cloud.sqlsentry.com -tunnistetietosi ja noudata SQL Sentryn todennusprosessia.
   
   ![](media/service-connect-to-sql-sentry/img6400.png)
   
   Ensimmäisen kerran, kun muodostat yhteyden, Power BI kysyy, haluatko sallia vain luku -käyttöoikeudet tiliisi. Aloita tuontiprosessi valitsemalla Myönnä.  Tuontiprosessi voi kestää muutamia minuutteja riippuen siitä, kuinka paljon tililläsi on tietoja.
   
   ![](media/service-connect-to-sql-sentry/img7400.png)
6. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Uudet kohteet on merkitty keltaisella tähdellä \*:
   
   ![](media/service-connect-to-sql-sentry/img8200.png)
7. Valitse SQL Sentry -koontinäyttö.
   
   Tämä on oletuskoontinäyttö, jonka Power BI on luonut tietojesi näyttämistä varten. Voit muokata tätä koontinäyttöä, jotta näet tiedot juuri haluamallasi tavalla.
   
   ![](media/service-connect-to-sql-sentry/img9dashboard800.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md)
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajoitettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Seuraavat tiedot ovat käytettävissä SQL Sentrystä Power BI:ssä:

| Taulukon nimi | Kuvaus |
| --- | --- |
| Yhteys |Tämä taulukko sisältää tietoja SQL Sentrylle määritetyistä yhteyksistä. |
| Päivämäärä<br /> |Tämä taulukko sisältää päivämääriä tästä päivästä taaksepäin aikaisimpaan päivämäärään, josta suorituskykytietoja on kerätty ja säilytetty. |
| Käyttämättömyysaika<br /> |Tämä taulukko sisältää käyttämättömyysaikaan ja käyttöaikaan liittyviä tietoja jokaisesta palvelimesta, jota ympäristössäsi seurataan. |
| Muistin käyttö<br /> |Tässä taulukossa on tietoja siitä, paljonko muistia on käytettävissä tai vapaana kullakin palvelimellasi.<br /> |
| Palvelin<br /> |Tässä taulukossa on tallennetietoja ympäristösi jokaisesta palvelimesta. |
| Palvelimen kunto<br /> |Tämä taulukko sisältää tietoa kaikista tapahtumista, jotka on luotu ympäristösi mukautetuilla ehdoilla, mukaan lukien vakavuus ja lukumäärä. |

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien etsiminen
**Tietokantatunnus** löytyy kirjautumalla kohtaan <https://cloud.sqlsentry.com> uudessa selainikkunassa.  **Tietokantatunnus** on lueteltu yleiskatsauksen pääsivulla:

    ![](media/service-connect-to-sql-sentry/database2.png)

**Tietokantatunnus** näkyy myös Tietokannan tiedot -näytössä:

    ![](media/service-connect-to-sql-sentry/database.png)


## <a name="troubleshooting"></a>Vianmääritys
Jos joidenkin sovellustesi tietoja ei näy Power BI:ssä, varmista, että käytät oikeaa Tietokantatunnusta ja että sinulla on oikeudet tietojen tarkasteluun. 

Jos et omista SQL Sentry -tietokantaa, jota synkronoidaan kohteeseen <https://cloud.sqlsentry.com>, ota yhteyttä järjestelmänvalvojaan ja varmista, että sinulla on oikeudet kerättyjen tietojen tarkasteluun.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:hin](service-get-data.md)

