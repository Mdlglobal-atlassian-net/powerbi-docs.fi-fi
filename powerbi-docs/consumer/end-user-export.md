---
title: Tietojen vieminen Power BI -visualisoinnista
description: Tietojen vieminen raportin visualisoinnin ja koontinäytön visualisoinnista ja tarkasteleminen Excelissä.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 4/9/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: d4384db8e05a69b138e76377e7c7b845867fa881
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61063726"
---
# <a name="export-data-from-visual"></a>Tietojen vieminen visualisoinnin
Jos haluat nähdä tiedot visualisoinnin luomiseen käytetään [tiedot näkyvät Power BI](end-user-show-data.md) tai viedä tiedot Exceliin. Voit viedä tietoja edellyttää tyyppi tai käyttöoikeutta ja sisällön muokkausoikeudet. Jos et voi viedä, ota yhteyttä Power BI-järjestelmänvalvojaan. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Power BI-koontinäytön visualisoinnista

1. Aloita Power BI-koontinäytön. Tätä käytetään koontinäytön ***markkinointi- ja mallin*** sovelluksen. Voit myös [ladata sovelluksen Appsource.comiin](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282).

    ![](media/end-user-export/power-bi-dashboard.png)

2. Osoittamalla visualisointia näyttämään kolme pistettä (...) ja valitse toiminto-valikko.

    ![](media/end-user-export/power-bi-dashboard-export-visual.png)

3. Valitse **vieminen Exceliin**.

4. Seuraavaksi tapahtuva asia riippuu, mitä selainta käytät. Sinua saatetaan kehottaa tallentamaan tiedoston tai voit viety tiedosto selaimen alareunassa linkki. 

    ![](media/end-user-export/power-bi-export-browser.png)

5. Avaa tiedosto Excelissä.  

    ![](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Raportin visualisoinnista
Voit viedä tietoja raportin visualisoinnista .csv-tai .xlsx (Excel) muoto. 

1. Valitse koontinäytön ruutua pohjana olevan raportin avaamiseksi.  Tässä esimerkissä valitsemme saman visualisoinnin kuin edellä, *yhteensä yksiköt vuoden alusta varianssiprosenteilla*. 

    ![](media/end-user-export/power-bi-export-report.png)

    Koska tämä ruutu on luotu *myynti- ja Markkinointimalli* raportin, joka on raportti, joka avautuu. Ja näyttöön avautuu sivu, joka sisältää valitun ruudun visualisointi. 

2. Valitse ruutu raportissa. Huomaa **suodattimet** ruudun oikealla puolella. Tämä visualisointi on suodatinta. Lisätietoja suodattimet, katso [käyttää suodattimia raportin](end-user-report-filter.md).

    ![](media/end-user-export/power-bi-export-filters.png)


3. Valitse visualisoinnin oikean yläkulman kolme pistettä. Valitse **Vie tiedot**.

    ![](media/end-user-export/power-bi-export-report2.png)

4. Näet viedä Summarized tietoja tai pohjana olevan eri. Jos käytät *myynti- ja markkinointimalli* sovelluksen **pohjana olevat tiedot** poistetaan käytöstä. Mutta voit kohdata raportteja, joissa molemmat vaihtoehdot ovat käytössä. Tässä on selitetty ero.

    **Yhteenvedetyt tiedot**: Valitse tämä vaihtoehto, jos haluat viedä tiedot-kohdassa visualisoinnissa.  Tämäntyyppistä vienti näyttää vain visualisoinnin luomiseen käytettyjen tietojen. Jos visualisointi on suodattimia, myös voit viedä tiedot suodatetaan. Esimerkiksi tämän visualisoinnin, vienti sisältää vain 2014 tiedot ja keskialueella, ja vain tiedot neljä valmistajat: Vanarsdelin, Natura, Aliqui ja Prirum.
  

    **Pohjana olevat tiedot**: Valitse tämä vaihtoehto, jos haluat viedä tiedot näkyvät tiedot visualisoinnin **sekä** pohjana olevan tietojoukon muita tietoja.  Tämä saattaa sisältää tietoja, jotka on sisälsi tietojoukon, mutta sitä ei käytetä visualisoinnissa. 

    ![](media/end-user-export/power-bi-export-report3.png)

5. Seuraavaksi tapahtuva asia riippuu, mitä selainta käytät. Sinua saatetaan kehottaa tallentamaan tiedoston tai voit viety tiedosto selaimen alareunassa linkki. 

    ![](media/end-user-export/power-bi-export-edge.png)


7. Avaa tiedosto Excelissä. Vertaa viedä Microsoft samaan visualisointiin koontinäytössä vietyjä tietoja tietojen määrää. Ero on, että tämän viennin sisältää **pohjana olevat tiedot**. 

    ![](media/end-user-export/power-bi-underlying.png)

