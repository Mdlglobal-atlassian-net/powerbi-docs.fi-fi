---
title: Raportin Suodattimet-ruutuun tutustuminen
description: Suodattimen lisääminen raporttiin Power BI -palvelussa kuluttajille
author: mihart
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/22/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: af784c772ddbdd895f7e6c576d91d4e2fec8ffeb
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73862061"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Aloita raportin Suodattimet-ruudun esittely

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Tässä artikkelissa tutustutaan raportin **Suodattimet**-ruutuun Power BI -palvelussa. Suodattimilla saat tiedoistasi näkyviin uusia merkityksiä.

Tietoja voi suodattaa Power BI:ssä monin eri tavoin. Saat lisätietoja suodattimista ohjeartikkelista [Suodattimet ja korostaminen Power BI -raporteissa](../power-bi-reports-filters-and-highlighting.md).

![Näyttökuvassa on selaimessa auki oleva raportti, jossa nuoli osoittaa Suodattimet-kohtaan.](media/end-user-report-filter/power-bi-report.png)

## <a name="working-with-the-report-filters-pane"></a>Raportin Suodattimet-ruudun käyttäminen

Kun työtoverisi jakaa raportin kanssasi, etsi **Suodattimet**-ruutu. Joskus se on kutistettuna raportin oikeassa reunassa. Laajenna se valitsemalla se.

![Näyttökuvassa on raportti, jossa Suodattimet-ruutu on laajennettuna.](media/end-user-report-filter/power-bi-expand-filter-pane.png)

**Suodattimet**-ruutu sisältää suodattimia, jotka raportin *suunnittelija* on lisännyt raporttiin. Kaltaisesi *kuluttajat* voivat käyttää olemassa olevia suodattimia ja tallentaa muutokset, mutta ette voi lisätä uusia suodattimia raporttiin. Esimerkiksi yllä olevassa näyttökuvassa suunnittelija on lisännyt kolme sivutason suodatinta: **Segmentti on Kaikki**, **Vuosi on 2014** ja **Alue on Keski**. Voit käyttää ja muuttaa näitä suodattimia, mutta et voi lisätä neljättä sivutason suodatinta.

Power BI-palvelussa raportit säilyttävät muutokset, jotka teet **Suodattimet**-ruudussa. Palvelu siirtää nämä muutokset myös raportin mobiiliversioon. 

Voit palauttaa **Suodattimet**-ruudun suunnittelijan oletusarvoihin valitsemalla **Palauta oletukset** yläreunan valikkoriviltä.

![Näyttökuvassa on Palauta oletukset -kuvake.](media/end-user-report-filter/power-bi-reset-icon.png) 

> [!NOTE]
> Jos et näe **Palauta oletukset** -valintaa, raportin *suunnittelija* on saattanut poistaa sen käytöstä. *Suunnittelija* voi myös lukita tietyt suodattimet niin, että niitä ei voi muuttaa.

## <a name="view-all-the-filters-for-a-report-page"></a>Raporttisivun kaikkien suodattimien näyttäminen

**Suodattimet**-ruudussa näkyvät kaikki suodattimet, jotka raportin tekijä on lisännyt raporttiin. **Suodattimet**-ruudussa on myös alue, jossa voit tarkastella tietoja suodattimista ja käyttää niitä. Tallenna tekemäsi muutokset tai palauta suodattimen alkuperäiset asetukset **Palauta oletukset** -toiminnolla.

Jos haluat tallentaa muutoksia, voit myös luoda oman kirjanmerkin. Lisätietoja on artikkelissa [Mitä kirjanmerkit ovat?](end-user-bookmarks.md).

**Suodattimet**-ruudusta näet erilaiset raporttisuodattimet ja voit hallita niitä: raportti, raporttisivu ja visualisointi.

Tässä esimerkissä olemme valinneet visualisoinnin, jossa on kolme suodatinta. Raporttisivulla on myös suodattimia, jotka on lueteltu **Tämän sivun suodattimet** -otsikon alla. Lisäksi koko raportilla on **päivämääräsuodatin**.

![Näyttökuvassa on visualisoinnin sisältävä raportti, jossa sen suodattimet näytetään korostettuina.](media/end-user-report-filter/power-bi-filters-pane.png)

Joidenkin suodattimien vieressä lukee **(Kaikki)** . **(Kaikki)** tarkoittaa sitä, että kaikki arvot sisältyvät suodattimeen. Yllä olevassa näyttökuvassa **Segmentti(Kaikki)** kertoo meille, että tämä raporttisivu sisältää tiedot kaikista tuotesegmenteistä. 

Kaikki tätä raporttia tarkastelevat voivat käsitellä näitä suodattimia.

### <a name="view-only-those-filters-applied-to-a-visual"></a>Vain visualisoinnissa käytettyjen suodattimien näyttäminen

Jos haluat tarkastella tarkemmin tietyssä visualisoinnissa käytettyjä suodattimia, siirrä hiiren osoitin visualisoinnin kohdalle ja tuo näkyviin suodatinkuvake ![Näyttökuva Suodatin-kuvakkeesta](media/end-user-report-filter/power-bi-filter-icon.png). Valitsemalla suodatinkuvakkeen näet ponnahdusikkunan, joka sisältää kaikki visualisointiin vaikuttavat suodattimet, osittajat ja niin edelleen. Ponnahdusikkunan suodattimet sisältävät **Suodattimet**-ruudussa näkyvät suodattimet sekä valittuun visualisointiin vaikuttavia lisäsuodattimia.

![Näyttökuvassa on luettelo suodattimista sekä nuolia, jotka osoittavat Suodattimet-ruudussa oleviin suodattimiin.](media/end-user-report-filter/power-bi-hover-filters.png)

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

Tässä esimerkissä:
1. **Sisältyy** ilmaisee, että visualisointi on ristiinsuodatettu. Tämä tarkoittaa sitä, että Utahin, Coloradon ja Texasin osavaltiot on valittu jossakin muussa tämän raporttisivun visualisoinnissa. Tässä tapauksessa kyseessä on kartta. Näiden kolmen osavaltion valinta estää kaikkien muiden osavaltioiden tietojen näyttämisen valitussa palkkikaaviossa.  

1. **Päivämäärä** on suodatin, jota käytetään kaikkiin tämän raportin sivuihin, ja

1. **Alue on Keski** ja **Vuosi on 2014** ovat suodattimia, joita käytetään tässä raporttisivussa, ja

4. **Valmistaja on VanArsdel, Natura, Aliqui tai Pirum** on suodatin, jota käytetään tässä visualisoinnissa.


### <a name="search-in-a-filter"></a>Hae suodattimessa

Joskus suodattimella voi olla pitkä luettelo arvoja. Etsi ja valitse haluamasi arvo hakuruudun avulla.

![Näyttökuvassa näkyy suodattimen hakutoiminto.](media/end-user-report-filter/power-bi-search.png)

### <a name="display-filter-details"></a>Suodattimen tietojen näyttäminen

Saat paremman kuvan suodattimesta tutustumalla käytettävissä oleviin arvoihin ja määriin.  Näet suodattimen tiedot viemällä hiiren osoittimen sen päälle ja valitsemalla suodattimen nimen vieressä olevan nuolen.
  
![Näyttökuvassa on suodatin, josta näkyy valittu West-alue.](media/end-user-report-filter/power-bi-filter-expand.png)

### <a name="change-filter-selections"></a>Suodatinvalintojen muokkaaminen

Voit etsiä tiedoista merkityksiä suodattimien avulla. Voit muokata suodatinvalintoja kentän nimen vieressä olevalla avattavan valikon nuolella.  Vaihtoehdot vaihtelevat yksinkertaisista valinnoista päivämäärä- ja lukualueisiin. Tämä riippuu Power BI:n suodattamasta tietotyypistä ja suodattimesta. Alla olevassa kehittyneessä suodattimessa vaihdoimme puukartan **yksiköiden kokonaismäärän vuoden alusta** suodattimen arvoksi 2 000–3 000. Huomaa, että tämä muutos poistaa Prirumin puukartasta.
  
![Näyttökuvassa näkyvät raportti ja sen suodattimet, joissa puukartta näkyy valittuna.](media/end-user-report-filter/power-bi-treemap-filters.png)

> [!TIP]
> Jos haluat valita samanaikaisesti useita suodatinarvoja, paina CTRL-näppäintä valitessasi arvoja. Useimmat suodattimet tukevat monivalintaa.

### <a name="reset-filter-to-default"></a>Suodattimen palauttaminen oletuksiin

Jos haluat peruuttaa kaikki suodattimiin tekemäsi muutokset, valitse **Palauta oletukset** yläosan valikosta.  Tämä palauttaa suodattimet raportin suunnittelijan määrittämiin oletuksiin.

![Näyttökuvassa on Palauta oletukset -toiminto.](media/end-user-report-filter/power-bi-reset-icon.png)

### <a name="clear-a-filter"></a>Suodattimen tyhjentäminen

Jos haluat nollata suodattimen tilan (Kaikki), tyhjennä se valitsemalla suodattimen nimen vieressä oleva pyyhinkuvake.

![Näyttökuva pyyhinkuvakkeesta.](media/end-user-report-filter/power-bi-eraser.png)
  
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