---
title: Miten järjestelmänvalvojat voivat hallita Power BI Desktopin kirjautumislomaketta
description: Lue, miten voit hallita ensimmäistä kirjautumislomaketta Power BI Desktopia avattaessa.
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 519f8b56b5086292addf577d969a707a6d6efcc8
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/09/2018
ms.locfileid: "30972997"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Miten järjestelmänvalvojat voivat hallita Power BI Desktopin kirjautumislomaketta
Kun Power BI Desktop käynnistetään ensimmäisen kerran, näyttöön tulee kirjautumislomake. Tiedot voidaan täyttää, tai voit jatkaa kirjautumalla Power BI:hin. Järjestelmänvalvojat voivat hallita tätä lomaketta rekisteriavaimen avulla. 

![Power BI Desktopin ensimmäinen kirjautumislomake](media/desktop-admin-sign-in-form/sign-in-form.png)

Järjestelmänvalvojat voivat poistaa kirjautumislomakkeen käytöstä seuraavalla rekisteriavaimella. Tämä voidaan poistaa myös koko organisaation globaaleilla käytännöillä.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

Arvo 0 poistaa valintaikkunan käytöstä.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

