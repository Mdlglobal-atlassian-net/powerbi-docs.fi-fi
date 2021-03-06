---
title: Vianmäärityksen lisätietojen kirjaaminen
description: Nämä ohjeet tarjoavat kaksi mahdollista vaihtoehtoa lisädiagnostiikkatietojen keräämisen manuaalisesti Power BI-verkkoasiakkaasta.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/17/2019
ms.author: kfollis
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 670373afb5cb890c87a24a129cd43fde7bd5d892
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83128898"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Power BI:n vianmäärityksen lisätietojen kirjaaminen

Tässä artikkelissa on ohjeita lisädiagnostiikkatietojen keräämisen manuaalisesti Power BI-verkkoasiakkaasta.

1. Selaa [Power BI:ta](https://app.powerbi.com) Microsoft Edgellä tai Internet Explorerilla.

1. Avaa Microsoft Edgen kehittäjien työkalut painamalla **F12**-näppäintä.

   ![Näyttökuva Microsoft Edgen kehittäjien työkalujen Elementit-välilehdestä.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. Valitse **Verkko**-välilehti. Se sisältää luettelon liikenteestä, joka on jo siepattu.

   ![Näyttökuva Microsoft Edgen kehittäjien työkalujen Verkko-välilehdestä.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Vaihtoehdot ovat:

    * Voit selata ikkunassa ja jäljentää mahdollisia eteen tulevia ongelmia.

    * Voit piilottaa ja näyttää Kehittäjän työkalut -ikkunan milloin tahansa istunnon aikana painamalla F12-näppäintä.

1. Voit lopettaa istunnon profiloinnin valitsemalla punaisen neliön Kehittäjien työkalut -alueella **Verkko**-välilehdessä.

   ![Näyttökuva Microsoft Edgen kehittäjien työkalujen Verkko-välilehdestä pysäytyspainike näkyvissä.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Valitse levykekuvake, jos haluat viedä tiedot HTTP Archive (HAR) -tiedostona.

   ![Näyttökuva Microsoft Edgen kehittäjien työkalujen Verkko-välilehdestä levykekuvake näkyvissä.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Anna tiedostonimi ja tallenna HAR-tiedosto.

    HAR-tiedosto sisältää kaikki tiedot verkkopyynnöistä selainikkunan ja Power BI:n välillä, mukaan lukien seuraavat tiedot:

    * kunkin pyynnön aktiviteettitunnukset

    * kunkin pyynnön tarkka aikaleima

    * asiakkaalle palautetut virhetiedot.

    Tämä jäljitys sisältää myös tiedot,  joita käytetään täyttämään näytössä näkyviä visualisointeja.

1. Voit hankkia HAR-tiedoston tukemaan tarkastelua.

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
