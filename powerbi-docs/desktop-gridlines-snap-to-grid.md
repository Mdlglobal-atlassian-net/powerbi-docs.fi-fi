---
title: Ruudukon ja Kohdista ruudukkoon -toiminnon käyttö Power BI Desktop -raporteissa
description: Käytä ruudukkoa, Kohdista ruudukkoon, Z-järjestys, tasaus ja jakelu Power BI Desktop-raporteissa
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1b6b1a3ecda7d3f827975da8fcfec5d9d5b67023
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973782"
---
# <a name="use-gridlines-and-snap-to-grid-in-power-bi-desktop-reports"></a>Ruudukon ja Kohdista ruudukkoon -toiminnon käyttö Power BI Desktop -raporteissa
**Power BI Desktop** -raportin pohja sisältää ruudukoita, joiden avulla voit siististi tasata raporttisivun visualisoinnit. Se sisältää myös Kohdista ruudukkoon -toiminnon, jolloin visualisoinnit näyttävät siisteiltä, ovat tasattuja ja tasaisin välein.

**Power BI Desktopissa** voit myös säätää raportin objektien z-järjestystä (Siirrä eteenpäin, Lähetä taaksepäin) sekä tasata tai jakaa tasaisesti valittuja visualisointeja pohjalla.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_0.png)

### <a name="enabling-gridlines-and-snap-to-grid"></a>Ruudukoiden ja ruudukkoon kohdistamisen käyttöönotto
Ota ruudukot käyttöön- ja Kohdista ruudukkoon -toiminnoissa valitaan **Näkymä**-valintanauha ja sitten valintaruudut toiminnoille **Näytä ruudukko** ja **Kohdista ruudukkoon.** Voit valita toisen tai molemmat ruudut, sillä ne toimivat itsenäisesti.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_1.png)

> [!NOTE]
> Jos **Näytä ruudukko** ja **Kohdista ruudukkoon** on poistettu käytöstä, muodosta yhteys mihin tahansa tietolähteeseen, jolloin ne tulevat käyttöön.
> 
> 

### <a name="using-gridlines"></a>Ruudukon viivojen käyttö
Ruudukot ovat visuaalisia oppaita, joiden avulla voit nähdä, onko kaksi tai useampi visualisointi tasattu oikein. Kun yrität määrittää, onko (vähintään kaksi) visualisointia tasattu vaakasuunnassa tai pystysuunnassa, käytä ruudukkoa määrittämään, onko reunat tasattu.

Voit valita komennolla *CTRL + napsautus* useamman kuin yhden visualisoinnin kerrallaan. Tällöin näet kaikkien valittujen visualisointien reunat, jolloin näet helposti, onko visualisoinnit tasattu oikein.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_2.png)

#### <a name="using-gridlines-inside-visuals"></a>Ruudukon käyttö visualisointien sisällä
Power BI:ssa visualisointien sisällä on myös ruudukkoja, jotka antavat visuaaliset ohjeet arvopisteiden ja arvojen vertailuun. Syyskuun 2017 versiosta alkaen **Power BI Desktop** mahdollistaa nyt ruudukoiden hallinnan visualisointien sisällä käyttämällä **X-akselin** tai **Y-akselin** korttia (soveltuvin osin visuaalisen tyypin perusteella), joka löytyy **Muoto**-osasta **Visualisoinnit**-ruudusta. Voit hallita ruudukon seuraavia elementtejä visualisoinnin sisällä:

* Ruudukon ottaminen käyttöön ja käytöstä poistaminen
* Ruudukon värin muuttaminen
* Ruudukon viivojen (leveys) säätäminen
* Valitse visualisoinnin ruudukon viivan tyyli, esimerkiksi yhtenäinen viiva, katkoviiva tai pisteviiva

Ruudukon tiettyjen elementtien muokkaaminen voi olla erityisen hyödyllistä raporteissa, joissa visualisointeihin käytetään tummia taustoja. Seuraavassa kuvassa näkyy *Ruudukot*-osion **X-akselin** kortti.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_9.png)

### <a name="using-snap-to-grid"></a>Ruudukkoon kohdistamisen käyttö
Kun otat käyttöön **Kohdista ruudukkoon**, kaikki visualisoinnit **Power BI Desktop** -pohjalla, joka siirrät (tai joiden kokoa muutat) tasataan automaattisesti lähimmälle ruudukon akselille, jolloin on paljon helpompaa varmistaa, että kaksi tai useampi visualisointi tasataan samaan vaaka- tai pystysijaintiin tai kokoon.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_3.png)

Muuta ei tarvitsekaan tehdä **Ruudukon** ja **Kohdista ruudukkoon** -toiminnon käyttämiseksi, jotta voidaan varmistaa, että raporttien visualisoinnit on tasattu siististi.

### <a name="using-z-order-align-and-distribute"></a>Z-järjestyksen, tasauksen ja jakelun käyttö
Voit myös hallita raportin visualisoinnin järjestystä, jota kutsutaan usein elementtien *z-järjestykseksi*. Näin voit asettaa visualisoinnit päällekkäin haluamallasi tavalla ja sitten muuttaa kunkin visualisoinnin järjestystä edestä taakse. Tämä järjestys tehdään käyttämällä **Tuo eteenpäin**- ja **Lähetä taaksepäin** -painikkeita, jotka löytyvät **Järjestä** osan **Muoto**-valintanauhasta. Se tulee esiin heti, kun valitset yhden tai useamman visualisoinnin sivulla (se ei ole käytettävissä, jos visualisointia ei ole valittuna).

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_4.png)

**Muoto**-valintanauhasta voit myös tasata visualisointeja monella eri tavalla. Näin voit varmistaa visualisointien näkymisen sivulla tasauksena, joka mielestäsi näyttää hyvältä ja toimii parhaiten.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_5.png)

Kun yksi visualisointi on valittuna, käytä **Tasaa**-painiketta tasaamaan kyseinen visualisointi raporttipohjan reunaan (tai keskelle) seuraavassa kuvassa esitetyllä tavalla.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_6.png)

Kun valittuna on vähintään kaksi visualisointia, ne tasataan yhdessä ja käytetään visualisoinnin aiemmin tasattua reunaa tasaukseen. Jos esimerkiksi valittuna on kaksi visualisointia ja *Tasaa vasemmalle* -painike on valittuna, visualisoinnit tasataan kaikkien valittujen visualisointien äärimmäisenä vasemmalla olevaan reunaan.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_7.png)

Voit myös jakaa visualisoinnit tasaisesti raporttipohjalle joko pysty- tai vaakasuunnassa. Käytä vain **Jakele**-painiketta **Muoto**-valintanauhasta.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_8.png)

Käyttämällä vaikka vain muutamaa valintaa näistä ruudukoiden, tasauksen ja jakelun työkaluista raporttisi näyttävät juuri siltä, miltä haluat.

