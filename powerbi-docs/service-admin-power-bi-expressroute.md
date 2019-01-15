---
title: Power BI ja ExpressRoute
description: Power BI ja ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 0c4618150094a4eabb0dc9745e9ac93e4f342ff1
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291092"
---
# <a name="power-bi-and-expressroute"></a>Power BI ja ExpressRoute

**ExpressRoute** on Azure-palvelu, jonka avulla voit luoda yksityisen yhteyden Azure tietokeskuksen (jossa Power BI sijaitsee) ja paikallisen infrastruktuurin väliset yhteydet, tai luoda yksityiset yhteydet Azure palvelinkeskusten ja yhdistävän sijoittamisen välillä.

**Power BI:n** ja **ExpressRouteb** avulla voit luoda yksityisen verkkoyhteyden omasta yrityksestä Power BI:lle (tai palveluntarjoajan ulkoistamisominaisuutta käyttämällä), ohittamalla Internetin suojataksesi entistä paremmin luottamuksellisia Power BI -tietoja ja yhteyksiä.

Saat lisätietoja [ExpressRouten yleiskatsauksesta](/azure/expressroute/expressroute-introduction). Power BI on yhteensopiva ExpressRouten kanssa muutamaa poikkeusta lukuun ottamatta, joissa Power BI noutaa tai lähettää tietoja julkisessa Internetissä. Tarkista luettelo [Power BI:n käyttämistä URL-osoitteista](power-bi-whitelist-urls.md).

![ExpressRoute-kaavio](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)