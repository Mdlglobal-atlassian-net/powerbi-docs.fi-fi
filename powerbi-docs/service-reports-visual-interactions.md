---
title: Visualisointien toimintatapojen muokkaaminen raportissa
description: Ohjeet visualisointitoimien määrittämiseen Microsoft Power BI -palvelun raportissa ja Power BI Desktopin raportissa
author: mihart
ms.reviewer: ''
featuredvideoid: N_xYsCbyHPw
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 116ff1df7ddc75df79e6f2f28296543449498599
ms.sourcegitcommit: 64a270362c60581a385af7fbc31394e3ebcaca41
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/31/2020
ms.locfileid: "76894709"
---
# <a name="change-how-visuals-interact-in-a-power-bi-report"></a>Visualisointien vuorovaikutuksen muuttaminen Power BI -raportissa
Jos sinulla on raportin muokkausoikeudet, voit käyttää **visualisointitoimia** ja muuttaa sitä, miten raporttisivun visualisoinnit vaikuttavat toisiinsa. 

## <a name="introduction-to-visual-interactions"></a>Visualisointitoimien johdanto
Raporttisivun visualisoinneilla voi oletusarvoisesti ristiinsuodattaa ja ristiinkorostaa sivun muita visualisointeja.
Esimerkiksi osavaltion valitseminen karttavisualisoinnissa korostaa sarakekaavion ja suodattaa viivakaavion näyttämään vain yhtä osavaltiota koskevat tiedot.
Katso [Tietoja suodattamisesta ja korostamisesta](power-bi-reports-filters-and-highlighting.md). Jos sinulla on visualisointi, joka tukee [porautumista](consumer/end-user-drill.md), yhteen visualisointiin porautuminen ei oletusarvoisesti vaikuta muihin raporttisivun visualisointeihin. Nämä molemmat oletustoimintatavat voidaan ohittaa ja vuorovaikutus voidaan määrittää visualisointikohtaisesti.

Tässä artikkelissa kerrotaan, miten voit käyttää **visualisointitoimia** Power BI Desktopissa. Prosessi vastaa Power BI -palvelun [muokkausnäkymää](service-interact-with-a-report-in-editing-view.md). Jos sinulla on vain lukunäkymän käyttöoikeus tai jos raportti on jaettu kanssasi, et voi muuttaa visualisointitoimien asetuksia.

Termejä *ristiinsuodatus* ja *ristiinkorostus* käytetään tässä kuvatun toiminnan erottamiseksi siitä, mitä tapahtuu, kun käytät visualisointien *suodattamiseen* ja *korostamiseen***Suodattimet**-ruutua.  

> [!NOTE]
> Tässä videossa käytetään Power BI Desktopin ja Power BI -palvelun vanhempia versioita. 
>
>

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


## <a name="enable-the-visual-interaction-controls"></a>Visualisointitoimien ohjausobjektien ottaminen käyttöön
Jos sinulla on raportin muokkausoikeudet, voit ottaa käyttöön visualisointitoimien ohjausobjektit ja mukauttaa sitten sitä, miten raporttisivusi visualisoinnit suodattuvat ja korostavat toisiaan. 

1. Valitse visualisointi, jotta siitä tulee aktiivinen.  
2. Näytä **Visualisointitoimet**-asetukset.
    

    - Valitse Desktopissa **Muotoile > Toimet**.

        ![valitse Muotoile ja valitse sitten Toimet](media/service-reports-visual-interactions/power-bi-interaction.png)

    - Avaa raportti Power BI -palvelun muokkausnäkymässä ja valitse avattava valikko raportin valikkoriviltä.

        ![Visualisointitoimien avattava valikko](media/service-reports-visual-interactions/power-bi-service.png)

3. Voit tuoda visualisointitoimien ohjausobjektit näkyviin valitsemalla **Muokkaa vuorovaikutuksia**. Power BI lisää suodatuksen ja korostuksen kuvakkeet kaikkiin muihin raporttisivun visualisointeihin. Näemme, että puukartassa ristiinsuodatetaan viivakaaviota ja karttaa sekä ristiinkorostetaan pylväskaaviota. Nyt voit muuttaa sitä, kuinka valittu visualisointi vaikuttaa muihin raporttisivun visualisointeihin.
   
    ![raportti, jossa Visualisointitoimet on käytössä](media/service-reports-visual-interactions/power-bi-turn-on.png)


## <a name="change-the-interaction-behavior"></a>Vaikutustavan vaihtaminen
Tutustu siihen, miten visualisoinnit vaikuttavat toisiinsa, valitsemalla kukin raporttisivullasi oleva visualisointi (yksi kerrallaan).  Valitse arvopiste, palkki tai muoto ja katso sen vaikutusta muihin visualisointeihin. Jos näkemäsi toiminta ei vastaa haluamaasi, voit muuttaa vaikutustapaa. Muutokset tallentuvat raportin yhteydessä, joten raporttisi käyttäjät saavat saman visuaalisen kokemuksen kuin itsekin sait.


Aloita valitsemalla visualisointi, jotta siitä tulee aktiivinen.  Huomaa, että sivun kaikki muut visualisoinnit näyttävät nyt vuorovaikutuskuvakkeet. Tummennettu kuvake on se, jota käytetään. Määritä seuraavaksi, miten haluat **valitun visualisoinnin** vaikuttavan muihin.  Toista vaiheet tarvittaessa muille raporttisivun visualisoinneille.

Jos haluat, että valittu visualisointi
   
   * ristiinsuodattaa jokin sivun muista visualisoinneista, valitse **suodatinkuvake** visualisoinnin oikeasta yläkulmasta ![suodatinkuvake](media/service-reports-visual-interactions/power-bi-filter-icon.png).
   * ristiinkorostaa jokin sivun muista visualisoinneista, valitse **korostuskuvake** ![korostuskuvake](media/service-reports-visual-interactions/power-bi-highlight-icon.png).
   * ei vaikuta johonkin sivun muuhun visualisointiin, valitse **ei vaikutusta** -kuvake ![ei vaikutusta -kuvake](media/service-reports-visual-interactions/power-bi-no-impact.png).

## <a name="change-the-interactions-of-drillable-visualizations"></a>Muuta porattavissa olevien visualisointien vaikutustapoja
[Tiettyjä Power BI -visualisointeja voidaan porata](consumer/end-user-drill.md). Oletusarvon mukaan jos visualisointia porataan, se ei vaikuta raporttisivun muihin visualisointeihin. Tätä toimintaa voidaan kuitenkin muuttaa. 

> [!TIP]
> Testaa tätä itse käyttämällä [Henkilöstöhallintomallin PBIX-tiedostoa](https://download.microsoft.com/download/6/9/5/69503155-05A5-483E-829A-F7B5F3DD5D27/Human%20Resources%20Sample%20PBIX.pbix). Tiedostossa on pylväskaavio, joka porautuu alaspäin **Uudet palkkaukset** -välilehdellä.
>

1. Valitse porattavissa oleva visualisointi, jotta se on aktiivinen. 

2. Ota porautuminen alaspäin käyttöön valitsemalla porautuminen alaspäin -kuvake.

    ![ota porautuminen käyttöön](media/service-reports-visual-interactions/power-bi-drill-down.png)

2. Valitse valikkopalkista **Muotoile** > **Poraaminen suodattaa muut visualisoinnit**.  Nyt kun visualisoinnissa poraudutaan alaspäin (ja ylöspäin), muut raporttisivun visualisoinnit muuttuvat nykyisen porautumisvalinnan mukaisesti. 

    ![ota käyttöön poraaminen suodattaa muut visualisoinnit](media/service-reports-visual-interactions/power-bi-drill.png)

3. Jos näkemäsi toiminta ei vastaa haluamaasi, voit muuttaa vaikutustapaa [edellä kuvatulla tavalla](#change-the-interaction-behavior).
    
## <a name="next-steps"></a>Seuraavat vaiheet
[Suodattaminen ja korostaminen Power BI -raporteissa](power-bi-reports-filters-and-highlighting.md)