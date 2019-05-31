---
title: Valvonnan organisaatiossa
description: Lue, miten voit Power BI:n avulla käyttää valvontaa toteutettujen toimien seuraamista ja tutkimista varten. Voit käyttää tietoturva- ja yhteensopivuuskeskusta tai PowerShelliä.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 559ff45974274420e2545228720000359d5fe971
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906859"
---
# <a name="use-auditing-within-your-organization"></a>Valvonnan organisaatiossa

Tietäminen, kuka tekee mitä toimia missäkin Power BI-vuokraajan voi olla ratkaisevaa organisaatiosi toteuttaa asetetut vaatimukset, kuten säädösten noudattaminen ja tietueiden hallintaa. Käytä Power BI-valvontatoimintoa valvoaksesi käyttäjien, kuten ”Näytä raportti” ja ”Näytä koontinäyttö” tehdä toimia. Valvonnan avulla ei voi valvoa käyttöoikeuksia.

Voit käyttää valvonnassa Office 365:n tietoturva-ja yhteensopivuuskeskusta tai PowerShelliä. Valvonta käyttää Exchange Onlinen toimintoja, jotka valmistellaan automaattisesti tukemaan Power BI:tä.

Voit voit suodattaa valvontatiedot päivämääräalueen, käyttäjän, koontinäytön, raportin, tietojoukon ja toimintotyyppi mukaan. Voit myös ladata toiminnot csv (pilkuin eroteltu arvo)-tiedostoon ja analysoida offline-tilassa.

## <a name="requirements"></a>Vaatimukset

Seuraavat vaatimukset on täytettävä valvontalokien käyttämistä varten:

* On oltava joko Yleinen järjestelmänvalvoja tai joille on määritetty valvontalokien tai View-Only-valvontalokien rooli Exchange Online käyttää valvontalokia. Oletusarvon mukaan yhteensopivuus-hallinnan ja organisaation hallinta rooliryhmät mukana nämä roolit määritetty **käyttöoikeudet** sivun Exchange-hallintakeskuksessa.

    Jotta muiden kuin järjestelmänvalvojien tilien valvontalokia, sinun on lisättävä käyttäjä yksi näiden Rooliryhmien jäsen. Jos haluat tehdä sen toisella tavalla, voit luoda mukautettu rooliryhmän Exchangen hallintakeskuksen, Määritä Valvontalokeihin tai View-Only-valvontalokit-rooli tähän ryhmään ja lisää sitten uuden rooliryhmän muulla kuin järjestelmänvalvojatilillä. Lisätietoja saat [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups) (Rooliryhmien hallinta Exchange Onlinessa) -ohjeartikkelista.

    Jos et pääse Exchangen hallintakeskukseen Microsoft 365 -hallintakeskuksesta, siirry osoitteeseen https://outlook.office365.com/ecp ja kirjaudu sisään tunnistetiedoillasi.

* Jos pääset valvontalokiin, mutta eivät ole yleinen järjestelmänvalvoja tai Power BI-palvelun järjestelmänvalvoja, ei ole Power BI-hallintaportaalin käyttöoikeus. Tässä tapauksessa sinun on käytettävä suoraa linkkiä [Office 365:n tietoturva- ja yhteensopivuuskeskukseen](https://sip.protection.office.com/#/unifiedauditlog).

## <a name="access-your-audit-logs"></a>Käyttää valvontalokien

Käyttämään lokit Varmista ensin käyttöön Power BI kirjautumisessa. Jos haluat lisätietoja, katso artikkelia [Valvontalokit](service-admin-portal.md#audit-logs) hallintaportaalin dokumentaatiossa. Voi olla jopa 48 tunnin viive välillä olet ottanut valvonnan käyttöön ja kun tarkastelet valvontatiedot. Jos et näe tietoja välittömästi, tarkista valvontalokit myöhemmin. Jos haet oikeuksia hallintalokien tarkasteluun, samanlainen viive voi esiintyä, ennen kuin oikeudet on myönnetty.

Power BI:n valvontalokit ovat saatavilla suoraan [Office 365:n tietoturva- ja yhteensopivuuskeskuksessa](https://sip.protection.office.com/#/unifiedauditlog). On myös linkki Power BI-hallintaportaalissa:

1. Valitse Power BI **hammaspyöräkuvake** oikeassa yläkulmassa ja valitse sitten **hallintaportaalissa**.

   ![Näyttökuva hammasrataskuvake avattava valikko, jossa järjestelmänvalvojan portaalin asetusta kutsutaan.](media/service-admin-auditing/powerbi-admin.png)

1. Valitse **Valvontalokit**.

1. Valitse **Siirry O365-hallintakeskukseen**.

   ![Näyttökuva hallintaportaalissa valvontalokien kirjaa asetus ja siirry Microsoft O365-hallintakeskukseen vaihtoehdot kutsutaan.](media/service-admin-auditing/audit-log-o365-admin-center.png)

## <a name="search-only-power-bi-activities"></a>Vain Power BI -toimien haku

Voit rajata tulokset vain Power BI -toimiin seuraavasti. Katso toimien luettelo jäljempänä tässä artikkelissa olevasta kohdasta, jossa on [Power BI:n valvomien toimien luettelo](#activities-audited-by-power-bi).

1. Valitse **haku valvontalokista** sivun **haku**, valitse avattavasta- **toiminnot**.

2. Valitse **Power BI -toimet**.

   ![Näyttökuva-haku valvontalokista Power BI-toimintojen kutsutaan.](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Napsauta mistä tahansa valintaruudun ulkopuolelta sulkeaksesi sen.

Haut, palauttaa vain Power BI-toimintoja.

## <a name="search-the-audit-logs-by-date"></a>Haku valvontalokeista päivämäärän mukaan

Voit hakea lokeista päivämääräalueen mukaan käyttämällä **Aloituspäivämäärä**- ja **Lopetuspäivämäärä**-kenttiä. Oletusarvon mukainen valinta on viimeisten seitsemän päivän aikana. Näytön esittää päivämäärä ja kellonaika UTC-aika (UTC)-muodossa. Suurin päivämääräalue, jonka voit määrittää, on 90 päivää. 

Saat virheen, jos valittu päivämääräalue on yli 90 päivää. Jos käytät 90 päivän suurinta mahdollista päivämääräaluetta, valitse **aloituspäivämääräksi** tämänhetkinen aika. Muutoin näkyviin tulee virhe, jossa ilmoitetaan alkamispäivämäärän olevan päättymispäivämäärää aiemmin. Jos olet ottanut valvonnan käyttöön viimeisen 90 päivän aikana, suurin mahdollinen päivämääräalue ei voi alkaa ennen päivämäärää, jolloin valvonta otettiin käyttöön.

![Näyttökuva-haku valvontalokista kutsutaan alkamispäivän ja päättymispäivän jälkeen asetuksilla.](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>Haku valvontalokeista käyttäjien mukaan

Voit hakea valvontalokimerkinnöistä toimintojen tehdä tietyille käyttäjille. Anna vähintään yksi käyttäjänimet **käyttäjät** kenttä. Käyttäjänimi Näyttää sähköpostiosoitteelta. Se on tili, jolla käyttäjät kirjautuvat sisään Power BI-kanssa. Jätä tämä ruutu tyhjäksi, jos haluat tulokseksi merkintöjä organisaatiosi kaikkien käyttäjien (ja palvelutilien) osalta.

![Hae käyttäjien mukaan](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="view-search-results"></a>Näytä hakutulokset

Kun olet valinnut **haku**, hakutulokset ladataan. Hetken kuluttua ne näkyvät **tulokset**. Kun haku on valmis, näytössä näkyy löytyneiden tulosten määrä. **Haku valvontalokista** näyttää enintään 1 000 tapahtumaa. Jos hakuehtojen mukaisia tapahtumia yli 1 000, sovellus näyttää uusimmat 1 000 tapahtumaa.

### <a name="view-the-main-results"></a>Näytä tärkeimmät tulokset

**Tulokset** alue on seuraavat tiedot jokaisesta haun palauttamasta tapahtumasta. Voit lajitella tulokset valitsemalla sarakkeen otsikon **Tulokset**-kohdasta.

| **Sarake** | **Määritelmä** |
| --- | --- |
| Päivämäärä |Päivämäärä ja aika (UTC-muodossa), jolloin tapahtuma ilmeni. |
| IP-osoite |Laitetta, jota käytetään kirjattu toimintaa IP-osoite. Sovellus näyttää IP-osoitteen joko IPv4- tai IPv6-osoitemuodossa. |
| Käyttäjä |Käyttäjä (tai palvelutili), joka suoritti tapahtuman aiheuttaneen toimen. |
| Toimi |Käyttäjän suorittama toimi. Tämä arvo vastaa toimia, jotka olet valinnut avattavassa **Toimet**-luettelossa. Exchange-järjestelmänvalvojan valvontalokin tapahtuman osalta tämän sarakkeen arvo on Exchange cmdlet-komento. |
| Kohde |Objekti luodaan tai jota muutettiin vastaavan toiminnon vuoksi. Esimerkiksi tarkasteltu tai muokatut-tiedosto tai päivitetty käyttäjätili. Kaikilla toimilla ei ole arvoa tässä sarakkeessa. |
| Tieto |Lisätieto toimesta. Tässäkään kaikilla toimilla ei ole arvoa. |

### <a name="view-the-details-for-an-event"></a>Tapahtuman tietojen tarkasteleminen

Jos haluat tarkastella lisätietoja tapahtuma, valitse tapahtuman hakutulosten luettelossa. A **tiedot** sivu tulee näkyviin, jolla on yksityiskohtaiset ominaisuudet tapahtuman tietueesta. **Tiedot** sivu näyttää ominaisuudet mukaan Office 365-palvelussa, jossa tapahtuma ilmenee.

Saat näkyviin nämä tiedot valitsemalla **Lisätiedot**. Kaikkien Power BI -syötteiden RecordType-ominaisuuden arvo on 20. Katso lisätietoja muista ominaisuuksista artikkelista [Yksityiskohtaiset ominaisuudet valvontalokissa](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/).

   ![Näyttökuva valvonnan tiedot keskustelu, jossa lisätietojen vaihtoehto kutsutaan.](media/service-admin-auditing/audit-details.png)

## <a name="export-search-results"></a>Hakutulosten vieminen

Jos haluat viedä Power BI-valvontalokin CSV-tiedostoon, toimi seuraavasti.

1. Valitse **Vie tulokset**.

1. Valitse joko **Tallenna ladatut tulokset** tai **Lataa kaikki tulokset**.

    ![Näyttökuva vienti-tulokset vaihtoehto.](media/service-admin-auditing/export-auditing-results.png)

## <a name="use-powershell-to-search-audit-logs"></a>Valvontalokien hakeminen PowerShellin avulla

Voit myös käyttää valvontalokeja PowerShellin avulla sisäänkirjautumisesi perusteella. Seuraavassa esimerkissä näytetään, miten voit muodostaa yhteyden Exchange Online PowerShelliin ja hakea sitten Power BI -valvontalokisyötteet [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/)-komennolla. Suorita komentosarja, järjestelmänvalvojan on määritettävä voit tarvittavia käyttöoikeuksia kuvatulla tavalla [vaatimukset](#requirements) osiossa.

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

Lisätietoja Exchange Onlineen yhdistämisestä on kohdassa [Yhdistäminen kohteeseen Exchange Online PowerShell](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/). Katso toinen esimerkki PowerShellin käyttämisestä valvontalokien avulla artikkelista [Power BI -valvontalokin ja PowerShellin käyttäminen Power BI Pro -käyttöoikeuksien määrittämiseksi](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="activities-audited-by-power-bi"></a>Power BI:n valvomat toimet

Seuraavat toiminnot ovat valvoo Power BI:

| Kutsumanimi                                     | Toiminnon nimi                              | Huomautukset                                  |
|---------------------------------------------------|---------------------------------------------|------------------------------------------|
| Lisätty tietolähde Power BI -yhdyskäytävään             | AddDatasourceToGateway                      |                                          |
| Lisätty Power BI -kansion käyttöoikeus                      | AddFolderAccess                             | Ei tällä hetkellä käytössä                       |
| Lisätty Power BI -ryhmän jäsenet                      | AddGroupMembers                             |                                          |
| Järjestelmänvalvoja liitti tietovuon tallennustilin vuokraajaan | AdminAttachedDataflowStorageAccountToTenant | Ei tällä hetkellä käytössä                       |
| Analysoitu Power BI -tietojoukko                         | AnalyzedByExternalApplication               |                                          |
| Analysoitu Power BI -raportti                          | AnalyzeInExcel                              |                                          |
| Sidottu Power BI -tietojoukko yhdyskäytävään                | BindToGateway                               |                                          |
| Muutettu kapasiteetin tila                            | ChangeCapacityState                         |                                          |
| Muutettu kapasiteetin käyttäjän määritys                  | UpdateCapacityUsersAssignment               |                                          |
| Muutetut Power BI -tietojoukon yhteydet              | SetAllConnections                           |                                          |
| Muutettu Power BI -yhdyskäytävän järjestelmänvalvojia                   | ChangeGatewayAdministrators                 |                                          |
| Muutettu Power BI -yhdyskäytävän tietolähteen käyttäjiä        | ChangeGatewayDatasourceUsers                |                                          |
| Luotu organisaation Power BI -sisältöpaketti      | CreateOrgApp                                |                                          |
| Luotu Power BI -sovellus                              | CreateApp                                   |                                          |
| Luotu Power BI -koontinäyttö                        | CreateDashboard                             |                                          |
| Luotu Power BI -tietovuo                         | CreateDataflow                              |                                          |
| Luotu Power BI -tietojoukko                          | CreateDataset                               |                                          |
| Luotu Power BI -sähköpostiviestien tilaus               | CreateEmailSubscription                     |                                          |
| Luotu Power BI -kansio                           | CreateFolder                                |                                          |
| Luotu Power BI -yhdyskäytävä                          | CreateGateway                               |                                          |
| Luotu Power BI -ryhmä                            | CreateGroup                                 |                                          |
| Luotu Power BI -raportti                           | CreateReport                                |                                          |
| Tietovuo siirretty ulkoiselle tallennustilille     | DataflowMigratedToExternalStorageAccount    | Ei tällä hetkellä käytössä                       |
| Lisätty tietovuon käyttöoikeudet                        | DataflowPermissionsAdded                    | Ei tällä hetkellä käytössä                       |
| Poistettu tietovuon käyttöoikeudet                      | DataflowPermissionsRemoved                  | Ei tällä hetkellä käytössä                       |
| Poistettu organisaation Power BI -sisältöpaketti      | DeleteOrgApp                                |                                          |
| Poistettu Power BI -kommentti                          | DeleteComment                               |                                          |
| Poistettu Power BI -koontinäyttö                        | DeleteDashboard                             | Ei tällä hetkellä käytössä                       |
| Poistettu Power BI -tietovuo                         | DeleteDataflow                              | Ei tällä hetkellä käytössä                       |
| Poistettu Power BI -tietojoukko                          | DeleteDataset                               |                                          |
| Poistettu Power BI -sähköpostiviestien tilaus               | DeleteEmailSubscription                     |                                          |
| Poistettu Power BI -kansio                           | DeleteFolder                                |                                          |
| Poistettu Power BI -kansion käyttöoikeus                    | DeleteFolderAccess                          | Ei tällä hetkellä käytössä                       |
| Poistettu Power BI -yhdyskäytävä                          | DeleteGateway                               |                                          |
| Poistettu Power BI -ryhmä                            | DeleteGroup                                 |                                          |
| Poistettu Power BI -raportti                           | DeleteReport                                |                                          |
| Löydetty Power BI -tietojoukon tietolähteet          | GetDatasources                              |                                          |
| Ladattu Power BI -raportti                        | DownloadReport                              |                                          |
| Muokattu Power BI -varmenteiden käyttöoikeutta          | EditCertificationPermission                 | Ei tällä hetkellä käytössä                       |
| Muokattu Power BI -koontinäyttöä                         | EditDashboard                               | Ei tällä hetkellä käytössä                       |
| Muokattu Power BI -tietojoukkoa                           | EditDataset                                 |                                          |
| Muokattu Power BI -tietojoukon ominaisuuksia                | EditDatasetProperties                       | Ei tällä hetkellä käytössä                       |
| Muokattu Power BI -raporttia                            | EditReport                                  |                                          |
| Viety Power BI -tietovuo                        | ExportDataflow                              |                                          |
| Viety Power BI -raportin visualisointitiedot              | ExportReport                                |                                          |
| Viety Power BI -ruudun tiedot                       | ExportTile                                  |                                          |
| Tietovuon käyttöoikeuksien lisääminen epäonnistui                | FailedToAddDataflowPermissions              | Ei tällä hetkellä käytössä                       |
| Tietovuon käyttöoikeuksien poistaminen epäonnistui             | FailedToRemoveDataflowPermissions           | Ei tällä hetkellä käytössä                       |
| Luotu Power BI -tietovuon SAS-tunnus             | GenerateDataflowSasToken                    |                                          |
| Luotu Power BI -upotustunnus                    | GenerateEmbedToken                          |                                          |
| Tuotu tiedosto Power BI:hin                         | Tuo                                      |                                          |
| Asennettu Power BI -sovellus                            | InstallApp                                  |                                          |
| Siirretty työtila kapasiteettiin                  | MigrateWorkspaceIntoCapacity                |                                          |
| Kirjoitettu Power BI -kommentti                           | PostComment                                 |                                          |
| Tulostettu Power BI -koontinäyttö                        | PrintDashboard                              |                                          |
| Tulostettu Power BI -raporttisivu                      | PrintReport                                 |                                          |
| Julkaistu Power BI -raportti verkkoon                  | PublishToWebReport                          |                                          |
| Vastaanotettu salainen Power BI -tietovuo Key Vaultista  | ReceiveDataflowSecretFromKeyVault           | Ei tällä hetkellä käytössä                       |
| Poistettu tietolähde Power BI -yhdyskäytävästä         | RemoveDatasourceFromGateway                 |                                          |
| Poistettu Power BI -ryhmän jäsenet                    | DeleteGroupMembers                          |                                          |
| Poistettu työtila kapasiteetista                 | RemoveWorkspacesFromCapacity                |                                          |
| Nimetty uudelleen Power BI -koontinäyttö                        | RenameDashboard                             |                                          |
| Pyydetty Power BI -tietovuon päivitystä               | RequestDataflowRefresh                      | Ei tällä hetkellä käytössä                       |
| Pyydetty Power BI -tietojoukon päivitystä                | RefreshDataset                              |                                          |
| Noudettu Power BI -työtilat                     | GetWorkspaces                               |                                          |
| Määritetty ajoitettu päivitys Power BI -tietovuolle        | SetScheduledRefreshOnDataflow               |                                          |
| Määritetty ajoitettu päivitys Power BI -tietojoukolle         | SetScheduledRefresh                         |                                          |
| Jaettu Power BI -koontinäyttö                         | ShareDashboard                              |                                          |
| Jaettu Power BI -raportti                            | ShareReport                                 |                                          |
| Power BI:n pidennetty kokeilujakso aloitettu                   | OptInForExtendedProTrial                    | Ei tällä hetkellä käytössä                       |
| Aloitettu Power BI -kokeilujakso                            | OptInForProTrial                            |                                          |
| Ota haltuun Power BI -tietolähde                   | TakeOverDatasource                          |                                          |
| Ota haltuun Power BI -tietojoukko                        | TakeOverDataset                             |                                          |
| Julkaisematon Power BI -sovellus                          | UnpublishApp                                |                                          |
| Päivitä kapasiteetin resurssin hallinnan asetukset      | UpdateCapacityResourceGovernanceSettings    | Ei tällä hetkellä Microsoft 365 -hallintakeskuksessa |
| Päivitetty kapasiteetin järjestelmänvalvoja                            | UpdateCapacityAdmins                        |                                          |
| Päivitetty kapasiteetin näyttönimi                     | UpdateCapacityDisplayName                   |                                          |
| Päivitetyt organisaation Power BI -asetukset          | UpdatedAdminFeatureSwitch                   |                                          |
| Päivitetty Power BI -sovellus                              | UpdateApp                                   |                                          |
| Päivitetty Power BI -tietovuo                         | UpdateDataflow                              |                                          |
| Päivitetyt Power BI -tietojoukon tietolähteet             | UpdateDatasources                           |                                          |
| Päivitetyt Power BI -tietojoukon parametrit               | UpdateDatasetParameters                     |                                          |
| Päivitetty Power BI -sähköpostiviestien tilaus               | UpdateEmailSubscription                     |                                          |
| Päivitetty Power BI -kansio                           | UpdateFolder                                |                                          |
| Päivitetty Power BI -kansion käyttöoikeus                    | UpdateFolderAccess                          |                                          |
| Päivitetyt Power BI -yhdyskäytävän tietolähteen tunnukset  | UpdateDatasourceCredentials                 |                                          |
| Tarkasteltu Power BI -koontinäyttö                         | ViewDashboard                               |                                          |
| Tarkasteltu Power BI -tietovuo                          | ViewDataflow                                |                                          |
| Tarkasteltu Power BI -raportti                            | ViewReport                                  |                                          |
| Tarkasteltu Power BI -ruutu                              | ViewTile                                    |                                          |
| Tarkastellut Power BI -käyttötiedot                     | ViewUsageMetrics                            |                                          |
|                                                   |                                             |                                          |

## <a name="next-steps"></a>Seuraavat vaiheet

[Mitä on Power BI:n hallinta?](service-admin-administering-power-bi-in-your-organization.md)  

[Power BI -hallintaportaali](service-admin-portal.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
