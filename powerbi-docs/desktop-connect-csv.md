---
title: CSV-tiedostoihin yhdistäminen Power BI Desktopissa
description: CSV-tiedostoon yhdistäminen ja tietojen käyttäminen helposti Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c5d817af65529506a0ee515be5e287a629d6ad54
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "73878561"
---
# <a name="connect-to-csv-files-in-power-bi-desktop"></a>CSV-tiedostoihin yhdistäminen Power BI Desktopissa
Yhteyden muodostaminen pilkuin erotettujen arvojen (*CSV*) tiedostoon Power BI Desktopissa tapahtuu pitkälti samoin kuin yhteyden muodostaminen Excel-työkirjaan. Kumpikin on helppoa. Tässä artikkelissa kerrotaan vaiheittain, miten voit muodostaa yhteyden mihin tahansa CSV-tiedostoon, johon sinulla on käyttöoikeus.

Aloita valitsemalla Power BI Desktopissa**Nouda tiedot > DSV** **Aloitus**-valintanauhasta.

![](media/desktop-connect-csv/connect-to-csv_1.png)

Valitse CSV-tiedosto avautuvassa **Avaa**-valintaikkunassa.

![](media/desktop-connect-csv/connect-to-csv_2.png)

Kun valitset **Avaa**, Power BI Desktop käyttää tiedostoa ja määrittää tietyt tiedostomääritteet, kuten tiedoston alkuperän, erottimen tyypin ja tiedostossa olevien tietotyyppien tunnistamiseen käytettävien rivien määrän.

Nämä tiedostomääritteet ja -asetukset näkyvät avattavassa luettelossa valintoina **CSV-tuonti**-valintaikkunan yläosassa (kuva alla). Voit muuttaa tunnistettuja asetuksia manuaalisesti valitsemalla toisen vaihtoehdon avattavasta valitsimesta.

![](media/desktop-connect-csv/connect-to-csv_3.png)

Kun olet tyytyväinen valintoihin, voit valita **Lataa** ja tuoda tiedoston Power BI Desktopiin tai **Muokkaa** ja avata **Kyselyeditorin**, jossa voit muokata tai muuntaa tietoja enemmän ennen tietojen tuomista.

Kun lataat tiedot Power BI Desktopiin, näet taulukon ja sen sarakkeet (joka esitetään kenttinä Power BI Desktopissa) **Kentät**-ruudussa Power BI Desktopin Raportti-näkymän oikeassa sivussa.

![](media/desktop-connect-csv/connect-to-csv_4.png)

Muuta ei tarvita – CSV-tiedoston tiedot ovat nyt Power BI Desktopissa.

Voit nyt käyttää Power BI Desktopia visualisointien tai raporttien luomiseen tai vuorovaikutukseen muiden tietojen kanssa, joihin ehkä haluat olla yhteydessä ja joita tuot, kuten Excel-työkirjat, tietokannat tai muut tietolähteet.

> [!IMPORTANT]
> Kun tuot CSV-tiedoston, Power BI Desktop luo *sarakkeet=x* (jossa *x* on CSV-tiedoston sarakkeiden määrä alkuperäisen tuonnin aikana) vaiheena Power Query -editorissa. Jos myöhemmin lisäät sarakkeita ja tietolähde on määritetty päivitettäväksi, alkuperäisen *x*-sarakemäärän ylittäviä sarakkeita ei päivitetä. 


## <a name="next-steps"></a>Seuraavat vaiheet
Power BI Desktopin avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   

