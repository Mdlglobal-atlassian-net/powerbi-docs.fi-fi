---
title: Raportin Suodattimet-ruutuun tutustuminen
description: Suodattimen lisääminen raporttiin Power BI -palvelussa kuluttajille
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/30/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: dcf62925d8e5eef07fb6295f8d8141413947f8fb
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413060"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Aloita raportin Suodattimet-ruudun esittely
Tässä artikkelissa raportin suodattimet-ruudun tarkastellaan samankaltaisella Power BI-palvelussa. Suodattimien avulla voit löytää uusia merkityksellisiä tietoja.

Tietojen suodattaminen Power BI:ssä voidaan tehdä monella eri tavalla, ja suosittelemme lukemaan ensin kohdan [Tietoja suodattimista ja korostuksista](../power-bi-reports-filters-and-highlighting.md).

![raportti selaimessa](media/end-user-report-filter/power-bi-browser-new2.png)

## <a name="working-with-the-report-filters-pane"></a>Raportin Suodattimet-ruudun käyttäminen
Kun työtoverisi jakaa raportin kanssasi, etsi **Suodattimet**-ruutu. Joskus se on kutistettuna raportin oikeassa reunassa. Laajenna se valitsemalla se.   

![raportti selaimessa](media/end-user-report-filter/power-bi-filter-pane.png)

Suodattimet-ruutu sisältää suodattimia, jotka raportin *suunnittelija* on lisännyt raporttiin. *Kuluttajien* , kuten voit käsitellä olemassa olevia suodattimia ja tallentaa tekemäsi muutokset, mutta ei voi lisätä uusia suodattimia raporttiin. Esimerkiksi yllä olevassa näyttökuvassa suunnittelija on lisännyt kaksi sivutason suodatinta: Segmentti ja käynnissä vuoden. Voit käyttää ja muuttaa näitä suodattimia, mutta et voi lisätä kolmatta sivutason suodatinta.

Power BI-palvelussa raportit säilyttävät suodattimet-ruudussa tekemäsi muutokset ja mobile-vähimmäisversio raportin mobiiliversioon muutokset. Voit palauttaa suodatinruudun suunnittelijan oletusarvoihin valitsemalla **Palauta oletukset** yläreunan valikkoriviltä.  

![Palauta oletukset](media/end-user-report-filter/power-bi-reset-to-default.png)   

## <a name="view-all-the-filters-for-a-report-page"></a>Näytä raporttisivun kaikki suodattimet
Suodattimet-ruutu näkyy raportin mukaan lisätään kaikki suodattimet *suunnittelutyökalu*. Suodattimet-ruutu on myös alue, jossa voit tarkastella tietoja suodattimet ja käsitellä niitä. Voit tallentaa muutokset tehdään tai käytä **Palauta oletukset** palata suodatin oletusasetukset.

Jos haluat tallentaa muutokset, voit myös luoda henkilökohtainen kirjanmerkki.  Jos haluat lisätietoja, katso [kirjanmerkin lisääminen raporttiin](end-user-bookmarks.md).

On useita erilaisia raporttisuodattimet, jotka näytetään ja suodattimet-ruudun hallittujen sovellettavia visualisoinnissa, raporttisivun tai koko raportin.

Tässä esimerkissä olemme valinneet visualisoinnin, joka on 2 suodattimia. Raportin sivulla on myös suodattimet, jotka on lueteltu **suodattimia tällä sivulla** otsikon. Ja koko raportissa on suodatin päivämäärälle.

![suodatinluettelo](media/end-user-report-filter/power-bi-all-filters2.png)

Joidenkin suodattimien vieressä on sana **All**, ja tämä tarkoittaa, että kaikki arvot sisältyvät suodattimeen.  Esimerkiksi **Segment(All)** yllä olevassa näyttökuvassa kertoo, että tämä raporttisivu sisältää tietoja tuotteen segmentit.  Toisaalta, sivutason suodatin **alue on Länsi** , raporttisivu sisältää vain Länsi-alueen tiedot.

Kaikki tätä raporttia tarkastelevat voivat käsitellä näitä suodattimia.

### <a name="view-only-those-filters-applied-to-a-visual"></a>Näytä vain ottaa käyttöön visualisoinnin suodattimia
Saadaksesi lähemmin tietyn visualisoinnin suodattimet osoita sitä visualisointia, näkyviin suodatinkuvaketta ![kuvake](media/end-user-report-filter/power-bi-filter-icon.png). Valitse suodatinkuvaketta voit tarkastella ponnahdusikkunoita suodattimet, osittajat ja niin edelleen, joka vaikuttaa tämän visualisoinnin. Ponnahdusikkunat suodattimet ovat samoja suodattimia näkyvä **suodattimet** ruudussa. 

![suodatinluettelo](media/end-user-report-filter/power-bi-hover-visual-filter.png)

 
Tässä on tämä näkymä näyttää Suodatintyyppejä:
- Perussuodattimet
- Osittajat
- Ristiinkorostus
- Ristiinsuodatus
- Lisäsuodattimet
- Ylimmät N-suodattimet
- Suhteelliset päivämääräsuodattimet
- Synkronoinnin osittajat
- Sisällytä / Jätä pois -suodattimet
- Suodattimet, jotka välitetään URL-osoitteen kautta



Esimerkissä alla:
1. Näemme, että pylväskaavio on ristiinsuodatuksia.
2. **Sisältyvät** kertoo, että ristisuodatus-on **segmentin**, ja kolme ovat mukana. 
3. Osittaja on otettu käyttöön **vuosineljänneksen**.
4. **Alueen** on käytetty tämä raporttisivu suodatin ja
5. **Onvanarsdel** ja **vuoden** ovat suodattimia tähän visualisointiin.


![suodatinluettelo](media/end-user-report-filter/power-bi-visual-pop-up.png)

### <a name="search-in-a-filter"></a>Hae suodattimessa
Joskus suodatin voi olla pitkä luettelo arvoja. Hakuruudun avulla voit etsiä ja valita haluamasi arvo. 

![Hae suodattimessa](media/end-user-report-filter/power-bi-fiter-search.png)

### <a name="display-filter-details"></a>Näytä tiedot
Ymmärtää suodatin, tutustu käytettävissä olevat arvot ja määrät.  Voit tarkastella suodattimen tietoja viemällä hiiren osoitin ja valitsemalla suodattimen nimen vieressä olevan nuolen. 
  
![näyttää Lindseys-kohdan valittuna](media/end-user-report-filter/power-bi-expand-filter.png)

### <a name="change-filter-selections"></a>Muuta suodatinvalinnat
Yksi tapa hakea merkityksellisiä tietoja on käsitellä suodattimia. Voit muuttaa kenttänimen vieressä valikkonuolta kentät suodatetaan.  Suodatus- ja suodatetaan tietotyypin mukaan vaihtoehtoja alueen tunnistetaan päivämäärillä tai numeroilla alueet luettelosta yksinkertainen vaihtoehdosta. Suodattimessa Lisäasetukset alla, suodatin vaihtaminen **yhteensä yksiköt vuoden alusta** -3 000 – 2 000 puukartan. Huomaa, että tämä poistaa Prirum puukartan. 
  
![näyttää Fashions Direct -kohdan valittuna](media/end-user-report-filter/power-bi-filter-treemap.png)

> [!TIP]
> Voit valita useamman kuin yhden suodattimen arvo kerrallaan, pitämällä CTRL-näppäintä. Useimmat suodattimet tue Monivalinta. 

### <a name="reset-filter-to-default"></a>Palauta oletukset suodatin
Jos haluat pois kaikki muutokset takaisin tekemäsi suodattimia, valitse **Palauta oletukset** yläreunan valikkoriviltä.  Palautetaan suodattimet niiden alkuperäiseen tilaan, kuten raportti on määritetty *suunnittelutyökalu*. 

![Palauta oletukset](media/end-user-report-filter/power-bi-reset-to-default.png)
    
### <a name="clear-a-filter"></a>Suodattimen tyhjentäminen
Onko vain yksi suodatin, jonka haluaisit määritettävät **(kaikki)** , poista se valitsemalla pyyhin-kuvakkeen ![ pyyhin-kuvakkeen ](media/end-user-report-filter/power-bi-eraser-icon.png) suodattimen nimen vieressä.
  
<!--  too much detail for consumers

## Types of filters: text field filters
### List mode
Ticking a checkbox either selects or deselects the value. The **All** checkbox can be used to toggle the state of all checkboxes on or off. The checkboxes represent all the available values for that field.  As you adjust the filter, the restatement updates to reflect your choices. 

![list mode filter](media/end-user-report-filter/power-bi-restatement-new.png)

Note how the restatement now says "is Mar, Apr or May".

### Advanced mode
Select **Advanced Filtering** to switch to advanced mode. Use the dropdown controls and text boxes to identify which fields to include. By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.  

![advanced mode](media/end-user-report-filter/power-bi-advanced.png)

## Types of filters: numeric field filters
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the values are infinite or represent a range, selecting the field name opens the advanced filter mode. Use the dropdown and text boxes to specify a range of values that you want to see. 

![advanced filter](media/end-user-report-filter/power-bi-dropdown-and-text.png)

By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.

## Types of filters: date and time
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the field values represent date or time, you can specify a start/end time when using Date/Time filters.  

![datetime filter](media/end-user-report-filter/pbi_date-time-filters.png)

-->

## <a name="next-steps"></a>Seuraavat vaiheet
[Lue, miksi ja miten visualisoinneilla on ristiinsuodatus ja ristiinkorostus suhteessa toisiinsa raportin sivulla](end-user-interactions.md)