---
title: Puhelimelle optimoitujen Power BI ‑raporttien tarkastelu
description: Lue, miten voit toimia Power BI ‑puhelinsovelluksissa katselemista varten optimoitujen raporttisivujen kanssa.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/22/2019
ms.author: mshenhav
ms.openlocfilehash: 79ca47f83bb39ab9d6df141b5a26dcb54e00c72c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100948"
---
# <a name="view-power-bi-reports-optimized-for-your-phone"></a>Puhelimelle optimoitujen Power BI ‑raporttien tarkastelu

Koskee seuraavia:

| ![iPhone](./media/mobile-apps-view-phone-report/ios-logo-40-px.png) | ![Android-puhelin](./media/mobile-apps-view-phone-report/android-logo-40-px.png) |
|:--- |:--- |
| iPhonet |Android-puhelimet |

Kun tarkastelet Power BI-raportti puhelimessa, Power BI tarkistaa, onko raportti optimoitu puhelimia varten. Jos se on Power BI Avaa automaattisesti optimoidun raportin pystynäkymässä.

![Raportti pystysuuntaisessa tilassa](./media/mobile-apps-view-phone-report/07-power-bi-phone-report-portrait.png)

Jos puhelimille optimoitua raporttia ei ole, raportti avautuu silti mutta optimoimattomassa vaakanäkymässä. Vaikka raportista olisi puhelinoptimoitu versio, raportin voi avata optimoimattomassa alkuperäisessä raporttiasettelussa kääntämällä puhelimen vaakasuuntaan. Jos vain osa raportin sivuista on optimoitu, pystynäkymässä tulee esiin ilmoitus, jossa kerrotaan, että raportti on käytettävissä vaakanäkymässä.

![Optimoimaton raporttisivu](./media/mobile-apps-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Kaikki muut Power BI ‑raporttien ominaisuudet toimivat myös puhelinoptimoiduissa raporteissa. Lue lisää siitä käytettävissä olevista ominaisuuksista:

* [Raportit iPhone-puhelimissa](mobile-reports-in-the-mobile-apps.md). 
* [Raportit Android-puhelimissa](mobile-reports-in-the-mobile-apps.md).

## <a name="filter-the-report-page-on-a-phone"></a>Raporttisivun suodattaminen puhelimella
Jos puhelinoptimoituun raporttiin on määritetty suodattimia, voit käyttää niitä tarkastellessasi raporttia puhelimella. Raportti avautuu puhelimessasi suodatettu raportissa verkossa suodatetaan arvot. Saat ilmoituksen siitä, että sivulla on aktiivisia suodattimia. Voit muuttaa suodattimia puhelimessasi.

1. Napauta suodatinkuvaketta ![Puhelimen suodatinkuvake](./media/mobile-apps-view-phone-report/power-bi-phone-filter-icon.png) sivun alareunasta. 
2. Tuo esiin sinua kiinnostavat tulokset käyttämällä joko perus- tai lisäsuodattimia.
   
    ![BI-puhelinversion puhelinraportin lisäsuodatin](./media/mobile-apps-view-phone-report/power-bi-iphone-advanced-filter-toronto.gif)

## <a name="cross-highlight-visuals"></a>Visualisointien ristiinkorostaminen
Näytä toimii pysty visualisointien ristiinkorostaminen samalla tavoin kuin Power BI-palvelussa ja vaaka-näkymää: kun valitset tietoja yhdessä visualisoinnissa, tiedot korostuvat myös muissa tämän sivun visualisoinneissa.

Lue lisää [suodattamisesta ja korostamisesta Power BI:ssä](../../power-bi-reports-filters-and-highlighting.md).

## <a name="select-visuals"></a>Visualisointien valitseminen
Kun valitset puhelinraportissa visualisoinnin, puhelinraportti korostaa visualisoinnin ja kohdistaa siihen, mikä poistaa taustaa vasten tehtävät eleet käytöstä.

Kun visualisointi on valittuna, voit tehdä erilaisia toimintoja, kuten vierittää visualisointia. Kun haluat poistaa visualisoinnin valinnan, kosketa aluetta visualisoinnin ulkopuolella.

## <a name="open-visuals-in-focus-mode"></a>Visualisointien avaaminen tarkastelutilassa
Puhelinraportit on myös Kohdistustila: Hanki suurempi nähdä yksittäisen visualisoinnin ja tutustu entistä helpommin.

* Napauta puhelinraportissa visualisoinnin oikeasta yläkulmasta kolmea pistettä ( **...** ) &gt; **Laajenna tarkastelutilaan**.
  
    ![Laajenna tarkastelutilaan](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)

Älä kohdistustilassa toteuttaa raporttipohjassa ja päinvastoin. Esimerkiksi Korosta arvoa visualisoinnissa, ja palaat sitten koko raporttiin, raportti on suodatettu visualisoinnissa arvon haluat.

Näytön kokorajoitusten vuoksi jotkin toiminnot ovat käytettävissä vain tarkastelutilassa:

* **Poraudu alaspäin** johdattaa tarkastelijan syvemmälle visualisoinnin esittämiin tietoihin. Lisätietoja [alas- ja ylöspäin porautumisesta](mobile-apps-view-phone-report.md#drill-down-in-a-visual) puhelinraporteissa annetaan jäljempänä.
* **Lajittele** visualisoinnin arvoja.
* **Kumoa**: poistaa visualisoinnin tarkastelussa tehdyt toimet ja palauttaa raportin luonnin yhteydessä määritetyn tietojoukon.
  
    Jos haluat poistaa kaikki tarkastelutoimet, napauta kolmea pistettä ( **...** ) > **Kumoa**.
  
    ![Kumoa](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)
  
    Kumoaminen on käytettävissä sekä raporttitasolla, tyhjentää tarkastelutoimet kaikista visualisoinneista tai visualisoinnin tasolla tyhjentää valitun visualisoinnin tarkastelemisen.   

## <a name="drill-down-in-a-visual"></a>Porautuminen alaspäin visualisoinnissa
Jos visualisointiin on määritetty hierarkiatasot, voit porautua syvemmälle visualisoinnin esittämien tietojen yksityiskohtiin ja palata sitten takaisin ylöspäin. [Lisää visualisointiin mahdollisuus porautua alaspäin](../end-user-drill.md) joko Power BI -palvelussa tai Power BI Desktopissa.

On muutamia porautuminen tyyppiä:

### <a name="drill-down-on-a-value"></a>Poraudu alaspäin arvo
1. Napauta pitkään arvopistettä visualisoinnissa (Napauta ja pidä).
2. Työkaluvihje tulee näkyviin, ja jos hierarkia on määritetty, sitten työkaluvihjeen alatunniste näkyy Poraudu alaspäin ja ylöspäin osoittava nuoli.
3. Napauta alanuolta porautuminen

    ![Napauta Poraudu alaspäin](././media/mobile-apps-view-phone-report/report-drill-down.png)
    
4. Napauta Poraamisen ylänuolta.

### <a name="drill-to-next-level"></a>Siirry seuraavalle tasolle
1. Napauta puhelimella raportin oikeasta yläkulmasta kolmea pistettä ( **...** ) &gt; **Laajenna tarkastelutilaan**.
   
    ![Laajenna tarkastelutilaan](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)
   
    Tässä esimerkissä palkit kuvaavat osavaltioiden arvoja.
2. Napauta tutkimiskuvaketta ![Tutkimiskuvake](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-icon.png) vasemmassa alakulmassa.
   
    ![Tutkimistila](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-mode.png)
3. Napauta joko vaihtoehtoa **Näytä seuraava taso** tai **Laajenna seuraavalle tasolle**.
   
    ![Laajenna seuraavalle tasolle](./media/mobile-apps-view-phone-report/power-bi-phone-report-expand-levels.png)
   
    Nyt palkit esittävät kaupunkien arvot.
   
    ![Laajennetut tasot](./media/mobile-apps-view-phone-report/power-bi-phone-report-expanded-levels.png)
4. Jos napautat vasemmassa yläkulmassa olevaa nuolta, palaat puhelinraporttiin, jossa arvot näkyvät edelleen alemmalle tasolle laajennettuna.
   
    ![Laajennettuna edelleen alemmalle tasolle](./media/mobile-apps-view-phone-report/power-bi-back-to-phone-report-expanded-levels.png)
5. Voit palata takaisin alkuperäiselle tasolle napauttamalla uudelleen kolmea pistettä ( **...** ) > **Kumoa**.
   
    ![Kumoa](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)

## <a name="drill-through-from-a-value"></a>Porautua arvo
Porautuminen yhdistää yhden raporttisivun arvot raportin muilla sivuilla. Kun voit porautua arvopisteestä raportin toiselle sivulle, arvopisteiden arvot on käytetty Porattu-sivun kautta tai se on valitut tiedot kontekstissa.
Raporttien tekijät voivat [määrittää porautuminen](https://docs.microsoft.com/power-bi/desktop-drillthrough) luodessaan raportin.

1. Napauta pitkään arvopistettä visualisoinnissa (Napauta ja pidä).
2. Työkaluvihje tulee näkyviin, ja jos porautuminen on määritetty, sitten työkaluvihjeen alatunniste näkyy porautuminen nuolta.
3. Napauta nuolta porautuminen

    ![Napauta porautuminen](././media/mobile-apps-view-phone-report/report-drill-through1.png)

4. Valitse Poraudu raporttisivu

    ![Valitse raporttisivu](././media/mobile-apps-view-phone-report/report-drill-through2.png)

5. Käytä app-otsikkoa ja palaa sivulle, voit käynnistää takaisin-painike.


## <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI -puhelinsovelluksille optimoitujen raporttien luominen](../../desktop-create-phone-report.md)
* [Koontinäytön puhelinnäkymän luominen Power BI:ssä](../../service-create-dashboard-mobile-phone-view.md)
* [Mihin tahansa kokoon optimaalisten reagoivien visualisointien luominen](../../visuals/desktop-create-responsive-visuals.md)
* Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

