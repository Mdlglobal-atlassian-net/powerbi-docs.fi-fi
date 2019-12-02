---
title: Porautumisen käyttäminen Power BI Desktopissa
description: Lue, miten voit porautua tietoihin uudella raporttisivulla Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: a7b00b0cb611dd3e0921885ddaca6547fdb43fd3
ms.sourcegitcommit: 7f27b9eb0e001034e672050735ab659b834c54a3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/22/2019
ms.locfileid: "74311020"
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Porautumisen käyttäminen Power BI Desktopissa
Power BI Desktopin *porautumisen* avulla voit luoda raporttisivun, jolla keskitytään tiettyyn entiteettiin, kuten toimittajaan, asiakkaaseen tai valmistajaan. Jos haluat porautua, napsauta hiiren kakkospainikkeella arvopistettä toisella raporttisivulla ja poraudu sitten keskittyvällä sivulla: näin saat lisätietoja, jotka on suodatettu kyseisen kontekstin mukaisesti.

![Porautumisen käyttö](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Porautumisen käyttö
1. Jos haluat käyttää porautumista, luo raporttisivu, jolla on visualisointeja, jotka haluat porautumisen kohde-entiteettityypille. 

    Oletetaan, että haluat tarjota porautumisen esimerkiksi valmistajille. Tässä tapauksessa voit luoda porautumissivun, jolla on visualisointeja kokonaismyynnistä, toimitettujen yksiköiden kokonaismääristä, kategoriakohtaisista myynneistä, aluekohtaisista myynneistä ja niin edelleen. Tällä tavoin, kun kyseiselle sivulle poraudutaan, visualisointi on kohdistettu valitsemaasi valmistajaan.

2. Vedä sitten porautumissivulla **visualisointipaneelin** **Kentät-** osiossa se kenttä, jolle haluat ottaa porautumisen käyttöön, **Porautumissuodattimiin**.

    ![Porautumislähde](media/desktop-drillthrough/drillthrough_02.png)

    Kun lisäät kentän **porautumissuodattimiin**, Power BI Desktop luo automaattisesti visualisoinnin *Takaisin*-painikkeelle. Visualisointi muuttuu painikkeeksi julkaistuissa raporteissa. Käyttäjät, jotka käyttävät raporttiasi Power BI -palvelussa, voivat tämän painikkeen avulla palata raporttisivulle, jolta he tulivat.

    ![Porautumiskuva](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>Oman kuvan käyttäminen Takaisin-painikkeena    
 Koska Takaisin-painike on kuva, voit korvata kyseisen visualisoinnin kuvan visualisoinnin millä tahansa haluamallasi kuvalla. Se toimii silti oikein Takaisin-painikkeena niin, että raportin käyttäjät voivat palata alkuperäiselle sivulle. 

Jos haluat käyttää itse valitsemaasi kuvaa Takaisin-painikkeena, toimi seuraavasti:

1. Valitse **Aloitus**-välilehdeltä **Kuva**. Etsi haluamasi kuva ja sijoita se porautumissivulle.

2. Valitse uusi kuva porautumissivulla. Aseta **Muotoile kuva** -ruudussa **Toiminto**-liukusäädin asentoon **Käytössä** ja määritä sitten **Tyyppi**-arvoksi **Takaisin**. Kuva toimii nyt Takaisin-painikkeena.

    ![Lataa kuvaa ja määritä tyypiksi Takaisin](media/desktop-drillthrough/drillthrough_05.png)

    
     Käyttäjät voivat nyt napsauttaa hiiren kakkospainikkeella raporttisi arvopistettä, jolloin avautuu pikavalikko, joka tukee porautumista kyseiselle sivulle. 

    ![Porautumisvalikko](media/desktop-drillthrough/drillthrough_04.png)

    Kun raportin käyttäjä valitsee porautumisen, sivu suodatetaan näyttämään tietoja hiiren kakkospainikkeella napsautetusta arvopisteestä. Oletetaan esimerkiksi, että käyttäjä napsauttaa hiiren kakkospainikkeella arvopistettä Contososta (valmistaja) ja valitsee porautumisen. Avautuva porautumissivu on suodatettu näyttämään tietoja Contososta.

## <a name="pass-all-filters-in-drillthrough"></a>Kaikkien suodattimien siirtäminen porautumisessa

Toukokuun 2018 Power BI Desktop -versiosta alkaen voit siirtää kaikki käytetyt suodattimet porautumisikkunaan. Voit esimerkiksi valita vain tietyn tuoteluokan ja kyseiseen luokkaan suodatetut visualisoinnit ja valita sitten porautumisen. Saatat olla kiinnostunut siitä, miltä porautuminen näyttäisi kaikkien näiden suodattimien ollessa käytössä.

Jos haluat säilyttää kaikki käytetyt suodattimet, ota **Visualisoinnit**-ruudun **Porautuminen**-osiossa **Säilytä kaikki suodattimet** -asetus **käyttöön**. 

![Säilytä kaikki suodattimet](media/desktop-drillthrough/drillthrough_06.png)

Toukokuuta 2018 edeltävissä Power BI Desktop -versioissa toiminta vastaa toimintaa siinä tapauksessa, että tämä asetus **ei ole käytössä**.

Kun sitten poraudut visualisointiin, voit nähdä, mitkä suodattimet on otettu käyttöön sen seurauksena, että lähdevisualisoinnissa on käytössä tilapäisiä suodattimia. Nämä tilapäiset suodattimet näkyvät **Visualisointi**ruudun **Porautuminen**-osiossa kursivoituina. 

![Kursivoidut tilapäiset suodattimet](media/desktop-drillthrough/drillthrough_07.png)

Voisit tehdä tämän myös työkaluvihjesivuille, mutta käyttö olisi tässä tapauksessa outoa, koska työkaluvihjeet eivät näyttäisi toimivan oikein. Tästä syystä käyttöä työkaluvihjeiden kanssa ei suositella.

## <a name="add-a-measure-to-drillthrough"></a>Mittarin lisääminen porautumiseen

Sen lisäksi, että voit siirtää kaikki suodattimet porautumisikkunaan, voit myös lisätä mittarin tai numeerisen yhteenvetosarakkeen porautumisalueeseen. Voit ottaa sen käyttöön vetämällä porautumiskentän **Porautuminen**-korttiin. 

![Mittarin lisääminen porautumiseen](media/desktop-drillthrough/drillthrough_08.png)

Kun lisäät mittarin tai numeerisen yhteenvetosarakkeen, voit porautua sivuun, kun kenttää käytetään visualisoinnin *Arvo*-alueella.

Tässä oli kaikki, mitä sinun tarvitsee tietää käyttääksesi porautumista raporteissasi. Se on erinomainen tapa laajentaa porautumissuodattimeksi valitsemasi entiteetin tietonäkymää.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit olla kiinnostunut myös seuraavista artikkeleista:

* [Raporttien välillä porautumisen käyttäminen Power BI Desktopissa](desktop-cross-report-drill-through.md)
* [Osittajien käyttäminen Power BI Desktopissa](visuals/power-bi-visualization-slicers.md)

