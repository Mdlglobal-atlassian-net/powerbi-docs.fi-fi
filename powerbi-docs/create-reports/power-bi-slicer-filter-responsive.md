---
title: Kooltaan muokattavan reagoivan osittajan luominen Power BI:ssa
description: Lue, miten voit luoda reagoivan osittajan, jonka kokoa voidaan muokata sopimaan raporttiin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: f4e70bdcd877c29063a73cc24111d4dc04aa39b9
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83280974"
---
# <a name="create-a-responsive-slicer-you-can-resize-in-power-bi"></a>Kooltaan muokattavan reagoivan osittajan luominen Power BI:ssa

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Reagoivien osittajien kokoa voidaan muuttaa mihin tahansa raportin tilaan sopivaksi. Reagoivan osittajan avulla, voit muuttaa niiden kokoa eri kokoihin ja muotoihin, vaakasuuntaisesta pystysuuntaiseksi ja nelikulmaiseksi, ja osittajan arvot järjestävät itsensä kuin sinä. Power BI Desktopin ja Power BI -palvelun avulla voit saada aikaan vaakasuuntaisia osittajia ja reagoivia päivämäärä/alueosittajia. Päivämäärä-/alueosittajilla on myös parannetut kosketusalueet, joten niiden muuttaminen on helpompaa sormenpäällä. Voit tehdä reagoivista osittajista niin pieni tai suuria kuin haluat. Ne myös muuttuvat kooltaan automaattisesti sopimaan hyvin raportteihin Power BI -palvelussa ja Power BI -mobiilisovelluksissa. 

![Reagoivilla osittajilla voi olla erilaisia muotoja](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-0-slicer.gif)

## <a name="create-a-slicer"></a>Osittajan luominen

Ensimmäinen vaihe dynaamisen osittajan luomisessa on perusosittajan luominen. 

1. Valitse **Osittaja**-kuvake ![](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-0-slicer-icon.png)**Visualisoinnit**-ruudusta.
2. Vedä kenttä, jonka haluat suodattaa, kohtaan **Kenttä**.

    ![Kentän lisääminen osittajaan](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-1-create.png)

## <a name="convert-to-a-horizontal-slicer"></a>Vaakasuuntainen osittajan muuntaminen

1. Kun olet valinnut osittajan, tuo muotoiluasetukset näkyviin valitsemalla **Visualisoinnit**-ruudusta **Muotoile**-välilehti.
2. Laajenna **Yleinen**-osaa ja sitten valitse kohdasta **Suunta** **vaakasuuntainen**.

    ![Osittajan määrittäminen vaakasuuntaiseksi](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-2-horizontal.png) 

1.  Luultavasti haluat tehdä siitä leveämmän, jotta voit näyttää enemmän arvoja.

     ![Osittajan leventäminen](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-3-wider.png)

## <a name="make-it-responsive-and-experiment-with-it"></a>Tee siitä reagoiva ja tee sillä kokeita

Tämä on helppo vaihe. 

1. Työnnä **Suunta**-kohdan alla **Yleiset**-osassa **Muoto**-välilehdessä **Reagoiva** asentoon **Käytössä**.  

    ![Osittaja on nyt reagoiva](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-4-responsive-on.png)

1. Nyt voit muokata sitä. Lyhennä, pidennä, levennä tai kavenna sitä vetämällä kulmista. Jos pienennät sitä riittävästi, siitä tulee pelkkä suodatinkuvake.

    ![Niin pieni reagoiva osittaja, että se on suodatinkuvake](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-5-mini-icon.png)

## <a name="add-it-to-a-phone-report-layout"></a>Lisääminen puhelinraporttiasetteluun

Power BI Desktopissa voit luoda puhelinasettelun raportin jokaista sivua varten. Jos sivulla on puhelinasettelu, se näkyy matkapuhelimessa pystynäkymässä. Muussa tapauksessa sitä pitää tarkastella vaakanäkymässä. 

1. Valitse **Näkymä**-valikosta **Puhelinasettelu**.

     ![Puhelinasettelun kuvake, Näkymä-valikko](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-6-phone-layout-button.png)
    
1. Vedä kaikki puhelinraporttiin haluamasi visualisoinnit ruudukkoon. Kun vedät reagoivaa osittajaa, tee siitä haluamasi kokoinen, tässä tapauksessa vain suodatin-kuvakkeen kokoinen.

    ![Osittajan lisääminen puhelinraporttiasetteluun](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-7-phone-slicer-icon.png)

Lue lisää, kuinka luodaan [raportteja, jotka on optimoitu Power BI-mobiilisovelluksille](desktop-create-phone-report.md).

## <a name="make-a-time-or-range-slicer-responsive"></a>Ajan tai alueen osittajan reagoivaksi saaminen

Voit seurata samoja vaiheita tehdessäsi ajan tai alueen osittajan reagoivaksi. Kun olet määrittänyt asetuksen **Reagoiva** arvoon **On**, huomaat muutamia asioita:

- Visualisoinnit optimoivat syöteruutujen järjestyksen alustan sallitun koon mukaan. 
- Tietoelementin näyttö on optimoitu tekemään osittajista mahdollisimman käyttökelpoisia piirtoalustan salliman koon perusteella. 
- Uudet liukusäätimien pyöreät kädensijat optimoivat kosketusohjauksen. 
- Jos visualisoinnista tulee liian pieni, jotta siitä olisi hyötyä, siitä tulee kuvake, joka edustaa visualisoinnin tyyppiä omalla paikallaan. Voit käsitellä sitä kaksoisnapauttamalla se auki tarkastelutilassa. Tämä säästää arvokasta tilaa raportin sivulla toiminnoista tinkimättä.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Osittajat Power BI -palvelussa](../visuals/power-bi-visualization-slicers.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)