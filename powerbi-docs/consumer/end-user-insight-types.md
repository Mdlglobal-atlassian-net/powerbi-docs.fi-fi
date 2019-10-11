---
title: Power BI:n tukemat merkityksellisten tietojen tyypit
description: Nopeat merkitykselliset tiedot ja Näytä merkitykselliset tiedot Power BI:llä.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/2/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 507d49ba6cdb894667bf66f8f35c5c325b9ff25e
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2019
ms.locfileid: "71943913"
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

![Esimerkki luokan poikkeavista havainnoista](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Aikasarjan muutospisteet
Korostaa kohdat, joissa tietojen aikasarjan trendeissä on merkittäviä muutoksia.

![Esimerkki aikasarjan muutospisteistä](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Korrelaatio
Havaitsee tilanteet, joissa usea mittari osoittaa keskinäistä korrelaatiota, kun niitä verrataan tietojoukon dimensioon.

![Esimerkki korrelaatiosta](./media/end-user-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Pieni varianssi
Havaitsee tapaukset, jossa arvopisteet eivät eroa keskiarvosta huomattavasti.

![Esimerkki pienestä varianssista](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Enemmistö (päätekijät)
Etsii tapauksia, jossa kokonaisarvon enemmistön voidaan katsoa johtuneen yhdestä tekijästä, kun se jaetaan toisella dimensiolla.  

![Esimerkki päätekijöistä](./media/end-user-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Aikasarjan yleiset trendit
Havaitsee ylöspäin ja alaspäin suuntautuvat trendit aikasarjatiedoissa.

![Esimerkki aikasarjan yleisistä trendeistä](./media/end-user-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Kausivaihtelu aikasarjassa
Etsii toistuvia kuvioita aikasarjatiedoissa, kuten viikoittaista, kuukausittaista tai vuosittaista kausivaihtelua.

![Esimerkki kausivaihtelusta](./media/end-user-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Vakaa jako
Korostaa tapaukset, joissa on olemassa pääkohde-alikohde-korrelaatio alikohteen osuudessa suhteessa pääkohteen yleisarvoon jatkuvassa muuttujassa.

![Esimerkki vakaasta jaosta](./media/end-user-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Aikasarjan poikkeavat havainnot
Tunnistaa aikasarjan tiedoissa erityiset päivämäärät tai ajat, joiden arvot eroavat huomattavasti muista päivä-/aika-arvoista.

![Esimerkki aikasarjan poikkeavista havainnoista](./media/end-user-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n merkitykselliset tiedot](end-user-insights.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

