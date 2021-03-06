---
title: PowerShellin cmdlet-komennot, REST-ohjelmointirajapinnat ja .NET SDK:t järjestelmänvalvojille
description: Lue, miten voit hallita Power BI:tä komentosarjojen ja ohjelmointirajapintojen avulla.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: b4f4227a53a87cd831962bc5c944a569531b8232
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83136309"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShellin cmdlet-komennot, REST-ohjelmointirajapinnat ja .NET SDK Power BI:n hallintaa varten
Power BI:ssä järjestelmänvalvojat voivat luoda yleisiä tehtäviä koskevia komentosarjoja PowerShellin cmdlet-komentojen avulla. Se sisältää myös REST-ohjelmointirajapinnat ja .NET SDK:n hallinnollisten ratkaisujen kehittämiseen. Tässä ohjeaiheessa näytetään cmdlet-komentojen luettelo sekä vastaava SDK-menetelmä ja REST-ohjelmointirajapinnan päätepiste. Lisätietoja:

- PowerShellin [lataaminen](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) ja [dokumentaatio](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST-ohjelmointirajapinnan [dokumentaatio](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET SDK:n [lataaminen](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

> Alla olevia cmdlet-komentoja on kutsuttava `-Scope Organization`-kutsulla vuokraajan hallintaa vastaan toimimiseksi.

| **Cmdlet-komennon nimi** | **Aliakset** | **SDK-menetelmä** | **REST-ohjelmointirajapinnan päätepiste** | **Kuvaus** |
| --- | --- | --- | --- | --- |
| `Get-PowerBIDatasource` | – | `Datasets_GetDataSourcesAsAdmin` | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Hakee tietolähteitä annetulle tietojoukolle. |
| `Get-PowerBIDataset` | – | `Datasets_GetDatasetsAsAdmin` | /v1.0/myorg/admin/datasets | Hakee tietojoukkojen täydellisen luettelon Power BI -vuokraajassa. |
| `Get-PowerBIWorkspace` | `Get-PowerBIGroup` | `Groups_GetGroupsAsAdmin` | /v1.0/myorg/admin/groups | Hakee työtilojen täydellisen luettelon Power BI -vuokraajassa. |
| `Add-PowerBIWorkspaceUser` | `Add-PowerBIGroupUser` | `Groups_AddUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users | Lisää käyttäjän jäsenenä tiettyyn työtilaan. |
| `Remove-PowerBIWorkspaceUser` | `Remove-PowerBIGroupUser` | `Groups_DeleteUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Poistaa käyttäjän tietyn työtilan jäsenluettelosta. |
| `Restore-PowerBIWorkspace` |`Restore-PowerBIGroup` | `Groups_RestoreDeletedGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/restore | Palauttaa poistetun työtilan. |
| `Set-PowerBIWorkspace` |`Set-PowerBIGroup` | `Groups_UpdateGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId} | Päivittää tietyn työtilan ominaisuudet. |
| `Get-PowerBIDataset -WorkspaceId` | – | `Groups_GetDatasetsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/datasets | Hakee tietyssä työtilassa olevat tietojoukot. |
| `Get-PowerBIReport` | – | `Reports_GetReportsAsAdmin` | /v1.0/myorg/admin/reports | Hakee raporttien täydellisen luettelon Power BI -vuokraajassa. |
| `Get-PowerBIDashboard` | – | `Dashboards_GetDashboardsAsAdmin` | /v1.0/myorg/admin/dashboards | Hakee koontinäyttöjen täydellisen luettelon Power BI -vuokraajassa. |
| `Get-PowerBIDashboard -WorkspaceId` | – | `Groups_GetDashboardsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Hakee tietyssä työtilassa olevat koontinäytöt. |
| `Get-PowerBITile` | `Get-PowerBIDashboardTile` | `Dashboards_GetTilesAsAdmin` | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Hakee tietyn koontinäytön ruudut. |
| `Get-PowerBIReport` | – | `Groups_GetReportsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/reports | Hakee tietyssä työtilassa olevat raportit. |
| `Get-PowerBIImport` | – | `Imports_GetImportsAsAdmin` | /v1.0/myorg/admin/imports | Hakee tuontien täydellisen luettelon Power BI -vuokraajassa. |
| `Connect-PowerBIServiceAccount` | `Login-PowerBI` &  `Login-PowerBIServiceAccount` | – | – | Kirjaudu sisään Power BI:hin ja aloita istunto. |
| `Disconnect-PowerBIServiceAccount` | `Logout-PowerBI` & `Logout-PowerBIServiceAccount` | – | – | Kirjaudu ulos Power BI:stä ja sulje nykyinen istunto. |
| `Invoke-PowerBIRestMethod`| – | – | – | Lähetä satunnaisia REST-ohjelmointirajapinnan kutsuja Power BI:hin. |
| `Get-PowerBIAccessToken`| – | – | – | Hanki Power BI -käyttöoikeustietue istunnossa. |
| `Resolve-PowerBIError`| – | – | – | Hanki tarkat virhetiedot epäonnistuneista cmdlet-kutsuista. |
