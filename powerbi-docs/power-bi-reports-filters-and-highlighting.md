---
title: Tietoja Power BI -raporttien suodattimista ja korostamisesta
description: Tietoja Power BI -raporttien suodattimista ja korostamisesta
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: monitoring
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/13/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: ffbab0c1e203ce3fd8779b4eebca90debbb531e5
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2018
ms.locfileid: "30975432"
---
# <a name="about-filters-and-highlighting-in-power-bi-reports"></a>Tietoja Power BI -raporttien suodattimista ja korostamisesta
***Suodattimet*** poistavat kaikki muut tiedot paitsi ne, joihin haluat keskittyä.  ***Korostus*** ei suodata, koska se ei poista tietoja, vaan korostaa näkyvien tietojen alijoukon, jolloin korostamattomat tiedot pysyvät näkyvissä, mutta himmennettynä.

Raportteja voidaan suodattaa ja korostaa monin eri tavoin Power BI:ssä. Kaikkien näiden tietojen kasaaminen yhteen artikkeliin olisi turhan sekavaa, joten olemme olet ryhmitelleet tiedot näin:

* Johdanto suodattimiin ja korostuksiin (artikkeli, jota luet parhaillaan)
* Tavat, joilla voit [luoda ja käyttää suodattimia ja korostusta Muokkausnäkymässä tai raporteissa, jotka omistat](power-bi-report-add-filter.md). Kun sinulla on omistaja muokkausoikeudet, voit luoda, muokata ja poistaa suodattimia ja korostuksia raporteissa.
* Tavat, jolla voit [käyttää suodattimia ja korostuksia raportissa, joka on jaettu kanssasi tai raportin Lukunäkymässä](service-reading-view-and-editing-view.md). Se, mitä voit tehdä, on rajoitetumpaa, mutta Power BI tarjoaa silti laajan valikoiman vaihtoehtoja suodattamiseen ja korostamiseen.  
* [Yksityiskohtainen esittely suodatinten ja korostusten ohjaimista, jotka ovat käytettävissä Muokkausnäkymässä ](power-bi-how-to-report-filter.md), mukaan lukien perusteellisempi esittely suodatintyypeistä (esimerkiksi päivämäärä ja kellonaika, numerot ja teksti) sekä perusvaihtoehtojen ja laajempien vaihtoehtojen välinen ero.
* Nyt, kun olet oppinut, miten suodattimet ja korostus toimivat oletusarvoisesti, [voit lukea, miten sivulla olevat visualisoinnit suodattavat ja korostavat toisiaan](service-reports-visual-interactions.md)

> [!TIP]
> Mistä Power BI tietää, miten tiedot liittyvät toisiinsa?  Se käyttää pohjana olevan [tietomallin](https://support.office.com/article/Create-a-Data-Model-in-Excel-87e7a54c-87dc-488e-9410-5c75dbcb0f7b?ui=en-US&rs=en-US&ad=US) eri taulukoiden ja kenttien välisiä suhteita pannessaan raporttisivulla olevat kohteet vuorovaikutukseen keskenään.
> 
> 

## <a name="introduction-to-filters-and-highlighting-in-reports-using-the-filters-pane"></a>Johdanto raporteissa oleviin suodattimiin ja korostuksiin Suodattimet-ruudun avulla
 Tässä artikkelissa esitellään suodattaminen ja korostaminen Power BI -palvelussa.  Käyttökokemus on kuitenkin lähes sama kuin Power BI Desktopissa.  

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Suodattimia ja korostuksia voidaan ottaa käyttöön käyttämällä **Suodattimet**-ruutua tai tekemällä valinnat suoraan itse raportissa (ad-hoc-raportin osalta katso sivun alareuna). Suodattimet-ruudussa näkyvät taulukot ja kentät, joita on käytetty raportissa sekä suodattimet, joita on mahdollisesti käytetty. Suodattimet on jaettu seuraavasti: **Sivutaso**, **Raporttitaso**, **Siirtyminen** ja **Visuaalinen taso**.  Näet vain visuaalisen tason suodattimia, jos olet valinnut visualisoinnin raportin pohjalta.

> [!TIP]
> Jos suodattimessa on sana **Kaikki** sen vieressä, se tarkoittaa, että koko kenttä on sisällytetty suodattimena.  Esimerkiksi **Chain(All)** alla olevassa näyttökuvassa ilmaisee, että tämä raporttisivu sisältää tietoja kaikista säilön ketjuista.  Toisaalta raporttitason **FiscalYear is 2013 or 2014** -suodatin ilmaisee, että raportti sisältää tietoja vain tilikaudelle 2013 ja 2014.
> 
> 

## <a name="filters-in-reading-view-versus-editing-view"></a>Suodattimet Lukunäkymässä verrattuna Muokkausnäkymään
Raportteja voidaan käsitellä kahdessa eri näkymässä: [Lukunäkymässä ja Muokkausnäkymässä](service-reading-view-and-editing-view.md).  Käytettävissä olevat suodatusominaisuudet vaihtelevat näkymän mukaan.

* Muokkausnäkymässä voit lisätä raportti- ja sivusuodattimia sekä siirtymissuodattimia ja visuaalisia suodattimia. Kun tallennat raportin, suodattimet tallennetaan raportin kanssa, vaikka avaisit sen mobiilisovelluksessa. Lukunäkymässä raporttia tarkastelevat henkilöt voivat käsitellä lisäämiäsi suodattimia, mutta he eivät voi lisätä uusia suodattimia raporttiin.
* Lukunäkymässä voit käsitellä kaikkia suodattimia, jotka ovat jo olemassa raportissa, ja tallentaa tekemäsi valinnat.  Et kuitenkaan voi lisätä uusia suodattimia.

### <a name="the-filters-pane-in-reading-view"></a>Suodattimet-ruutu Lukunäkymässä
Jos sinulla on oikeudet raporttiin vain Lukunäkymässä, Suodattimet-ruutu näyttää tältä:

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Tällä raportin sivulla on 6 sivutason suodatinta ja 1 raporttitason suodatin.

Visuaalisen tason suodattimet saat tarvittaessa näkymiin valitsemalla visuaalisen. Alla olevassa kuvassa kuplakaaviossa on 6 suodatinta käytössä.

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

Lukunäkymässä voit tutkia tietoja muokkaamalla olemassa olevia suodattimia. Tekemäsi muutokset tallennetaan raporttiin myös silloin, kun avaat raportin mobiilisovelluksessa. Lue tarkemmat ohjeet artikkelista [Power BI -palvelun Lukunäkymä ja Muokkausnäkymä](service-reading-view-and-editing-view.md)

### <a name="the-filters-pane-in-editing-view"></a>Suodattimet-ruutu Muokkausnäkymässä
Kun sinulla on raportin omistajan oikeudet ja avaat raportin Muokkausnäkymässä, näet, että **Suodattimet** on vain yksi monista käytettävissä olevista muokkausruuduista.

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Samoin kuin Lukunäkymässä (edellä) näemme, että tällä raportin sivulla on 6 sivutason suodatinta ja 1 raporttitason suodatin. Ja valitsemalla kuplakaavion näkisimme, että sillä on 6 visuaalisen tason suodatinta.

Muokkausnäkymässä on kuitenkin niin paljon muutakin, mitä suodattimilla ja korostuksilla voidaan tehdä. Merkittävin ero on, että voimme lisätä uusia suodattimia. Ohjeet sen tekemiseen ja paljon muuta on artikkelissa [Suodattimen lisääminen raporttiin](power-bi-report-add-filter.md)

## <a name="ad-hoc-filtering-and-highlighting"></a>Ad-hoc-suodattaminen ja korostaminen
Valitse raportin kankaasta kenttä muun sivun suodattamiseksi ja korostamiseksi. Valitse sitten tyhjä tila samassa visualisoinnissa sen poistamiseksi. Tämäntyyppinen suodattaminen ja korostaminen on hauska tapa tutustua nopeasti tietojen vaikutuksiin. Katso ohjeet artikkelista[Visuaaliset vuorovaikutukset](service-reports-visual-interactions.md) tällaisen ristiinsuodatuksen ja ristiinkorostuksen hienosäätämisestä.

![](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)

Kun suljet raportin, tekemäsi muutokset tallennetaan. Jos haluat kumota suodatuksen, valitse **Palauta oletusarvot** yläreunan valikkoriviltä.

![](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Suodattimien ja korostamisen käsitteleminen (Lukunäkymässä)](service-reading-view-and-editing-view.md)

[Suodattimen lisääminen raporttiin (Muokkausnäkymässä)](power-bi-report-add-filter.md)

[Tutustu raportin suodattimiin](power-bi-how-to-report-filter.md)

[Raportin visualisointien ristiinsuodatuksen ja ristiinkorostuksen muuttaminen suhteessa toisiinsa](service-reports-visual-interactions.md)

Lue lisää [Power BI -raporteista](service-reports.md)

Ilmenikö muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

