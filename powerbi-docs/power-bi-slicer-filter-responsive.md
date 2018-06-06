---
title: Kooltaan muokattavan reagoivan osittajan luominen Power BI:ssa
description: Lue, miten voit luoda reagoivan osittajan, jonka kokoa voidaan muokata sopimaan raporttiin.
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
ms.date: 12/08/2017
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 2ab907dd15e43892147967902fbb94d09ef4125b
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2018
ms.locfileid: "30975327"
---
# <a name="create-a-responsive-slicer-you-can-resize-in-power-bi-preview"></a>Kooltaan muokattavan reagoivan osittajan luominen Power BI:ssa (esikatselu)

Reagoivien osittajien kokoa voidaan muuttaa mihin tahansa raportin tilaan sopivaksi. Reagoivan osittajan avulla, voit muuttaa niiden kokoa eri kokoihin ja muotoihin, vaakasuuntaisesta pystysuuntaiseksi ja nelikulmaiseksi, ja osittajan arvot järjestävät itsensä kuin sinä. Power BI Desktopin ja Power BI -palvelun avulla voit saada aikaan vaakasuuntaisia osittajia ja reagoivia päivämäärä/alueosittajia. Päivämäärä-/alueosittajilla on myös parannetut kosketusalueet, joten niiden muuttaminen on helpompaa sormenpäällä. Voit tehdä reagoivista osittajista niin pieni tai suuria kuin haluat. Ne myös muuttuvat kooltaan automaattisesti sopimaan hyvin raportteihin Power BI -palvelussa ja Power BI -mobiilisovelluksissa. 

![Reagoivilla osittajilla voi olla erilaisia muotoja](media/power-bi-slicer-filter-responsive/responsive-slicer-gif.gif)

## <a name="create-a-slicer"></a>Osittajan luominen

Ensimmäinen vaihe dynaamisen osittajan luomisessa on perusosittajan luominen. 

1. Valitse **Osittaja**-kuvake ![](media/power-bi-slicer-filter-responsive/power-bi-slicer-icon.png) **Visualisoinnit**-ruudusta.
2. Vedä kenttä, jonka haluat suodattaa, kohtaan **Kenttä**.

    ![Kentän lisääminen osittajaan](media/power-bi-slicer-filter-responsive/power-bi-slicer-field.png)

## <a name="convert-to-a-horizontal-slicer"></a>Vaakasuuntainen osittajan muuntaminen

1. Kun olet valinnut osittajan, tuo muotoiluasetukset näkyviin valitsemalla **Visualisoinnit**-ruudusta **Muotoile**-välilehti.
2. Laajenna **Yleinen**-osaa ja sitten valitse kohdasta **Suunta** **vaakasuuntainen**.

    ![Osittajan määrittäminen vaakasuuntaiseksi](media/power-bi-slicer-filter-responsive/power-bi-slicer-horizontal.png) 

1.  Luultavasti haluat tehdä siitä leveämmän, jotta voit näyttää enemmän arvoja.

     ![Osittajan leventäminen](media/power-bi-slicer-filter-responsive/power-bi-slicer-wide-horizontal.png)

## <a name="make-it-responsive-and-experiment-with-it"></a>Tee siitä reagoiva ja tee sillä kokeita

Tämä on helppo vaihe. 

1. Hetki kohdan **Suunta** alla **Yleiset**-osassa **Muoto** -välilehdessä työnnä **Reagoiva (esikatselu)** asentoon **On** .  

    ![Osittaja on nyt reagoiva](media/power-bi-slicer-filter-responsive/power-bi-slicer-wide-responsive.png)

1. Nyt voit muokata sitä. Lyhennä, pidennä, levennä tai kavenna sitä vetämällä kulmista. Jos pienennät sitä riittävästi, siitä tulee pelkkä suodatinkuvake.

    ![Niin pieni reagoiva osittaja, että se on suodatinkuvake](media/power-bi-slicer-filter-responsive/power-bi-slicer-small-filter-icon.png)

## <a name="add-it-to-a-phone-report-layout"></a>Lisääminen puhelinraporttiasetteluun

Power BI Desktopissa voit luoda puhelinasettelun raportin jokaista sivua varten. Jos sivulla on puhelinasettelu, se näkyy matkapuhelimessa pystynäkymässä. Muussa tapauksessa sitä pitää tarkastella vaakanäkymässä. 

1. Valitse **Näkymä**-valikosta **Puhelinasettelu**.

     ![Puhelinasettelun kuvake, Näkymä-valikko](media/power-bi-slicer-filter-responsive/power-bi-phone-layout-menu.png)
    
1. Vedä kaikki puhelinraporttiin haluamasi visualisoinnit ruudukkoon. Kun vedät reagoivaa osittajaa, tee siitä haluamasi kokoinen, tässä tapauksessa vain suodatin-kuvakkeen kokoinen.

    ![Osittajan lisääminen puhelinraporttiasetteluun](media/power-bi-slicer-filter-responsive/power-bi-slicer-phone-layout.png)

Lue lisää, kuinka luodaan [raportteja, jotka on optimoitu Power BI-mobiilisovelluksille](desktop-create-phone-report.md).

## <a name="make-a-time-or-range-slicer-responsive"></a>Ajan tai alueen osittajan reagoivaksi saaminen

Voit seurata samoja vaiheita tehdessäsi ajan tai alueen osittajan reagoivaksi. Kun olet määrittänyt asetuksen **Reagoiva** arvoon **On**, huomaat muutamia asioita:

- Visualisoinnit optimoivat syöteruutujen järjestyksen alustan sallitun koon mukaan. 
- Tietoelementin näyttö on optimoitu tekemään osittajista mahdollisimman käyttökelpoisia piirtoalustan salliman koon perusteella. 
- Uudet liukusäätimien pyöreät kädensijat optimoivat kosketusohjauksen. 
- Jos visualisoinnista tulee liian pieni, jotta siitä olisi hyötyä, siitä tulee kuvake, joka edustaa visualisoinnin tyyppiä omalla paikallaan. Voit käsitellä sitä kaksoisnapauttamalla se auki kohdistustilassa. Tämä säästää arvokasta tilaa raportin sivulla toiminnoista tinkimättä.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Opetusohjelma: Osittajat Power BI -palvelussa](power-bi-visualization-slicers.md)
- Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)