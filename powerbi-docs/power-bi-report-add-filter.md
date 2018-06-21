---
title: Visualisointi-, sivu-, porautumis- tai raporttisuodattimen lisääminen raporttiin
description: Sivu-, visualisointi- tai raporttisuodattimen lisääminen raporttiin Power BI:ssä
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/26/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: e5e257fd245687f2aeb83a9ee45c0342cf16392d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34561697"
---
# <a name="add-a-filter-to-a-power-bi-service-report-in-editing-view"></a>Suodattimen lisääminen Power BI -palvelun raporttiin (muokkausnäkymässä)
> [!TIP]
> Suosittelemme lukemaan ensin artikkelin [Tietoja Power BI -raporttien suodattimista ja korostamisesta](power-bi-reports-filters-and-highlighting.md).

Tämän artikkelin esimerkeissä on käytetty Power BI-palvelua. Vaiheet ovat kuitenkin lähes samanlaiset Power BI Desktopissa.
> 
> 

## <a name="what-is-the-difference-between-report-filters-in-editing-view-versus-reading-view"></a>Raporttisuodattimien väliset erot muokkausnäkymässä ja lukunäkymässä
Raportteja voidaan käsitellä kahdessa eri näkymässä: [lukunäkymässä](service-reading-view-and-editing-view.md) ja [muokkausnäkymässä](service-interact-with-a-report-in-editing-view.md).  Käytettävissä olevat suodatusominaisuudet vaihtelevat näkymän mukaan.

* Muokkausnäkymässä voit lisätä raportti- ja sivusuodattimia sekä visuaalisia suodattimia. Suodattimet tallennetaan raporttiin. Lukunäkymässä raporttia katsovat käyttäjät voivat käsitellä lisäämiäsi suodattimia.
* Lukunäkymässä voit käsitellä raportissa olevia raportti-, porautumis- ja sivusuodattimia sekä visuaalisia suodattimia, mutta et voi lisätä uusia suodattimia. Suodattimet-ruudussa tekemäsi muutokset tallennetaan raporttiin myös silloin, kun tarkastelet raporttia mobiilisovelluksessa tai poistut raportista ja palaat siihen myöhemmin.  

> [!NOTE]
> Tässä artikkelissa kerrotaan, miten voit luoda suodattimia raporttiin **muokkausnäkymässä**.  Lisätietoja lukunäkymän suodattimista on artikkelissa [Suodattimien käsitteleminen raportissa lukunäkymässä](service-reading-view-and-editing-view.md).


## <a name="filters-available-in-the-power-bi-filters-pane"></a>Power BI:n *Suodattimet*-ruudussa käytettävissä olevat suodattimet
Suodattimet-ruutu näkyy raportin piirtoalustan oikeassa reunassa sen mukaan, onko käytössä Desktop vai Power BI. Jos et näe Suodattimet-ruutua, laajenna ruutu valitsemalla oikeasta yläkulmasta >-kuvake.

Käytössä on neljä erilaista suodatinta:

- **sivusuodatin** koskee kaikkia raporttisivulla olevia visualisointeja     
- **visuaalinen suodatin** koskee raporttisivulla olevaa yksittäistä visualisointia    
- **porautumissuodatin** koskee mitä tahansa raportin entiteettiä    
- **raporttisuodatin** koskee kaikkia raportin sivuja.    

    ![Suodattimet-ruutu Lukunäkymässä](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

Koska suodattimet *pysyvät*, kun siirryt pois raportista, Power BI säilyttää suodattimet, osittajan ja muut tietojen näkymän muutokset, jotka olet tehnyt. Näin voit jatkaa siitä, mihin jäit, kun palaat raporttiin. Jos et halua suodattimen muutosten säilyvän, valitse **Palauta oletukset** ylävalikosta.

![Pysyvät suodattimet -painike](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="add-a-filter-to-a-specific-visualization-aka-visual-filter"></a>Suodattimen lisääminen tiettyyn visualisointiin (visuaalinen suodatin)
Voit tehdä tämän seuraavilla tavoilla: 

* suodattamalla kentän, joka on jo käytössä visualisoinnissa
* määrittämällä kentän, joka ei ole käytössä visualisoinnissa, ja lisäämällä kyseisen kentän suoraan **Visuaalisen tason suodattimet** -säilöön.

### <a name="by-filtering-the-fields-already-in-the-visualization"></a>Visualisoinnissa jo käytössä olevien kenttien suodattaminen
1. Avaa [raportti muokkausnäkymässä](service-reading-view-and-editing-view.md).
   
   ![](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu (jos ne eivät ole jo avoinna).
   
   ![](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Valitse visualisointi, jotta siitä tulee aktiivinen. Kaikki visualisoinnissa käytettävät kentät määritetään **Kentät**-ruudussa ja luetellaan lisäksi **Visuaalisen tason suodattimet** -otsikon alla olevassa **Suodattimet**-ruudussa.
   
   ![](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. Tässä vaiheessa lisäämme suodattimen kenttään, joka on jo käytössä visualisoinnissa. 
   
   * Vieritä alaspäin **Visuaalisen tason suodattimet** -alueelle ja laajenna suodatettava kenttä valitsemalla nuolipainike. Tässä esimerkissä suodatamme kentän **StoreNumberName**
     
      ![](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
   * Määritä suodatusasetukseksi **Perussuodatus**, **Lisäsuodatus** tai **Ylimmät N** (katso artikkeli [Raporttisuodattimien käyttäminen](power-bi-how-to-report-filter.md)). Tässä esimerkiksi valitsemme perussuodatuksen ja valitsemme numerot 10, 11, 15 ja 18.
     
      ![](media/power-bi-report-add-filter/power-bi-basic-filters.png) 
   * Visualisointi muuttuu vastaamaan uutta suodatinta. Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät voivat käsitellä suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.
     
      ![](media/power-bi-report-add-filter/power-bi-filter-effect.png)
5. Nyt lisäämme visualisointiin täysin uuden kentän visuaalisen tason suodattimena.
   
   * Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena visuaalisen tason suodattimena, ja vedä se **Visuaalisen tason suodattimet** -alueelle.  Tässä esimerkissä vedämme **Aluejohtaja**-kentän **Visuaalisen tason suodattimet** -säilöön ja valitsemme vain henkilön Antti Mäntylä. 
     
      ![](media/power-bi-report-add-filter/power-bi-andrew.png)
   * Huomaa, että **Aluejohtaja**-kenttää *ei* lisätä itse visualisointiin. Visualisointi muodostuu Akseli-kohdan arvosta **StoreNumberName** ja Arvo-kohdan arvosta **This Year Sales**.  
     
      ![](media/power-bi-report-add-filter/power-bi-visualization.png)
   * Visualisointi suodatetaan nyt niin, että siinä näkyvät vain Antin tiettyjen myymälöiden tämän vuoden myynti.
     
     ![](media/power-bi-report-add-filter/power-bi-filtered-andrew.png)

## <a name="add-a-filter-to-an-entire-page-aka-page-view-filter"></a>Suodattimen lisääminen koko sivulle (sivunäkymän suodatin)
1. Avaa [raportti muokkausnäkymässä](service-reading-view-and-editing-view.md).
2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu (jos ne eivät ole jo avoinna).
3. Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena sivutason suodattimena, ja vedä se **Sivutason suodattimet** -alueelle.  
4. Valitse suodatettavat arvot ja määritä suodatusasetukseksi **Perussuodatus** tai **Lisäsuodatus** (katso artikkeli [Raporttisuodattimien käyttäminen](power-bi-how-to-report-filter.md)).
   
   Kaikki sivulla olevat visualisoinnit, joita tämä suodatin koskee, piirretään uudelleen, jotta ne vastaavat tehtyjä muutoksia. 
   
   ![](media/power-bi-report-add-filter/filterpage.gif)

Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät voivat käsitellä suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.

## <a name="add-a-drillthrough-filter"></a>Porautumissuodattimen lisääminen
Power BI -palvelun ja Power BI Desktopin porautumisen avulla voit luoda *kohderaporttisivun*, jolla keskitytään tiettyyn entiteettiin, kuten toimittajaan, asiakkaaseen tai valmistajaan. Nyt käyttäjät voivat muilla raporttisivuilla napsauttaa hiiren kakkospainikkeella kyseisen entiteetin arvopistettä ja porautua tiettyyn entiteettiin keskittyvälle sivulle.

### <a name="create-a-drillthrough-filter"></a>Porautumissuodattimen luominen
Avaa Asiakkaan tuottavuuden malli muokkausnäkymässä. Oletetaan, että haluat luoda sivun, jolla keskitytään Johtaja-liiketoiminta-alueisiin.   

1. Lisää raporttiin uusi sivu ja anna sen nimeksi **Tiimijohtaja**. Tämä on porautumisen *kohdesivu*.
2. Lisää visualisointeja, jotka seuraavat tiimijohtajien liiketoiminta-alueiden avaintietoja.    
3. Lisää porautumissuodattimiin myös **Johtaja > Johtajan nimi**.    
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    Huomaa, että Power BI lisää taaksepäin osoittavan nuolen raporttisivulle.  Valitsemalla taaksepäin osoittavan nuolen käyttäjät voivat palata *alkuperäiselle* raporttisivulle eli sivulle, jolla he valitsivat porautumisen. Taaksepäin osoittava nuoli toimii vain lukunäkymässä.
   
     ![](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>Porautumissuodattimen käyttäminen
Katsotaan, miten porautumissuodatin toimii.

1. Aloita **Tiimin tuloskortti** -raporttisivulta.    
2. Oletetaan, että olet Antero Mäntylä ja haluat nähdä Tiimijohtaja-raporttisivun, joka on suodatettu näyttämään vain sinun tietosi.  Avaa Porautuminen-valikkovaihtoehto napsauttamalla hiiren kakkospainikkeella vasemman yläreunan alueen kaaviosta mitä tahansa vihreää arvopistettä.
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. Poraudu **Tiimijohtaja**-raporttisivulle valitsemalla **Porautuminen > Tiimijohtaja**. Sivu suodatetaan näyttämään tietoja hiiren kakkospainikkeella napsauttamastasi arvopisteestä – tässä tapauksessa Antti Mäntylästä. Vain porautumissuodattimissa oleva kenttä välitetään porautumisraporttisivulle.  
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-filter-to-an-entire-report-aka-report-filter"></a>Suodattimen lisääminen koko raporttiin (raporttisuodatin)
1. Avaa [raportti muokkausnäkymässä](service-reading-view-and-editing-view.md).
2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu (jos ne eivät ole jo avoinna).
3. Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena raporttitason suodattimena, ja vedä se **Raporttitason suodattimet** -alueelle.  
4. Valitse suodatettavat arvot (katso artikkeli [Raporttisuodattimien käyttäminen](power-bi-how-to-report-filter.md)).

    Aktiivisella sivulla ja kaikilla raportin sivuilla olevat visualisoinnit muuttuvat uuden suodattimen mukaisiksi. Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät voivat käsitellä suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.

1. Palaa edelliselle raporttisivulle valitsemalla taaksepäin osoittava nuoli.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

- Joissakin tilanteissa visuaalisen tason suodatin ja sivutason suodatin voivat palauttaa eri tuloksia.  Esimerkiksi, kun lisäät visuaalisen tason suodattimen, Power BI suodattaa kootut tulokset.  Oletuskooste on Summa, mutta voit [muuttaa koostetyyppiä](service-aggregates.md).  

    Kun lisäät sivutason suodattimen, Power BI suodattaa ilman koostamista.  Tämä johtuu siitä, että sivulla voi olla useita visualisointeja, joista jokainen voi hyödyntää eri koostetyyppiä.  Suodatinta käytetään siis jokaisella tietorivillä.

- Jos Kentät-ruutu ei ole näkyvissä, varmista, että valittuna on raportin [muokkausnäkymä](service-interact-with-a-report-in-editing-view.md).    
- Jos olet tehnyt paljon muutoksia suodattimiin ja haluat palata raportin tekijän oletusasetuksiin, valitse **Palauta oletukset** ylävalikosta.

## <a name="next-steps"></a>Seuraavat vaiheet
 [Raporttisuodattimien käyttäminen](power-bi-how-to-report-filter.md)

  [Suodattimet ja korostaminen raporteissa](power-bi-reports-filters-and-highlighting.md)

[Suodattimien ja korostamisen käsitteleminen raportin lukunäkymässä](service-reading-view-and-editing-view.md)

[Raportin visualisointien ristiinsuodatuksen ja ristiinkorostuksen muuttaminen suhteessa toisiinsa](service-reports-visual-interactions.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

