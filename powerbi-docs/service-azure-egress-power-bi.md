---
title: Power BI:n ja Azuren lähtevä liikenne
description: Tutustu Azuren lähtevän liikenteen maksuihin ja Power BI:hin vuokraajan sijainnin ja Power BI Premiumin perusteella
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: 528d31a72d2c78b0a00f853d2df82f3a4eb04eae
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295329"
---
# <a name="power-bi-and-azure-egress"></a>Power BI:n ja Azuren lähtevä liikenne

Kun käytät Power BI:tä Azure-tietolähteiden kanssa, voit välttää Azuren lähtevän liikenteen maksut varmistamalla, että Power BI -vuokraajasi sijaitsee samalla alueella kuin Azure-tietolähteesi.

Kun Power BI-vuokraajasi otetaan käyttöön samalla Azure-alueella kuin tietolähteesikin, ajoitetuista päivitys- ja DirectQuery-vuorovaikutuksista ei peritä lähtevän liikenteen maksuja. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Power BI -vuokraajan sijainnin määrittäminen

Jos haluat tietää, missä Power BI -vuokraajasi sijaitsee, tutustu artikkeliin [Missä Power BI -vuokraajani sijaitsee](service-admin-where-is-my-tenant-located.md).

Jos olet Power BI Premiumin Multi-Geo -asiakas ja Power BI -vuokraajasi sijainti ei ole parhaimmassa mahdollisessa paikassa joidenkin Azure-pohjaisten tietolähteidesi kannalta, voit ottaa käyttöön Power BI Premiumin Multi-Geon haluamallasi Azure-alueella ja hyötyä siitä, että Power BI-vuokraajasi ja Azure-tietolähteesi sijaitsevat samalla Azure-alueella.

## <a name="next-steps"></a>Seuraavat vaiheet

Jos haluat lisätietoja Power BI Premiumista tai Multi-Geosta, tutustu seuraaviin resursseihin:

* [Mikä on Microsoft Power BI Premium?](service-premium.md)
* [Ohjeet Power BI Premiumin ostamiseen](service-admin-premium-purchase.md)
* [Power BI Premiumin Multi-Geo-tuki (esikatselu)](service-admin-premium-multi-geo.md)
* [Missä Power BI -vuokraajani sijaitsee?](service-admin-where-is-my-tenant-located.md)
* [Power BI Premiumin usein kysytyt kysymykset](service-premium-faq.md)


