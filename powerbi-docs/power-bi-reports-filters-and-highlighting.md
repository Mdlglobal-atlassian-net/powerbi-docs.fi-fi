---
title: Suodattimet ja korostaminen Power BI -raporteissa
description: Tietoja Power BI -raporttien suodattimista ja korostamisesta
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/23/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: f1722690ff974a9d4fac6e94243e1024bfbfc12e
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79207064"
---
# <a name="filters-and-highlighting-in-power-bi-reports"></a>Suodattimet ja korostaminen Power BI -raporteissa
 Tässä artikkelissa esitellään suodattaminen ja korostaminen Power BI -palvelussa. Käyttökokemus on lähes sama kuin Power BI Desktopissa. *Suodattimet* poistavat kaikki muut tiedot paitsi ne, joihin haluat keskittyä. *Korostus* ei ole suodattamista. Se ei poista tietoja, vaan korostaa näkyvien tietojen alijoukon; korostamattomat tiedot pysyvät näkyvissä, mutta himmeinä.

Raportteja voidaan suodattaa ja korostaa monin eri tavoin Power BI:ssä. Kaikkien näiden tietojen kokoaminen yhteen artikkeliin olisi turhan sekavaa, joten tiedot on jaettu seuraaviin osioihin:

* Johdanto suodattimiin ja korostuksiin (artikkeli, jota luet parhaillaan).
* Ohjeet [suodattimien luomiseen ja käyttämiseen muokkausnäkymässä](power-bi-report-add-filter.md) Power BI Desktopin ja Power BI -palvelun raporteissa. Kun sinulla on raportin muokkausoikeudet, voit luoda, muokata ja poistaa suodattimia raporteissa.
* Tavat, joilla visualisoinnit [käyttävät suodattimia ja korostuksia kanssasi jaetussa raportissa](consumer/end-user-interactions.md) raportin lukunäkymässä Power BI -palvelussa. Se, mitä voit tehdä, on rajoitetumpaa, mutta käytettävissäsi on silti laaja valikoima vaihtoehtoja suodattamiseen ja korostamiseen.  
* Yksityiskohtainen esittely [suodattimien ja korostusten ohjaimista, jotka ovat käytettävissä muokkausnäkymässä](power-bi-report-add-filter.md) Power BI Desktopissa ja Power BI -palvelussa. Artikkelissa perehdytään suodattimien tyyppeihin, kuten päivämäärään ja aikaan, lukuihin ja tekstiin. Se kattaa myös erot perus- ja lisäasetusten välillä.
* Kun olet oppinut, miten suodattimet ja korostus toimivat oletusarvoisesti, voit lukea siitä, [miten sivulla olevat visualisoinnit suodattavat ja korostavat toisiaan](service-reports-visual-interactions.md)

**Tiesitkö?** Power BI:ssä on uusi suodatuskokemus. Lue lisää [uudesta suodatuskokemuksesta Power BI -raporteissa](power-bi-report-filter.md).

![Uusi suodatuskokemus](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading.png)


## <a name="intro-to-the-filters-pane"></a>Suodattimet-ruudun esittely

Voit käyttää suodattimia **Suodattimet**-ruudussa tai [tekemällä valintoja osittajissa](visuals/power-bi-visualization-slicers.md) suoraan itse raportissa. Suodattimet-ruudussa näkyvät taulukot ja kentät, joita on käytetty raportissa sekä suodattimet, joita on mahdollisesti käytetty. 

![Suodattimet-ruutu](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Käytössä on neljä erilaista suodatinta:

- **sivusuodatin** koskee kaikkia raporttisivulla olevia visualisointeja     
- **visuaalinen suodatin** koskee raporttisivulla olevaa yksittäistä visualisointia. Näet vain visuaalisen tason suodattimia, jos olet valinnut visualisoinnin raporttipohjasta.    
- **raporttisuodatin** koskee kaikkia raportin sivuja.    
- **porautumissuodatin** koskee mitä tahansa raportin entiteettiä    

Voit hakea haluamaasi arvoa sivulta, visualisoinnista ja raporttisuodattimista luku- tai muokkausnäkymässä ja valita sen. 

![Hae suodattimessa](media/power-bi-reports-filters-and-highlighting/power-bi-search-filter.png)

Jos suodattimen vieressä on sana **kaikki**, se tarkoittaa, että kaikki kentän arvot sisältyvät suodattimeen.  Esimerkiksi **Chain(All)** alla olevassa näyttökuvassa tarkoittaa, että tämä raporttisivu sisältää tietoja kaikista säilön ketjuista.  Toisaalta raporttitason **FiscalYear is 2013 or 2014** -suodatin ilmaisee, että raportti sisältää tietoja vain tilikaudelta 2013 ja 2014.

## <a name="filters-in-reading-or-editing-view"></a>Suodattimet luku- tai muokkausnäkymässä
Raportteja voidaan käsitellä kahdessa eri näkymässä: [lukunäkymässä](consumer/end-user-reading-view.md) ja muokkausnäkymässä. Käytettävissä olevat suodatusominaisuudet vaihtelevat näkymän mukaan.

* Muokkausnäkymässä voit lisätä raportti- ja sivusuodattimia sekä porautumissuodattimia ja visuaalisia suodattimia. Kun tallennat raportin, suodattimet tallennetaan raportin mukana, vaikka avaisit sen mobiilisovelluksessa. Lukunäkymässä raporttia tarkastelevat henkilöt voivat käsitellä lisäämiäsi suodattimia, mutta he eivät voi lisätä uusia suodattimia raporttiin.
* Lukunäkymässä voit käsitellä kaikkia raportissa jo olevia suodattimia ja tallentaa tekemäsi valinnat. Et voi lisätä uusia suodattimia.

### <a name="filters-in-reading-view"></a>Suodattimet lukunäkymässä
Jos sinulla on oikeudet raporttiin vain lukunäkymässä, Suodattimet-ruutu näyttää tältä:

![Suodattimet lukunäkymässä](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Tällä raportin sivulla on kuusi sivutason suodatinta ja yksi raporttitason suodatin.

Jokaisessa visualisoinnissa voi olla suodattimia kaikille visualisoinnin kentille, ja raportin tekijä voi lisätä muita. Alla olevassa kuvassa kuplakaaviossa on kuusi suodatinta.

![Visualisointitason suodatin](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

Lukunäkymässä voit tutkia tietoja muokkaamalla olemassa olevia suodattimia. Tekemäsi muutokset tallennetaan raporttiin myös silloin, kun avaat raportin mobiilisovelluksessa. Lue ohjeet [raportin Suodattimet-ruudun esittelystä](consumer/end-user-report-filter.md)

Kun suljet raportin, suodattimet tallennetaan. Jos haluat kumota suodatuksen ja palata takaisin raportin laatijan oletusarvoiseen suodatukseen, jaotteluun, porautumiseen ja lajitteluun, valitse yläosan valikosta **Palauta oletukset**.

![Palauta oletukset -kuvake](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

### <a name="filters-in-editing-view"></a>Suodattimet muokkausnäkymässä
Kun sinulla on raportin omistajan oikeudet ja avaat raportin muokkausnäkymässä, näet, että **Suodattimet** on vain yksi monista käytettävissä olevista muokkausruuduista.

![Suodattimet-ruutu muokkausnäkymässä](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Kuten lukunäkymässä, tällä raportin sivulla on kuusi sivutason suodatinta ja yksi raporttitason suodatin. Valitsemalla kuplakaavion voitaisiin nähdä, että sillä on kuusi visuaalisen tason suodatinta.

Suodattimia ja korostamista voidaan hyödyntää enemmän muokkausnäkymässä. Pääasiassa voidaan lisätä uusia suodattimia. Lue siitä, miten [raporttiin lisätään suodatin](power-bi-report-add-filter.md), ja paljon muuta.

## <a name="ad-hoc-highlighting"></a>Ad-hoc-korostaminen
Valitse arvon tai akselin nimi visualisoinnista, jos haluat korostaa muut sivulla olevat visualisoinnit. Jos haluat poistaa korostuksen, valitse arvo uudelleen tai valitse mikä tahansa tyhjä tila samassa visualisoinnissa. Korostaminen on hauska tapa tutustua nopeasti tietojen vaikutuksiin. Ohjeet tällaisen ristiinkorostuksen hienosäätämisestä ovat artikkelissa [Visualisointitoimet](service-reports-visual-interactions.md) .

![Ristiinkorostus](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)


## <a name="next-steps"></a>Seuraavat vaiheet

[Uusi suodatuskokemus Power BI -raporteissa](power-bi-report-filter.md)

[Lisää suodatin raporttiin (muokkausnäkymässä)](power-bi-report-add-filter.md)

[Tutustu raportin suodattimiin](consumer/end-user-report-filter.md)

[Muuta raportin visualisointien ristiinsuodatusta ja ristiinkorostusta suhteessa toisiinsa](consumer/end-user-interactions.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

