---
title: Visualisointiin porautuminen Power BI:ssä
description: Tässä asiakirjassa kerrotaan, miten voit porautua visualisointiin Power BI -palvelussa ja Power BI Desktopissa.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: MNAaHw4PxzE
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: fb834c92953c2cafcbca77bc1b3828b385755bca
ms.sourcegitcommit: 743e44fc8730fea0f7149916080b0c6d7eb6359d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/28/2018
ms.locfileid: "30974697"
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Visualisointiin porautuminen Power BI:ssä
## <a name="drill-down-requires-a-hierarchy"></a>Porautuminen edellyttää hierarkiaa
Kun visualisoinnissa on hierarkia, saat porautumalla näkyviin lisää tietoja. Sinulla voi olla esimerkiksi visualisointi, joka kuvaa olympiamitalien määrää hierarkian mukaan, joka muodostuu urheilusta, lajista ja tapahtumasta. Visualisointi näyttää oletusarvoisesti mitalimäärän urheilulajin mukaan – esimerkiksi voimistelu, hiihto ja vesiurheilu. Mutta koska sillä on hierarkia, visualisoinnin yhden elementin (kuten palkin, rivin tai kuplan) valitseminen antaa yksityiskohtaisemman kuvan. Valitsemalla **vesiurheilu**-elementin saat näkyviin uintia, uimahyppyä ja vesipalloa koskevat tiedot.  Valitsemalla **uimahyppy**-elementin saat näkyviin ponnahduslauta-, koroke- ja taitohyppytapahtumat.

Voit lisätä hierarkioita omistamiisi raportteihin, mutta et niihin, jotka on jaettu kanssasi.
Etkö ole varma, mitkä Power BI -visualisoinnit sisältävät hierarkian?  Pidä hiiren osoitinta visualisoinnin päällä, ja jos nämä porauksen ohjausobjektit tulevat näkyviin, visualisoinnissa on hierarkia.

![](media/power-bi-visualization-drill-down/power-bi-drill-icon4.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon3.png)
![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) ![](media/power-bi-visualization-drill-down/power-bi-drill-icon6.png)  

Päivämäärät ovat hierarkian yksilöivä tyyppi. Kun lisäät visualisointiin päivämääräkentän, Power BI lisää automaattisesti aikahierarkian, joka sisältää vuoden, vuosineljänneksen, kuukauden ja päivän. Lisätietoja saat [Visuaaliset hierarkiat ja porautuminen](guided-learning/visualizations.yml#step-18) -opetusohjelmasta tai katsomalla alla oleva video.


  <iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Opettele luomaan hierarkioita Power BI Desktopin avulla katsomalla [How to create and add hierarchies](https://youtu.be/q8WDUAiTGeU) -video
> 
> 

## <a name="two-methods-to-drill-down"></a>Kaksi porautumismenetelmää
Voit porautua visualisoinnissa alaspäin (ja ylöspäin) kahdella tavalla.  Molemmat kuvataan tässä artikkelissa. Kummallakin tavalla voi tehdä saman asian, joten voit valita sen, mistä eniten pidät itse.

> [!NOTE]
> [Avaa Jälleenmyyntianalyysimalli](sample-datasets.md) Power BI -palvelussa ja luo puukartta, jossa näkyvät **yksiköt yhteensä tänä vuonna** (Arvot) alueen (**Territory)**, kaupungin **(City)**, postinumeron **(PostalCode)** ja nimen **(Name)** (Ryhmä) mukaan.  
> 
> 

## <a name="method-one-for-drill-down"></a>Porautumismenetelmä yksi
Tässä menetelmässä käytetään porautumiskuvakkeita, jotka näkyvät itse visualisoinnin yläkulmissa.

1. Avaa raportti Power BI:n [luku- tai muokkausnäkymässä](service-reading-view-and-editing-view.md). Porautuminen edellyttää visualisointia, jolla on hierarkia. 
   
   Hierarkia esitellään alla olevassa animaatiossa.  Visualisoinnissa on alueesta, kaupungista, postinumerosta ja postitoimipaikasta koostuva hierarkia. Jokainen alue sisältää yhden tai useamman kaupungin, jokainen kaupunki yhden tai useamman postinumeron ja niin edelleen. Visualisointi näyttää oletusarvoisesti vain alueen tiedot, koska *Territory* (Alue) näkyy luettelossa ensimmäisenä.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Ota porautuminen käyttöön valitsemalla visualisoinnin oikeassa yläkulmassa näkyvä nuolikuvake. Kun kuvake on tumma, porautuminen on käytössä. Jos et ota porautumista käyttöön, visuaalisen elementin (kuten palkin tai kuplan) valitseminen ristisuodattaa muut raportin sivulla olevat kaaviot.    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. Voit porautua alaspäin **yksi kenttä kerrallaan** valitsemalla yhden elementin visualisoinnistasi. Palkkikaaviossa tämä tarkoittaa, että napsautat yhtä palkeista. Puukartassa tämä tarkoittaa, että napsautat yhtä **lehdistä**. Huomaa, että otsikko muuttuu porautuessasi alaspäin ja uudelleen takaisin ylös. Tässä animaatiossa se muuttuu otsikosta "Total Units This Year by Territory" (Yksiköt yhteensä tänä vuonna alueen mukaan) otsikoksi "Total Units This Year by Territory and City" (Yksiköt yhteensä tänä vuonna alueen ja kaupungin mukaan) ja sen jälkeen otsikoksi "Total Units This Year by Territory, City and Postal Code" (Yksiköt yhteensä tänä vuonna alueen, kaupungin ja postinumeron mukaan) ja otsikoksi "Total Units This Year by Territory, City, Postal Code, and Name (Yksiköt yhteensä tänä vuonna alueen, kaupungin, postinumeron ja nimen mukaan). Poraudu takaisin ylös valitsemalla **Poraudu ylöspäin** -kuvake ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png), joka näkyy visualisoinnin vasemmassa yläkulmassa (ks. kuva alla).
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. Jos haluat porautua alaspäin ***kaikki kentät kerrallaan***, valitse visualisoinnin vasemmassa yläkulmassa näkyvä kaksoisnuoli.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. Kun haluat porautua takaisin ylös, valitse visualisoinnin vasemmassa yläkulmassa näkyvä ylöspäin osoittava nuoli.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-two-for-drill-down"></a>Porautumismenetelmä kaksi
Tässä menetelmässä käytetään Power BI:n ylävalikkopalkin avattavaa **Tutki**-valikkoa.

1. Avaa raportti Power BI:n [luku- tai muokkausnäkymässä](service-reading-view-and-editing-view.md). Porautuminen edellyttää visualisointia, jolla on hierarkia. 
   
   Hierarkia näkyy alla olevassa kuvassa.  Visualisoinnissa on alueesta, kaupungista, postinumerosta ja postitoimipaikasta koostuva hierarkia. Jokainen alue sisältää yhden tai useamman kaupungin, jokainen kaupunki yhden tai useamman postinumeron ja niin edelleen. Visualisointi näyttää oletusarvoisesti vain alueen tiedot, koska *Territory* (Alue) näkyy luettelossa ensimmäisenä.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Ota porautuminen käyttöön aktivoimalla visualisointi valitsemalla se. Valitse sen jälkeen Power BI:n ylävalikkopalkista **Tutki** > **Poraudu alaspäin**. Visualisoinnin oikeassa yläkulmassa näkyvän porautumiskuvakkeen tausta muuttuu mustaksi. ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. Kun porautuminen on otettu käyttöön, voit porautua alaspäin yksi kenttä kerrallaan valitsemalla jonkin puukartan lehdistä. Tässä esimerkissä valittuna on alue nimeltä **NC**, jolloin voidaan tarkastella Pohjois-Carolinassa tänä vuonna myytyjen yksiköiden kokonaismäärää kaupungeittain.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. Voit porautua alaspäin kaikki kentät kerrallaan valitsemalla **Tutki** > **Näytä seuraava taso**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. Kun haluat porautua takaisin ylös, valitse **Tutki** > **Poraudu ylöspäin**.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)

6. Kun haluat nähdä visualisoinnin luomiseen käytettävät tiedot, valitse **Näytä tiedot**. Tiedot näkyvät visualisoinnin alapuolella olevassa ruudussa. Tämä ruutu pysyy näkyvissä, kun jatkat porautumista visualisoinnin läpi. Lisätietoja saat [Show data used to create the visual](service-reports-show-data.md) -ohjeista.

## <a name="understanding-the-hierarchy-axis-and-hierarchy-group"></a>Tietoja hierarkia-akselista ja hierarkiaryhmästä
Voit ajatella hierarkia-akselia ja hierarkiaryhmää mekanismina, jonka avulla voit suurentaa ja pienentää niiden tietojen askelväliä, joita haluat tarkastella. Kaikki tiedot, jotka voidaan järjestää luokkiin ja aliluokkiin, ovat kelvollisia sisältämään hierarkian. Tämä sisältää tietysti päivämäärät ja kellonajat.

Voit luoda hierarkian sisältävän visualisoinnin Power BI:ssä valitsemalla yhden tai useamman tietokentän lisättäväksi joko **Akseli**-ruutuun tai **Ryhmä**-ruutuun ja lisäämällä tiedot, joita haluat tarkastella tietokenttinä **Arvot**-ruudussa. Tiedät tietojen olevan hierarkkisia, jos porautumistilan kuvakkeet näkyvät visualisoinnin vasemmassa ja oikeassa yläkulmassa. 

Käytännössä kannattaa ajatella kahdenlaisia hierarkkisia tietoja:
- Päivämäärä- ja kellonaikatiedot – jos sinulla on tietotyypin päivämäärä/aika sisältävä tietokenttä, tällöin sinulla on jo hierarkkisia tietoja. Power BI luo automaattisesti hierarkian kaikille tietokentille, joiden arvot voidaan jäsentää [päivämäärä/aika](https://msdn.microsoft.com/library/system.datetime.aspx)-rakenteeksi. Sinun tarvitsee vain lisätä yksi päivämäärä-/aikakenttä **Akseli**- tai **Ryhmä**-ruutuun.
- Luokkatiedot – jos tiedot on saatu alikokoelmia sisältävistä kokoelmista tai niissä on muutoin tietorivejä, joilla on yhteisiä arvoja, tällöin tietosi ovat hierarkkisia.

Power BI:n avulla voit tarkastella alijoukkoja yksitellen tai kaikkia kerrallaan. Voit porautua tietojen läpi nähdäksesi yksittäisen alijoukon kullakin tasolla tai nähdäksesi kaikki alijoukot samanaikaisesti kullakin tasolla. Voit esimerkiksi porautua alaspäin tiettyyn vuoteen tai tarkastella kunkin vuoden kaikkia tuloksia etenemällä hierarkiassa alaspäin. Vastaavasti voit porautua ylöspäin samalla tavalla.

Seuraavissa osioissa kuvataan, kuinka poraudutaan alaspäin ylimmästä näkymästä, keskimmäisestä näkymästä ja alimmasta näkymästä.

### <a name="hierarchical-data-and-time-data"></a>Hierarkkiset tiedot ja aikatiedot
Avaa [Jälleenmyyntianalyysimalli](sample-datasets.md) ja luo pinottu pylväskaaviovisualisointi, jossa tarkastellaan **kuukautta** (Akseli) **kokonaismyynnin** (Arvot) mukaan.  

Vaikka akselin tietokenttä onkin **kuukausi**, se luo myös **Vuosi**-luokan **Akseli**-ruutuun. Tämä johtuu siitä, että Power BI tarjoaa täyden päivämäärä/aikarakenteen kaikille arvoille, jotka se lukee. Hierarkian yläosassa näkyvät vuotta koskevat tiedot.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-1.png)

Kun Porautuminen alaspäin -tila on käytössä, siirry hierarkiassa yksi taso alaspäin napsauttamalla kaavion palkkia. Näet kolme palkkia käytettävissä olevista vuosineljännestiedoista. Valitse vasemman yläkulman kuvakkeista **Expand all down one level of the hierarchy** (Laajenna kaikki alaspäin yhden hierarkiatason verran). Tee tämän jälkeen sama uudelleen siirtyäksesi hierarkian alimmalle tasolle, joka näyttää jokaisen kuukauden tulokset.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-2.png)

Visualisoinnin lisäksi näemme kussakin raportissa hahmonnettujen tietojen hierarkian. Seuraavassa taulukossa näkyvät **Näytä tiedot** -toiminnon tulokset raportissa, joka porautuu alaspäin yksittäisestä kuukaudesta tai kaikista kuukausista. 

Huomaa, että tiedot ovat samat vuosineljänneksen ja koko vuoden raporteissa, mutta porautuessasi alaspäin **Arvot**-kohtaan määritetyn tiedon tasolle, näet, miten yksittäinen raportti muuttuu yksityiskohtaisemmaksi ja ”kaikki kuukaudet” -raportissa on enemmän tietoja.


|Laajennettu tila|Vuosi|Vuosineljännes|Kuukausi|Päivä|
| ---|:---:|:---:|:---:|---|
|Yksittäinen|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-day.png)|
|Kaikki|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-day.png)|


### <a name="hierarchical-category-data"></a>Hierarkkiset luokkatiedot
Kokoelmista ja alikokoelmista mallinnetut tiedot ovat hierarkkisia. Hyvä esimerkki tästä ovat sijaintitiedot. Otetaan esimerkiksi tietolähteessä oleva taulukko, jonka sarakkeet ovat maa, osavaltio, kaupunki ja postinumero. Tiedot, joiden maa, osavaltio ja kaupunki ovat samat, ovat hierarkkisia.

Avaa tätä esimerkkiä varten [Jälleenmyyntianalyysimalli](sample-datasets.md). Luo pinottu pylväskaaviovisualisointi, jossa tarkastellaan **yksiköiden kokonaismäärää tänä vuonna** (Arvot) **alueen**, **kaupungin**, **postinumeron** ja **nimen** (Ryhmä) mukaan.  

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-1.png)

Porautuminen alaspäin -tilan ollessa käytössä valitse vasemman yläkulman kuvakkeista **Expand all down one level of the hierarchy** (Laajenna kaikki alaspäin yhden hierarkiatason verran) -kuvake kolme kertaa.
Sinun pitäisi olla hierarkian alimmalla tasolla, joka näyttää alueen, kaupungin ja postinumeron tulokset.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-2.png)

Visualisoinnin lisäksi näemme kussakin raportissa hahmonnettujen tietojen hierarkian. Seuraavassa taulukossa näkyvät **Näytä tiedot** -toiminnon tulokset raportissa, joka porautuu alaspäin yhden alueen tiedoissa tai kaikkien alueiden tiedoissa. Porautuessasi alaspäin näet, miten yksittäinen raportti muuttuu yksityiskohtaisemmaksi ja ”kaikki alueet” -raportissa on enemmän tietoja.


| Laajennettu tila|Alue|Kaupunki|Postinumero|Nimi|
| ---|:---:|:---:|:---:|---|
|Yksittäinen|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal-name.png)|
|Kaikki|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal-name.png)|


## <a name="considerations-and-limitations"></a>Huomioon otettavat seikat ja rajoitukset
* Jos päivämääräkentän lisääminen visualisointiin ei luo hierarkiaa, syynä voi olla, että ”päivämäärä”-kenttää ei ole todellisuudessa tallennettu päivämääräksi. Jos omistat tietojoukon, avaa se Power BI Desktopin *tietonäkymässä*, valitse päivämäärän sisältävä sarake ja muuta Mallinnus-välilehdellä **tietotyypiksi** **päivämäärä** tai  **päivämäärä/aika**. Jos raportti on jaettu kanssasi, voit pyytää muutosta omistajalta.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Visualisoinnit Power BI -raporteissa](power-bi-report-visualizations.md)

[Power BI -raportit](service-reports.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

