---
title: Power BI:n visualisointien kehittynyt muokkaustila
description: Tässä artikkelissa kerrotaan, miten voit määrittää käyttöliittymän ohjausobjektit Power BI:n visualisoinneissa.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 97242883fe90c8f5e115818a24e4bb1c49f69b77
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380550"
---
# <a name="advanced-edit-mode-in-power-bi-visuals"></a>Power BI:n visualisointien kehittynyt muokkaustila

Jos tarvitset kehittyneitä käyttöliittymän ohjausobjekteja Power BI:n visualisoinnissa, voit hyödyntää kehittynyttä muokkaustilaa. Kun olet raportin muokkaustilassa, valitse **Muokkaa**-painike ja määritä muokkaus tilaksi **Kehittynyt**. Visualisointi voi käyttää `EditMode`-merkintää määrittääkseen, tuleeko sen näyttää tämä käyttöliittymän ohjausobjekti.

Visualisointi ei oletusarvoisesti tue muokkaustilan lisäasetuksia. Jos vaaditaan erilaista käyttäytymistä, se on määritettävä eksplisiittisesti visualisoinnin tiedostossa *capabilities.json* asettamalla ominaisuus `advancedEditModeSupport`.

Mahdolliset arvot ovat:

- `0` – NotSupported

- `1` – SupportedNoAction

- `2` – SupportedInFocus

## <a name="enter-advanced-edit-mode"></a>Siirtyminen kehittyneeseen muokkaustilaan

Näkyvissä on **Muokkaa**-painike, jos:

* `advancedEditModeSupport`-ominaisuuden asetukseksi tiedostossa *capabilities.json* on määritetty `SupportedNoAction` tai `SupportedInFocus`.

* Visualisointia tarkastellaan raportin muokkaustilassa.

Jos `advancedEditModeSupport`-ominaisuus puuttuu tiedostosta *capabilities.json* tai jos sen asetuksena on `NotSupported`, **Muokkaa**-painike ei ole näkyvissä.

![Siirry muokkaustilaan](media/advanced-edit-mode/edit-mode.png)

Kun valitset **Muokkaa**, visualisointi saa update()-kutsun, jossa EditMode-asetuksena on `Advanced`. Sen mukaan, mikä arvo on määritetty *capabilities.json*-tiedostossa, seuraavat toiminnot toteutetaan:

* `SupportedNoAction`: Isäntä ei vaadi lisätoimia.
* `SupportedInFocus`: Isäntä avaa visualisoinnin tarkastelutilaan.

## <a name="exit-advanced-edit-mode"></a>Poistuminen kehittyneestä muokkaustilasta

**Takaisin raporttiin** -painike on näkyvissä, jos:

* `advancedEditModeSupport`-ominaisuuden asetukseksi tiedostossa *capabilities.json* on määritetty `SupportedInFocus`.
