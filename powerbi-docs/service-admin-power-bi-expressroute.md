---
title: Power BI ja ExpressRoute
description: Power BI ja ExpressRoute
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 59ddddcf1b02f07b850294fa314b7508f7f9fcdc
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73856963"
---
# <a name="power-bi-and-expressroute"></a>Power BI ja ExpressRoute

**ExpressRoute** on Azure-palvelu, jonka avulla voit luoda yksityisen yhteyden Azure tietokeskuksen (jossa Power BI sijaitsee) ja paikallisen infrastruktuurin väliset yhteydet, tai luoda yksityiset yhteydet Azure palvelinkeskusten ja yhdistävän sijoittamisen välillä.

**Power BI:n** ja **ExpressRouteb** avulla voit luoda yksityisen verkkoyhteyden omasta yrityksestä Power BI:lle (tai palveluntarjoajan ulkoistamisominaisuutta käyttämällä), ohittamalla Internetin suojataksesi entistä paremmin luottamuksellisia Power BI -tietoja ja yhteyksiä.

Saat lisätietoja [ExpressRouten yleiskatsauksesta](/azure/expressroute/expressroute-introduction). Power BI on yhteensopiva ExpressRouten kanssa muutamaa poikkeusta lukuun ottamatta, joissa Power BI noutaa tai lähettää tietoja julkisessa Internetissä. Tarkista luettelo [Power BI:n käyttämistä URL-osoitteista](power-bi-whitelist-urls.md).

![ExpressRoute-kaavio](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)