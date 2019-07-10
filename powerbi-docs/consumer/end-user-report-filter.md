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
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: ef7e4f556832f1323043a80cf219678a16511c9e
ms.sourcegitcommit: e67bacbfc5638ee97e3d2e0e7f5bd2d9aac78f9c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/02/2019
ms.locfileid: "67532833"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Aloita raportin Suodattimet-ruudun esittely

Tässä artikkelissa tutustutaan raportin **Suodattimet**-ruutuun Power BI -palvelussa. Suodattimilla saat tiedoistasi näkyviin uusia merkityksiä.

Tietoja voi suodattaa Power BI:ssä monin eri tavoin. Saat lisätietoja suodattimista ohjeartikkelista [Suodattimet ja korostaminen Power BI -raporteissa](../power-bi-reports-filters-and-highlighting.md).

![Näyttökuvassa on selaimessa auki oleva raportti, jossa nuoli osoittaa Suodattimet-kohtaan.](media/end-user-report-filter/power-bi-browser-new2.png)

## <a name="working-with-the-report-filters-pane"></a>Raportin Suodattimet-ruudun käyttäminen

Kun työtoverisi jakaa raportin kanssasi, etsi **Suodattimet**-ruutu. Joskus se on kutistettuna raportin oikeassa reunassa. Laajenna se valitsemalla se.

![Näyttökuvassa on raportti, jossa Suodattimet-ruutu on laajennettuna.](media/end-user-report-filter/power-bi-filter-pane.png)

**Suodattimet**-ruutu sisältää suodattimia, jotka raportin *suunnittelija* on lisännyt raporttiin. Kaltaisesi *kuluttajat* voivat käyttää olemassa olevia suodattimia ja tallentaa muutokset, mutta ette voi lisätä uusia suodattimia raporttiin. Esimerkiksi yllä olevassa näyttökuvassa suunnittelija on lisännyt kaksi sivutason suodatinta: **Segmentti** ja **Vuosi**. Voit käyttää ja muuttaa näitä suodattimia, mutta et voi lisätä kolmatta sivutason suodatinta.

Power BI-palvelussa raportit säilyttävät muutokset, jotka teet **Suodattimet**-ruudussa. Palvelu siirtää nämä muutokset myös raportin mobiiliversioon.

Voit palauttaa **Suodattimet**-ruudun suunnittelijan oletusarvoihin valitsemalla ![Näyttökuva Palauta oletukset -toiminnosta.](media/end-user-report-filter/power-bi-reset.png) yläreunan valikkoriviltä.

## <a name="view-all-the-filters-for-a-report-page"></a>Raporttisivun kaikkien suodattimien näyttäminen

**Suodattimet**-ruudussa näkyvät kaikki suodattimet, jotka raportin tekijä on lisännyt raporttiin. **Suodattimet**-ruudussa on myös alue, jossa voit tarkastella tietoja suodattimista ja käyttää niitä. Voit tallentaa tekemäsi muutokset tai palauttaa alkuperäiset suodatinasetukset valitsemalla **Palauta oletukset**.

Jos haluat tallentaa muutoksia, voit myös luoda oman kirjanmerkin.  Lisätietoja on artikkelissa [Mitä kirjanmerkit ovat?](end-user-bookmarks.md).

**Suodattimet**-ruudusta näet erilaiset raporttisuodattimet ja siinä voit hallita niitä. Voit käyttää niitä visualisoinnissa, raporttisivulla tai koko raportissa.

Tässä esimerkissä olemme valinneet visualisoinnin, jossa on kaksi suodatinta. Raporttisivulla on myös suodattimia, jotka on lueteltu **Tämän sivun suodattimet** -otsikon alla. Lisäksi koko raportilla on **päivämääräsuodatin**.

![Näyttökuvassa on visualisoinnin sisältävä raportti, jossa sen suodattimet näytetään korostettuina.](media/end-user-report-filter/power-bi-all-filters2.png)

Joidenkin suodattimien vieressä lukee **(Kaikki)** . **(Kaikki)** tarkoittaa sitä, että kaikki arvot sisältyvät suodattimeen. Yllä olevassa näyttökuvassa **Segmentti(Kaikki)** kertoo meille, että tämä raporttisivu sisältää tiedot kaikista tuotesegmenteistä. Jos valitset **Alue on Länsi** -sivutason suodattimen, raporttisivu sisältää tiedot vain Länsi-alueelta.

Kaikki tätä raporttia tarkastelevat voivat käsitellä näitä suodattimia.

### <a name="view-only-those-filters-applied-to-a-visual"></a>Vain visualisoinnissa käytettyjen suodattimien näyttäminen

Jos haluat tarkastella tarkemmin tietyssä visualisoinnissa käytettyjä suodattimia, siirrä hiiren osoitin visualisoinnin kohdalle ja tuo näkyviin suodatinkuvake ![Näyttökuva Suodatin-kuvakkeesta](media/end-user-report-filter/power-bi-filter-icon.png). Valitsemalla suodatinkuvakkeen näet ponnahdusikkunan, joka sisältää kaikki visualisointiin vaikuttavat suodattimet, osittajat ja niin edelleen. Ponnahdusikkunan suodattimet ovat samat suodattimet, jotka näytetään **Suodattimet**-ruudussa.

![Näyttökuvassa on luettelo suodattimista sekä nuolia, jotka osoittavat Suodattimet-ruudussa oleviin suodattimiin.](media/end-user-report-filter/power-bi-hover-visual-filter.png)

Tässä näkymässä voidaan näyttää seuraavia suodattimia:

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

Katso seuraavaa esimerkkiä.

1. Näemme, että pylväskaavio on ristiinsuodatettu.

1. **Sisältyy** kertoo meille, että ristisuodatus koskee **segmenttiä** ja että mukana on kolme.

1. **Vuosineljännes**-kohdassa on käytössä osittaja.

1. Raporttisivulla on käytössä **Alue**-suodatin.

1. Tässä visualisoinnissa ovat käytössä suodattimet **OnVanArsdel** ja **Vuosi**.

![Näyttökuvassa näkyy raportti ja sen suodattimet numeroituna luettelossa.](media/end-user-report-filter/power-bi-visual-pop-up.png)

### <a name="search-in-a-filter"></a>Hae suodattimessa

Joskus suodattimella voi olla pitkä luettelo arvoja. Etsi ja valitse haluamasi arvo hakuruudun avulla.

![Näyttökuvassa näkyy suodattimen hakutoiminto.](media/end-user-report-filter/power-bi-fiter-search.png)

### <a name="display-filter-details"></a>Suodattimen tietojen näyttäminen

Saat paremman kuvan suodattimesta tutustumalla käytettävissä oleviin arvoihin ja määriin.  Näet suodattimen tiedot viemällä hiiren osoittimen sen päälle ja valitsemalla suodattimen nimen vieressä olevan nuolen.
  
![Näyttökuvassa on suodatin, josta näkyy valittu West-alue.](media/end-user-report-filter/power-bi-expand-filter.png)

### <a name="change-filter-selections"></a>Suodatinvalintojen muokkaaminen

Voit etsiä tiedoista merkityksiä suodattimien avulla. Voit muokata suodatinvalintoja kentän nimen vieressä olevalla avattavan valikon nuolella.  Vaihtoehdot vaihtelevat yksinkertaisista valinnoista päivämäärä- ja lukualueisiin. Tämä riippuu Power BI:n suodattamasta tietotyypistä ja suodattimesta. Alla olevassa kehittyneessä suodattimessa vaihdoimme puukartan **yksiköiden kokonaismäärän vuoden alusta** suodattimen arvoksi 2 000–3 000. Näet, että tämä muutos poistaa Prirumin puukartasta.
  
![Näyttökuvassa näkyvät raportti ja sen suodattimet, joiden perusteella valittuna on Fashions Direct.](media/end-user-report-filter/power-bi-filter-treemap.png)

> [!TIP]
> Jos haluat valita samanaikaisesti useita suodatinarvoja, paina CTRL-näppäintä valitessasi arvoja. Useimmat suodattimet tukevat monivalintaa.

### <a name="reset-filter-to-default"></a>Suodattimen palauttaminen oletuksiin

Jos haluat peruuttaa kaikki suodattimiin tekemäsi muutokset, valitse **Palauta oletukset** yläosan valikosta.  Tämä palauttaa suodattimet raportin suunnittelijan määrittämiin oletuksiin.

![Näyttökuvassa on Palauta oletukset -toiminto.](media/end-user-report-filter/power-bi-reset.png)

### <a name="clear-a-filter"></a>Suodattimen tyhjentäminen

Jos haluat määrittä vain yhdelle suodattimelle **(Kaikki)** -asetuksen, tyhjennä se valitsemalla pyyhinkuvake ![Näyttökuva Pyyhin-kuvakkeesta.](media/end-user-report-filter/power-bi-eraser-icon.png) nimen vieressä.
  
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

Lue, miksi ja miten [visualisoinneilla on ristiinsuodatus ja ristiinkorostus suhteessa toisiinsa raportin sivulla](end-user-interactions.md)