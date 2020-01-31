---
title: Mallinäkymä Power BI Desktopissa
description: Mallinäkymä Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/17/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: ea568c061142e66e79351de8a6c0f0603a46f775
ms.sourcegitcommit: 08f65ea314b547b41b51afef6876e56182190266
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/25/2020
ms.locfileid: "76753217"
---
# <a name="work-with-model-view-in-power-bi-desktop"></a>Mallinäkymän käyttö Power BI Desktopissa

*Mallinäkymässä* näytetään kaikki mallin taulukot, sarakkeet ja suhteet. Tästä näkymästä voi olla hyötyä etenkin silloin, kun mallin monien taulukoiden välillä on monimutkaisia suhteita.

Jos haluat nähdä nykyisen mallin näkymän, valitse **Malli**-kuvake ikkunan vieressä. Voit näyttää käytetyt sarakkeet viemällä kohdistimen suhteen päälle.

![Mallinäkymä, Power BI Desktop](media/desktop-relationship-view/model-view-full-screen.png)

Kuvassa *Stores*-taulukossa on *StoreKey*-sarake, joka liittyy *Sales*-taulukkoon, jossa on myös *StoreKey*-sarake. Kahdessa taulukossa on *Monta yhteen* (\*: 1) -suhde. Rivin keskellä oleva nuoli osoittaa suodatinkontekstin työnkulun suunnan. Kaksi nuolta tarkoittaa, että ristiinsuodatuksen suunnaksi on määritetty *Molemmat*.

Voit avata suhteen **Muokkaa suhdetta** -valintaikkunassa kaksoisnapsauttamalla suhdetta. Lisätietoja suhteista on artikkelissa [Suhteiden luominen ja hallinta Power BI Desktopissa](desktop-create-and-manage-relationships.md).
