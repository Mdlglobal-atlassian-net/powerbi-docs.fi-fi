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
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61187866"
---
# <a name="power-bi-and-expressroute"></a>Power BI ja ExpressRoute

**ExpressRoute** on Azure-palvelu, jonka avulla voit luoda yksityisen yhteyden Azure tietokeskuksen (jossa Power BI sijaitsee) ja paikallisen infrastruktuurin väliset yhteydet, tai luoda yksityiset yhteydet Azure palvelinkeskusten ja yhdistävän sijoittamisen välillä.

**Power BI:n** ja **ExpressRouteb** avulla voit luoda yksityisen verkkoyhteyden omasta yrityksestä Power BI:lle (tai palveluntarjoajan ulkoistamisominaisuutta käyttämällä), ohittamalla Internetin suojataksesi entistä paremmin luottamuksellisia Power BI -tietoja ja yhteyksiä.

Saat lisätietoja [ExpressRouten yleiskatsauksesta](/azure/expressroute/expressroute-introduction). Power BI on yhteensopiva ExpressRouten kanssa muutamaa poikkeusta lukuun ottamatta, joissa Power BI noutaa tai lähettää tietoja julkisessa Internetissä. Tarkista luettelo [Power BI:n käyttämistä URL-osoitteista](power-bi-whitelist-urls.md).

![ExpressRoute-kaavio](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)