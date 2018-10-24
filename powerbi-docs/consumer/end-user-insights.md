---
title: Koontitietojen automaattinen luominen Power BI:llä
description: Lue, miten voit saada tietojoukkoja ja koontinäytön ruutuja koskevia katsauksia.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/10/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: f68e962eacf04005d83ec0def10cf8e0e24f6e10
ms.sourcegitcommit: dc8b8a2cf2dcc96ccb46159802ebd9342a7fa840
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/11/2018
ms.locfileid: "49112034"
---
# <a name="automatically-generate-data-insights-with-power-bi"></a>Koontitietojen automaattinen luominen Power BI:llä
Koontinäytön visualisointiruutujen kautta voit tarkastella tietoja. Kun valitset ruudun, raportti avautuu. Raportissa voit suodattaa ja lajitella raportin taustalla olevaa tietojoukkoa ja perehtyä siihen tarkemmin. Kun suoritat merkityksellisiä tietoja, Power BI tarkastelee tietoja puolestasi.

Saat nopeita merkityksellisiä tietoja ja voit luoda tietoihin perustuvia mielenkiintoisia, vuorovaikutteisia visualisointeja. Nopeat merkitykselliset tiedot voidaan suorittaa tietylle koontinäytön ruudulle, tai voit suorittaa merkitykselliset tiedot jopa toisiin merkityksellisiin tietoihin.

Merkityksellisiä tietoja -ominaisuus on perustuu kasvavaan [edistyneiden analyysialgoritmien joukkoon](end-user-insight-types.md), jota kehitetään yhdessä Microsoft Researchin kanssa. Sen avulla entistä useammat ihmiset voivat saada merkityksellisiä tietoja tiedoistaan uusilla ja intuitiivisilla tavoilla.

## <a name="run-insights-on-a-dashboard-tile"></a>Merkityksellisten tietojen suorittaminen koontinäytön ruudulle
Kun suoritat merkitykselliset tiedot koontinäytön ruudulle, Power BI hakee vain kyseisen koontinäytön ruudun luomiseen käytetyt tiedot. 

1. [Avaa koontinäyttö](end-user-dashboards.md).
2. Osoita ruutua. Valitse kolme pistettä (...) ja sitten **Näytä merkitykselliset tiedot**. 

    ![kolme pistettä -valikkotila](./media/end-user-insights/power-bi-hover.png)


3. Ruutu avautuu [kohdistustilassa](end-user-focus.md) ja merkityksellisten tietojen kortit näytetään oikealla.    
   
    ![Kohdistustila](./media/end-user-insights/pbi-insights-tile.png)    
4. Herättivätkö yksittäiset merkitykselliset tiedot kiinnostuksesi? Tutustu asiaan tarkemmin valitsemalla kyseinen kortti. Valitut merkitykselliset tiedot näytetään vasemmalla ja uudet kortit, joiden tiedot peruvat pelkästään kyseisiin merkityksellisiin tietoihin, näytetään oikealla.    

 ## <a name="interact-with-the-insight-cards"></a>Vuorovaikutus merkityksellisten tietojen korttien kanssa
   * suodattaa visualisointeja.  Voit tarkastella suodattimia valitsemalla oikeasta yläkulmasta nuolen, joka laajentaa Suodattimet-ruudun.

     ![merkitykselliset tiedot- ja suodatinvalikko laajennettuna](./media/end-user-insights/power-bi-insights-on-insights.png)
   
   * Merkityksellisten tietojen suorittaminen korttiin. Tätä kutsutaan usein **aiheeseen liittyviksi merkityksellisiksi tiedoiksi**. Valitse oikeasta yläkulmasta hehkulamppukuvake ![Hanki merkityksellisiä tietoja -kuvake](./media/end-user-insights/power-bi-bulb-icon.png) tai **Hanki merkityksellisiä tietoja**.
     
     ![valikkopalkki, jossa näkyy Hae merkityksellisiä tietoja -kuvake](./media/end-user-insights/power-bi-autoinsights-tile.png)
     
     Merkitykselliset tiedot näytetään vasemmalla ja uudet kortit, joiden tiedot peruvat pelkästään kyseisiin merkityksellisiin tietoihin, näytetään oikealla.
     
     ![suodatetut merkitykselliset tiedot](./media/end-user-insights/power-bi-insights-on-insights-new.png)

Voit palata alkuperäiseen merkityksellisten tietojen pohjaan valitsemalla vasemmasta yläkulmasta **Poistu kohdistustilasta**.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- **Näytä merkitykselliset tiedot** ei toimi DirectQueryllä – se toimii vain Power BI:hin ladatuilla tiedoilla.
- **Näytä merkitykselliset tiedot** ei toimi kaikissa koontinäytön ruututyypeissä. Se ei ole käytettävissä esimerkiksi mukautetuissa visualisoinneissa.<!--[custom visuals](end-user-custom-visuals.md)-->


## <a name="next-steps"></a>Seuraavat vaiheet
Lue lisätietoja [nopeiden merkityksellisten tietojen tyypeistä](end-user-insight-types.md)

