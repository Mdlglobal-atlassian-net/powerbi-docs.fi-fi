---
title: Tietojen noutaminen tiedostoista
description: Lue lisää siitä, miten voit noutaa tietoja Excel-, Power BI Desktop- ja CSV-tiedostoista Power BI:hin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 82afd38611252486196c580da35e6d04d58a2479
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/27/2018
ms.locfileid: "39327794"
---
# <a name="get-data-from-files"></a>Tietojen noutaminen tiedostoista
![](media/service-get-data-from-files/file_icons.png)

Power BI:ssä voit muodostaa yhteyden tai tuoda tietoja ja raportteja kolmentyyppisistä tiedostoista.

* Microsoft Excel (.xlsx tai .xlsm)
* Power BI Desktop (.pbix)
* Pilkulla eroteltu arvo (.csv)

## <a name="what-does-get-data-from-a-file-really-mean"></a>Mitä tietojen noutamisella tiedostosta todella tarkoitetaan?
Power BI:ssä tutkittavat tiedot ovat peräisin tietojoukosta. Tietojoukon muodostaminen edellyttää kuitenkin joidenkin tietojen noutamista. Tässä artikkelissa perehdymme tietojen noutamiseen tiedostoista.

Tietojoukon tärkeyden ja niiden sisältämien tietojen noutamisen ymmärtämiseksi käytämme esimerkkinä autoa. Istahda siis autoosi ja katso sen kojetaulua. Se muistuttaa melko lailla sitä, että istuisit tietokoneellasi katsomassa Power BI:n raporttinäkymää. Kojetaulusta näet, mitä autossasi tapahtuu – moottorin käyntinopeuden, lämpötilan, kytketyn vaihteen, ajonopeuden jne.

Power BI:ssä tietojoukko muistuttaa auton moottoria. Tietojoukko tarjoaa datan, mittarit ja tiedot, jotka näytetään Power BI:n raporttinäkymässä. Moottori – eli tietojoukko – tarvitsee tietenkin polttoainetta, eli Power BI:n tapauksessa tietoja. Autossa on polttoainesäiliö, joka syöttää moottoriin polttoainetta. Power BI:ssä tarvitaan vastaavasti säiliö, josta voidaan syöttää tietoja tietojoukkoon. Tässä tapauksessa polttoainesäiliö on Power BI Desktop -tiedosto, Excel-työkirjatiedosto tai. CSV-tiedosto.

Viedään esimerkki vielä astetta pidemmälle. Auton polttoainesäiliö on täytettävä polttoaineella. Power BI Desktop-, Excel- tai .CSV-tiedoston polttoainetta ovat muiden tietolähteiden tiedot. Saamme tietoja toisesta tietolähteestä ja laitamme ne Excel-, Power BI Desktop- tai .CSV-tiedostoon. Jos kyseessä on Excel-työkirja tai .CSV-tiedosto, voimme lisätä tietorivejä manuaalisesti. Voimme myös muodostaa yhteyden ulkoiseen tietolähteeseen ja kysellä ja ladata tietoja tiedostoomme. Kun meillä on tiedosto, joka sisältää tietoja, voimme tuoda sen Power BI:hin tietojoukkona.

> [!NOTE]
> Excel-työkirjoissa tietojen täytyy olla taulukossa tai tietomallissa, jotta ne voidaan tuoda Power BI:hin.
> 
> 

## <a name="where-your-file-is-saved-makes-a-difference"></a>Tiedoston tallennussijainnilla on merkitystä
**Paikallisesti** – Jos tallennat tiedoston tietokoneesi paikalliselle asemalle tai muuhun organisaatiosi sijaintiin, voit *tuoda* Power BI:n kautta tiedostosi Power BI:hin. Todellisuudessa tiedosto säilyy paikallisella kiintolevyllä, joten koko tiedostoa ei varsinaisesti tuoda Power BI:hin. Käytännössä Power BI ‑sivustolle luodaan uusi tietojoukko, johon tiedot – ja joissakin tapauksissa tietomalli – ladataan. Jos tiedostossa on raportteja, ne näkyvät Power BI -sivuston Raportit-kohdassa.

**OneDrive – yritys** – Jos sinulla on OneDrive for Business ja olet kirjautunut siihen sisään käyttämällä samaa tiliä, jolla kirjaudut Power BI:hin, se on selvästi tehokkain tapa synkronoida Excel-, Power BI Desktop- ja .CSV-tiedostoissa olevat työsi Power BI:ssä olevien tietojoukkojen, raporttien ja raporttinäkymien kanssa. Koska sekä Power BI että OneDrive toimivat pilvipalvelussa, Power BI muodostaa yhteyden OneDrivessa sijaitsevaan tiedostoon noin tunnin välein. Jos muutoksia löytyy, Power BI:n tietojoukko, raportit ja raporttinäkymät päivitetään automaattisesti.

**OneDrive – henkilökohtainen** – Jos tallennat tiedostot henkilökohtaiseen OneDrive-tiliisi, saat monia samoja etuja kuin käyttäessäsi OneDrive for Businessia. Suurin ero on, että sinun on kirjauduttava sisään OneDriveen käyttämällä Microsoft-tiliäsi, kun muodostat ensimmäisen kerran yhteyden tiedostoon (Nouda tiedot > Tiedostot > OneDrive - henkilökohtainen). Yleensä Microsoft-tili on eri kuin tili, jota käytetään Power BI:hin kirjautumiseen. Kun kirjaudut sisään OneDriveen käyttämällä Microsoft-tiliäsi, muista valita asetus Pidä minut sisäänkirjautuneena. Näin Power BI voi muodostaa yhteyden tiedostoon noin tunnin välein ja varmistaa, että Power BI:n tietojoukko on synkronoitu.

**SharePoint-työryhmäsivustot** – Power BI Desktop -tiedostojen tallentaminen SharePoint-työryhmäsivustoihin tapahtuu lähes samoin kuin tallentaminen OneDrive for Businessiin. Suurin ero on siinä, miten yhteys Power BI:stä tiedostoon muodostetaan. Voit määrittää URL-osoitteen tai muodostaa yhteyden pääkansioon.

## <a name="ready-to-get-started"></a>Oletko valmis aloittamaan?
Seuraavista artikkeleista saat lisätietoja tiedoston noutamisesta Power BI:hin.

* [Tietojen hakeminen Excel-työkirjatiedostoista](service-excel-workbook-files.md)
* [Tietojen hakeminen Power BI Desktop -tiedostoista](service-desktop-files.md)
* [Tietojen hakeminen .csv-tiedostosta](service-comma-separated-value-files.md)

