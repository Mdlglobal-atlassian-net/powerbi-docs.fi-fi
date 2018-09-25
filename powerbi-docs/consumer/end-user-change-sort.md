---
title: Power BI -raportin kaavion lajittelutavan vaihtaminen
description: Power BI -raportin kaavion lajittelutavan vaihtaminen
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: dd8eeda3ba2bbc8da49a06199fa00dc3d731faaa
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565885"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI -raportin kaavion lajittelutavan vaihtaminen
Power BI -raportin avulla voit lajitella useimmat visualisoinnit aakkosjärjestykseen kaavion luokkien nimien mukaan tai kunkin luokan numeeristen arvojen mukaan. Tässä esimerkissä kaavio lajitellaan myymälän nimen mukaan.

![](media/end-user-change-sort/pbi_chartsortcategory.png)

Lajittelu on helppo vaihtaa luokasta (myymälän nimi) arvoon (myynti/neliöjalka).

1. Valitse kolme pistettä (...) ja valitse sitten **Lajitteluperuste: Myynti/neliöjalka**.
2. Valitse tarvittaessa lajittelukuvake ![](media/end-user-change-sort/sorticon.png) ja vaihda järjestykseksi **Laskeva**.

   ![](media/end-user-change-sort/sortby.gif)

   **HUOMAUTUS**: Kaikki visualisoinnit eivät ole lajiteltavissa.  Esimerkiksi seuraavia visualisointeja ei voi lajitella: Puukartta, Kartta, Täytetty kartta, Pistekaavio, Mittari, Kortti, Monirivinen kortti, Vesiputous.

## <a name="saving-changes-you-make-to-sort-order"></a>Lajittelujärjestyksen muutosten tallentaminen
Power BI -raportit säilyttävät suodattimet, osittajat, lajittelun ja muut tietojen näyttötapaan tekemäsi muutokset. Jos poistut raportista ja palaat myöhemmin takaisin, muutoksesi pysyvät voimassa.  Jos haluat palauttaa raportin laatijan asetukset takaisin käyttöön, valitse **Palauta oletukset** yläosan valikosta. 

![pysyvä lajittelu](./media/end-user-change-sort/power-bi-reset-to-default.png)

Jos **Palauta oletukset** -painike on harmaana, raportin tekijä on poistanut käytöstä mahdollisuuden tallentaa (pysyvät) muutokset.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Lajittelu muilla ehdoilla
Joskus visualisoinnin lajittelussa on käytettävä toista kenttää tai ehtoa.  Tarpeena voi olla esimerkiksi tietojen lajittelu kuukauden mukaan (eikä aakkosjärjestyksessä) tai vaikkapa koko numerojonon mukaan luvun sijasta (esimerkiksi 0, 1, 9, 20 eikä 0, 1, 20, 9).  

Joissakin tapauksissa visualisoinnin lajittelu voi onnistua halutulla tavalla esimerkiksi kuukauden mukaan.  Jos se ei onnistu, syynä voi olla se, että raportin taustalla oleva tietojoukko vaatii säätämistä. Seuraavassa on useita ratkaisuja:

* Käytä Power BI Desktopissa [Tietotyökalujen mallinnus -välilehteä lajittelemiseen toisen sarakkeen mukaan](../desktop-sort-by-column.md).
* Jos omistat tietojoukon Excelissä, lisää uusi sarake, joka liittää yhteen kuukauden nimen ja numeron. Päivitä tai tuo uudelleen tietojoukko, jotta uusi sarake näkyy Kentät-alueella.
* Varmista Excelissä, että numeeriset sarakkeet on merkitty kokonaisluvuksi tai desimaaliksi, eikä tekstiksi.

## <a name="next-steps"></a>Seuraavat vaiheet
Lue lisätietoja [Power BI -raporttien visualisoinneista](../visuals/power-bi-report-visualizations.md).

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
