---
title: Visualisointien toimintatapojen muokkaaminen raportissa
description: Ohjeet visualisointitoimien määrittämiseen Microsoft Power BI -palvelun raportissa ja Power BI Desktopin raportissa
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: N_xYsCbyHPw
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/11/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 6f739992ed282ada92b1049df09a8b5d4b3938a9
ms.sourcegitcommit: 654fae0af739bd599e029d692f142faeba0a502f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/20/2019
ms.locfileid: "56426581"
---
# <a name="change-how-visuals-interact-in-a-power-bi-report"></a>Visualisointien vuorovaikutuksen muuttaminen Power BI -raportissa
Jos sinulla on raportin muokkausoikeudet, voit käyttää **visualisointitoimia** ja muuttaa sitä, miten raporttisivun visualisoinnit vaikuttavat toisiinsa. 

Raporttisivun visualisoinneilla voi oletusarvoisesti ristiinsuodattaa ja ristiinkorostaa sivun muita visualisointeja.
Esimerkiksi osavaltion valitseminen karttavisualisoinnissa korostaa sarakekaavion ja suodattaa viivakaavion näyttämään vain yhtä osavaltiota koskevat tiedot.
Katso [Tietoja suodattamisesta ja korostamisesta](power-bi-reports-filters-and-highlighting.md). Jos sinulla on visualisointi, joka tukee [porautumista](consumer/end-user-drill.md), yhteen visualisointiin porautuminen ei oletusarvoisesti vaikuta muihin raporttisivun visualisointeihin. Nämä molemmat oletustoimintatavat voidaan ohittaa ja vuorovaikutus voidaan määrittää visualisointikohtaisesti.

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

