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
ms.date: 09/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3835bedc1b4ab2df87abf4704ef338ff7f4abc5d
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/13/2019
ms.locfileid: "56215040"
---
# <a name="waterfall-charts-in-power-bi"></a>Vesiputouskaaviot Power BI:ssä
Vesiputouskaavio näyttää juoksevan summan, kun arvoja lisätään tai vähennetään. On hyödyllistä ymmärtää, kuinka positiivisten ja negatiivisten muutosten sarja vaikuttaa alkuarvoon (esimerkiksi nettotuloon).

Sarakkeet ovat värillisiä, jotta näet nopeasti nousut ja laskut. Alkuarvon ja lopullisen arvon sarakkeet usein [alkavat vaaka-akselilla](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "alkavat vaaka-akselilla"), kun taas keskitason arvot ovat irrallisia sarakkeita. Tämän ulkoasun vuoksi vesiputouskaavioita kutsutaan myös siltakaavioiksi.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Milloin kannattaa käyttää vesiputouskaaviota
Vesiputouskaavio on hyvä vaihtoehto:

* kun olet tehnyt muutoksia mittayksikön aikasarjaan tai eri luokkiin
* jos haluat valvoa tärkeimpiä kokonaisarvoon vaikuttavia muutoksia
* jos haluat tehdä kaavion yrityksen vuosittaisesta tuotosta näyttämällä eri tulonlähteitä ja lopulta kokonaisvoiton (tai tappion).
* jos haluat havainnollistaa yrityksen alku- ja lopetushenkilöstömäärän vuoden aikana
* jos haluat visualisoida, kuinka paljon rahaa ansaitset ja käytät joka kuukausi sekä tilin juoksevan saldon. 

## <a name="create-a-waterfall-chart"></a>Vesiputouskaavion luominen
Luomme vesiputouskaavion, joka näyttää myynnin vaihtelun (arvioitu myynti vs. todellinen myynti) kuukauden mukaan. Seurataksesi kirjaudu Power BI:hin ja valitse **Nouda tiedot\> Mallit \> Jälleenmyyntianalyysimalli**. 

1. Valitse **Tietojoukot**-välilehti ja vieritä uuteen Jälleenmyyntianalyysimalli-tietojoukkoon.  Avaa tietojoukko raportin muokkausnäkymään valitsemalla **Luo raportti** -kuvake. 
   
    ![Tietojoukot-välilehti korostettuna](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-report.png)
2. Valitse **Kentät**-ruudussa **Myynti \> Myyntivariaatio yhteensä**. 
3. Muuta kaavio **vesiputoukseksi**. Jos **Myyntivariaatio yhteensä** ei ole **Y-akselin** alueella, vedä se sinne.
   
    ![Visualisointimallit](media/power-bi-visualization-waterfall-charts/convertwaterfall.png)
4. Valitse **Aika** \> **FiscalMonth** ja lisää se **Luokka**-kohtaan. 
   
    ![vesiputous](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)
5. Lajittele vesiputouskaavio aikajärjestyksessä. Valitse kaavion oikeasta yläkulmasta kolme pistettä (...) ja valitse **FiscalMonth**.
   
    ![valitse lajitteluperuste > FiscalMonth](media/power-bi-visualization-waterfall-charts/power-bi-sort-by.png)
   
    ![uuden nousevan järjestyksen lajittelun tulokset](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-sorted.png)
6. Tarkastele hieman enemmän nähdäksesi, mikä aiheuttaa eniten muutoksia kuukausittain. Vedä **Myymälä** > **Alue** ja **Erittely**-säilöön.
   
    ![Näyttää Myymälän Erittely-säilössä](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)
7. Oletusarvon mukaan Power BI lisää 5 suurinta osallistujaa nousuun tai laskuun kuukauden mukaan. Mutta me olemme kiinnostuneita vain 2 suurimmasta osallistujasta.  Valitse Muotoilu-ruudussa **Erittely** ja määritä **Suurin arvo** -kohtaan 2.
   
    ![Muotoilu > Erittely](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)
   
    Lyhyestä katsauksesta käy ilmi, että Ohion ja Pennsylvanian alueet ovat vesiputouskaavion suurimmat osallistujat sekä negatiivisessa että positiivisessa liikkeessä. 
   
    ![vesiputouskaavio](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)
8. Tämä on mielenkiintoinen havainto. Onko Ohion ja Pennsylvanian vaikutus niin merkittävä, koska myynti näillä kahdella alueella on paljon muita alueita suurempaa?  Voimme tarkistaa asian. Luo kartta, jossa myynti näytetään alueen mukaan tänä vuonna ja viime vuonna.  
   
    ![kartta lähennettynä Pennsylvaniaan ja Ohioon](media/power-bi-visualization-waterfall-charts/power-bi-map.png)
   
    Karttamme tukee teoriaa.  Se näyttää, että näillä kahdella alueella oli suurin myyntiarvo viime vuonna (kuplan koko) ja tänä vuonna (kuplan varjostus).

## <a name="highlighting-and-cross-filtering"></a>Korostaminen ja ristiinsuodatus
Lisätietoja Suodattimet-paneelin käyttämisestä saat ohjeaiheesta [Suodattimen lisääminen raporttiin](../power-bi-report-add-filter.md).

Sarakkeen korostaminen vesiputouskaaviossa ristiinsuodattaa muut raporttisivulla olevat visualisoinnit... ja päinvastoin. Summasarake ei kuitenkaan käynnistä korostusta tai vastaa ristiinsuodatukseen.

## <a name="next-steps"></a>Seuraavat vaiheet

[Visualisointitoimet](../service-reports-visual-interactions.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)