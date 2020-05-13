---
title: 'Pikaopas: tietoihin yhdistäminen Power BI Desktopissa'
description: Ohjeet Power BI Desktopin käytettävissä oleviin tietolähteisiin yhdistämiseen
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: quickstart
ms.date: 01/10/2020
ms.author: davidi
LocalizationGroup: quickstart
ms.openlocfilehash: d689258b4e4da5349d57b41f72d4266eb759029b
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348593"
---
# <a name="quickstart-connect-to-data-in-power-bi-desktop"></a>Pikaopas: Tietoihin yhdistäminen Power BI Desktopissa

Tässä pikaoppaassa muodostat yhteyden tietoihin Power BI Desktopin avulla. Tämä on ensimmäinen vaihe tietomallien ja raporttien luomiseen.

![Power BI Desktop](media/desktop-what-is-desktop/what-is-desktop_01.png)

Jos et ole rekisteröitynyt Power BI:hin, [rekisteröidy ilmaiseen kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

Tarvitset seuraavat resurssit, jotta voit suorittaa tämän artikkelin vaiheet:

* Lataa ja asenna Power BI Desktop, joka on ilmainen paikallisessa tietokoneessa suoritettava sovellus. Voit [ladata Power BI Desktopin](https://powerbi.microsoft.com/desktop) suoraan tai hakea sen [Microsoft Storesta](https://aka.ms/pbidesktopstore).
* [Lataa tämä Excel-mallityökirja](https://go.microsoft.com/fwlink/?LinkID=521962) ja luo kansio nimeltä *C:\PBID-qs*, johon tallennat kyseisen Excel-tiedoston. Tämän pikaoppaan myöhemmissä vaiheissa oletetaan, että ladattu Excel-työkirja sijaitsee kyseisessä paikassa.
* Power BI Desktopin monet tietoliittimet edellyttävät todentamista Internet Explorer 10:llä (tai tätä uudemmalla versiolla).

## <a name="launch-power-bi-desktop"></a>Käynnistä Power BI Desktop

Kun olet asentanut Power BI Desktopin, käynnistä se paikallisessa tietokoneessa. Näet Power BI -opetusohjelman. Toimi sen ohjeiden mukaisesti tai sulje valintaikkuna ja aloita tyhjällä pohjalla. Pohja on paikka, jossa luot visualisointeja ja raportteja tiedoistasi.

![Power BI Desktop ja tyhjä pohja](media/desktop-quickstart-connect-to-data/qs-connect-data_01.png)

## <a name="connect-to-data"></a>tietoihin yhdistäminen

Power BI Desktopilla voit yhdistää moniin erityyppisiin tietoihin. Voit yhdistää perustietolähteisiin, esimerkiksi Microsoft Excel -tiedostoon. Voit yhdistää monenlaisia tietoja sisältäviin verkkopalveluihin, kuten Salesforceen, Microsoft Dynamicsiin, Azure Blob -säilöön ja moniin muihin.

Muodosta yhteys tietoihin valitsemalla **Aloitus**-valintanauhassa **Nouda tiedot**.

![Valintanauhan Aloitus-välilehden Nouda tiedot -komento](media/desktop-quickstart-connect-to-data/qs-connect-data_02.png)

Näyttöön avautuu **Nouda tiedot**-ikkuna. Ikkunassa voit valita monista eri tietolähteistä, joihin Power BI Desktop voi muodostaa yhteyden. Tässä pikaoppaassa käytetään Excel-työkirjaa, jonka latasit [Edellytykset](#prerequisites)-kohdassa.

![Nouda tiedot kaikista lähteistä](media/desktop-quickstart-connect-to-data/qs-connect-data_03.png)

Koska tämä tietolähde on Excel-tiedosto, valitse **Nouda tiedot** -ikkunassa **Excel** ja valitse sitten **Yhdistä**-painike.

Power BI pyytää sinua antamaan Excel-tiedoston sijainnin, jotta siihen voidaan muodostaa yhteys. Ladatun tiedoston nimi on *Talousmalli*. Valitse kyseinen tiedosto ja valitse sitten **Avaa**.

![Nouda tiedot Talousmalli-tiedostossa](media/desktop-quickstart-connect-to-data/qs-connect-data_04.png)

Power BI Desktop lataa työkirjan ja lukee sen sisällön ja näyttää sitten tiedostossa käytettävissä olevat tiedot **siirtymistoiminnon** ikkunassa. Siinä voit valita, mitä tietoja haluat ladata Power BI Desktopiin. Valitse haluamasi taulukot valitsemalla valintaruutu jokaisen tuotavan taulukon vieressä. Tuo molemmat käytettävissä olevat taulukot.

![Tietojen valitseminen siirtymistoimintoikkunassa](media/desktop-quickstart-connect-to-data/qs-connect-data_05.png)

Kun olet tehnyt valintasi, valitse **Lataa** tietojen tuomiseksi Power BI Desktopiin.

## <a name="view-data-in-the-fields-pane"></a>Näytä tiedot Kentät-ruudussa

Kun olet ladannut taulukot, tiedot näkyvät **Kentät**-ruudussa. Voit laajentaa kunkin taulukon valitsemalla sen nimen vieressä olevan nuolen. Seuraavassa kuvassa *rahoitus*-taulukko on laajennettu ja sen kentät ovat näkyvissä.

![Nouda tiedot](media/desktop-quickstart-connect-to-data/qs-connect-data_06.png)

Siinä kaikki. Olet muodostanut yhteyden tietoihin Power BI Desktopissa ja ladannut ne, joten näet nyt kaikki kyseisissä taulukoissa käytettävissä olevat kentät.

## <a name="next-steps"></a>Seuraavat vaiheet

Kun olet muodostanut yhteyden tietoihin, voit tehdä Power BI Desktopilla monia asioita. Voit esimerkiksi luoda visualisointeja ja raportteja. Lisätietoja saat seuraavista resursseista:

* [Power BI Desktopin käytön aloittaminen](../fundamentals/desktop-getting-started.md)
