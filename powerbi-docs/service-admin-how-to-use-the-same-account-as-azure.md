---
title: Saman tilin käyttö Power BI:een ja Azureen
description: Samalla tilillä kirjautuminen Power BI:hin ja Azureen
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: f9659ad657c4466ad58eb40d4a07916b46f9536a
ms.sourcegitcommit: 6a44cb5b0328b60ebe7710378287f1e20bc55a25
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/10/2019
ms.locfileid: "70877791"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Saman tilin käyttö Power BI:een ja Azureen

Jos olet Power BI- ja Azure-käyttäjä, haluat ehkä käyttää samaa kirjautumistunnusta molempiin palveluihin niin, että sinun ei tarvitse kirjoittaa salasanaasi kahdesti.

Power BI kirjaa sinut sisään käyttämällä organisaation käyttäjätiliä, joka on liitetty työpaikan tai oppilaitoksen sähköpostiosoitteeseen.  Azure kirjaa sinut sisään joko Microsoft-tilillä tai organisaation tilillä.

Jos haluat käyttää samaa kirjautumista Azuren ja Power BI:n kohdalla, muista kirjautua Azureen organisaation tilillä.

**Entä jos olen jo kirjautuneena Azureen Microsoft-tilini kautta?**

Voit lisätä organisaatiotilisi rinnakkaisjärjestelmänvalvojaksi Azureen seuraavasti:

1. Kirjaudu sisään [Azure-portaaliin](http://portal.azure.com/). Jos käytössäsi on useita Azure-hakemistoja, valitse **Tilaukset** ja suodata niin, että näet vain hakemiston ja tilaukset, joita haluat muokata.

1. Valitse siirtymisruudussa **Käyttöoikeuksien valvonta (IAM)** ja valitse sitten **Lisää** \> **Lisää rinnakkaisjärjestelmänvalvoja**.

    ![Rinnakkaisjärjestelmänvalvojan lisääminen Azure-portaalissa](media/service-admin-how-to-use-the-same-account-as-azure/add-co-administrator.png)

1. Anna organisaatiotiliisi liittyvä sähköpostiosoite ja valitse **Lisää**.

1. Kun seuraavan kerran kirjaudut sisään Azure-portaaliin, käytä organisaatiolta saamaasi sähköpostiosoitetta.

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
