---
title: Tietojen vieminen Power BI -visualisoinnista
description: Tietojen vieminen raportin tai koontinäytön visualisoinnista ja tarkasteleminen Excelissä.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: jtlLGRKBvXY
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: b5e5463f19c95106a026770ad987f013f472e541
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973962"
---
# <a name="export-data-from-visualizations"></a>Tietojen vieminen visualisoinneista
Jos haluat tarkastella tietoja, joita käytetään visualisoinnin luonnissa, voit [näyttää kyseiset tiedot Power BI:ssä](service-reports-show-data.md) tai viedä tiedot Exceliin .xlsx- tai .csv-tiedostona.   

Katso videolta, miten tiedot viedään raportin visualisoinnista, tallennetaan .xlsx-tiedostoksi ja avataan Excelissä. Kokeile sitten itse noudattamalla videon alapuolella olevia vaiheittaisia ohjeita.

<iframe width="560" height="315" src="https://www.youtube.com/embed/KjheMTGjDXw" frameborder="0" allowfullscreen></iframe>

## <a name="from-a-visualization-on-a-power-bi-dashboard"></a>Power BI -koontinäytön visualisoinnista
1. Valitse visualisoinnin oikean yläkulman kolme pistettä.
   
    ![](media/power-bi-visualization-export-data/pbi-export-tile3.png)
2. Valitse **Vie tiedot** -kuvake.
   
    ![](media/power-bi-visualization-export-data/pbi_export_dash.png)
3. Tiedot viedään .csv-tiedostoon. Jos visualisointi on suodatettu, myös ladatut tiedot suodatetaan.
4. Selain kehottaa tallentamaan tiedoston.  Kun tiedosto on tallennettu, avaa se Excelissä.
   
    ![](media/power-bi-visualization-export-data/pbi-export-to-excel.png)

## <a name="from-a-visualization-in-a-report"></a>Raportin visualisoinnista
Seuraa mukana avaamalla [Hankinta-analyysimallin raportti](sample-procurement.md) [muokkausnäkymässä](service-reading-view-and-editing-view.md). [Lisää uusi tyhjä raporttisivu](power-bi-report-add-page.md). Lisää sitten kooste ja visualisoinnin tason suodatin noudattamalla alla olevia ohjeita.

1. Luo uusi pylväskaavio.  Valitse Kentät-ruudussa **Sijainti > Kaupunki** ja **Lasku > Alennusprosentti**.  Voit joutua siirtämään **alennusprosentin** Arvo-kohtaan. 
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data3.png)
2. Muuta **alennusprosentin** kooste **määrästä** **keskiarvoksi**. Arvo-kohdassa valitse **alennusprosentin** (voi myös olla **alennusprosentin määrä**) oikealla puolella oleva nuoli ja valitse **Keskiarvo**.
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data6.png)
3. Lisää suodatin kohdassa **Kaupunki** ja poista **Atlanta**.
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data4.png)
   
   Nyt voit kokeilla molempia tietojen vientivaihtoehtoja.
4. Valitse visualisoinnin oikean yläkulman kolme pistettä. Valitse **Vie tiedot**.
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data2.png)
5. Jos visualisoinnissa on kooste (esimerkiksi jos olet muuttanut **määrän** *keskiarvoksi*, **summaksi** tai *vähimmäisarvoksi*), sinulla on kaksi vaihtoehtoa: **Yhteenvedetyt tiedot** ja **Pohjana olevat tiedot**. Lue lisätietoja koosteista artikkelissa [Koosteet Power BI:ssä](service-aggregates.md).
   
    ![](media/power-bi-visualization-export-data/power-bi-export-data5.png)
6. Valitse **Yhteenvedetyt tiedot** > **Vie** ja valitse .xlsx tai .csv. Power BI vie tiedot.  Jos olet käyttänyt suodattimia visualisoinnissa, viedyt tiedot viedään suodatettuina. Kun valitset **Vie**, selain pyytää sinua tallentamaan tiedoston. Kun tiedosto on tallennettu, avaa se Excelissä.
   
   **Yhteenvedetyt tiedot**: Valitse tämä asetus, jos sinulla ei ole koostetta tai jos sinulla on kooste, mutta et halua nähdä koko erittelyä. Jos sinulla on palkkikaavio 4 palkilla, saat 4 tietoriviä. Yhteenvedetyt tiedot voidaan tallentaa .xlsx- tai .csv-muodossa.
   
   Tässä esimerkissä Excel-vienti näyttää kunkin kaupungin kokonaissumman. Koska Atlanta on suodatettu pois, se ei sisälly tuloksiin.  Laskentataulukon ensimmäisellä rivillä näkyy suodattimet, joita käytettiin poimittaessa tietoja Power BI:stä.
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data7.png)
7. Kokeile nyt valita **Pohjana olevat tiedot** > **Vie** ja sitten .xlsx. Power BI vie tiedot. Jos olet käyttänyt suodattimia visualisoinnissa, viedyt tiedot viedään suodatettuina. Kun valitset **Vie**, selain pyytää sinua tallentamaan tiedoston. Kun tiedosto on tallennettu, avaa se Excelissä.
   
   >[!WARNING]
   >Viemällä pohjana olevat tiedot käyttäjät voivat tarkastella kaikkia yksityiskohtaisia tietoja – kaikissa sarakkeissa. Power BI -palvelun järjestelmänvalvojat voivat poistaa tämän käytöstä organisaatiossa. Jos olet tietojoukon omistaja, voit määrittää sarakkeet ”piilotetuiksi” niin, että ne eivät näy kenttäluettelossa Power BI Desktopissa tai Power BI -palvelussa.
   
   
   **Pohjana olevat tiedot**: Valitse tämä asetus, jos visualisoinnissa ei ole koostetta ja haluat nähdä kaikki pohjana olevat tiedot. Valitsemalla *Pohjana olevat tiedot* kooste poistetaan. Kun valitset **Vie**, tiedot viedään .xlsx-tiedostoon ja selain pyytää sinua tallentamaan tiedoston. Kun tiedosto on tallennettu, avaa se Excelissä.
   
   Tässä esimerkissä Excel-vienti näyttää yhden rivin tietojoukon kullekin kaupungille ja kyseisen rivin alennusprosentin. Toisin sanoen tiedot tasoitetaan koostamisen sijaan. Laskentataulukon ensimmäisellä rivillä näkyy suodattimet, joita käytettiin poimittaessa tietoja Power BI:stä.  
   
   ![](media/power-bi-visualization-export-data/power-bi-export-data8.png)

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioon otettavat seikat
* **Power BI Desktopista** ja **Power BI -palvelusta** voidaan viedä korkeintaan 30 000 riviä .csv-tiedostoon ja
* 150 000 riviä .xlsx-tiedostoon.
* *Pohjana olevien tietojen* vienti ei toimi, jos tietolähde on reaaliaikainen Analysis Services -yhteys, versio on vanhempi kuin 2016 ja mallin taulukoilla ei ole yksilöiviä tunnuksia.  
* *Pohjana olevien tietojen* vienti ei toimi, jos *Näytä kohteet, joilla ei ole tietoja* -asetus on käytössä vietävässä visualisoinnissa.
* Käytettäessä DirectQueryä voidaan viedä enintään 16 Mt tietoja. Tästä johtuen kaikkia rivejä ei ehkä viedä, etenkin vietäessä useita sarakkeita tai vaikeasti pakattavia tietoja. Myös muut tekijät voivat kasvattaa tiedostokokoa ja vähentää vietyjen rivien määrää.
* Power BI tukee vientiä vain visualisoinneissa, jotka käyttävät tavallisia koosteita. Mallia tai raportin mittayksiköitä käyttäviä visualisointeja ei voi viedä.
* Mukautettuja visualisointeja ja R-visualisointeja ei tueta tällä hetkellä.
* Organisaation ulkopuoliset käyttäjät eivät voi viedä tietoja heidän kanssaan jaetuista koontinäytöistä. 
* Jos .csv-tiedostossa on unicode-merkkejä, teksti ei ehkä näy oikein Excelissä. Tiedoston voi avata Muistiossa ongelmitta. Esimerkiksi valuuttasymbolit ja vieraskieliset sanat ovat Unicode-merkkejä. Vaihtoehtoinen menetelmä on tuoda .csv-tiedosto suoraan Exceliin sen avaamisen sijaan. Jos haluat tehdä tämän:
  
  1. Avaa Excel
  2. Valitse **Tiedot**-välilehdellä **Nouda ulkoiset tiedot** > **tekstistä**.
* Power BI -järjestelmänvalvojat voivat poistaa tietojen viennin käytöstä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Koontinäytöt Power BI:ssä](service-dashboards.md)  
[Raportit Power BI:ssä](service-reports.md)  
[Power BI:n peruskäsitteet](service-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

