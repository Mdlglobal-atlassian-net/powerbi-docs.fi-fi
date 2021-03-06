---
title: Merkityksellisten tietojen luominen automaattisesti Power BI:llä
description: Lue, miten voit saada tietojoukkoja ja koontinäytön ruutuja koskevia katsauksia.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2019
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 4178d9cc5ce6f8e671c0d996bb64ee9a1389acdb
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83306596"
---
# <a name="generate-data-insights-automatically-with-power-bi"></a>Merkityksellisten tietojen luominen automaattisesti Power BI:llä
Etkö tiedä, mistä aloittaisit uuden tietojoukon kanssa?  Tarvitsetko koontinäytön nopeasti?  Haluatko koontitietoja, jotka ovat ehkä jääneet huomaamatta?

Saat nopeita merkityksellisiä tietoja ja voit luoda tietoihin perustuvia mielenkiintoisia, vuorovaikutteisia visualisointeja. Nopeat merkitykselliset tiedot voidaan suorittaa koko tietojoukolle (nopeat tiedot) tai tietylle koontinäytön ruudulle (suodatetut tiedot). Voit suorittaa merkitykselliset tiedot jopa toisiin merkityksellisiin tietoihin!

> [!NOTE]
> Merkitykselliset tiedot eivät toimi DirectQueryllä – ne toimivat vain Power BI:hin ladatuilla tiedoilla.
> 

Merkityksellisiä tietoja -ominaisuus on perustuu kasvavaan [edistyneiden analyysialgoritmien joukkoon](../consumer/end-user-insight-types.md), jota kehitetään yhdessä Microsoft Researchin kanssa. Sen avulla entistä useammat ihmiset voivat saada merkityksellisiä tietoja tiedoistaan uusilla ja intuitiivisilla tavoilla.

## <a name="run-quick-insights-on-a-dataset"></a>Nopeiden merkityksellisten tietojen suorittaminen tietojoukkoon
Katso, kuinka Amanda suorittaa nopeat merkitykselliset tiedot tietojoukkoon, avaa merkityksellisen tiedon tarkastelutilassa, kiinnittää yhden tiedoista ruutuna koontinäytölleen ja hakee sitten merkityksellisiä tietoja koontinäytön ruudusta.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Nyt on sinun vuorosi. Tutustu merkityksellisiin tietoihin [toimittajan laatuanalyysimallin](sample-supplier-quality.md) avulla.

1. Valitse **Tietojoukot**-välilehdeltä **Enemmän vaihtoehtoja** (...) ja valitse sitten **Hanki nopeita merkityksellisiä tietoja**.
   
    ![Tietojoukot-välilehti](media/service-insights/power-bi-ellipses.png)
   
    ![Ellipsivalikko](media/service-insights/power-bi-tab.png)
2. Power BI hakee tietojoukostasi trendejä [erilaisten algoritmien](../consumer/end-user-insight-types.md) avulla.
   
    ![Haetaan merkityksellisiä tietoja -valintaikkuna](media/service-insights/pbi_autoinsightssearching.png)
3. Merkitykselliset tietosi ovat valmiit muutamassa sekunnissa.  Näytä visualisoinnit valitsemalla **Tarkastele merkityksellisiä tietoja**.
   
    ![Onnistumisilmoitus](media/service-insights/pbi_autoinsightsuccess.png)
   
    > [!NOTE]
    > Joistain tietojoukoista ei voi luoda merkityksellisiä tietoja, koska tiedot eivät ole tilastollisesti merkittäviä.  Saat lisätietoja tutustumalla ohjeartikkeliin [Tietojen optimointi merkityksellisiä tietoja varten](service-insights-optimize.md).
    > 
    
4. Visualisoinneissa näytetään erityinen **nopeat merkitykselliset tiedot** -pohja, jossa on enintään 32 erillistä merkityksellisiä tietoja sisältävää korttia. Jokaisessa kortissa on taulukko tai kaavio sekä lyhyt kuvaus.
   
    ![Nopeat merkitykselliset tiedot -pohja](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-insight-cards"></a>Vuorovaikutus merkityksellisten tietojen korttien kanssa

1. Osoita korttia ja lisää visualisointi koontinäyttöön valitsemalla kiinnityskuvake.

2. Osoita korttia, valitse **Enemmän vaihtoehtoja** (...) ja valitse sitten **Näytä merkitykselliset tiedot**. 

    Merkityksellisten tietojen näyttö avautuu kohdistustilassa.
   
    ![Merkityksellisten tietojen kohdistustila](media/service-insights/power-bi-insight-focus.png)
3. Tarkastelutilassa voit:
   
   * suodattaa visualisointeja. Jos **Suodattimet**-ruutu ei ole vielä avoinna, laajenna se valitsemalla ikkunan oikeassa reunassa oleva nuoli.

       ![Merkityksellisten tietojen suodatinvalikko laajennettuna](media/service-insights/power-bi-insights-filter-new.png)
   * Kiinnitä merkityksellisten tietojen kortti koontinäyttöön valitsemalla **Kiinnitä visualisointi**.
   * Suorita merkityksellisiä tietoja suoraan kortissa. Tätä kutsutaan usein *tietojen suodattamiseksi*. Valitse oikeasta yläkulmasta hehkulamppukuvake ![Hanki merkityksellisiä tietoja -kuvake](media/service-insights/power-bi-bulb-icon.png) tai **Hanki merkityksellisiä tietoja**.
     
       ![Hanki merkityksellisiä tietoja -kuvake](media/service-insights/pbi-autoinsights-tile.png)
     
     Merkitykselliset tiedot näytetään vasemmalla ja uudet kortit, joiden tiedot peruvat pelkästään kyseisiin merkityksellisiin tietoihin, näytetään oikealla.
     
       ![Suodatetut merkitykselliset tiedot](media/service-insights/power-bi-insights-on-insights-new.png)
4. Voit palata alkuperäiseen merkityksellisten tietojen pohjaan valitsemalla vasemmasta yläkulmasta **Poistu tarkastelutilasta**.

## <a name="run-insights-on-a-dashboard-tile"></a>Merkityksellisten tietojen suorittaminen koontinäytön ruudulle
Sen sijaan, että hakisit merkityksellisiä tietoja koko tietojoukosta, tarkenna hakuasi tekemällä merkityksellisten tietojen suodatus yksittäisen koontinäytön ruudun luomiseen käytetyissä tiedoissa. 

1. Avaa koontinäyttö.
2. Osoita ruutua. Valitse **Enemmän vaihtoehtoja** (...) ja valitse sitten **Näytä merkitykselliset tiedot**. Ruutu avautuu [tarkastelutilassa](../consumer/end-user-focus.md) ja merkityksellisten tietojen kortit näytetään oikealla.    
   
    ![Tarkastelutila](media/service-insights/pbi-insights-tile.png)    
3. Herättivätkö yksittäiset merkitykselliset tiedot kiinnostuksesi? Tutustu asiaan tarkemmin valitsemalla kyseinen kortti. Valitut merkitykselliset tiedot näytetään vasemmalla ja uudet kortit, joiden tiedot peruvat pelkästään kyseisiin merkityksellisiin tietoihin, näytetään oikealla.    
4. Jatka tietoihin tutustumista. Kun löydät mielenkiintoisia merkityksellisiä tietoja, kiinnitä se koontinäyttöösi valitsemalla **Kiinnitä visualisointi** oikeasta yläkulmasta.

## <a name="next-steps"></a>Seuraavat vaiheet
- Jos omistat tietojoukon, [optimoi se nopeita merkityksellisiä tietoja varten](service-insights-optimize.md).
- Lue lisätietoja [nopeiden merkityksellisten tietojen tyypeistä](../consumer/end-user-insight-types.md).

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/).
