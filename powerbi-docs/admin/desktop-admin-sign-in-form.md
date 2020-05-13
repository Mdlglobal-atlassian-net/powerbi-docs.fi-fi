---
title: Miten järjestelmänvalvojat voivat hallita Power BI Desktopin kirjautumislomaketta
description: Lue, miten voit hallita ensimmäistä kirjautumislomaketta Power BI Desktopia avattaessa.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 934827311e089e34e56fbcffe4d4c58a056df4ad
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83130225"
---
# <a name="administrators-manage-the-power-bi-desktop-sign-in-form"></a>Järjestelmänvalvojat: Power BI Desktopin kirjautumislomakkeen halinta
Kun Power BI Desktop käynnistetään ensimmäisen kerran, näyttöön tulee kirjautumislomake. Tiedot voidaan täyttää, tai voit jatkaa kirjautumalla Power BI:hin. Järjestelmänvalvojat hallitsevat tätä lomaketta rekisteriavaimen avulla. 

![Power BI Desktopin ensimmäinen kirjautumislomake](media/desktop-admin-sign-in-form/sign-in-form.png)

Järjestelmänvalvojat poistavat kirjautumislomakkeen käytöstä seuraavalla rekisteriavaimella. Tämä voidaan poistaa myös koko organisaatiosta globaaleilla käytännöillä.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
Voit myös kokeilla seuraavaa avainta, joka on toiminut joidenkin asiakkaiden kohdalla heidän määritystensä perusteella:

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

Arvo 0 poistaa valintaikkunan käytöstä.




Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

