---
title: Korttivisualisoinnit (suurten lukujen ruudut)
description: Kortin visualisoinnin luominen Power BI:ssä
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 37b7a85534e1ad8f1f301994dea895e098758d1b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73870984"
---
# <a name="card-visualizations"></a>Kortin visualisoinnit

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Joskus yksittäinen luku on tärkein seikka, jota haluat seurata Power BI-raporttinäytöllä tai raportissa, kuten kokonaismyynti, markkinaosuus vuositasolla tai kokonaismahdollisuudet. Tämä visualisointi on nimeltään *Kortti*. Samoin kuin lähes kaikki alkuperäiset Power BI-visualisoinnit, kortit voidaan luoda käyttäen raporttieditoria tai Q&A:ta.

![kortin visualisointi](media/power-bi-visualization-card/pbi-opptuntiescard.png)

## <a name="prerequisite"></a>Edellytys

Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** \> **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.

## <a name="option-1-create-a-card-using-the-report-editor"></a>Vaihtoehto 1: Kortin luominen raporttieditoria käyttämällä

Ensimmäinen tapa luoda kortti on käyttää Power BI Desktopin raporttieditoria.

1. Aloita tyhjältä raporttisivulta ja valitse kenttä **Myymälä** \> **Avoimien myymälöiden määrä**.

    Power BI luo pylväskaavion, jossa yksi luku.

   ![esimerkki numeroruutu kaavio](media/power-bi-visualization-card/pbi-overview-chart.png)

2. Valitse Visualisoinnit-ruudussa korttikuvake.

   ![esimerkki numeroruutu kortti](media/power-bi-visualization-card/power-bi-card-visualization.png)

Olet nyt luonut kortin raporttieditorin avulla. Alla on toinen vaihtoehto kortin luomiseen Q&A-kysymysruudun avulla.

## <a name="option-2-create-a-card-from-the-qa-question-box"></a>Vaihtoehto 2: Luo kortti Q&A-kysymysruudusta
Q&A-kysymysruutu on toinen vaihtoehto kortin luomiseen. Q&A-kysymysruutu on käytettävissä Power BI Desktopin raporttinäkymässä.

1. Aloita tyhjältä raporttisivulta

1. Valitse ikkunan yläosassa **Esitä kysymys** -kuvake. 

    Power BI luo kortin ja ruudun kysymystäsi varten. 

   ![esitä kysymys -kuvakkeen sijainti](media/power-bi-visualization-card/power-bi-q-and-a-overview.png)

2. Voit esimerkiksi kirjoittaa kysymysruutuun tekstin ”Tinan kokonaismyynti”.

    Kysymysruutu antaa ehdotuksia ja uudelleenmuotoiluja ja näyttää lopuksi kokonaismäärän.  

   ![kysymysruutu esimerkki](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

   ![kortti esimerkki kysymysmenetelmästä](media/power-bi-visualization-card/power-bi-q-and-a-card.png)

Olet nyt luonut kortin Q&A-kysymysruudun avulla. Seuraavassa on ohjeet korttisi muotoilemiseen omiin tarpeisiisi.

## <a name="format-a-card"></a>Muotoile kortti
Käytössäsi on monia vaihtoehtoja otsikoiden, tekstin, värin ja monien muiden ominaisuuksien muuttamiseen. Opit parhaiten luomalla kortin ja tutustumalla sitten Muotoilu-ruutuun. Tässä on joitakin käytössäsi olevista muotoiluasetuksista. 

Muotoilu-ruutu on käytettävissä, kun käsittelet korttia raportissa. 

1. Aloita avaamalla muotoiluruutu valitsemalla maalitelakuvake. 

    ![kortti, jossa maalitela korostettuna](media/power-bi-visualization-card/power-bi-format-card-2.png)

2. Kun kortti on valittu, laajenna **Arvopisteen otsikko** ja muuta väriä, kokoa ja fonttiperhettä. Jos sinulla olisi tuhansia myymälöitä, voisit käyttää **Näytä yksiköt** -toimintoa näyttääksesi myymälöiden määrän tuhansina ja hallitaksesi myös desimaalien määrää. Voit näyttää 125 832,00:n sijaan esimerkiksi 125,8 k.

    ![kortti ja tietojen muoto esimerkki](media/power-bi-visualization-card/power-bi-card-format-2.png)

3.  Laajenna **Luokan nimi** ja muuta väriä ja kokoa.

    ![kortti ja luokka esimerkki](media/power-bi-visualization-card/power-bi-card-format-category.png)

4. Laajenna **Tausta** ja siirrä liukusäädin Käytössä-asentoon.  Nyt voit muuttaa taustaväriä ja läpinäkyvyyttä.

    ![liukusäädin KÄYTÖSSÄ-asennossa](media/power-bi-visualization-card/power-bi-format-color-2.png)

5. Jatka muotoiluasetusten tutkimista, kunnes kortti näyttää juuri siltä kuin haluat. 

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Jos kysymysruutu ei näy ollenkaan, ota yhteyttä järjestelmän tai vuokraajan järjestelmänvalvojaan.    

## <a name="next-steps"></a>Seuraavat vaiheet
[Yhdistelmäkaaviot Power BI:ssä](power-bi-visualization-combo-chart.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
