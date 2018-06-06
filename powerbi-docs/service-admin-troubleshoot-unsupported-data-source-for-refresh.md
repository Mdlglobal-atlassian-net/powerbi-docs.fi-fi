---
title: Tukemattoman tietolähteen vianmääritys päivitystä varten
description: Tukemattoman tietolähteen vianmääritys päivitystä varten
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: d09d75350cbffbab78c1a44252f18d2216c2505f
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
ms.locfileid: "30975812"
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>Tukemattoman tietolähteen vianmääritys päivitystä varten
Näyttöön saattaa tulla virhe, kun yrität määrittää tietojoukkoa ajoitetulle päivitykselle.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

Näin tapahtuu, jos käyttämäsi tietolähdettä Power BI Desktopin sisällä ei tue päivityksissä. Sinun on löydettävä tietolähde, jota käytät ja vertailtava sitä tuettujen tietolähteiden luetteloon kohdassa [Power BI -tietojen päivittäminen](refresh-data.md). 

## <a name="find-the-data-source"></a>Tietolähteen löytäminen
Jos et ole varma, mitä tietolähdettä käytettiin, löydät sen seuraavien vaiheiden avulla Power BI Desktop sisällä.  

1. Varmista Power BI Desktopissa, että olet **Raportti** -ruudussa.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. Valitse **Muokkaa kyselyjä** valintanauhasta.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. Valitse **Laajennettu editori**.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. Kirjoita muistiin luettelossa annettu lähteen palvelu.  Tässä esimerkissä palvelu on ActiveDirectory.  
   ![](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. Vertaa palvelua luetteloon tuetuista tietolähteestä, joka löytyy kohdasta [Power BI-tietojen päivittäminen](refresh-data.md).  Huomaat, että Active Directorya ei ole tuettu tietolähteen päivittämiseksi.  

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojen päivittäminen](refresh-data.md)  
[Power BI -yhdyskäytävä – Personal](personal-gateway.md)  
[Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

