---
title: Tietoihin yhdistämisen pikaopas
description: Tietolähteeseen yhdistäminen Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: quickstart
ms.date: 05/07/2018
ms.author: davidi
LocalizationGroup: quickstart
ms.openlocfilehash: 3f29bd899c62adbe2de1fdedd25b60cb104c71e0
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34287827"
---
# <a name="quickstart-connect-to-data-in-power-bi-desktop"></a>Pikaopas: Tietoihin yhdistäminen Power BI Desktopissa

Tässä pikaoppaassa muodostat yhteyden tietoihin **Power BI Desktopin** avulla. Tämä on ensimmäinen vaihe tietomallien ja raporttien luomiseen.

![Power BI Desktop](media/desktop-what-is-desktop/what-is-desktop_01.png)

Jos et ole rekisteröitynyt Power BI:hin, [rekisteröidy ilmaiseen kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

Tarvitset seuraavat, jotta voit suorittaa tämän artikkelin vaiheet:
* Lataa ja asenna ilmainen **Power BI Desktop** -sovellus, joka suoritetaan paikallisessa tietokoneessa. Voit [ladata **Power BI Desktopin**](https://powerbi.microsoft.com/desktop) suoraan tai hakea sen [ **Microsoft-kaupasta**](http://aka.ms/pbidesktopstore).
* [Lataa tämä Excel-mallityökirja](http://go.microsoft.com/fwlink/?LinkID=521962) ja luo kansio nimeltä *C:\PBID-qs*, johon tallennat kyseisen Excel-tiedoston. Tämän pikaoppaan seuraavissa vaiheissa oletetaan, että ladattu Excel-työkirja sijaitsee kyseisessä paikassa.

## <a name="launch-power-bi-desktop"></a>Käynnistä Power BI Desktop

Kun olet asentanut **Power BI Desktop** -sovelluksen, käynnistä se paikallisessa tietokoneessa. Tyhjä pohja avautuu. Voit luoda siihen visualisointeja ja raportteja tiedoista, joihin muodostat yhteyden. 

![Power BI Desktop - tyhjä pohja](media/desktop-quickstart-connect-to-data/qs-connect-data_01.png)

## <a name="connect-to-data"></a>Tietoihin yhdistäminen

**Power BI Desktopin** avulla voit yhdistää moniin erityyppisiin tietoihin. Voit muodostaa yhteyden perustietolähteisiin, kuten Microsoft Excel -tiedostoon, tai monenlaisia tietoja sisältäviin verkkopalveluihin, kuten Salesforceen, Microsoft Dynamicsiin, Azure Blob -säilöön ja moniin muihin. 

Muodosta yhteys tietoihin valitsemalla **Aloitus**-valintanauhassa **Nouda tiedot**.

![Nouda tiedot](media/desktop-quickstart-connect-to-data/qs-connect-data_02.png)

**Nouda tiedot** -ikkuna aukeaa. Ikkunassa voit valita monista eri tietolähteistä, joihin **Power BI Desktop** pystyy muodostamaan yhteyden. Tässä pikaoppaassa käytämme lataamaasi Excel-työkirjaa, joka kuvailtiin tämän artikkelin alussa olevassa *Edellytykset*-osiossa. 

![Nouda tiedot](media/desktop-quickstart-connect-to-data/qs-connect-data_03.png)

Koska tämä on Excel-tiedosto, valitse **Nouda tiedot** -ikkunasta **Excel** ja valitse sitten **Yhdistä**-painike.

Sinua pyydetään antamaan Excel-tiedoston sijainti, jotta siihen voidaan muodostaa yhteys. Ladatun tiedoston nimi on *Rahoitusmalli*. Valitse kyseinen tiedosto ja valitse sitten **Avaa**.

![Nouda tiedot](media/desktop-quickstart-connect-to-data/qs-connect-data_04.png)

**Power BI Desktop** lataa työkirjan ja lukee sen sisällön ja näyttää sitten tiedostossa käytettävissä olevat tiedot **Siirtymistoiminta**-ikkunassa, jossa voit valita, mitä tietoja haluat ladata Power BI Desktopiin. Valitse taulukot merkitsemällä valintaruutu jokaisen tuotavan taulukon vieressä. Tässä tapauksessa tuomme molemmat käytettävissä olevat taulukot.

![Nouda tiedot](media/desktop-quickstart-connect-to-data/qs-connect-data_05.png)

Kun olet tehnyt valintasi, valitse **Lataa** tietojen tuomiseksi Power BI Desktopiin.

## <a name="view-data-in-the-fields-pane"></a>Näytä tiedot Kentät-ruudussa

Kun olet ladannut taulukot, tiedot näkyvät **Kentät**-ruudussa. Voit laajentaa kunkin taulukon valitsemalla sen nimen vieressä olevan kolmion. Seuraavassa kuvassa *rahoitus*-taulukko on laajennettu ja sen kentät ovat näkyvissä. 

![Nouda tiedot](media/desktop-quickstart-connect-to-data/qs-connect-data_06.png)

Siinä kaikki. Olet muodostanut yhteyden tietoihin **Power BI Desktopissa** ja ladannut ne, ja nyt voit nähdä kaikki kyseisissä taulukoissa käytettävissä olevat kentät.


## <a name="next-steps"></a>Seuraavat vaiheet
Kun olet muodostanut yhteyden tietoihin, voit tehdä **Power BI Desktopilla** monia asioita, kuten luoda visualisointeja ja raportteja. Lisätietoja saat seuraavista resursseista:

* [Power BI Desktopin aloitusopas](desktop-getting-started.md)

