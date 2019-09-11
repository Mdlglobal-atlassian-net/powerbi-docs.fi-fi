---
title: Raportissa olevan kaavion lajittelutavan vaihtaminen
description: Power BI -raportin kaavion lajittelutavan vaihtaminen
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 08/21/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 98a91b0651e7a357f0ba0462f6ba8734c64ab162
ms.sourcegitcommit: 09ee1b4697aad84d8f4c9421015d7e4dbd3cf25f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/04/2019
ms.locfileid: "70302737"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI -raportin kaavion lajittelutavan vaihtaminen
Power BI -raportin avulla voit lajitella useimmat visualisoinnit aakkosjärjestykseen kaavion luokkien nimien mukaan tai kunkin luokan numeeristen arvojen mukaan. Tässä esimerkissä kaavio lajitellaan **myymälän nimi** -luokan mukaan.

![palkkikaavio, jonka X-akseli on lajiteltu aakkosjärjestykseen](media/end-user-change-sort/pbi_chartsortcategory.png)

Lajittelu on helppo vaihtaa luokasta (myymälän nimi) arvoon (myynti/neliöjalka).

1. Valitse kolme pistettä (...) ja valitse sitten **Lajitteluperuste > Myynti/neliöjalka**.
2. Valitse tarvittaessa uudelleen kolme pistettä ja valitse sitten **Lajittele laskevaan järjestykseen**.

   ![video, jolla näytetään Lajittelujärjestys-kohdan valitseminen ja Nouseva, Laskeva](media/end-user-change-sort/sort.gif)

> [!NOTE]
> Kaikki visualisoinnit eivät ole lajiteltavissa. Esimerkiksi seuraavia visualisointeja ei voi lajitella: Puukartta, Kartta, Täytetty kartta, Pistekaavio, Mittari, Kortti, Vesiputous.

## <a name="saving-changes-you-make-to-sort-order"></a>Lajittelujärjestyksen muutosten tallentaminen
Power BI -raportit säilyttävät suodattimet, osittajat, lajittelun ja muut tietojen näyttötapaan tekemäsi muutokset. Jos poistut raportista ja palaat myöhemmin takaisin, muutoksesi pysyvät voimassa.  Jos haluat palauttaa raportin suunnittelijan asetukset takaisin käyttöön, valitse **Palauta oletukset** ylemmältä valikkoriviltä. 

![pysyvä lajittelu](media/end-user-change-sort/power-bi-reset.png)

Jos **Palauta oletukset** -painike on harmaana, raportin suunnittelija on poistanut käytöstä mahdollisuuden tallentaa (pysyvät) muutokset.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Lajittelu muilla ehdoilla
Joskus visualisoinnin lajittelussa on käytettävä toista kenttää tai ehtoa.  Tarpeena voi olla esimerkiksi tietojen lajittelu kuukauden mukaan (eikä aakkosjärjestyksessä) tai vaikkapa koko numerojonon mukaan luvun sijasta (esimerkiksi 0, 1, 9, 20 eikä 0, 1, 20, 9).  

Joissakin tapauksissa visualisoinnin lajittelu voi onnistua halutulla tavalla esimerkiksi kuukauden mukaan.  Jos se ei onnistu, syynä voi olla se, että raportin taustalla oleva tietojoukko vaatii säätämistä. Pyydä raportin suunnittelijaa päivittämään tietojoukko.

## <a name="next-steps"></a>Seuraavat vaiheet
Lue lisätietoja [Power BI -raporttien visualisoinneista](end-user-visualizations.md).

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)
