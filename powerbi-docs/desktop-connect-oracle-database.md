---
title: Oracle-tietokantaan yhdistäminen
description: Ohjeet ja Oracle-tietokannan Power BI Desktopiin yhdistämiseen tarvittavat ladattavat tiedostot
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 4/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a56097c02c9f3af63151d0a38e14fdc580e4ee9e
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34291001"
---
# <a name="connect-to-an-oracle-database"></a>Oracle-tietokantaan yhdistäminen
Yhteyden muodostaminen Oracle-tietokantaan **Power BI Desktopilla** edellyttää, että tietokoneessa on asennettuna Power BI Desktop ja oikea Oracle-asiakasohjelmisto. Oracle-asiakasohjelmiston versio (**32-bittinen** vai **64-bittinen**) määräytyy tietokoneeseen asennetun Power BI Desktop -version mukaan.

**Tuetut versiot**: Oracle 9 ja sitä uudemmat sekä Oracle-asiakasohjelmisto 8.1.7 ja sitä uudemmat.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Asennettuna olevan Power BI Desktop -version selvittäminen
Voit selvittää asennettuna olevan Power BI Desktop -version valitsemalla **Tiedosto > Ohje > Tietoja** ja tarkistamalla sitten **Versio:**-rivin tiedot. Seuraavassa kuvassa asennettuna on Power BI Desktopin 64-bittinen versio:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Oracle-asiakasohjelman asentaminen
**32-bittiset** Power BI Desktop -versiot: Lataa **32-bittinen** Oracle-asiakasohjelma seuraavasta linkistä ja asenna se tietokoneeseen:

* [32-bit Oracle Data Access Components (ODAC) with Oracle Developer Tools for Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

**64-bittiset** Power BI Desktop -versiot: Lataa **64-bittinen** Oracle-asiakasohjelma seuraavasta linkistä ja asenna se tietokoneeseen:

* [64-bit ODAC 12c Release 4 (12.1.0.2.4) for Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Oracle-tietokantaan yhdistäminen
Kun tietokoneessa on asennettuna vastaava Oracle-asiakasohjelman ohjain, voit muodostaa yhteyden Oracle-tietokantaan. Voit muodostaa yhteyden seuraavasti:

1. Valitse Nouda tiedot -ikkunasta **Tietokanta > Oracle Database**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. Kirjoita avautuvaan **Oracle Database** -valintaikkunaan palvelimen nimi ja valitse **Muodosta yhteys**. Jos SID-tunnus vaaditaan, anna se seuraavassa muodossa: *PalvelimenNimi/SID*, jossa SID on palvelimen yksilöllinen nimi. Jos *PalvelimenNimi/SID*-muoto ei toimi, kokeile *PalvelimenNimi/PalvelunNimi*-muotoa, jossa PalvelunNimi on yhteyden muodostuksessa käytetty alias.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. Jos haluat tuoda tietoja alkuperäisen tietokantakyselyn avulla, voit kirjoittaa kyselyn **SQL-lause**-ruutuun, jonka saa näkyviin laajentamalla **Oracle Database** -valintaikkunan **Lisäasetukset**-osion.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Kun olet kirjoittanut Oracle-tietokannan tiedot Oracle Database -valintaikkunaan (myös valinnaiset tiedot, kuten SID-tunnuksen tai alkuperäisen tietokantakyselyn), muodosta yhteys valitsemalla **OK**.
5. Jos Oracle-tietokanta edellyttää tietokannan käyttäjän tunnistetietoja, kirjoita kyseiset tiedot valintaikkunaan pyydettäessä.

