---
title: Power BI viivakaaviot
description: Power BI viivakaaviot
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 0654dccf55b1e13f26d8ecaabee0349f0e56afc6
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65535786"
---
# <a name="line-charts-in-power-bi"></a>Power BI viivakaaviot
Viivakaaviot ovat arvopisteitä, jotka ovat pistettä edustaa ja yhdistetty viivoilla sarjan. Viivakaavion voi olla yksi tai useita rivejä. Viivakaaviot on X ja Y-akselin. 

![viivakaavio](media/power-bi-line-charts/power-bi-line.png)

## <a name="create-a-line-chart"></a>Luo viivakaavio
Nämä ohjeet käyttämällä myynti ja markkinointi esimerkkisovellus luomaan viivakaavio, joka näyttää tämän vuoden myynti luokan mukaan. Seurataksesi noutaminen appsource.comiin mallisovellusta.

1. Aloita tyhjältä raporttisivulta. Jos käytät Power BI ‑palvelua, varmista, että avaat raportin [muokkausnäkymässä](../service-interact-with-a-report-in-editing-view.md).

2. Valitse kentät-ruudussa **SalesFact** \> **yksiköt yhteensä**, ja valitse **päivämäärä** > **kuukauden**.  Power BI Luo pylväskaavion raporttipohjalla.

    ![Valitse kentät-ruudusta](media/power-bi-line-charts/power-bi-step1.png)

4. Muunna viivakaavio valitsemalla rivin malli visualisoinnit-ruudussa. 

    ![Muunna viivakaavio](media/power-bi-line-charts/power-bi-convert-to-line.png)
   

4. Suodata-viivakaavion näyttämään tiedot vuoden 2012 2014. Jos suodattimet-ruutu on kutistettu, laajenna se nyt. Valitse kentät-ruudussa **päivämäärä** \> **vuoden** ja vedä se suodattimet-ruutu. Poista kohdassa **suodattimia tässä visualisoinnissa**. 
     
    ![rivin vieressä kentät-ruudussa](media/power-bi-line-charts/power-bi-year-filter.png)

    Muuta **Advanced suodattimet** - **perustason suodattimet** ja valitse **2012**, **2013** ja **2014**.

    ![Vuosi Filter](media/power-bi-line-charts/power-bi-filter-year.png)

6. Voit vaihtoehtoisesti [säätää kaavion tekstin väriä ja kokoa](power-bi-visualization-customize-title-background-and-legend.md). 

    ![Suurenna fonttikokoa ja muuta Y axisfont](media/power-bi-line-charts/power-bi-line-3years.png)

## <a name="add-additional-lines-to-the-chart"></a>Lisää kaavioon Lisää rivejä
Viivakaaviot voi olla useita eri rivejä. Ja joissakin tapauksissa rivien arvot voivat olla eriäviä ja että ne eivät näy hyvin. Katsotaan lisääminen Lisää rivejä Microsoftin nykyinen kaavion ja oppia miten meidän kaavion kun edustaa rivien arvot ovat hyvin erilaiset. 

### <a name="add-additional-lines"></a>Lisää Lisää rivejä
Sijaan Katsomme yksiköitä yhteensä kaikkien alueiden yksittäisen viivana kaaviossa, voimme jaetaanko yksiköitä yhteensä alueen mukaan. Lisää rivejä lisätä vetämällä **Geo** > **alueen** selite-kohtaan.

   ![Kukin alue yksi rivi](media/power-bi-line-charts/power-bi-line-regions.png)


### <a name="use-two-y-axes"></a>Kahden Y-akseleille käyttää
Entä jos haluat kokonaismyynti ja yksiköiden kokonaismäärä samasta kaaviosta? Myyntiluvut on paljon suurempi kuin yksikkö numeroita, tekemistä viivakaavio käyttökelvottomia. Itse asiassa yksiköitä yhteensä punainen rivi tulee olla nolla.

   ![Eriytyvä erittäin arvot](media/power-bi-line-charts/power-bi-diverging.png)

Yhden kaavion erittäin erkautuva arvojen näyttämiseksi käyttää yhdistelmäkaaviota. Saat kaikki Yhdistelmäkaaviot lukemalla [Power BI-Yhdistelmäkaaviot](power-bi-visualization-combo-chart.md). Tässä esimerkissä alla voimme näyttää myynti- ja yksiköt yhteen yhden kaavion lisäämällä toisen Y-akselin. 

   ![Eriytyvä erittäin arvot](media/power-bi-line-charts/power-bi-dual-axes.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Yksi viivakaavio ei voi olla kaksi Y-akselia.  Sinun tulee käyttää yhdistelmäkaaviota sen sijaan.
* Yllä esimerkkejä kaaviot muotoiltiin Suurenna fonttikokoa muuttaa fonttiväri, akselin otsikoiden lisääminen, center kaavion otsikon ja selitteen, Aloita kummatkin akselit ja nolla. Muotoilu-ruutu (maalirullakuvake) on suuri mahdollisuuksia kaavioiden näyttää ne haluamallasi tavalla. Paras tapa oppia on avata muotoilu-ruutu ja tutkia.

## <a name="next-steps"></a>Seuraavat vaiheet

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)


