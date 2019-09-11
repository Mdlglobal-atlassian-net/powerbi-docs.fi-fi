---
title: Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys
description: Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys Power BI:ssä
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/04/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 4bc14b9a3d863732c581e8a144d612d864d65af8
ms.sourcegitcommit: c799941c8169cd5b6b6d63f609db66ab2af93891
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/06/2019
ms.locfileid: "70391851"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys Power BI:ssä

Lisätietoja päivittämisestä on artikkeleissa [Tietojen päivittäminen Power BI:ssä](refresh-data.md) ja [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md).

Jos saat virheilmoituksen virhekoodilla 400 tunnistetietojen muokkaamisen aikana määrittäessäsi ajoitettua päivitystä Azure SQL -tietokannassa, kokeile seuraavaa asianmukaisen palomuurisäännön määrittämiseksi:

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

1. Siirry siihen Azure SQL -tietokantaan, jota varten määrität päivitystä.

1. Valitse **Yleiskatsaus**-lehden yläreunassa **Määritä palvelimen palo muuri**.

1. Varmista **Palomuuriasetukset**-lehdessä, että **Salli Azure-palveluiden käyttö** -asetuksena on **KÄYTÖSSÄ**.

    ![Azuren sallitut palvelut](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
