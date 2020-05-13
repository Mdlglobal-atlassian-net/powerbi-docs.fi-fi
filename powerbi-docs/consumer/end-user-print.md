---
title: Tulostaminen Power BI -palvelusta
description: Koontinäytön, ruudun tai raporttisivun tulostaminen Power BI -palvelusta.
author: mihart
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 03/12/2020
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: 8c91e2a07143a6355b7049e80cbdc3e4ba906013
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83145375"
---
# <a name="printing-from-the-power-bi-service"></a>Power BI -palvelusta tulostaminen

[!INCLUDE[consumer-appliesto-yynn](../includes/consumer-appliesto-yynn.md)]
## <a name="what-can-be-printed"></a>Mitä voit tulostaa
[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Power BI -palvelusta voit tulostaa koko koontinäytön, koontinäytön yksittäisen ruudun, raporttisivun tai raportin visualisoinnin. Jos raportissasi on useampi kuin yksi sivu, sinun on tulostettava jokainen sivu erikseen. 

## <a name="printing-considerations"></a>Huomioitavaa tulostamisessa

Useimmat Power BI -koontinäytöt ja -raportit luodaan raportin *suunnittelijoiden* avulla, jolloin niitä voidaan käyttää verkossa ja ne näyttävät upeilta, kun niitä tarkastellaan useissa eri laitteissa. Kun tulostat raportin, selaimesi valvoo, miltä sisältö näyttää paperilla. 

Voit säätää tulostetta selainasetusten avulla, mutta et ehkä siltikään saa haluamaasi tulosta. Harkitse [viemistä PDF-muotoon](end-user-pdf.md) ensin ja sitten PDF-tiedoston tulostamista. 

## <a name="adjust-your-browser-print-settings"></a>Selaimen tulostusasetusten säätäminen
Kun tulostat Power BI:stä, selaimesi avaa tulostusikkunan. Kunkin selaimen tulostusikkuna eroaa muista. Niissä kaikissa on kuitenkin samanlaisia asetuksia, joiden avulla voit muokata tulosteen ulkoasua. 

Seuraavassa on muutamia pikavinkkejä, joiden avulla voit muotoilla tulostetta.

   > 
1. Jos koontinäytön, raportin tai visualisoinnin leveys on suurempi kuin korkeus, harkitse **vaakasuuntaisen** asettelun käyttämistä. 

   ![Tulostuksen valintaikkuna, jossa näytetään asettelu vaakasuuntaisena](./media/end-user-print/power-bi-landscape-layout.png)

2. Jos haluat enemmän sisältöä tulostetulle sivulle, voit säätää esimerkiksi reunuksia ja skaalausta. 

    ![Tulostuksen valintaikkuna, jossa näkyy Lisää asetuksia](./media/end-user-print/power-bi-margins.png)

Testaa selaimesi asetuksia, kunnes ulkoasu on halutunlainen. Joiden selainten asetuksen mahdollistavat jopa taustagrafiikan tulostamisen. 

## <a name="print-a-dashboard"></a>Koontinäytön tulostaminen
1. Avaa koontinäyttö, jonka haluat tulostaa.
2. Valitse vasemmasta yläkulmasta Vie ja valitse sitten **Tulosta tämä sivu**.
   
    ![Koontinäytön tulostusasetus](./media/end-user-print/power-bi-dashboard-print.png)

3. Selaimen tulostusikkuna avautuu. Valitse asetukset. Esimerkiksi jos koontinäytön leveys on suurempi kuin korkeus, voit halutessasi muuttaa asettelun **vaakasuuntaiseksi**. Valitse **Tulosta**.
   
    ![Tulostuksen valintaikkuna](./media/end-user-print/power-bi-print-dash.png)

## <a name="print-a-dashboard-tile"></a>Koontinäytön yksittäisen ruudun tulostaminen
1. Avaa koontinäyttö [koko näytön tilaan](end-user-focus.md) valitsemalla yläreunan valikkopalkista koko näytön kuvake ![koko näytön kuvake](./media/end-user-print/power-bi-full-screen.png).

3. [Avaa ruutu tarkastelutilassa](end-user-focus.md) kuljettamalla osoitinta sen kohdalla kunnes **Enemmän vaihtoehtoja** (...) tulee näkyviin ja valitsemalla **Avaa tarkastelutilassa** tai kohdistuskuvake ![Kohdistuskuvake](./media/end-user-print/power-bi-focus-icon.png).
   
    ![kolmen pisteen valikko](./media/end-user-print/power-bi-menu-options.png)

4. Vie hiiren osoitin ruudun kohdalle, jolloin näkyviin tulee asetusvalikko.
   
    ![koko näytön tilan asetusvalikko](./media/end-user-print/menu-options-new.png)

4. Valitse Tulosta-kuvake ![Tulosta-kuvake](./media/end-user-print/print-icon.png).     

5. Selaimen tulostusikkuna avautuu. Valitse asetukset. Jos esimerkiksi ruutu ei mahdu sivulle, haluat ehkä muuttaa skaalauksen 75 %:iin. Valitse **Tulosta**.

    ![tulostusikkuna](./media/end-user-print/power-bi-scale.png) 

> [!TIP]
> Jos olet noudattanut kaikkia näitä vaiheita eikä ruutusi edelleenkään näy haluamallasi tavalla, kokeile seuraavaa.
> 1. Avaa tulostusikkuna ja tee tulostusasetuksiin muutoksia, joiden uskot parantavan tulostetta. Voit esimerkiksi muuttaa ulkoasua, reunuksia ja skaalausta. 
> 2. Valitse kuitenkin tulostamisen sijaan **Peruuta**. 
> 3. Käy läpi vaiheet 1–5 uudelleen. Ruutu mukautetaan uusiin tulostusikkunan asetuksiin ja on valmiina tulostamiseen.

## <a name="print-a-report-page"></a>Raporttisivun tulostaminen
Raportteja voi tulostaa yhden sivun kerrallaan.

1. Avaa raportti ja valitse **Vie** > **Tulosta** kun haluat tulostaa nykyisen raporttisivun.
   
    ![Power BI:n Tiedosto-valikko](./media/end-user-print/power-bi-report-print.png)
2. Selaimen tulostusikkuna avautuu.

3. Noudata tulostusvaiheita yllä olevassa **Koontinäytön tulostaminen** -kohdassa.
   


## <a name="print-a-report-visual"></a>Raportin yksittäisen visualisoinnin tulostaminen
1. [Avaa visualisointi tarkastelutilassa](end-user-focus.md) viemällä hiiren osoitin ruudun kohdalle ja valitsemalla kohdistuskuvake ![kohdistuskuvake](./media/end-user-print/power-bi-focus-icon.png) sen oikeasta alakulmasta.

2. Valitse vasemmasta yläkulmasta **Vie** > **Tulosta**, kun haluat tulostaa visualisoinnin.

    ![Power BI:n Tiedosto-valikko](./media/end-user-print/power-bi-report-print.png)


3. Noudata tulostusvaiheita yllä olevassa **Koontinäytön tulostaminen** -kohdassa.

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

* Kysymys: En voi tulostaa raportin kaikkia sivuja kerralla.    
* Vastaus: Totta. Raporttisivut voi tulostaa vain yksi sivu kerrallaan.
* Kysymys: En voi tulostaa PDF-muotoon.    
* Vastaus: Asetus tulee näkyviin vain silloin, jos olet ennalta määrittänyt selaimeen PDF-ohjaimen.    
* Kysymys: Se mitä näen, kun valitsen **Tulosta**, ei vastaa tässä esitettyjä kuvia.    
* Vastaus: Tulostusnäkymät vaihtelevat selaimen ja ohjelmistoversion mukaan.
* Kysymys: Tuloste ei skaalautunut oikein.  Koontinäyttö ei mahdu arkille. Muut skaalautumiseen ja paperin suuntaan liittyvät kysymykset.    
* Vastaus: Emme voi taata, että tulostettu kopio on täsmälleen samanlainen kuin Power BI ‑palvelussa näkyvä. Power BI ei voi hallita skaalausta, reunuksia, visuaalisia yksityiskohtia, paperin suuntausta ja kokoa. Kokeile mukauttaa selaimesi tulostusasetuksia. Voit mukauttaa esimerkiksi tulostussuuntaa (pysty- tai vaakasuunta), reunuksen kokoa ja skaalausta. Jos siitä ei ole apua, tutustu selaimesi ohjeisiin.      
* Kysymys: Kun tulostan koko näytön tilasta, en näe Tulosta-asetusta, kun viet hiiren osoittimen visualisoinnin päälle.   
* Vastaus: Palaa koontinäyttöön tai raporttiin oletusnäkymässä ja avaa visualisointi uudelleen tarkastelutilassa ja sitten koko näytön tilassa. 

## <a name="next-steps"></a>Seuraavat vaiheet
[Koontinäyttöjen ja raporttien jakaminen työtovereiden ja muiden kanssa](../collaborate-share/service-share-dashboards.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
