---
title: Tietojen ja tietueiden näyttäminen Power BI Desktop -visualisoinneissa
description: Power BI Desktopin ominaisuuksien ”Näytä tiedot” ja ”Näytä tietueet” käyttäminen yksityiskohtiin pääsemiseksi
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 66fe4a9eb109565108cd150369b2260a9d3e1d06
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83334357"
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Power BI Desktopin ominaisuuksien ”Näytä tiedot” ja ”Näytä tietueet” käyttäminen
**Power BI Desktopissa** voit syventyä minkä tahansa visualisoinnin tietoihin ja nähdä pohjana olevien tietojen tekstiesityksen tai yksittäiset tietueet valituista visualisoinneista. Näitä ominaisuuksia kutsutaan joskus nimellä *napsauttamalla tarkasteltava raportti* tai *alirakenneraportti* tai *alirakenneraporttien yksityiskohtien tiedot*.

Voit käyttää **Näytä tiedot** -toimintoa yhden valitun tietoelementin pohjana olevien rivien tarkastelemiseksi tai käyttää **Näytä tietueet** -toimintoa yhden valitun tietueen tai arvopisteen kaikkien tietojen näyttämiseksi. 

![Näytä tiedot ja Näytä tietueet](media/desktop-see-data-see-records/see-data-record.png)

>[!IMPORTANT]
>**Näytä tiedot** ja **Näytä tietueet** tukevat vain seuraavia visualisointityyppejä:
>  - Palkkikaavio
>  - Pylväskaavio
>  - Rengaskaavio
>  - Täytetty kartta
>  - Suppilo
>  - Kartta
>  - Ympyräkaavio
>  - Puukartta

## <a name="use-see-data-in-power-bi-desktop"></a>Näytä tiedot -toiminto Power BI Desktopissa

**Näytä tiedot** näyttää visualisoinnin pohjana olevat tiedot. **Näytä tiedot** -painike ilmestyy **Tiedot/poraudu** -välilehdelle valintanauhan **Visualisointityökalut** -osaan, kun visualisointi valitaan.

![Näytä tiedot valintanauhassa](media/desktop-see-data-see-records/see-data1.png)

Näet tiedot myös painamalla hiiren kakkospainiketta visualisoinnissa ja valitsemalla sitten **Näytä tiedot** näkyviin tulevasta valikosta, tai valitsemalla **Lisää vaihtoehtoja** (...) visualisoinnin oikeassa yläkulmassa ja valitsemalla sitten **Näytä tiedot**.

![Näytä tiedot napsauttamalla hiiren kakkospainikkeella](media/desktop-see-data-see-records/see-data2.png)&nbsp;&nbsp;![Näytä tiedot Lisää vaihtoehtoja](media/desktop-see-data-see-records/see-data3.png)

> [!NOTE]
> Sinun pitää siirtää hiiri visualisoinnin arvopisteen päälle, jotta hiiren kakkospainikkeen valikko olisi käytettävissä.

Kun valitset **Näytä tiedot** tai **Näytä tiedot**, Power BI Desktop -pohjassa näkyvät sekä tietojen visualisointi että tietojen tekstiesitys. *Vaakasuuntaisessa näkymässä* visualisointi näkyy pohjan yläosassa ja tiedot näkyvät alaosassa. 

![Vaakasuuntainen näkymä](media/desktop-see-data-see-records/see-data4a.png)

Voit myös vaihdella *pystysuuntaiseen näkymän* ja vaakasuuntaisen näkymän välillä valitsemalla kuvakkeen pohjan oikeassa yläkulmassa.

![Pystysuuntaisen näkymän valitsin](media/desktop-see-data-see-records/see-data4.png)

Voit siirtyä raporttiin valitsemalla **< Takaisin raporttiin** pohjan vasemmasta yläkulmasta.

![Takaisin raporttiin](media/desktop-see-data-see-records/see-data5.png)

## <a name="use-see-records-in-power-bi-desktop"></a>Näytä tietueet -toiminnon käyttäminen Power BI Desktopissa

Voit myös keskittyä yhden tietueen visualisointiin ja porautua sen pohjana oleviin tietoihin. Jos haluat käyttää **Näytä tietueet** -toimintoa, valitse visualisointi ja valitse sitten **Näytä tietueet** **Tiedot/poraudu** -välilehdessä valintanauhan **Visualisointityökalut** -osassa, ja valitse sitten arvopiste tai rivi visualisoinnissa. 

![Näytä tietueet valintanauhassa](media/desktop-see-data-see-records/see-record1.png)

> [!NOTE]
> Jos **Näytä tietueet** -painike on poistettu käytöstä ja himmennettynä valintanauhassa, se tarkoittaa, ettei valittu visualisointi tue **Näytä tietueet** -toimintoa.

Voit myös napsauttaa tietoelementtiä hiiren kakkospainikkeella ja valita **Näytä tietueet** näkyviin tulevasta valikosta.

![Näytä tietueet napsauttamalla hiiren kakkospainiketta](media/desktop-see-data-see-records/see-record2.png)

Kun valitset tietoelementiksi **Näytä tietueet**, Power BI Desktop -pohjassa näkyvät kaikki valittuun elementtiin liittyvät tiedot. 

![](media/desktop-see-data-see-records/see-record3.png)

Voit siirtyä raporttiin valitsemalla **< Takaisin raporttiin** pohjan vasemmasta yläkulmasta.

![](media/desktop-see-data-see-records/see-record4.png)

> [!NOTE]
>**Näytä tietueet** -toiminnolla on seuraavat rajoitukset:
> - Et voi muuttaa tietoja **Näytä tietueita** -näkymässä ja tallentaa niitä takaisin raporttiin.
> - Et voi käyttää **Näytä tietueet** -toimintoa, kun visualisointi käyttää laskettua mittaria.
> - Et voi käyttää **Näytä tietueet** -toimintoa, kun olet yhteydessä reaaliaikaiseen MD-malliin.

## <a name="next-steps"></a>Seuraavat vaiheet
**Power BI Desktop** sisältää erilaisia ominaisuuksia raportin muotoiluun ja tietojen hallintatoimintoihin. Tutustu seuraaviin resursseihin ja niiden muutamiin esimerkkeihin:

* [ Ryhmittely ja lokeroiminen Power BI Desktopissa](desktop-grouping-and-binning.md)
* [Käytä ruudukkoa, Kohdista ruudukkoon, Z-järjestys, Tasaus ja jakelu Power BI Desktop-raporteissa](desktop-gridlines-snap-to-grid.md)

