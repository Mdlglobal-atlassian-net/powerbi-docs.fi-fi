---
title: Visualisointien toimintatapojen muokkaaminen raportissa
description: Ohjeet visualisointitoimien määrittämiseen Microsoft Power BI -palvelun raportissa ja Power BI Desktopin raportissa
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: N_xYsCbyHPw
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: aae902d2fdc4198c362cf5c2a09a74d04704e519
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34241815"
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Visualisoinnin käsitteleminen Power BI -raportissa
Jos sinulla on raportin muokkausoikeudet, voit käyttää **visualisointitoimia** ja muuttaa sitä, miten raporttisivun visualisoinnit vaikuttavat toisiinsa. 

Raporttisivun visualisoinneilla voi oletusarvoisesti ristiinsuodattaa ja ristiinkorostaa sivun muita visualisointeja.
Esimerkiksi osavaltion valitseminen karttavisualisoinnissa korostaa sarakekaavion ja suodattaa viivakaavion näyttämään vain yhtä osavaltiota koskevat tiedot.
Katso [Tietoja suodattamisesta ja korostamisesta](power-bi-reports-filters-and-highlighting.md). Jos sinulla on visualisointi, joka tukee [porautumista](power-bi-visualization-drill-down.md), yhteen visualisointiin porautuminen ei oletusarvoisesti vaikuta muihin raporttisivun visualisointeihin. Nämä molemmat oletustoimintatavat voidaan ohittaa ja vuorovaikutus voidaan määrittää visualisointikohtaisesti.

Tässä artikkelissa kerrotaan, miten voit käyttää **visualisointitoimia** Power BI -palvelun [muokkausnäkymässä](service-interact-with-a-report-in-editing-view.md) ja Power BI Desktopissa. Jos raportti on jaettu kanssasi, et voi muuttaa visualisointitoimien asetuksia.

> [!NOTE]
> Termejä *ristiinsuodatus* ja *ristiinkorostus* käytetään tässä kuvatun toiminnan erottamiseksi siitä, mitä tapahtuu, kun käytät visualisointien suodattamiseen ja korostamiseen **Suodattimet**-ruutua.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Valitse visualisointi, jotta siitä tulee aktiivinen.  
2. Näytä **Visualisointitoimet**-asetukset.
    - Valitse Power BI -palvelussa avattava valikko raportin valikkoriviltä.

       ![Visualisointitoimien avattava valikko](media/service-reports-visual-interactions/power-bi-visual-interaction.png)

    - Valitse Desktopissa **Muotoile > Toimet**.

        ![valitse Muotoile ja valitse sitten Toimet](media/service-reports-visual-interactions/pbi-visual-interaction-desktop.png)

3. Voit ottaa visualisointitoimien ohjausobjektit käyttöön valitsemalla **Muokkaa vuorovaikutuksia**. Power BI lisää ristiinsuodatuksen ja ristiinkorostuksen kuvakkeet kaikkiin muihin raporttisivun visualisointeihin.
   
    ![raportti, jossa Visualisointitoimet on käytössä](media/service-reports-visual-interactions/power-bi-icons-on.png)
3. Määritä, miten valitun visualisoinnin pitäisi vaikuttaa muihin.  Toista vaiheet tarvittaessa muille raporttisivun visualisoinneille.
   
   * Jos sen tulee ristiinsuodattaa visualisointi, valitse **suodattimen** kuvake ![suodatinkuvake](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png).
   * Jos sen tulee ristiinkorostaa visualisointi, valitse **korostuksen** kuvake ![korostuskuvake](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png).
   * Jos sillä ei pidä olla vaikutusta, valitse **Ei vaikutusta** -kuvake ![ei vaikutusta -kuvake](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png).

4. Voit ottaa porautumisen ohjausobjektit käyttöön valitsemalla **Poraaminen suodattaa muut visualisoinnit**.  Nyt kun visualisoinnissa poraudutaan alaspäin (ja ylöspäin), muut raporttisivun visualisoinnit muuttuvat nykyisen porautumisvalinnan mukaisesti. 

   ![video porautumisen ohjausobjektien ottamisesta käyttöön](media/service-reports-visual-interactions/drill2.gif)

### <a name="next-steps"></a>Seuraavat vaiheet
[Raporttisuodattimien käyttäminen](power-bi-how-to-report-filter.md)

[Suodattimet ja korostaminen raporteissa](power-bi-reports-filters-and-highlighting.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

