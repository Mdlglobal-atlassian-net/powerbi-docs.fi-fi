---
title: Sieppaa lisätietojen
description: Nämä ohjeet tarjoavat kaksi mahdollista vaihtoehtoa lisädiagnostiikkatietojen keräämisen manuaalisesti Power BI-verkkoasiakkaasta.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 710fb4cdcf9efb051434966d47c2eaced17ac9ba
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100196"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Sieppaa lisätietojen Power BI

Tässä artikkelissa on ohjeet keräämisen manuaalisesti Power BI-WWW-asiakkaasta lisätietojen.

1. Siirry [Power BI](https://app.powerbi.com) Microsoft Edgen tai Internet Explorerin kanssa.

1. Paina **F12** Avaa Microsoft Edge-Kehitystyökalut.

   ![Microsoft Edge Developer näyttökuva Työkalut osat-välilehti.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. Valitse **Verkko**-välilehti. Se sisältää luettelon liikenteestä, joka on jo siepattu.

   ![Microsoft Edge Developer näyttökuva Työkalut verkko-välilehdelle.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Vaihtoehdot ovat:

    * Selata ikkunassa ja jäljentää saattavat olla välillä.

    * Piilottaa ja näyttää kehittäjän työkalut-ikkunan milloin tahansa istunnon aikana painamalla F12.

1. Lopeta istunto profilointi, voit valita punaisen neliön **verkon** välilehdessä kehittäjän työkalut alue.

   ![Microsoft Edge Developer näyttökuva Työkalut verkko-välilehdelle kutsulla ulos Pysäytä-painiketta.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Valitse Vie tiedot HTTP-arkisto (HAR)-tiedostona mukainen-kuvake.

   ![Microsoft Edge Developer näyttökuva Työkalut verkko-välilehdelle kuvatekstin mukainen-kuvakkeen kanssa.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Anna tiedostonimi ja tallenna HAR-tiedosto.

    HAR-tiedosto sisältää kaikki tiedot verkkopyynnöistä selainikkunan ja Power BI mukaan lukien välillä:

    * Aktiivisuustunnukset kullekin pyynnölle.

    * Aikaleiman kullekin pyynnölle.

    * Asiakkaalle palautetut virhetiedot.

    Tämä jäljitys sisältää myös tiedot,  joita käytetään täyttämään näytössä näkyviä visualisointeja.

1. Voit hankkia HAR-tiedoston tukemaan tarkastelua.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
