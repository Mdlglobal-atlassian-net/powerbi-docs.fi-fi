---
title: Visualisointityypit kuluttajille Power BI:ssä
description: Visualisointityypit Power BI -palvelussa
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/24/2019
ms.author: mihart
LocalizationGroup: Consumer
ms.openlocfilehash: 174886acf1d827497b48d660bb89e2b4057b09b9
ms.sourcegitcommit: 2954de034f5e1be655dd02cc756ff34f126d3034
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2019
ms.locfileid: "55234587"
---
# <a name="visualization-types-in-power-bi"></a>Visualisointityypit Power BI:ssä
Visualisointeja löytyy raporteista, koontinäytöistä, sovelluksista ja Q&A:sta. Jotkin näistä visualisointityypeistä ovat Power BI:hin sisältyviä visualisointeja ja jotkin ovat *mukautettuja visualisointeja*. Mukautetut visualisoinnit luodaan Power BI:n ulkopuolella siten, että *raporttien suunnittelijat* voivat lisätä niitä Power BI:n raportteihin, koontinäyttöihin ja sovelluksiin. 

Tämä artikkeli on yleiskatsaus Power BI:hin sisältyvistä visualisoinneista.  Ne ovat visualisointeja, joita näet useimmin. 

> [!NOTE]
> Jos haluat lisätietoja mukautetuista visualisoinneista, hae niitä [Microsoft AppSourcen](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) **Power BI -visualisointien osiossa**. Näet kustakin visualisoinnista kuvauksen, sen tekijän tiedot ja joko näyttökuvia tai videon. 

## <a name="list-of-visualizations-available-in-power-bi"></a>Luettelo visualisoinneista, jotka ovat käytettävissä Power BI:ssa
Kaikki nämä visualisoinnit löytyvät Power BI:n sovelluksista, koontinäytöistä, raporteista ja tietyistä [Q&A-osioista](#gna).

### <a name="area-charts-basic-layered-and-stacked"></a>Aluekaaviot: Perus (kerrostettu) ja pinottu
![aluekaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/basicareamapsmall.png)

Perusaluekaavio perustuu viivakaavioon, jonka alue on akselin ja täytetyn viivan välillä. Aluekaaviot korostavat muutoksen suuruutta ajan kuluessa, ja niiden avulla voidaan kiinnittää huomio trendin kokonaisarvoon. Esimerkiksi tiedot, jotka edustavat tuottoa ajan kuluessa, voidaan kuvata aluekaaviossa kokonaistuoton korostamiseksi.

### <a name="bar-and-column-charts"></a>Palkki- ja pylväskaaviot
![pylväskaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_bar.png)

 ![palkkikaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_col.png)

Palkkikaaviot ovat vakiomuotoisia katseltaessa tiettyä arvoa eri luokkien välillä.

### <a name="cards-single-number"></a>Kortit: Yksittäinen luku
![yksittäinen luku -kortti](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_card.png)

Yksittäisen luvun kortissa näytetään yksi fakta, yksi arvopiste. Joskus yksittäinen luku on tärkein seikka, jota haluat seurata Power BI-raporttinäytöllä tai raportissa, kuten kokonaismyynti, markkinaosuus vuositasolla tai kokonaismahdollisuudet.  

### <a name="cards-multi-row"></a>Kortit: Moniriviset
![monirivinen kortti](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/multi-row-card.png)

Monirivisissä korteissa näytetään yksi arvopiste tai useita arvopisteitä, yksi per rivi.


### <a name="combo-charts"></a>Yhdistelmäkaaviot
![yhdistelmäkaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/combosmall.png)

Yhdistelmäkaavio yhdistää pylväskaavion ja viivakaavion. Näiden kahden kaavion yhdistäminen nopeuttaa tietojen vertailua. Yhdistelmäkaavioissa voi olla yksi y-akseli tai kaksi y-akselia, joten tarkista kaavio tarkasti. 

Yhdistelmäkaavio on hyvä vaihtoehto, kun
- sinulla on viivakaavio ja pylväskaavio, joilla on sama X-akseli
- haluat vertailla useita mittayksiköitä eri arvoalueilla
- haluat havainnollistaa kahden mittayksikön välistä korrelaatiota yhdessä visualisoinnissa
- haluat tarkistaa, täyttääkö mittayksikkö toisen mittayksikön määrittämän tavoitteen
- haluat säästää tilaa piirtoalustalla.

### <a name="doughnut-charts"></a>Rengaskaaviot
![rengaskaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/donutsmall.png)

Rengaskaaviot muistuttavat ympyräkaavioita.  Ne näyttävät osien suhteen kokonaisuuteen. Ainoa ero on se, että keskellä on tyhjää tilaa otsikkoa tai kuvaketta varten.

### <a name="funnel-charts"></a>Suppilokaavio
![suppilokaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_funnel.png)

Suppilokaaviot auttavat visualisoimaan prosessia, jossa on vaiheita ja tietoyksikön työnkulku peräkkäin yhdestä vaiheesta seuraavaan.  Esimerkki tällaisesta on vaikkapa myyntiprosessi, joka alkaa liideistä ja päättyy ostamiseen.

Esimerkiksi myynnistä voi tehdä suppilokaavion, jossa seurataan asiakkuuksien eri vaiheita: liidi > hyväksytty liidi > prospekti > sopimus > myynti. Suppilon muoto välittää yhdellä silmäyksellä tarkastelemasi prosessin kunnon.
Suppilon kukin vaihe edustaa prosenttiosuutta kokonaismäärästä. Siten useimmissa tapauksissa suppilokaaviosta tulee suppilon muotoinen – ensimmäinen vaihe on kaikkein suurin ja kukin seuraava vaihe on pienempi kuin sitä edeltänyt vaihe. Myös päärynänmuotoisista suppilokaavioista on hyötyä: sen avulla voi tunnistaa ongelman prosessissa. Tyypillisesti kuitenkin ensimmäinen vaihe, ”sisäänotto”, on kaikkein suurin.

Suppilokaavio on hyvä vaihtoehto:
- kun tiedot seuraavat toinen toistaan ja etenevät vähintään 4 vaiheen kautta.
- kun on odotettavissa, että ”kohteiden” määrä ensimmäisessä vaiheessa on suurempi kuin viimeisessä vaiheessa.
- kun haluat laskea (tuoton/myyntien/sopimuksien jne.) mahdollisuuksia vaihekohtaisesti.
- kun haluat laskea ja seurata konversio- ja asiakaspoistuma-astetta.
- kun haluat paljastaa lineaarisen prosessin pullonkauloja.
- kun haluat seurata ostoskorin työnkulkua.
- kun haluat seurata napsautusvaiheiden kautta etenevien mainos- tai markkinointikampanjoiden etenemistä ja onnistumista.

### <a name="gauge-charts"></a>Mittarikaaviot
![mittarikaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/gauge_m.png)

Viisarimittarikaaviossa on pyöreä kaari, ja siinä on yksi arvo, joka mittaa edistymistä kohti tavoitetta/suorituskyvyn mittaria. Tavoite tai tavoitearvo esitetään riveittäin (neula). Tämän päämäärän edistyminen esitetään varjostuksella. Arvo, joka edustaa kyseistä edistymistä, näkyy lihavoituna kaaren sisällä. Kaikki mahdolliset arvot on jaettu tasaisesti kaarta pitkin minimistä (äärimmäisenä vasemmalla oleva arvo) maksimiin (äärimmäisenä oikealla oleva arvo).

Yllä olevassa esimerkissä olemme automyyjä, joka seuraa myyntitiimin keskimääräistä myyntiä kuukaudessa. Tavoitteemme on 140, ja sitä edustaa musta neula. Pienin mahdollinen keskimääräinen myynti on 0, ja maksimiksi on asetettu 200. Sininen varjostus näyttää, että olemme tällä hetkellä noin 120 kappaleen vauhdissa tässä kuussa. Onneksi meillä on vielä viikko aikaa tavoitteiden saavuttamiseksi.

Viisarimittarit ovat hyvä vaihtoehto, kun
- esitetään edistyminen kohti tavoitetta
- esitetään prosenttiyksiköitä, kuten suorituskyvyn mittareita
- näytetään yhden mittauksen kunto
- näytetään tiedot, joita voidaan nopeasti tarkistaa ja ymmärtää.

<!-- ### Key influencers chart
![key influencer](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-influencers2.png)

A key influencer chart displays the major contributors to a selected result or value.  -->

### <a name="kpis"></a>Suorituskyvyn mittarit
![suorituskykymittari](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-kpi.png)

Suorituskykyilmaisin (KPI) on visuaalinen vihje, joka kertoo edistymisen määrän kohti mitattavissa olevaa tavoitetta. 

Suorituskykyilmaisin on hyvä vaihtoehto, kun halutaan
- mitata edistymistä (minkä edellä vai jäljessä olen?)
- mitata etäisyyttä tavoitteeseen (kuinka paljon edellä tai jäljessä olen?)

### <a name="line-charts"></a>Viivakaaviot
![viivakaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_line.png)

Viivakaaviot korostavat koko arvosarjan yleistä muotoa yleensä ajan kuluessa.

### <a name="maps-basic-maps"></a>Kartat: Peruskartat
![peruskartta](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi-nancy_viz_map.png)

Peruskarttaa käytetään sekä luokiteltuun että kvantitatiiviseen tietoon, joilla on paikkatietojen sijainnit.

### <a name="maps-arcgis-maps"></a>Kartat: ArcGIS-kartat
![ArcGis-kartta](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-esri-map-theme2.png)

ArcGIS-kartat ja Power BI yhdessä tekevät kartoista muutakin kuin vain esitettäviä pisteitä. Valittavissasi on pohjakarttoja, sijaintityyppejä, teemoja, symbolityylejä ja viittauskerroksia, joiden avulla voit luoda upeita, informatiivisia karttavisualisointeja. Määräävien tietokerrosten (kuten laskentatietojen) yhdistäminen sijaintikohtaista analyysiä sisältäviin karttoihin mahdollistaa visualisoinnin tietojen ymmärtämisen syvemmin.

### <a name="maps-filled-maps-choropleth"></a>Kartat: Täytetyt kartat (Choropleth)
![täytetty kartta](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_filledmap.png)

Täytetyssä kartassa käytetään sävytystä tai kuvioita esittämään, miten arvot vaihtelevat suhteellisesti maantieteellisellä alueella. Suhteelliset erot hahmottuvat nopeasti, kun sävytys vaihtelee vaaleammasta (tarkoittaen harvinaisempaa/pienempää) tummempaan (yleisempi/enemmän).

### <a name="maps-shape-maps"></a>Kartat: Muotokartat
![muotokartta](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-shape-map2.png)

Muotokartalla verrataan alueita kartalla värien avulla. Muotokartta ei voi näyttää arvopisteiden tarkkoja maantieteellisiä sijainteja kartalla (toisin kuin karttavisualisoinnit). Sen sijaan sen päätarkoituksena on näyttää alueiden suhteellisia vertailuja kartalla eri värien avulla.

### <a name="matrix"></a>Matrix
![matriisi](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/matrix.png)

Matriisivisualisointi on eräänlainen taulukkovisualisointi (sillä on oma kohtansa alla), joka tukee vaiheittaista asettelua. Raporttien suunnittelijat lisäävät usein matriiseja raportteihin ja koontinäyttöihin, jotta käyttäjät voivat valita yhden elementin tai useita elementtejä (rivejä, sarakkeita tai soluja) matriisista ristiinkorostaakseen muita visualisointeja raporttisivulla.  

### <a name="pie-charts"></a>Ympyräkaaviot
![ympyräkaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_pie.png)

Ympyräkaaviot näyttävät osien suhteen kokonaisuuteen. 

### <a name="ribbon-chart"></a>Nauhakaavio
![nauhakaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/power-bi-ribbon.png)

Nauhakaaviot näyttävät, millä tietoluokalla on paras sijoitus (suurin arvo). Nauhakaaviot esittävät luokkamuutoksen tehokkaasti, koska korkein sija (suurin arvo) näkyy aina ylimpänä kullakin ajanjaksolla.

### <a name="scatter-bubble-and-dot-plot-charts"></a>Piste-, kupla- ja pistetulostuskaaviot


Pistekaaviossa on aina kaksi arvoakselia, jotka näyttävät yhden numeerisen tietosarjan vaakasuuntaisella akselilla ja toisen numeerisen arvosarjan pystysuuntaisella akselilla. Kaaviossa näytetään arvopisteet numeerisen arvon X ja Y leikkauskohdassa yhdistämällä nämä kaksi arvoa yhdeksi arvopisteeksi. Nämä arvopisteet voidaan jakaa tasaisesti tai epätasaisesti vaakasuuntaiselle akselille tietojen mukaan.

![kuplakaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_bubble.png)

Kuplakaaviossa arvopisteet korvataan kuplilla ja kuplan koko kuvastaa tietojen muuta dimensiota.

Pistetulostuskaavio muistuttaa kuplakaaviota ja hajontaa kuvaavaa pistekaaviota sillä erotuksella, että X-akselille voi tulostaa numeerisia tai luokittaisia tietoja.

### <a name="scatter-high-density"></a>Suuren tiheyden pistekaavio
![suuren tiheyden pistekaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/density-scatter.png)

Suuren tiheyden tiedoista otetaan näytteitä siksi, että näin voidaan kohtuullisen nopeasti luoda visualisointeja, joiden vuorovaikutteisuus säilyy. Suuren tiheyden tiedoissa käytetään algoritmia, joka poistaa päällekkäiset pisteet ja varmistaa, että kaikki tietojoukon pisteet näytetään visualisoinnissa. Se ei näytä vain näytettä tiedoista.  

Tämä tarjoaa parhaan vasteajan ja esityksen ja taltioi selkeästi tärkeimmät pisteet koko tietojoukosta.

### <a name="slicers"></a>Osittajat
![osittaja](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_slicer.png)

Osittaja on erillinen kaavio, jolla voidaan suodattaa sivun muita visualisointeja. Osittajia on monia erilaisia (luokka, alue, päivämäärä jne.). Niitä voidaan muotoilla siten, että on mahdollista valita yksi arvo, monia arvoja tai kaikki saatavilla olevat arvot. 

Ohittaja on hyvä vaihtoehto, kun haluat
- helpottaa käyttöä näyttämällä usein käytettyjä tai tärkeitä suodattimia raportin piirtoalustassa
- helpottaa nykyisen suodatetun tilan tarkastelua avaamatta avattavaa luetteloa
- käyttää suodatuksessa sarakkeita, jotka ovat tarpeettomia ja piilotettuina tietotaulukoissa
- luoda tarkempia raportteja sijoittamalla osittajia tärkeiden visualisointien viereen.

### <a name="standalone-images"></a>Erilliset kuvat
![erillinen kuva](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_image.png)

Erillinen kuva on graafinen elementti, joka on lisätty raporttiin tai koontinäyttöön. 


### <a name="tables"></a>Taulukot
![taulukkokaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/tabletype.png)

Taulukko on ruudukko, joka sisältää tietoja järjestettynä loogiseen sarjaan rivejä ja sarakkeita. Se voi sisältää myös otsikkoja ja summarivin. Taulukot toimivat hyvin kvantitatiivisessa vertailussa, jossa tarkastellaan moni arvoja tietystä kategoriasta. Esimerkiksi tässä taulukossa näkyvät luokan viisi eri mittayksikköä.

Taulukko on hyvä vaihtoehto:
- yksityiskohtaisen tiedon ja tarkkojen arvojen selaamiseen ja vertailemiseen (visuaalisten esitysmuotojen sijaan).
- tietojen esittämiseen taulukkomuodossa.
- numeeristen tietojen luokiteltuun esittämiseen.

### <a name="treemaps"></a>Puukartat
![puukarttakaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/pbi_nancy_viz_tree.png)

Puukartat ovat värillisiä suorakulmioita, joiden koko vastaa arvoa.  Ne voivat olla hierarkkisia, suorakulmiot sisäkkäin pääsuorakulmioissa. Kunkin suorakulmion sisällä oleva suorakulmio perustuu mitattavaan arvoon. Suorakulmiot järjestetään koon mukaan vasemmasta yläkulmasta (suurin) oikeaan alakulmaan (pienin).

Puukartat ovat hyvä vaihtoehto, kun haluat
- näyttää suuria määriä hierarkkisia tietoja
- palkkikaaviolla ei voida tehokkaasti käsitellä suuria määriä arvoja
- näyttää kunkin osan väliset ja koko kokonaisuuden mittasuhteet
- näyttää mittayksikön jakautuminen kuviona kussakin hierarkian luokkatasossa
- näyttää määritteet kokovertailun ja värikoodauksen avulla
- kuvioiden, poikkeavien arvojen, tärkeimpien tekijöiden ja poikkeusten erottuvan selvästi.

### <a name="waterfall-charts"></a>Vesiputouskaaviot
![vesiputouskaavio](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/waterfallsmall.png)

Vesiputouskaavio näyttää juoksevan summan, kun arvoja lisätään tai vähennetään. On hyödyllistä ymmärtää, kuinka positiivisten ja negatiivisten muutosten sarja vaikuttaa alkuarvoon (esimerkiksi nettotuloon).

Sarakkeet ovat värillisiä, jotta näet nopeasti nousut ja laskut. Alkuarvon ja lopullisen arvon sarakkeet usein alkavat vaaka-akselilla, kun taas keskitason arvot ovat irrallisia sarakkeita. Tämän ulkoasun vuoksi vesiputouskaavioita kutsutaan myös siltakaavioiksi.

Vesiputouskaavio on hyvä vaihtoehto:
- kun olet tehnyt muutoksia mittayksikön aikasarjaan tai eri luokkiin
- jos haluat valvoa tärkeimpiä kokonaisarvoon vaikuttavia muutoksia
- jos haluat tehdä kaavion yrityksen vuosittaisesta tuotosta näyttämällä eri tulonlähteitä ja lopulta kokonaisvoiton (tai tappion).
- jos haluat havainnollistaa yrityksen alku- ja lopetushenkilöstömäärän vuoden aikana
- jos haluat visualisoida, kuinka paljon rahaa ansaitset ja käytät joka kuukausi sekä tilin juoksevan saldon.

## <a name="tell-qa-which-visualization-to-use"></a>Kerro Q&A:llen minkä visualisoinnin haluat
Power BI Q&A:lla kirjoitettaessa kyselyjä luonnollisella kielellä voit määrittää visualisointityypin kyselyssäsi.  Esimerkki:

”***myynti osavaltioittain puukarttana***”

![q&a-istunto](../visuals/media/power-bi-visualization-types-for-reports-and-q-and-a/qatreemap.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisoinnit Power BI -raporteissa](end-user-visualizations.md)    
[Oikealla oleva visuaalinen viite osoitteesta sqlbi.com](http://www.sqlbi.com/wp-content/uploads/videotrainings/dashboarddesign/visuals-reference-may2017-A3.pdf)