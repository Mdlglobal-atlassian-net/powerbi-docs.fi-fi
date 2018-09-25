---
title: Power BI:n Suodattimet-ruudun yleiskatsaus
description: Yleiskatsaus raportin Suodattimet-ruudusta Power BI -palvelussa ja Power BI Dashboardissa.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 19ca2c1fa04d5d2cde06d850d3d6813fa6928783
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565195"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Aloita raportin Suodattimet-ruudun esittely
Tässä artikkelissa tutustutaan tarkemmin raportin Suodattimet-ruutuun. Ruutu näkyy [Power BI -palvelun muokkausnäkymässä ja lukunäkymässä](end-user-reading-view.md) ja [Power BI Desktopin raporttinäkymässä](../desktop-report-view.md).

Tietojen suodattaminen Power BI:ssä voidaan tehdä monella eri tavalla, ja suosittelemme lukemaan ensin kohdan [Tietoja suodattimista ja korostuksista](../power-bi-reports-filters-and-highlighting.md).

## <a name="working-with-the-report-filters-pane"></a>Raportin Suodattimet-ruudun käyttäminen
Power BI Desktopissa raportit avataan raporttinäkymässä. Power BI -palvelussa raportit voidaan avata [muokkausnäkymässä tai lukunäkymässä](end-user-reading-view.md). Muokkausnäkymässä ja työpöydän raporttinäkymässä raportin omistajat voivat [lisätä suodattimia raporttiin](../power-bi-report-add-filter.md), ja kyseiset suodattimet tallennetaan raportin kanssa. Lukunäkymässä raporttia tarkastelevat henkilöt voivat käsitellä suodattimia ja tallentaa muutokset, mutta he eivät voi lisätä uusia suodattimia raporttiin.

Power BI -palvelussa raportit säilyttävät Suodattimet-ruudussa tekemäsi muutokset, ja muutokset siirtyvät myös raportin mobiiliversioon. Voit palauttaa suodatinruudun luojan oletusarvoihin valitsemalla **Palauta oletukset** yläreunan valikkoriviltä.     

## <a name="open-the-filters-pane"></a>Avaa Suodattimet-ruutu
Kun raportti on avoinna, Suodattimet-ruutu näkyy raportin piirtoalustan oikeassa reunassa. Jos et näe ruutua, laajenna se valitsemalla nuoli oikeassa yläkulmassa. Jos olet Power BI -palvelun lukutilassa, ainoa oikealla puolella käytettävissä oleva ruutu on Suodattimet-ruutu.

Tässä esimerkissä olemme valinneet visualisoinnin, jossa on 6 suodatinta. Raporttisivulla on myös suodattimia, jotka on luetteloitu **Sivutason suodattimet** -otsikon alla. Käytössä on yksi [porautumissuodatin](../power-bi-report-add-filter.md), ja koko raportissa on myös suodatin: **FiscalYear** is 2013 or 2014.

![](media/end-user-report-filter/power-bi-filter-list.png)

Joidenkin suodattimien vieressä on sana **All**, ja tämä tarkoittaa, että kaikki arvot sisältyvät suodattimeen.  Esimerkiksi **Chain(All)** alla olevassa näyttökuvassa ilmaisee, että tämä raporttisivu sisältää tietoja kaikista säilön ketjuista.  Toisaalta, raporttitason **FiscalYear is 2013 or 2014** -suodatin ilmaisee, että raportti sisältää tietoja vain tilikaudelle 2013 ja 2014.

Kaikki tätä raporttia tarkastelevat voivat käsitellä näitä suodattimia.

* Voit tarkastella suodattimen tietoja viemällä hiiren osoittimen sen päälle ja valitsemalla suodattimen vieressä olevan nuolen.
  
   ![](media/end-user-report-filter/power-bi-expan-filter.png)
* Muuta suodatinta, esimerkiksi muuta **Lindseys**-suodatin **Fashions Direct** -suodattimeksi.
  
     ![](media/end-user-report-filter/power-bi-filter-chain.png)

* Palauta suodattimet niiden alkuperäiseen tilaan valitsemalla **Palauta oletukset** yläreunan valikkoriviltä.    
    ![](media/end-user-report-filter/power-bi-reset-to-default.png)
    
* Poista suodatin valitsemalla **x**:n suodattimen nimen vieressä.
  
  Suodattimen poistaminen poistaa sen luettelosta, mutta ei poista tietoja raportista.  Esimerkiksi jos poistat **FiscalYear is 2013 or 2014** -suodattimen, tilikauden tiedot säilyvät edelleen raportissa, mutta sitä ei enää suodateta näyttämään vain tilikausia 2013 ja 2014, vaan siinä näkyvät kaikki tilikaudet, jotka ovat tiedoissa.  Kuitenkin kun poistat suodattimen, et voi muokata sitä uudelleen, koska se poistetaan luettelosta. Parempi vaihtoehto on tyhjentää suodatin valitsemalla Pyyhin-kuvakkeen ![](media/end-user-report-filter/power-bi-eraser-icon.png).
  
  ![](media/end-user-report-filter/power-bi-delete-filter.png)

## <a name="filters-in-editing-view"></a>Suodattimet muokkausnäkymässä
Kun raportti on avoinna työpöydällä tai Power BI -palvelun muokkausnäkymässä, Suodattimet-ruutu näkyy raportin piirtoalustan oikeassa reunassa **Visualisointi-ruudun** alaosassa. Jos et näe ruutua, laajenna se valitsemalla nuoli oikeassa yläkulmassa.

![](media/end-user-report-filter/power-bi-all-filters.png).  

Jos visualisointia ei ole valittuna piirtoalustalla, niin Suodattimet-ruudussa näkyvät vain ne suodattimet, jotka koskevat koko raporttisivua tai koko raporttia, sekä mahdolliset porautussuodattimet. Alla olevassa esimerkissä visualisointia ei ole valittu eikä sivun tason tai porautumissuodattimia ole, mutta käytössä on raporttitason suodatin.  

![](media/end-user-report-filter/power-bi-no-visual.png)  

Jos visualisointi on valittuna piirtoalustalla, näkyvissä ovat myös suodattimet, jotka koskevat vain kyseistä visualisointia:   

![](media/end-user-report-filter/power-bi-visual-filters.png)

Jos haluat näyttää tietyn suodattimen asetukset, valitse suodattimen nimen vieressä oleva alanuoli.  Seuraavassa esimerkissä raporttitason suodattimena on 2013 ja 2014. Tämä on esimerkki **perussuodatuksesta**.  Voit näyttää lisäasetukset valitsemalla **Lisäsuodatus**.

![](media/end-user-report-filter/pbi_filterlistdropdown.jpg)

## <a name="clear-a-filter"></a>Suodattimen tyhjentäminen
 Voit tyhjentää suodattimen sekä lisäsuodatus- että perussuodatustilassa valitsemalla Pyyhin-kuvakkeen ![](media/end-user-report-filter/pbi_erasericon.jpg). 

## <a name="add-a-filter"></a>Suodattimen lisääminen
* Desktopissa ja Power BI -palvelun muokkausnäkymässä lisää suodatin visualisointiin, sivulle, porautumiseen tai raporttiin valitsemalla kentän Kentät-ruudusta ja vetämällä sen sopivaan suodattimeen, jossa näet sanat **Vedä kentät tähän**. Kun kenttä on lisätty suodattimena, voit hienosäätää sitä perussuodatuksen ja lisäsuodatuksen ohjausobjekteilla (kuvattu alla).

* **Uuden kentän vetäminen visuaalisen tason suodatinalueelle ei lisää kenttää visualisointiin**, mutta sen avulla voit suodattaa visualisoinnin tällä uudella kentällä. Alla olevassa esimerkissä **Ketju** lisätään uutena suodattimena visualisointiin. Huomaa, että pelkkä **Ketju**-suodattimen lisääminen ei muuta visualisointia, ennen kuin käytät perus- tai lisäsuodatuksen ohjausobjekteja.

    ![](media/end-user-report-filter/power-bi-visual-filter.gif)

* Kaikki visualisoinnin luomisessa käytettävät kentät ovat myös käytettävissä suodattimina. Aktivoi ensin visualisointi valitsemalla se. Kentät, jotka ovat käytössä visualisoinnissa, on lueteltu Visualisoinnit-ruudussa ja Suodattimet-ruudussa **Visuaalisen tason suodattimet** -otsikon alla.
  
   ![](media/end-user-report-filter/power-bi-visual-filter.png)  
  
   Voit hienosäätää kenttiä perussuodatuksen ja lisäsuodatuksen ohjausobjekteilla (kuvattu alla).

## <a name="types-of-filters-text-field-filters"></a>Suodatintyyppejä: tekstikentän suodattimet
### <a name="list-mode"></a>Luettelotila
Valintaruudun valinta joko valitsee tai poistaa arvon valinnan. **Kaikki**-valintaruutua käyttämällä kaikkien valintaruutujen tila voidaan ottaa käyttöön tai poistaa käytöstä. Valintaruudut edustavat kaikkia käytettävissä olevia arvoja kyseiselle kentälle.  Kun säädät suodatinta, oikaisu päivittyy tekemiesi valintojen mukaiseksi. 

![](media/end-user-report-filter/pbi_restatement.png)

Huomaa, miten oikaisussa lukee nyt ”is Amarilla or Carretera”.

### <a name="advanced-mode"></a>Mukautettu tila
Valitse **Lisäsuodatus** vaihtaaksesi mukautettuun tilaan. Avattavan valikon ohjausobjektien ja tekstiruutujen avulla voit määrittää sisällytettävät kentät. Valitsemalla välillä **Ja** ja **Tai**, voit luoda monimutkaisia suodatinlausekkeita. Valitse **Käytä suodatinta** -painike, kun olet määrittänyt haluamasi arvot.  

![](media/end-user-report-filter/aboutfilters.png)

## <a name="types-of-filters-numeric-field-filters"></a>Suodatintyyppejä: numeerisen kentän suodattimet
### <a name="list-mode"></a>Luettelotila
Jos arvot ovat rajattuja, kentän nimen valitseminen tuo näkyviin luettelon.  Katso yläpuolella olevasta kohdasta **Tekstikentän suodattimet** &gt; **Luettelotila** ohjeita valintaruutujen käyttämiseen.   

### <a name="advanced-mode"></a>Mukautettu tila
Jos arvot ovat loputtomia tai edustavat aluetta, kentän nimen valitseminen avaa lisäsuodatuksen tilan. Avattavan valikon ja tekstiruutujen avulla voit määrittää arvoalueen, jonka haluat nähdä. 

![](media/end-user-report-filter/pbi_dropdown-and-text.png)

Valitsemalla välillä **Ja** ja **Tai**, voit luoda monimutkaisia suodatinlausekkeita. Valitse **Käytä suodatinta** -painike, kun olet määrittänyt haluamasi arvot.

## <a name="types-of-filters-date-and-time"></a>Suodatintyyppejä: päivämäärä ja aika
### <a name="list-mode"></a>Luettelotila
Jos arvot ovat rajattuja, kentän nimen valitseminen tuo näkyviin luettelon.  Katso yläpuolella olevasta kohdasta **Tekstikentän suodattimet** &gt; **Luettelotila** ohjeita valintaruutujen käyttämiseen.   

### <a name="advanced-mode"></a>Mukautettu tila
Jos kenttäarvot ilmaisevat päivämäärää tai kellonaikaa, voit määrittää aloitus- tai lopetusajan käyttämällä Päivämäärä ja aika -suodattimia.  

![](media/end-user-report-filter/pbi_date-time-filters.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Suodattimet ja korostaminen raporteissa](../power-bi-reports-filters-and-highlighting.md)  
[Suodattimien ja korostamisen käsitteleminen raportin lukunäkymässä](end-user-reading-view.md)  
[Suodattimien luominen raportin muokkausnäkymässä](../power-bi-report-add-filter.md)  
[Muuta raportin visualisointien ristiinsuodatusta ja ristiinkorostusta suhteessa toisiinsa](end-user-interactions.md)

Lue lisää [Power BI -raporteista](end-user-reports.md)  
[Power BI:n peruskäsitteet](end-user-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

