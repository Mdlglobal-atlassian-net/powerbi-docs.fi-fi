---
title: PowerShellin cmdlet-komennot, REST-ohjelmointirajapinnat ja .NET SDK:t järjestelmänvalvojille
description: Lue, miten voit hallita Power BI:tä komentosarjojen ja ohjelmointirajapintojen avulla.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 1ed4298e4ed4cddcdf965bd427c654cab6adf1e6
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157007"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShellin cmdlet-komennot, REST-ohjelmointirajapinnat ja .NET SDK Power BI:n hallintaa varten
Power BI:ssä järjestelmänvalvojat voivat luoda yleisiä tehtäviä koskevia komentosarjoja PowerShellin cmdlet-komentojen avulla. Se sisältää myös REST-ohjelmointirajapinnat ja .NET SDK:n hallinnollisten ratkaisujen kehittämiseen. Tässä ohjeaiheessa näytetään cmdlet-komentojen luettelo sekä vastaava SDK-menetelmä ja REST-ohjelmointirajapinnan päätepiste. Lisätietoja:

- PowerShellin [lataaminen](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) ja [dokumentaatio](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST-ohjelmointirajapinnan [dokumentaatio](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET SDK:n [lataaminen](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

| **Cmdlet-komennon nimi** | **Aliakset** | **SDK-menetelmä** | **REST-ohjelmointirajapinnan päätepiste** | **Kuvaus** |
| --- | --- | --- | --- | --- |
| **Get-PowerBIDatasource** | – | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Hakee tietolähteitä annetulle tietojoukolle. |
| **Get-PowerBIDataset** | – | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Hakee tietojoukkojen täydellisen luettelon Power BI -vuokraajassa. |
| **Get-PowerBIWorkspace** | **Get-PowerBIGroup** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Hakee työtilojen täydellisen luettelon Power BI -vuokraajassa. |
| **Add-PowerBIWorkspaceUser** | **Add-PowerBIGroupUser** |Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | Lisää käyttäjän jäsenenä tiettyyn työtilaan. |
| **Remove-PowerBIWorkspaceUser** | **Remove-PowerBIGroupUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Poistaa käyttäjän tietyn työtilan jäsenluettelosta. |
| **Restore-PowerBIWorkspace** |**Restore-PowerBIGroup** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | Palauttaa poistetun työtilan. |
| **Set-PowerBIWorkspace** |**Set-PowerBIGroup** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | Päivittää tietyn työtilan ominaisuudet. |
| **Get-PowerBIDataset -WorkspaceId** | – | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | Hakee tietyssä työtilassa olevat tietojoukot. |
| **Export-PowerBIReport** | – | Reports\_ExportReportAsAdmin | – | Vie tietyn raportin paikalliseen tiedostoon. |
| **Get-PowerBIReport** | – | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Hakee raporttien täydellisen luettelon Power BI -vuokraajassa. |
| **Get-PowerBIDashboard** | – | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Hakee koontinäyttöjen täydellisen luettelon Power BI -vuokraajassa. |
| **Get-PowerBIDashboard** | – | Groups\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Hakee tietyssä työtilassa olevat koontinäytöt. |
| **Get-PowerBITile** | **Get-PowerBIDashboardTile** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Hakee tietyn koontinäytön ruudut. |
| **Get-PowerBIReport** | – | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | Hakee tietyssä työtilassa olevat raportit. |
| **Get-PowerBIImport** | – | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Hakee tuontien täydellisen luettelon Power BI -vuokraajassa. |
| **Connect-PowerBIServiceAccount** | **Login-PowerBI** &  **Login-PowerBIServiceAccount** | – | – | Kirjaudu sisään Power BI:hin ja aloita istunto. |
| **Disconnect-PowerBIServiceAccount** | **Logout-PowerBI** & **Logout-PowerBIServiceAccount** | – | – | Kirjaudu ulos Power BI:stä ja sulje nykyinen istunto. |
| **Invoke-PowerBIRestMethod**| – | – | – | Lähetä satunnaisia REST-ohjelmointirajapinnan kutsuja Power BI:hin. |
| **Get-PowerBIAccessToken**| – | – | – | Hanki Power BI -käyttöoikeustietue istunnossa. |
| **Resolve-PowerBIError**| – | – | – | Hanki tarkat virhetiedot epäonnistuneista cmdlet-kutsuista. |