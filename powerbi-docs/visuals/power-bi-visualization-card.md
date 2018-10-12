---
title: Korttivisualisoinnit (eli suurten lukujen ruudut)
description: Kortin visualisoinnin luominen Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 865e19f368b8e1915d0262ae6356e70a8dbc2781
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/27/2018
ms.locfileid: "47416892"
---
# <a name="card-visualizations"></a>Kortin visualisoinnit
Joskus yksittäinen luku on tärkein seikka, jota haluat seurata Power BI-raporttinäytöllä tai raportissa, kuten kokonaismyynti, markkinaosuus vuositasolla tai kokonaismahdollisuudet. Tämä visualisointi on nimeltään *Kortti*. Samoin kuin lähes kaikki alkuperäiset Power BI-visualisoinnit, kortit voidaan luoda käyttäen raporttieditoria tai Q&A:ta.

![kortin visualisointi](media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>Kortin luominen raporttieditoria käyttämällä
Näissä ohjeissa käytetään jälleenmyyntianalyysimallia. Jos haluat seurata ohjeita itse, [lataa malli](../sample-datasets.md) joko Power BI ‑palveluun (app.powerbi.com) tai Power BI Desktopiin.   

1. Aloita [tyhjältä raporttisivulta](../power-bi-report-add-page.md) ja valitse kenttä **Myymälä** \> **Avoimien myymälöiden määrä**. Jos käytät Power BI ‑palvelua, varmista, että avaat raportin [muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md).

    Power BI luo pylväskaavion, jossa yksi luku.

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. Valitse Visualisoinnit-ruudussa korttikuvake.

   ![](media/power-bi-visualization-card/power-bi-templates.png)
6. Osoita korttia ja lisää visualisointi koontinäyttöön valitsemalla kiinnityskuvake![](media/power-bi-visualization-card/pbi_pintile.png).

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. Kiinnitä ruutu aiemmin luotuun koontinäyttöön tai uuteen koontinäyttöön.

   * Aiemmin luotu raporttinäkymä: valitse raporttinäkymän nimi avattavasta luettelosta.
   * Uusi koontinäyttö: anna nimi uudelle koontinäytölle.
8. Valitse **Kiinnitä**.

   Onnistumissanoma (oikean yläkulman lähellä) ilmaisee, että visualisointi lisättiin ruutuna koontinäyttöön.

   ![](media/power-bi-visualization-card/power-bi-success2.png)
9. Valitse **Siirry raporttinäkymään**. Siinä voit [muokata ja siirtää](../service-dashboard-edit-tile.md) kiinnitetyn visualisoinnin.


## <a name="create-a-card-from-the-qa-question-box"></a>Luo kortti Q&A-kysymysruudusta
Q&A-kysymysruutu on helpoin tapa tehdä kortti. Q&A-kysymysruutu on käytettävissä Power BI -palvelun raporttinäkymästä tai Desktop-version raporttiruudulta. Seuraavat ohjeet kuvaavat kortin luomista Power BI -palvelun raporttinäkymästä. Jos haluat luoda korin Q&A:n avulla Power BI Desktopissa, [noudata seuraavia ohjeita](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA) Desktop-raporttien Q&A-esikatseluun.

1. Luo [raporttinäkymä](../service-dashboards.md) ja [hae tietoja](../service-get-data.md). Tässä esimerkissä käytetään [Mahdollisuusanalyysimallia](../sample-opportunity-analysis.md).

1. Ala kirjoittaa tiedoista etsittävää asiaa koontinäyttösi ylälaidassa olevaan kysymysruutuun. 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

> [!TIP]
> Power BI -palvelun raportissa [muokkausnäkymässä](../service-reading-view-and-editing-view.md) valitaan **Esitä kysymys** yläreunan valikkorivistä. Etsi Power BI Desktop -raportista tilaa ja avaa kysymysruutu kaksoisnapsauttamalla sitä.

3. Kirjoita kysymysruutuun esimerkiksi ”mahdollisuuksien määrä”.

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   Kysymysruutu antaa ehdotuksia ja uudelleenmuotoiluja ja näyttää lopuksi kokonaismäärän.  
4. Valitse nastakuvake ![](media/power-bi-visualization-card/pbi_pintile.png) oikeasta yläkulmasta kortin lisäämiseksi raporttinäkymään.

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. Kiinnitä kortti ruutuna aiemmin luotuun raporttinäkymään tai uuteen raporttinäkymään.

   * Aiemmin luotu koontinäyttö: valitse avattavasta luetteloruudusta koontinäytön nimi. Vaihtoehtosi rajoittuvat vain nykyisessä työtilassasi oleviin raporttinäkymiin.
   * Uusi raporttinäkymä: anna uudelle raporttinäkymälle nimi, jolloin se lisätään nykyiseen työtilaasi.
6. Valitse **Kiinnitä**.

   Onnistumissanoma (oikean yläkulman lähellä) ilmaisee, että visualisointi lisättiin ruutuna raporttinäkymään.  

   ![](media/power-bi-visualization-card/power-bi-success2.png)
7. Valitse **Siirry koontinäyttöön**, jotta näet uuden ruudun. Siellä voit esimerkiksi [nimetä uudelleen, muuttaa kokoa, lisätä hyperlinkin ja sijoittaa ruudun uudelleen](../service-dashboard-edit-tile.md) raporttinäkymässä.

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- Jos kysymysruutu ei näy ollenkaan, ota yhteyttä järjestelmän tai vuokraajan järjestelmänvalvojaan.    
- Jos käytössäsi on Desktop ja kaksoisnapsauttamalla tyhjää tilaa raportti ei avaa Q&A:a, voit joutua ottamaan sen käyttöön.  Valitse **Tiedosto > Asetukset ja vaihtoehdot > Asetukset > Esiversio-ominaisuudet > Q&A** ja käynnistä Desktop uudelleen.

## <a name="format-a-card"></a>Muotoile kortti
Käytössäsi on monia vaihtoehtoja otsikoiden, tekstin, värin ja monien muiden ominaisuuksien muuttamiseen. Opit parhaiten luomalla kortin ja tutustumalla sitten Muotoilu-ruutuun. Tässä on joitakin käytössäsi olevista muotoiluasetuksista. 

1. Aloita avaamalla muotoiluruutu valitsemalla maalitelakuvake. 

    ![kortti, jossa maalitelan ääriviivat](media/power-bi-visualization-card/power-bi-format-card.png)
2. Laajenna **Arvopisteen otsikko** ja muuta väriä, kokoa ja fonttiperhettä. Jos sinulla olisi tuhansia myymälöitä, voisit käyttää **Näytä yksiköt** -toimintoa näyttääksesi myymälöiden määrän tuhansina ja hallitaksesi myös desimaalien määrää. Voit näyttää 125 832,00:n sijaan esimerkiksi 125,8 k.

3.  Laajenna **Luokan nimi** ja muuta väriä ja kokoa.

    ![tummansininen väri valittu](media/power-bi-visualization-card/power-bi-card-format.png)

4. Laajenna **Tausta** ja siirrä liukusäädin Käytössä-asentoon.  Nyt voit muuttaa taustaväriä ja läpinäkyvyyttä.

    ![liukusäädin KÄYTÖSSÄ-asennossa](media/power-bi-visualization-card/power-bi-format-color.png)

5. Jatka muotoiluasetusten tutkimista, kunnes kortti näyttää juuri siltä kuin haluat. 

    ![Kortti, kun muotoilu on valmis](media/power-bi-visualization-card/power-bi-formatted.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Yhdistelmäkaaviot Power BI:ssä](power-bi-visualization-combo-chart.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
