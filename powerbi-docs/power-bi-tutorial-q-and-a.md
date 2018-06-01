---
title: Opetusohjelma – Q&A-toiminnon käyttö koontinäytössä tai raportissa
description: Opetusohjelma uusien visualisointien luontiin koontinäytöissä ja raporteissa Power BI:n Q&A-toiminnon avulla.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
editor: ''
tags: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/17/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 44501e5447248164f6f04d4463213939975e18ae
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815869"
---
# <a name="tutorial-how-to-use-qa-to-create-visualizations-and-build-reports"></a>Opetusohjelma: Visualisointien ja raporttien luominen Q&A-toiminnon avulla
[Q&A-yleiskatsauksessa](power-bi-q-and-a.md) opit Power BI:n Q&A-toiminnon perusteet sekä *kuluttajien* (joille jaetaan koontinäyttöjä ja raportteja) ja *luojien* (pohjana olevien raporttien ja tietojoukkojen omistajat) erot. Tässä opetusohjelmassa ensimmäinen osa on tarkoitettu ensisijaisesti kuluttajille, jotka käyttävät Power BI -palvelua. Toinen osa on tarkoitettu henkilöille, jotka luovat raportteja joko Power BI -palvelussa tai Power BI Desktopissa. Muita tähän liittyviä artikkeleita ovat [Q&A ja Power BI:n mobiilisovellus](mobile-apps-ios-qna.md) sekä [Q&A ja Power BI Embedded](developer/qanda.md).

Q&A on vuorovaikutteinen ja jopa hauska käyttää. Lisäksi yhden kysymyksen esittäminen johtaa usein moniin muihin sitä mukaa, kun visualisoinnit paljastavat uusia mielenkiintoisia polkuja. Katso videoesittely visualisointien luonnista Q&A:n avulla, tutustu kyseisiin visualisointeihin ja kiinnittää niitä koontinäyttöihin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-use-qa-on-a-dashboard-in-power-bi-service-apppowerbicom"></a>Osa 1: Q&A-toiminnon käyttäminen koontinäytössä Power BI -palvelussa (app.powerbi.com)
Koontinäyttö sisältää ruutuja, jotka on kiinnitetty yhdestä tai useammasta tietojoukosta. Voit kysyä kysymyksiä kaikista kyseisten tietojoukkojen sisältämistä tiedoista. Voit näyttää koontinäytön luomiseen käytetyt raportit ja tietojoukot valitsemalla **Näytä aiheeseen liittyvät** valikkorivistä.

![](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Q&A-kysymysruutu sijaitsee koontinäytön vasemmassa yläkulmassa. Tähän kirjoitat kysymyksesi luonnollisella kielellä. Q&A tunnistaa kirjoittamasi sanat ja etsii niiden avulla vastauksen (oikeasta tietojoukosta). Q&A auttaa myös kysymyksen muotoilemisessa automaattisella täydentämisellä, oikaisuilla sekä muilla tekstimuotoisilla ja visuaalisilla apuvälineillä.

![](media/power-bi-tutorial-q-and-a/powerbi-qna.png)

Vastaus kysymykseen näkyy vuorovaikutteisena visualisoinnilla, joka päivittyy sitä mukaa, kun muokkaat kysymystä.

1. Avaa koontinäyttö ja aseta kohdistin kysymysruutuun. Jo ennen kuin alat kirjoittaa, Q&A näyttää uuden näytön ehdotuksilla, jotka voivat olla avuksi kysymyksen muodostamisessa. Näet [pohjana olevan tietojoukon](service-get-data.md) taulukoiden nimet, ja toiminto voi myös ehdottaa valmiita kysymyksiä, jos tietojoukon omistaja on luonut [suositeltuja kysymyksiä](service-q-and-a-create-featured-questions.md).

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-cursor.png)

   Voit aina valita jonkin näistä kysymyksistä lähtökohdaksi ja tarkentaa sitä tarpeen mukaan, jotta löydät etsimäsi vastauksen. Vaihtoehtoisesti voit aloittaa uuden kysymyksen taulukon nimen perusteella.

2. Valitse tietojoukon vaihtoehdoista tai ala kirjoittaa oman kysymyksesi ja valitse avattavan luettelon ehdotuksista.

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-list.png)

3. Kun kirjoitat kysymystä, Q&A hakee parhaan [visualisoinnin](power-bi-visualization-types-for-reports-and-q-and-a.md) ja näyttää sen perusteella vastauksen; visualisointi muuttuu dynaamisesti kysymystä muokatessa.

   ![](media/power-bi-tutorial-q-and-a/powerbi-qna-viz.png)

4. Kun kirjoitat kysymystä, Power BI etsii parhaan vastauksen kaikkien niiden tietojoukkojen perusteella, jolla on ruutu koontinäytössä.  Jos kaikki ruudut ovat peräisin tietojoukosta *datasetA*, vastauksesi muodostetaan tietojoukon *datasetA* tiedoista.  Jos ruutuja on tietojoukoista *datasetA* ja *datasetB*, Q&A etsii parhaan vastauksen molemmista näistä tietojoukoista.

   > [!TIP]
   > Noudata varovaisuutta: jos sinulla on vain yksi ruutu tietojoukosta *datasetA* ja poistat sen koontinäytöstä, Q&A ei voi enää käyttää tietojoukkoa *datasetA*.
   >
   >
5. Kun olet tyytyväinen tulokseen, [kiinnittää visualisointi koontinäyttöön](service-dashboard-pin-tile-from-q-and-a.md) valitsemalla nastakuvakkeen oikeassa yläkulmassa. Jos koontinäyttö on jaettu kanssasi, tai se kuuluu johonkin sovellukseen, sitä ei voi kiinnittää.

   ![](media/power-bi-tutorial-q-and-a/pbi_qna_finish-typing-question.jpg)

##    <a name="part-2-use-qa-in-a-report-in-power-bi-service-or-power-bi-desktop"></a>Osa 2: Q&A-toiminnon käyttäminen raportissa Power BI -palvelussa tai Power BI Desktopissa

Q&A-toiminnon avulla voit tutkia tietojoukkoa ja lisätä visualisointeja raporttiin ja koontinäyttöihin. Raportti perustuu yhteen tietojoukkoon, ja se voi olla tyhjä tai sisältää sivukaupalla visualisointeja. Tyhjä raportti ei kuitenkaan tarkoita, ettei tietoja olisi tutkittavana – tietojoukko on linkitetty raporttiin ja vain odottaa tutkimista ja visualisointien luontia.  Jos haluat nähdä, minkä tietojoukon perusteella raportti on luotu, avaa raportti Power BI -palvelun lukunäkymässä ja valitse **Näytä aiheeseen liittyvät** valikkoriviltä.

![](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Q&A:n käyttö raporteissa edellyttää raportin ja pohjana olevan tietojoukon muokkausoikeuksia. [Q&A:n yleiskatsausaiheessa](power-bi-q-and-a.md) tätä kutsutaan *luoja*-skenaarioksi. Jos olet raportin *kuluttaja*, eli raportti on jaettu kanssasi, Q&A ei ole käytettävissä.

1. Avaa raportti muokkausnäkymässä (Power BI -palvelussa) tai raporttinäkymässä (Power BI Desktopissa) ja valitse **Esitä kysymys** valikkoriviltä.

    **Desktop**    
    ![](media/power-bi-tutorial-q-and-a/power-bi-desktop-question.png)

    **Palvelu**    
    ![](media/power-bi-tutorial-q-and-a/power-bi-service.png)

2. Q&A-kysymysruutu tulee näkyviin raporttipohjalla. Alla olevassa esimerkissä kysymysruutu näkyy toisen visualisoinnin päällä. Tämä ei haittaa käyttöä, mutta voit haluta [lisätä tyhjän sivun raporttiin](power-bi-report-add-page.md) ennen kysymyksen esittämistä.

    ![](media/power-bi-tutorial-q-and-a/power-bi-ask-question.png)

3. Aseta kohdistin kysymysruutuun. Kirjoittaessasi kysymystä Q&A näyttää ehdotuksia, joiden avulla voit muotoilla oikean kysymyksen.

   ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-suggestions.png)

4. Kun kirjoitat kysymystä, Q&A hakee parhaan [visualisoinnin](power-bi-visualization-types-for-reports-and-q-and-a.md) ja näyttää sen perusteella vastauksen; visualisointi muuttuu dynaamisesti kysymystä muokatessa.

   ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-visual.png)

5. Kun olet saanut haluamasi visualisoinnin, paina ENTER-näppäintä. Jos haluat tallentaa visualisoinnin ja raportin, valitse **Tiedosto > Tallenna**.

6. Tee haluamasi toimet uudessa visualisoinnissa. Visualisoinnin luontimenetelmällä ei ole merkitystä – sama vuorovaikutteisuus sekä kaikki muotoilut ja ominaisuudet ovat käytettävissä.

  ![](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-ellipses.png)

  Jos olet luonut visualisoinnin Power BI -palvelussa, voit myös [kiinnittää sen koontinäyttöön](service-dashboard-pin-tile-from-q-and-a.md).

## <a name="tell-qa-which-visualization-to-use"></a>Kerro Q&A:lle minkä visualisoinnin haluat.
Q&A:n avulla voit saada tietosi puhumaan puolestaan, mutta myös Power BI:n näyttämään vastauksen haluamassasi muodossa. Lisää vain ”nimellä <visualization type>” kysymyksesi loppuun.  Esimerkiksi ”näytä varastotilanne tuotantolaitoksen mukaan karttana” tai ”näytä varasto yhteensä korttina”.  Kokeile itse.

##  <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- Jos olet yhdistänyt tietojoukkoon käyttäen reaaliaikaista yhteyttä tai yhdyskäytävää, Q&A on oltava [käytössä tietojoukossa](service-q-and-a-direct-query.md).

- Olet avannut raportin, mutta Q&A-vaihtoehtoa ei näy. Jos käytät Power BI -palvelua, varmista, että avaat raportin muokkausnäkymässä. Jos et voi avata muokkausnäkymässä, sinulla ei ole raportin muokkausoikeuksia etkä pysty käyttämään Q&A-toimintoa kyseisessä raportissa.

## <a name="next-steps"></a>Seuraavat vaiheet
Takaisin artikkeliin [Q&A Power BI:ssä](power-bi-q-and-a.md)   
[Opetusohjelma: Q&A jälleenmyyntimallin kanssa](power-bi-visualization-introduction-to-q-and-a.md)   
[Vihjeitä Q&A-kysymysten esittämiseen](service-q-and-a-tips.md)   
[Työkirjan valmisteleminen Q&A-toimintoa varten](service-prepare-data-for-q-and-a.md)  
[Paikallisen tietojoukon valmisteleminen Q&A-toimintoa varten](service-q-and-a-direct-query.md)
[Kiinnitä ruutu koontinäyttöön Q&A:sta](service-dashboard-pin-tile-from-q-and-a.md)
