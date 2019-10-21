---
title: Tukemattoman tietolähteen vianmääritys päivitystä varten
description: Tukemattoman tietolähteen vianmääritys päivitystä varten
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 32c42f21eafa7118ed3977340517aeebe8c4219b
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/17/2019
ms.locfileid: "72542910"
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>Tukemattoman tietolähteen vianmääritys päivitystä varten
Näyttöön saattaa tulla virhe, kun yrität määrittää tietojoukkoa ajoitetulle päivitykselle.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

Näin tapahtuu, jos käyttämäsi tietolähdettä Power BI Desktopin sisällä ei tue päivityksissä. Sinun on löydettävä tietolähde, jota käytät ja vertailtava sitä tuettujen tietolähteiden luetteloon kohdassa [Power BI -tietojen päivittäminen](refresh-data.md). 

## <a name="find-the-data-source"></a>Tietolähteen löytäminen
Jos et ole varma, mitä tietolähdettä käytettiin, löydät sen seuraavien vaiheiden avulla Power BI Desktop sisällä.  

1. Varmista Power BI Desktopissa, että olet **Raportti** -ruudussa.  
   ![Desktop-raporttiruutu](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. Valitse **Muokkaa kyselyjä** valintanauhasta.  
   ![Muokkaa kyselyitä](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. Valitse **Laajennettu editori**.  
   ![Laajennettu editori](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. Kirjoita muistiin luettelossa annettu lähteen palvelu.  Tässä esimerkissä palvelu on ActiveDirectory.  
   ![Tietolähdepalvelu](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. Vertaa palvelua luetteloon tuetuista tietolähteestä, joka löytyy kohdasta [Power BI-tietojen päivittäminen](refresh-data.md).  Huomaat, että Active Directorya ei ole tuettu tietolähteen päivittämiseksi.  

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojen päivittäminen](refresh-data.md)  
[Power BI -yhdyskäytävä – Personal](service-gateway-personal-mode.md)  
[Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)  
[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
[Power BI -yhdyskäytävän vianmääritys – Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

