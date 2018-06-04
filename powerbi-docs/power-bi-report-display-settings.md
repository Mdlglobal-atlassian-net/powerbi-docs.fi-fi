---
title: Raportin sivun näyttö- ja näkymäasetukset
description: Raportin sivun näyttö- ja näkymäasetukset
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: ''
qualityfocus: ''
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/24/2017
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 8d8fd5e3c983acc458647ae5efce67bafd4cd412
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973802"
---
# <a name="page-display-settings-in-a-power-bi-report"></a>Power BI -raportin sivun näyttöasetukset
Ymmärrämme, miten tärkeää on pitää raportin asettelu pikselilleen oikein. Joskus se voi olla hankalaa, koska sinä ja työtoverisi saatatte katsella raportteja erikokoisilta näytöiltä, joissa on erilaiset kuvasuhteet. 

Näyttönäkymän oletusasetuksena on **Sovita sivulle**, ja näytön koon oletusasetus on **16:9**. Jos haluat lukita käyttöön jonkin muun kuvasuhteen tai sovittaa raportin eri tavalla, käytettävissäsi ovat ***Sivunäkymä***- ja ***Sivun koko*** ‑asetukset.

<iframe width="560" height="315" src="https://www.youtube.com/embed/5tg-OXzxe2g" frameborder="0" allowfullscreen></iframe>


## <a name="where-to-find-page-view-settings-in-power-bi-service-and-power-bi-desktop"></a>Sivun näkymäasetusten sijainti Power BI -palvelussa ja Power BI Desktopissa
Sivun näkymäasetukset ovat käytettävissä sekä Power BI -palvelussa että Power BI Desktopissa, mutta niiden käyttöliittymät poikkeavat hieman toisistaan. Seuraavissa kahdessa osiossa kerrotaan, missä näkymäasetukset sijaitsevat kummassakin Power BI ‑työkalussa.

### <a name="in-power-bi-desktop"></a>Power BI Desktopissa
Valitse Raporttinäkymästä **Näkymä**, jolloin esiin tulee sivun näkymäasetukset sekä puhelimen asetteluasetukset.

  ![Valinta-paneeli](media/power-bi-report-display-settings/power-bi-desktop-view-settings.png)

### <a name="in-power-bi-service-apppowerbicom"></a>Power BI -palvelussa (app.powerbi.com)
Avaa Power BI-palvelussa raportti ja valitse vasemmasta yläkulmasta valikko **Näkymä**.

![](media/power-bi-report-display-settings/power-bi-change-page-view.png)

Sivun näkymäasetukset ovat käytettävissä sekä [luku- että muokkausnäkymässä](service-reading-view-and-editing-view.md). Muokkausnäkymässä raportin omistaja voi määrittää yksittäisille raportin sivuille sivun näkymäasetukset, ja asetukset tallentuvat yhdessä raportin kanssa. Kun työtoverit avaavat raportin lukunäkymässä, he näkevät raportin sivut omistajan asetusten mukaisesti.  Lukunäkymässä työtoverit voivat muuttaa *joitakin* sivun näkymäasetuksia, mutta muutoksia ei tallenneta raportin sulkemisen yhteydessä.

##    <a name="page-view-settings"></a>Sivun näkymäasetukset
Ensimmäiset *Sivunäkymä*-asetukset määrittävät raporttisivun näyttämisen suhteessa selainikkunaan.  Vaihtoehdot ovat:

* **Sovita sivulle** (oletusasetus): sisältö skaalataan sen mukaan, miten se sopii sivulle parhaiten
* **Sovita leveyteen**: sisältö ovat skaalataan mahtumaan sivulle leveyssuunnassa
* **Todellinen koko**: sisältö näytetään täydessä koossa

Seuraavat *Sivunäkymä*-asetukset määrittävät objektien asettelun raporttipohjalla.

* **Näytä ruudukon viivat**: ottaa käyttöön ruudukon, joka auttaa objektien sijoittelemisessa raporttipohjalle
* **Kohdista ruudukkoon**: käytetään **Näytä ruudukon viivat** ‑asetuksen kanssa objektien tasaamiseen tarkasti raporttipohjalle 
* **Lukitse objektit**: lukitsee kaikki pohjalla olevat objektit niin, ettei niitä voi siirtää eikä niiden kokoa muuttaa
* **Valinta-paneeli**: Valinta-paneelissa on luettelo kaikista raporttipohjalla olevista objekteista, joista voit päättää, mitkä näytetään ja mitkä piilotetaan

    ![Valinta-paneeli](media/power-bi-report-display-settings/power-bi-selection-pane.png)



## <a name="page-size-settings"></a>Sivun koko ‑asetukset
![](media/power-bi-report-display-settings/power-bi--page-size.png)

*Sivun koko* ‑asetukset ovat vain raportin omistajan käytettävissä. Power BI -palvelussa (app.powerbi.com) se tarkoittaa, että pystyy avaamaan raportin [muokkausnäkymässä](service-reading-view-and-editing-view.md). Asetuksilla määritetään raporttipohjan kuvasuhde ja todellinen koko (kuvapisteinä).   

* Suhde 4:3
* Suhde 16:9 (oletusasetus)
* Cortana
* Letter
* Mukautettu (korkeus ja leveys kuvapisteinä)

## <a name="next-steps"></a>Seuraavat vaiheet
[Opettele käyttämään sivun näkymä- ja kokoasetuksia omissa Power BI ‑raporteissasi](power-bi-change-report-display-settings.md).

Lue lisää [Power BI -raporteista](service-reports.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
