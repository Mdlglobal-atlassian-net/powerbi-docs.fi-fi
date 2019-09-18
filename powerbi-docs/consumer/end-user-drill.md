---
title: Porautuminen alas- ja ylöspäin visualisoinnissa
description: Tässä artikkelissa kerrotaan, miten voit porautua alaspäin visualisointiin Microsoft Power BI -palvelussa ja Power BI Desktopissa.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: MNAaHw4PxzE
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 6/17/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 29823a2f1ca7f1448df54282e0ce081310974eb3
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/16/2019
ms.locfileid: "67265657"
---
# <a name="drill-mode-in-a-visualization-in-power-bi"></a>Visualisointiin porautumistila Power BI:ssä

Tässä artikkelissa kerrotaan, miten voit porautua alaspäin visualisointiin Microsoft Power BI -palvelussa ja Power BI Desktopissa. Power BI -raporteissa voi olla useita tietohierarkioita, jotka antavat mahdollisimman monia merkityksellisiä tietoja datasta. Kun poraat arvopisteitä ylös- tai alaspäin, voit tutkia tarkemmin tietojesi yksityiskohtia. Voit hyödyntää niitä jopa kaikkein pienimmissä mobiililaitteissa.

## <a name="drill-requires-a-hierarchy"></a>Porautuminen edellyttää hierarkiaa

Kun visualisoinnissa on hierarkia, saat porautumalla alaspäin näkyviin lisää tietoja. Sinulla voi olla esimerkiksi visualisointi, joka kuvaa olympiamitalien määrää hierarkian mukaan, joka muodostuu urheilusta, lajista ja tapahtumasta. Visualisointi näyttää oletusarvoisesti mitalimäärän urheilulajin mukaan – esimerkiksi voimistelu, hiihto ja vesiurheilu. Mutta koska sillä on hierarkia, visualisoinnin yhden elementin (kuten palkin, rivin tai kuplan) valitseminen näyttää selvästi yksityiskohtaisemman kuvan. Valitsemalla **vesiurheilu**-elementin saat näkyviin uintia, uimahyppyä ja vesipalloa koskevat tiedot.  Valitsemalla **uimahyppy**-elementin saat näkyviin ponnahduslauta-, koroke- ja taitohyppytapahtumat.

Voit lisätä hierarkioita omistamiisi raportteihin, mutta et niihin, jotka on jaettu kanssasi.
Etkö ole varma, mitkä Power BI -visualisoinnit sisältävät hierarkian? Liikuta hiiren osoitinta visualisoinnin päällä. Jos nämä porauksen ohjausobjektit tulevat näkyviin yläkulmissa, visualisoinnissa on hierarkia.

![Näyttökuva Poraudu alaspäin yksi taso -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon4.png)  ![Näyttökuva Ota alaspäin porautuminen käyttöön ja poista se käytöstä -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon2.png)  ![Näyttökuva Poraa kaikki kentät alaspäin kerralla -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon3.png)
![poraa ylöspäin -kuvake](./media/end-user-drill/power-bi-drill-icon5.png) ![Näyttökuva Laajenna alaspäin -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon6.png)  

Päivämäärät ovat hierarkian yksilöivä tyyppi. Kun lisäät visualisointiin päivämääräkentän, Power BI lisää automaattisesti aikahierarkian, joka sisältää vuoden, vuosineljänneksen, kuukauden ja päivän. Lisätietoja saat artikkelista [Visualisoinnin hierarkiat ja porautuminen alaspäin](../guided-learning/visualizations.yml?tutorial-step=18) tai katsomalla alla olevan videon.

<iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Jos haluat lisätietoja siitä, miten voit luoda hierarkioita Power BI Desktopin avulla, katso video [Miten hierarkioita luodaan ja lisätään](https://youtu.be/q8WDUAiTGeU).

## <a name="prerequisites"></a>Edellytykset

1. Power BI -palvelussa tai Desktopissa porautuminen edellyttää visualisointia, jolla on hierarkia.

1. Avaa seuraamista varten [Jälleenmyyntianalyysin malli](../sample-datasets.md). Luo **Puukartan** visualisointi, joka näyttää seuraavat:

    | Säilö | Kenttä |
    | ---- | ----- |
    | Arvo |Myynti<br>\|\_ Yksiköt yhteensä tänä vuonna |
    | Ryhmä | Myymälä<br>\|\_ Alue<br>\|\_ Kaupunki<br>\|\_ Postinumero<br>\|\_ Nimi

    Puukartassa on alueesta, kaupungista, postinumerosta ja postitoimipaikasta koostuva hierarkia. Jokainen alue sisältää yhden tai useamman kaupungin, jokainen kaupunki yhden tai useamman postinumeron ja niin edelleen. Visualisointi näyttää oletusarvoisesti vain alueen tiedot, koska *Alue* näkyy luettelossa ensimmäisenä.

    ![Näyttökuva Visualisoinnit-ruudusta, jossa Alue-kenttä on korostettu.](media/end-user-drill/power-bi-hierarcy-list.png)

1. Voi olla hankala ymmärtää sitä, miten erilaiset porautumiskuvakkeet toimivat yhdessä. Suodatetaanpa puukartta, jossa näytetään vain kaksi pienempää aluetta: **KY** ja **TN**. Valitse puukartta ja laajenna sitten **Alue** kohdassa **Visuaalisen tason suodattimet** ja valitse **KY** ja **TN**.

    ![Näyttökuva Visualisoinnit-ruudusta, jossa on suodatin KY:lle ja TN:lle.](./media/end-user-drill/power-bi-filter.png)

    Nyt puukartassa näkyy vain kaksi aluetta.

    ![Näyttökuva visualisoinneista, jossa KY ja TN on korostettu.](./media/end-user-drill/power-bi-territories.png)

## <a name="three-ways-to-use-the-drill-features"></a>Kolme tapaa käyttää porautumisominaisuuksia

Poraudu alaspäin-, Poraudu ylöspäin- ja Laajenna-toimintoja voi käyttää useilla eri tavoilla visualisoinneissa, jotka sisältävät hierarkioita. Tässä artikkelissa esitellään seuraavaksi ensimmäinen tapa. Kun olet oppinut alaspäin porautumisen ja laajennuksen perusteet, osaat käyttää niitä kaikkea kolmea. Ne kaikki tekevät samoja asioita. Kokeile niitä ja valitse se, josta pidät eniten.

- Kun osoitat visualisointia, näet kuvakkeet ja voit käyttää niitä.  

    ![Näyttökuva esimerkistä, jossa hiirtä liikutetaan vaihtoehdon päällä.](./media/end-user-drill/power-bi-hover.png)

- Valikko tulee näkyviin hiiren kakkospainiketta napsauttamalla.

    ![Näyttökuva esimerkistä, jossa napsautetaan hiiren kakkospainiketta.](./media/end-user-drill/power-bi-drill-menu.png)

- Valitse Power BI-valikkoriviltä **Tutki**.

   ![Näyttökuva, jossa valitaan Resurssienhallinta, joka näyttää porautumiskuvakkeet ja vaihtoehdot.](media/end-user-drill/power-bi-explore.png)

## <a name="drill-pathways"></a>Porautumisen polut

### <a name="drill-down"></a>Poraudu alaspäin

Käytettävissäsi on useita tapoja porautua visualisointiin. **Poraudu alaspäin** vie sinut seuraavalle tasolle hierarkiassa. Jos tarkastelet **Alue**-tasoa, voit porautua alaspäin kaupungin tasolle, sitten postinumeron tasolle ja lopuksi nimen tasolle. Polun jokainen vaihe tuo näkyviin uusia tietoja.

![Kaavio, jossa näytetään porautumisen polku](./media/end-user-drill/power-bi-drill-path.png)

### <a name="expand"></a>Laajenna

**Laajenna** lisää muita hierarkiatasoja nykyiseen näkymään. Jos siis tarkastelet **Alue**-tasoa, voit laajentaa ja lisätä kaupungin, postinumeron ja nimen tiedot puukarttaan. Jokainen polun vaihe tuo näkyviin edelliset tiedot ja lisää uuden tietojen tason.

![Kaavio, joka näyttää Laajenna-polun](./media/end-user-drill/power-bi-expand-path.png)

Voit myös valita, haluatko porautua alaspäin vai laajentaa yksi kenttä kerrallaan tai kaikki kentät kerrallaan.

## <a name="drill-down-all-fields-at-once"></a>Porautuminen alaspäin kaikki kentät kerrallaan

1. Aloita puukartan ylätasolta, jossa näkyvät KY:n ja TN:n tiedot. Laajenna puukarttaa valitsemalla jokin kahvoista ja vetämällä sitä oikealle.

    ![Näyttökuva puukartan visualisoinnista, jossa näytetään KY ja TN](./media/end-user-drill/power-bi-drill-down.png)

1. Jos haluat porautua alaspäin *kaikki kentät kerrallaan*, valitse visualisoinnin vasemmassa yläkulmassa oleva kaksoisnuoli ![kaksinkertainen alaspäin porautumiskuvake](./media/end-user-drill/power-bi-drill-icon3.png). Puukartassa näkyvät nyt Kentuckyn ja Tennesseen kaupunkitiedot.

    ![Näyttökuva puukartan visualisoinnista, joka näyttää porautumisen alaspäin kaupunkeihin.](./media/end-user-drill/power-bi-drill-down1.png)

1. Porautumalla alaspäin vielä kerran siirryt postinumeron tasolle hierarkiassa.

    ![Näyttökuva puukartan visualisoinnista, joka näyttää porautumisen alaspäin postinumeroon.](./media/end-user-drill/power-bi-drill-down2.png)

1. Jos haluat porautua takaisin ylöspäin, valitse ylänuoli visualisoinnin vasemmassa yläkulmassa ![Näyttökuva Porautuminen ylöspäin yksi taso -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon5.png).

## <a name="drill-down-one-field-at-a-time"></a>Porautuminen alaspäin yksi kenttä kerrallaan

Tässä menetelmässä käytetään Poraudu alaspäin -kuvaketta, joka näkyy itse visualisoinnin oikeassa yläkulmassa.

1. Valitse Poraudu alaspäin -kuvake, jos haluat ottaa sen käyttöön ![Näyttökuva Porautuminen alaspäin käytössä / pois käytöstä -kuvakkeesta, joka on otettu käyttöön.](./media/end-user-drill/power-bi-drill-icon2.png).

    Nyt voit halutessasi porautua **yksi kenttä kerrallaan**.

    ![Näyttökuva visualisoinnista, jossa nuoli osoittaa Porautuminen alaspäin käytössä / pois käytöstä -kuvakkeeseen, joka on otettu käyttöön](media/end-user-drill/power-bi-drill-icon-new.png)

    Jos et ota porautumista alaspäin käyttöön, visualisointielementin (kuten palkin, kuplan tai lehden) valitseminen ei poraa alaspäin. Sen sijaan se ristisuodattaa muut raporttisivulla olevat kaaviot.

1. Valitse lehti **TN:lle**. Puukartassa näytetään nyt kaikki Tennesseen kaupungit, joissa on myymälä.

    ![Näyttökuva puukartasta, joka näyttää vain TN:n tiedot.](media/end-user-drill/power-bi-drill-down-one1.png)

1. Tässä vaiheessa voit:

    1. Jatkaa porautumista alaspäin Tennesseelle.

    1. Porautua alaspäin tiettyyn kaupunkiin Tennesseessä.

    1. Laajentaa sen sijaan (katso **Laajenna kaikki kentät kerrallaan** alla).

    Poraudutaan jälleen alaspäin yksi kenttä kerrallaan.  Valitse **Knoxville, TN**. Puukartassa näkyy nyt Knoxvillen myymälän postinumero.

    ![Näyttökuva puukartasta, joka näyttää postinumeron 37919.](media/end-user-drill/power-bi-drill-down-one2.png)

    Huomaa, että otsikko muuttuu porautuessasi alaspäin ja uudelleen takaisin ylös.

## <a name="expand-all-and-expand-one-field-at-a-time"></a>Kaikkien kenttien laajentaminen ja laajentaminen yksi kenttä kerrallaan

Puukartta, jossa näkyy vain postinumero, ei ole kovin havainnollinen.  Laajennetaan siis hierarkiaa yksi taso alaspäin.  

1. Kun puukartta on aktiivinen, valitse *Laajenna alaspäin* -kuvake ![Näyttökuva Laajenna alaspäin -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon6.png) Puukartassa näkyy nyt kaksi hierarkian tasoa: postinumero ja myymälän nimi.

    ![Näyttökuva puukartasta, joka näyttää postinumeron ja myymälän nimen](./media/end-user-drill/power-bi-expand1.png)

1. Jos haluat nähdä kaikki neljä Tennesseen tietojen hierarkiatasoa, valitse Poraudu ylöspäin -nuoli, kunnes saavutat puukartan toisen tason, **Yksiköt yhteensä tänä vuonna alueen ja kaupungin mukaan**.

    ![Näyttökuva puukartasta, joka näyttää kaikki TN:n tiedot.](media/end-user-drill/power-bi-drill-down-one1.png)

1. Varmista, että porautuminen alaspäin on edelleen käytössä, ![Näyttökuva Poraudu alaspäin käytössä / pois käytöstä -kuvakkeesta, joka on otettu käyttöön.](./media/end-user-drill/power-bi-drill-icon2.png) ja valitse *Laajenna alaspäin* -kuvake ![Näyttökuva Laajenna alaspäin -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon6.png) Puukartassa näkyy nyt joitakin lisätietoja. Pelkän kaupungin ja osavaltion sijasta siinä näkyy nyt myös postinumero.

    ![Näyttökuva visualisoinnista, joka näyttää kaupungin, osavaltion ja postinumeron.](./media/end-user-drill/power-bi-expand-one3.png)

1. Valitse *Laajenna alaspäin* -kuvake vielä kertaalleen, jotta näet puukartassa Tennesseen tietojen kaikki neljä hierarkiatasoa. Osoittamalla lehteä näet vielä lisää tietoja.

    ![Näyttökuva puukartasta, joka näyttää työkaluvihjeen, jossa on lehtikohtaisia tietoja.](./media/end-user-drill/power-bi-expand-all.png)

## <a name="drilling-filters-other-visuals"></a>Poraaminen suodattaa muut visualisoinnit

Kun työskentelet Poraudu-tilassa, päätät itse, millä tavoin alaspäin porautuminen ja laajentaminen vaikuttaa sivun muihin visualisointeihin.

Oletusarvoisesti poraaminen ei suodata raportin muita visualisointeja. Voit kuitenkin ottaa tämän ominaisuuden käyttöön Power BI Desktopissa ja Power BI -palvelussa.

1. Valitse Desktopissa **Muoto**-välilehti ja merkitse sitten valintaruutu kohdassa **Poraaminen suodattaa muut visualisoinnit**.

    ![Näyttökuva, jossa näytetään Poraaminen suodattaa muut visualisoinnit -asetus Power BI Desktopissa](./media/end-user-drill/power-bi-drill-filters-desktop.png)

1. Kun nyt poraudut alaspäin, poraudut ylöspäin tai laajennat visualisointia hierarkiassa, tämä toiminto suodattaa sivulla olevat muut visualisoinnit.

    ![Näyttökuva tuloksesta Desktopissa.](./media/end-user-drill/power-bi-drill-filters.png)

    ![Näyttökuva toisesta tuloksesta Desktopissa.](./media/end-user-drill/power-bi-drill-filters2.png)

> [!NOTE]
> Voit ottaa tämän toiminnon käyttöön Power BI -palvelussa yläreunan valikkoriviltä valitsemalla **Visualisointitoimet** > **Poraaminen suodattaa muut visualisoinnit**.
>
> ![Näyttökuva, jossa näytetään Poraaminen suodattaa muut visualisoinnit -asetus Power BI -palvelussa](./media/end-user-drill/power-bi-drill-filters-service.png)

## <a name="learn-about-the-hierarchy-axis-and-hierarchy-group"></a>Tietoja hierarkia-akselista ja hierarkiaryhmästä

Voit ajatella hierarkia-akselia ja hierarkiaryhmää mekanismina, jonka avulla voit suurentaa ja pienentää niiden tietojen askelväliä, joita haluat tarkastella. Kaikki tiedot, jotka voidaan järjestää luokkiin ja aliluokkiin, ovat kelvollisia sisältämään hierarkian, mukaan lukien päivämäärät ja ajat.

Voit luoda hierarkian sisältävän visualisoinnin Power BI:ssä valitsemalla yhden tai useamman tietokentän lisättäväksi joko **Akseli**-säilöön tai **Ryhmä**-säilöön. Lisää sitten **Arvot**-säilöön tietoja, joita haluat tarkastella tietokenttinä . Tiedät tietojen olevan hierarkkisia, jos *porautumistilan* kuvakkeet näkyvät visualisoinnin vasemmassa ja oikeassa yläkulmassa.

Käytännössä kannattaa ajatella kahdenlaisia hierarkkisia tietoja:

- Päivämäärä- ja kellonaikatiedot – jos sinulla on tietotyypin päivämäärä/aika sisältävä tietokenttä, tällöin sinulla on jo hierarkkisia tietoja. Power BI luo automaattisesti hierarkian kaikille tietokentille. Voit jäsentää arvot yhdeksi [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx)-rakenteeksi. Sinun tarvitsee vain lisätä yksi päivämäärä-/aikakenttä **Akseli**- tai **Ryhmä**-ruutuun.

- Luokkatiedot – jos Power BI poimii tiedot alikokoelmia sisältävistä kokoelmista tai niissä on muutoin tietorivejä, joilla on yhteisiä arvoja, tietosi ovat hierarkkisia.

Power BI:n avulla voit laajentaa alijoukkoja yksitellen tai kaikki kerrallaan. Voit porautua alaspäin tietojen läpi nähdäksesi yksittäisen alijoukon kullakin tasolla tai nähdäksesi kaikki alijoukot samanaikaisesti kullakin tasolla. Voit esimerkiksi porautua alaspäin tiettyyn vuoteen tai tarkastella kunkin vuoden kaikkia tuloksia etenemällä hierarkiassa alaspäin.

Vastaavasti voit porautua ylöspäin samalla tavalla.

Seuraavissa osioissa kuvataan, kuinka poraudutaan alaspäin ylimmästä näkymästä, keskimmäisestä näkymästä ja alimmasta näkymästä.

### <a name="hierarchical-data-and-time-data"></a>Hierarkkiset tiedot ja aikatiedot

Tässä esimerkissä:

1. Seuraa [Jälleenmyyntianalyysin mallia](../sample-datasets.md) ja luo pinottu pylväskaaviovisualisointi, jossa tarkastellaan seuraavia:

    | Säilö | Kenttä |
    | ---- | ----- |
    | Akseli | Aika<br>\|\_ Kuukausi |
    | Arvot | Myynti<br>\|\_ TotalSales |

    Vaikka akselin tietokenttä onkin **kuukausi**, se luo myös **Vuosi**-luokan **Akseli**-ruutuun. Tämä johtuu siitä, että Power BI tarjoaa täyden DateTime-rakenteen kaikille arvoille, jotka se lukee. Hierarkiassa ylhäällä näytetään vuotta koskevat tiedot.

    ![Näyttökuva yksittäisestä palkista, joka näyttää tiedot ryhmiteltynä vuoden mukaan](media/end-user-drill/power-bi-hierarchical-axis-datetime-1.png)

1. Kun Porautuminen alaspäin -tila on käytössä, siirry hierarkiassa yksi taso alaspäin valitsemalla kaavion palkin. Näet kolme palkkia saatavilla oleville vuosineljännestiedoille.

1. Valitse sitten vasemman yläkulman kuvakkeista **Laajenna kaikki alaspäin yhden hierarkiatason verran**.

1. Tee se jälleen kerran siirtyäksesi hierarkian alimmalle tasolle, joka näyttää jokaisen kuukauden tulokset.

    ![Näyttökuva palkkikaaviosta, jossa on palkki kuukautta kohti](media/end-user-drill/power-bi-hierarchical-axis-datetime-2.png)

Visualisoinnin lisäksi näemme kussakin raportissa hahmonnettujen tietojen hierarkian. Valitse oikeassa yläkulmassa olevat kolme pistettä (...) ja valitse sitten **Näytä tiedot**. Seuraavassa taulukossa näytetään alaspäin porautumisen tulokset raportissa yhdestä kuukaudesta tai kaikista kuukausista:

|Laajennettu tila|Vuosi|Vuosineljännes|Kuukausi|Päivä|
| --- |:---:|:---:|:---:|---|
|Yksittäinen|![yksittäinen vuosi](./media/end-user-drill/power-bi-hierarchical-year.png)|![yksittäinen vuosineljännes](media/end-user-drill/power-bi-hierarchical-quarter.png)|![yksittäinen kuukausi](./media/end-user-drill/power-bi-hierarchical-one-month.png)|![yksittäinen päivä](media/end-user-drill/power-bi-hierarchical-one-day.png)|
|Kaikki|![kaikki vuodet](./media/end-user-drill/power-bi-hierarchical-year.png)|![kaikki vuosineljännekset](media/end-user-drill/power-bi-hierarchical-quarter.png)|![kaikki kuukaudet](./media/end-user-drill/power-bi-hierarchical-all-month.png)|![kaikki päivät](media/end-user-drill/power-bi-hierarchical-all-day.png)|

Huomaa, että tiedot ovat samat **vuosineljänneksen** ja **vuoden** raporteille. Kun olet porautunut alaspäin **Arvot**-kohtaan määritetyn tiedon tasolle, näet, miten yksittäinen raportti muuttuu yksityiskohtaisemmaksi ja ”kaikki kuukaudet” -raportissa on enemmän tietoja.

### <a name="hierarchical-category-data"></a>Hierarkkiset luokkatiedot

Kokoelmista ja alikokoelmista mallinnetut tiedot ovat hierarkkisia.

Hyvä esimerkki tästä ovat sijaintitiedot. Otetaan esimerkiksi tietolähteessä oleva taulukko, jonka sarakkeet ovat maa, osavaltio, kaupunki ja postinumero. Tiedot, joiden maa, osavaltio ja kaupunki ovat samat, ovat hierarkkisia.

Tässä esimerkissä:

1. Seuraa [Jälleenmyyntianalyysin mallia](../sample-datasets.md). Luo pinottu pylväskaaviovisualisointi, jossa tarkastellaan seuraavia:

    | Säilö | Kenttä |
    | ---- | ----- |
    | Arvo |Myynti<br>\|\_ Yksiköt yhteensä tänä vuonna |
    | Akseli | Myymälä<br>\|\_ Alue<br>\|\_ Kaupunki – Kaupunki on ehkä vedettävä **Selite**-säilöstä **Akseli**-säilöön.<br>\|\_ Postinumero<br>\|\_ Nimi |

    ![Näyttökuva palkkikaaviosta, joka näyttää tämän vuoden yksiköiden kokonaismäärän alueen mukaan.](media/end-user-drill/power-bi-hierarchical-axis-category-1.png)

1. Kun Porautuminen alaspäin -tila on käytössä, valitse vasemman yläkulman kuvakkeista **Laajenna kaikki alaspäin yhden hierarkiatason verran** kolme kertaa.

    Sinun pitäisi olla hierarkian alimmalla tasolla, joka näyttää alueen, kaupungin ja postinumeron tulokset.

    ![Näyttökuva palkkikaaviosta, joka näyttää alimman hierarkiatason ja eniten yksityiskohtia.](media/end-user-drill/power-bi-hierarchical-axis-category-2.png)

Visualisoinnin lisäksi näemme kussakin raportissa hahmonnettujen tietojen hierarkian. Valitse oikeassa yläkulmassa olevat kolme pistettä (...) ja valitse sitten **Näytä tiedot**. Seuraavassa taulukossa näytetään alaspäin porautumisen tiedot yhdelle alueelle tai kaikille alueille.

| Laajennettu tila|Alue|Kaupunki|Postinumero|Nimi|
| ---|:---:|:---:|:---:|---|
|Yksittäinen|![yksittäinen alue](./media/end-user-drill/power-bi-hierarchical-territory.png)|![yksittäinen kaupunki](media/end-user-drill/power-bi-hierarchical-one-territory-city.png)|![yksittäinen postinumero](./media/end-user-drill/power-bi-hierarchical-one-territory-city-postal.png)|![yksittäinen nimi](media/end-user-drill/power-bi-hierarchical-one-territory-city-postal-name.png)|
|Kaikki|![kaikki alueet](./media/end-user-drill/power-bi-hierarchical-territory.png)|![kaikki kaupungit](media/end-user-drill/power-bi-hierarchical-all-territory-city.png)|![kaikki postinumerot](./media/end-user-drill/power-bi-hierarchical-all-territory-city-postal.png)|![kaikki nimet](media/end-user-drill/power-bi-hierarchical-all-territory-city-postal-name.png)|

 Kun poraudut alaspäin, näet, miten **yksittäinen** raportti muuttuu yksityiskohtaisemmaksi ja **Kaikki** alueet -raportissa on enemmän tietoja.

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

Jos päivämääräkentän lisääminen visualisointiin ei luo hierarkiaa, syynä voi olla se, että Päivämäärä-kenttää ei ole todellisuudessa tallennettu päivämääräksi. Jos omistat tietojoukon:

1. Avaa se *Tieto*-näkymässä Power BI Desktopissa

1. Valitse sarake, jossa on päivämäärä.

1. Vaihda **Mallinnus**-välilehdessä **Tietotyyppi**-kohdan vaihtoehdoksi **Päivämäärä** tai **Päivämäärä/aika**.

![Näyttökuva valitusta Tieto-näkymästä. Voit oikeassa yläkulmassa nähdä Päivämäärä-tyypin.](media/end-user-drill/power-bi-change-data-type2.png)

Jos raportti on jaettu kanssasi, voit pyytää muutosta omistajalta.

## <a name="next-steps"></a>Seuraavat vaiheet

[Visualisoinnit Power BI -raporteissa](../visuals/power-bi-report-visualizations.md)

[Power BI -raportit](end-user-reports.md)

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
