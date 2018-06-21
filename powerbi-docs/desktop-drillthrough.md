---
title: Porautumisen käyttäminen Power BI Desktopissa
description: Lue, miten voit porautua tietoihin uudella raporttisivulla Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 8c9a0d075c6d55baa1f518874fa668a3f0db8cb3
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34291278"
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Porautumisen käyttäminen Power BI Desktopissa
**Power BI Desktopin** **porautumisen** avulla voit luoda raporttisivun, jolla keskitytään tiettyyn entiteettiin, kuten toimittajaan, asiakkaaseen tai valmistajaan. Käyttäjät voivat keskitetyllä raporttisivuilla napsauttaa hiiren kakkospainikkeella arvopistettä toisella raporttisivulla ja porautua keskittyvälle sivulle saadakseen lisätietoja, jotka on suodatettu kyseisen kontekstin mukaisesti.

![porautumisen käyttö](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Porautumisen käyttö
1. Jos haluat käyttää **porautumista**, luo raporttisivu, jolla on visualisointeja, jotka haluaisit nähdä porautumisen kohde-entiteettityypistä. 

    Esimerkiksi, jos haluat tarjota valmistajille porautumisen, voit luoda porautumissivun, jolla on visualisointeja kokonaismyynnistä, toimitettujen yksiköiden kokonaismääristä, kategoriakohtaisista myynneistä, aluekohtaisista myynneistä ja niin edelleen. Tällä tavoin, kun kyseiselle sivulle poraudutaan, visualisointi on kohdistettu valitsemaasi valmistajaan.

2. Vedä sitten porautumissivulla **visualisointipaneelin** **Kentät-** osiossa se kenttä, josta haluat porautua, **Porautumissuodattimiin**.

    ![porautumislähde](media/desktop-drillthrough/drillthrough_02.png)

    Kun lisäät kentän **porautumissuodattimiin**, **Power BI Desktop** luo automaattisesti visualisoinnin *Takaisin*-painikkeelle. Visualisointi muuttuu julkaistuilla raporteilla painikkeeksi, jonka avulla raporttia **Power BI -palvelussa** hyödyntävät käyttäjät voivat palata kätevästi sille raporttisivulle, jolta he tulivat (sivu, jolla he valitsivat porauksen).

    ![porautumiskuva](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>Oman kuvan käyttäminen Takaisin-painikkeena    
 Takaisin-painike on kuva, joten voit korvata kuvan millä tahansa haluamallasi kuvalla, ja se toimii silti oikein Takaisin-painikkeena, jolla raportin käyttäjät voivat palata alkuperäiselle sivulle.

1. Valitse **Aloitus**-välilehdestä **Kuva**, etsi haluamasi kuva ja sijoita se porautumissivulle.
2. Valitse uusi kuva Porautuminen-sivulla ja aseta Muotoile kuva -osassa **Linkki**-liukusäädin päällä-asentoon ja valitse **Tyyppi**-asetukseksi **Takaisin**. Kuva toimii nyt Takaisin-painikkeena.

    ![kuvan käyttäminen Takaisin-painikkeena](media/desktop-drillthrough/drillthrough_05.png)

    Kun **porautumissivusi** on valmis, ja käyttäjä napsauttaa hiiren kakkospainikkeella sellaista raporttisi arvopistettä, joka käyttää **porautumissuodattimiin** lisäämääsi kenttää, näytölle tulee kontekstivalikko, jonka avulla käyttäjät voivat porautua kyseiselle sivulle.

    ![porautumisvalikko](media/desktop-drillthrough/drillthrough_04.png)

    Kun raportin kuluttaja valitsee porautumisen, sivu suodatetaan näyttämään tietoja hiiren kakkospainikkeella napsautetusta arvopisteestä. Jos käyttäjä esimerkiksi napsauttaa hiiren kakkospainikkeella Contosoa (valmistaja) koskevaa arvopistettä ja valitsee porautumisen, hänet viedään Contosolla suodatetulle porautumissivulle.

## <a name="pass-all-filters-in-drillthrough"></a>Kaikkien suodattimien siirtäminen porautumisessa

Toukokuun 2018 **Power BI Desktop** -versiosta alkaen voit siirtää kaikki käytetyt suodattimet porautumisikkunaan. Olet ehkä esimerkiksi valinnut vain tietyn tuoteluokan ja kyseiseen luokkaan suodatetut visualisoinnit ja valitset sitten porautumisen. Saatat olla kiinnostunut siitä, miltä porautuminen näyttäisi kaikkien näiden suodattimien ollessa käytössä.

Jos haluat säilyttää kaikki käytetyt suodattimet, aseta **Visualisoinnit**-ruudun **Porautuminen**-osiossa **Siirrä kaikki suodattimet** -vaihtopainike **päälle**. 

![säilytä kaikki suodattimet](media/desktop-drillthrough/drillthrough_06.png)

Toukokuuta 2018 edeltävissä **Power BI Desktop** -versioissa toiminta vastaa toimintaa siinä tapauksessa, että tämä vaihtopainike on **pois päältä**.

Kun sitten poraudut visualisointiin, voit nähdä, mitkä suodattimet on otettu käyttöön sen seurauksena, että lähdevisualisoinnissa on käytössä tilapäisiä suodattimia. Nämä tilapäiset suodattimet näkyvät porautumisikkunassa kursivoituina. 

![kursivoitu tilapäiset suodattimet](media/desktop-drillthrough/drillthrough_07.png)

Huomaa, että voisit tehdä tämän myös työkaluvihjesivujen tapauksessa, mutta käyttökokemus olisi tällöin outo (työkaluvihjeet eivät näyttäisi toimivan oikein), joten käyttöä työkaluvihjeiden kanssa ei suositella.

## <a name="add-a-measure-to-drillthrough"></a>Mittarin lisääminen porautumiseen

Sen lisäksi, että voit siirtää kaikki suodattimet porautumisikkunaan, voit myös lisätä mittarin (tai numeerisen yhteenvetosarakkeen) porautumisalueeseen. Voit ottaa sen käyttöön yksinkertaisesti vetämällä porautumiskentän porautumiskorttiin. 

![mittarin lisääminen porautumiseen](media/desktop-drillthrough/drillthrough_08.png)

Kun lisäät mittarin (tai numeerisen yhteenvetosarakkeen), voit porautua sivuun, kun kenttää käytetään visualisoinnin *Arvo*-alueella.

Sen enempää ei tarvita, jotta voit käyttää **porautumista** raporteissasi. Se on erinomainen tapa laajentaa porautumissuodattimeksi valitsemasi entiteetin tietonäkymää.

## <a name="next-steps"></a>Seuraavat vaiheet

Voit olla kiinnostunut myös seuraavista artikkeleista:

* [Osittajien käyttäminen Power BI Desktopissa](desktop-slicers.md)

