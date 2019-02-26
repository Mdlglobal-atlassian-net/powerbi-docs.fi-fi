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
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 2303f5b357008de141f084eb0394701420a24dbe
ms.sourcegitcommit: a054782370dec56d49bb205ee10b7e2018f22693
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/22/2019
ms.locfileid: "56661487"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Aloita raportin Suodattimet-ruudun esittely
Tässä artikkelissa tutustutaan raportin Suodattimet-ruutuun Power BI -palvelussa.

Tietojen suodattaminen Power BI:ssä voidaan tehdä monella eri tavalla, ja suosittelemme lukemaan ensin kohdan [Tietoja suodattimista ja korostuksista](../power-bi-reports-filters-and-highlighting.md).

![raportti selaimessa](media/end-user-report-filter/power-bi-browser.png)

## <a name="working-with-the-report-filters-pane"></a>Raportin Suodattimet-ruudun käyttäminen
Kun työtoverisi jakaa raportin kanssasi, etsi **Suodattimet**-ruutu. Joskus se on kutistettuna raportin oikeassa reunassa. Laajenna se valitsemalla se.   

![raportti selaimessa](media/end-user-report-filter/power-bi-expanded.png)

Suodattimet-ruutu sisältää suodattimia, jotka raportin *suunnittelija* on lisännyt raporttiin. Kaltaisesi *kuluttajat* voivat käsitellä suodattimia ja tallentaa muutokset, mutta he eivät voi lisätä uusia suodattimia raporttiin. Esimerkiksi yllä olevassa näyttökuvassa suunnittelija on lisännyt kaksi sivutason suodatinta: Segmentti ja Vuosi. Voit käyttää ja muuttaa näitä suodattimia, mutta et voi lisätä kolmatta sivutason suodatinta.

Power BI -palvelussa raportit säilyttävät Suodattimet-ruudussa tekemäsi muutokset, ja muutokset siirtyvät myös raportin mobiiliversioon. Voit palauttaa suodatinruudun suunnittelijan oletusarvoihin valitsemalla **Palauta oletukset** yläreunan valikkoriviltä.     

## <a name="open-the-filters-pane"></a>Avaa Suodattimet-ruutu
Kun raportti on avoinna, Suodattimet-ruutu näkyy raportin piirtoalustan oikeassa reunassa. Jos et näe ruutua, laajenna se valitsemalla nuoli oikeassa yläkulmassa.  

Tässä esimerkissä olemme valinneet visualisoinnin, jossa on 6 suodatinta. Raporttisivulla on myös suodattimia, jotka on luetteloitu **Sivutason suodattimet** -otsikon alla. Käytössä on yksi [porautumissuodatin](../power-bi-report-add-filter.md), ja koko raportissa on myös suodatin:  **Tilivuosi** on 2013 tai 2014.

![suodatinluettelo](media/end-user-report-filter/power-bi-filter-list.png)

Joidenkin suodattimien vieressä on sana **All**, ja tämä tarkoittaa, että kaikki arvot sisältyvät suodattimeen.  Esimerkiksi **Chain(All)** alla olevassa näyttökuvassa ilmaisee, että tämä raporttisivu sisältää tietoja kaikista säilön ketjuista.  Toisaalta raporttitason **FiscalYear is 2013 or 2014** -suodatin ilmaisee, että raportti sisältää tietoja vain tilikaudelle 2013 ja 2014.

Kaikki tätä raporttia tarkastelevat voivat käsitellä näitä suodattimia.

- Etsi ja valitse haluamasi arvo hakemalla sivusta, visualisoinnista, raportista ja porautumissuodattimista. 

    ![Hae suodattimessa](media/end-user-report-filter/power-bi-filter-search.png)

- Voit tarkastella suodattimen tietoja viemällä hiiren osoittimen sen päälle ja valitsemalla suodattimen vieressä olevan nuolen.
  
   ![näyttää Lindseys-kohdan valittuna](media/end-user-report-filter/power-bi-expan-filter.png)
* Muuta suodatinta, esimerkiksi muuta **Lindseys**-suodatin **Fashions Direct** -suodattimeksi.
  
     ![näyttää Fashions Direct -kohdan valittuna](media/end-user-report-filter/power-bi-filter-chain.png)

* Palauta suodattimet niiden alkuperäiseen tilaan valitsemalla **Palauta oletukset** yläreunan valikkoriviltä.    
    ![palauta oletukset](media/end-user-report-filter/power-bi-reset-to-default.png)
    
* Poista suodatin valitsemalla **x**:n suodattimen nimen vieressä.
  
    ![x korostettu](media/end-user-report-filter/power-bi-delete-filter.png)

  Suodattimen poistaminen poistaa sen luettelosta, mutta ei poista tietoja raportista.  Esimerkiksi jos poistat **FiscalYear is 2013 or 2014** -suodattimen, tilikauden tiedot säilyvät edelleen raportissa, mutta sitä ei enää suodateta näyttämään vain tilikausia 2013 ja 2014, vaan siinä näkyvät kaikki tilikaudet, jotka ovat tiedoissa.  Kuitenkin kun poistat suodattimen, et voi muokata sitä uudelleen, koska se poistetaan luettelosta. Parempi vaihtoehto on tyhjentää suodatin valitsemalla Pyyhin-kuvake ![ pyyhin-kuvake ](media/end-user-report-filter/power-bi-eraser-icon.png).
  
  



## <a name="clear-a-filter"></a>Suodattimen tyhjentäminen
 Valitse joko lisäsuodatus- tai perussuodatustilassa Pyyhin-kuvake  ![pyyhin-kuvake](media/end-user-report-filter/pbi_erasericon.jpg) tyhjentääksesi suodattimen. 


## <a name="types-of-filters-text-field-filters"></a>Suodatintyyppejä: tekstikentän suodattimet
### <a name="list-mode"></a>Luettelotila
Valintaruudun valinta joko valitsee tai poistaa arvon valinnan. **Kaikki**-valintaruutua käyttämällä kaikkien valintaruutujen tila voidaan ottaa käyttöön tai poistaa käytöstä. Valintaruudut edustavat kaikkia käytettävissä olevia arvoja kyseiselle kentälle.  Kun säädät suodatinta, oikaisu päivittyy tekemiesi valintojen mukaiseksi. 

![luettelotilan suodatin](media/end-user-report-filter/power-bi-restatement-new.png)

Huomaa, miten oikaisussa lukee nyt ”is Mar, Apr or May”.

### <a name="advanced-mode"></a>Mukautettu tila
Valitse **Lisäsuodatus** vaihtaaksesi mukautettuun tilaan. Avattavan valikon ohjausobjektien ja tekstiruutujen avulla voit määrittää sisällytettävät kentät. Valitsemalla välillä **Ja** ja **Tai**, voit luoda monimutkaisia suodatinlausekkeita. Valitse **Käytä suodatinta** -painike, kun olet määrittänyt haluamasi arvot.  

![mukautettu tila](media/end-user-report-filter/power-bi-advanced.png)

## <a name="types-of-filters-numeric-field-filters"></a>Suodatintyyppejä: numeerisen kentän suodattimet
### <a name="list-mode"></a>Luettelotila
Jos arvot ovat rajattuja, kentän nimen valitseminen tuo näkyviin luettelon.  Katso yläpuolella olevasta kohdasta **Tekstikentän suodattimet** &gt; **Luettelotila** ohjeita valintaruutujen käyttämiseen.   

### <a name="advanced-mode"></a>Mukautettu tila
Jos arvot ovat loputtomia tai edustavat aluetta, kentän nimen valitseminen avaa lisäsuodatuksen tilan. Avattavan valikon ja tekstiruutujen avulla voit määrittää arvoalueen, jonka haluat nähdä. 

![lisäsuodatus](media/end-user-report-filter/power-bi-dropdown-and-text.png)

Valitsemalla välillä **Ja** ja **Tai**, voit luoda monimutkaisia suodatinlausekkeita. Valitse **Käytä suodatinta** -painike, kun olet määrittänyt haluamasi arvot.

## <a name="types-of-filters-date-and-time"></a>Suodatintyyppejä: päivämäärä ja aika
### <a name="list-mode"></a>Luettelotila
Jos arvot ovat rajattuja, kentän nimen valitseminen tuo näkyviin luettelon.  Katso yläpuolella olevasta kohdasta **Tekstikentän suodattimet** &gt; **Luettelotila** ohjeita valintaruutujen käyttämiseen.   

### <a name="advanced-mode"></a>Mukautettu tila
Jos kenttäarvot ilmaisevat päivämäärää tai kellonaikaa, voit määrittää aloitus- tai lopetusajan käyttämällä Päivämäärä ja aika -suodattimia.  

![päivämäärä ja aika -suodatin](media/end-user-report-filter/pbi_date-time-filters.png)


## <a name="next-steps"></a>Seuraavat vaiheet
[Lue, miksi ja miten visualisoinneilla on ristiinsuodatus ja ristiinkorostus suhteessa toisiinsa raportin sivulla](end-user-interactions.md)