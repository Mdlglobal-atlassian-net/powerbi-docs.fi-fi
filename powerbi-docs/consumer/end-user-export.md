---
title: Tietojen vieminen Power BI -visualisoinnista
description: Vie tiedot raportin visualisoinnista sekä raporttinäkymän visualisoinnista ja avaa ne Excelissä.
author: mihart
manager: kvivek
ms.reviewer: cmfinlan
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/11/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: 80033cafbe66303a1d6f55bba61f7d19449dc45b
ms.sourcegitcommit: f34acbf9fb1ab568fd89773aaf412a847f88dd34
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/18/2019
ms.locfileid: "72589516"
---
# <a name="export-data-from-a-visual"></a>Tietojen vieminen visualisoinnista

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Jos haluat nähdä visualisoinnin luomiseen käytetyt tiedot, [voit näyttää kyseiset tiedot Power BI:ssä](end-user-show-data.md) tai viedä ne tiedot Exceliin. Tietojen vienti edellyttää sopivaa käyttöoikeutta sekä sisällön muokkausoikeuksia. Jos vieminen ei onnistu, ota yhteys Power BI -järjestelmänvalvojaasi. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Power BI -raporttinäkymän visualisoinnista

1. Aloita Power BI -raporttinäkymästä. Käytämme ***Markkinointi ja myynti*** -mallisovelluksen raporttinäkymää. Voit [ladata kyseisen sovelluksen osoitteesta AppSource.com](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282).

    ![Sovelluksen raporttinäkymä](media/end-user-export/power-bi-dashboards.png)

2. Kun viet osoittimen visualisoinnin päälle, näet kolme pistettä (...) sekä napsauttamalla avattavan toimintovalikon.

    ![Valikko, joka avautuu valitessa kolme pistettä](media/end-user-export/power-bi-action-menu.png)

3. Valitse **Vie Exceliin**.

4. Selaimestasi riippuu, mitä seuraavaksi tapahtuu. Sinua saatetaan kehottaa tallentamaan tiedosto tai selaimen alareunassa voidaan näyttää linkki vietyyn tiedostoon. 

    ![Chrome-selain, jossa näkyy linkki vietyyn tiedostoon](media/end-user-export/power-bi-dashboard-exports.png)

5. Avaa tiedosto Excelissä.  

    ![Yksiköiden kokonaismäärän varianssi Excelissä](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Raportin visualisoinnista
Voit viedä tietoja raportin visualisoinnista .csv- ja .xlsx (Excel) -muodossa. 

1. Valitse jokin raporttinäkymän ruutu, jolloin sen pohjana oleva raportti avautuu.  Tässä esimerkissä valitaan sama visualisointi kuin yllä (*Yksiköiden kokonaismäärän varianssiprosentti vuoden alusta)* . 

    ![Korostettu raporttinäkymän ruutu](media/end-user-export/power-bi-export-reports.png)

    Koska tämä ruutu luotiin *Myynti ja markkinointi* -malliraportista, kyseinen raportti avautuu. Raportti avautuu sivulle, joka sisältää valitun ruudun visualisoinnin. 

2. Valitse ruutu raportista. Laajenna oikealla oleva **Suodattimet**-ruutu. Tässä visualisoinnissa on käytetty suodattimia. Lisätietoja suodattimista on artikkelissa [Suodattimien käyttäminen raportissa](end-user-report-filter.md).

    ![Suodattimet-ruutu valittuna](media/end-user-export/power-bi-export-filter.png)


3. Valitse visualisoinnin oikean yläkulman kolme pistettä. Valitse **Vie tiedot**.

    ![Avattavasta valikosta valittujen tietojen vieminen](media/end-user-export/power-bi-export-report.png)

4. Voit viedä Yhteenvedetyt tiedot tai Pohjana olevat tiedot. Jos käytät *Myynti ja markkinointi* -mallisovellusta, **Pohjana olevat tiedot** -vaihtoehto ei ole käytössä. Saatat kuitenkin kohdata raportteja, joissa molemmat vaihtoehdot ovat käytettävissä. Niiden erot ovat seuraavat.

    **Yhteenvedetyt tiedot**: valitse tämä vaihtoehto, jos haluat viedä tietoja siitä, mitä näet visualisoinnissa.  Tällainen vientityyppi näyttää vain visualisoinnin luomiseen käytetyt tiedot. Jos visualisoinnissa on käytössä suodattimia, myös vietävät tiedot suodatetaan. Esimerkiksi tässä visualisoinnissa vienti sisältää vain sellaisia tietoja, jotka koskevat vuotta 2014, Keski-aluetta ja neljää valmistajaa: VanArsdel, Natura, Aliqui ja Pirum.
  

    **Pohjana olevat tiedot**: Valitse tämä vaihtoehto, jos haluat viedä visualisoinnissa näytetyt tiedot **sekä** lisätietoja pohjana olevasta tietojoukosta.  Ne voivat sisältää tietoja, jotka sisältyvät tietojoukkoon, mutta joita ei käytetä visualisoinnissa. 

    ![Valikko, josta valitset pohjana olevat tiedot tai yhteenvedetyt tiedot](media/end-user-export/power-bi-export-option.png)

5. Selaimestasi riippuu, mitä seuraavaksi tapahtuu. Sinua saatetaan kehottaa tallentamaan tiedosto tai selaimen alareunassa voidaan näyttää linkki vietyyn tiedostoon. 

    ![Viety tiedosto näytettynä Microsoft Edge -selaimessa](media/end-user-export/power-bi-export-edge-browser.png)


6. Avaa tiedosto Excelissä. Vertaa samasta visualisoinnista vietyjen tietoihin määrää raporttinäkymän samasta visualisoinnista vietyihin tietoihin. Ero on, että tämä vienti sisältää **pohjana olevia tietoja**. 

    ![Excel-malli](media/end-user-export/power-bi-underlying.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Visualisoinnin lähdetietojen näyttäminen](end-user-show-data.md)