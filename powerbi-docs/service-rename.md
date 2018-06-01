---
title: Nimeä uudelleen koontinäytöt, raportit, työtilat, raporttisivut ja tietojoukot
description: Nimeä melkein mitä tahansa uudelleen Power BI -palvelussa.
services: powerbi
documentationcenter: ''
author: mihart
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
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: cdea6474901dad27a4155b80fb605502102201a5
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/09/2018
ms.locfileid: "29721550"
---
# <a name="rename-almost-anything-in-power-bi-service"></a>Nimeä melkein mitä tahansa uudelleen Power BI -palvelussa
Tässä artikkelissa opetetaan, miten Power BI -palvelussa nimetään uudelleen koontinäyttö, raportti, raporttisivu, työkirja, tietojoukko, sovellus ja työtila.

**Voinko muuttaa nimen?**

| Sisältötyyppi | Olen tekijä tai luoja | Jaettu kanssani |
| --- | --- | --- |
| Työtilan koontinäyttö |Kyllä |Ei |
| Työtilan raportti |Kyllä |Ei |
| Työtilan työkirja |Kyllä |Ei |
| Työtilan tietojoukko |Kyllä |Ei |
| Sovellustyötila |Kyllä, jos olet omistaja tai sinulla on järjestelmänvalvojan oikeudet |Ei |
| Julkaistut sovellukset |Ei sovellusnäytöltä, mutta sovelluksen nimen voi muuttaa sovellustyötilassa ja julkaista uudelleen uudella nimellä, jos sinulla on järjestelmänvalvojan oikeudet |Ei |
| Sovelluksen sisältö (koontinäyttö, raportti, työkirja ja tietojoukko) |Ei sovellusnäytöltä, mutta sovelluksen sisällön voi nimetä uudelleen sovellustyötilassa ja julkaista uudelleen uudella nimellä, jos sinulla on järjestelmänvalvojan oikeudet |Ei |
| Sisältö **Jaettu kanssani** -kohdissa |Ei |Ei |

## <a name="rename-a-dashboard-report-or-workbook"></a>Nimeä uudelleen koontinäyttö, raportti tai työkirja
1. Aloita työtilasta ja valitse **Koontinäytöt**-, **Raportit**- tai **Työkirjat**-välilehti. Vie hiiren osoitin uudelleen nimettävän kohteen päälle ja valitse hammaspyöräkuvake ![hammaspyöräkuvake](media/service-rename/powerbi-cog-icon.png). Jos et näe hammaspyöräkuvaketta, sinulla ei ole oikeutta uudelleen nimeämiseen.
   
   ![Power BI -palvelun työtila](media/service-rename/power-bi-workspace-dashboards.png)
2. Kirjoita Asetukset-sivulla uusi nimi ja valitse **Tallenna**.
   
   ![Tietojoukon Asetukset-ikkuna](media/service-rename/power-bi-rename-dashboard2.png)

## <a name="rename-a-dataset"></a>Nimeä tietojoukko uudelleen
1. Aloita työtilasta ja valitse **Tietojoukot**-välilehti.
   
   ![Työtilan Tietojoukot-välilehti](media/service-rename/power-bi-ellipses.png)
2. Vie hiiren osoitin uudelleen nimettävän kohteen päälle, valitse kolme pistettä (...) ja valitse **Nimeä uudelleen**.  
   
      ![Valitse Nimeä uudelleen](media/service-rename/power-bi-rename-datasets.png)
   
   > [!NOTE]
   > Avattavan valikon vaihtoehdot vaihtelevat.
   > 
   > 
3. Kirjoita Asetukset-sivulla uusi nimi ja valitse **Tallenna**.
   
     ![Nimeä ruutu uudelleen](media/service-rename/power-bi-rename.png)

## <a name="rename-an-app-workspace"></a>Nimeä sovellustyötila uudelleen
Sovellustyötilan voi nimetä uudelleen kuka tahansa, jolla on järjestelmänvalvojan oikeudet.

1. Aloita siitä työtilasta, jonka haluat nimetä uudelleen.
2. Valitse oikeasta yläkulmasta kolme pistettä (...) ja valitse **Muokkaa työtilaa**. Jos et näe tätä asetusta, sinulla ei ole oikeutta nimetä tätä työtilaa uudelleen. 
   
    ![Valitse Muokkaa työtilaa](media/service-rename/power-bi-edit-workspace.png)
3. Kirjoita uusi työtilan nimi ja valitse **Tallenna**.
   
   ![Muokkaa työtilaa -ruutu](media/service-rename/power-bi-workspace-rename.png)

## <a name="rename-a-page-in-a-report"></a>Nimeä raportin sivu uudelleen
Etkö pidä Power BI -raporttisi sivun nimestä?  Uusi nimi on vain napsautuksen päässä. Sivuja voi nimetä uudelleen [raportin muokkausnäkymässä](service-interact-with-a-report-in-editing-view.md).

1. Avaa raportti [muokkausnäkymässä](service-reading-view-and-editing-view.md).
2. Etsi raporttisivun välilehdet Power BI -ikkunan alareunasta.
   
    ![Raportti, jossa välilehdet näkyvät korostettuna](media/service-rename/report-page-tabs-new.png)
3. Avaa raporttisivu, jonka haluat nimetä uudelleen, valitsemalla välilehti.
4. Korosta välilehti kaksoisnapsauttamalla sen nimeä.  
   
    ![Lähikuva välilehden nimestä](media/service-rename/hilite-tab.png)
5. Kirjoita uusi raporttisivun nimi ja paina ENTER-näppäintä.
   
    ![Kirjoita uusi sivun nimi](media/service-rename/new-name.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Jos uudelleen nimettävä kohde on jaettu kanssasi tai kuuluu sisältöpakettiin, et näe hammaspyöräkuvaketta etkä pääse asetuksiin.
* Jos et näe **Tietojoukot**-välilehdessä kolmea pistettä (...), laajenna selainikkuna.

Ilmenikö muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

