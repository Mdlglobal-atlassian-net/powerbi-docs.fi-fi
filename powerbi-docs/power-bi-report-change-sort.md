---
title: Power BI -raportin kaavion lajittelutavan vaihtaminen
description: Power BI -raportin kaavion lajittelutavan vaihtaminen
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
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8160011a30b54345d446f352148665e3840323d9
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30974552"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI -raportin kaavion lajittelutavan vaihtaminen
Power BI -raportin avulla voit lajitella useimmat visualisoinnit aakkosjärjestykseen kaavion luokkien nimien mukaan tai kunkin luokan numeeristen arvojen mukaan. Tässä esimerkissä kaavio lajitellaan myymälän nimen mukaan.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

Lajittelu on helppo vaihtaa luokasta (myymälän nimi) arvoon (myynti/neliöjalka).

1. Valitse kolme pistettä (...) ja valitse sitten **Lajitteluperuste: Myynti/neliöjalka**.
2. Valitse tarvittaessa lajittelukuvake ![](media/power-bi-report-change-sort/sorticon.png) ja vaihda järjestykseksi **Laskeva**.

   ![](media/power-bi-report-change-sort/sortby.gif)

   **HUOMAUTUS**: Kaikki visualisoinnit eivät ole lajiteltavissa.  Esimerkiksi seuraavia visualisointeja ei voi lajitella: Puukartta, Kartta, Täytetty kartta, Pistekaavio, Mittari, Kortti, Monirivinen kortti, Vesiputous.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Lajittelu muilla ehdoilla
Joskus visualisoinnin lajittelussa on käytettävä toista kenttää tai ehtoa.  Tarpeena voi olla esimerkiksi tietojen lajittelu kuukauden mukaan (eikä aakkosjärjestyksessä) tai vaikkapa koko numerojonon mukaan luvun sijasta (esimerkiksi 0, 1, 9, 20 eikä 0, 1, 20, 9).  

Joissakin tapauksissa visualisoinnin lajittelu voi onnistua halutulla tavalla esimerkiksi kuukauden mukaan.  Jos se ei onnistu, syynä voi olla se, että raportin taustalla oleva tietojoukko vaatii säätämistä. Seuraavassa on useita ratkaisuja:

* Käytä Power BI Desktopissa [Tietotyökalujen mallinnus -välilehteä lajittelemiseen toisen sarakkeen mukaan](desktop-sort-by-column.md).
* Jos omistat tietojoukon Excelissä, lisää uusi sarake, joka liittää yhteen kuukauden nimen ja numeron. Päivitä tai tuo uudelleen tietojoukko, jotta uusi sarake näkyy Kentät-alueella.
* Varmista Excelissä, että numeeriset sarakkeet on merkitty kokonaisluvuksi tai desimaaliksi, eikä tekstiksi.

## <a name="next-steps"></a>Seuraavat vaiheet
Lue lisätietoja [Power BI -raporttien visualisoinneista](power-bi-report-visualizations.md).

[Power BI:n peruskäsitteet](service-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
