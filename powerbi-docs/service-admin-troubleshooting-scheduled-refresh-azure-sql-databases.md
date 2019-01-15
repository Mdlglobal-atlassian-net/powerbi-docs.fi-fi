---
title: Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys
description: Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys Power BI:ssä
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 17ee932bf0331940c7b30b020ab8fc43cdc9fdf5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274671"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Azure SQL -tietokantojen ajoitetun päivityksen vianmääritys Power BI:ssä
Yksityiskohtaiset ohjeet ajoitetun päivityksen määrittämisestä ovat artikkelissa [Power BI -tietojen päivittäminen](refresh-data.md).

Jos saat virheilmoituksen virhekoodilla 400 tunnistetietojen muokkaamisen aikana määrittäessäsi ajoitettua päivitystä Azure SQL -tietokannassa, kokeile seuraavaa asianmukaisen palomuurisäännön määrittämiseksi:

1. Kirjaudu Azure-hallintaportaaliin
2. Siirry sen Azure SQL -palvelimen kohdalle, jolle olet määrittämässä päivitystä
3. Ota ”Windows Azure Services” käyttöön sallittujen palveluiden kohdassa

![Azuren sallitut palvelut](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

