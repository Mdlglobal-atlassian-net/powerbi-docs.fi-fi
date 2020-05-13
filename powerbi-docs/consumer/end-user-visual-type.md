---
title: Visualisointityypit kuluttajille Power BI:ssä
description: Visualisointityypit Power BI -palvelussa
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: mihart
LocalizationGroup: Consumer
ms.openlocfilehash: acfcd863a537153e70734d5f83e89e384438885e
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279430"
---
# <a name="visual-types-in-power-bi"></a>Visualisointityypit Power BI:ssä

[!INCLUDE[consumer-appliesto-yynn](../includes/consumer-appliesto-yynn.md)]

Visualisointeja on raporteissa, koontinäytöissä, sovelluksissa ja Q&A:ssa. Jotkin näistä visualisointityypeistä ovat Power BI:hin sisältyviä visualisointeja ja jotkin *Power BI -visualisointeja*. Mukautetut visualisoinnit luodaan Power BI:n ulkopuolella siten, että *raporttien suunnittelijat* voivat lisätä niitä Power BI:n raportteihin ja koontinäyttöihin. 

Tämä artikkeli on yleiskatsaus Power BI -palveluun sisältyvistä visualisoinneista.  Ne ovat visualisointeja, joita näet useimmin. Lisätietoja näistä visualisoinneista on [Power BI:n raporttien*visualisointityyppien* suunnitteluohjeissa](../visuals/power-bi-visualization-types-for-reports-and-q-and-a.md)

> [!NOTE]
> Jos haluat lisätietoja Power BI -visualisoinneista, hae niitä [Microsoft AppSourcen](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)**Power BI -visualisointien osiossa**. Näet kustakin visualisoinnista kuvauksen, sen tekijän tiedot ja joko näyttökuvia tai videon. 

## <a name="list-of-visuals-available-in-power-bi"></a>Power BI:ssä käytettävissä olevien visualisointityyppien luettelo
Kaikki nämä visualisoinnit löytyvät Power BI:n koontinäytöistä ja raporteista ja tietyistä [Q&A-osioista](end-user-q-and-a.md). Jos haluat ohjeita visualisointien käyttöön, lue ohjeartikkeli [Visualisointien käyttö raporteissa, koontinäytöissä ja sovelluksissa](end-user-visualizations.md)

### <a name="area-charts-basic-layered-and-stacked"></a>Aluekaaviot: Perus (kerrostettu) ja pinottu
![aluekaavio](media/end-user-visual-type/basic-area-map-small.png)

Perusaluekaavio perustuu viivakaavioon, jonka alue on akselin ja täytetyn viivan välillä. Aluekaaviot korostavat muutoksen suuruutta ajan kuluessa, ja niiden avulla voidaan kiinnittää huomio trendin kokonaisarvoon. Esimerkiksi tiedot, jotka edustavat tuottoa ajan kuluessa, voidaan kuvata aluekaaviossa kokonaistuoton korostamiseksi.

### <a name="bar-and-column-charts"></a>Palkki- ja pylväskaaviot
![pylväskaavio](media/end-user-visual-type/pbi-nancy-viz-bar.png)

 ![palkkikaavio](media/end-user-visual-type/pbi-nancy-viz-col.png)

Palkkikaaviot ovat vakiomuotoisia katseltaessa tiettyä arvoa eri luokkien välillä.

### <a name="cards-single-number"></a>Kortit: Yksittäinen luku
![yksittäinen luku -kortti](media/end-user-visual-type/pbi-nancy-viz-card.png)

Yksittäisen luvun kortissa näytetään yksi fakta, yksi arvopiste. Joskus yksittäinen luku on tärkein seikka, jota haluat seurata Power BI-raporttinäytöllä tai raportissa, kuten kokonaismyynti, markkinaosuus vuositasolla tai kokonaismahdollisuudet.  

### <a name="cards-multi-row"></a>Kortit: Moniriviset
![monirivinen kortti](media/end-user-visual-type/multi-row-card.png)

Monirivisissä korteissa näytetään yksi arvopiste tai useita arvopisteitä, yksi per rivi.


### <a name="combo-charts"></a>Yhdistelmäkaaviot
![yhdistelmäkaavio](media/end-user-visual-type/combo-small.png)

Yhdistelmäkaavio yhdistää pylväskaavion ja viivakaavion. Näiden kahden kaavion yhdistäminen nopeuttaa tietojen vertailua. Yhdistelmäkaavioissa voi olla yksi y-akseli tai kaksi y-akselia, joten tarkista kaavio tarkasti. 

Yhdistelmäkaavio on hyvä vaihtoehto, kun:
- sinulla on viivakaavio ja pylväskaavio, joilla on sama X-akseli
- haluat vertailla useita mittareita eri arvoalueilla
- haluat havainnollistaa kahden mittarin välistä korrelaatiota yhdessä visualisoinnissa
- haluat tarkistaa, täyttääkö mittari toisen mittarin määrittämän tavoitteen
- haluat säästää tilaa piirtoalustalla.

### <a name="doughnut-charts"></a>Rengaskaaviot
![rengaskaavio](media/end-user-visual-type/donut-small.png)

Rengaskaaviot muistuttavat ympyräkaavioita.  Ne näyttävät osien suhteen kokonaisuuteen. Ainoa ero on se, että keskellä on tyhjää tilaa otsikkoa tai kuvaketta varten.

### <a name="funnel-charts"></a>Suppilokaavio
![suppilokaavio](media/end-user-visual-type/pbi-nancy-viz-funnel.png)

Suppilokaaviot auttavat visualisoimaan prosessia, jossa on vaiheita ja tietoyksikön työnkulku peräkkäin yhdestä vaiheesta seuraavaan.  Esimerkki tällaisesta on vaikkapa myyntiprosessi, joka alkaa liideistä ja päättyy ostamiseen.

Esimerkiksi myynnistä voi tehdä suppilokaavion, jossa seurataan asiakkuuksien eri vaiheita: liidi > hyväksytty liidi > prospekti > sopimus > myynti. Suppilon muoto välittää yhdellä silmäyksellä tarkastelemasi prosessin kunnon.
Suppilon kukin vaihe edustaa prosenttiosuutta kokonaismäärästä. Siten useimmissa tapauksissa suppilokaaviosta tulee suppilon muotoinen – ensimmäinen vaihe on kaikkein suurin ja kukin seuraava vaihe on pienempi kuin sitä edeltänyt vaihe. Myös päärynänmuotoisista suppilokaavioista on hyötyä: sen avulla voi tunnistaa ongelman prosessissa. Tyypillisesti kuitenkin ensimmäinen vaihe, ”sisäänotto”, on kaikkein suurin.


### <a name="gauge-charts"></a>Mittarikaaviot
![mittarikaavio](media/end-user-visual-type/gauge-m.png)

Viisarimittarikaaviossa on pyöreä kaari, ja siinä on yksi arvo, joka mittaa edistymistä kohti tavoitetta/suorituskyvyn mittaria. Tavoite tai tavoitearvo esitetään riveittäin (neula). Tämän päämäärän edistyminen esitetään varjostuksella. Arvo, joka edustaa kyseistä edistymistä, näkyy lihavoituna kaaren sisällä. Kaikki mahdolliset arvot on jaettu tasaisesti kaarta pitkin minimistä (äärimmäisenä vasemmalla oleva arvo) maksimiin (äärimmäisenä oikealla oleva arvo).

Yllä olevassa esimerkissä olemme automyyjä, joka seuraa myyntitiimin keskimääräistä myyntiä kuukaudessa. Tavoitteemme on 140, ja sitä edustaa musta neula. Pienin mahdollinen keskimääräinen myynti on 0, ja maksimiksi on asetettu 200. Sininen varjostus näyttää, että olemme tällä hetkellä noin 120 kappaleen vauhdissa tässä kuussa. Onneksi meillä on vielä viikko aikaa tavoitteiden saavuttamiseksi.

Viisarimittarit ovat hyvä vaihtoehto, kun:
- esitetään edistyminen kohti tavoitetta
- esitetään prosenttiyksiköitä, kuten suorituskyvyn mittareita
- näyttää yhden mittarin kunnon
- näytetään tiedot, joita voidaan nopeasti tarkistaa ja ymmärtää.

 ### <a name="key-influencers-chart"></a>Tärkeimpien vaikuttajien kaavio
![tärkein vaikuttaja](media/end-user-visual-type/power-bi-influencer.png)

Tärkeimpien vaikuttajien kaaviossa näytetään valittuun tulokseen tai arvoon eniten vaikuttavat tekijät.

Tärkeimmät vaikuttajat auttaa sinua ymmärtämään tekijöitä, jotka vaikuttavat johonkin tärkeään arvoon. Tällainen vaikuttaja voi olla esimerkiksi se, *mikä saa asiakkaat tekemään toisen tilauksen *tai* miksi myynti oli hyvällä tasolla viime kesäkuussa*. 

### <a name="kpis"></a>Suorituskyvyn mittarit
![suorituskykymittari](media/end-user-visual-type/power-bi-kpi.png)

Suorituskykyilmaisin (KPI) on visuaalinen vihje, joka kertoo edistymisen määrän kohti mitattavissa olevaa tavoitetta. 

Suorituskykyilmaisin on hyvä vaihtoehto, kun halutaan
- mitata edistymistä (minkä edellä vai jäljessä olen?)
- mitata etäisyyttä tavoitteeseen (kuinka paljon edellä tai jäljessä olen?)

### <a name="line-charts"></a>Viivakaaviot
![viivakaavio](media/end-user-visual-type/pbi-nancy-viz-line.png)

Viivakaaviot korostavat koko arvosarjan yleistä muotoa yleensä ajan kuluessa.

### <a name="maps-basic-maps"></a>Kartat: Peruskartat
![peruskartta](media/end-user-visual-type/pbi-nancy-viz-map.png)

Peruskarttaa käytetään sekä luokiteltuun että kvantitatiiviseen tietoon, joilla on paikkatietojen sijainnit.

### <a name="maps-arcgis-maps"></a>Kartat: ArcGIS-kartat
![ArcGis-kartta](media/end-user-visual-type/power-bi-esri-map-theme2.png)

ArcGIS-kartat ja Power BI yhdessä tekevät kartoista muutakin kuin vain esitettäviä pisteitä. Valittavissasi on pohjakarttoja, sijaintityyppejä, teemoja, symbolityylejä ja viittauskerroksia, joiden avulla voit luoda upeita, informatiivisia karttavisualisointeja. Määräävien tietokerrosten (kuten laskentatietojen) yhdistäminen sijaintikohtaista analyysiä sisältäviin karttoihin mahdollistaa visualisoinnin tietojen ymmärtämisen syvemmin.

### <a name="maps-filled-maps-choropleth"></a>Kartat: Täytetyt kartat (Choropleth)
![täytetty kartta](media/end-user-visual-type/pbi-nancy-viz-filledmap.png)

Täytetyssä kartassa käytetään sävytystä tai kuvioita esittämään, miten arvot vaihtelevat suhteellisesti maantieteellisellä alueella. Suhteelliset erot hahmottuvat nopeasti, kun sävytys vaihtelee vaaleammasta (tarkoittaen harvinaisempaa/pienempää) tummempaan (yleisempi/enemmän).

### <a name="maps-shape-maps"></a>Kartat: Muotokartat
![muotokartta](media/end-user-visual-type/power-bi-shape-map2.png)

Muotokartalla verrataan alueita kartalla värien avulla. Muotokartta ei voi näyttää arvopisteiden tarkkoja maantieteellisiä sijainteja kartalla. Sen sijaan sen päätarkoituksena on näyttää alueiden suhteellisia vertailuja kartalla eri värien avulla.

### <a name="matrix"></a>Matriisi
![matriisi](media/end-user-visual-type/matrix.png)

Matriisivisualisointi on eräänlainen taulukkovisualisointi (sillä on oma kohtansa alla), joka tukee vaiheittaista asettelua. Raporttien suunnittelijat lisäävät usein matriiseja raportteihin ja koontinäyttöihin, jotta käyttäjät voivat valita yhden elementin tai useita elementtejä (rivejä, sarakkeita tai soluja) matriisista ristiinkorostaakseen muita visualisointeja raporttisivulla.  

### <a name="pie-charts"></a>Ympyräkaaviot
![ympyräkaavio](media/end-user-visual-type/pbi-nancy-viz-pie.png)

Ympyräkaaviot näyttävät osien suhteen kokonaisuuteen. 

### <a name="power-apps-visual"></a>Power Apps -visualisointi
![Power Apps -visualisointi](media/end-user-visual-type/power-bi-powerapps-visual.png)

Raporttien suunnittelijat voivat luoda Power Apps -visualisoinnin ja upottaa sen Power BI -raporttiin. Käyttäjät voivat käsitellä tätä visualisointia Power BI -raportissa. 

### <a name="qa-visual"></a>Q&A-visualisointi
![Q&A-visualisoinnit](media/end-user-visual-type/power-bi-q-and-a.png)

>[!TIP]
>Samaan tapaan kuin [koontinäytön Q&A-kokemuksen kanssa](../create-reports/power-bi-tutorial-q-and-a.md), Q&A-visualisoinnin avulla voit esittää kysymyksiä tiedoistasi käyttämällä luonnollista kieltä. 

Lisätietoja on artikkelissa [Q&A-visualisoinnit Power BI:ssä](../visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

### <a name="ribbon-chart"></a>Nauhakaavio
![nauhakaavio](media/end-user-visual-type/power-bi-ribbon.png)

Nauhakaaviot näyttävät, millä tietoluokalla on paras sijoitus (suurin arvo). Nauhakaaviot esittävät luokkamuutoksen tehokkaasti, koska korkein sija (suurin arvo) näkyy aina ylimpänä kullakin ajanjaksolla.

### <a name="scatter-bubble-and-dot-plot-charts"></a>Piste-, kupla- ja pistetulostuskaaviot


Pistekaaviossa on aina kaksi arvoakselia, jotka näyttävät yhden numeerisen tietosarjan vaakasuuntaisella akselilla ja toisen numeerisen arvosarjan pystysuuntaisella akselilla. Kaaviossa näytetään arvopisteet numeerisen arvon X ja Y leikkauskohdassa yhdistämällä nämä kaksi arvoa yhdeksi arvopisteeksi. Nämä arvopisteet voidaan jakaa tasaisesti tai epätasaisesti vaakasuuntaiselle akselille tietojen mukaan.

![kuplakaavio](media/end-user-visual-type/pbi-nancy-viz-bubble.png)

Kuplakaaviossa arvopisteet korvataan kuplilla ja kuplan koko kuvastaa tietojen muuta dimensiota.



Pistetulostuskaavio muistuttaa kuplakaaviota ja hajontaa kuvaavaa pistekaaviota sillä erotuksella, että X-akselille voi tulostaa numeerisia tai luokittaisia tietoja. Tässä esimerkissä käytetään neliöitä ympyröiden sijaan ja piirretään myynti X-akselille.

![pistetulostuskaavio](media/end-user-visual-type/power-bi-dot-plot-squares.png)

### <a name="scatter-high-density"></a>Suuren tiheyden pistekaavio
![suuren tiheyden pistekaavio](media/end-user-visual-type/density-scatter.png)

Suuren tiheyden tiedoista otetaan näytteitä siksi, että näin voidaan kohtuullisen nopeasti luoda visualisointeja, joiden vuorovaikutteisuus säilyy. Suuren tiheyden tiedoissa käytetään algoritmia, joka poistaa päällekkäiset pisteet ja varmistaa, että kaikki tietojoukon pisteet näytetään visualisoinnissa. Se ei näytä vain näytettä tiedoista.  

Tämä tarjoaa parhaan vasteajan ja esityksen ja taltioi selkeästi tärkeimmät pisteet koko tietojoukosta.

### <a name="slicers"></a>Osittajat
![osittaja](media/end-user-visual-type/pbi-slicer.png)

Osittaja on erillinen kaavio, jolla voidaan suodattaa sivun muita visualisointeja. Osittajia on monia erilaisia (luokka, alue, päivämäärä jne.). Niitä voidaan muotoilla siten, että on mahdollista valita yksi arvo, monia arvoja tai kaikki saatavilla olevat arvot. 

Ohittaja on hyvä vaihtoehto, kun haluat
- helpottaa käyttöä näyttämällä usein käytettyjä tai tärkeitä suodattimia raportin piirtoalustassa
- helpottaa nykyisen suodatetun tilan tarkastelua avaamatta avattavaa luetteloa
- käyttää suodatuksessa sarakkeita, jotka ovat tarpeettomia ja piilotettuina tietotaulukoissa
- luoda tarkempia raportteja sijoittamalla osittajia tärkeiden visualisointien viereen.

### <a name="standalone-images"></a>Erilliset kuvat
![erillinen kuva](media/end-user-visual-type/pbi-nancy-viz-image.png)

Erillinen kuva on graafinen elementti, joka on lisätty raporttiin tai koontinäyttöön. 


### <a name="tables"></a>Taulukot
![taulukkokaavio](media/end-user-visual-type/table-type.png)

Taulukko on ruudukko, joka sisältää tietoja järjestettynä loogiseen sarjaan rivejä ja sarakkeita. Se voi sisältää myös otsikkoja ja summarivin. Taulukot toimivat hyvin kvantitatiivisessa vertailussa, jossa tarkastellaan moni arvoja tietystä kategoriasta. Esimerkiksi tässä taulukossa näkyvät luokan viisi eri mittaria.

Taulukko on hyvä vaihtoehto:
- yksityiskohtaisen tiedon ja tarkkojen arvojen selaamiseen ja vertailemiseen (visuaalisten esitysmuotojen sijaan).
- tietojen esittämiseen taulukkomuodossa.
- numeeristen tietojen luokiteltuun esittämiseen.

### <a name="treemaps"></a>Puukartat
![puukarttakaavio](media/end-user-visual-type/pbi-nancy-viz-tree.png)

Puukartat ovat värillisiä suorakulmioita, joiden koko vastaa arvoa.  Ne voivat olla hierarkkisia, suorakulmiot sisäkkäin pääsuorakulmioissa. Kunkin suorakulmion sisällä oleva suorakulmio perustuu mitattavaan arvoon. Suorakulmiot järjestetään koon mukaan vasemmasta yläkulmasta (suurin) oikeaan alakulmaan (pienin).

Puukartat ovat hyvä vaihtoehto seuraaville:
- näyttää suuria määriä hierarkkisia tietoja
- palkkikaaviolla ei voida tehokkaasti käsitellä suuria määriä arvoja
- näyttää kunkin osan väliset ja koko kokonaisuuden mittasuhteet
- näyttää mittarin jakautuminen kuviona kussakin hierarkian luokkatasossa
- näyttää määritteet kokovertailun ja värikoodauksen avulla
- kuvioiden, poikkeavien arvojen, tärkeimpien tekijöiden ja poikkeusten erottuvan selvästi.

### <a name="waterfall-charts"></a>Vesiputouskaaviot
![vesiputouskaavio](media/end-user-visual-type/waterfall-small.png)

Vesiputouskaavio näyttää juoksevan summan, kun arvoja lisätään tai vähennetään. On hyödyllistä ymmärtää, kuinka positiivisten ja negatiivisten muutosten sarja vaikuttaa alkuarvoon (esimerkiksi nettotuloon).

Sarakkeet ovat värillisiä, jotta näet nopeasti nousut ja laskut. Alkuarvon ja lopullisen arvon sarakkeet usein alkavat vaaka-akselilla, kun taas keskitason arvot ovat irrallisia sarakkeita. Tämän ulkoasun vuoksi vesiputouskaavioita kutsutaan myös siltakaavioiksi.

Vesiputouskaavio on hyvä vaihtoehto:
- kun olet tehnyt muutoksia mittarin aikasarjaan tai eri luokkiin
- jos haluat valvoa tärkeimpiä kokonaisarvoon vaikuttavia muutoksia
- jos haluat tehdä kaavion yrityksen vuosittaisesta tuotosta näyttämällä eri tulonlähteitä ja lopulta kokonaisvoiton (tai tappion).
- jos haluat havainnollistaa yrityksen alku- ja lopetushenkilöstömäärän vuoden aikana
- jos haluat visualisoida, kuinka paljon rahaa ansaitset ja käytät joka kuukausi sekä tilin juoksevan saldon.

## <a name="tell-qa-which-visual-to-use"></a><a name="qna"></a>Kerro Q&A:lle, minkä visualisoinnin haluat
Kun kirjoitat Power BI Q&A:lla kyselyjä luonnollisella kielellä, voit määrittää visualisointityypin kyselyssäsi.  Esimerkki:


”***myynti osavaltioittain puukarttana***”

![q&a-istunto](media/end-user-visual-type/qa-treemap.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisointien käyttö raporteissa, koontinäytöissä ja sovelluksissa](end-user-visualizations.md)    
[Oikealla oleva visuaalinen viite osoitteesta sqlbi.com](https://www.sqlbi.com/wp-content/uploads/videotrainings/dashboarddesign/visuals-reference-may2017-A3.pdf)

