---
title: Power BI:n Q&A-visualisoinnin käyttäminen
description: Power BI:n Q&A-visualisoinnin määrittäminen
author: mihart
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/19/2019
ms.author: mohaali
ms.openlocfilehash: 9805b98df7f606e61412ca9dee7dc0467a1649a3
ms.sourcegitcommit: 90bd747b7c460d17b74cd386d3f5714234b1f6c9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/03/2019
ms.locfileid: "74791794"
---
# <a name="introduction-to-power-bi-qa-visual"></a>Johdatus Power BI:n Q&A-visualisointiin

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

## <a name="what-is-the-qa-visual"></a>Mikä Q&A-visualisointi on

Q&A-visualisoinnin avulla käyttäjät voivat esittää kysymyksiä käyttämällä luonnollista kieltä ja saada vastauksia visualisoinnin muodossa. 

![Q&A-visualisoinnin esittely](../natural-language/media/qna-visual-walkthrough.gif)

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Q&A-visualisointia voidaan käyttää välineenä, jonka avulla *käyttäjät* saavat nopeasti vastauksia tietoihinsa ja jonka avulla *suunnittelijat* voivat luoda visualisointeja raporttiin vain kaksoisnapsauttamalla mitä tahansa kohtaa raportissa ja käyttämällä luonnollista kieltä. Koska Q&A-visualisointi käyttäytyy kuin mikä tahansa muu visualisointi, se voidaan ristiinsuodatettaa/ristiinkorostaa ja se tukee myös kirjanmerkkejä. Q&A-visualisointi tukee myös teemoja ja muita oletusmuotoiluasetuksia, jotka ovat käytettävissä Power BI:ssä.

Q&A-visualisointi koostuu neljästä ydinosasta:

- Kysymysruutu. Tähän käyttäjät voivat kirjoittaa kysymykseensä, ja heille näytetään ehdotuksia, joiden avulla he voivat viimeistellä kysymyksensä.
- Valmiiksi täytetty ehdotettujen kysymysten luettelo.
- Kuvake, joka muuntaa Q&A-visualisoinnin vakiovisualisoinniksi. 
- Kuvake, joka avaa Q&A-työkalut, joiden avulla suunnittelijat voivat määrittää pohjana olevan luonnollisen kielen moduulin.

## <a name="prerequisites"></a>Edellytykset

1. Tässä opetusohjelmassa käytetään [myynti- ja markkinointimallin](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix) PBIX-tiedostoa. 

1. Valitse Power BI Desktopin valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. Etsi oma **myynti- ja markkinointimallin** PBIX-tiedostosi

1. Avaa tiedosto raporttinäkymään ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.


Jos näyttöön tulee virhe Q&A-visualisointia luotaessa, tarkista [rajoitukset](../natural-language/q-and-a-limitations.md)-osiosta, tuetaanko tietolähdemääritystä.

## <a name="create-a-qa-visual-using-a-suggested-question"></a>Luo Q&A-visualisointi käyttämällä ehdotettua kysymystä
Tässä harjoituksessa valitaan yksi ehdotetuista kysymyksistä Q&A-visualisoinnin luomiseksi. 

1. Aloita tyhjältä raporttisivulta ja valitse Q&A-visualisointikuvake Visualisoinnit-ruudusta.

    ![Visualisointi-ruutu, jossa Q&A-visualisointikuvake on korostettuna](media/power-bi-visualization-q-and-a/power-bi-icon.png)

2. Muuta visualisoinnin kokoa vetämällä reunaa.

    ![Q&A-visualisointi raporttipohjalla](media/power-bi-visualization-q-and-a/power-bi-qna.png)

3. Jos haluat luoda visualisoinnin, valitse jokin ehdotetuista kysymyksistä tai ala kirjoittaa kysymysruutuun. Tässä esimerkissä olemme valinneet **parhaat maantieteelliset osavaltiot tuoton summan mukaan**. Power BI tekee parhaansa valitakseen käytettävän visualisointityypin. Tässä tapauksessa kyseessä on kartta.

    ![Q&A-visualisoinnin kartta](media/power-bi-visualization-q-and-a/power-bi-map.png)

    Voit kuitenkin määrittää Power BI:n käyttämään tiettyä visualisointityyppiä lisäämällä sen luonnollisen kielen kyselyyn. Muista, että kaikki visualisointityypit eivät toimi tai ole järkeviä tietojesi kanssa. Nämä tiedot eivät esimerkiksi tuota mielekästä pistekaaviota. Ne toimivat kuitenkin täytettynä karttana.

    ![Q&A-visualisointi täytettynä karttana](media/power-bi-visualization-q-and-a/power-bi-specify-map.png)

## <a name="create-a-qa-visual-using-a-natural-language-query"></a>Q&A-visualisoinnin luominen luonnollisen kielen kyselyn avulla
Edellisessä esimerkissä valittiin yksi ehdotetuista kysymyksistä Q&A-visualisoinnin luomiseksi.  Tässä harjoituksessa kirjoitat oman kysymyksesi. Power BI:n automaattinen täydennys, ehdotukset ja palaute auttavat kysymyksen kirjoittamisessa.

Jos et ole varma, minkä tyyppisiä kysymyksiä haluat esittää tai mitä termejä haluat käyttää, laajenna **Näytä kaikki ehdotukset** tai selaa Kentät-ruutua, joka löytyy pohjan oikeasta reunasta. Näin voit tutustua Myynti ja markkinointi -tietojoukon ehtoihin ja sisältöön.

![pohja, jossa Näytä kaikki ehdotukset ja Kentät-ruutu ovat korostettuina](media/power-bi-visualization-q-and-a/power-bi-terminology.png)


1. Kirjoita kysymys Q&A-kenttään. Power BI alleviivaa sanat, joita se ei tunnista, punaisella. Aina kun se on mahdollista, Power BI auttaa määrittämään tunnistamattomia sanoja.  Alla olevassa ensimmäisessä esimerkissä jompikumpi ehdotuksista sopii meille.  

    ![Kysymyksen kirjoittaminen Q&A-ruutuun](media/power-bi-visualization-q-and-a/power-bi-red-suggest.png)

2. Kun kirjoitamme kysymystä lisää, Power BI ilmoittaa, ettei se ymmärrä kysymystä, ja yrittää auttaa. Alla olevassa esimerkissä Power BI kysyy "Tarkoititko..." ja ehdottaa eri tapaa esittää kysymys käyttämällä tietojoukkomme terminologiaa. 

    ![Ehdotuksia näyttävä Q&A-visualisointi](media/power-bi-visualization-q-and-a/power-bi-define.png)

5. Power BI:n avulla pystyimme esittämään kysymyksen tunnistettavia termejä käyttämällä. Power BI näyttää tulokset linjakaaviona. 

    ![Q&A-visualisoinnin tulokset](media/power-bi-visualization-q-and-a/power-bi-type.png)


6. Muutetaan visualisointi pylväskaavioksi. 

    ![Q&A-visualisointi, jossa kysymykseen on lisätty "pylväskaaviona"](media/power-bi-visualization-q-and-a/power-bi-specify-visual.png)

7.  Lisää visualisointeja raporttisivulle ja tarkastele, miten Q&A-visualisointi on vuorovaikutuksessa muiden sivulla olevien visualisointien kanssa. Tässä esimerkissä Q&A-visualisointi on suodattanut viivakaavion ja kartan ristiin sekä korostanut palkkikaaviot ristiin.

    ![Q&A-visualisointi, jossa yksi palkki on valittuna, ja vaikutus muihin kolmeen visualisointiin raporttisivulla](media/power-bi-visualization-q-and-a/power-bi-filters.png)

## <a name="format-and-customize-the-qa-visual"></a>Q&A-visualisoinnin ulkoasun muotoileminen ja mukauttaminen
Q&A-visualisointia voidaan mukauttaa käyttämällä muotoiluruutua ja ottamalla käyttöön teema. 

### <a name="apply-a-theme"></a>Ota teema käyttöön
Kun valitset teeman, kyseinen teema otetaan käyttöön koko raporttisivulla. Valittavana on monia teemoja, joten kokeile niitä, kunnes löydät haluamasi ulkoasun. 

1. Valitse valikkoriviltä **Aloitus**-välilehti ja valitse **Vaihda teemaa**. 

    ![Työpöytä, jossa Vaihda teemaa on valittuna](media/power-bi-visualization-q-and-a/power-bi-themes.png)

    
    
2. Tässä esimerkissä olemme valinneet **Lisää teemoja** > **Turvallinen värisokeille**.

    ![Q&A-visualisointi, jossa on käytössä värisokea-teema](media/power-bi-visualization-q-and-a/power-bi-color-blind.png)

### <a name="format-the-qa-visual"></a>Muotoile Q&A-visualisointia
Muotoile Q&A visualisointia, kysymyskenttää ja tapaa, jolla ehdotukset näytetään. Voit muuttaa kaikkea otsikon taustasta väriin, joka näkyy, kun hiiren osoitin on tunnistamattomien sanojen päällä. Olemme lisänneet kysymysruutuun harmaan taustan ja muuttaneet alleviivaukset keltaisiksi ja vihreiksi. Otsikko on keskitetty, ja sillä on keltainen tausta. 

![Q&A-visualisointi, joka näyttää tehdyt muotoilut](media/power-bi-visualization-q-and-a/power-bi-q-and-a-format.png)

## <a name="convert-your-qa-visual-into-a-standard-visual"></a>Muunna Q&A-visualisointi vakiovisualisoinniksi
Olemme muotoilleet värisokeille turvallista pylväskaaviovisualisointia hieman lisäämällä siihen otsikon ja reunan. Nyt olemme valmiit muuntamaan sen raportin vakiovisualisoinniksi ja kiinnittämään sen koontinäyttöön.

Valitse ![hammasrataskuvake](media/power-bi-visualization-q-and-a/power-bi-convert-icon.png)-kuvake, jos haluat **muuttaa tämän Q&A-tuloksen vakiovisualisoinniksi**.

![Q&A-visualisointi, jossa nuoli osoittaa vakiovisualisointikuvakkeeseen](media/power-bi-visualization-q-and-a/power-bi-visual-convert.png)

Tämä visualisointi ei ole enää Q&A-visualisointi vaan vakiosarakekaavio. Se voidaan kiinnittää koontinäyttöön. Raportissa tämä visualisointi käyttäytyy samalla tavalla kuin muut vakiovisualisoinnit. Huomaa, että Visualisoinnit-ruudussa näkyy valittuna pylväskaaviokuvake Q&A-visualisointikuvakkeen sijaan.

Jos käytät ***Power BI -palvelua***, voit nyt kiinnittää visualisoinnin koontinäyttöön valitsemalla Kiinnitä-kuvakkeen. 


![Power BI-palvelu, jonka Kiinnitä-kuvake on korostettuna](media/power-bi-visualization-q-and-a/power-bi-pin.png)


## <a name="advanced-features-of-the-qa-visual"></a>Q&A-visualisoinnin kehittyneet ominaisuudet
Hammasrataskuvakkeen valitseminen avaa Q&A-visualisoinnin Työkalut-ruudun. 

![Q&A-visualisointi, jossa Työkalut-kuvake on valittuna](media/power-bi-visualization-q-and-a/power-bi-q-and-a-tooling.png)

Työkalut-ruudun avulla voit opettaa Q&A:lle termejä, joita se ei tunnista, hallita näitä termejä ja hallita tämän tietojoukon ja raportin ehdotettuja kysymyksiä. Työkalut-ruudussa voit myös tarkastella kysymyksiä, joita on esitetty tätä Q&A-visualisointia käyttämällä, ja nähdä kysymykset, jotka käyttäjät ovat merkinneet. Jos haluat lisätietoja, lue [Tietoja Q&A-työkaluista](../natural-language/q-and-a-tooling-intro.md).

![Q&A:n Työkalut-ruutu](media/power-bi-visualization-q-and-a/power-bi-q-and-a-tooling-pane.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Q&A-visualisointi integroituu Officen ja Bingin kanssa, ja ne yrittävät sovittaa yleiset tunnistamattomat sanat tietojoukkosi kenttiin.  

## <a name="next-steps"></a>Seuraavat vaiheet

Luonnollisen kielen voi integroida useilla eri tavoilla. Katso lisätietoja seuraavista artikkeleista:

* [Q&A-työkalut](../natural-language/q-and-a-tooling-intro.md)
* [Q&A:n parhaat käytännöt](../natural-language/q-and-a-best-practices.md)
