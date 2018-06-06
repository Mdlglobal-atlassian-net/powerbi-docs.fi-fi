---
title: Porautumisen käyttäminen Power BI Desktopissa
description: Lue, miten voit porautua tietoihin uudella raporttisivulla Power BI Desktopissa
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f4cf7b0b850445b794c092f01b7e9a837ca3f215
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973767"
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Porautumisen käyttäminen Power BI Desktopissa
**Power BI Desktopin** **porautumisen** avulla voit luoda raporttisivun, jolla keskitytään tiettyyn entiteettiin, kuten toimittajaan, asiakkaaseen tai valmistajaan. Käyttäjät voivat keskitetyllä raporttisivuilla napsauttaa hiiren kakkospainikkeella arvopistettä toisella raporttisivulla ja porautua keskittyvälle sivulle saadakseen lisätietoja, jotka on suodatettu kyseisen kontekstin mukaisesti.

![](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Porautumisen käyttö
Jos haluat käyttää **porautumista**, luo raporttisivu, jolla on visualisointeja, jotka haluaisit nähdä porautumisen kohde-entiteettityypistä. Esimerkiksi, jos haluat tarjota valmistajille porautumisen, voit luoda porautumissivun, jolla on visualisointeja kokonaismyynnistä, toimitettujen yksiköiden kokonaismääristä, kategoriakohtaisista myynneistä, aluekohtaisista myynneistä ja niin edelleen. Tällä tavoin, kun kyseiselle sivulle poraudutaan, visualisointi on kohdistettu siihen valmistajaan, jota klikkasit ja jonka kohdalta porauduit.

Vedä sitten porautumissivulla **visualisointipaneelin** **Kentät-** osiossa se kenttä, josta haluat porautua, **Porautumissuodattimiin**.

![](media/desktop-drillthrough/drillthrough_02.png)

Kun lisäät kentän **porautumissuodattimiin**, **Power BI Desktop** luo automaattisesti visualisoinnin *Takaisin*-painikkeelle. Visualisointi muuttuu julkaistuilla raporteilla painikkeeksi, jonka avulla raporttia **Power BI -palvelussa** hyödyntävät käyttäjät voivat palata kätevästi sille raporttisivulle, jolta he tulivat (sivu, jolla he valitsivat porauksen).

![](media/desktop-drillthrough/drillthrough_03.png)

Koska *Takaisin*-painike on kuva, voit korvata kyseisen visualisoinnin kuvan visualisoinnin millä tahansa haluamallasi kuvalla, ja se toimii silti oikein painikkeena, joilla raportin käyttäjät voivat palata alkuperäiselle sivulle. Käyttääksesi omaa kuvaasi Takaisin-painikkeena, aseta kuva porautumissivulle, valitse se ja määritä *Takaisin-painikkeen* liukusäädin asentoon päällä. Tämän jälkeen kuvasi toimii *Takaisin*-painikkeena.

![](media/desktop-drillthrough/drillthrough_05.png)

Kun **porautumissivusi** on valmis, käyttäjien napsauttaessa hiiden kakkospainikkeella sellaista raporttisi arvopistettä, joka käyttää porautumissivulla **porautumissuodattimiin** lisäämääsi kenttää, näytölle ilmestyy kontekstivalikko, jonka avulla käyttäjät voivat porautua kyseiselle sivulle.

![](media/desktop-drillthrough/drillthrough_04.png)

Kun käyttäjä valitsee porautumisen, sivu suodatetaan näyttämään tietoja hiiren kakkospainikkeella napsautetusta arvopisteestä. Esimerkiksi, jos käyttäjä napsauttaa hiiren kakkospainikkeella Contosoa (valmistaja) koskevaa arvopistettä ja valitsee porautumisen, hänet viedään Contosolla suodatetulle porautumissivulle.

> [!NOTE]
> Vain **porautumissuodattimissa** oleva kenttä välitetään porautumisraporttisivulle. Mitään muuta kontekstitietoja ei välitetä.
> 
> 

Sen enempää ei tarvita, jotta voisit käyttää **porautumista** raporteissasi. Se on erinomainen tapa laajentaa porautumissuodattimeksi valitsemasi entiteetin tietonäkymää.

