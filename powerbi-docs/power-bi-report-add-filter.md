---
title: Visualisointi-, sivu-, porautumis- tai raporttisuodattimen lisääminen Power BI -raporttiin
description: Sivu-, visualisointi-, raportti- tai porautumissuodattimen lisääminen Power BI -raporttiin
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/28/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: c70e29bf7dcd5a307cbcb4762595716595dfa523
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973277"
---
# <a name="add-a-filter-to-a-power-bi-service-report-in-editing-view"></a>Suodattimen lisääminen Power BI -palvelun raporttiin (muokkausnäkymässä)

Tässä artikkelissa kerrotaan, miten voit lisätä sivu-, visualisointi-, raportti- tai porautumissuodattimen Power BI -raporttiin. Artikkelin esimerkit koskevat Power BI -palvelua. Vaiheet ovat lähes samanlaiset Power BI Desktopissa.

## <a name="filters-in-editing-view-or-reading-view"></a>Lukunäkymän tai muokkausnäkymän suodattimet
Voit käsitellä raportteja kahdessa eri näkymässä: lukunäkymässä ja muokkausnäkymässä. Käytettävissä olevat suodatusominaisuudet vaihtelevat näkymän mukaan. [Lue lisää Power BI -raporttien suodattimista ja korostamisesta](power-bi-reports-filters-and-highlighting.md).

Tässä artikkelissa kerrotaan, miten voit luoda suodattimia raporttiin **muokkausnäkymässä**.  Lisätietoja lukunäkymän suodattimista on artikkelissa [Suodattimien käsitteleminen raportissa lukunäkymässä](consumer/end-user-reading-view.md).

## <a name="filter-types-in-the-filters-pane"></a>Suodatintyypit Suodattimet-ruudussa
Suodattimet-ruutu näkyy raportin piirtoalustan oikeassa reunassa sen mukaan, onko käytössä Desktop vai Power BI. Jos et näe Suodattimet-ruutua, laajenna ruutu valitsemalla oikeasta yläkulmasta >-kuvake.

Suodattimia on neljää tyyppiä: **sivusuodattimet**, **visuaaliset suodattimet**, **porautumissuodattimet** ja **raporttisuodattimet**.

![Suodattimet-ruutu Lukunäkymässä](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

Koska suodattimet *pysyvät*, kun siirryt pois raportista, Power BI säilyttää suodattimet, osittajan ja muut tietojen näkymän muutokset, jotka olet tehnyt. Näin voit jatkaa siitä, mihin jäit, kun palaat raporttiin. Jos et halua suodattimen muutosten säilyvän, valitse **Palauta oletukset** ylävalikosta.

![Pysyvät suodattimet -painike](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="add-a-filter-to-a-visual"></a>Suodattimen lisääminen visualisointiin
Voit lisätä suodattimen tiettyyn visualisointiin (eli visuaalisen suodattimen) kahdella eri tavalla. 

* Voit suodattaa kentän, joka on jo käytössä visualisoinnissa.
* Vaihtoehtoisesti voit määrittää kentän, joka ei ole käytössä visualisoinnissa, ja lisätä kyseisen kentän suoraan **Visuaalisen tason suodattimet** -säilöön.

Tässä menettelyssä käytetään jälleenmyyntianalyysimallia. Voi halutessasi ladata sen ja käyttää sitä apuna. Lataa [Jälleenmyyntianalyysimalli](sample-retail-analysis.md).

### <a name="filter-the-fields-in-the-visual"></a>Visualisoinnin kenttien suodattaminen


1. Avaa [raportti muokkausnäkymässä](service-the-report-editor-take-a-tour.md).
   
   ![](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu (jos ne eivät ole jo avoinna).
   
   ![](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Valitse visualisointi, jotta siitä tulee aktiivinen. Kaikki visualisoinnissa käytettävät kentät näkyvät **Kentät**-ruudussa ja luetellaan lisäksi **Visuaalisen tason suodattimet** -otsikon alla olevassa **Suodattimet**-ruudussa.
   
   ![](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. Tässä vaiheessa lisäämme suodattimen kenttään, joka on jo käytössä visualisoinnissa. 
   
    Vieritä alaspäin **Visuaalisen tason suodattimet** -alueelle ja laajenna suodatettava kenttä valitsemalla nuolipainike. Tässä esimerkissä suodatamme kentän **StoreNumberName** perusteella.
     
    ![](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
    
    Määritä suodatusasetukseksi **Perussuodatus**, **Lisäsuodatus** tai **Ylimmät N**. Tässä esimerkissä teemme perussuodatuksen avulla haun **cha** ja valitsemme löytyvät viisi myymälää.
     
    ![](media/power-bi-report-add-filter/power-bi-search-filter.png) 
   
    Visualisointi muuttuu vastaamaan uutta suodatinta. Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät ensinnäkin näkevät visuaalisen suodattimen ja voivat lisäksi käsitellä suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.
     
    ![](media/power-bi-report-add-filter/power-bi-search-visual-filter-results.png)

### <a name="filter-with-a-field-thats-not-in-the-visual"></a>Suodattaminen kentällä, joka ei ole visualisoinnissa

Nyt lisäämme visualisointiin uuden kentän visuaalisen tason suodattimena.
   
1. Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena visuaalisen tason suodattimena, ja vedä se **Visuaalisen tason suodattimet** -alueelle.  Tässä esimerkissä vedämme **Aluejohtaja**-kentän **Visuaalisen tason suodattimet** -säilöön, teemme haun **an** ja valitsemme löytyvät kolme johtajaa. 
     
    ![](media/power-bi-report-add-filter/power-bi-search-add-visual-filter.png)

    Huomaa, että **Aluejohtaja**-kenttää *ei* lisätä itse visualisointiin. Visualisointi muodostuu Akseli-kohdan arvosta **StoreNumberName** ja Arvo-kohdan arvosta **This Year Sales**.  
     
    ![](media/power-bi-report-add-filter/power-bi-visualization.png)

    Visualisointi suodatetaan nyt niin, että siinä näkyy vain kolmen johtajan tiettyjen myymälöiden tämän vuoden myynti.
     
    ![](media/power-bi-report-add-filter/power-bi-search-visual-filter-results-2.png)

    Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät voivat käsitellä **Aluejohtaja**-suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.

## <a name="add-a-filter-to-an-entire-page"></a>Suodattimen lisääminen koko sivulle

Voit myös lisätä suodattimen koko sivulle (sivunäkymän suodatin).
1. Avaa [raportti muokkausnäkymässä](service-the-report-editor-take-a-tour.md).
2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu (jos ne eivät ole jo avoinna).
3. Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena sivutason suodattimena, ja vedä se **Sivutason suodattimet** -alueelle.  
4. Valitse suodatettavat arvot ja määritä suodatusasetukseksi **Perussuodatus** tai **Lisäsuodatus**.
   
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
1. Avaa [raportti muokkausnäkymässä](service-the-report-editor-take-a-tour.md).
2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu (jos ne eivät ole jo avoinna).
3. Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena raporttitason suodattimena, ja vedä se **Raporttitason suodattimet** -alueelle.  
4. Valitse arvot, joiden perusteella haluat suodattaa.

    Aktiivisella sivulla ja kaikilla raportin sivuilla olevat visualisoinnit muuttuvat uuden suodattimen mukaisiksi. Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät voivat käsitellä suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.

1. Palaa edelliselle raporttisivulle valitsemalla taaksepäin osoittava nuoli.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

- Joissakin tilanteissa visuaalisen tason suodatin ja sivutason suodatin voivat palauttaa eri tuloksia.  Esimerkiksi, kun lisäät visuaalisen tason suodattimen, Power BI suodattaa kootut tulokset.  Oletuskooste on Summa, mutta voit [muuttaa koostetyyppiä](service-aggregates.md).  

    Kun lisäät sivutason suodattimen, Power BI suodattaa ilman koostamista.  Tämä johtuu siitä, että sivulla voi olla useita visualisointeja, joista jokainen voi hyödyntää eri koostetyyppiä.  Suodatinta käytetään siis jokaisella tietorivillä.

- Jos Kentät-ruutu ei ole näkyvissä, varmista, että valittuna on raportin [muokkausnäkymä](service-interact-with-a-report-in-editing-view.md).    
- Jos olet tehnyt paljon muutoksia suodattimiin ja haluat palata raportin tekijän oletusasetuksiin, valitse **Palauta oletukset** ylävalikosta.

## <a name="next-steps"></a>Seuraavat vaiheet
[Aloita raportin Suodattimet-ruudun esittely](consumer/end-user-report-filter.md)

[Suodattimet ja korostaminen raporteissa](power-bi-reports-filters-and-highlighting.md)

[Suodattimien ja korostamisen käsitteleminen raportin lukunäkymässä](consumer/end-user-reading-view.md)

[Raportin visualisointien ristiinsuodatuksen ja ristiinkorostuksen muuttaminen suhteessa toisiinsa](consumer/end-user-interactions.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

