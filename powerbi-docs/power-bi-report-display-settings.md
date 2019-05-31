---
title: Power BI -raportin sivun näyttöasetukset
description: Raportin sivun näyttö- ja näkymäasetukset
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 8a96371d6cb54d47d412165ef179df78a34b8e19
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412946"
---
# <a name="page-display-settings-in-a-power-bi-report"></a>Power BI -raportin sivun näyttöasetukset
Ymmärrämme on pitää raportin asettelu pikselilleen täydellisen. Joskus se voi olla haastavaa, koska sinä ja työtoverisi voivat tarkastella näitä raportteja erikokoisilta näytöiltä, joissa eri kuvasuhteet. 

Näyttönäkymän oletusasetuksena on **Sovita sivulle**, ja näytön koon oletusasetus on **16:9**. Jos haluat lukita käyttöön jonkin muun kuvasuhteen tai sovittaa raportin eri tavalla, käytettävissäsi on kaksi työkalua: ***Sivunäkymä*** asetukset ja ***sivun koko*** asetukset.


<iframe width="560" height="315" src="https://www.youtube.com/embed/5tg-OXzxe2g" frameborder="0" allowfullscreen></iframe>


## <a name="where-to-find-page-view-settings-in-the-power-bi-service-and-power-bi-desktop"></a>Sivun näkymäasetukset mistä Power BI-palvelussa ja Power BI Desktop
Sivun näkymäasetukset ovat käytettävissä Power BI-palvelussa ja Power BI Desktop, mutta niiden käyttöliittymät poikkeavat hieman erilainen. Seuraavassa kerrotaan löytämiseen näkymäasetukset sijaitsevat kummassakin Power BI ‑työkalussa.

### <a name="in-power-bi-desktop"></a>Power BI Desktopissa
Valitse Raporttinäkymästä **Näkymä**, jolloin esiin tulee sivun näkymäasetukset sekä puhelimen asetteluasetukset.

  ![Työpöydän sivun näkymäasetukset](media/power-bi-report-display-settings/power-bi-desktop-view-settings.png)

### <a name="in-the-power-bi-service-apppowerbicom"></a>Power BI-palvelussa (app.powerbi.com)
Avaa Power BI-palvelussa raportti ja valitse **näkymän** vasemmasta yläkulmasta valikko.

![palvelun sivun näkymäasetukset](media/power-bi-report-display-settings/power-bi-change-page-view.png)

Sivun näkymäasetukset ovat käytettävissä sekä [Lukunäkymä ja Muokkausnäkymä](consumer/end-user-reading-view.md). Muokkausnäkymässä raportin omistaja voi määrittää yksittäisille raporttisivuille sivun näkymäasetukset ja asetukset tallentuvat raportin kanssa. Kun työtoverit avaavat raportin lukunäkymässä, he näkevät raportin sivut omistajan asetusten mukaisesti. Lukunäkymässä, työtoverit voivat muuttaa *joitakin* , **Sivunäkymä** asetukset, mutta muutoksia ei tallenneta raportin sulkemisen yhteydessä.

## <a name="page-view-settings"></a>Sivun näkymäasetukset
Sivun näkymäasetukset ensimmäiset määrittää raporttisivun suhteessa selainikkunaan. Vaihtoehdot ovat:

* **Sovita sivulle** (oletus): Sisältö skaalataan sopimaan sivulle parhaiten
* **Sovita leveyteen**: Sisältö ovat skaalataan mahtumaan sivulle leveyssuunnassa
* **Todellinen koko**: Sisältö näytetään täydessä koossa

Toinen joukko sivun asetukset ohjausobjektit raporttipohjalla objektien asettelun. Vaihtoehdot ovat:

* **Näytä ruudukon viivat**: Ota käyttöön ruudukon, joka auttaa objektien sijoittelemisessa raporttipohjalle.
* **Kohdista ruudukkoon**: Käyttäminen **Näytä ruudukon viivat** - ‑asetuksen objektien raporttipohjalla. 
* **Lukitse objektit**: Lukitse objektien piirtoalustalla, niin, että niitä voi siirtää eikä niiden kokoa muuttaa.
* **Valinta-ruutu**: **Valinta** ruudussa näkyvät kaikkien objektien pohjalla. Voit päättää, mitkä näytetään ja mitkä piilotetaan.

    ![Valinta-paneeli](media/power-bi-report-display-settings/power-bi-selection-pane.png)



## <a name="page-size-settings"></a>Sivun koon asetukset
![Muuta sivun koon asetukset](media/power-bi-report-display-settings/power-bi-page-size.png)

**Sivun koko** asetukset ovat vain raportin omistajan käytettävissä. Power BI-palvelussa (app.powerbi.com) se tarkoittaa, että pystyy avaamaan raportin [muokkausnäkymässä](consumer/end-user-reading-view.md). **Sivun koko** asetukset ovat **visualisoinnit** ruudussa ja ohjausobjektin kuvasuhde ja todellinen koko (kuvapisteinä) raporttipohjan:   

* Suhde 4:3
* Suhde 16:9 (oletusasetus)
* Cortana
* Letter
* Mukautettu (korkeus ja leveys kuvapisteinä)

## <a name="next-steps"></a>Seuraavat vaiheet
[Raporttinäkymä Power BI Desktop](desktop-report-view.md)

[Muuta sivun näkymä ja sivun koon asetukset-Power BI-raporteissa](consumer/end-user-report-view.md)

Lue lisää [Power BI -raporteista](consumer/end-user-reports.md)

[Power BI-palvelun kuluttajille peruskäsitteet](consumer/end-user-basic-concepts.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

