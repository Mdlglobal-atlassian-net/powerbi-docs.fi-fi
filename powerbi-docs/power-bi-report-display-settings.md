---
title: Power BI -raportin sivun näyttöasetukset
description: Raportin sivun näyttö- ja näkymäasetukset
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: cc2ddd0b6fbd0b621c07056ed4b525f66d81319c
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/21/2019
ms.locfileid: "74265880"
---
# <a name="page-display-settings-in-a-power-bi-report"></a>Power BI -raportin sivun näyttöasetukset
Ymmärrämme, miten tärkeää on pitää raportin asettelu pikselilleen oikeana. Joskus se voi olla hankalaa, koska sinä ja työtoverisi saatatte katsella raportteja erikokoisilta näytöiltä, joissa on erilaiset kuvasuhteet. 

Näyttönäkymän oletusasetuksena on **Sovita sivulle**, ja näytön koon oletusasetus on **16:9**. Jos haluat lukita käyttöön jonkin muun kuvasuhteen tai sovittaa raportin eri tavalla, käytettävissäsi on kaksi työkalua: ***Sivunäkymä***-asetukset ja ***Sivun koko*** -asetukset.


<iframe width="560" height="315" src="https://www.youtube.com/embed/5tg-OXzxe2g" frameborder="0" allowfullscreen></iframe>


## <a name="where-to-find-page-view-settings-in-the-power-bi-service-and-power-bi-desktop"></a>Sivun näkymäasetusten sijainti Power BI -palvelussa ja Power BI Desktopissa
Sivun näkymäasetukset ovat käytettävissä sekä Power BI -palvelussa että Power BI Desktopissa, mutta niiden käyttöliittymät poikkeavat hieman toisistaan. Seuraavissa osioissa kerrotaan, missä näkymäasetukset sijaitsevat kummassakin Power BI -työkalussa.

### <a name="in-power-bi-desktop"></a>Power BI Desktopissa
Valitse Raporttinäkymästä **Näkymä**, jolloin esiin tulee sivun näkymäasetukset sekä puhelimen asetteluasetukset.

  ![Työpöydän sivun näkymäasetukset](media/power-bi-report-display-settings/power-bi-desktop-view-settings.png)

### <a name="in-the-power-bi-service-apppowerbicom"></a>Power BI -palvelussa (app.powerbi.com)
Avaa Power BI -palvelussa raportti ja valitse vasemmasta yläkulmasta valikko **Näkymä**.

![palvelun sivun näkymäasetukset](media/power-bi-report-display-settings/power-bi-change-page-view.png)

Sivun näkymäasetukset ovat käytettävissä sekä [luku- että muokkausnäkymässä](consumer/end-user-reading-view.md). Muokkausnäkymässä raportin omistaja voi määrittää yksittäisille raportin sivuille sivun näkymäasetukset, ja asetukset tallentuvat yhdessä raportin kanssa. Kun työtoverit avaavat raportin lukunäkymässä, he näkevät raportin sivut omistajan asetusten mukaisesti. Lukunäkymässä työtoverit voivat muuttaa *joitakin* **Sivunäkymä**-asetuksia, mutta muutoksia ei tallenneta raportin sulkemisen yhteydessä.

## <a name="page-view-settings"></a>Sivun näkymäasetukset
Ensimmäiset Sivunäkymä-asetukset määrittävät raporttisivun näyttämisen suhteessa selainikkunaan. Vaihtoehdot ovat:

* **Sovita sivulle** (oletus): Sisältö skaalataan sen mukaan, miten se sopii sivulle parhaiten
* **Sovita leveyteen**: Sisältö skaalataan mahtumaan sivulle leveyssuunnassa
* **Todellinen koko**: Sisältö näytetään täydessä koossa

Seuraavat Sivunäkymä-asetukset määrittävät objektien asettelun raporttipohjalla. Vaihtoehdot ovat:

* **Näytä ruudukon viivat**: Ottaa käyttöön ruudukon, joka auttaa objektien sijoittelemisessa raporttipohjalle.
* **Kohdista ruudukkoon**: käytetään **Näytä ruudukon viivat** -asetuksen kanssa objektien tasaamiseen tarkasti raporttipohjalle. 
* **Lukitse objektit**: lukitsee kaikki pohjalla olevat objektit niin, ettei niitä voi siirtää eikä niiden kokoa muuttaa.
* **Valintaruutu**: **Valinta**-ruudussa näkyvät kaikki kankaalla olevat objektit. Voit päättää, mitkä näytetään ja mitkä piilotetaan.

    ![Valinta-paneeli](media/power-bi-report-display-settings/power-bi-selection-pane.png)



## <a name="page-size-settings"></a>Sivun koko -asetukset
![muuta sivun kokoa -asetukset](media/power-bi-report-display-settings/power-bi-page-size.png)

**Sivun koko** -asetukset ovat vain raportin omistajan käytettävissä. Power BI -palvelussa (app.powerbi.com) se tarkoittaa, että raportin pystyy avaamaan [muokkausnäkymässä](consumer/end-user-reading-view.md). **Sivun koko** -asetukset ovat **Visualisoinnit**-ruudussa, ja ne määrittävät raporttipohjan kuvasuhteen ja todellisen koon (kuvapisteinä):   

* Suhde 4:3
* Suhde 16:9 (oletusasetus)
* Letter
* Mukautettu (korkeus ja leveys kuvapisteinä)

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttinäkymä Power BI Desktopissa](desktop-report-view.md)

[Muuta sivun näkymä- ja kokoasetuksia omissa Power BI -raporteissasi](consumer/end-user-report-view.md)

Lue lisää [Power BI -raporteista](consumer/end-user-reports.md)

[Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

