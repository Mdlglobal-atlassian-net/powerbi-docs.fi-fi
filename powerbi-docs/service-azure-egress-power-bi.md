---
title: Power BI:n ja Azuren lähtevä liikenne
description: Tutustu Azuren lähtevän liikenteen maksuihin ja Power BI:hin vuokraajan sijainnin ja Power BI Premiumin perusteella
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: 17175e1accb5013b960c5e1a71ae036b3dda72f3
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73855582"
---
# <a name="power-bi-and-azure-egress"></a>Power BI:n ja Azuren lähtevä liikenne

Kun käytät Power BI:tä Azure-tietolähteiden kanssa, voit välttää Azuren lähtevän liikenteen maksut varmistamalla, että Power BI -vuokraajasi sijaitsee samalla alueella kuin Azure-tietolähteesi.

Kun Power BI-vuokraajasi otetaan käyttöön samalla Azure-alueella kuin tietolähteesikin, ajoitetuista päivitys- ja DirectQuery-vuorovaikutuksista ei peritä lähtevän liikenteen maksuja. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Power BI -vuokraajan sijainnin määrittäminen

Jos haluat tietää, missä Power BI -vuokraajasi sijaitsee, tutustu artikkeliin [Missä Power BI -vuokraajani sijaitsee](service-admin-where-is-my-tenant-located.md).

Jos olet Power BI Premiumin Multi-Geo -asiakas ja Power BI -vuokraajasi sijainti ei ole parhaimmassa mahdollisessa paikassa joidenkin Azure-pohjaisten tietolähteidesi kannalta, voit ottaa käyttöön Power BI Premiumin Multi-Geon haluamallasi Azure-alueella ja hyötyä siitä, että Power BI-vuokraajasi ja Azure-tietolähteesi sijaitsevat samalla Azure-alueella.

## <a name="next-steps"></a>Seuraavat vaiheet

Jos haluat lisätietoja Power BI Premiumista tai Multi-Geosta, tutustu seuraaviin resursseihin:

* [Mikä on Microsoft Power BI Premium?](service-premium-what-is.md)
* [Ohjeet Power BI Premiumin ostamiseen](service-admin-premium-purchase.md)
* [Power BI Premiumin Multi-Geo-tuki (esikatselu)](service-admin-premium-multi-geo.md)
* [Missä Power BI -vuokraajani sijaitsee?](service-admin-where-is-my-tenant-located.md)
* [Power BI Premiumin usein kysytyt kysymykset](service-premium-faq.md)


