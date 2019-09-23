---
title: Suuret tietojoukot, arvopisterajat ja tietostrategiat
description: Visualisointien tietorajat ja tietojen vähentämisen strategiat
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 6b5f2fa44a45cca06f90474d8c76fd6f06cae3ce
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61276402"
---
# <a name="data-point-limits-and-strategies-by-visual-type"></a>Arvopisterajat ja strategiat visualisointityypin mukaan

Kun visualisointia hahmonnetaan Power BI:ssä, visualisoinnin on oltava nopea ja tarkka. Se edellyttää tausta-algoritmien määrittämistä jokaiselle visualisointityypille. Power BI:n visualisointien on oltava riittävän joustavia, jotta ne pystyvät käsittelemään erikokoisia tietojoukkoja. Joissakin tietojoukoissa voi olla vain muutamia arvopisteitä, kun taas toisissa arvopisteitä voi olla useita petatavuja. Tässä artikkelissa käsitellään strategioita, joiden avulla Power BI hahmontaa visualisoinnit.

## <a name="data-reduction-strategies"></a>Tietojen vähentämisen strategiat
Jokaisessa visualisoinnissa käytetään vähintään yhtä *tietojen vähentämisen strategiaa*, jotta analysoinnissa mahdollisesti tarvittavia valtavia tietomääriä voidaan käsitellä. Yksinkertaisessakin taulukossa käytetään strategiaa, jolla vältetään koko tietojoukon lataaminen asiakkaaseen.  Käytettävä vähentämisstrategia vaihtelee visualisointityypin mukaan. Jokainen visualisointi valitsee tuettuja *tietojen vähentämisen strategioita* osaksi palvelimelle lähetettävää tietopyyntöä. 

Jokainen visualisointi määrittää näiden strategioiden parametrit, jotta tietojen kokonaismäärään voidaan vaikuttaa.   

## <a name="strategies"></a>Strategiat
Kullekin strategialle on oletusarvoja visualisoitavan tiedon muodon ja tyypin mukaan. Oletusarvot voidaan kuitenkin ohittaa Power BI:n Muotoilu-ruudussa, jotta tuloksena saadaan oikea käyttökokemus. 

* **Tietojen ikkunointi** (segmentointi): Käyttäjät voivat selata visualisoinnin tietoja lataamalla asteittain osia koko tietojoukosta.
* **TopN**: Näyttää vain ensimmäiset N kohdetta
* **Yksinkertainen malli**: Näytä ensimmäinen, viimeinen ja tasaisesti jakautuneet N kohdetta niiden välillä.
* **BottomN**: Näyttää vain viimeiset N kohdetta.  Tämä sopii usein päivitettyjen tietojen seurantaan.
* **Suuren tiheyden näytteenotto** – parannettu näytteenottoalgoritmi, jossa noudatetaan entistä paremmin poikkeavia arvoja ja/tai käyrän muotoa.
    * **Lokeroitu viivaotanta** – arvopisteiden otanta akselilla olevien lokeroiden poikkeavien arvojen perusteella
    * **Päällekkäisten pisteiden näytteenotto** – arvopisteiden otanta päällekkäisten arvojen perusteella poikkeavien arvojen säilyttämiseksi

## <a name="statistics"></a>Tilastotiedot
Tietyt mallit voivat tarjota tilastotietoja tiettyjen sarakkeiden arvojen määrästä. Kun tällaisia tietoja on käytettävissä, tietoja hyödynnetään paremman tasapainon tarjoamiseen useissa hierarkioissa, jos visualisointi ei nimenomaisesti ohita arvojen määrää strategiassa.

Katso lisätietoja artikkelista [Analysis Servicesin uudet ominaisuudet](https://docs.microsoft.com/sql/analysis-services/what-s-new-in-analysis-services?view=sql-server-2017).

## <a name="dynamic-limits"></a>Dynaamiset rajoitukset
Yllä mainittujen strategioiden lisäksi visualisoinneissa, joissa on kaksi ryhmittelysarakkeiden hierarkiaa (akseli ja selite tai luokka ja sarja), käytetään yhtä lisästrategiaa nimeltään *dynaamiset rajoitukset*.  Dynaamiset rajoitukset on suunniteltu tarjoamaan entistä tasapainoisemmat arvopisteet. 

Dynaamiset rajoitukset tarjoaa paremman pisteiden valinnan harvoista tiedoista tilastollisiin rajoituksiin verrattuna. Visualisointi voidaan esimerkiksi määrittää valitsemaan 100 luokkaa ja 10 sarjaa, joissa on yhteensä 1 000 pistettä. Todellisissa tiedoissa on kuitenkin 50 luokkaa ja 20 sarjaa.  Kyselyn suorituksessa dynaamiset rajoitukset valitsevat kaikki 20 sarja, jotta pyydetty 1 000 pisteen raja täyttyy.

Dynaamiset rajoitukset otetaan käyttöön automaattisesti, kun palvelin täyttää alla esitetyt vaatimukset:

* Power BI Desktopissa, jossa on paikallinen SSAS-versio 2016 tai uudempi, [hyödynnetään palvelimen SuperDax-ominaisuuksia](https://blogs.msdn.microsoft.com/analysisservices/2015/09/02/whats-new-in-microsoft-sql-server-analysis-services-tabular-models-in-sql-server-2016-ctp-2-3/)

* Desktopissa ja Power BI -palvelussa, kun käytetään tuotua mallia, suoraa kyselyä, suoraa yhteyttä palveluun tai suoraa yhteyttä AS PaaS -palveluun. 

* Dynaamisia rajoituksia ei voida käyttää Power BI -palvelussa, kun yhteys muodostetaan paikallisen yhdyskäytävän kautta paikalliseen SSAS-palveluun. Paikallinen yhdyskäytävä ei tue täysin dynaamisten rajoitusten strategiaa, joka palauttaa paikallisesta SASS-palvelusta poikkeavan tulosjoukkorakenteen.  

## <a name="strategies-and-data-point-limits-by-visual-type"></a>Strategiat ja arvopisterajat visualisointityypin mukaan

### <a name="area-chart"></a>Aluekaavio
Katso [viivaotannan toimintaperiaate](../desktop-high-density-sampling.md#how-the-new-line-sampling-algorithm-works)

### <a name="barcolumn-chart"></a>Palkki-/pylväskaavio
- Luokittaisessa tilassa
    - Luokat: Virtualisointi käyttämällä 500 rivin ikkunaa yhdellä kertaa
    - Sarja: Ylimmät 60
    - Skalaaritilassa (tässä voidaan käyttää dynaamisia rajoituksia)
        - Maksimipisteet: 10 000
        - Luokat: 500 arvon malli
        - Sarja: Ylimmät 20 arvoa

### <a name="card-multirow"></a>Kortti (monirivinen) 
- Arvot: Virtualisointi käyttämällä 200 rivin ikkunaa yhdellä kertaa

### <a name="combo-chart"></a>Yhdistelmäkaavio
 Käyttää samaa strategiaa kuin pylväskaavio. Huomaa, että **yhdistelmäkaavion** rivillä ei käytetä suuren tiheyden algoritmia, jota käytetään **viivakaaviossa**.

### <a name="custom-visuals"></a>Mukautetut visualisoinnit
Jopa 30 000, mutta visualisoinnin tekijät määrittävät käytettävät strategiat

### <a name="doughnut"></a>Rengaskaavio
- Maksimipisteet: 3 500
- Ryhmä: Ylimmät 500
- Tiedot: Ylimmät 20

### <a name="filled-map-choropleth"></a>Täytetty koropleettikartta 
Täytetyssä kartassa voidaan käyttää tilastotiedot tai dynaamisia rajoja. Power BI yrittää käyttää vähentämistä seuraavassa järjestyksessä: dynaamiset rajat, tilastotiedot ja lopuksi määritys. 
- Maksimipisteet: 10 000
- Luokat: Ylimmät 500
- Sarja (kun sekä X että Y ovat käytettävissä): Ylimmät 20

### <a name="funnel"></a>Suppilo
- Maksimipisteet: 3 500
- Luokat: Ylimmät 3 500

### <a name="kpi"></a>Suorituskykyilmaisin
- Trendiakseli
- Alimmat 3 500

### <a name="line-chart"></a>Viivakaavio
Katso [viivaotannan toimintaperiaate](../desktop-high-density-sampling.md#how-the-new-line-sampling-algorithm-works)

### <a name="line-chart-high-density"></a>Viivakaavio, suuri tiheys
Katso [Suuren tiheyden otanta](../desktop-high-density-sampling.md)

### <a name="map"></a>Kartta 
- Maksimipisteet: 3 500

Kartassa voi olla määritysten mukaan:
- Sijainti: Ylimmät 3 500
- Sijainti, koko: Ylimmät 3 500
- Sijainti, leveys- ja pituusastekoosteet (+/-koko): Ylimmät 3 500
- Leveysaste, pituusaste: katso [Suuren tiheyden pistekaaviot](desktop-high-density-scatter-charts.md)
- Leveysaste, pituusaste, koko: Ylimmät 3 500
- Selite, leveysaste, pituusaste: katso [Suuren tiheyden pistekaaviot](desktop-high-density-scatter-charts.md)
- Selite, leveysaste, pituusaste, koko: Ylimmät 233 selitettä, ylimmät 15 leveys- ja pituusastetta (tässä voidaan käyttää tilastotietoja tai dynaamisia rajoituksia)
- Sijainti, selite, pituusaste ja leveysaste koosteina (+/-koko): Ylimmät 233 sijaintia, ylimmät 15 selitettä (tässä voidaan käyttää tilastotietoja tai dynaamisia rajoituksia)

### <a name="matrix"></a>Matriisi
- Rivit: Virtualisointi käyttämällä 500 rivin ikkunaa yhdellä kertaa
- Sarakkeet: Ylimmät 100 ryhmittelysaraketta 
- Arvot: useita arvoja ei oteta huomioon tietojen vähentämisessä

### <a name="radial-gauge"></a>Viisarimittari
Ei vähentämisstrategiaa

### <a name="slicer"></a>Osittaja
- Arvot: Virtualisointi käyttämällä 200 rivin ikkunaa yhdellä kertaa

### <a name="scatter-chart-high-density"></a>Pistekaavio (suuri tiheys)
Katso [Suuren tiheyden pistekaaviot](https://docs.microsoft.com/power-bi/visuals/desktop-high-density-scatter-charts)

### <a name="pie"></a>Ympyrä
- Maksimipisteet: 3 500
- Ryhmä: Ylimmät 500
- Tiedot: Ylimmät 20

### <a name="r--python-visuals"></a>R- ja Python-visualisoinnit
Rajoitettu 150 000 riviin. Jos valittuna on yli 150 000 riviä, vain ensimmäiset 150 000 riviä ovat käytössä

### <a name="ribbon-chart"></a>Nauhakaavio
- Luokittaisessa tilassa
    - Luokat: Virtualisointi (tietojen ikkunointi) käyttämällä 500 rivin ikkunaa yhdellä kertaa
    - Sarja: Ylimmät 60
    - Skalaaritilassa (tässä voidaan käyttää dynaamisia rajoituksia)
        - Maksimipisteet: 10 000
        - Luokat: 500 arvon malli
        - Sarja: Ylimmät 20 arvoa

### <a name="shape-map"></a>Muotokartta
Täytetyssä kartassa voidaan käyttää tilastotiedot tai dynaamisia rajoja. 
- Maksimipisteet: 10 000
- Luokat: Ylimmät 500
- Sarja (kun sekä X että Y ovat käytettävissä): Ylimmät 20

### <a name="table"></a>Taulukko
- Arvot: Virtualisointi (tietojen ikkunointi) käyttämällä 500 rivin ikkunaa yhdellä kertaa

### <a name="tree-map-this-could-use-statistics-or-dynamic-limits"></a>Puukartta (tässä voidaan käyttää tilastotietoja tai dynaamisia rajoituksia)
- Maksimipisteet: 3 500
- Ryhmä: Ylimmät 500
- Tiedot: Ylimmät 20

### <a name="waterfall-chart"></a>Vesiputouskaavio
- Kun käytössä on vain luokkasäilö
    - Maksimipisteet: 3 500
    - Vain luokka - ylimmät 3 500
- Kun käytettävissä ovat sekä luokka että erittely
    - Luokka: Virtualisointi (tietojen ikkunointi) käyttämällä 30 rivin ikkunaa yhdellä kertaa
    - Erittely – ylimmät 200 arvoa


## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisointityypit](power-bi-report-visualizations.md)
