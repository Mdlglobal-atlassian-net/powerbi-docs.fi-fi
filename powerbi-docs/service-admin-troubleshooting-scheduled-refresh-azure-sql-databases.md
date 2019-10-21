---
title: Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys
description: Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys Power BI:ssä
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 09/04/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6d71a1202ba996b70c7477a33ccab936bebbfc5e
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/17/2019
ms.locfileid: "72542793"
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
