---
title: Tietojen suojaamisen tulosraportti
description: Lisätietoja tietojen suojaamisen tulosraportista
author: paulinbar
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: d2bd3308de21aa6064765b820745201efd8b23ab
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79112483"
---
# <a name="data-protection-metrics-report-preview"></a>Tietojen suojaamisen tulosraportti (esikatselu)

## <a name="what-is-the-data-protection-metrics-report"></a>Mikä tietojen suojaamisen tulosraportti on?
Tietojen suojaamisen tulosraportin avulla [Power BI -järjestelmänvalvojat](../service-admin-role.md) voivat valvoa ja seurata tietojen luottamuksellisuustunnisteiden käyttöönottoa ja käyttöä vuokraajassaan.

![Tietojen suojaamisen tulosraportti](./media/service-security-data-protection-metrics-report/protection-metrics-seven-days-1.png)
 
Raportin ominaisuudet:
* 100 %:n pinottu pylväskaavio, josta näkee luottamuksellisuustunnisteiden päivittäisen käytön vuokraajassa viimeisten 7, 30 tai 90 päivän ajalta. Tämän kaavion avulla on helppo seurata eri tunnistetyyppien suhteellista käyttöä ajan kuluessa.
* Rengaskaaviot, joista näkee luottamuksellisuustunnisteiden käytön nykyisen tilan vuokraajassa koontinäyttöjen, raporttien, tietojoukkojen ja tietovoiden osalta.
* Linkki Cloud App Security -portaaliin, josta näkee Power BI:n hälytykset, vaarassa olevat käyttäjät, toimintolokit ja muut tiedot. Jos haluat lisätietoja, katso [Microsoft Cloud App Securityn hallinnan käyttäminen Power BI:ssä (esikatselu)](./service-security-using-microsoft-cloud-app-security-controls.md).

Raportti päivittyy 24 tunnin välein.

## <a name="viewing-the-data-protection-metrics-report"></a>Tietojen suojaamisen tulosraportin tarkastelu

Raportin avaamiseen ja tarkasteluun vaaditaan [Power BI -järjestelmänvalvojan rooli](../service-admin-role.md).
Jos haluat tarkastella raporttia, siirry kohtaan **Asetukset > Hallintaportaali** ja valitse **Suojausmittarit (esikatselu)** .

![suojausmittareiden hallintaportaali](./media/service-security-data-protection-metrics-report/protection-metrics-admin-portal.png)
 
 
Kun avaat tietojen suojaamisen tulosraportin ensimmäisen kerran, sen lataaminen voi kestää muutamia sekunteja. Raportti ja tietojoukko nimeltä **Tietojen suojausmittarit (automaattisesti muodostettu)** luodaan yksityiseen ympäristöösi kohtaan Oma työtila. Emme suosittele sen tarkastelemista tässä – tämä ei ole täydellinen raportti. Tarkastele raporttia mieluummin hallintaportaalissa edellä kuvatulla tavalla.

> [!CAUTION]
> Älä muuta raporttia tai tietojoukkoa millään tavalla, koska raportista julkaistaan ajoittain uusia versioita ja alkuperäiseen raporttiin tekemäsi muutokset korvataan, jos päivität uuteen versioon.

## <a name="report-updates"></a>Raporttipäivitykset

Tietojen suojaamisen tulosraportista julkaistaan ajoittain parannettuja versioita. Jos uusi versio on saatavilla, kun avaat raportin, sinulta kysytään, haluatko avata uuden version. Jos vastaat kyllä, raportista ladataan uusi versio, joka korvaa vanhan version. Vanhaan raporttiin ja/tai tietojoukkoon mahdollisesti tekemäsi muutokset menetetään. Sinun ei ole pakko avata uutta versiota, mutta silloin et pääse hyötymään uuden version parannuksista. 
## <a name="notes-and-considerations"></a>Huomautukset ja huomioitavat asiat
* [Tietojen suojauksen](./service-security-enable-data-sensitivity-labels.md) on oltava käytössä vuokraajassasi ja myös [luottamuksellisuustunnisteiden on oltava käytössä](../designer/service-security-apply-data-sensitivity-labels.md), jotta tietojen suojaamisen tulosraportti voidaan luoda onnistuneesti. 
* Organisaatiollasi on oltava asianmukainen [Cloud App Security -käyttöoikeus](https://docs.microsoft.com/power-bi/admin/service-security-using-microsoft-cloud-app-security-controls#microsoft-cloud-app-security-licensing), jotta Cloud App Securityn tietoja voidaan käyttää.
* Jos päätät jakaa tietojen suojaamisen tulosraportin tietoja sellaisen käyttäjän kanssa, joka ei ole Power BI -järjestelmänvalvoja, ota huomioon, että raportti sisältää luottamuksellisia tietoja organisaatiostasi.
* Tietojen suojaamisen tulosraportti on erityinen raportti, jota ei näy Jaettu kanssani-, Viimeaikaiset- ja Suosikit-luetteloissa.
* Tietojen suojaamisen tulosraportti ei ole [ulkoisten käyttäjien (Azure Active Directoryn B2B-vieraskäyttäjät)](../service-admin-azure-ad-b2b.md) käytettävissä.
## <a name="next-steps"></a>Seuraavat vaiheet
* [Tietojen suojaus Power BI:ssä (esiversio)](./service-security-data-protection-overview.md)
* [Microsoft Cloud App Securityn hallinnan käyttäminen Power BI:ssä (esikatselu)](./service-security-using-microsoft-cloud-app-security-controls.md)
* [Tietoja Power BI -palvelun järjestelmänvalvojan roolista](../service-admin-role.md)
* [Luottamuksellisuustunnisteiden käyttöönotto Power BI:ssä](./service-security-enable-data-sensitivity-labels.md)