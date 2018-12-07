---
title: Power BI ja ExpressRoute
description: Power BI ja ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 62289c974e25207f3a991e7f17a0ee965c729b8a
ms.sourcegitcommit: b03912343a5a214c6bb972aaa6aa051c2a5f4332
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/05/2018
ms.locfileid: "52900125"
---
# <a name="power-bi-and-expressroute"></a>Power BI ja ExpressRoute

**ExpressRoute** on Azure-palvelu, jonka avulla voit luoda yksityisen yhteyden Azure tietokeskuksen (jossa Power BI sijaitsee) ja paikallisen infrastruktuurin väliset yhteydet, tai luoda yksityiset yhteydet Azure palvelinkeskusten ja yhdistävän sijoittamisen välillä.

**Power BI:n** ja **ExpressRouten** avulla voit luoda yksityisen verkkoyhteyden omasta yrityksestä Power BI:lle (tai palveluntarjoajan ulkoistamisominaisuutta käyttämällä), ohittamalla Internetin suojataksesi entistä paremmin luottamuksellisia Power BI -tietoja ja yhteyksiä.

Saat lisätietoja [ExpressRouten yleiskatsauksesta](/azure/expressroute/expressroute-introduction). Power BI on yhteensopiva ExpressRouten kanssa muutamaa poikkeusta lukuun ottamatta, joissa Power BI noutaa tai lähettää tietoja julkisessa Internetissä. Tarkista luettelo [Power BI:n käyttämistä URL-osoitteista](power-bi-whitelist-urls.md).

![ExpressRoute-kaavio](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)