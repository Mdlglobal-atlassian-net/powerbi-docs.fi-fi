---
title: 'Tarkastella ja visualisointien luominen Power BI Q & A: n avulla'
description: 'Miten uusien visualisointien luontiin koontinäytöissä ja raporteissa Power BI Q & A: n avulla.'
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: c6fd8967a49515af4d0614653b3d7550c335052f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65625387"
---
# <a name="use-power-bi-qa-to-explore-your-data-and-create-visuals"></a>Tarkastele tietoja ja luoda visualisointeja Power BI Q & A: n avulla

Joskus nopein tapa saada vastauksia tiedoista on esittää kysymyksiä luonnollisella kielellä. Power BI-Q & A-toiminnon avulla voit tarkastella tietojasi omin sanoin.  Ensimmäinen osa tässä artikkelissa kerrotaan, miten käytetään Q & A Power BI-palvelussa koontinäyttöjä. Toinen osa näyttää, mitä voit tehdä Q & A Power BI-palvelussa tai Power BI Desktop-raporttien luomiseen. Katso lisätietoja tausta [Q & A kuluttajien](consumer/end-user-q-and-a.md) artikkelissa. 

[Q & A Power BI-mobiilisovelluksissa](consumer/mobile/mobile-apps-ios-qna.md) ja [Q & A ja Power BI Embedded](developer/qanda.md) on kuvattu artikkeleita. 

Q & A on vuorovaikutteinen, jopa hauska. Usein yksi kysymys liidit muille, kun visualisoinnit paljastavat uusia mielenkiintoisia polkuja käyttää. Katso videoesittely visualisointien luonnista Q&A:n avulla, tutustu kyseisiin visualisointeihin ja kiinnittää niitä koontinäyttöihin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-use-qa-on-a-dashboard-in-the-power-bi-service"></a>Osa 1: Q & A: n käyttäminen koontinäytössä Power BI-palvelussa

Power BI-palvelussa (app.powerbi.com) koontinäyttö sisältää ruutuja, jotka on kiinnitetty vähintään yksi, joten voit kysyä kysymyksiä kaikista kyseisten tietojoukkojen sisältämistä tiedoista. Jos haluat nähdä koontinäytön luomiseen käytetyt raportit ja tietojoukot, valitse **Näytä Aiheeseen liittyvät** valikkoriviltä.

![Näytä Aiheeseen liittyvät raportit ja tietojoukot](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Q & A-kysymysruutu sijaitsee koontinäytön, jossa kirjoitat kysymyksesi luonnollisella kielellä vasemmassa yläkulmassa. Etkö näe Q & A-ruudussa? Katso [seikat ja vianmääritys](consumer/end-user-q-and-a.md#considerations-and-troubleshooting) - **Q & A kuluttajien** artikkelissa.  Q & A tunnistaa kirjoittamasi sanat ja etsii niiden avulla (mikä tietojoukossa) vastauksen. Q&A auttaa myös kysymyksen muotoilemisessa automaattisella täydentämisellä, oikaisuilla sekä muilla tekstimuotoisilla ja visuaalisilla apuvälineillä.

![Q & A-kysymysruutu](media/power-bi-tutorial-q-and-a/powerbi-qna.png)

Vastaus kysymykseen näkyy vuorovaikutteisena visualisoinnilla, joka päivittyy sitä mukaa, kun muokkaat kysymystä.

1. Avaa koontinäyttö ja aseta kohdistin kysymysruutuun. Valitse oikeassa yläkulmassa **uusi Q & A-käyttökokemus**.

    ![Power BI uusi Q & A-käyttökokemus](media/power-bi-tutorial-q-and-a/power-bi-qna-new-experience.png)

1. Jo ennen kuin alat kirjoittaa, Q&A näyttää uuden näytön ehdotuksilla, jotka voivat olla avuksi kysymyksen muodostamisessa. Näet lauseet ja sen pohjana olevista tietojoukoista taulukoiden nimet sisältävä kysymyksiä ja saada jopa kysymyksiä, jos tietojoukon omistaja on luonut [suositeltuja kysymyksiä](service-q-and-a-create-featured-questions.md),

   ![Q & A-ehdotetut kysymykset](media/power-bi-tutorial-q-and-a/power-bi-qna-suggested-questions.png)

   Voit valita jonkin näistä kysymyksistä lähtökohdaksi ja tarkentaa löytää tietyn vastauksen kysymykseen. Tai voit aloittaa uuden kysymyksen taulukon nimen avulla.

2. Sinulla on kysyttävää, luettelosta tai ala kirjoittaa oman kysymyksesi ja valitse avattavan luettelon ehdotuksista.

   ![Valitse kysymys luettelosta](media/power-bi-tutorial-q-and-a/power-bi-qna-select-a-question-how-many-stores.png)

3. Kun kirjoitat kysymystä, Q & A valitsee parhaan visualisoinnin ja näyttää vastauksen.

   ![Q & A: kuinka monta tallentaa osavaltion mukaan](media/power-bi-tutorial-q-and-a/power-bi-qna-how-many-stores-by-state.png)

4. Visualisointi muuttuu dynaamisesti sinuna muokatessa.

   ![Q & A: kuinka monta tallentaa palkkikaaviona osavaltion mukaan](media/power-bi-tutorial-q-and-a/power-bi-qna-stores-by-state-bar-chart.png)

1. Kun kirjoitat kysymystä, Power BI etsii parhaan vastauksen kaikkien niiden tietojoukkojen perusteella, jolla on ruutu koontinäytössä.  Jos kaikki ruudut ovat peräisin tietojoukosta *datasetA*, vastauksesi muodostetaan tietojoukon *datasetA* tiedoista.  Jos ruutuja on tietojoukoista *datasetA* ja *datasetB*, sitten Q & A etsii parhaan vastauksen 2 tietojoukoista.

   > [!TIP]
   > Noudata varovaisuutta: jos sinulla on vain yksi ruutu tietojoukosta *datasetA* ja poistat sen koontinäytöstä, Q&A ei voi enää käyttää tietojoukkoa *datasetA*.
   >

5. Kun olet tyytyväinen tulokseen, kiinnitä visualisointi koontinäyttöön valitsemalla Kiinnitä-kuvake oikeassa yläkulmassa. Jos koontinäyttö on jaettu kanssasi, tai se kuuluu johonkin sovellukseen, sitä ei voi kiinnittää.

   ![Q & A: n kiinnittää visualisoinnin](media/power-bi-tutorial-q-and-a/power-bi-qna-pin-visual.png)

## <a name="part-2-use-qa-in-a-report-in-power-bi-service-or-power-bi-desktop"></a>Osa 2: Q&A-toiminnon käyttäminen raportissa Power BI -palvelussa tai Power BI Desktopissa

Q&A-toiminnon avulla voit tutkia tietojoukkoa ja lisätä visualisointeja raporttiin ja koontinäyttöihin. Raportti perustuu yhteen tietojoukkoon, ja se voi olla tyhjä tai sisältää sivukaupalla visualisointeja. Tyhjä raportti ei kuitenkaan tarkoita, ettei tietoja olisi tutkittavana – tietojoukko on linkitetty raporttiin ja vain odottaa tutkimista ja visualisointien luontia.  Jos haluat nähdä, minkä tietojoukon perusteella raportti on luotu, avaa raportti Power BI -palvelun lukunäkymässä ja valitse **Näytä aiheeseen liittyvät** valikkoriviltä.

![Näytä liittyvät tietojoukot](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Q & A: n käyttö raporteissa edellyttää raportin ja pohjana olevan tietojoukon muokkausoikeuksia. - [Q & A kuluttajien](consumer/end-user-q-and-a.md) artikkelissa viittaamme tämän *tekijä* skenaario. Jos olet sen sijaan *kuluttaja* raportti, joka on jaettu kanssasi, Q & A ei ole käytettävissä.

1. Avaa raportti muokkausnäkymässä (Power BI-palvelussa) tai raporttinäkymässä (Power BI Desktop) ja valitse **esitä kysymys** valikkoriviltä.

    **Power BI Desktop**    
    ![Valitse esitä kysymys Power BI Desktop](media/power-bi-tutorial-q-and-a/power-bi-desktop-question.png)

    **Palvelu**    
    ![Kirjoita kysymys Valitse Power BI-palvelussa](media/power-bi-tutorial-q-and-a/power-bi-service.png)

2. Q&A-kysymysruutu tulee näkyviin raporttipohjalla. Alla olevassa esimerkissä kysymysruutu näkyy toisen visualisoinnin päällä. Tämä ei haittaa käyttöä, mutta voit haluta lisätä tyhjän sivun raporttiin ennen kysymyksen esittämistä.

    ![Q & A-kysymysruutu](media/power-bi-tutorial-q-and-a/power-bi-ask-question.png)

3. Aseta kohdistin kysymysruutuun. Kirjoittaessasi kysymystä Q&A näyttää ehdotuksia, joiden avulla voit muotoilla oikean kysymyksen.

   ![Kirjoita Q & A-kysymysruudun](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-suggestions.png)

4. Kun kirjoitat kysymystä, Q&A hakee parhaan [visualisoinnin](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md) ja näyttää sen perusteella vastauksen; visualisointi muuttuu dynaamisesti kysymystä muokatessa.

   ![Q & A: Luo visualisoinnin](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-visual.png)

5. Kun olet saanut haluamasi visualisoinnin, paina ENTER-näppäintä. Jos haluat tallentaa visualisoinnin ja raportin, valitse **Tiedosto > Tallenna**.

6. Tee haluamasi toimet uudessa visualisoinnissa. Visualisoinnin luontimenetelmällä ei ole merkitystä – sama vuorovaikutteisuus sekä kaikki muotoilut ja ominaisuudet ovat käytettävissä.

   ![Visualisoinnin käsitellä](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-ellipses.png)

   Jos olet luonut visualisoinnin Power BI -palvelussa, voit myös [kiinnittää sen koontinäyttöön](service-dashboard-pin-tile-from-q-and-a.md).

## <a name="tell-qa-which-visualization-to-use"></a>Kerro Q&A:llen minkä visualisoinnin haluat
Q&A:n avulla voit saada tietosi puhumaan puolestaan, mutta myös Power BI:n näyttämään vastauksen haluamassasi muodossa. Lisää vain ”nimellä <visualization type>” kysymyksesi loppuun.  Esimerkiksi ”näytä varastotilanne tuotantolaitoksen mukaan karttana” tai ”näytä varasto yhteensä korttina”.  Kokeile itse.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
- Jos olet yhdistänyt tietojoukkoon käyttäen reaaliaikaista yhteyttä tai yhdyskäytävää, Q&A on oltava [käytössä tietojoukossa](service-q-and-a-direct-query.md).

- Olet avannut raportin, mutta Q&A-vaihtoehtoa ei näy. Jos käytät Power BI -palvelua, varmista, että avaat raportin muokkausnäkymässä. Jos et voi avata muokkausnäkymässä, se tarkoittaa, että sinulla ei ole raportin muokkausoikeuksia ja voit käyttää Q & A: n kyseisessä raportissa.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Q & A kuluttajat](consumer/end-user-q-and-a.md)   
- [Vihjeitä Q & A-kysymysten esittämiseen](consumer/end-user-q-and-a-tips.md)   
- [Työkirjan valmisteleminen Q&A-toimintoa varten](service-prepare-data-for-q-and-a.md)  
- [Paikallisen tietojoukon valmisteleminen Q & A](service-q-and-a-direct-query.md)   
- [Ruudun kiinnittäminen koontinäyttöön Q & A](service-dashboard-pin-tile-from-q-and-a.md)
