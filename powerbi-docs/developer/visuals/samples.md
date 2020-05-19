---
title: Power BI -visualisointiesimerkkejä
description: Tässä artikkelissa esitellään Power BI:n mallivisualisoinnit, kuten osittajat, yli 20 eri kaaviotyyppiä, WebGL- ja R-visualisoinnit sekä komentosarjat.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/17/2019
ms.openlocfilehash: 5e2ad0fa43a186be76a58f1ab3bb4bf054a677a5
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83132111"
---
# <a name="samples-of-power-bi-visuals"></a>Power BI -visualisointien mallit

Voit ladata nämä Power BI -visualisoinnit, käyttää niitä ja muokata niitä GitHubista. Nämä esimerkit kuvaavat sitä, miten voit käsitellä yleisiä tilanteita, kun kehität sovellusta Power BI:ssä.

## <a name="slicers"></a>Osittajat

Osittajan avulla voit tarkentaa raportin muissa visualisoinneissa näkyvän tietojoukon osaa. Osittajat ovat yksi monesta tavasta suodattaa tietoja Power BI:ssä.

| <img src="media/samples/chiclet-slicer.png" width="200">  | <img src="media/samples/timeline-slicer.png" width="200"> | <img src="media/samples/sample-slicer.png" width="200">|
| ------------- | ------------- | -------------|
| [Chiclet-osittaja](https://github.com/Microsoft/powerbi-visuals-chicletslicer/)  </br>Näytä kuvan tai tekstin painikkeet, jotka toimivat suodattimena muille visualisoinneille | [Aikajanan osittaja](https://github.com/Microsoft/powerbi-visuals-timeline/) </br>Graafinen päivämääräalueen valitsin, joka suodattaa päivämäärän mukaan | [Osittajaesimerkki](https://github.com/Microsoft/powerbi-visuals-sampleslicer/) </br>Esittelee kehittyneen suodatuksen ohjelmointirajapinnan käyttöä

## <a name="charts"></a>Kaaviot

Voit hyödyntää valikoimaamme, kuten palkkikaavioita, ympyräkaavioita ja sanapilveä.

| <img src="media/samples/aster-plot.png" width="200">  | <img src="media/samples/bullet-chart.png" width="200"> | <img src="media/samples/Chord.png" width="200">|
| ------------- | ------------- | -------------|
| [Asterikaavio](https://github.com/Microsoft/powerbi-visuals-asterplot/)  </br>Tavallisen rengaskaavion kierre, joka käyttää toista arvoa taivutuskulman tekemiseen | [Nuolikaavio ](https://github.com/Microsoft/powerbi-visuals-bulletchart/) </br>Palkkikaavio, joka sisältää visuaalisia lisäelementtejä kontekstin tarjoamista varten. Tästä on hyötyä tavoitteiden seurannassa | [Jänne](https://github.com/Microsoft/powerbi-visuals-chord/) </br>Graafinen menetelmä tietojen välisten suhteiden näyttämiseen
| <img src="media/samples/dot-plot.png" width="200"> | <img src="media/samples/dual-kpi.png" width="200">| <img src="media/samples/enhanced-scatter.png" width="200"> 
| [Pistekaavio](https://github.com/Microsoft/powerbi-visuals-dotplot/) </br>Näyttää taajuuksien jakauman hienolla tavalla | [Dual KPI ‑kaavio](https://github.com/Microsoft/powerbi-visuals-dualkpi/) </br>Visualisoi tehokkaasti kaksi mittaria ajan kuluessa ja näytä niiden trendi yhteisellä aikajanalla | [Parannettu pistekaavio](https://github.com/Microsoft/powerbi-visuals-enhancedscatter/) </br>Parannus olemassa olevaan pistekaavioon
| <img src="media/samples/forcegraph.png" width="200">| <img src="media/samples/gantt.png" width="200">| <img src="media/samples/table-heatmap.png" width="200">
| [Force Graph](https://github.com/Microsoft/powerbi-visuals-forcegraph/) </br>Pakota asettelukaavio käyrän polun mukaiseksi. Tästä on hyötyä entiteettien välisten yhteyksien näyttämiseen | [Gantt-kaavio](https://github.com/Microsoft/powerbi-visuals-gantt/) </br>Palkkikaavio, joka esittää projektin aikajanan tai aikataulun resurssien kanssa | [Lämpökarttataulukko](https://github.com/Microsoft/powerbi-visuals-heatmap/) </br>Vertaa tietoja helposti ja intuitiivisesti käyttämällä värejä taulukossa
| <img src="media/samples/histogram-chart.png" width="200"> | <img src="media/samples/linedot-chart.png" width="200"> | <img src="media/samples/mekko-chart.png" width="200"> 
| [Histogrammikaavio](https://github.com/Microsoft/powerbi-visuals-histogram/) </br>Visualisoi tietojen jakautumisen jatkuvalla aikavälillä tai tietyllä ajanjaksolla | [Viiva-pallokaavio](https://github.com/Microsoft/powerbi-visuals-linedotchart/) </br>Animoitu viivakaavio, jossa on hauskoja animoituja pisteitä ja joka herättää hyötyä yleisön mielenkiinnon tietojen avulla | [Mekko-kaavio](https://github.com/Microsoft/powerbi-visuals-mekkochart/) </br>Sekoitus 100 %:n pinotusta pylväskaaviosta ja 100 %:n pinotusta palkkikaaviosta yhdistettynä yhdeksi näkymäksi
| <img src="media/samples/multikpi.png" width="200"> | <img src="media/samples/powerkpi.png" width="200"> | <img src="media/samples/powerkpi-matrix.png" width="200"> 
| [Multi KPI](https://github.com/microsoft/PowerBI-visuals-MultiKPI/) </br> Tehokas monen suorituskykyilmaisimen visualisointi, jossa on avainsuorituskykyilmaisin sekä useita tukitietojen sparkline-kaavioita | [Power KPI](https://github.com/microsoft/PowerBI-visuals-PowerKPI/) </br>Tehokas suorituskykyilmaisin sekä monirivinen kaavio ja selitteet nykyistä päivämäärää, arvoa ja variansseja varten | [Power KPI ‑taulukko](https://github.com/microsoft/PowerBI-visuals-PowerKPIMatrix/) </br>Valvo tasapainotettuja tuloskortteja ja rajoittamatonta määrää mittareita ja suorituskykyilmaisimia kompaktissa ja helppolukuisessa luettelossa
| <img src="media/samples/pulse-chart.png" width="200">| <img src="media/samples/radar-chart.png" width="200"> | <img src="media/samples/sankey-chart.png" width="200"> 
| [Jaksoittainen kaavio](https://github.com/Microsoft/powerbi-visuals-pulsechart/) </br>Tämä viivakaavio, johon on merkitty tärkeät tapahtumat, sopii täydellisesti tarinan kertomiseen tietojen avulla| [Säteittäinen kaavio](https://github.com/Microsoft/powerbi-visuals-radarchart/) </br>Esittää useita mittareita tulostettuna luokka-akselille, mistä on hyötyä määritteiden vertailemisessa | [Sankey-kaavio](https://github.com/Microsoft/powerbi-visuals-sankey/) </br>Vuokaavio, jossa sarjan leveys on suhteessa vuon laatuun
| <img src="media/samples/stream-graph.png" width="200"> | <img src="media/samples/sunburst.png" width="200">| <img src="media/samples/tornado.png" width="200">
| [Virtakaavio](https://github.com/Microsoft/powerbi-visuals-streamgraph/) </br>Pinottu aluekaavio, jossa on tasainen interpolointi ja jota käytetään usein ajan kuluessa muuttuvien arvojen näyttämiseen | [Auringonsädekaavio](https://github.com/Microsoft/powerbi-visuals-sunburst/) </br>Monitasoinen rengaskaavio hierarkkisten tietojen visualisoimista varten| [Tornadokuvaaja](https://github.com/Microsoft/powerbi-visuals-tornado/) </br>Vertaa muuttujien suhteellista tärkeyttä kahden ryhmän välillä
 | <img src="media/samples/word-cloud.png" width="200">
 | [Sanapilvi](https://github.com/Microsoft/powerbi-visuals-wordcloud/) </br>Luo hauska visualisointi tiedoissasi usein esiintyvästä tekstistä

## <a name="webgl"></a>WebGL

WebGL sallii verkkosisällön käyttää OpenGL ES 2.0:aan perustuvaa ohjelmointirajapintaa 2D-ja 3D-hahmonnukseen HTML-pohjalla.

| <img src="media/samples/globe-map.png" width="250">|
| ------------- |
| [Karttapallo](https://github.com/Microsoft/powerbi-visuals-globemap/) </br>Tulosta sijainnit vuorovaikutteiselle kolmiulotteiselle kartalle

## <a name="r-visuals"></a>R-visualisoinnit

Nämä esimerkit esittelevät, miten voit hyödyntää R-visualisointien ja R-komentosarjojen analyyttista ja visuaalista tehokkuutta.

| <img src="media/samples/association-rules.png" width="200">| <img src="media/samples/clustering.png" width="200">| <img src="media/samples/clustering-with-outliers.png" width="200">|
|------------- |------------- |------------- |------------- |
| [Liittämissäännöt](https://github.com/Microsoft/powerbi-visuals-assorules/) </br>Paljasta näennäisesti toisiinsa liittymättömien tietojen väliset yhteydet jos-niin-lausekkeiden avulla | [Klusterointi](https://github.com/Microsoft/powerbi-visuals-clustering-kmeans/) </br>Etsi samankaltaisuusryhmät tiedoistasi k-means-algoritmin avulla | [Klusterointi ja poikkeamat](https://github.com/microsoft/PowerBI-visuals-dbscan/) </br>Löydä samankaltaisuusryhmät ja poikkeamat tiedoistasi
| <img src="media/samples/correlation-plot.png" width="200"> | <img src="media/samples/decision-tree-chart.png" width="200"> | <img src="media/samples/forecasting-tbats.png" width="200"> 
| [Korrelaatiokaavio](https://github.com/Microsoft/powerbi-visuals-corrplot/) </br>Korosta tietotaulukon korreloivimmat muuttujat | [Päätöspuukaavio](https://github.com/Microsoft/powerbi-visuals-decision-tree/) </br>Puun muotoinen toimintakaavio tilastollisen todennäköisyyden määrittämiseksi rekursiivisen osioinnin avulla | [TBATS-ennusteet](https://github.com/Microsoft/powerbi-visuals-forcasting-tbats/) </br>TBATS-mallin avulla suoritettavat aikasarjaennusteet sarjalle, jolla on useita kausivaihteluja malleja
| <img src="media/samples/forecasting-with-ARIMA.png" width="200"> | <img src="media/samples/funnel-plot.png" width="200"> | <img src="media/samples/outliers-detection.png" width="200"> 
| [Ennustaminen ARIMA:n avulla](https://github.com/Microsoft/powerbi-visuals-forcastingarima/) </br>Ennakoi tulevat arvot historiallisten tietojen perusteella käyttäen autoregressiivistä integroitua liukuvaa keskiarvoa (ARIMA) | [Suppilokaavio](https://github.com/Microsoft/powerbi-visuals-funnel/) </br>Etsi suppilokaavion avulla poikkeavat arvot tiedoista | [Poikkeamien havaitseminen](https://github.com/Microsoft/powerbi-visuals-outliers-det/) </br>Selvitä tietojesi poikkeamat sopivimmalla menetelmällä ja kaaviolla
| <img src="media/samples/spline-chart.png" width="200"> | <img src="media/samples/time-series-decomposition-chart.png" width="200"> | <img src="media/samples/time-series-forecasting-chart.png" width="200">
| [Splinikaavio](https://github.com/Microsoft/powerbi-visuals-spline/) </br>Visualisoi ja selvitä tietojen häiriöt | [Aikasarjan hajautuskaavio](https://github.com/Microsoft/powerbi-visuals-timeseriesdecomposition/) </br>Selvitä aikasarjakomponentit STL:n (Seasonal and Trend decomposition using Loess) avulla | [Aikasarjan ennustekaavio](https://github.com/Microsoft/powerbi-visuals-forcasting-exp/) </br>Eksponentiaalisen tasoitusmallin käyttäminen tulevien arvojen ennustamiseen aiemmin havaittujen arvojen perusteella

## <a name="next-steps"></a>Seuraavat vaiheet

Jos haluat kokeilla Power BI -visualisointien luomista, lue [Opetusohjelma: Power BI -visualisoinnin kehittäminen](custom-visual-develop-tutorial.md).
