---
title: Power BI:n tukemat merkityksellisten tietojen tyypit
description: Nopeat merkitykselliset tiedot ja Näytä merkitykselliset tiedot Power BI:llä.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: eabe72a2aa44c87bed4ebc3f4c9ac65678dd4774
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280216"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Power BI:n tukemat merkityksellisten tietojen tyypit
## <a name="how-does-insights-work"></a>Merkityksellisten tietojen toiminta
Power BI hakee nopeasti tietojoukosta erilaisia alijoukkoja ja hyödyntää kehittyneitä algoritmeja, joiden avulla se pyrkii tunnistamaan mahdollisesti merkityksellisiä tietoja. Power BI tarkistaa niin suuren osan tietojoukosta kuin mahdollista määritetyn ajan sisällä.

Voit verrata merkityksellisiä tietoja tietojoukkoon tai koontinäytön ruutuun.   

## <a name="what-types-of-insights-can-we-find"></a>Minkälaisia merkityksellisiä tietoja on olemassa?
Seuraavana muutamia käyttämiämme algoritmeja:

## <a name="category-outliers-topbottom"></a>Luokan poikkeavat havainnot (ylä/ala)
Korostaa tapaukset, joissa mallin mittayksikössä yhdellä tai kahdella dimension jäsenellä on paljon suuremmat arvot kuin muilla dimension jäsenillä.  

![Esimerkki luokan poikkeavista havainnoista](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Aikasarjan muutospisteet
Korostaa kohdat, joissa tietojen aikasarjan trendeissä on merkittäviä muutoksia.

![Esimerkki aikasarjan muutospisteistä](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Korrelaatio
Havaitsee tilanteet, joissa usea mittayksikkö osoittaa keskinäistä korrelaatiota, kun niitä verrataan tietojoukon dimensioon.

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

Jos omistat tietojoukon, [optimoi se merkityksellisiä tietoja varten](../service-insights-optimize.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

