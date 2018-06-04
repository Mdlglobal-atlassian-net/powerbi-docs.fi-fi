---
title: Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys
description: Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys Power BI:ssä
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 9439ac6bd0b4df568b964f548372fb94d2fd0b26
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34238522"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys Power BI:ssä
Yksityiskohtaiset ohjeet ajoitetun päivityksen määrittämisestä ovat artikkelissa [Power BI -tietojen päivittäminen](refresh-data.md).

Jos saat virheilmoituksen virhekoodilla 400 tunnistetietojen muokkaamisen aikana määrittäessäsi ajoitettua päivitystä Azure SQL -tietokannassa, kokeile seuraavaa asianmukaisen palomuurisäännön määrittämiseksi:

1. Kirjaudu Azure-hallintaportaaliin
2. Siirry sen Azure SQL -palvelimen kohdalle, jolle olet määrittämässä päivitystä
3. Ota ”Windows Azure Services” käyttöön sallittujen palveluiden kohdassa

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Ilmenikö muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

