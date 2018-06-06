---
title: Tietojen ja tietueiden näyttäminen Power BI Desktop -visualisoinneissa
description: Power BI Desktopin ominaisuuksien ”Näytä tiedot” ja ”Näytä tietueet” käyttäminen yksityiskohtiin pääsemiseksi
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/22/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: c44a5140fe40217aac170abb0b351197803b6299
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30974502"
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Power BI Desktopin ominaisuuksien ”Näytä tiedot” ja ”Näytä tietueet” käyttäminen
**Power BI Desktopissa** voit syventyä minkä tahansa visualisoinnin tietoihin ja nähdä tietojen tekstiesityksen tai yksittäiset tietoelementit valituista visualisoinneista. Näitä ominaisuuksia kutsutaan joskus nimellä *napsauttamalla tarkasteltava raportti* tai *alirakenneraportiksi* tai *alirakenneraporttien yksityiskohtien tiedoiksi*.

Voit käyttää **Näytä tietueet** tarkastelemaan yhden valitun tietoelementin pohjana olevia rivejä tai käyttää **Näytä tiedot** tekstimuotoisten versioiden visualisoinnissa käytettyjen arvojen näyttämiseksi. Toimintojen **Näytä tietueet** ja **Näytä tiedot** käyttöön liittyy joitakin rajoituksia, joita käsitellään tämän artikkelin lopussa.

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>Näytä tiedot -toiminnon käyttäminen Power BI Desktopissa
**Näytä tiedot** -painike sijaitsee **Tiedot/poraudu** -välilehdellä **Visualisointityökalut** -osassa valintanauhaa.

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

Voit myös käyttää **Näytä tiedot** -painiketta napsauttamalla visualisointia hiiren oikealla painikkeella ja valitsemalla sitten **Näytä tiedot** esiin tulevasta valikosta.

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> Sinun pitää siirtää hiiri visualisoinnin arvopisteen päälle, jotta hiiren kakkospainikkeen valikko olisi käytettävissä.
> 
> 

Kun valitset **Näytä tiedot**, **Power BI Desktop** keskittyy valitsemaasi visualisointiin ja tietoihin, ja käyttää alustan tilan visualisoinnin ja datan tekstiesityksen näyttämiseksi. Visualisointi näkyy piirtoalustan yläosassa, ja tiedot näytetään alaosassa seuraavassa kuvassa esitetyllä tavalla. Tämä on *vaakasuuntainen* näkymä.

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

Voit myös vaihtaa *pystysuuntaiseen näkymään* (tai takaisin *vaakanäkymään*) valitsemalla kuvake oikeassa yläkulmassa.

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

Voit siirtyä raporttiin valitsemalla **< Takaisin raportin** piirtoalustan vasemmasta yläkulmasta.

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>Näytä tietueet -toiminnon käyttäminen Power BI Desktopissa
Voit myös keskittyä yhden tietoelementin visualisointiin ja porautua sen pohjana oleviin tietoihin. Kun visualisointi on valittu, on olemassa kaksi tapaa käyttää **Näytä tietueet** -toimintoa. Voit ottaa käyttöön **Näytä tietueet** -vaihtopainikkeen **Tiedot/poraudu** -valintanauhasta ja napsauta sitten tietoelementtiä tai napsauta tietoelementtiä hiiren kakkospainikkeella ja valitse **Näytä tietueet** esiin tulevasta valikosta.

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> Jos valittu visualisointi ei tue **Näytä tietueet** -toimintoa, valintanauhan painike näkyy harmaana.
> 
> 

Kun **Näytä tietueet** on valittuna, **Power BI Desktop** keskittyy yksittäiseen tietoelementtiin ja käyttää piirtoalustan aluetta kyseisen elementin tietojen näyttämiseen seuraavassa kuvassa esitetyllä tavalla.

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

> [!NOTE]
> Et voi tallentaa muutoksia tiedoista, joita tarkastellaan (tai joita käyttäjät muokkaavat) **Näytä tietueet** -toiminnossa raportin näkemiseksi.

Voit siirtyä raporttiin valitsemalla **< Takaisin raportin** -painike piirtoalustan vasemmasta yläkulmasta.

## <a name="limitations"></a>Rajoitukset
Joitakin rajoituksia on otettava huomioon käytettäessä toimintoja **Näytä tiedot** tai **Näytä tietueet**:

* Vain seuraavia visualisointityyppejä tuetaan:
  * **Palkki**
  * **Sarake**
  * **Kartta**
  * **Puukartta**
  * **Täytetty kartta**
  * **Ympyräkaavio**
  * **Ympyrä**
  * **Suppilo**
* Et voi käyttää **Näytä tietueet** -toimintoa, kun visualisointi käyttää laskettua mittayksikköä
* Et voi käyttää **Näytä tietueet** -toimintoa, kun olet yhteydessä MD-malliin

## <a name="next-steps"></a>Seuraavat vaiheet
**Power BI Desktop** sisältää erilaisia ominaisuuksia raportin muotoiluun ja tietojen hallintatoimintoihin. Tutustu seuraaviin resursseihin ja niiden muutamiin esimerkkeihin:

* [ Ryhmittely ja lokeroiminen Power BI Desktopissa](desktop-grouping-and-binning.md)
* [Käytä ruudukkoa, Kohdista ruudukkoon, Z-järjestys, Tasaus ja jakelu Power BI Desktop-raporteissa](desktop-gridlines-snap-to-grid.md)

