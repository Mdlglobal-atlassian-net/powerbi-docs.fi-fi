---
title: Vesiputouskaaviot Power BI:ssä
description: Vesiputouskaaviot Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: maTzOJSRB3g
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c9ad87d851f52db6cd2720c9e3bd5d4bb7b189a7
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/27/2019
ms.locfileid: "67409129"
---
# <a name="waterfall-charts-in-power-bi"></a>Vesiputouskaaviot Power BI:ssä

Vesiputouskaaviot näyttävät juoksevan kokonaissumman, kun Power BI lisää ja vähentää arvoja. Ne ovat hyödyllisiä sen ymmärtämiseksi, miten positiivisten ja negatiivisten muutosten sarja vaikuttaa alkuarvoon (kuten nettotuloon).

Sarakkeet ovat värikoodattuja, joten huomaat nopeasti nousut ja laskut. Alkuarvon ja lopullisen arvon sarakkeet usein [alkavat vaaka-akselilla](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "alkavat vaaka-akselilla"), kun taas keskitason arvot ovat irrallisia sarakkeita. Tämän tyylin vuoksi vesiputouskaavioita kutsutaan myös siltakaavioiksi.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Milloin kannattaa käyttää vesiputouskaaviota

Vesiputouskaavio on hyvä vaihtoehto:

* kun olet tehnyt muutoksia mittarin aikasarjaan tai eri luokkiin

* jos haluat valvoa tärkeimpiä kokonaisarvoon vaikuttavia muutoksia

* jos haluat tehdä kaavion yrityksen vuosittaisesta tuotosta näyttämällä eri tulonlähteitä ja lopulta kokonaisvoiton (tai tappion)

* jos haluat havainnollistaa yrityksen alku- ja lopetushenkilöstömäärää vuoden aikana

* jos haluat visualisoida, kuinka paljon rahaa ansaitset ja käytät joka kuukausi sekä tilin juoksevan saldon.

## <a name="prerequisites"></a>Edellytykset

* Power BI -palvelu tai Power BI Desktop

* Jälleenmyyntianalyysimallin raportti

## <a name="get-the-retail-analysis-sample-report"></a>Jälleenmyyntianalyysimallin raportin hankkiminen

Näissä ohjeissa käytetään jälleenmyyntianalyysimallia. Visualisoinnin luominen edellyttää tietojoukon ja raportin muokkausoikeuksia. Kaikeksi onneksi Power BI -mallit ovat kaikki muokattavissa. Jos joku jakaa raportin kanssasi, et voi luoda visualisointeja raporteissa. Voit seurata mukana hankkimalla [jälleenmyyntianalyysimallin raportin](../sample-datasets.md).

Kun olet hankkinut **jälleenmyyntianalyysimallin** tietojoukon, voit aloittaa.

## <a name="create-a-waterfall-chart"></a>Vesiputouskaavion luominen

Luot vesiputouskaavion, joka näyttää myynnin vaihtelun (arvioitu myynti vs. todellinen myynti) kuukauden mukaan.

1. Valitse **Oma työtila** -kohdasta **Tietojoukot** > **Luo raportti**.

    ![Näyttökuva tietojoukoista > Luo raportti.](media/power-bi-visualization-waterfall-charts/power-bi-create-a-report.png)

1. Valitse **Kentät**-ruudussa **Myynti**  > **Myyntivariaatio yhteensä**.

   ![Näyttökuva, jossa Myynti > Myyntivariaation yhteensä on valittuna, ja tulokseksi saatu visualisointi.](media/power-bi-visualization-waterfall-charts/power-bi-first-value.png)

1. Valitse Vesiputous-kuvake ![Näyttökuva Vesiputous-kuvakkeesta](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-icon.png) kaavion muuntamiseksi puukartaksi.

    Jos **Myyntivariaatio yhteensä** ei ole **Y-akselin** alueella, vedä se sinne.

    ![Visualisointimallit](media/power-bi-visualization-waterfall-charts/convertwaterfall.png)

1. Valitse **Aika** > **FiscalMonth** sen lisäämiseksi **Luokka**-säilöön.

    ![vesiputous](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)

1. Varmista, että Power BI lajitteli vesiputouskaavion aikajärjestyksessä. Valitse kaavion oikeassa yläkulmassa olevat kolme pistettä (...).

    Tarkista, että keltainen ilmaisin on **Lajittele nousevaan järjestykseen**- ja **FiscalMonth**-vaihtoehtojen vieressä vasemmalla

    ![Valitse Lajitteluperuste > FiscalMonth](media/power-bi-visualization-waterfall-charts/power-bi-sort-by.png)

    Voit myös tarkastella X-akselin arvoja ja näet, että ne ovat järjestyksessä **tammikuusta** **elokuuhun**.

    Tarkastele hieman enemmän nähdäksesi, mikä aiheuttaa eniten muutoksia kuukausittain.

1. Vedä **Myymälä** > **Alue** ja **Erittely**-säilöön.

    ![Näyttää Myymälän Erittely-säilössä](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)

    Oletusarvon mukaan Power BI lisää viisi suurinta osallistujaa nousuun tai laskuun kuukauden mukaan.

    ![Näyttää Myymälän Erittely-säilössä](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-initial.png)

    Olet kiinnostunut vain kahdesta suurimmasta osallistujasta.

1. Valitse **Muotoilu**-ruudussa **Erittely** ja määritä **Suurimmat erittelyt** arvoksi **2**.

    ![Muotoilu > Erittely](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)

    Lyhyestä katsauksesta käy ilmi, että Ohion ja Pennsylvanian alueet ovat vesiputouskaavion suurimmat osallistujat sekä negatiivisessa että positiivisessa liikkeessä.

    ![vesiputouskaavio](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)

    Tämä on mielenkiintoinen havainto. Onko Ohion ja Pennsylvanian vaikutus niin merkittävä, koska myynti näillä kahdella alueella on paljon muita alueita suurempaa? Voit tarkistaa asian.

1. Luo kartta, jossa myynti näytetään alueen mukaan tänä vuonna ja viime vuonna.

    ![kartta lähennettynä Pennsylvaniaan ja Ohioon](media/power-bi-visualization-waterfall-charts/power-bi-map.png)

    Kartta tukee teoriaasi. Se näyttää, että näillä kahdella alueella oli suurin myyntiarvo viime vuonna (kuplan koko) ja tänä vuonna (kuplan varjostus).

## <a name="highlighting-and-cross-filtering"></a>Korostaminen ja ristiinsuodatus

Lisätietoja **Suodattimet**-ruudun käytöstä on artikkelissa [Lisää suodatin raporttiin muokkausnäkymässä](../power-bi-report-add-filter.md).

Sarakkeen korostaminen vesiputouskaaviossa ristiinsuodattaa muut raporttisivulla olevat visualisoinnit ja päinvastoin. **Summa**sarake ei kuitenkaan käynnistä korostusta tai vastaa ristiinsuodatukseen.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Visualisointien vuorovaikutuksen muuttaminen Power BI -raportissa](../service-reports-visual-interactions.md)

* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
