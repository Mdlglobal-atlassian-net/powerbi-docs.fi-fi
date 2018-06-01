---
title: Power BI:n visualisoinnin optimointi mihin tahansa kokoon
description: Lue, miten voit optimoida visualisointeja Power BI Desktopissa ja Power BI -puhelinsovellusten Power BI -palvelussa.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 4c80048213b20365102bcb9c6842c342d8b9052b
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30973737"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Power BI:n visualisoinnin optimointi mihin tahansa kokoon
Voit määrittää koontinäytön tai raportin visualisoinnin *reagoivaksi*, jos haluat, että dataa ja merkityksellisiä tietoja näytetään dynaamisesti suurin mahdollinen määrä, oli näyttö minkäkokoinen tahansa.

Visualisoinnin koon muuttuessa Power BI priorisoi tietonäkymän automaattisesti esimerkiksi poistamalla täytön ja siirtämällä selitteen visualisoinnin yläpuolelle, jolloin visualisointi pysyy informatiivisena myös pienessä koossa. Reagoinnista on hyötyä erityisesti puhelinten Power BI -mobiilisovelluksien visualisoinneissa.

![Reagoivan visualisoinnin koon muuttaminen](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Voit ottaa käyttöön reagoinnin mille tahansa visualisoinnille, jossa on X- ja Y-akselit ja osittajia.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Power BI Desktopin reagoinnin ottaminen käyttöön
1. Ollessasi Power BI Desktopin **Näkymä**-välilehdellä varmista, että olet **Työpöydän asettelussa**.
   
    ![Työpöydän asettelu -kuvake](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Valitse visualisointi, ja valitse **Visualisoinnit**-ruudussa **Muotoile**-osa.
3. Laajenna **Yleinen** > siirrä **Reagoiva** tilaan **Päällä**.
   
    ![Reagoiva päällä](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Nyt, kun [luot puhelimelle optimoidun raportin](desktop-create-phone-report.md) ja lisäät tämän visualisoinnin, sen koko muuttuu hallitusti.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Power BI -palvelun reagoinnin ottaminen käyttöön
Voit ottaa käyttöön visualisoinnin reagoinnin raportille Power BI -palvelussa. Sinun on pystyttävä muokkaamaan raporttia.

1. Valitse Power BI -palvelun raportissa ([https://powerbi.com](https://powerbi.com)) **Muokkaa raporttia**.
2. Valitse visualisointi, ja valitse **Visualisoinnit**-ruudussa **Muotoile**-osa.
3. Laajenna **Yleinen** > siirrä **Reagoiva** tilaan **Päällä**.
   
    ![Reagoiva päällä](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Nyt, kun [luot koontinäytöstä puhelinnäkymän](service-create-dashboard-mobile-phone-view.md) ja lisäät tämän visualisoinnin, sen koko muuttuu hallitusti.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI -puhelinsovelluksille optimoitujen raporttien luominen](desktop-create-phone-report.md)
* [Koontinäytön puhelinnäkymän luominen Power BI:ssä](service-create-dashboard-mobile-phone-view.md)
* [Puhelimelle optimoitujen Power BI ‑raporttien tarkastelu](mobile-apps-view-phone-report.md)
* Ilmenikö muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

