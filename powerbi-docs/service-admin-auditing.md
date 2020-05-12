---
title: Käyttäjien toiminnan seuraaminen Power BI:ssä
description: Lue, miten voit Power BI:n avulla käyttää toimintolokeja ja valvontaa tehtyjen toimien seuraamista ja tutkimista varten.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/03/2020
ms.author: kfollis
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: c2a8372a5c31e41b49746ebbea3ba4801eeac493
ms.sourcegitcommit: a199dda2ab50184ce25f7c9a01e7ada382a88d2c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/06/2020
ms.locfileid: "82866652"
---
# <a name="track-user-activities-in-power-bi"></a>Käyttäjien toiminnan seuraaminen Power BI:ssä

Sen tietäminen, kuka tekee mitä toimia missäkin Power BI -vuokraajasi kohteissa, voi olla ratkaisevaa, kun autetaan organisaatiotasi toteuttamaan sille asetetut vaatimukset, kuten säädösten noudattaminen ja tietueiden hallinta. Power BI:ssä voi seurata käyttäjien toimia kahdella eri tavalla, jotka ovat [Power BI:n toimintoloki](#use-the-activity-log) ja [yhdistetty Office 365 ‑valvontaloki](#use-the-audit-log). Molemmat lokit sisältävät [Power BI:n valvontatiedoista](#operations-available-in-the-audit-and-activity-logs) täydellisen kopion, mutta seuraavassa taulukossa esitetään yhteenveto niiden olennaisista eroista.

| **Yhdistetty Office 365 ‑valvontaloki** | **Power BI:n toimintoloki** |
| --- | --- |
| Sisältää Power BI:n valvontatapahtumien lisäksi tapahtumia SharePoint Onlinesta, Exchange Onlinesta, Dynamics 365:stä ja muista palveluista. | Sisältää vain Power BI:n valvontatapahtumat. |
| Käyttöoikeudet vain käyttäjillä, joilla on valvontalokien käyttöoikeudet tai pelkät valvontalokien katseluoikeudet, kuten yleisillä järjestelmänvalvojilla ja tarkastajilla. | Käyttöoikeudet yleisillä järjestelmänvalvojilla ja Power BI ‑palvelun järjestelmänvalvojilla. |
| Yleiset järjestelmänvalvojat ja tarkastajat voivat tehdä hakuja yhdistetystä valvontalokista Office 365:n Tietoturva-ja yhteensopivuuskeskuksen, Microsoft 365:n Tietoturvakeskuksen tai Microsoft 365:n Yhteensopivuuskeskuksen kautta. | Hakujen tekemiseen toimintolokista ei ole vielä käyttöliittymää. |
| Yleiset järjestelmänvalvojat ja tarkastajat voivat ladata valvontalokin kirjaukset itselleen käyttämällä Office 365:n hallinnan ohjelmointirajapintoja sekä cmdlet-komentoja. | Yleiset järjestelmänvalvojat ja Power BI ‑palvelun järjestelmänvalvojat voivat ladata toimintolokin kirjaukset itselleen käyttämällä Power BI:n REST API ‑ohjelmointirajapintaa sekä hallinnan cmdlet-komentoa. |
| Valvontatietoja säilytetään 90 päivää. | Toimintotietoja säilytetään 30 päivää (julkinen esiversio). |
| | |

## <a name="use-the-activity-log"></a>Toimintolokin käyttäminen

Power BI ‑palvelun järjestelmänvalvojana voit analysoida kaikkien Power BI ‑resurssien käyttöä vuokraajatasolla käyttämällä Power BI:n toimintolokiin perustuvia mukautettuja raportteja. Voit ladata toimintotiedot itsellesi käyttämällä REST API ‑ohjelmointirajapintaa tai PowerShellin cmdlet-komentoa. Voit myös suodattaa toimintotietoja päivämäärävälin, käyttäjän ja toiminnon tyypin mukaan.

### <a name="activity-log-requirements"></a>Toimintolokin vaatimukset

Seuraavien vaatimusten on täytyttävä Power BI:n toimintolokien käyttämistä varten:

- Sinun on oltava joko yleinen järjestelmänvalvoja tai Power BI ‑palvelun järjestelmänvalvoja.
- Olet asentanut [Power BI:n cmdlet-hallintaohjelmat](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt) paikallisesti tai käytät Power BI:n cmdlet-hallintaohjelmia Azure Cloud Shellin kautta.

### <a name="activityevents-rest-api"></a>ActivityEvents REST API

Voit viedä toimintotapahtumat blob-säilöön tai SQL-tietokantaan Power BI REST API ‑ohjelmointirajapintoihin perustuvan hallintasovelluksen avulla. Voit sitten rakentaa vietyjen tietojen päälle mukautetun käyttöraportin. **ActivityEvents** REST API ‑kutsuun on määritettävä alku- ja loppupäivämäärä sekä valinnaisesti myös suodatin, jolla toiminnot valitaan poimittaviksi joko toimintotyypin tai käyttäjätunnuksen perusteella. Koska toimintoloki voi sisältää suuren määrän tietoja, **ActivityEvents**-ohjelmointirajapinta tukee tällä hetkellä vain enintään yhden päivän tietojen lataamista pyyntöä kohden. Toisin sanoen alku- ja loppupäivämääräksi on määritettävä sama päivä, kuten alla olevassa esimerkissä. Muista määrittää DateTime-arvot UTC-muodossa.

```
https://api.powerbi.com/v1.0/myorg/admin/activityevents?startDateTime='2019-08-31T00:00:00'&endDateTime='2019-08-31T23:59:59'
```

Jos lokikirjausten määrä on suuri, **ActivityEvents**-ohjelmointirajapinta palauttaa vain noin 5 000 – 10 000 kirjausta sekä jatkumistunnuksen. Kutsu **ActivityEvents**-ohjelmointirajapintaa uudelleen jatkumistunnuksen avulla, jotta saat seuraavan kirjauserän, ja niin edelleen, kunnes olet noutanut kaikki kirjaukset etkä saa enää uutta jatkumistunnusta. Seuraavassa on esimerkki jatkumistunnuksen käytöstä.

```
https://api.powerbi.com/v1.0/myorg/admin/activityevents?continuationToken='%2BRID%3ARthsAIwfWGcVAAAAAAAAAA%3D%3D%23RT%3A4%23TRC%3A20%23FPC%3AARUAAAAAAAAAFwAAAAAAAAA%3D'
```

Riippumatta siitä, paljonko kirjauksia kutsusi noutaa, kutsu jatkumistunnuksella ohjelmointirajapintaa uudelleen niin kauan kuin saat tulosten mukana jatkumistunnuksen. Kutsu saattaa palauttaa jatkumistunnuksen myös niin, ettei sen yhteydessä palauteta yhtään toimintokirjauksia. Seuraavassa esimerkissä näytetään, miten vastauksessa palautettavan jatkumistunnuksen voi laittaa toistamaan kutsun:

```
while(response.ContinuationToken != null)
{
   // Store the activity event results in a list for example
    completeListOfActivityEvents.AddRange(response.ActivityEventEntities);

    // Make another call to the API with continuation token
    response = GetPowerBIActivityEvents(response.ContinuationToken)
}
completeListOfActivityEvents.AddRange(response.ActivityEventEntities);
```
> [!NOTE]
> Kaikkien tapahtumien näkyviin tuleminen voi kestää 24 tuntia, mutta täydelliset tiedot ovat yleensä käytettävissä paljon aikaisemmin.
>
>
### <a name="get-powerbiactivityevent-cmdlet"></a>Get-PowerBIActivityEvent-cmdlet

Lataa toimintatapahtumat PowerShellin Power BI Management ‑cmdletien avulla. **Get-PowerBIActivityEvent**-cmdlet  käsittelee jatkuvuustunnuksen automaattisesti. **Get-PowerBIActivityEvent**-cmdlet-komennossa StartDateTime- ja EndDateTime-parametreja koskevat samat rajoitukset kuin **ActivityEvents** REST API ‑ohjelmointirajapinnassa. Toisin sanoen alku- ja loppupäivämäärän on viitattava samaan päivämääräarvoon, koska voit noutaa kerrallaan toimintotiedot vain yhdeltä päivältä.

Seuraava komentosarja havainnollistaa, miten voit ladata kaikki Power BI ‑toiminnot. Komento muuntaa JSON-tulokset .NET-objekteiksi, jolloin pääset helposti tarkastelemaan yksittäisen toiminnon ominaisuuksia. Näissä esimerkeissä näytetään päivän pienin ja suurin mahdollinen aikaleima, jotta yksikään tapahtuma ei jää huomaamatta.

```powershell
Login-PowerBI

$activities = Get-PowerBIActivityEvent -StartDateTime '2019-08-31T00:00:00' -EndDateTime '2019-08-31T23:59:59' | ConvertFrom-Json

$activities.Count
$activities[0]

```

### <a name="filter-activity-data"></a>Toimintotietojen suodattaminen

Voit suodattaa toimintotapahtumia toimintotyypin ja käyttäjätunnuksen mukaan. Seuraava komentosarja havainnollistaa, miten ladataan vain **ViewDashboard**-toimintojen tapahtumatiedot. Lisätietoja tuetuista parametreista saat komennolla `Get-Help Get-PowerBIActivityEvent`.

```powershell
Login-PowerBI

$activities = Get-PowerBIActivityEvent -StartDateTime '2019-08-31T00:00:00' -EndDateTime '2019-08-31T23:59:59' -ActivityType 'ViewDashboard' | ConvertFrom-Json

$activities.Count
$activities[0]

```

## <a name="use-the-audit-log"></a>Valvontalokin käyttäminen

Jos tehtävänäsi on seurata käyttäjien toimintaa sekä Power BI:ssä että Office 365:ssä, voit hoitaa valvonnan joko Office 365:n Tietoturva- ja yhteensopivuuskeskuksen kautta tai käyttää PowerShelliä. Valvonta käyttää Exchange Onlinen toimintoja, jotka valmistellaan automaattisesti tukemaan Power BI:tä.

Voit suodattaa valvontatiedot päivämääräalueen, käyttäjän, koontinäytön, raportin, tietojoukon ja toimintatyypin mukaan. Voit myös ladata toimet CSV-tiedostoon (tiedosto, jonka arvot on erotettu luetteloerottimella) offline-tilassa analysointia varten.

### <a name="audit-log-requirements"></a>Valvontalokin vaatimukset

Seuraavat vaatimukset on täytettävä valvontalokien käyttämistä varten:

- Sinun on oltava yleinen järjestelmänvalvoja tai sinulla on oltava Exchange Onlinessa rooli, joka sallii valvontalokien käytön tai tarkastelun, jotta pääset näkemään valvontalokin. Oletusarvoisesti kyseiset roolit määritetään Yhteensopivuuden hallinta- ja Organisaation hallinta -rooliryhmille valmiiksi Exchangen hallintakeskuksen **Käyttöoikeudet**-sivulla.

    Jos haluat antaa valvontalokin käyttöoikeuden muulle kuin järjestelmänvalvojatilille, lisää kyseinen käyttäjä jompaankumpaan edellä mainituista rooliryhmistä. Vaihtoehtoisesti voit luoda Exchangen hallintakeskuksessa mukautetun rooliryhmän, jolle määrität valvontalokien käytön tai tarkastelun sallivan roolin ja johon sitten lisäät kyseisen tilin. Lisätietoja saat [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups) (Rooliryhmien hallinta Exchange Onlinessa) -ohjeartikkelista.

    Jos et pääse Exchangen hallintakeskukseen Microsoft 365 -hallintakeskuksesta, siirry osoitteeseen https://outlook.office365.com/ecp ja kirjaudu sisään tunnistetiedoillasi.

- Jos pääset valvontalokiin, mutta et ole yleinen järjestelmänvalvoja tai Power BI -palvelun järjestelmänvalvoja, et voi käyttää Power BI -hallintaportaalia. Tässä tapauksessa käytä suoraa linkkiä [Office 365:n tietoturva- ja yhteensopivuuskeskukseen](https://sip.protection.office.com/#/unifiedauditlog).

### <a name="access-your-audit-logs"></a>Valvontalokien käyttö

Jos haluat käyttää lokeja, varmista ensin, että sisäänkirjaus on käytössä Power BI:ssä. Jos haluat lisätietoja, katso artikkelia [Valvontalokit](service-admin-portal.md#audit-logs) hallintaportaalin dokumentaatiossa. Valvonnan käyttöönoton ja valvontatietojen tarkastelumahdollisuuden välillä voi olla jopa 48 tunnin viive. Jos et näe tietoja välittömästi, tarkista valvontalokit myöhemmin. Jos haet oikeuksia hallintalokien tarkasteluun, samanlainen viive voi esiintyä, ennen kuin oikeudet on myönnetty.

Power BI:n valvontalokit ovat saatavilla suoraan [Office 365:n tietoturva- ja yhteensopivuuskeskuksessa](https://sip.protection.office.com/#/unifiedauditlog). Täällä on myös linkki Power BI:n hallintaportaalista:

1. Valitse Power BI:ssä oikeasta yläkulmasta **hammasrataskuvake** ja valitse sitten **Hallintaportaali**.

   ![Näyttökuva hammasrataskuvakkeen avattavasta valikosta Hallintaportaali-kohta valittuna.](media/service-admin-auditing/powerbi-admin.png)

1. Valitse **Valvontalokit**.

1. Valitse **Siirry O365-hallintakeskukseen**.

   ![Näyttökuva hallintaportaalista Valvontalokit- ja Siirry Microsoft O365 -hallintakeskukseen -vaihtoehdot valittuina.](media/service-admin-auditing/audit-log-o365-admin-center.png)

### <a name="search-only-power-bi-activities"></a>Vain Power BI -toimien haku

Voit rajata tulokset vain Power BI -toimiin seuraavasti. Katso toimien luettelo jäljempänä tässä artikkelissa olevasta kohdasta, jossa on [Power BI:n valvomien toimien luettelo](#operations-available-in-the-audit-and-activity-logs).

1. Valitse **Haku valvontalokista** -sivun **Haku**-kohdasta avattava **Toimet**-luettelo.

2. Valitse **Power BI -toimet**.

   ![Näyttökuva Haku valvontalokista -kohdasta Power BI -toimet valittuina.](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Napsauta mistä tahansa valintaruudun ulkopuolelta sulkeaksesi sen.

Hakusi palauttavat vain Power BI -toimia.

### <a name="search-the-audit-logs-by-date"></a>Haku valvontalokeista päivämäärän mukaan

Voit hakea lokeista päivämääräalueen mukaan käyttämällä **Aloituspäivämäärä**- ja **Lopetuspäivämäärä**-kenttiä. Oletusvalinta on viimeiset seitsemän päivää. Päivämäärä ja aika näytetään muodossa koordinoitu yleisaika (UTC). Suurin päivämääräalue, jonka voit määrittää, on 90 päivää. 

Näkyviin tulee virhe, jos valittu päivämääräalue on yli 90 päivää. Jos käytät 90 päivän suurinta mahdollista päivämääräaluetta, valitse **aloituspäivämääräksi** tämänhetkinen aika. Muutoin näkyviin tulee virhe, jossa ilmoitetaan alkamispäivämäärän olevan päättymispäivämäärää aiemmin. Jos olet ottanut valvonnan käyttöön viimeisen 90 päivän aikana, suurin mahdollinen päivämääräalue ei voi alkaa ennen päivämäärää, jolloin valvonta otettiin käyttöön.

![Näyttökuva Haku valvontalokista -kohdasta, jossa Aloituspäivämäärä- ja Lopetuspäivämäärä-vaihtoehdot ovat valittuina.](media/service-admin-auditing/search-audit-log-by-date.png)

### <a name="search-the-audit-logs-by-users"></a>Haku valvontalokeista käyttäjien mukaan

Voit hakea valvontalokimerkinnöistä tiettyjen käyttäjien tekemiä toimia. Syötä yksi tai useampi käyttäjänimi **Käyttäjät**-kenttään. Käyttäjänimi näyttää sähköpostiosoitteelta. Se on tili, jolla käyttäjät kirjautuvat Power BI:hin. Jätä tämä ruutu tyhjäksi, jos haluat tulokseksi merkintöjä organisaatiosi kaikkien käyttäjien (ja palvelutilien) osalta.

![Hae käyttäjien mukaan](media/service-admin-auditing/search-audit-log-by-user.png)

### <a name="view-search-results"></a>Näytä hakutulokset

Kun olet valinnut **Hae**, hakutulokset ladataan. Muutaman hetken kuluttua ne näkyvät **Tulokset**-kohdassa. Kun haku on valmis, löytyneiden tulosten määrä tulee näkyviin. **Haku valvontalokista** näyttää enintään 1 000 tapahtumaa. Jos yli 1 000 tapahtumaa täyttää hakuehdot, sovellus näyttää 1 000 uusinta tapahtumaa.

#### <a name="view-the-main-results"></a>Näytä tärkeimmät tulokset

**Tulokset**-alueella on seuraavat tiedot kullekin haun palauttamalle tapahtumalle. Voit lajitella tulokset valitsemalla sarakkeen otsikon **Tulokset**-kohdasta.

| **Sarake** | **Määritelmä** |
| --- | --- |
| Päivämäärä |Päivämäärä ja aika (UTC-muodossa), jolloin tapahtuma ilmeni. |
| IP-osoite |Lokiin kirjatussa toimessa käytetyn laitteen IP-osoite. Sovellus näyttää IP-osoitteen joko IPv4- tai IPv6-osoitemuodossa. |
| Käyttäjä |Käyttäjä (tai palvelutili), joka suoritti tapahtuman aiheuttaneen toimen. |
| Toiminta |Käyttäjän suorittama toimi. Tämä arvo vastaa toimia, jotka olet valinnut avattavassa **Toimet**-luettelossa. Exchange-järjestelmänvalvojan valvontalokin tapahtuman osalta tämän sarakkeen arvo on Exchange cmdlet-komento. |
| Kohde |Objekti, joka luotiin tai jota muokattiin vastaavan toimen vuoksi. Esimerkiksi tarkasteltu tai muokattu tiedosto tai päivitetty käyttäjätili. Kaikilla toimilla ei ole arvoa tässä sarakkeessa. |
| Tieto |Lisätieto toimesta. Tässäkään kaikilla toimilla ei ole arvoa. |

#### <a name="view-the-details-for-an-event"></a>Tapahtuman tietojen tarkasteleminen

Voit tarkastella lisätietoja tapahtumasta valitsemalla tapahtuman tietueen hakutulosluettelosta. Näkyviin tulee **Tiedot**-sivu, johon sisältyvät yksityiskohtaiset ominaisuudet tapahtuman tietueesta. **Tiedot**-sivulla näytettävät ominaisuudet riippuvat siitä, missä Office 365 -palvelussa tapahtuma ilmenee.

Saat näkyviin nämä tiedot valitsemalla **Lisätiedot**. Kaikkien Power BI -syötteiden RecordType-ominaisuuden arvo on 20. Katso lisätietoja muista ominaisuuksista artikkelista [Yksityiskohtaiset ominaisuudet valvontalokissa](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/).

   ![Näyttökuva valvontatietojen valinta ikkunasta Lisätietoja-vaihtoehto valittuna.](media/service-admin-auditing/audit-details.png)

### <a name="export-search-results"></a>Hakutulosten vieminen

Voit viedä Power BI -valvontalokin CSV-tiedostoon seuraavasti.

1. Valitse **Vie tulokset**.

1. Valitse joko **Tallenna ladatut tulokset** tai **Lataa kaikki tulokset**.

    ![Näyttökuva Vie tulokset -vaihtoehdosta.](media/service-admin-auditing/export-auditing-results.png)

### <a name="use-powershell-to-search-audit-logs"></a>Valvontalokien hakeminen PowerShellin avulla

Voit myös käyttää valvontalokeja PowerShellin avulla sisäänkirjautumisesi perusteella. Seuraavassa esimerkissä näytetään, miten voit muodostaa yhteyden Exchange Online PowerShelliin ja hakea sitten Power BI -valvontalokisyötteet [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/)-komennolla. Jotta voit suorittaa komentosarjan, järjestelmänvalvojan on määritettävä sinulle [Valvontalokin vaatimukset](#audit-log-requirements) ‑osiossa kuvatut oikeudet.

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

### <a name="use-powershell-to-export-audit-logs"></a>Valvontalokien vieminen PowerShellin avulla

Voit myös viedä valvonta lokien hakutulokset PowerShellin avulla. Seuraavassa esimerkissä kuvataan lähettäminen [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/)-komennosta ja tulosten vieminen [Export-Csv](/powershell/module/microsoft.powershell.utility/export-csv)-cmdlet-komennolla. Jotta voit suorittaa komentosarjan, järjestelmänvalvojan on määritettävä sinulle [Valvontalokin vaatimukset](#audit-log-requirements) ‑osiossa kuvatut oikeudet.

```powershell
$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2019 -EndDate 9/15/2019 -RecordType PowerBI -ResultSize 5000 |
Export-Csv -Path "c:\temp\PowerBIAuditLog.csv" -NoTypeInformation

Remove-PSSession $Session
```

Lisätietoja Exchange Onlineen yhdistämisestä on kohdassa [Yhdistäminen kohteeseen Exchange Online PowerShell](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/). Katso toinen esimerkki PowerShellin käyttämisestä valvontalokien avulla artikkelista [Power BI -valvontalokin ja PowerShellin käyttäminen Power BI Pro -käyttöoikeuksien määrittämiseksi](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="operations-available-in-the-audit-and-activity-logs"></a>Valvonta- ja toimintolokien käytettävissä olevat toiminnot

Seuraavat toiminnot ovat käytettävissä sekä valvonta- että toimintolokeissa.

| Kutsumanimi                                     | Toiminnon nimi                              | Huomautukset                                  |
|---------------------------------------------------|---------------------------------------------|------------------------------------------|
| Lisätty tietolähde Power BI -yhdyskäytävään             | AddDatasourceToGateway                      |                                          |
| Lisätty Power BI -kansion käyttöoikeus                      | AddFolderAccess                             | Ei tällä hetkellä käytössä                       |
| Lisätty Power BI -ryhmän jäsenet                      | AddGroupMembers                             |                                          |
| Järjestelmänvalvoja liitti tietovuon tallennustilin vuokraajaan | AdminAttachedDataflowStorageAccountToTenant | Ei tällä hetkellä käytössä                       |
| Analysoitu Power BI -tietojoukko                         | AnalyzedByExternalApplication               |                                          |
| Analysoitu Power BI -raportti                          | AnalyzeInExcel                              | Muodostetaan, kun käyttäjät käyttävät palvelua. Tiedoston `*.odc` lataaminen ei luo valvontatapahtumaa                                         |
| Liitetty tietovuon tallennustili                 | AttachedDataflowStorageAccount              |                                          |
| Sidottu Power BI -tietojoukko yhdyskäytävään                | BindToGateway                               |                                          |
| Peruutettu tietovuon päivitys                        | CancelDataflowRefresh                       |                                          |
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
| Luotu Power BI -raportti                           | CreateReport <sup>1</sup>                                |                                          |
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
| Muokatut tietovuon ominaisuudet                        | EditDataflowProperties                      |                                          |
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
| Julkaistu Power BI -raportti verkkoon                  | PublishToWebReport <sup>2</sup>                         |                                          |
| Vastaanotettu salainen Power BI -tietovuo Key Vaultista  | ReceiveDataflowSecretFromKeyVault           |                                          |
| Poistettu tietolähde Power BI -yhdyskäytävästä         | RemoveDatasourceFromGateway                 |                                          |
| Poistettu Power BI -ryhmän jäsenet                    | DeleteGroupMembers                          |                                          |
| Poistettu työtila kapasiteetista                 | RemoveWorkspacesFromCapacity                |                                          |
| Nimetty uudelleen Power BI -koontinäyttö                        | RenameDashboard                             |                                          |
| Pyydetty Power BI -tietovuon päivitystä               | RequestDataflowRefresh                      | Ei tällä hetkellä käytössä                       |
| Pyydetty Power BI -tietojoukon päivitystä                | RefreshDataset                              |                                          |
| Noudettu Power BI -työtilat                     | GetWorkspaces                               |                                          |
| Määritetty työtilan tietovuon tallennussijainti     | SetDataflowStorageLocationForWorkspace      |                                          |
| Määritetty ajoitettu päivitys Power BI -tietovuolle        | SetScheduledRefreshOnDataflow               |                                          |
| Määritetty ajoitettu päivitys Power BI -tietojoukolle         | SetScheduledRefresh                         |                                          |
| Jaettu Power BI -koontinäyttö                         | ShareDashboard                              |                                          |
| Jaettu Power BI -raportti                            | ShareReport                                 |                                          |
| Power BI:n pidennetty kokeilujakso aloitettu                   | OptInForExtendedProTrial                    | Ei tällä hetkellä käytössä                       |
| Aloitettu Power BI -kokeilujakso                            | OptInForProTrial                            |                                          |
| Ota haltuun Power BI -tietolähde                   | TakeOverDatasource                          |                                          |
| Ota haltuun Power BI -tietojoukko                        | TakeOverDataset                             |                                          |
| Otti haltuun Power BI -tietovuon                     | TookOverDataflow                             |                                          |
| Julkaisematon Power BI -sovellus                          | UnpublishApp                                |                                          |
| Päivitä kapasiteetin resurssin hallinnan asetukset      | UpdateCapacityResourceGovernanceSettings    | Ei tällä hetkellä Microsoft 365 -hallintakeskuksessa |
| Päivitetty kapasiteetin järjestelmänvalvoja                            | UpdateCapacityAdmins                        |                                          |
| Päivitetty kapasiteetin näyttönimi                     | UpdateCapacityDisplayName                   |                                          |
| Päivitetyt tietovuon tallennustilan määrityksen käyttöoikeudet   | UpdatedDataflowStorageAssignmentPermissions |                                          |
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

<sup>1</sup> Julkaiseminen Power BI Desktopista palveluun on palvelussa CreateReport-tapahtuma.

<sup>2</sup> PublishtoWebReport viittaa [Julkaise verkkoon](service-publish-to-web.md) ‑ominaisuuteen.

## <a name="next-steps"></a>Seuraavat vaiheet

[Mitä on Power BI:n hallinta?](service-admin-administering-power-bi-in-your-organization.md)  

[Power BI -hallintaportaali](service-admin-portal.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
