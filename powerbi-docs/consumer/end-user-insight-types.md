---
title: Power BI:n tukemat merkityksellisten tietojen tyypit
description: Nopeat merkitykselliset tiedot ja Näytä merkitykselliset tiedot Power BI:llä.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/31/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 75462c2414854d0848254a36b89bcdd1de365ec5
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73863478"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Power BI:n tukemat merkityksellisten tietojen tyypit

Power BI -palvelu voi automaattisesti etsiä merkityksellisiä tietoja koontinäytöistä tai raporteista.

## <a name="how-does-insights-work"></a>Merkityksellisten tietojen toiminta
Power BI tekee nopeasti hakuja tietojoukkojesi eri alijoukoista. Haun aikana Power BI käyttää joukkoa kehittyneitä algoritmeja, jotka löytävät mahdollisesti kiinnostavia merkityksellisiä tietoja. Power BI tarkistaa niin suuren osan tietojoukosta kuin mahdollista määritetyn ajan sisällä.

Voit verrata merkityksellisiä tietoja tietojoukkoon tai koontinäytön ruutuun.   

## <a name="what-types-of-insights-can-we-find"></a>Minkälaisia merkityksellisiä tietoja on olemassa?
Seuraavana muutamia käyttämiämme algoritmeja:

## <a name="category-outliers-topbottom"></a>Luokan poikkeavat havainnot (ylä/ala)
Korostaa tapaukset, joissa mallin mittarissa yhdellä tai kahdella dimension jäsenellä on paljon suuremmat arvot kuin muilla dimension jäsenillä.  

![Esimerkki luokan poikkeavista havainnoista](./media/end-user-insight-types/pbi-auto-insight-types-category-outliers.png)

## <a name="change-points-in-a-time-series"></a>Aikasarjan muutospisteet
Korostaa kohdat, joissa tietojen aikasarjan trendeissä on merkittäviä muutoksia.

![Esimerkki aikasarjan muutospisteistä](./media/end-user-insight-types/pbi-auto-insight-types-changepoint.png)

## <a name="correlation"></a>Korrelaatio
Havaitsee tilanteet, joissa usea mittari osoittaa keskinäistä korrelaatiota, kun niitä verrataan tietojoukon dimensioon.

![Esimerkki korrelaatiosta](./media/end-user-insight-types/pbi-auto-insight-types-correlation.png)

## <a name="low-variance"></a>Pieni varianssi
Havaitsee tapaukset, jossa arvopisteet eivät eroa keskiarvosta huomattavasti.

![Esimerkki pienestä varianssista](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Enemmistö (päätekijät)
Etsii tapauksia, jossa kokonaisarvon enemmistön voidaan katsoa johtuneen yhdestä tekijästä, kun se jaetaan toisella dimensiolla.  

![Esimerkki päätekijöistä](./media/end-user-insight-types/pbi-auto-insight-types-majority.png)

## <a name="overall-trends-in-time-series"></a>Aikasarjan yleiset trendit
Havaitsee ylöspäin ja alaspäin suuntautuvat trendit aikasarjatiedoissa.

![Esimerkki aikasarjan yleisistä trendeistä](./media/end-user-insight-types/pbi-auto-insight-types-trend.png)

## <a name="seasonality-in-time-series"></a>Kausivaihtelu aikasarjassa
Etsii toistuvia kuvioita aikasarjatiedoissa, kuten viikoittaista, kuukausittaista tai vuosittaista kausivaihtelua.

![Esimerkki kausivaihtelusta](./media/end-user-insight-types/pbi-auto-insight-types-seasonality-new.png)

## <a name="steady-share"></a>Vakaa jako
Korostaa tapaukset, joissa on olemassa pääkohde-alikohde-korrelaatio alikohteen osuudessa suhteessa pääkohteen yleisarvoon jatkuvassa muuttujassa.

![Esimerkki vakaasta jaosta](./media/end-user-insight-types/pbi-auto-insight-types-steadyshare.png)

## <a name="time-series-outliers"></a>Aikasarjan poikkeavat havainnot
Tunnistaa aikasarjan tiedoissa erityiset päivämäärät tai ajat, joiden arvot eroavat huomattavasti muista päivä-/aika-arvoista.

![Esimerkki aikasarjan poikkeavista havainnoista](./media/end-user-insight-types/pbi-auto-insight-types-time-series-outliers.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n merkitykselliset tiedot](end-user-insights.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

