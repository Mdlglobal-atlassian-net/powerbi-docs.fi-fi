---
title: Nauhakaavioiden käyttäminen Power BI:ssä
description: Nauhakaavioiden luominen ja käyttäminen Power BI Desktopissa
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e6044f3a2cfdbfc40d0497ebde25780336dc1dc4
ms.sourcegitcommit: d04b9e1426b8544ce16ef25864269cc43c2d9f7b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "71715495"
---
# <a name="use-ribbon-charts-in-power-bi"></a>Nauhakaavioiden käyttäminen Power BI:ssä

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Voit käyttää nauhakaavioita tietojen visualisointiin ja selvittääksesi nopeasti, millä tietoluokalla on korkein sija (suurin arvo). Nauhakaaviot esittävät luokkamuutoksen tehokkaasti, koska korkein sija (suurin arvo) näkyy aina ylimpänä kullakin ajanjaksolla. 

![nauhakaavio](media/desktop-ribbon-charts/ribbon-charts-01.png)

## <a name="prerequisites"></a>Edellytykset

Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.

## <a name="create-a-ribbon-chart"></a>Nauhakaavion luominen

1. Luo nauhakaavio valitsemalla **Nauhakaavio** **Visualisoinnit**-ruudusta.

    ![visualisointimallit](media/desktop-ribbon-charts/power-bi-template.png)

    Nauhakaavioissa tietoluokat yhdistetään visualisoidun aikajatkumon ajan nauhoilla, joten näet helposti, miten tietty luokka sijoittuu kaavion koko x-akselille (yleensä aikajana).

2. Valitse kentät **Akseli**, **Selite** ja **Arvo**.  Tässä esimerkissä valitsemme seuraavat kentät: **Myymälä** > **Avauspäivä**, **Kohde** > **Luokka** ja **Myynti** > **Tämän vuoden myynti** > **Arvo**.  

    ![valitut kentät](media/desktop-ribbon-charts/power-bi-ribbon-values.png)

    Koska tietojoukko sisältää vain yhden vuoden tiedot, poistimme myös **Vuosi**- ja **Vuosineljännes**-kentät **akselista**.

3. Valintanauhan kaaviossa näytetään sijoitus joka toiselle kuukaudelle. Näet, miten sijoitus muuttuu ajan myötä. Esimerkiksi Koti-luokka siirtyy toisesta viidenteen helmikuusta maaliskuuhun.

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

Määritä arvopisteiden otsikoiden muotoiluasetukset. Tässä esimerkissä määritämme tekstin väriksi valkoisen ja näyttöyksiköiksi tuhannet.

![nauhamalli Visualisointi-ruudulla](media/desktop-ribbon-charts/power-bi-data-labels.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Pistekaaviot ja kuplakaaviot Power BI:ssä](power-bi-visualization-scatter.md)

[Visualisointityypit Power BI:ssä](power-bi-visualization-types-for-reports-and-q-and-a.md)
