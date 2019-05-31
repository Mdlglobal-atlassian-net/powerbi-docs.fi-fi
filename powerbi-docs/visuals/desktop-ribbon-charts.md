---
title: Nauhakaavioiden käyttäminen Power BI:ssä
description: Nauhakaavioiden luominen ja käyttäminen Power BI -palvelussa ja Power BI Desktopissa
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/30/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 08a2de32b092ba24b66ddd9f173be1eaea8819ab
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61394461"
---
# <a name="use-ribbon-charts-in-power-bi"></a>Nauhakaavioiden käyttäminen Power BI:ssä
Voit käyttää nauhakaavioita tietojen visualisointiin ja selvittääksesi nopeasti, millä tietoluokalla on korkein sija (suurin arvo). Nauhakaaviot esittävät luokkamuutoksen tehokkaasti, koska korkein sija (suurin arvo) näkyy aina ylimpänä kullakin ajanjaksolla. 

![nauhakaavio](media/desktop-ribbon-charts/ribbon-charts_01.png)

## <a name="create-a-ribbon-chart"></a>Nauhakaavion luominen
Avaa seuraamista varten [Jälleenmyyntianalyysin malliraportti](../sample-retail-analysis.md). 

1. Luo nauhakaavio valitsemalla **Nauhakaavio** **Visualisoinnit**-ruudusta.

    ![visualisointimallit](media/desktop-ribbon-charts/ribbon-charts_02.png)

    Nauhakaavioissa tietoluokat yhdistetään visualisoidun aikajatkumon ajan nauhoilla, joten näet helposti, miten tietty luokka sijoittuu kaavion koko x-akselille (yleensä aikajana).

2. Valitse kentät **Akseli**, **Selite** ja **Arvo**.  Tässä esimerkissä valitsemme seuraavat kentät: **Päivämäärä**, **Myynti** ja **Tämän vuoden myynti**.  

    ![valitut kentät](media/desktop-ribbon-charts/power-bi-ribbon-values.png)

    Koska tietojoukko sisältää vain yhden vuoden tiedot, poistimme myös **Vuosi**-kentän **akselista**. 

3. Valintanauhan kaaviossa näytetään sijoitus joka toiselle kuukaudelle. Näet, miten sijoitus muuttuu ajan myötä.  Esimerkiksi Koti-luokka siirtyy kolmannesta neljänneksi ja takaisin kolmanneksi. Junioreiden luokka siirtyy kolmannesta viidenneksi heinäkuussa. 

    ![nauhakaavio](media/desktop-ribbon-charts/power-bi-ribbon.png)

## <a name="format-a-ribbon-chart"></a>Nauhakaavion muotoileminen
Kun luot nauhakaavion, voit käyttää **Muotoilu**-osan muotoiluasetuksia **Visualisoinnit**-ruudussa. Nauhakaavioiden muotoiluasetukset ovat samankaltaisia kuin pinotussa pylväskaaviossa, mutta ne sisältävät lisäksi nauhoihin liittyviä muotoiluasetuksia.

![nauhamalli Visualisointi-ruudulla](media/desktop-ribbon-charts/power-bi-format-ribbon.png)

Voit säätää asetuksia näillä nauhakaavioiden muotoiluasetuksilla.

* **Välistys**-asetuksella voit asettaa, kuinka paljon tilaa nauhojen väliin jätetään. Luku on prosenttiosuus sarakkeen enimmäiskorkeudesta.
* **Täsmäytä sarjan väri** -asetuksella voit sovittaa nauhojen värin sarjan väriin. Kun asetus on **pois käytöstä**, nauhat näkyvät harmaina.
* **Läpinäkyvyys** määrittää, miten läpinäkyviä nauhat ovat. Oletusasetus on 30.
* **Reuna**-asetuksella voit sijoittaa tumman reunaviivan nauhojen ylä- ja alareunoihin. Reunat ovat oletusarvoisesti pois käytöstä.

Koska valintanauhan kaaviossa ei ole y-akselin selitteitä, sinun kannattaa ehkä lisätä arvopisteiden otsikot. Valitse Muotoilu-ruudussa **Arvopisteiden otsikot**. 

![arvopisteiden otsikoiden muotoiluasetukset](media/desktop-ribbon-charts/power-bi-labels.png)

Määritä arvopisteiden otsikoiden muotoiluasetukset.  Tässä esimerkissä määritämme tekstin väriksi valkoisen, desimaalien määräksi nollan ja näyttöyksiköiksi tuhannet. 

![nauhamalli Visualisointi-ruudulla](media/desktop-ribbon-charts/power-bi-data-labels.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Pistekaaviot ja kuplakaaviot Power BI:ssä](power-bi-visualization-scatter.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)