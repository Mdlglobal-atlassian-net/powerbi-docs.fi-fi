---
title: Tietojen vieminen Power BI -visualisoinnista
description: Vie tiedot raportin visualisoinnista sekä raporttinäkymän visualisoinnista ja avaa ne Excelissä.
author: mihart
ms.reviewer: cmfinlan
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/22/2020
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: 27128618fc594a8b7259a3de3862c6766eaecd86
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2020
ms.locfileid: "76537493"
---
# <a name="export-data-from-a-visual"></a>Tietojen vieminen visualisoinnista

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Jos haluat nähdä visualisoinnin luomiseen käytetyt tiedot, [voit näyttää kyseiset tiedot Power BI:ssä](end-user-show-data.md) tai viedä ne tiedot Exceliin. Tietojen vienti edellyttää sopivaa käyttöoikeutta sekä sisällön muokkausoikeuksia. Jos vieminen ei onnistu, ota yhteys Power BI -järjestelmänvalvojaasi. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Power BI -raporttinäkymän visualisoinnista

1. Aloita Power BI -raporttinäkymästä. Käytämme ***Markkinointi ja myynti*** -mallisovelluksen raporttinäkymää. Voit [ladata kyseisen sovelluksen osoitteesta AppSource.com](https://appsource.microsoft.com/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282).

    ![Sovelluksen raporttinäkymä](media/end-user-export/power-bi-dashboards.png)

2. Kun viet osoittimen visualisoinnin päälle, näet **Enemmän vaihtoehtoja** (...) sekä napsauttamalla avattavan toimintovalikon.

    ![Valikko, joka avautuu valitessa kolme pistettä](media/end-user-export/power-bi-options-menu.png)

3. Valitse **Vie .csv-tiedostoon**.

4. Selaimestasi riippuu, mitä seuraavaksi tapahtuu. Sinua saatetaan kehottaa tallentamaan tiedosto tai selaimen alareunassa voidaan näyttää linkki vietyyn tiedostoon. 

    ![Chrome-selain, jossa näkyy linkki vietyyn tiedostoon](media/end-user-export/power-bi-dashboard-exports.png)

5. Avaa tiedosto Excelissä. 

    > [!NOTE]
    > Jos sinulla ei ole käyttöoikeuksia tietoihin, et voi viedä etkä avata niitä Excelissä.  

    ![Yksiköiden kokonaismäärän varianssi Excelissä](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Raportin visualisoinnista
Voit viedä tietoja raportin visualisoinnista .csv- ja .xlsx (Excel) -muodossa. 

1. Valitse jokin raporttinäkymän ruutu, jolloin sen pohjana oleva raportti avautuu.  Tässä esimerkissä valitaan sama visualisointi kuin yllä (*Yksiköiden kokonaismäärän varianssiprosentti vuoden alusta)* . 

    ![Korostettu raporttinäkymän ruutu](media/end-user-export/power-bi-export-reports.png)

    Koska tämä ruutu luotiin *Myynti ja markkinointi* -malliraportista, kyseinen raportti avautuu. Raportti avautuu sivulle, joka sisältää valitun ruudun visualisoinnin. 

2. Valitse visualisointi raportissa. Laajenna oikealla oleva **Suodattimet**-ruutu. Tässä visualisoinnissa on käytetty suodattimia. Lisätietoja suodattimista on artikkelissa [Suodattimien käyttäminen raportissa](end-user-report-filter.md).

    ![Suodattimet-ruutu valittuna](media/end-user-export/power-bi-export-filter.png)


3. Valitse **Lisää toimintoja (...)** visualisoinnin oikeasta yläkulmasta. Valitse **Vie tiedot**.

    ![Avattavasta valikosta valittujen tietojen vieminen](media/end-user-export/power-bi-export-report.png)

4. Voit viedä Yhteenvedetyt tiedot tai Pohjana olevat tiedot. Jos käytät *Myynti ja markkinointi* -mallisovellusta, **Pohjana olevat tiedot** -vaihtoehto ei ole käytössä. Saatat kuitenkin kohdata raportteja, joissa molemmat vaihtoehdot ovat käytettävissä. Niiden erot ovat seuraavat.

    **Yhteenvedetyt tiedot**: valitse tämä vaihtoehto, jos haluat viedä tietoja siitä, mitä näet visualisoinnissa juuri nyt.  Tällainen vientityyppi näyttää vain visualisoinnin nykytilan luomiseen käytetyt tiedot. Jos visualisoinnissa on käytössä suodattimia, myös vietävät tiedot suodatetaan. Esimerkiksi tässä visualisoinnissa vienti sisältää vain sellaisia tietoja, jotka koskevat vuotta 2014, Keski-aluetta ja neljää valmistajaa: VanArsdel, Natura, Aliqui ja Pirum. Jos visualisoinnissa on koosteita (summa, keskiarvo jne.), myös vienti koostetaan. 
  

    **Pohjana olevat tiedot**: Valitse tämä vaihtoehto, jos haluat viedä visualisoinnissa näytetyt tiedot **sekä** lisätietoja pohjana olevasta tietojoukosta.  Ne voivat sisältää tietoja, jotka sisältyvät tietojoukkoon, mutta joita ei käytetä visualisoinnissa. Jos visualisoinnissa on käytössä suodattimia, myös vietävät tiedot suodatetaan.  Jos visualisoinnissa on koosteita (summa, keskiarvo jne.), vienti poistaa koosteen ja oleelliselta osin tiedot tasoitetaan. 

    ![Valikko, josta valitset pohjana olevat tiedot tai yhteenvedetyt tiedot](media/end-user-export/power-bi-export-underlying.png)

5. Selaimestasi riippuu, mitä seuraavaksi tapahtuu. Sinua saatetaan kehottaa tallentamaan tiedosto tai selaimen alareunassa voidaan näyttää linkki vietyyn tiedostoon. 

    ![Viety tiedosto näytettynä Microsoft Edge -selaimessa](media/end-user-export/power-bi-export-edge-browser.png)

    > [!NOTE]
    > Jos sinulla ei ole käyttöoikeuksia tietoihin, et voi viedä etkä avata niitä Excelissä.  


6. Avaa tiedosto Excelissä. Vertaa samasta visualisoinnista vietyjen tietoihin määrää raporttinäkymän samasta visualisoinnista vietyihin tietoihin. Ero on, että tämä vienti sisältää **pohjana olevia tietoja**. 

    ![Excel-malli](media/end-user-export/power-bi-underlying.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Visualisoinnin lähdetietojen näyttäminen](end-user-show-data.md)