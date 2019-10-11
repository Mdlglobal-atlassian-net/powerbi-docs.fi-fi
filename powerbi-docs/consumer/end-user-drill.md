---
title: Porautuminen alas- ja ylöspäin visualisoinnissa
description: Tässä artikkelissa kerrotaan, miten voit porautua visualisointiin Microsoft Power BI -palvelussa.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/1/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: bc6a6557d01ba8145659bb244be8eb5786220665
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2019
ms.locfileid: "71944110"
---
# <a name="drill-mode-in-a-visual-in-power-bi"></a>Visualisointiin porautumistila Power BI:ssä

Tässä artikkelissa kerrotaan, miten voit porautua visualisointiin Microsoft Power BI -palvelussa. Kun poraat arvopisteitä ylös- tai alaspäin, voit tutkia tarkemmin tietojesi yksityiskohtia. 

## <a name="drill-requires-a-hierarchy"></a>Porautuminen edellyttää hierarkiaa

Kun visualisoinnissa on hierarkia, saat porautumalla näkyviin lisää tietoja. Sinulla voi olla esimerkiksi visualisointi, joka kuvaa olympiamitalien määrää hierarkian mukaan, joka muodostuu urheilusta, lajista ja tapahtumasta. Visualisointi näyttää oletusarvoisesti mitalimäärän urheilulajin mukaan, esimerkiksi voimistelu, hiihto ja vesiurheilu. Mutta koska sillä on hierarkia, visualisoinnin yhden elementin (kuten palkin, rivin tai kuplan) valitseminen antaa yksityiskohtaisemman kuvan. Valitsemalla **vesiurheilu**-elementin saat näkyviin uintia, uimahyppyä ja vesipalloa koskevat tiedot.  Valitsemalla **uimahyppy**-elementin saat näkyviin ponnahduslauta-, koroke- ja taitohyppytapahtumat.

Päivämäärät ovat hierarkian yksilöivä tyyppi.  Raporttien suunnittelijat lisäävät usein päivämäärähierarkioita visualisointeihin. Yleinen päivämäärähierarkia sisältää vuoden, vuosineljänneksen, kuukauden ja päivän. 

## <a name="figure-out-which-visuals-can-be-drilled"></a>Selvitä, mihin visualisointeihin voidaan porautua
Etkö ole varma, mitkä Power BI -visualisoinnit sisältävät hierarkian? Liikuta hiiren osoitinta visualisoinnin päällä. Jos näet porautumisen ohjausobjektien yhdistelmän ylhäällä, visualisoinnissa on hierarkia.

![Näyttökuva porautumiskuvakkeista.](./media/end-user-drill/power-bi-drill-icons.png)  

## <a name="learn-how-to-drill-down-and-up"></a>Opi porautumaan alas- ja ylöspäin

Tässä esimerkissä käytetään puukarttaa, jossa on hierarkia, joka koostuu alueesta, kaupungista, postinumerosta ja myymälän nimestä. Puukartassa ennen porautumista tarkastellaan alueella tänä vuonna myytyjen yksiköiden kokonaismäärää. 

![Näyttökuva puukartasta ja sen suodattimista.](./media/end-user-drill/power-bi-treemaps.png)  


### <a name="two-ways-to-access-the-drill-features"></a>Kaksi tapaa käyttää porautumisominaisuuksia

Poraudu alaspäin-, Poraudu ylöspäin- ja Laajenna-toimintoja voi käyttää kahdella eri tavalla visualisoinneissa, jotka sisältävät hierarkioita. Kokeile niitä ja käytä sitä, josta pidät eniten.

- Ensimmäinen tapa: kun osoitat visualisointia, näet kuvakkeet ja voit käyttää niitä.  

    ![Näyttökuva esimerkistä, jossa hiirtä liikutetaan vaihtoehdon päällä.](./media/end-user-drill/power-bi-hover.png)

- Toinen tapa: napsauta visualisointia hiiren kakkospainikkeella ja käytä valikkoa.

    ![Näyttökuva esimerkistä, jossa napsautetaan hiiren kakkospainiketta.](./media/end-user-drill/power-bi-drill-menu.png)



## <a name="drill-pathways"></a>Porautumisen polut

### <a name="drill-down-all-fields-at-once"></a>Porautuminen alaspäin kaikki kentät kerrallaan
![Porautumiskuvake](./media/end-user-drill/power-bi-drill-icon3.png)

Käytettävissä on useita tapoja porautua visualisointiin. Poraudu alaspäin -kuvakkeen valinta vie seuraavalle tasolle hierarkiassa. Jos katsot **Alue**-tasoa Kentuckyssä ja Tennesseessä, voit porautua molemmissa osavaltioissa kaupunkitasolle, sitten postinumeron tasolle ja lopuksi myymälän nimen tasolle. Polun jokainen vaihe tuo näkyviin uusia tietoja.

![Kaavio, jossa näytetään porautumisen polku](./media/end-user-drill/power-bi-drill-path.png)

Valitse porautumiskuvake ![Porautuminen ylöspäin -kuvake](./media/end-user-drill/power-bi-drill-icon5.png) kunnes pääset takaisin kohtaan Yksikköjen kokonaismäärä tänä vuonna alueen mukaan.

### <a name="expand-all-fields-at-once"></a>Laajenna kaikki kentät kerralla
![Laajenna-kuvake](./media/end-user-drill/power-bi-drill-icon6.png)

**Laajenna** lisää muita hierarkiatasoja nykyiseen näkymään. Jos siis tarkastelet **Alue**-tasoa, voit laajentaa ja lisätä kaupungin, postinumeron ja nimen tiedot puukarttaan. Jokainen polun vaihe tuo näkyviin edelliset tiedot ja lisää uuden tietojen tason.

![Kaavio, joka näyttää Laajenna-polun](./media/end-user-drill/power-bi-expand-path.png)

Voit myös valita, haluatko porautua alaspäin vai laajentaa yksi kenttä kerrallaan.


### <a name="drill-down-one-field-at-a-time"></a>Porautuminen alaspäin yksi kenttä kerrallaan


1. Valitse Poraudu alaspäin -kuvake, jos haluat ottaa sen käyttöön ![Näyttökuva Porautuminen alaspäin käytössä / pois käytöstä -kuvakkeesta, joka on otettu käyttöön.](./media/end-user-drill/power-bi-drill-icon2.png).

    Nyt voit halutessasi porautua alaspäin **yksi kenttä kerrallaan** valitsemalla visualisoinnin elementin. Esimerkkejä visuaalisista elementeistä: palkki, kupla ja lehti.

    ![Näyttökuva visualisoinnista, jossa nuoli osoittaa Porautuminen alaspäin käytössä / pois käytöstä -kuvakkeeseen, joka on otettu käyttöön.](media/end-user-drill/power-bi-drill-icon-selected.png)

    Jos et ota porautumista alaspäin käyttöön, visualisoinnin elementin (kuten palkin, kuplan tai lehden) valitseminen ei poraa alaspäin. Sen sijaan se ristisuodattaa muut raporttisivulla olevat kaaviot.

1. Valitse lehti **TN:lle**. Puukartassa näytetään nyt kaikki Tennesseen kaupungit ja alueet, joissa on myymälä.

    ![Näyttökuva puukartasta, joka näyttää vain TN:n tiedot.](media/end-user-drill/power-bi-drill-down-one.png)

1. Tässä vaiheessa voit:

    1. Jatkaa porautumista alaspäin Tennesseelle.

    1. Porautua alaspäin tiettyyn kaupunkiin Tennesseessä.

    1. Laajenna sen sijaan.

    Poraudutaan jälleen alaspäin yksi kenttä kerrallaan.  Valitse **Knoxville, TN**. Puukartassa näkyy nyt Knoxvillen myymälän postinumero.

    ![Näyttökuva puukartasta, joka näyttää postinumeron 37919.](media/end-user-drill/power-bi-drill-two.png)

    Huomaa, että otsikko muuttuu porautuessasi alaspäin ja uudelleen takaisin ylös.

### <a name="expand-all-and-expand-one-field-at-a-time"></a>Kaikkien kenttien laajentaminen ja laajentaminen yksi kenttä kerrallaan

Puukartta, jossa näkyy vain postinumero, ei ole kovin havainnollinen.  *Laajennetaan* siis hierarkiaa yksi taso alaspäin.  

1. Kun puukartta on aktiivinen, valitse *Laajenna alaspäin* -kuvake ![Näyttökuva Laajenna alaspäin -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon6.png) Puukartassa näkyy nyt kaksi hierarkian tasoa: postinumero ja myymälän nimi.

    ![Näyttökuva puukartasta, joka näyttää postinumeron ja myymälän nimen](./media/end-user-drill/power-bi-expand-one.png)

1. Jos haluat nähdä kaikki neljä Tennesseen tietojen hierarkiatasoa, valitse Poraudu ylöspäin -nuoli, kunnes saavutat puukartan toisen tason, **Yksiköt yhteensä tänä vuonna alueen ja kaupungin mukaan**.

    ![Näyttökuva puukartasta, joka näyttää kaikki TN:n tiedot.](media/end-user-drill/power-bi-expand-two.png)

1. Varmista, että porautuminen alaspäin on edelleen käytössä, ![Näyttökuva Poraudu alaspäin käytössä / pois käytöstä -kuvakkeesta, joka on otettu käyttöön.](./media/end-user-drill/power-bi-drill-icon2.png) ja valitse *Laajenna alaspäin* -kuvake ![Näyttökuva Laajenna alaspäin -kuvakkeesta.](./media/end-user-drill/power-bi-drill-icon6.png) Puukartassa näytetään nyt sama määrä lehtiä (ruutuja), mutta jokaisessa lehdessä on lisätietoja. Pelkän kaupungin ja osavaltion sijasta siinä näkyy nyt myös postinumero.

    ![Näyttökuva visualisoinnista, joka näyttää kaupungin, osavaltion ja postinumeron.](./media/end-user-drill/power-bi-expand-three.png)

1. Valitse *Laajenna alaspäin* -kuvake vielä kertaalleen, jotta näet puukartassa Tennesseen tietojen kaikki neljä hierarkiatasoa. Osoittamalla lehteä näet vielä lisää tietoja.

    ![Näyttökuva puukartasta, joka näyttää työkaluvihjeen, jossa on lehtikohtaisia tietoja.](./media/end-user-drill/power-bi-expand-all.png)

## <a name="show-the-data-as-you-drill"></a>Näytä tiedot porautuessasi
Käytä **Näytä tiedot** -valintaa, jotta näet kulissien taakse. Aina kun poraudut tai laajennat, **Näytä tiedot** näyttää tiedot, joita käytetään visualisoinnin luomiseen. Tietojen avulla voit ymmärtää, miten hierarkiat, porautuminen ja laajentaminen toimivat yhdessä visualisointien luomisessa. 

Valitse oikeassa yläkulmassa olevat kolme pistettä (...) ja valitse sitten **Näytä tiedot**. 

![Näyttökuva kolmen pisteen valikosta.](./media/end-user-drill/power-bi-ellipses.png)

Seuraavassa taulukossa näytetään tulokset, jotka saadaan näkyviin porauduttaessa alaspäin kaikki kentät kerralla alueesta myymälään nimeen.  


![Näyttökuva jokaisen neljän porautumistason tietojen näyttämisestä.](./media/end-user-drill/power-bi-show-data.png)

Huomaa, että kokonaismäärät ovat samat kohdissa **Kaupunki**, **Postinumero** ja **Nimi**. Näin ei aina ole.  Näissä tiedoissa on vain yksi myymälä kullakin postinumerolla ja kussakin kaupungissa.  



## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset
Oletusarvoisesti poraaminen ei suodata raportin muita visualisointeja. Raportin suunnittelija voi kuitenkin muuttaa tätä oletustoimintaa. Kun poraudut, katso, ovatko sivun muut visualisoinnit ristiinsuodatettu tai ristiinkorostettu.


## <a name="next-steps"></a>Seuraavat vaiheet

[Visualisoinnit Power BI -raporteissa](../visuals/power-bi-report-visualizations.md)

[Power BI -raportit](end-user-reports.md)

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
