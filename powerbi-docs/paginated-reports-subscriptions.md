---
title: Sivutetut raportit Power BI-palvelussa tilaaminen
description: Tässä artikkelissa opit seuraavat asiat mielessä tietoja tilaaminen sivutetut raportit Power BI-palvelussa.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: ccec6658808d94728f2a4f14de67c36da0f51def
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222189"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Tilaa itsellesi ja muille sivutetut raportit Power BI-palvelussa 

Voit nyt määrittää itsellesi ja muille Sivutettujen raporttien sähköpostitilaukset Power BI-palvelussa. Yleensä prosessi on sama kuin [tilaaminen raportteja ja koontinäyttöjä Power BI-palvelussa](service-report-subscribe.md). Tässä artikkelissa havainnollisesti eroista ja huomioon otettavia seikkoja. 

Määritetään tilaukset, valitse kuinka usein haluat saada sähköpostiviestit: päivittäin, viikoittain tai tunnittaisten. Jos valitset päivittäin tai viikoittain, voit valita aika haluat suorittaa tilaus. Voit määrittää enintään 24 eri tilauksissa jokaisen raportin päivässä. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Sivutetun raportin tilauksia huomioitavat seikat 

- Toisin kuin koontinäyttöjen tai Power BI-raporttien tilaukset tilauksesi sisältää liitteen koko raportin tulos.  Liitteen seuraavista tuetaan: PDF-Muotoon, PowerPoint-esityksenä (PPTX), Excel-työkirjan (XLSX), Word-asiakirja (DOCX), CSV-tiedosto ja XML.

- Ei sähköpostiviestin teksti raportin ei ole esikatselukuva.  Olemme suunnittelu on valinnainen kohteena raportin ensimmäisen sivun kuva. 

- Suurin raportin liitteen koko on 25 Mt. 

- Voit tilata muille käyttäjille sivutetut raportit, jotka muodostavat yhteyden tällä hetkellä tuetun tietolähteitä, mukaan lukien Azure Analysis Services- tai Power BI-tietojoukot. Pidä mielessä, raportin liitteen vastaa-käyttöoikeudet tietoja samaan tapaan kuin SQL Server Reporting Services-tänään. 

- Raporttisivujen tilaukset on sidottu raportin nimi.  

- Sähköpostitilaukset lähetetään käyttäen raportin parametrien oletusarvot. 

- Ei ole **jälkeen tietojen päivittämisen** vaihtoehto taajuuden sivutetuissa raporteissa. Saat uusimmat arvot aina taustalla olevaan tietolähteeseen. 

## <a name="next-steps"></a>Seuraavat vaiheet

[Tilaa itsellesi ja muille raportteja ja koontinäyttöjä Power BI-palvelussa](service-report-subscribe.md)

[Mitä ovat sivutetut raportit Power BI Premiumissa? (esikatselu)](paginated-reports-report-builder-power-bi.md)
