---
title: Power BI:n tukemat merkityksellisten tietojen tyypit
description: Nopeat merkitykselliset tiedot ja Näytä merkitykselliset tiedot Power BI:llä.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 4870fac504f36600c13af49c5798d896eeb59261
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79113156"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Power BI:n tukemat merkityksellisten tietojen tyypit

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

Power BI voi etsiä tiedoistasi mielenkiintoisia trendejä ja malleja. Nämä trendit ja mallit esitetään *merkityksellisiksi tiedoiksi* kutsuttujen visualisointien muodossa. 

Jos haluat lisätietoja merkityksellisten tietojen käyttämisestä, katso [Power BI:n merkitykselliset tiedot](end-user-insights.md)

![merkityksellisiä tietoja](media/end-user-insight-types/power-bi-insight.png)

## <a name="how-does-insights-work"></a>Merkityksellisten tietojen toiminta
Power BI tekee nopeasti hakuja tietojoukkojesi eri alijoukoista. Haun aikana Power BI käyttää joukkoa kehittyneitä algoritmeja, jotka löytävät mahdollisesti kiinnostavia merkityksellisiä tietoja. Power BI:n *käyttäjät* voivat suorittaa merkityksellisiä tietoja koontinäytön ruuduille.

## <a name="some-terminology"></a>Terminologia
Power BI käyttää tilastollisia algoritmeja merkityksellisten tietojen tunnistamiseen. Algoritmit luetellaan ja kuvataan tämän artikkelin seuraavassa osiossa. Ennen kuin käsittelemme algoritmeja, selitämme muutamia termejä, jotka saattavat olla sinulle vieraita. 

* **Mittari** – mittari on määrällinen (numeromuotoinen) kenttä, jota voidaan käyttää laskutoimituksissa. Tavallisia laskutoimituksia ovat summa, keskiarvo ja minimi. Jos yrityksemme esimerkiksi valmistaa ja myy rullalautoja, mittarimme voivat olla myytyjen rullalautojen lukumäärä ja keskimääräinen vuosivoitto.  
* **Dimensio** – dimensiot ovat kategorista (teksti-) tietoa. Dimensio kuvaa henkilöä, objektia, kohdetta, tuotteita, paikkaa ja aikaa. Tietojoukossa dimensiot ovat tapa ryhmitellä *mittarit* hyödyllisiin luokkiin. Rullalautayrityksessämme dimensiot voivat tarkoittaa myynnin (joka on mittari) tarkastelua mallin, värin, maan tai markkinointikampanjan mukaan.   
* **Korrelaatio** – korrelaatio kertoo meille, miten asioiden käyttäytyminen liittyy toisiin asioihin.  Jos niiden kasvun tai vähenemisen mallit ovat samanlaiset, ne korreloivat positiivisesti. Jos taas niiden muutossuunnat ovat vastakkaiset, ne korreloivat negatiivisesti. Jos esimerkiksi punaisten rullalautojen myynti kasvaa aina televisiomarkkinointikampanjan myötä, punaisten rullalautojen myynnin ja televisiokampanjan välillä on positiivinen korrelaatio.
* **Aikasarja** – aikasarja on tapa näyttää aika peräkkäisinä arvopisteinä. Nämä arvopisteet voivat olla esimerkiksi sekunteja, tunteja, kuukausia tai vuosia.  
* **Jatkuva muuttuja** – jatkuva muuttuja voi olla mikä tahansa arvo minimi- ja maksimirajan välillä, muuten kyseessä on diskreetti muuttuja. Esimerkkejä ovat lämpötila, paino, ikä ja aika. Jatkuviin muuttujiin voi sisältyä arvon osia tai murto-osia. Myytyjen sinisten rullalautojen kokonaismäärä on diskreetti muuttuja, koska emme voi myydä rullalaudan puolikasta.  

## <a name="what-types-of-insights-can-you-find"></a>Minkälaisia merkityksellisiä tietoja on olemassa?
Power BI käyttää seuraavia algoritmeja. 

### <a name="category-outliers-topbottom"></a>Luokan poikkeavat havainnot (ylä/ala)
Korostaa tapaukset, joissa yhdellä tai kahdella luokalla on paljon suuremmat arvot kuin muilla luokilla.  

![Esimerkki luokan poikkeavista havainnoista](./media/end-user-insight-types/pbi-auto-insight-types-category-outliers.png)

### <a name="change-points-in-a-time-series"></a>Aikasarjan muutospisteet
Korostaa kohdat, joissa tietojen aikasarjan trendeissä on merkittäviä muutoksia.

![Esimerkki aikasarjan muutospisteistä](./media/end-user-insight-types/pbi-auto-insight-types-changepoint.png)

### <a name="correlation"></a>Korrelaatio
Havaitsee tapaukset, joissa useat mittarit osoittavat samanlaisen mallin tai trendin, kun niitä verrataan tietojoukon luokkaan tai arvoon.

![Esimerkki korrelaatiosta](./media/end-user-insight-types/pbi-auto-insight-types-correlation.png)

### <a name="low-variance"></a>Pieni varianssi
Havaitsee tapaukset, joissa dimension arvopisteet eivät ole kaukana keskiarvosta, eli varianssi on pieni. Oletetaan, että sinulla on dimensio ”Myynti” ja dimensio ”alue”. Kun tarkastelet alueita, huomaat, että arvopisteiden ja (arvopisteiden) keskiarvon välillä on hyvin vähän eroa. Merkityksellinen tieto käynnistyy, kun myynnin varianssi kaikilla alueilla alittaa kynnysarvon. Tällöin myynti on siis melko samankaltaista kaikilla alueilla.

![Esimerkki pienestä varianssista](./media/end-user-insight-types/power-bi-low-variance.png)

### <a name="majority-major-factors"></a>Enemmistö (päätekijät)
Etsii tapauksia, jossa kokonaisarvon enemmistön voidaan katsoa johtuneen yhdestä tekijästä, kun se jaetaan toisella dimensiolla.  

![Esimerkki päätekijöistä](./media/end-user-insight-types/pbi-auto-insight-types-majority.png)

### <a name="overall-trends-in-time-series"></a>Aikasarjan yleiset trendit
Havaitsee ylöspäin ja alaspäin suuntautuvat trendit aikasarjatiedoissa.

![Esimerkki aikasarjan yleisistä trendeistä](./media/end-user-insight-types/pbi-auto-insight-types-trend.png)

### <a name="seasonality-in-time-series"></a>Kausivaihtelu aikasarjassa
Etsii toistuvia kuvioita aikasarjatiedoissa, kuten viikoittaista, kuukausittaista tai vuosittaista kausivaihtelua.

![Esimerkki kausivaihtelusta](./media/end-user-insight-types/pbi-auto-insight-types-seasonality-new.png)

### <a name="steady-share"></a>Vakaa jako
Korostaa tapaukset, joissa on olemassa pääkohde-alikohde-korrelaatio alikohteen osuudessa suhteessa pääkohteen yleisarvoon jatkuvassa muuttujassa. Vakaan jaon merkitykselliset tiedot koskevat mittayksikön, dimension ja toisen päivämäärä/aika-dimension kontekstia. Tämä merkityksellinen tieto käynnistyy, kun tietyllä dimension arvolla, esimerkiksi Koillisalue-arvolla, on vakaa prosenttiosuus kokonaismyynnistä kyseisessä päivämäärä-/aikadimensiossa.

Vakaan jaon merkityksellinen tieto muistuttaa pienen varianssin merkityksellistä tietoa, koska ne molemmat liittyvät arvon varianssin puutteeseen tietyllä aikavälillä. Vakaan jaon merkitykselliset tiedot mittaavat kuitenkin varianssin puutetta **prosenttiosuudessa kokonaisuudesta** tietyllä aikavälillä, kun taas pienen varianssin merkitykselliset tiedot mittaavat varianssin puutetta absoluuttisissa mittausarvoissa tietyssä dimensiossa.

![Esimerkki vakaasta jaosta](./media/end-user-insight-types/pbi-auto-insight-types-steadyshare.png)

### <a name="time-series-outliers"></a>Aikasarjan poikkeavat havainnot
Tunnistaa aikasarjan tiedoissa erityiset päivämäärät tai ajat, joiden arvot eroavat huomattavasti muista päivä-/aika-arvoista.

![Esimerkki aikasarjan poikkeavista havainnoista](./media/end-user-insight-types/pbi-auto-insight-types-time-series-outliers.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n merkitykselliset tiedot](end-user-insights.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

