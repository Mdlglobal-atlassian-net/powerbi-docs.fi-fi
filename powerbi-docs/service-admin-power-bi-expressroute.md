---
title: Power BI ja ExpressRoute
description: Power BI ja ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c7d12bf6a1a2a02c988f8351a1844be1080ad2b8
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074790"
---
# <a name="power-bi-and-expressroute"></a>Power BI ja ExpressRoute

**ExpressRoute** on Azure-palvelu, jonka avulla voit luoda yksityisen yhteyden Azure tietokeskuksen (jossa Power BI sijaitsee) ja paikallisen infrastruktuurin väliset yhteydet, tai luoda yksityiset yhteydet Azure palvelinkeskusten ja yhdistävän sijoittamisen välillä.

**Power BI:n** ja **ExpressRouteb** avulla voit luoda yksityisen verkkoyhteyden omasta yrityksestä Power BI:lle (tai palveluntarjoajan ulkoistamisominaisuutta käyttämällä), ohittamalla Internetin suojataksesi entistä paremmin luottamuksellisia Power BI -tietoja ja yhteyksiä.

Saat lisätietoja [ExpressRouten yleiskatsauksesta](/azure/expressroute/expressroute-introduction). Power BI on yhteensopiva ExpressRouten kanssa muutamaa poikkeusta lukuun ottamatta, joissa Power BI noutaa tai lähettää tietoja julkisessa Internetissä. Tarkista luettelo [Power BI:n käyttämistä URL-osoitteista](power-bi-whitelist-urls.md).

![ExpressRoute-kaavio](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)