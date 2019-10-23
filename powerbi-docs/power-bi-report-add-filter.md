---
title: Suodattimen lisääminen Power BI - raporttiin
description: Sivu-, visualisointi- tai raporttisuodattimen lisääminen raporttiin Power BI:ssä
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/02/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: be2304e655adadf20f5d33f46840c5a0cb82aa9f
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/17/2019
ms.locfileid: "72544946"
---
# <a name="add-a-filter-to-a-report-in-power-bi"></a>Suodattimen lisääminen Power BI - raporttiin

[!INCLUDE [power-bi-service-new-look-include](includes/power-bi-service-new-look-include.md)]

Tässä artikkelissa kerrotaan, miten voit lisätä sivu-, visualisointi-, raportti- tai porautumissuodattimen Power BI -raporttiin. Artikkelin esimerkit koskevat Power BI -palvelua. Vaiheet ovat lähes samanlaiset Power BI Desktopissa.

**Tiesitkö?** Power BI:ssä on uusi suodatuskokemus. Lue lisää [uudesta suodatuskokemuksesta Power BI -raporteissa](power-bi-report-filter.md).

![Uusi suodatuskokemus](media/power-bi-report-add-filter/power-bi-filter-reading.png)

Power BI tarjoaa useita erilaisia suodattimia manuaalisista ja automaattisista suodattimista porautumisen suodattimiin ja läpivientikyselyjen suodattimiin. Lue lisää [erilaisista suodattimista](power-bi-report-filter-types.md).

## <a name="filters-in-editing-view-or-reading-view"></a>Lukunäkymän tai muokkausnäkymän suodattimet
Voit käsitellä raportteja kahdessa eri näkymässä: lukunäkymässä ja muokkausnäkymässä. Käytettävissä olevat suodatusominaisuudet vaihtelevat näkymän mukaan. [Lue lisää Power BI -raporttien suodattimista ja korostamisesta](power-bi-reports-filters-and-highlighting.md).

Tässä artikkelissa kerrotaan, miten voit luoda suodattimia raporttiin **muokkausnäkymässä**.  Lisätietoja lukunäkymän suodattimista on artikkelissa [Suodattimien käsitteleminen raportissa lukunäkymässä](consumer/end-user-report-filter.md).

Koska suodattimet *pysyvät*, kun siirryt pois raportista, Power BI säilyttää suodattimet, osittajan ja muut tietojen näkymän muutokset, jotka olet tehnyt. Näin voit jatkaa siitä, mihin jäit, kun palaat raporttiin. Jos et halua suodattimen muutosten säilyvän, valitse **Palauta oletukset** ylävalikosta.

![Pysyvät suodattimet -painike](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="levels-of-filters-in-the-filters-pane"></a>Suodattimien tasot Suodattimet-ruudussa
Suodattimet-ruutu näkyy raportin piirtoalustan oikeassa reunassa sen mukaan, onko käytössä Desktop vai Power BI. Jos et näe Suodattimet-ruutua, laajenna ruutu valitsemalla oikeasta yläkulmasta >-kuvake.

Voit määrittää suodattimia raportin kolmelle eri tasolle: visualisointitason, sivutason ja raporttitason suodattimet. Voit myös määrittää porautumisen suodattimia. Tässä artikkelissa selvitetään eri tasoja.

![Suodattimet-ruutu Lukunäkymässä](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

## <a name="add-a-filter-to-a-visual"></a>Suodattimen lisääminen visualisointiin
Voit lisätä visualisointitason suodattimen tiettyyn visualisointiin kahdella eri tavalla. 

* Voit suodattaa kentän, joka on jo käytössä visualisoinnissa.
* Vaihtoehtoisesti voit määrittää kentän, joka ei ole käytössä visualisoinnissa, ja lisätä kyseisen kentän suoraan **Visuaalisen tason suodattimet** -säilöön.


Tässä menettelyssä käytetään jälleenmyyntianalyysimallia. Voi halutessasi ladata sen ja käyttää sitä apuna. Lataa [jälleenmyyntianalyysimallin](sample-retail-analysis.md#get-the-content-pack-for-this-sample) sisältöpaketti.

### <a name="filter-the-fields-in-the-visual"></a>Visualisoinnin kenttien suodattaminen

1. Avaa raporttisi Muokkausnäkymässä valitsemalla **Lisää asetuksia (...)**  > **Muokkaa raporttia**.
   
   ![Muokkaa raporttia -painike](media/power-bi-report-add-filter/power-bi-edit-view.png)

2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu (jos ne eivät ole jo avoinna).
   
   ![Visualisoinnit, suodattimet ja Kentät-ruudut](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Valitse visualisointi, jotta siitä tulee aktiivinen. Kaikki visualisoinnissa käytettävät kentät näkyvät **Kentät**-ruudussa ja luetellaan lisäksi **Visuaalisen tason suodattimet** -otsikon alla olevassa **Suodattimet**-ruudussa.
   
   ![Valitse visualisointitason suodattimet](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. Tässä vaiheessa lisäämme suodattimen kenttään, joka on jo käytössä visualisoinnissa. 
   
    Vieritä alaspäin **Visuaalisen tason suodattimet** -alueelle ja laajenna suodatettava kenttä valitsemalla nuolipainike. Tässä esimerkissä suodatamme kentän **StoreNumberName** perusteella.
     
    ![Nuoli laajentaa suodatinta](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
    
    Määritä suodatusasetukseksi **Perussuodatus**, **Lisäsuodatus** tai **Ylimmät N**. Tässä esimerkissä teemme perussuodatuksen avulla haun **cha** ja valitsemme löytyvät viisi myymälää.
     
    ![Haku perussuodatuksessa](media/power-bi-report-add-filter/power-bi-search-filter.png) 
   
    Visualisointi muuttuu vastaamaan uutta suodatinta. Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät ensinnäkin näkevät visuaalisen suodattimen ja voivat lisäksi käsitellä suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.
     
    ![Suodatettu visualisointi](media/power-bi-report-add-filter/power-bi-search-visual-filter-results.png)
    
    Kun käytät suodatinta visualisoinnissa käytetyssä kentässä, ja kenttä koostetaan (esimerkiksi summa, keskiarvo tai määrä), suodatat *koostetussa* arvossa jokaisessa arvopisteessä. Jos siis haluat suodattaa yllä olevan visualisoinnin, jossa **Tämän vuoden myynti > 500000**, tarkoittaa, että tuloksessa näkyy vain **13 - Charleston Fashion Direct** -arvopiste. [Mallimittareiden](desktop-measures.md) suodattimet koskevat aina arvopisteen koostearvoa.

### <a name="filter-with-a-field-thats-not-in-the-visual"></a>Suodattaminen kentällä, joka ei ole visualisoinnissa

Nyt lisäämme visualisointiin uuden kentän visuaalisen tason suodattimena.
   
1. Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena visuaalisen tason suodattimena, ja vedä se **Visuaalisen tason suodattimet** -alueelle.  Tässä esimerkissä vedämme **Aluejohtaja**-kentän **Visuaalisen tason suodattimet** -säilöön, teemme haun **an** ja valitsemme löytyvät kolme johtajaa.
     
    ![Lisää kenttä Suodattimet-ruutuun](media/power-bi-report-add-filter/power-bi-search-add-visual-filter.png)

    Huomaa, että **Aluejohtaja**-kenttää *ei* lisätä itse visualisointiin. Visualisointi muodostuu Akseli-kohdan arvosta **StoreNumberName** ja Arvo-kohdan arvosta **This Year Sales**.  
     
    ![Kenttä ei ole visualisoinnissa](media/power-bi-report-add-filter/power-bi-visualization.png)

    Visualisointi suodatetaan nyt niin, että siinä näkyy vain kolmen johtajan tiettyjen myymälöiden tämän vuoden myynti.
     
    ![Suodatettu visualisointi](media/power-bi-report-add-filter/power-bi-search-visual-filter-results-2.png)

    Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät voivat käsitellä **Aluejohtaja**-suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.
    
    Jos vedät *numeerisen sarakkeen* suodatinruutuun visuaalisen tason suodattimen luomiseksi, suodatinta käytetään *pohjana olevissa tietoriveissä*. Esimerkiksi suodattimen lisääminen **Yksikkökustannus**-kenttään ja määrittämällä sen arvoksi **Yksikkökustannus** > 20 näyttää vain niiden tuoterivien tiedot, joissa yksikkökustannus oli suurempi kuin 20, visualisoinnissa näytettävien arvopisteiden kokonaisyksikkökustannuksesta riippumatta.

## <a name="add-a-filter-to-an-entire-page"></a>Suodattimen lisääminen koko sivulle

Voit myös lisätä sivutason suodattimen koko sivun suodattamiseksi.

1. Avaa jälleenmyyjäanalyysimalli Power BI -palvelussa ja siirry sitten **Alueen kuukausimyynti** -sivulle. 

2. Avaa raportti Muokkausnäkymässä valitsemalla **...**  > **Muokkaa raporttia**.
   
   ![Muokkaa raporttia -painike](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu (jos ne eivät ole jo avoinna).
3. Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena sivutason suodattimena, ja vedä se **Sivutason suodattimet** -alueelle.  
4. Valitse suodatettavat arvot ja määritä suodatusasetukseksi **Perussuodatus** tai **Lisäsuodatus**.
   
   Kaikki sivulla olevat visualisoinnit piirretään uudelleen vastaamaan muutosta.
   
   ![Lisää suodatin ja valitse arvot](media/power-bi-report-add-filter/filterpage.gif)

    Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät voivat käsitellä suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.

## <a name="add-a-drillthrough-filter"></a>Porautumissuodattimen lisääminen
Power BI -palvelun ja Power BI Desktopin porautumisen avulla voit luoda *kohderaporttisivun*, jolla keskitytään tiettyyn entiteettiin, kuten toimittajaan, asiakkaaseen tai valmistajaan. Nyt käyttäjät voivat muilla raporttisivuilla napsauttaa hiiren kakkospainikkeella kyseisen entiteetin arvopistettä ja porautua tiettyyn entiteettiin keskittyvälle sivulle.

### <a name="create-a-drillthrough-filter"></a>Porautumissuodattimen luominen
Seuraa mukana lataamalla [Asiakkaan tuottavuuden malli](sample-customer-profitability.md#get-the-content-pack-for-this-sample). Oletetaan, että haluat luoda sivun, jolla keskitytään Johtaja-liiketoiminta-alueisiin.

1. Avaa jälleenmyyjäanalyysimalli Power BI -palvelussa ja siirry sitten **Alueen kuukausimyynti** -sivulle.

2. Avaa raporttisi Muokkausnäkymässä valitsemalla **Lisää asetuksia (...)**  > **Muokkaa raporttia**.
   
   ![Muokkaa raporttia -painike](media/power-bi-report-add-filter/power-bi-edit-view.png)

1. Lisää raporttiin uusi sivu ja anna sen nimeksi **Tiimijohtaja**. Tämä sivu on porautumisen *kohde*.
2. Lisää visualisointeja, jotka seuraavat tiimijohtajien liiketoiminta-alueiden avaintietoja.    
3. Vedä **Johto**-taulukosta **Johto** porautumissuodattimien ruutuun.    
   
    ![Lisää arvo porautumisen suodattimiin](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    Huomaa, että Power BI lisää taaksepäin osoittavan nuolen raporttisivulle.  Valitsemalla taaksepäin osoittavan nuolen käyttäjät voivat palata *alkuperäiselle* raporttisivulle eli sivulle, jolla he valitsivat porautumisen. Valitse taaksepäin osoittava nuoli painamalla muokkausnäkymässä Ctrl-näppäintä pitkään
   
     ![Taaksepäin osoittava nuoli](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>Porautumissuodattimen käyttäminen
Katsotaan, miten porautumissuodatin toimii.

1. Aloita **Tiimin tuloskortti** -raporttisivulta.    
2. Oletetaan, että olet Antero Mäntylä ja haluat nähdä Tiimijohtaja-raporttisivun, joka on suodatettu näyttämään vain sinun tietosi.  Avaa Porautuminen-valikkovaihtoehto napsauttamalla hiiren kakkospainikkeella vasemman yläreunan alueen kaaviosta mitä tahansa vihreää arvopistettä.
   
    ![Aloita porautumistoiminto](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. Poraudu **Tiimijohtaja**-raporttisivulle valitsemalla **Porautuminen > Tiimijohtaja**. Sivu suodatetaan näyttämään tietoja hiiren kakkospainikkeella napsauttamastasi arvopisteestä – tässä tapauksessa Antti Mäntylästä. Kaikki alkuperäisen sivun suodattimia käytetään porautumisraporttisivulla.  
   
    ![Valitse porautumistoiminto](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-report-level-filter-to-filter-an-entire-report"></a>Lisää raporttitason suodatin koko raportin suodattamiseksi

1. Avaa raportti Muokkausnäkymässä valitsemalla **Muokkaa raporttia**.
   
   ![Muokkaa raporttia -painike](media/power-bi-report-add-filter/power-bi-edit-view.png)

2. Avaa Visualisoinnit- ja Suodattimet-ruutu sekä Kentät-ruutu, jos ne eivät ole jo avoinna.
3. Valitse Kentät-ruudusta kenttä, jonka haluat lisätä uutena raporttitason suodattimena, ja vedä se **Raporttitason suodattimet** -alueelle.  
4. Valitse arvot, joiden perusteella haluat suodattaa.

    Aktiivisella sivulla ja kaikilla raportin sivuilla olevat visualisoinnit muuttuvat uuden suodattimen mukaisiksi. Jos tallennat suodattimen sisältävän raportin, raporttia lukevat käyttäjät voivat käsitellä suodatinta lukunäkymässä valitsemalla tai tyhjentämällä arvoja.

1. Palaa edelliselle raporttisivulle valitsemalla taaksepäin osoittava nuoli.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

- Jos Kentät-ruutu ei ole näkyvissä, varmista, että valittuna on raportin [muokkausnäkymä](service-interact-with-a-report-in-editing-view.md).    
- Jos olet tehnyt paljon muutoksia suodattimiin ja haluat palata raportin tekijän oletusasetuksiin, valitse **Palauta oletukset** ylävalikosta.

## <a name="next-steps"></a>Seuraavat vaiheet
[Aloita raportin Suodattimet-ruudun esittely](consumer/end-user-report-filter.md)

[Suodattimet ja korostaminen raporteissa](power-bi-reports-filters-and-highlighting.md)

[Erilaiset Power BI -suodattimet](power-bi-report-filter-types.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

