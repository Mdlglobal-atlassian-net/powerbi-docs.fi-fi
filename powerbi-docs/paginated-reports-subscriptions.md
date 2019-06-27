---
title: Sivutettujen raporttien tilaaminen Power BI -palvelussa
description: Tässä artikkelissa kerrotaan, millaiset asiat sinun on pidettävä mielessä tilatessasi sivutettuja raportteja Power BI -palvelussa.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: 472606fcb3b823cdcb722c9d8d6421d0ec652d24
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/12/2019
ms.locfileid: "66839551"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Power BI -palvelun sivutettujen raporttien tilaaminen itsellesi ja muille 

Voit nyt määrittää itsellesi ja muille sivutettujen raporttien sähköpostitilauksia Power BI -palvelussa. Prosessi on yleisesti samanlainen kuin [tilatessa raportteja ja raporttinäkymiä Power BI -palvelussa](service-report-subscribe.md). Tässä artikkelissa kerrotaan erot ja huomioitavat asiat. 

Kun määrität tilauksia, valitset kuinka usein haluat saada sähköpostiviestejä: päivittäin, viikoittain tai tunneittain. Jos tilaat päivittäin tai viikoittain, voit valita kellonajan, jolloin tilausalgoritmi suoritetaan. Voit määrittää enintään 24 eri tilausta päivää kohden kullekin raportille. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Huomioitavaa sivutettujen raporttien tilauksessa 

- Toisin kuin raporttinäkymien tai Power BI -raporttien tilaukset, tilauksesi liite sisältää raportin täydelliset tulokset.  Tuetut liitetyypit ovat: PDF, PowerPoint-esitys (PPTX), Excel-työkirja (XLSX), Word-asiakirja (DOCX), CSV-tiedosto ja XML.

- Sähköpostiviestin runko ei sisällä raportin esikatselukuvaa.  Suunnitteilla on, että raportin ensimmäinen sivu näytettäisiin valinnaisena kohteena. 

- Raportin liitteen enimmäiskoko on 25 Mt. 

- Voit tilata muille käyttäjille sivutettuja raportteja, jotka muodostavat yhteyden mihin tahansa tällä hetkellä tuettuun tietolähteeseen, kuten Azure Analysis Services -palveluihin tai Power BI -tietojoukkoihin. Muista, että raportin liite kuvastaa käyttöoikeuksiesi mukaisia tietoja, aivan kuten SQL Server Reporting Services -palveluissakin. 

- Raporttisivujen tilaukset on sidottu raportin nimeen.  

- Sähköpostitilaukset lähetetään käyttäen raportin oletusarvoisia parametriarvoja. 

- Sivutettujen raporttien tapauksessa **Tietojen päivittämisen jälkeen** -vaihtoehto ei ole saatavilla. Saat aina taustalla olevan tietolähteen uusimmat arvot. 

## <a name="next-steps"></a>Seuraavat vaiheet

[Tilaa Power BI -palvelun raportteja ja raporttinäkymiä itsellesi ja muille](service-report-subscribe.md)

[Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
