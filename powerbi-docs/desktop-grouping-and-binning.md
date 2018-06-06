---
title: Ryhmittely ja lokeroiminen Power BI Desktopissa
description: Opi elementtien ryhmittely ja lokeroiminen Power BI Desktopissa
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
ms.date: 01/19/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: ec663e61a6cb5281500e605fda35ecb81d7b71a2
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973717"
---
# <a name="use-grouping-and-binning-in-power-bi-desktop"></a>Ryhmittely ja lokeroiminen Power BI Desktopissa
Kun **Power BI Desktop** luo visualisointeja, se kokoaa yhteen tietosi lohkoiksi (tai **ryhmiksi**) perustuen arvoihin, jotka löytyvät pohjana olevista tiedoista. Useimmiten esitys on kunnossa, mutta joskus saatat haluta tarkentaa miten kyseiset lohkot esitetään. Saatat esimerkiksi haluta sijoittaa kolme tuoteluokkaa yhteen suurempaan luokkaan (yksi *ryhmä*). Tai haluat ehkä nähdä myyntiluvut yhdessä lokerossa lukuna 1 000 000 euroa tasaisesti jaetun 923,983 euron sijaan.

Power BI Desktopissa voit **ryhmitellä** arvopisteet auttamaan sinua tarkastelemaan, analysoimaan ja tutkiman visualisointien tietoja ja trendejä. Voit myös määrittää **lokeron koon**, mitä kutsutaan usein **lokeroimiseksi**, jos haluat sijoittaa arvot yhtä suuriin ryhmiin, joiden avulla voit paremmin visualisoida tietoja merkitsevällä tavalla.

### <a name="using-grouping"></a>Ryhmittelyn käyttö
Jos haluat käyttää **ryhmittelyä**, valitse vähintään kaksi visualisoinnin elementtiä käyttämällä näppäinyhdistelmää CTRL + NAPSAUTUS elementtien monivalintaan. Napsauta seuraavaksi hiiren kakkospainikkeella monivalintaelementtejä ja valitse *Ryhmä* esiin tulevasta valikosta.

![](media/desktop-grouping-and-binning/grouping-binning_1.png)

Kun ryhmä on luotu, se lisätään **Selite**-säiliöön visualisointia varten, ja se näkyy myös **kentät** luettelossa.

![](media/desktop-grouping-and-binning/grouping-binning_2.png)

Kun sinulla on ryhmä, voit helposti muokata kyseisen ryhmän jäseniä napsauttamalla hiiren kakkospainikkeella kenttää **Selite**-säilöstä tai **Kentät**-luettelosta ja valitsemalla *Muokkaa ryhmiä*.

![](media/desktop-grouping-and-binning/grouping-binning_3.png)

Esiin tulevassa **Ryhmät**-ikkunassa voit luoda uusia ryhmiä tai muokata olemassa olevia ryhmiä. Voit myös *nimetä uudelleen* minkä tahansa ryhmän kaksoisnapsauttamalla **Ryhmä** -otsikkoa kohdasta **Ryhmät ja jäsenet** ja kirjoittamalla uuden nimen.

Voit tehdä tässä ikkunassa ryhmillä kaikenlaista. Voit lisätä kohteita **Arvot, joiden ryhmittely on purettu** -luettelosta uuteen ryhmään tai yhdeksi olemassa olevaksi ryhmäksi. Jos haluat luoda uuden ryhmän, valitse kaksi tai useampi kohde (käyttäen painikeyhdistelmää CTRL + napsautus) **Arvot, joiden ryhmittely on purettu** -ruutuun ja napsauta sitten **Ryhmä** -painiketta kyseisen ruudun alta.

Voit lisätä puretun arvon aiemmin luotuun ryhmään: valitse purettu arvo ja valitse sitten aiemmin luotu ryhmä, johon haluat lisätä sen ja valitse **Ryhmä**-painike. Jos haluat poistaa tietoyksikön ryhmästä, valitse se **Ryhmät ja jäsenet** -ruudusta ja napsauta sitten **Pura ryhmittely**. Voit myös valita, onko ryhmittelemättömät luokat sijoitettava ryhmään **Muut** vai pitääkö niiden jäädä puretuiksi.

![](media/desktop-grouping-and-binning/grouping-binning_4.png)

> [!NOTE]
> Voit luoda ryhmiä mille tahansa kentälle kohdassa **Kentät** ilman monivalintaa olemassa olevasta visualisoinnista. Napsauta kenttää hiiren kakkospainikkeella ja valitse **Ryhmä** esiin tulevasta valikosta.
> 
> 

### <a name="using-binning"></a>Lokeroinnin käyttäminen
Voit määrittää numeeristen ja aika-kenttien lokeron koon **Power BI Desktopissa.** Voit käyttää lokeroimisen **Power BI Desktopissa** näkyvien tietojen oikeaan kokoon saattamiseksi.

Voit käyttää lokeron kokoa napsauttamalla hiiren kakkospainikkeella **Kenttä** ja valitsemalla **Ryhmät**.

![](media/desktop-grouping-and-binning/grouping-binning_5.png)

**Ryhmät**-ikkunassa asetetaan haluttu **lokeron koko**.

![](media/desktop-grouping-and-binning/grouping-binning_6.png)

Kun valitset **OK** huomaat, että uusi kenttä tulee näkyviin **Kentät**-ruutuun *(lokerot)* liitettynä. Sitten voit vetää tämän kentän alustalle lokeron koon käyttämiseksi visualisoinnissa.

![](media/desktop-grouping-and-binning/grouping-binning_7.png)

Jos haluat nähdä **lokeroimisen** käytännössä, katso tämä [video](https://www.youtube.com/watch?v=BRvdZSfO0DY).

Tässä kaikki **ryhmittelystä** ja **lokeroimisesta**, kun haluat varmistaa visualisointien näkymisen raporteissa juurin niin kuin haluat niiden näkyvän.

