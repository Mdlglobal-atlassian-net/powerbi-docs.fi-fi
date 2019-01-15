---
title: Merkityksellisten tietojen käyttäminen ja tarkasteleminen koontinäytön ruuduissa
description: Lue, miten voit Power BI:n loppukäyttäjänä saada merkityksellisiä tietoja koontinäytön ruuduista.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 1edfa2d4eff5977ac1e517d9a3455e544fba5c72
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274578"
---
# <a name="view-data-insights-on-dashboard-tiles-with-power-bi"></a>Merkityksellisten tietojen tarkasteleminen koontinäytön ruuduissa Power BI:n avulla
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
Kun sinulla on merkityksellinen tieto avattuna, jatka siihen tutustumista.

   * Suodata visualisointi piirtoalustalla.  Voit tarkastella suodattimia valitsemalla oikeasta yläkulmasta nuolen, joka laajentaa Suodattimet-ruudun.

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

