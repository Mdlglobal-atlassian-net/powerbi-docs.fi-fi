---
title: Valvonnan käyttö organisaatiossa
description: Lue, miten voit Power BI:n avulla käyttää valvontaa toteutettujen toimien seuraamista ja tutkimista varten. Voit käyttää tietoturva- ja yhteensopivuuskeskusta tai PowerShelliä.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 294fb3a0142908ce0ab068e075ce39f950a0b124
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973346"
---
# <a name="using-auditing-within-your-organization"></a>Valvonnan käyttö organisaatiossa

Sen tietäminen, kuka tekee mitä toimia missäkin Power BI -vuokraajasi kohteissa, voi olla ratkaisevaa, kun autetaan organisaatiotasi toteuttamaan sille asetetut vaatimukset, kuten säädösten noudattaminen ja tietueiden hallinta. Voit Power BI -valvonnan avulla valvoa käyttäjien suorittamia toimia, kuten ”Näytä raportti” ja ”Näytä koontinäyttö”. Valvonnan avulla ei voi valvoa käyttöoikeuksia.

Voit käyttää valvonnassa Office 365:n tietoturva-ja yhteensopivuuskeskusta tai PowerShelliä. Käsittelemme niitä kumpaakin tässä artikkelissa. Voit suodattaa valvontatiedot päivämääräalueen, käyttäjän, koontinäytön, raportin, tietojoukon ja toimintatyypin mukaan. Voit myös ladata toimet CSV-tiedostoon (tiedosto, jonka arvot on erotettu luetteloerottimella) offline-tilassa analysointia varten.

## <a name="requirements"></a>Vaatimukset

Seuraavat vaatimukset on täytettävä valvontalokien käyttämistä varten:

- Jotta voisit käyttää Office 365:n tietoturva- ja yhteensopivuuskeskuksen valvontaosaa, sinulla on oltava Exchange Online -lisenssi (sisältyy Office 365 Enterprise E3- ja E5 -tilauksiin).

- Sinun on joko oltava yleinen järjestelmänvalvoja tai sinulla on oltava Exchange-järjestelmänvalvojarooli, joka mahdollistaa valvontalokin käytön. Exchange-järjestelmänvalvojarooleja hallitaan Exchangen hallintakeskuksen kautta. Lisätietoja on kohdassa [Exchange Onlinen käyttöoikeudet](/exchange/permissions-exo/permissions-exo/).

- Jos pääset valvontalokiin, mutta et ole yleinen järjestelmänvalvoja tai Power BI -palvelun järjestelmänvalvoja, et voi käyttää Power BI -hallintaportaalia. Tässä tapauksessa sinun on saatava suora linkki [Office 365:n tietoturva- ja yhteensopivuuskeskukseen](https://sip.protection.office.com/#/unifiedauditlog).

- Tarkastellaksesi vuokraajasi Power BI -valvontalokeja sinulla on oltava vähintään yksi vuokraajan Exchange-postilaatikko.

## <a name="accessing-your-audit-logs"></a>Valvontalokien käyttö

Jos haluat käyttää lokeja, varmista ensin, että sisäänkirjaus on käytössä Power BI:ssä. Jos haluat lisätietoja, katso artikkelia [Valvontalokit](service-admin-portal.md#audit-logs) hallintaportaalin dokumentaatiossa. Valvonnan käyttöönoton ja valvontatietojen tarkastelumahdollisuuden välillä voi olla jopa 48 tunnin viive. Jos et näe tietoja välittömästi, tarkista valvontalokit myöhemmin. Jos haet oikeuksia hallintalokien tarkasteluun, samanlainen viive voi esiintyä, ennen kuin oikeudet on myönnetty.

Power BI:n valvontalokit ovat saatavilla suoraan [Office 365:n tietoturva- ja yhteensopivuuskeskuksessa](https://sip.protection.office.com/#/unifiedauditlog). Täällä on myös linkki Power BI:n hallintaportaalista:

1. Valitse Power BI:ssä oikeasta yläkulmasta **hammasrataskuvake** ja valitse sitten **Hallintaportaali**.

   ![Hallintaportaali](media/service-admin-auditing/powerbi-admin.png)

1. Valitse **Valvontalokit**.

1. Valitse **Siirry O365-hallintakeskukseen**.

   ![Siirry O365-hallintakeskukseen](media/service-admin-auditing/audit-log-o365-admin-center.png)

Voi sallia muille kuin järjestelmänvalvojatileille valvontalokin käytön myöntämällä oikeuksia Exchange Online -hallintakeskuksessa. Voit esimerkiksi määrittää käyttäjän olemassa olevaan rooliryhmään, kuten organisaation hallinta, tai luoda uuden rooliryhmän roolilla valvontalokit. Lisätietoja on artikkelissa [Exchange Onlinen käyttöoikeudet](/exchange/permissions-exo/permissions-exo/).

## <a name="search-only-power-bi-activities"></a>Vain Power BI -toimien haku

Voit rajata tulokset vain Power BI -toimiin seuraavasti. Katso toimien luettelo jäljempänä tässä artikkelissa olevasta kohdasta, jossa on [Power BI:n valvomien toimien luettelo](#list-of-activities-audited-by-power-bi).

1. Valitse **Haku valvontalokista** -sivun **Haku**-kohdasta avattava **Toimet**-luettelo.

2. Valitse **Power BI -toimet**.

   ![Haku valvontalokista](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Napsauta mistä tahansa valintaruudun ulkopuolelta sulkeaksesi sen.

Hakusi suodatetaan nyt vain Power BI -toimiin.

## <a name="search-the-audit-logs-by-date"></a>Haku valvontalokeista päivämäärän mukaan

Voit hakea lokeista päivämääräalueen mukaan käyttämällä **Aloituspäivämäärä**- ja **Lopetuspäivämäärä**-kenttiä. Oletusarvoisesti valittuna on seitsemän viime päivää. Päivämäärä ja aika näytetään muodossa koordinoitu yleisaika (UTC). Suurin päivämääräalue, jonka voit määrittää, on 90 päivää. 

Näkyviin tulee virhe, jos valittu päivämääräalue on yli 90 päivää. Jos käytät 90 päivän suurinta mahdollista päivämääräaluetta, valitse **aloituspäivämääräksi** tämänhetkinen aika. Muutoin näkyviin tulee virhe, jossa ilmoitetaan alkamispäivämäärän olevan päättymispäivämäärää aiemmin. Jos olet ottanut valvonnan käyttöön viimeisen 90 päivän aikana, suurin mahdollinen päivämääräalue ei voi alkaa ennen päivämäärää, jolloin valvonta otettiin käyttöön.

![](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>Haku valvontalokeista käyttäjien mukaan

Voit hakea valvontalokimerkinnöistä tiettyjen käyttäjien suorittamia toimia. Voit tehdä tämän syöttämällä yhden tai useamman käyttäjänimen **Käyttäjät**-kenttään. Käyttäjänimi näyttää sähköpostiosoitteelta; se on tili, jolla käyttäjät kirjautuvat sisään Power BI:hin. Jätä tämä ruutu tyhjäksi, jos haluat tulokseksi merkintöjä organisaatiosi kaikkien käyttäjien (ja palvelutilien) osalta.

![Hae päivämäärän mukaan](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="view-search-results"></a>Näytä hakutulokset

Kun olet valinnut **Hae**, hakutulokset ladataan, ja hetken kuluttua ne näytetään **Tulokset**-kohdassa. Kun haku on valmis, löytyneiden tulosten määrä tulee näkyviin. Näyttöön tulee enintään 1 000 tapahtumaa; jos hakuehtojen mukaisia tapahtumia on yli 1 000, näytetään uusimmat 1 000 tapahtumaa.

### <a name="view-the-main-results"></a>Näytä tärkeimmät tulokset

**Tulokset**-alue sisältää seuraavat tiedot kullekin haun palauttamalle tapahtumalle. Voit lajitella tulokset valitsemalla sarakkeen otsikon **Tulokset**-kohdasta.

| **Sarake** | **Määritelmä** |
| --- | --- |
| Päivämäärä |Päivämäärä ja aika (UTC-muodossa), jolloin tapahtuma ilmeni. |
| IP-osoite |Sen laitteen IP-osoite, jota käytettiin toimen kirjaamisen aikana. IP-osoite näkyy joko IPv4- tai IPv6-osoitemuodossa. |
| Käyttäjä |Käyttäjä (tai palvelutili), joka suoritti tapahtuman aiheuttaneen toimen. |
| Toimi |Käyttäjän suorittama toimi. Tämä arvo vastaa toimia, jotka olet valinnut avattavassa **Toimet**-luettelossa. Exchange-järjestelmänvalvojan valvontalokin tapahtuman osalta tämän sarakkeen arvo on Exchange cmdlet-komento. |
| Kohde |Objekti, joka luotiin tai jota muokattiin vastaavan toimen seurauksena. Esimerkiksi tiedosto, jota tarkasteltiin tai muokattiin, tai käyttäjätili, jota päivitettiin. Kaikilla toimilla ei ole arvoa tässä sarakkeessa. |
| Tieto |Lisätieto toimesta. Tässäkään kaikilla toimilla ei ole arvoa. |

### <a name="view-the-details-for-an-event"></a>Tapahtuman tietojen tarkasteleminen

Voit nähdä tapahtumasta lisätietoja napsauttamalla tapahtuman tietuetta hakutulosluettelosta. Näkyviin tulee **Tiedot**-sivu, johon sisältyvät yksityiskohtaiset ominaisuudet tapahtuman tietueesta. Näytettävät ominaisuudet riippuvat siitä, missä Office 365 -palvelussa tapahtuma ilmenee. 

Saat näkyviin nämä tiedot valitsemalla **Lisätiedot**. Kaikkien Power BI -syötteiden RecordType-ominaisuuden arvo on 20. Katso lisätietoja muista ominaisuuksista artikkelista [Yksityiskohtaiset ominaisuudet valvontalokissa](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/).

   ![Valvontatiedot](media/service-admin-auditing/audit-details.png)

## <a name="export-search-results"></a>Hakutulosten vieminen

Voit viedä Power BI -valvontalokin CSV-tiedostoon seuraavasti.

1. Valitse **Vie tulokset**.

1. Valitse joko **Tallenna ladatut tulokset** tai **Lataa kaikki tulokset**.

    ![Tulosten vieminen](media/service-admin-auditing/export-auditing-results.png)

## <a name="use-powershell-to-search-audit-logs"></a>Valvontalokien hakeminen PowerShellin avulla

Voit myös käyttää valvontalokeja PowerShellin avulla sisäänkirjautumisesi perusteella. Seuraavassa esimerkissä näytetään, miten voit käyttää [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/)-komentoa Power BI -valvontalokisyötteiden hakemiseksi.

Jotta voit käyttää [New-PSSession](/powershell/module/microsoft.powershell.core/new-pssession/)-komentoa, tilillesi on oltava määritetty Exchange Online -käyttöoikeus ja sinun on voitava käyttää vuokraajasi valvontalokia. Lisätietoja Exchange Onlineen yhdistämisestä on kohdassa [Yhdistäminen kohteeseen Exchange Online PowerShell](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/).

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

Katso toinen esimerkki PowerShellin käyttämisestä valvontalokien avulla artikkelista [Power BI -valvontalokin ja PowerShellin käyttäminen Power BI Pro -käyttöoikeuksien määrittämiseksi](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="activities-audited-by-power-bi"></a>Power BI:n valvomat toimet

Power BI valvoo seuraavia toimia.

* AddDatasourceToGateway
* AddGroupMembers
* AnalyzedByExternalApplication
* AnalyzeInExcel
* AttachDataflowStorageAccount
* BindToGateway
* ChangeCapacityState
* ChangeGatewayAdministrators
* ChangeGatewayDatasourceUsers
* CreateApp
* CreateDashboard
* CreateDataflow
* CreateDataset
* CreateEmailSubscription
* CreateFolder
* CreateGateway
* CreateGroup
* CreateOrgApp
* CreateReport
* DeleteComment
* DeleteDashboard
* DeleteDataflow
* DeleteDataset
* DeleteEmailSubscription
* DeleteFolder
* DeleteGateway
* DeleteGroup
* DeleteGroupMembers
* DeleteOrgApp
* DeleteReport
* DownloadReport
* EditDataset
* EditReport
* ExportDataflow
* ExportReport
* ExportTile
* GenerateDataflowSasToken
* GenerateEmbedToken
* GetDatasources
* Tuo
* InstallApp
* MigrateWorkspaceIntoCapacity
* OptInForProTrial
* PostComment
* PrintDashboard
* PrintReport
* PublishToWebReport
* RefreshDataset
* RemoveDatasourceFromGateway
* RemoveWorkspacesFromCapacity
* RenameDashboard
* SetAllConnections
* SetScheduledRefresh
* SetScheduledRefreshOnDataflow
* ShareDashboard
* ShareReport
* TakeOverDataset
* TakeOverDatasource
* UnpublishApp
* UpdateApp
* UpdateCapacityAdmins
* UpdateCapacityDisplayName
* UpdateCapacityResourceGovernanceSettings
* UpdateCapacityUsersAssignment
* UpdatedAdminFeatureSwitch
* UpdateDataflow
* UpdateDatasetParameters
* UpdateDatasourceCredentials
* UpdateDatasources
* UpdateEmailSubscription
* UpdateFolder
* UpdateFolderAccess
* ViewDashboard
* ViewDataflow
* ViewReport
* ViewTile
* ViewUsageMetrics

## <a name="next-steps"></a>Seuraavat vaiheet

[Mitä on Power BI:n hallinta?](service-admin-administering-power-bi-in-your-organization.md)  

[Power BI -hallintaportaali](service-admin-portal.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
