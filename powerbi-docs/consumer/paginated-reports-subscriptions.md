---
title: Sivutettujen raporttien tilaaminen Power BI -palvelussa
description: Tässä artikkelissa kerrotaan, millaiset asiat sinun on pidettävä mielessä tilatessasi sivutettuja raportteja Power BI -palvelussa.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 12/03/2019
ms.openlocfilehash: c7f377c1295d4cd8f0d226331fcb6db697786e5a
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141265"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Power BI -palvelun sivutettujen raporttien tilaaminen itsellesi ja muille 

Voit nyt määrittää itsellesi ja muille sivutettujen raporttien sähköpostitilauksia Power BI -palvelussa. Prosessi on yleisesti samanlainen kuin [tilatessa raportteja ja raporttinäkymiä Power BI -palvelussa](end-user-subscribe.md). Tässä artikkelissa kerrotaan erot ja huomioitavat asiat. 

Kun määrität tilauksia, valitset kuinka usein haluat saada sähköpostiviestejä: päivittäin, viikoittain, kuukausittain tai tunneittain. Voit valita myös tilauksen suorittamisajan. Voit määrittää enintään 24 eri tilausta kullekin raportille. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Huomioitavaa sivutettujen raporttien tilauksessa 

- Toisin kuin raporttinäkymien tai Power BI -raporttien tilaukset, tilauksesi liite sisältää raportin täydelliset tulokset.  Tuetut liitetyypit ovat: PDF, PowerPoint-esitys (PPTX), Excel-työkirja (XLSX), Word-asiakirja (DOCX), CSV-tiedosto ja XML.

- Voit lisätä raportin esikatselukuvan sähköpostiviestin runkoon.  Tämä on valinnainen toimenpide, ja se voi muuttaa hieman liitetyn raporttiasiakirjan ensimmäistä sivua valitun liitetiedostomuodon mukaan. 

- Raportin liitteen enimmäiskoko on 25 Mt. 

- Voit tilata muille käyttäjille sivutettuja raportteja, jotka muodostavat yhteyden mihin tahansa tällä hetkellä tuettuun tietolähteeseen, kuten Azure Analysis Services -palveluihin tai Power BI -tietojoukkoihin. Muista, että raportin liite kuvastaa käyttöoikeuksiesi mukaisia tietoja, aivan kuten SQL Server Reporting Services -palveluissakin. 

- Sähköpostitilaukset voidaan lähettää joko valituilla nykyisillä parametreilla tai raportin oletusparametreilla.  Voit määrittää eri parametriarvoja kullekin raporttia varten luomallesi tilaukselle. 

- Jos raportin tekijä on määrittänyt lausekepohjaisia parametreja (esimerkiksi oletusarvo on aina nykyinen päivämäärä), tilauksessa käytetään sitä oletusarvona. Voit muuttaa muita parametriarvoja ja valita nykyisten arvojen käyttämisen, mutta ellet nimenomaisesti muuta myös kyseistä arvoa, tilauksessa käytetään lausekepohjaista parametria.

- Sivutettujen raporttien tapauksessa **Tietojen päivittämisen jälkeen** -vaihtoehto ei ole saatavilla. Saat aina taustalla olevan tietolähteen uusimmat arvot. 

## <a name="next-steps"></a>Seuraavat vaiheet

[Tilaa Power BI -palvelun raportteja ja raporttinäkymiä itsellesi ja muille](../collaborate-share/service-report-subscribe.md)

[Sivutetut raportit Power BI -palvelussa](end-user-paginated-report.md)
