---
title: SQL-tietokantavalvonnan sisältöpaketti
description: SQL-tietokantavalvonnan sisältöpaketti Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 36351491f7cb99a2e597ef4fd498ef7c38da386e
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34243887"
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>SQL-tietokantavalvonnan sisältöpaketti Power BI:lle
Power BI:n sisältöpaketti Azuren [SQL-tietokantavalvontaa](http://azure.microsoft.com/documentation/articles/sql-database-auditing-get-started/) varten auttaa sinua ymmärtämään tietokantatoimia ja saamaan merkityksellisiä tietoja poikkeamista, jotka saattavat ilmaista ongelmia yrityksessä tai mahdollisia tietoturvarikkomuksia. 

Muodosta yhteys [SQL-tietokantavalvonnan sisältöpakettiin](https://app.powerbi.com/getdata/services/sql-db-auditing) Power BI:tä varten.

>[!NOTE]
>Sisältöpaketti tuo tietoja kaikista taulukoista, joiden nimessä on sana AuditLogs, ja liittää ne yksittäiseen tietomallitaulukkoon nimeltä AuditLogs. Viimeiset 250 000 tapahtumaa sisällytetään ja tiedot päivitetään päivittäin.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunasta **Nouda tiedot**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getdata.png) 
2. Valitse Palvelut-ruudussa Nouda.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getservices.png) 
3. Valitse **SQL-tietokantavalvonta** \> **Nouda**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/sqldbaudit.png)
4. SQL-tietokantavalvonnan ikkunassa:
   
   - Anna sen Azure-taulukon tallennustilin nimi tai URL-osoite, johon lokit on tallennettu.
   
   - Anna haluamasi SQL-palvelimen nimi. Lataa kaikkien palvelimien valvontalokit kirjoittamalla ”\*”.
   
   - Anna haluamasi SQL-tietokannan nimi. Lataa kaikkien tietokantojen valvontalokit kirjoittamalla ”\*”.
   
   - Anna haluamasi lokit sisältävän Azure-taulukon nimi. Lataa valvontalokit kaikista taulukoista, joiden nimessä on teksti AuditLogs, kirjoittamalla ”\*”.
   
   >[!IMPORTANT]
   >Suorituskykysyistä on suositeltavaa aina määrittää tarkka taulukkonimi, vaikka kaikki valvontalokit olisi tallennettuna yhteen taulukkoon.
   
   - Anna haluamasi valvontalokien alkamispäivämäärä. Jos haluat ladata valvontalokit ilman ajan alarajaa, kirjoita ”\*”. Lataa valvontalokit viimeisestä päivästä lähtien kirjoittamalla ”1d”.
   
   - Anna haluamasi valvontalokien päättymispäivämäärä. Lataa valvontalokit ilman ajan ylärajaa kirjoittamalla ”\*”.
   
   ![](media/service-connect-to-azure-sql-database-auditing/dbauditing_param.png)
5. Valitse todentamismenetelmää varten **Avain**, anna oma **tiliavaimesi** \> **Kirjaudu sisään**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqlauditing3.png)
6. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Uudet kohteet on merkitty keltaisella tähdellä \*.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqldbauditingnewdash.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojen noutaminen Power BI:hin](service-get-data.md)
[Power BI:n käytön aloittaminen](service-get-started.md)
