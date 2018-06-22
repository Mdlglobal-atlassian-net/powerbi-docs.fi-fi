---
title: Tuo tietoja verkkosivulta esimerkin avulla Power BI Desktopissa (esikatselu)
description: Tuo tietoja verkkosivulta antamalla esimerkki siitä mitä haluat tuoda
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 55c1a70e054b6bb6ff06c7fe6f83b58d8b1f26f3
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290978"
---
# <a name="get-data-from-a-web-page-by-providing-an-example-preview"></a>Tuo tietoja verkkosivulta antamalla esimerkki (esikatselu)

Tietojen tuominen verkkosivulta antaa käyttäjien tuoda tietoja helposti verkkosivuilta **Power BI Desktopiin**. Usein kuitenkin verkkosivujen tiedot eivät ole selkeissä taulukoissa, jotka on helppo tuoda, joten tietojen tuominen tällaisilta sivuilta saattaa olla haastavaa, vaikka tiedot olisivatkin jäsenneltyjä ja yhtenäisiä. 

Ongelmaan on ratkaisu. Toiminnon **Tuo esimerkin mukaisia tietoja verkosta** avulla voit näyttää **Power BI Desktopille** mitä tietoja haluat tuoda antamalla yhden tai useampia esimerkkejä yhdistin-dialogissa, jolloin se etsii sivuston muut esimerkkejäsi vastaavat tiedot. Tämän ratkaisun avulla voit tuoda verkkosivuilta kaikenlaisia tietoja, mukaan lukien sekä *taulukoissa* että taulukoiden ulkopuolella olevia tietoja. 

![Tuo esimerkin mukaisia tietoja](media/desktop-connect-to-web-by-example/web-by-example_01.png)


## <a name="enabling-the-preview-feature-get-data-from-web-by-example"></a>Tuo esimerkin mukaisia tietoja -toiminnon esikatseluominaisuuden ottaminen käyttöön

**Tuo esimerkin mukaisia tietoja verkosta**-visualisointi on esikatseluvaiheessa. Sen täytyy olla käytössä **Power BI Desktopissa**. Jos haluat ottaa sen käyttöön, valitse **Tiedosto > Asetukset ja vaihtoehdot > Asetukset > Esiversio-ominaisuudet** ja valitse sitten kohta **Uusi kokemus verkosta**. Sinun täytyy käynnistää Power BI Desktop uudelleen tämän jälkeen.

![ota esikatseluominaisuus käyttöön](media/desktop-connect-to-web-by-example/web-by-example_02.png)

Kun esikatseluominaisuus on otettu käyttöön, voit aloittaa sen käyttämisen. 

## <a name="using-get-data-from-web-by-example"></a>Toiminnon Tuo esimerkin mukaisia tietoja käyttäminen

Käyttääksesi **Tuo esimerkin mukaisia tietoja verkosta** -toimintoa käyttääksesi valitse **Nouda tiedot** **Aloitus**-valintanauhasta. Ikkunan avauduttua valitse **Muut** vasemmassa ruudussa olevista kategorioista ja valitse sitten**Verkko**.

![valitse Verkko kohdassa Nouda tiedot](media/desktop-connect-to-web-by-example/web-by-example_03.png)

Syötä sitten sen verkkosivun URL-osoite, jolta haluat tuoda tietoja. Tässä artikkelissa käytämme Microsoft Store -verkkosivua ja näytämme miten tämä yhdistin toimii. 

Jos haluat edetä mukana, voit käyttää [Microsoft Storen URL-osoitetta](https://www.microsoft.com/en-us/store/top-paid/games/xbox?category=classics), jota käytämme artikkelissa:

    https://www.microsoft.com/en-us/store/top-paid/games/xbox?category=classics

![verkkodialogi](media/desktop-connect-to-web-by-example/web-by-example_04.png)

Kun valitset **OK**, sinut viedään **Siirtymistoiminnon** dialogiin, jossa esitetään verkkosivulta mahdollisesti automaattisesti havaitut taulukot. Kuten alla näkyvässä kuvassa on esitetty, taulukoita ei löytynyt, mutta sivun alaosassa on painike **Poimi taulukko käyttäen esimerkkejä**, jolla voit antaa esimerkkejä.


![Siirtymistoimintoikkuna](media/desktop-connect-to-web-by-example/web-by-example_05.png)

**Poimi taulukko käyttäen esimerkkejä** avaa interaktiivisen ikkunan, jossa voit esikatsella verkkosivun sisältöä ja syöttää esimerkkiarvoja tiedoista, jotka haluat tuoda. 

Tässä esimerkissä tuomme kunkin sivustolla olevan pelin *Nimen* ja *Hinnan*. Voimme tehdä niin antamalla pari esimerkkiä sivulta kussakin sarakkeessa, kuten seuraavassa kuvassa on esitetty. Kuten syötetyissä esimerkeissä, **Power Query** (joka on varsinainen teknologia, joka poimii tiedot verkkosivulta) pystyy tuomaan tiedot, jotka vastaavat esimerkkien antamaa mallia älykkäitä tietojenpoiminta-algoritmeja käyttämällä.

![esimerkkien mukaiset tiedot](media/desktop-connect-to-web-by-example/web-by-example_06.png)

Kun olemme tyytyväisiä verkkosivulta poimittuihin tietoihin, valitsemme **OK** siirtyäksemme **Kyselyeditoriin**, jossa voimme soveltaa muita muutoksia tai muokata tietoja, kuten yhdistää nämä tiedot muista lähteistä peräisin oleviin tietoihin.

![esimerkkien mukaiset tiedot](media/desktop-connect-to-web-by-example/web-by-example_07.png)

Sitten voit luoda visualisointeja tai käyttää muuten verkkosivun tietoja luodessasi **Power BI Desktop** -raportteja.


## <a name="next-steps"></a>Seuraavat vaiheet
**Power BI Desktopin** avulla voit muodostaa yhteyden hyvin monenlaisiin tietoihin. Lisätietoja näistä tietolähteistä saat seuraavista resursseista:

* [Lisää sarake esimerkin mukaan](desktop-add-column-from-example.md)
* [Yhdistä verkkosivuun](desktop-connect-to-web.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yhteyden muodostaminen Excel-työkirjoihin Power BI Desktopissa](desktop-connect-excel.md)   
* [CSV-tiedostoihin yhdistäminen Power BI Desktopissa](desktop-connect-csv.md)   
* [Tietojen antaminen suoraan Power BI Desktopiin](desktop-enter-data-directly-into-desktop.md)   
