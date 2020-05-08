---
title: Mallintamisnäkymän käyttö Power BI Desktopissa
description: Mallintamisnäkymän avulla voit tarkastella monimuotoisia tietojoukkoja visuaalisessa muodossa Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: b9df4398c410f52e3d5cdd51a99a40de107f5867
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "75760878"
---
# <a name="work-with-modeling-view-in-power-bi-desktop"></a>Mallintamisnäkymän käyttö Power BI Desktopissa

**Power BI Desktopin** **mallintamisnäkymässä** voit tarkastella ja käsitellä monimuotoisia tietojoukkoja, jotka sisältävät useita taulukoita.


## <a name="using-modeling-view"></a>Mallintamisnäkymän käyttäminen

Voit käyttää mallintamisnäkymää valitsemalla mallintamisnäkymän kuvakkeen **Power BI Desktopin** vasemmasta reunasta seuraavassa kuvassa esitetyllä tavalla.

![Mallintamisnäkymän kuvake Power BI Desktopissa](media/desktop-modeling-view/modeling-view_02.png)

## <a name="creating-separate-diagrams"></a>Erillisten kaavioiden luominen

Mallintamisnäkymän avulla voit luoda mallista kaavioita, jotka sisältävät vain mallin taulukoiden alijoukon. Tämä voi tarjota selkeämmän näkymän taulukoihin, joita haluat käsitellä, ja helpottaa työskentelyä monimuotoisten tietojoukkojen parissa. Jos haluat luoda uuden kaavion vain taulukoiden alijoukolla, valitse **+** -merkki **Kaikki taulukot** -välilehden vieressä Power BI Desktop -ikkunan alaosassa.

![Luo uusi kaavio napsauttamalla +-merkkiä Välilehdet-osassa](media/desktop-modeling-view/modeling-view_03.png)

Sitten voit vetää taulukon **Kentät**-luettelosta kaavion pinnalle. Napsauta taulukkoa hiiren kakkospainikkeella ja valitse sitten **Lisää liittyvät taulukot** avautuvasta valikosta.

![Napsauta taulukkoa hiiren kakkospainikkeella ja valitse Lisää liittyvät taulukot](media/desktop-modeling-view/modeling-view_04.png)

Kun teet näin, alkuperäiseen taulukkoon liittyvät taulukot näkyvät uudessa kaaviossa. Seuraavassa kuvassa näytetään, miten liittyvät taulukot näytetään, kun olet valinnut **Lisää liittyvät taulukot** -valikkovaihtoehdon.

![Liittyvien taulukoiden näyttäminen](media/desktop-modeling-view/modeling-view_05.png)

## <a name="setting-common-properties"></a>Yhteisten ominaisuuksien määrittäminen

Voit valita useita objekteja kerralla mallintamisnäkymässä pitämällä **CTRL**-näppäintä painettuna samalla, kun valitset useita taulukoita. Kun valitset useita taulukoita, ne näkyvät korostettuina mallintamisnäkymässä. Kun useita taulukoita korostetaan, **Ominaisuudet**-ruudussa käyttöön otetut muutokset koskevat kaikkia valittuja taulukoita.

Voit esimerkiksi muuttaa [tallennustilan](desktop-storage-mode.md) useiden taulukoiden kohdalla kaavionäkymässä pitämällä **CTRL**-näppäintä painettuna, valitsemalla taulukoita ja muuttamalla sitten tallennustila-asetuksen  **Ominaisuudet**-ruudussa.

![Valitse useita taulukoita pitämällä CTRL-näppäintä painettuna ja määritä sitten yhteiset ominaisuudet kaikille valituille taulukoille](media/desktop-modeling-view/modeling-view_06.png)


## <a name="next-steps"></a>Seuraavat vaiheet

Seuraavissa artikkeleissa kerrotaan lisää tietomalleista ja kuvataan myös DirectQuery yksityiskohtaisemmin.

* [Koosteet Power BI Desktopissa (esikatselu)](desktop-aggregations.md)
* [Yhdistelmämallit Power BI Desktopissa](desktop-composite-models.md)
* [Tallennustilan tila Power BI Desktopissa (esikatselu)](desktop-storage-mode.md)
* [Moni-moneen-yhteydet Power BI Desktopissa](desktop-many-to-many-relationships.md)


DirectQuery-artikkeleita:

* [DirectQueryn käyttäminen Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet Power BI:ssä](desktop-directquery-data-sources.md)
