---
title: Power BI:n visualisoinnin optimointi mihin tahansa kokoon
description: Lue, miten voit optimoida olemassa olevien raporttien visualisointeja Power BI Desktopissa ja Power BI -palvelussa Power BI -mobiilisovelluksille.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 1260f2c69a4ab913f7451671ab7821ee250998c0
ms.sourcegitcommit: fb1885da7cf11367660edbf7b7346dc039ee9b5d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187233"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Power BI:n visualisoinnin optimointi mihin tahansa kokoon
Kun luot uuden raportin, visualisoinnit ovat oletuksena *reagoivia*: dataa ja merkityksellisiä tietoja näytetään dynaamisesti suurin mahdollinen määrä, oli näyttö minkä kokoinen tahansa. Voit määrittää myös vanhempien raporttien sisältämien visualisointien koon dynaamisesti muuttuvaksi.

Visualisoinnin koon muuttuessa Power BI priorisoi tietonäkymän automaattisesti esimerkiksi poistamalla täytön ja siirtämällä selitteen visualisoinnin yläpuolelle, jolloin visualisointi pysyy informatiivisena myös pienessä koossa. Reagoinnista on hyötyä erityisesti puhelinten Power BI -mobiilisovelluksien visualisoinneissa.

![Reagoivan visualisoinnin koon muuttaminen](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Minkä tahansa X- ja Y-akselit ja osittajia sisältävän visualisoinnin kokoa voidaan muuttaa dynaamisesti.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Power BI Desktopin reagoinnin ottaminen käyttöön
1. Ollessasi vanhemmassa raportissa Power BI Desktopissa, varmista **Näkymä**-välilehdellä, että olet **Työpöydän asettelussa**.
   
    ![Työpöydän asettelu -kuvake](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Valitse visualisointi, ja valitse **Visualisoinnit**-ruudussa **Muotoile**-osa.
3. Laajenna **Yleinen** > siirrä **Reagoiva** tilaan **Päällä**.
   
    ![Reagoiva päällä](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Nyt, kun [luot puhelimelle optimoidun raportin](../desktop-create-phone-report.md) ja lisäät tämän visualisoinnin, sen koko muuttuu hallitusti.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Power BI -palvelun reagoinnin ottaminen käyttöön
Voit ottaa käyttöön visualisoinnin reagoinnin vanhemmalle raportille Power BI -palvelussa. Sinun on pystyttävä muokkaamaan raporttia.

1. Valitse Power BI -palvelun raportissa ([https://powerbi.com](https://powerbi.com)) **Muokkaa raporttia**.
2. Valitse visualisointi, ja valitse **Visualisoinnit**-ruudussa **Muotoile**-osa.
3. Laajenna **Yleinen** > siirrä **Reagoiva** tilaan **Päällä**.
   
    ![Reagoiva päällä](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Kun nyt [luot puhelinnäkymän raportista](../desktop-create-phone-report.md) ja lisäät tämän visualisoinnin, sen koko muuttuu hallitusti.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI -puhelinsovelluksille optimoitujen raporttien luominen](../desktop-create-phone-report.md)
* [Puhelimelle optimoitujen Power BI ‑raporttien tarkastelu](../consumer/mobile/mobile-apps-view-phone-report.md)
* Ilmenikö muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

