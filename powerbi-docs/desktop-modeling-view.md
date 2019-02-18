---
title: Mallintamisnäkymän käyttäminen Power BI Desktopissa (esikatselu)
description: Mallintamisnäkymän avulla voit tarkastella monimuotoisia tietojoukkoja visuaalisessa muodossa Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: ccb78c8d22fdb7b9fecbb202dca488c44d36a15d
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/13/2019
ms.locfileid: "56216305"
---
# <a name="modeling-view-in-power-bi-desktop-preview"></a>Mallintamisnäkymä Power BI Desktopissa (esikatselu)

**Mallintamisnäkymän** avulla **Power BI Desktopissa** voit tarkastella ja käsitellä monimuotoisia tietojoukkoja, jotka sisältävät useita taulukoita. Voit tehdä seuraavia asioita mallintamisnäkymässä:


## <a name="enabling-the-modeling-view-preview-feature"></a>Mallintamisnäkymän esikatselutoiminnon ottaminen käyttöön

Mallintamisnäkymä-ominaisuus on esikatseluvaiheessa. Sen täytyy olla käytössä **Power BI Desktopissa**. Voit ottaa mallintamisnäkymän käyttöön valitsemalla **Tiedosto > Vaihtoehdot ja asetukset > Vaihtoehdot > Esikatselutoiminnot** ja valitsemalla sitten **Mallintamisnäkymä**-valintaruudun seuraavassa kuvassa esitetyn mukaisesti.

![Mallintamisnäkymän esikatselutoiminnon ottaminen käyttöön Power BI Desktopissa](media/desktop-modeling-view/modeling-view_01.png)

Esikatselutoiminnon käyttöönotto edellyttää **Power BI Desktopin** käynnistämistä uudelleen. Saat tästä kehotteen. 

![Ota esikatselutoiminnot käyttöön käynnistämällä Power BI Desktop uudelleen](media/desktop-modeling-view/modeling-view_01b.png)

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
* [Yhdistelmämallit Power BI Desktopissa (esikatselu)](desktop-composite-models.md)
* [Tallennustilan tila Power BI Desktopissa (esikatselu)](desktop-storage-mode.md)
* [Moni-moneen-yhteydet Power BI Desktopissa (esikatselu)](desktop-many-to-many-relationships.md)


DirectQuery-artikkeleita:

* [DirectQueryn käyttäminen Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet Power BI:ssä](desktop-directquery-data-sources.md)
