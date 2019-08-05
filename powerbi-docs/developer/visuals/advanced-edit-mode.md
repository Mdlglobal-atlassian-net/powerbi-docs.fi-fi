---
title: Muokkaustilan lisäasetukset
description: Power BI:n visualisoinnit, joissa on edistyneet käyttöliittymän ohjaustoiminnot
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 625105aed773bce5cf70932f092faf60ea001c2c
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425547"
---
# <a name="advanced-edit-mode"></a>Muokkaustilan lisäasetukset

Edistyneitä käyttöliittymän ohjaustoimintoja edellyttävät visualisoinnit voivat määrittää muokkaustilan lisäasetusten tuen.
Jos se on tuettu, raportin muokkaustilassa visualisoinnin valikkoon ilmestyy `Edit`-painike.
Kun `Edit`-painiketta napsautetaan, EditModen asetukseksi tulee `Advanced`.
Visualisointi voi käyttää EditMode-lippua määrittääkseen, tuleeko nämä käyttöliittymän ohjausobjektit näyttää.

Visualisointi ei oletusarvoisesti tue muokkaustilan lisäasetuksia.
Jos vaaditaan erilaista käyttäytymistä, se on määritettävä eksplisiittisesti visualisoinnin tiedostossa `capabilities.json` asettamalla ominaisuus `advancedEditModeSupport`.

Mahdolliset arvot ovat:

- 0 - NotSupported

- 1 - SupportedNoAction

- 2 - SupportedInFocus

## <a name="entering-advanced-edit-mode"></a>Siirtyminen muokkaustilan lisäasetuksiin

`Edit`-painike on näkyvissä, jos:

 1– `advancedEditModeSupport`-ominaisuus tiedostossa capabilities.json on joko `SupportedNoAction` tai `SupportedInFocus`.

 2– visualisointia tarkastellaan raportin muokkaustilassa.

Jos `advancedEditModeSupport`-ominaisuus puuttuu tiedostosta capabilities.json tai jos sen asetuksena on `NotSupported`, Muokkaa-painike poistuu näkyvistä.

![Siirry muokkaustilaan](./media/edit-mode.png)

Kun käyttäjä napsauttaa kohtaa `Edit`, visualisointi saa update()-kutsun, jossa EditModen asetuksena on `Advanced`.
Seuraavat toiminnot toteutuvat ominaisuuksiin määritetyn arvon mukaan:

* `SupportedNoAction` – Ei isännän lisätoimia.
* `SupportedInFocus` – Isäntä avaa visualisoinnin kohdistustilaan.

## <a name="exiting-advanced-edit-mode"></a>Poistuminen kehittyneestä muokkaustilasta

`Back to report`-painike on näkyvissä, jos:

1 – `advancedEditModeSupport`-ominaisuus kohteessa capabilities.json on `SupportedInFocus`.
