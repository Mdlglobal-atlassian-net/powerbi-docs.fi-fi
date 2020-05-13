---
title: Tietojen hakeminen .CSV-tiedostosta
description: Lue lisää siitä, miten voit noutaa tietoja .CSV-tiedostoista Power BI:hin
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: a33c8a45f4f32efb0a47df82b8af23d42c281ae9
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83300340"
---
# <a name="get-data-from-comma-separated-value-csv-files"></a>Tietojen hakeminen .CSV-tiedostosta
![](media/service-comma-separated-value-files/csv_icon.png)

Pilkuilla eroteltuja arvoja sisältävät tiedostot, eli .CSV-tiedostot, ovat yksinkertaisia tekstitiedostoja, joiden riveillä olevat arvot on eroteltu pilkulla. Tämän tyypin tiedostot voivat sisältää erittäin suuria tietomääriä melko pienessä tiedostokoossa, minkä ansiosta ne sopivat hyvin Power BI:n tietolähteeksi. Voit ladata .CSV-mallitiedoston [tästä](https://go.microsoft.com/fwlink/?LinkID=619356).

Jos sinulla on .CSV-tiedosto, voit tuoda sen Power BI -sivustoosi tietojoukkona ja tutkia tietoja, luoda raporttinäkymiä ja jakaa tietoja muiden kanssa.

>[!TIP]
>Monet organisaatiot luovat joka päivä päivitetyt tiedot sisältävän .CSV-tiedoston. Varmistaaksesi, että tietojoukkosi Power BI:ssä pysyy synkronoituna päivitetyn tiedostosi kanssa, tallenna tiedosto OneDriveen samalla nimellä.

## <a name="where-your-file-is-saved-makes-a-difference"></a>Tiedoston tallennussijainnilla on merkitystä
**Paikallisesti** – Jos tallennat tiedoston tietokoneesi paikalliselle asemalle tai muuhun organisaatiosi sijaintiin voit *tuoda* Power BI:n kautta tiedostosi Power BI:hin. Todellisuudessa tiedosto säilyy paikallisella kiintolevyllä, joten koko tiedostoa ei varsinaisesti tuoda Power BI:hin. Käytännössä Power BI:hin luodaan uusi tietojoukko, johon .CSV-tiedoston tiedot ladataan.

**OneDrive – yritys** – Ehdottomasti tehokkain tapa, jolla voit pitää .CSV-tiedostosi ja Power BI:n tietojoukon, raportit ja raporttinäkymät synkronoituina, on käyttää OneDrive for Businessia ja kirjautua siihen sisään samalla tilillä kuin Power BI:hinkin. Koska sekä Power BI että OneDrive toimivat pilvipalvelussa, Power BI *muodostaa yhteyden* OneDrivessa sijaitsevaan tiedostoon noin tunnin välein. Jos muutoksia löytyy, Power BI:n tietojoukko, raportit ja raporttinäkymät päivitetään automaattisesti.

**OneDrive – henkilökohtainen** – Jos tallennat tiedostot henkilökohtaiseen OneDrive-tiliisi, saat monia samoja etuja kuin käyttäessäsi OneDrive for Businessia. Suurin ero on, että sinun on kirjauduttava sisään OneDriveen käyttämällä Microsoft-tiliäsi, kun muodostat ensimmäisen kerran yhteyden tiedostoon (Nouda tiedot > Tiedostot > OneDrive - henkilökohtainen). Yleensä Microsoft-tili on eri kuin tili, jota käytetään Power BI:hin kirjautumiseen. Kun kirjaudut sisään OneDriveen käyttämällä Microsoft-tiliäsi, muista valita asetus Pidä minut sisäänkirjautuneena. Näin Power BI voi muodostaa yhteyden tiedostoon noin tunnin välein ja varmistaa, että Power BI:n tietojoukko on synkronoitu.

**SharePoint-työryhmäsivustot** – Power BI Desktop -tiedostojen tallentaminen SharePoint-työryhmäsivustoihin tapahtuu lähes samoin kuin tallentaminen OneDrive for Businessiin. Suurin ero on siinä, miten yhteys Power BI:stä tiedostoon muodostetaan. Voit määrittää URL-osoitteen tai muodostaa yhteyden pääkansioon.

## <a name="import-or-connect-to-a-csv-file"></a>Tuo tietoja tai yhdistä .CSV-tiedostoon
>[!IMPORTANT]
>Power BI:hin tuotavan tiedoston enimmäiskoko on 1 gigatavu.

1. Valitse Power BI:n siirtymisruudussa **Nouda tiedot**.
   
   ![](media/service-comma-separated-value-files/csv_get_data_button.png)
2. Valitse **Tiedostot**-kohdassa **Nouda**.
   
   ![](media/service-comma-separated-value-files/csv_files_get.png)
3. Etsi tiedosto.
   
   ![](media/service-comma-separated-value-files/csv_find_your_file.png)

## <a name="next-steps"></a>Seuraavat vaiheet
**Tutki tietoja** – Kun olet noutanut tiedot tiedostosta Power BI:hin, on aika tutkia niitä. Napsauta hiiren kakkospainikkeella uutta tietojoukkoa ja valitse sitten **Tutki**.

**Ajoitettu päivitys** – Jos tiedosto on tallennettu paikalliseen asemaan, voit määrittää ajoitetun päivityksen, jolloin tietojoukko ja raportit Power BI:ssä pysyvät ajan tasalla. Lue lisää artikkelista [Tietojen päivittäminen Power BI:ssä](refresh-data.md). Jos tiedosto on tallennettu OneDriveen, Power BI Synkronoi sen automaattisesti noin tunnin välein.

