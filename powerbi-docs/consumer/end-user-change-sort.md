---
title: Raportissa olevan kaavion lajittelutavan vaihtaminen
description: Power BI -raportin kaavion lajittelutavan vaihtaminen
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/28/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: e325d13dd8001e8da41dc5602bf3f7dbba2f371f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73852379"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI -raportin kaavion lajittelutavan vaihtaminen

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Voit muuttaa visualisoinnin ulkoasua Power BI -palvelussa lajittelemalla sen eri tietokenttien mukaan. Muuttamalla visualisoinnin lajittelua voit korostaa välitettäviä tietoja ja varmistaa, että visualisointi kuvastaa tätä trendiä (tai tietoa).

Voit lajitella visualisoinnit haluamallasi tavalla ja muokata niiden ulkoasua, olipa käytössä siten numeerisia tietoja (kuten myyntilukuja) tai tekstiä (kuten osavaltioiden nimiä). Power BI tarjoaa käyttöösi joustavat lajitteluvaihtoehdot ja pikavalikot. Valitse missä tahansa visualisoinnissa **Lisää toimintoja** (...), ja valitse sitten kenttä, jonka mukaan haluat lajitella.

![palkkikaavio, jonka X-akseli on lajiteltu aakkosjärjestykseen](media/end-user-change-sort/power-bi-more-actions.png)

Koontinäytössä olevia visualisointeja ei voi lajitella, mutta Power BI -raportissa voit lajitella useimmat visualisoinnit aakkosjärjestykseen kaavion luokkien nimien mukaan tai kunkin luokan numeeristen arvojen mukaan. Tässä esimerkissä kaavio on lajiteltu aakkosjärjestykseen **myymälän nimi** -luokan mukaan.

![palkkikaavio, jonka X-akseli on lajiteltu aakkosjärjestykseen](media/end-user-change-sort/pbi-chartsortcategory.png)

Lajittelu on helppo vaihtaa luokasta (myymälän nimi) arvoon (myynti/neliöjalka).

1. Valitse **Lisää toimintoja** (...) ja valitse sitten **Lajitteluperuste > Myynti/neliöjalka**.
2. Valitse tarvittaessa uudelleen **Lisää toimintoja** ja valitse sitten **Lajittele laskevaan järjestykseen**. Lajitteluperusteena oleva kenttä näkyy lihavoituna ja siinä on keltainen palkki.

   ![video, jolla näytetään Lajittelujärjestys-kohdan valitseminen ja Nouseva, Laskeva](media/end-user-change-sort/sort.gif)

> [!NOTE]
> Kaikki visualisoinnit eivät ole lajiteltavissa. Esimerkiksi seuraavia visualisointeja ei voi lajitella: Puukartta, Kartta, Täytetty kartta, Pistekaavio, Mittari, Kortti, Vesiputous.

## <a name="saving-changes-you-make-to-sort-order"></a>Lajittelujärjestyksen muutosten tallentaminen
Power BI -raportit säilyttävät suodattimet, osittajat, lajittelun ja muut tietojen näyttötapaan tekemäsi muutokset. Jos poistut raportista ja palaat myöhemmin takaisin, muutoksesi pysyvät voimassa.  Jos haluat palauttaa raportin suunnittelijan asetukset takaisin käyttöön, valitse **Palauta oletukset** ylemmältä valikkoriviltä. 

![pysyvä lajittelu](media/end-user-change-sort/power-bi-reset.png)

Jos **Palauta oletukset** -painike on harmaana, raportin suunnittelija on poistanut käytöstä mahdollisuuden tallentaa (pysyvät) muutokset.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Lajittelu muilla ehdoilla
Joskus visualisoinnin lajittelussa on käytettävä toista kenttää (joka ei sisälly visualisointiin) tai ehtoa.  Tarpeena voi olla esimerkiksi tietojen lajittelu kuukauden mukaan (eikä aakkosjärjestyksessä) tai vaikkapa koko numerojonon mukaan luvun sijasta (esimerkiksi 0, 1, 9, 20 eikä 0, 1, 20, 9).  Raportin suunnittelija voi päivittää tietojoukon, jotta tällainen lajittelu voidaan ottaa käyttöön. Suunnittelijan yhteystiedot löytyvät valitsemalla raportin nimi otsikkoriviltä.

![Valikko, joka näyttää yhteystiedot](media/end-user-change-sort/power-bi-contact.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Lue lisätietoja [Power BI -raporttien visualisoinneista](end-user-visualizations.md).

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)
