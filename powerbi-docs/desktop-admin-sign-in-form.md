---
title: Miten järjestelmänvalvojat voivat hallita Power BI Desktopin kirjautumislomaketta
description: Lue, miten voit hallita ensimmäistä kirjautumislomaketta Power BI Desktopia avattaessa.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 5c31277b640b16882bef5c5f2cd9c56b441ede82
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61329874"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Miten järjestelmänvalvojat voivat hallita Power BI Desktopin kirjautumislomaketta
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




Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

