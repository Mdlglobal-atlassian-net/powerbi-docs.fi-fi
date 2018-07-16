---
title: Tukemattoman tietolähteen vianmääritys päivitystä varten
description: Tukemattoman tietolähteen vianmääritys päivitystä varten
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 864e7a3d78386f6996d866f45558add3b51faa69
ms.sourcegitcommit: ba447d7cc94418d7d3cf6fdcb686ec1a859258a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/02/2018
ms.locfileid: "37145185"
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
[Power BI -yhdyskäytävä – Personal](service-gateway-personal-mode.md)  
[Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

