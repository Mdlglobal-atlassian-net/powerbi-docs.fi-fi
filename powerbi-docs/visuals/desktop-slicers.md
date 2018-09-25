---
title: Osittajien käyttäminen Power BI Desktopissa
description: Voit käyttää osittajia Power BI Desktopissa raporttien suodattamiseen, korostamiseen ja mukauttamiseen
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 161ea8f20db36c129787e84242ea002980d0f8dd
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565862"
---
# <a name="using-slicers-power-bi-desktop"></a>Osittajien käyttäminen Power BI Desktopissa

Voit käyttää **osittajaa** **Power BI Desktopissa** raporttisivun visualisointien tulosten suodattamiseen. Osittajilla voit helposti säätää käytettävää suodatinta käsittelemällä itse osittajaa. Voit myös määrittää asetuksia siitä, miten osittaja näkyy ja miten sitä käsitellään. Seuraavassa kuvassa näkyy osittaja, jossa sen avattava *tyyppi*-valikko on näkyvissä. 

![osittajat Desktopissa](./media/desktop-slicers/desktop-slicers_01.png)

Osittaja voidaan näyttää jollakin seuraavista tyypeistä:

* Luettelo
* Avattava valikko
* Välillä
* Pienempi tai yhtä suuri kuin
* Suurempi tai yhtä suuri kuin

Voit lisätä osittajan raporttiin napsauttamalla **osittaja**-visualisointia **Visualisoinnit**-ruudussa.

![osittajan visuaalinen tyyppi](./media/desktop-slicers/desktop-slicers_02.png)

Osittajat toimivat samalla tavalla sekä **Power BI Desktopissa** että **Power BI -palvelussa**. Osittajien käyttämisestä on erillinen artikkeli: [Osittajat Power BI -palvelussa](power-bi-visualization-slicers.md).

## <a name="synchronize-slicers-across-report-pages"></a>Osittajien synkronointi raporttisivuilla

Voit synkronoida osittajat useilla raporttisivuilla **Power BI Desktopissa**. Jos haluat synkronoida osittajat, valitse valintanauhan **Näytä**-ruudusta **Synkronoi osittajat**. Kun synkronoit osittajat, näkyviin tulee **Synkronoi osittajat** -ruutu seuraavan kuvan mukaisesti.

![näytä synkronoi osittajat -ruutu](./media/desktop-slicers/desktop-slicers_03.png)

**Synkronoi osittajat** -ruudussa voit määrittää, miten osittaja synkronoidaan raportin sivuilla. Voit määrittää, **käytetäänkö** kutakin osittajaa kullakin yksittäisellä raporttisivulla ja **näkyykö** osittaja kullakin yksittäisellä raporttisivulla.

Voit esimerkiksi sijoittaa osittajan raportin **sivulle 2** seuraavan kuvan mukaisesti. Voit sen jälkeen valita, *käytetäänkö* osittajaa kullakin valitulla sivulla ja *näkyykö* osittaja kullakin valitulla sivulla raportissa. Voit käyttää näistä mitä tahansa yhdistelmää kussakin osittajassa. 

![synkronoi osittajat](./media/desktop-slicers/desktop-slicers_04.png)

Ruudun **Lisää kaikkiin** -linkin käyttäminen ottaa valitun osittajan käyttöön raportin kaikilla sivuilla.


Huomaa, että **Synkronoi osittajat** -ruudussa näkyvät valinnat koskevat vain *valittua osittajaa*. Voit käyttää useita osittajia eri sivuilla ja määrittää ruudun avulla, miten kutakin osittajaa käytetään raportin eri sivuilla. 

Vaikka osittajien valinta voidaan synkronoida, muita valintoja, kuten tyyliä, muokkausta ja poistoa, *ei* synkronoida. 

## <a name="advanced-options-for-slicers"></a>Osittajien lisäasetukset

Voit myös käyttää **ryhmänimeä** osittajien kokoelmaan **Synkronoi osittajat** -ruudun **Lisäasetukset**-osasta. Samaan ryhmään kuuluvat osittajat voidaan synkronoida usealle sivulle. 

![osittajien ryhmänimi](./media/desktop-slicers/desktop-slicers_05.png)

Tämän ominaisuuden avulla voit luoda synkronoitavan mukautettujen osittajien ryhmän. Voit vaihtaa oletusnimen haluamaksesi nimeksi. 

Ryhmänimen avulla voit käyttää osittajia joustavasti. Voit luoda erillisiä ryhmiä, joiden avulla samaa kenttää käyttävät osittajat synkronoidaan tai joiden avulla voit sijoittaa eri kenttiä käyttävät osittajat samaan ryhmään. 


## <a name="next-steps"></a>Seuraavat vaiheet

Voit olla kiinnostunut myös seuraavista artikkeleista:

* [Osittajat Power BI -palvelussa](power-bi-visualization-slicers.md)
* [Numeerisen alueen osittajan käyttö Power BI Desktopissa](../desktop-slicer-numeric-range.md)
* [Suhteellisen päivämääräosittajan ja -suodattimen käyttö Power Bi Desktopissa](desktop-slicer-filter-date-range.md)

