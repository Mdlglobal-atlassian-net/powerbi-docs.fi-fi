---
title: Power BI:n tukemat merkityksellisten tietojen tyypit
description: Nopeat merkitykselliset tiedot ja Näytä merkitykselliset tiedot Power BI:llä.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 44b59019f1955258716e23fb2dd55182134cc6a2
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34250593"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Power BI:n tukemat merkityksellisten tietojen tyypit
## <a name="how-does-insights-work"></a>Merkityksellisten tietojen toiminta
Power BI hakee nopeasti tietojoukosta erilaisia alijoukkoja ja hyödyntää kehittyneitä algoritmeja, joiden avulla se pyrkii tunnistamaan mahdollisesti merkityksellisiä tietoja. Power BI tarkistaa niin suuren osan tietojoukosta kuin mahdollista määritetyn ajan sisällä.

Voit verrata merkityksellisiä tietoja tietojoukkoon tai koontinäytön ruutuun.   

## <a name="what-types-of-insights-can-we-find"></a>Minkälaisia merkityksellisiä tietoja on olemassa?
Seuraavana muutamia käyttämiämme algoritmeja:

## <a name="category-outliers-topbottom"></a>Luokan poikkeavat havainnot (ylä/ala)
Korostaa tapaukset, joissa mallin mittayksikössä yhdellä tai kahdella dimension jäsenellä on paljon suuremmat arvot kuin muilla dimension jäsenillä.  

![Esimerkki luokan poikkeavista havainnoista](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Aikasarjan muutospisteet
Korostaa kohdat, joissa tietojen aikasarjan trendeissä on merkittäviä muutoksia.

![Esimerkki aikasarjan muutospisteistä](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Korrelaatio
Havaitsee tilanteet, joissa usea mittayksikkö osoittaa keskinäistä korrelaatiota, kun niitä verrataan tietojoukon dimensioon.

![Esimerkki korrelaatiosta](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Pieni varianssi
Havaitsee tapaukset, jossa arvopisteet eivät eroa keskiarvosta huomattavasti.

![Esimerkki pienestä varianssista](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Enemmistö (päätekijät)
Etsii tapauksia, jossa kokonaisarvon enemmistön voidaan katsoa johtuneen yhdestä tekijästä, kun se jaetaan toisella dimensiolla.  

![Esimerkki päätekijöistä](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Aikasarjan yleiset trendit
Havaitsee ylöspäin ja alaspäin suuntautuvat trendit aikasarjatiedoissa.

![Esimerkki aikasarjan yleisistä trendeistä](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Kausivaihtelu aikasarjassa
Etsii toistuvia kuvioita aikasarjatiedoissa, kuten viikoittaista, kuukausittaista tai vuosittaista kausivaihtelua.

![Esimerkki kausivaihtelusta](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Vakaa jako
Korostaa tapaukset, joissa on olemassa pääkohde-alikohde-korrelaatio alikohteen osuudessa suhteessa pääkohteen yleisarvoon jatkuvassa muuttujassa.

![Esimerkki vakaasta jaosta](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Aikasarjan poikkeavat havainnot
Tunnistaa aikasarjan tiedoissa erityiset päivämäärät tai ajat, joiden arvot eroavat huomattavasti muista päivä-/aika-arvoista.

![Esimerkki aikasarjan poikkeavista havainnoista](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n merkitykselliset tiedot](service-insights.md)

Jos omistat tietojoukon, [optimoi se merkityksellisiä tietoja varten](service-insights-optimize.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

