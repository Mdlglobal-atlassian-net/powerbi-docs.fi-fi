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
ms.openlocfilehash: 3ab200194d89eb15892dc4f452079eb56df8a608
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/23/2019
ms.locfileid: "71191489"
---
# <a name="waterfall-charts-in-power-bi"></a>Vesiputouskaaviot Power BI:ssä

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Vesiputouskaaviot näyttävät juoksevan kokonaissumman, kun Power BI lisää ja vähentää arvoja. Ne ovat hyödyllisiä sen ymmärtämiseksi, miten positiivisten ja negatiivisten muutosten sarja vaikuttaa alkuarvoon (kuten nettotuloon).

Sarakkeet ovat värikoodattuja, joten huomaat nopeasti nousut ja laskut. Alkuarvon ja lopullisen arvon sarakkeet usein [alkavat vaaka-akselilla](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "alkavat vaaka-akselilla"), kun taas keskitason arvot ovat irrallisia sarakkeita. Tämän tyylin vuoksi vesiputouskaavioita kutsutaan myös siltakaavioiksi.

   > [!NOTE]
   > Tässä videossa käytetään Power BI Desktopin vanhempaa versiota.
   > 
   > 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Milloin kannattaa käyttää vesiputouskaaviota

Vesiputouskaavio on hyvä vaihtoehto:

* kun olet tehnyt muutoksia mittarin aikasarjaan tai eri luokkiin

* jos haluat valvoa tärkeimpiä kokonaisarvoon vaikuttavia muutoksia

* jos haluat tehdä kaavion yrityksen vuosittaisesta tuotosta näyttämällä eri tulonlähteitä ja lopulta kokonaisvoiton (tai tappion)

* jos haluat havainnollistaa yrityksen alku- ja lopetushenkilöstömäärää vuoden aikana

* jos haluat visualisoida, kuinka paljon rahaa ansaitset ja käytät joka kuukausi sekä tilin juoksevan saldon.

## <a name="prerequisite"></a>Edellytys

Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.


## <a name="create-a-waterfall-chart"></a>Vesiputouskaavion luominen

Luot vesiputouskaavion, joka näyttää myynnin vaihtelun (arvioitu myynti vs. todellinen myynti) kuukauden mukaan.

1. Valitse **Kentät**-ruudussa **Myynti**  > **Myyntivariaatio yhteensä**.

   ![Näyttökuva, jossa Myynti > Myynnin ero yhteensä on valittuna, ja tulokseksi saatu visualisointi.](media/power-bi-visualization-waterfall-charts/power-bi-first-value.png)

1. Valitse Vesiputous-kuvake ![Näyttökuva Vesiputous-kuvakkeesta](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-icon.png)

    ![Visualisointimallit](media/power-bi-visualization-waterfall-charts/convert-waterfall.png)

1. Valitse **Aika** > **FiscalMonth** sen lisäämiseksi **Luokka**-säilöön.

    ![vesiputous](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)

1. Varmista, että Power BI lajitteli vesiputouskaavion aikajärjestyksessä. Valitse kaavion oikeassa yläkulmassa olevat kolme pistettä (...).

    Tässä esimerkissä valitaan vaihtoehto **Lajittele nousevaan järjestykseen**

    Tarkista, että keltainen ilmaisin on **Lajittele nousevaan järjestykseen** -vaihtoehdon vieressä vasemmalla. Tämä ilmaisee, että valitsemasi asetus on käytössä.

    ![Valitse Lajitteluperuste > Lajittele nousevaan järjestykseen](media/power-bi-visualization-waterfall-charts/power-bi-sort-by.png)

    Seuraavaksi valitaan **Lajitteluperuste** ja valitse **FiscalMonth**. Kuten edellisessä vaiheessa, valintasi vieressä näkyvä keltainen ilmaisin osoittaa, kun valinta-asetuksesi on käytössä.

    ![Valitse Lajitteluperuste > FiscalMonth](media/power-bi-visualization-waterfall-charts/power-bi-sort-by-fiscal-month.png)

    Voit myös tarkastella X-akselin arvoja ja näet, että ne ovat järjestyksessä **tammikuusta** **elokuuhun**.

    Tarkastele hieman enemmän nähdäksesi, mikä aiheuttaa eniten muutoksia kuukausittain.

1.  Valitse **Myymälä** > **Alue**, jolloin**Alue** lisätään **Erittely**-säilöön.

    ![Näyttää Myymälän Erittely-säilössä](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)

    Oletusarvon mukaan Power BI lisää viisi suurinta osallistujaa nousuun tai laskuun kuukauden mukaan. Alla olevassa kuvassa visualisointiruutu näkyy laajennettuna lisätietojen näyttämistä varten. 

    ![Näyttää Myymälän Erittely-säilössä](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-initial.png)

    Olet kiinnostunut vain kahdesta suurimmasta osallistujasta.

1. Valitse **Muotoilu**-ruudussa **Erittely** ja määritä **Suurimmat erittelyt** arvoksi **2**.

    ![Muotoilu > Erittely](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)

    Lyhyestä katsauksesta käy ilmi, että Ohion ja Pennsylvanian alueet ovat vesiputouskaavion suurimmat osallistujat sekä negatiivisessa että positiivisessa liikkeessä.

    ![vesiputouskaavio](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)

## <a name="next-steps"></a>Seuraavat vaiheet

* [Visualisointien vuorovaikutuksen muuttaminen Power BI -raportissa](../service-reports-visual-interactions.md)

* [Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
