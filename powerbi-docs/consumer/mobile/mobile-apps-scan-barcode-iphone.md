---
title: Viivakoodin lukeminen Power BI -mobiilisovelluksesta
description: Voit skannata viivakoodeja todellisessa maailmassa ja siirtyä suoraan suodatettuihin BI-tietoihin Power BI -mobiilisovelluksessa.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 12/02/2019
ms.author: painbar
ms.openlocfilehash: dfe5e6350d0209f836900a921aadc5347b181766
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276164"
---
# <a name="scan-a-barcode-with-your-device-from-the-power-bi-mobile-app"></a>Viivakoodin lukeminen laitteella Power BI -mobiilisovelluksesta
Voit skannata viivakoodeja todellisessa maailmassa ja siirtyä suoraan suodatettuihin BI-tietoihin Power BI -mobiilisovelluksessa.


Koskee seuraavia:

| ![iPhone](./media/mobile-apps-qr-code/ios-logo-40-px.png) | ![iPadit](./media/mobile-apps-qr-code/ios-logo-40-px.png) | ![Android-puhelin](././media/mobile-apps-qr-code/android-logo-40-px.png) | ![Android-tabletti](././media/mobile-apps-qr-code/android-logo-40-px.png) |
|:--- |:--- |:--- |:--- |
|iPhonet |iPadit |Android-puhelimet |Android-tabletit |

Työtoverisi on saattanut esimerkiksi [merkitä viivakoodikentän raporttiin Power BI Desktopissa](../../transform-model/desktop-mobile-barcodes.md) ja jakaa raportin kanssasi. 

![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-scanner.png)

Kun luet tuotteen viivakoodin laitteen Power BI -sovelluksen skannerilla, näet raportin (tai raporttien luettelon) kyseisellä viivakoodilla. Voit avata raportin kyseiseen viivakoodiin suodatettuna.

## <a name="scan-a-barcode-with-the-power-bi-scanner"></a>Viivakoodin skannaaminen Power BI -skannerilla
1. Napauta siirtymispalkissa **Lisää vaihtoehtoja** (...) ja napauta sitten **Skanneri**.

    ![](media/mobile-apps-scan-barcode-iphone/power-bi-scanner.png)

2. Jos kamerasi ei ole käytössä, sinun on sallittava Power BI -sovellukselle kameran käyttö. Tämä on yhden kerran suoritettava hyväksyntä. 
4. Osoita skannerilla tuotteen viivakoodia. Näkyviin tulee luettelo kyseiseen viivakoodiin liittyvistä raporteista.
5. Napauta raportin nimeä avataksesi sen laitteessasi. Raportti suodattuu automaattisesti kyseisen viivakoodin mukaan.

## <a name="filter-by-other-barcodes-while-in-a-report"></a>Suodattaminen muiden viivakoodien perusteella raportissa
Tarkastellessasi viivakoodilla suodatettua raporttia laitteellasi haluat ehkä suodattaa saman raportin eri viivakoodilla.

* Jos viivakoodin kuvakkeessa on suodatin ![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-filtered-icon-black.png), suodatin on aktiivinen ja raportti on jo suodatettu viivakoodilla. 
* Jos kuvakkeessa ei ole suodatinta ![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-unfiltered-icon.png), suodatin ei ole aktiivinen ja raporttia ei ole suodatettu viivakoodilla. 

Kummassakin tapauksessa napauta kuvaketta avataksesi pienen valikon, jossa on irrallinen skanneri.

* Kohdista skanneri uuteen kohteeseen vaihtaaksesi raportin suodattimen eri viivakoodin arvoon. 
* Valitse **Tyhjennä viivakoodisuodatin** palataksesi suodattamattomaan raporttiin.
* Valitse **Suodata viimeaikaisten viivakoodien mukaan** vaihtaaksesi raportin suodattimen viivakoodiin, jonka olet skannannut nykyisessä istunnossa.

## <a name="issues-with-scanning-a-barcode"></a>Ongelmia viivakoodin skannaamisessa
Seuraavassa on joitakin sanomia, joita näyttöön saattaa tulla, kun skannaat tuotteen viivakoodia.

### <a name="couldnt-filter-report"></a>”Raporttia ei voitu suodattaa...”
Raportti, jonka haluat suodattaa, perustuu tietomalliin, joka ei sisällä tätä viivakoodiarvoa. Esimerkiksi tuote ”kivennäisvesi” ei sisälly raporttiin.  

### <a name="allsome-of-the-visuals-in-the-report-dont-contain-any-value"></a>Raportin kaikki tai jotkin visualisoinnit eivät sisällä mitään arvoa
Skannattu viivakoodiarvo on olemassa mallissa, mutta raportin kaikki tai jotkin visualisoinnit eivät sisällä tätä arvoa, ja siksi suodatus palauttaa tyhjän tilan. Yritä tarkastella raportin muita sivuja arvon osalta tai muokata raporttejasi Power BI Desktopissa 

### <a name="looks-like-you-dont-have-any-reports-that-can-be-filtered-by-barcodes"></a>”Vaikuttaa siltä, ettei sinulla ole raportteja, jotka voidaan suodattaa viivakoodien avulla.”
Tämä tarkoittaa, että sinulla ei ole viivakoodia käyttäviä raportteja. Viivakoodiskanneri voi suodattaa vain raportteja, joissa on **Viivakoodi**-sarake.  

Varmista, että sinä tai raportin omistaja on merkinnyt **Viivakoodi**-nimisen sarakkeen Power BI Desktopissa. Lue lisätietoja [viivakoodikentän merkitsemisestä Power BI Desktopissa](../../transform-model/desktop-mobile-barcodes.md)

### <a name="couldnt-filter-report---looks-like-this-barcode-doesnt-exist-in-the-report-data"></a>”Raporttia ei voitu suodattaa – Vaikuttaa siltä, että tätä viivakoodia ei ole raportin tiedoissa.”
Raportti, jonka haluat suodattaa, perustuu tietomalliin, joka ei sisällä tätä viivakoodiarvoa. Esimerkiksi tuote ”kivennäisvesi” ei sisälly raporttiin. Voit skannata eri tuotteen, valita eri raportin (jos useampi kuin yksi raportti on käytettävissä) tai tarkastella raporttia suodattamattomana. 

## <a name="next-steps"></a>Seuraavat vaiheet
* [Viivakoodikentän merkitseminen Power BI Desktopissa](../../transform-model/desktop-mobile-barcodes.md)
* [Koontinäyttöruudut Power BI:ssä](../end-user-tiles.md)
* [Koontinäytöt Power BI:ssä](../end-user-dashboards.md)
