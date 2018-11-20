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
ms.openlocfilehash: f4455fef5a2ed0e7ee23ff8ca3a0b626cd695838
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507987"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShellin cmdlet-komennot, REST-ohjelmointirajapinnat ja .NET SDK Power BI:n hallintaa varten
Power BI:ssä järjestelmänvalvojat voivat luoda yleisiä tehtäviä koskevia komentosarjoja PowerShellin cmdlet-komentojen avulla. Se sisältää myös REST-ohjelmointirajapinnat ja .NET SDK:n hallinnollisten ratkaisujen kehittämiseen. Tässä ohjeaiheessa näytetään cmdlet-komentojen luettelo sekä vastaava SDK-menetelmä ja REST-ohjelmointirajapinnan päätepiste. Lisätietoja:

  - PowerShellin [lataaminen](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) ja [dokumentaatio](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
  - REST-ohjelmointirajapinnan [dokumentaatio](https://docs.microsoft.com/rest/api/power-bi/admin)
  - .NET SDK:n [lataaminen](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) 


| **Cmdlet-komennon nimi** | **SDK-menetelmä** | **REST-ohjelmointirajapinnan päätepiste** | **Kuvaus** |
| --- | --- | --- | --- |
| **Get-PowerBIDatasource** | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Hakee tietolähteitä annetulle tietojoukolle. |
| **Get-PowerBIDataset** | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Hakee tietojoukkojen täydellisen luettelon Power BI -vuokraajassa. |
| **Get-PowerBIWorkspace** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Hakee työtilojen täydellisen luettelon Power BI -vuokraajassa. |
| **Add-PowerBIWorkspaceUser** | Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | Lisää käyttäjän jäsenenä tiettyyn työtilaan. |
| **Remove-PowerBIWorkspaceUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Poistaa käyttäjän tietyn työtilan jäsenluettelosta. |
| **Restore-PowerBIWorkspace** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | Palauttaa poistetun työtilan. |
| **Set-PowerBIWorkspace** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | Päivittää tietyn työtilan ominaisuudet. |
| **Get-PowerBIDataset -WorkspaceId** | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | Hakee tietyssä työtilassa olevat tietojoukot. |
| **Export-PowerBIReport** | Reports\_ExportReportAsAdmin | – | Vie tietyn raportin paikalliseen tiedostoon. |
| **Get-PowerBIReport** | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Hakee raporttien täydellisen luettelon Power BI -vuokraajassa. |
| **Get-PowerBIDashboard** | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Hakee koontinäyttöjen täydellisen luettelon Power BI -vuokraajassa. |
| **Get-PowerBIDashboard -WorkspaceId** | Groups\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Hakee tietyssä työtilassa olevat koontinäytöt. |
| **Get-PowerBITile -DashboardId** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Hakee tietyn koontinäytön ruudut. |
| **Get-PowerBIReport -WorkspaceId** | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | Hakee tietyssä työtilassa olevat raportit. |
| **Get-PowerBIImport** | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Hakee tuontien täydellisen luettelon Power BI -vuokraajassa. |
| **Connect-PowerBIServiceAccount** | – | – | Kirjaudu sisään Power BI:hin ja aloita istunto. |
| **Disconnect-PowerBIServiceAccount** | – | – | Kirjaudu ulos Power BI:stä ja sulje nykyinen istunto. |
| **Invoke-PowerBIRestMethod** | – | – | Lähetä satunnaisia REST-ohjelmointirajapinnan kutsuja Power BI:hin. |
| **Get-PowerBIAccessToken** | – | – | Hanki Power BI -käyttöoikeustietue istunnossa. |
| **Resolve-PowerBIError** | – | – | Hanki tarkat virhetiedot epäonnistuneista cmdlet-kutsuista. |