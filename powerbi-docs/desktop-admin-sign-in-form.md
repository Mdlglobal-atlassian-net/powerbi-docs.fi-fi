---
title: Miten järjestelmänvalvojat voivat hallita Power BI Desktopin kirjautumislomaketta
description: Lue, miten voit hallita ensimmäistä kirjautumislomaketta Power BI Desktopia avattaessa.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
ms.openlocfilehash: a61075993afaa75aea420f55babc773dec075f73
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280885"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Miten järjestelmänvalvojat voivat hallita Power BI Desktopin kirjautumislomaketta
Kun Power BI Desktop käynnistetään ensimmäisen kerran, näyttöön tulee kirjautumislomake. Tiedot voidaan täyttää, tai voit jatkaa kirjautumalla Power BI:hin. Järjestelmänvalvojat hallitsevat tätä lomaketta rekisteriavaimen avulla. 

![Power BI Desktopin ensimmäinen kirjautumislomake](media/desktop-admin-sign-in-form/sign-in-form.png)

Järjestelmänvalvojat poistavat kirjautumislomakkeen käytöstä seuraavalla rekisteriavaimella. Tämä voidaan poistaa myös koko organisaatiosta globaaleilla käytännöillä.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

Arvo 0 poistaa valintaikkunan käytöstä.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

