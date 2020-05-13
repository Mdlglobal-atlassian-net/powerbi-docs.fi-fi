---
title: Ryhmittely ja lokeroiminen Power BI Desktopissa
description: Opi elementtien ryhmittely ja lokeroiminen Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/18/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 525f7bf4c967722d8f98a9184127bc8c7907cea1
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83309471"
---
# <a name="use-grouping-and-binning-in-power-bi-desktop"></a>Ryhmittely ja lokeroiminen Power BI Desktopissa
Kun Power BI Desktop luo visualisointeja, se kokoaa tiedot lohkoiksi (tai ryhmiksi), jotka perustuvat pohjalla olevien tietojen sisältämiin arvoihin. Useimmiten esitys on kunnossa, mutta joskus saatat haluta tarkentaa miten kyseiset lohkot esitetään. Saatat esimerkiksi haluta sijoittaa kolme tuoteluokkaa yhteen suurempaan luokkaan (yksi *ryhmä*). Tai haluat ehkä nähdä myyntiluvut yhdessä lokerossa lukuna 1 000 000 euroa 923 983 euron suuruisten lohkojen sijaan.

Power BI Desktopissa voit *ryhmitellä* arvopisteet auttamaan sinua tarkastelemaan, analysoimaan ja tutkiman visualisointien tietoja ja trendejä. Voit myös määrittää *lokeron koon*, jos haluat sijoittaa arvot yhtä suuriin ryhmiin, joiden avulla voit paremmin visualisoida tietoja merkitsevällä tavalla. Tätä toimintoa kutsutaan usein *lokeroimiseksi*.

## <a name="using-grouping"></a>Ryhmittelyn käyttö
Jos haluat käyttää ryhmittelyä, valitse vähintään kaksi visualisoinnin elementtiä käyttämällä näppäinyhdistelmää CTRL + NAPSAUTUS useiden elementtien valintaan. Napsauta sitten jotakin monivalintaelementtiä hiiren kakkospainikkeella ja valitse pikavalikosta **Ryhmittele**.

![Ryhmittele-komento, kaavio, ryhmittely, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_1.png)

Kun ryhmä on luotu, se lisätään **Selite**-säiliöön visualisointia varten. Ryhmä näkyy myös **Kentät**-luettelossa.

![Selite- ja Kentät-luettelot, ryhmittely, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_2.png)

Kun sinulla on ryhmä, voit helposti muokata kyseisen ryhmän jäseniä. Napsauta hiiren kakkospainikkeella **Selite**-säilön tai **Kentät**-luettelon kenttää ja valitse **Muokkaa ryhmiä**.

![Muokkaa ryhmiä -komento, Selite- ja Kentät-luettelot, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_3.png)

**Ryhmät**-ikkunassa voit luoda uusia ryhmiä tai muokata olemassa olevia ryhmiä. Voit myös *nimetä uudelleen* minkä tahansa ryhmän. Kaksoisnapsauta ryhmän otsikkoa **Ryhmät ja jäsenet** -ruudussa ja kirjoita sitten uusi nimi.

Voit tehdä ryhmillä kaikenlaista. Voit lisätä kohteita **Arvot, joiden ryhmittely on purettu** -luettelosta uuteen ryhmään tai yhdeksi olemassa olevaksi ryhmäksi. Jos haluat luoda uuden ryhmän, valitse kaksi tai useampi kohde (käyttäen painikeyhdistelmää CTRL + napsautus) **Arvot, joiden ryhmittely on purettu** -ruutuun ja valitse sitten **Ryhmä** -painiketta kyseisen ruudun alta.

Voit lisätä puretun arvon aiemmin luotuun ryhmään: valitse jokin **purettu arvo** ja valitse sitten aiemmin luotu ryhmä, johon haluat lisätä arvon ja valitse **Ryhmä**-painike. Jos haluat poistaa tietoyksikön ryhmästä, valitse se **Ryhmät ja jäsenet** -ruudusta ja valitse sitten **Pura ryhmittely**. Voit myös siirtää ryhmittelemättömiä luokkia **Muut**-ryhmään tai jättää ne ryhmittelemättä.

![Ryhmät-valintaikkuna, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_4.png)

> [!NOTE]
> Voit luoda ryhmiä mille tahansa kentälle kohdassa **Kentät** ilman monivalintaa olemassa olevasta visualisoinnista. Napsauta kenttää hiiren kakkospainikkeella ja valitse **Uusi ryhmä** esiin tulevasta valikosta.

## <a name="using-binning"></a>Lokeroinnin käyttäminen
Voit määrittää numeeristen ja aika-kenttien lokeron koon **Power BI Desktopissa.** Voit käyttää lokeroimisen Power BI Desktopissa näkyvien tietojen oikeaan kokoon saattamiseksi.

Voit käyttää lokeron kokoa napsauttamalla hiiren kakkospainikkeella **Kenttä** ja valitsemalla **Uusi ryhmä**.

![Uusi ryhmä -komento, Kentät-luettelo, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_5.png)

**Ryhmät**-valintaikkunassa asetetaan haluttu **lokeron koko**.

![Lokeron koko, Ryhmät-valintaikkuna, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_6.png)

Kun valitset **OK** huomaat, että uusi kenttä tulee näkyviin **Kentät**-ruutuun **(lokerot)** liitettynä. Sitten voit vetää tämän kentän alustalle lokeron koon käyttämiseksi visualisoinnissa.

![Vedä lokerokenttä pohjaan, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_7.png)

Jos haluat nähdä *lokeroimisen* käytännössä, katso tämä [video](https://www.youtube.com/watch?v=BRvdZSfO0DY).

Tässä kaikki *ryhmittelystä* ja *lokeroimisesta*, kun haluat varmistaa visualisointien näkymisen raporteissa juurin niin kuin haluat niiden näkyvän.
