---
title: Valvonnan käyttö organisaatiossa
description: Lue, miten voit Power BI:n avulla käyttää valvontaa toteutettujen toimien seuraamista ja tutkimista varten. Voit käyttää tietoturva- ja yhteensopivuuskeskusta tai PowerShelliä.
services: powerbi
documentationcenter: ''
author: mgblythe
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
ms.date: 12/12/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 46f8d11d45423a9f7df96ac4d1e59c5d805304a7
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/08/2018
ms.locfileid: "30977302"
---
# <a name="using-auditing-within-your-organization"></a>Valvonnan käyttö organisaatiossa

<iframe width="560" height="315" src="https://www.youtube.com/embed/zj4kA39jV_4?showinfo=0" frameborder="0" allowfullscreen></iframe>

Lue, miten voit Power BI:n avulla käyttää valvontaa toteutettujen toimien seuraamista ja tutkimista varten. Voit käyttää tietoturva- ja yhteensopivuuskeskusta tai PowerShelliä.

Sen tietäminen, kuka tekee mitä toimia missäkin Power BI -vuokraajasi kohteissa, voi olla ratkaisevaa, kun autetaan organisaatiotasi toteuttamaan sille asetetut vaatimukset, kuten säädösten noudattaminen ja tietueiden hallinta.

Voit suodattaa valvontatiedot päivämääräalueen, käyttäjän, koontinäytön, raportin, tietojoukon ja toimintatyypin mukaan. Voit myös ladata toimet CSV-tiedostoon (tiedosto, jonka arvot on erotettu luetteloerottimella) offline-tilassa analysointia varten.

> [!NOTE]
> Power BI:n valvontatoiminto on esikatselutilassa ja on käytettävissä kaikilla tietoalueilla.

## <a name="requirements"></a>Vaatimukset
Seuraavat vaatimukset on täytettävä valvontalokien käyttämistä varten:

- Jotta voisit käyttää Office 365:n tietoturva- ja yhteensopivuuskeskuksen valvontaosaa, sinulla on oltava Exchange Online -lisenssi (sisältyy Office 365 Enterprise E3- ja E5 -tilauksiin).
- Sinun on joko oltava yleinen järjestelmänvalvoja tai sinulla on oltava Exchange-järjestelmänvalvojarooli, joka mahdollistaa valvontalokin käytön. 

  Exchange-järjestelmänvalvojarooleja hallitaan Exchangen hallintakeskuksen kautta. Lisätietoja on kohdassa [Exchange Onlinen käyttöoikeudet](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx).

- Jos pääset valvontalokiin, mutta et ole yleinen järjestelmänvalvoja tai Power BI -palvelun järjestelmänvalvoja, et voi käyttää Power BI -hallintaportaalia. Tässä tapauksessa sinun on saatava suora linkki Office 365:n tietoturva- ja yhteensopivuuskeskukseen.

## <a name="enabling-auditing-functionality-in-the-power-bi-admin-portal"></a>Valvontatoiminnon käyttöönotto Power BI -hallintaportaalissa

Sinun on otettava organisaatiosi osalta valvonta käyttöön, jotta voit käsitellä raportteja. Voit tehdä tämän hallintaportaalin vuokraaja-asetuksissa.

1. Valitse **hammasrataskuvake** oikeasta yläkulmasta.

2. Valitse **Hallintaportaali**.
   
   ![](media/service-admin-auditing/powerbi-admin.png)

3. Valitse **Vuokraaja-asetukset**.
   
   ![](media/service-admin-auditing/powerbi-admin-tenant-settings.png)

4. Kytke päälle **Valvontalokien luominen sisäisen toiminnan valvonnan ja vaatimustenmukaisuuden tarpeisiin**.

5. Valitse **Käytä**.

Power BI alkaa kirjata erilaisia toimia, joita käyttäjäsi suorittavat Power BI:ssä. Kestää jopa 48 tuntia, ennen kuin lokit näkyvät O365:n tietoturva- ja yhteensopivuuskeskuksessa. Lisätietoja kirjattavista toimista on kohdassa [Luettelo Power BI:n valvomista toimista](#list-of-activities-audited-by-power-bi).

> [!NOTE]
> Jos haluat ottaa Power BI:n valvonnan käyttöön vuokraajassasi, siinä on oltava vähintään yksi Exchange-postilaatikon käyttöoikeus.

## <a name="accessing-your-audit-logs"></a>Valvontalokien käyttö

Voit valvoa Power BI -lokeja käymällä O365:n tietoturva- ja yhteensopivuuskeskuksessa.

1. Valitse **hammasrataskuvake** oikeasta yläkulmasta.

2. Valitse **Hallintaportaali**.
   
   ![](media/service-admin-auditing/powerbi-admin.png)

3. Valitse **Valvontalokit**.
 
4. Valitse **Siirry O365-hallintakeskukseen**.
   
   ![](media/service-admin-auditing/audit-log-o365-admin-center.png)

Vaihtoehtoisesti voit selata kohtaan [Office 365 | Tietoturva ja yhteensopivuus](https://protection.office.com/#/unifiedauditlog).

> [!NOTE]
> Voi sallia muille kuin järjestelmänvalvojatileille valvontalokin käytön myöntämällä oikeuksia Exchange Online -hallintakeskuksessa. Voit esimerkiksi määrittää käyttäjän olemassa olevaan rooliryhmään, kuten organisaation hallinta, tai luoda uuden rooliryhmän roolilla valvontalokit. Lisätietoja on artikkelissa [Exchange Onlinen käyttöoikeudet](https://technet.microsoft.com/library/jj200692\(v=exchg.150\).aspx).

## <a name="search-only-power-bi-activities"></a>Vain Power BI -toimien haku

Voit rajata tulokset vain Power BI -toimiin tekemällä seuraavasti.

1. Valitse sivulla **Haku valvontalokista** avattava luettelo aiheesta **Toimet** kohdassa **Haku**.

2. Valitse **Power BI -toimet**.
   
   ![](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Napsauta mistä tahansa valintaruudun ulkopuolelta sulkeaksesi sen.

Hakusi suodatetaan nyt vain Power BI -toimiin.

## <a name="search-the-audit-logs-by-date"></a>Haku valvontalokeista päivämäärän mukaan

Voit hakea lokeista päivämääräalueen mukaan käyttämällä kenttiä ”Alkamispäivämäärä” ja ”Päättymispäivämäärä”. Oletusarvoisesti valittuna on seitsemän viime päivää. Päivämäärä ja aika näytetään muodossa koordinoitu yleisaika (UTC). Suurin päivämääräalue, jonka voit määrittää, on 90 päivää. Näkyviin tulee virhe, jos valittu päivämääräalue on yli 90 päivää.

> [!NOTE]
> Jos käytät 90 päivän suurinta mahdollista päivämääräaluetta, valitse alkamispäivämääräksi tämänhetkinen aika. Muutoin näkyviin tulee virhe, jossa ilmoitetaan alkamispäivämäärän olevan päättymispäivämäärää aiemmin. Jos olet ottanut valvonnan käyttöön 90 viime päivän aikana, suurin mahdollinen päivämääräalue ei voi alkaa ennen päivämäärää, jolloin valvonta otettiin käyttöön.

![](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>Haku valvontalokeista käyttäjien mukaan

Voit hakea valvontalokimerkinnöistä tiettyjen käyttäjien suorittamia toimia. Voit tehdä tämän syöttämällä yhden tai useamman käyttäjänimen kenttään ”Käyttäjät”.  Kyseessä on käyttäjänimi, jolla he kirjautuvat Power BI:hin. Se näyttää sähköpostiosoitteelta.
Jätä tämä ruutu tyhjäksi, jos haluat tulokseksi merkintöjä organisaatiosi kaikkien käyttäjien (ja palvelutilien) osalta.

![](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="viewing-search-results"></a>Hakutulosten tarkastelu

Kun painat hakupainiketta, hakutulokset ladataan, ja hetken kuluttua ne näkyvät kohdassa Tulokset. Kun haku on valmis, löytyneiden tulosten määrä tulee näkyviin. 

> [!NOTE]
> Enintään 1 000 tapahtumaa näytetään; jos hakuehtojen mukaisia tapahtumia on yli 1 000, uusimmat 1 000 tapahtumaa näytetään.

Tulokset sisältävät seuraavat tiedot jokaisesta haun palauttamasta tapahtumasta.

| **Sarake** | **Määritelmä** |
| --- | --- |
| Päivämäärä |Päivämäärä ja aika (UTC-muodossa), jolloin tapahtuma ilmeni. |
| IP-osoite |Sen laitteen IP-osoite, jota käytettiin toimen kirjaamisen aikana. IP-osoite näkyy joko IPv4- tai IPv6-osoitemuodossa. |
| Käyttäjä |Käyttäjä (tai palvelutili), joka suoritti tapahtuman aiheuttaneen toimen. |
| Toimi |Käyttäjän suorittama toimi. Tämä arvo vastaa toimia, jotka olet valinnut avattavassa luettelossa Toimet. Exchange-järjestelmänvalvojan valvontalokin tapahtuman osalta tämän sarakkeen arvo on Exchange cmdlet-komento. |
| Kohde |Objekti, joka luotiin tai jota muokattiin vastaavan toimen seurauksena. Esimerkiksi tiedosto, jota tarkasteltiin tai muokattiin tai käyttäjätili, jota päivitettiin. Kaikilla toimilla ei ole arvoa tässä sarakkeessa. |
| Tieto |Lisätieto toimesta. Tässäkään kaikilla toimilla ei ole arvoa. |

> [!NOTE]
> Saat lajiteltua tulokset valitsemalla sarakkeen otsikon kohdasta Tulokset. Voit lajitella tulokset järjestykseen A–Ö tai Ö–A. Napsauta Päivämäärä-otsikkoa tulosten lajittelemiseksi vanhimmasta uusimpaan tai uusimmasta vanhimpaan.

## <a name="view-the-details-for-an-event"></a>Tapahtuman tietojen tarkasteleminen

Voit tarkastella lisätietoja tapahtumasta valitsemalla tapahtuman tietueen hakutulosluettelosta. Näkyviin tulee tietosivu, johon sisältyvät yksityiskohtaiset ominaisuudet tapahtuman tietueesta. Näytettävät ominaisuudet riippuvat siitä, missä Office 365 -palvelussa tapahtuma ilmenee. Saat näkyviin lisätietoja valitsemalla **Lisätiedot**.

Seuraavassa taulukossa ovat tiedot, joita voi tulla näkyviin.

| **Parametri tai tapahtuma** | **Kuvaus** | **Lisätiedot** |
| --- | --- | --- |
| Ladattu Power BI -raportti |Tämä toimi kirjataan aina, kun raportti ladataan |Raportin nimi, tietojoukon nimi |
| Luo raportti |Tämä toimi kirjataan aina, kun luodaan uusi raportti. |Raportin nimi, tietojoukon nimi |
| Muokkaa raporttia |Tämä toimi kirjataan aina, kun raporttia muokataan. |Raportin nimi, tietojoukon nimi |
| Luo tietojoukko |Tämä toimi kirjataan aina, kun luodaan tietojoukko. |Tietojoukon nimi, DataConnectivityMode |
| Poista tietojoukko |Tämä toimi kirjataan aina, kun poistetaan tietojoukko. |Tietojoukon nimi, DataConnectivityMode |
| Luo Power BI -sovellus |Tämä toimi kirjataan aina, kun luodaan Power BI -sovellus |Sovelluksen nimi, oikeudet, työtilan nimi |
| Asenna Power BI -sovellus |Tämä toimi kirjataan aina, kun asennetaan Power AI -sovellus |Sovelluksen nimi |
| Päivitä Power BI -sovellus |Tämä toimi kirjataan aina, kun Power-sovellus päivitetään |Sovelluksen nimi, oikeudet, työtilan nimi |
| Power BI:n pidennetty kokeilujakso aloitettu |Tämä toimi kirjataan aina, kun käyttäjä hyväksyy pidennetyn pro-kokeilujakson, joka jatkuu 31. toukokuuta 2018 asti | |
| Analysoitu Power BI -tietojoukko |Tämä toimi kirjataan aina, kun Power BI -tietojoukko analysoidaan Excelissä. | |
| Luotu Power BI -yhdyskäytävä |Tämä toimi kirjataan aina, kun luodaan uusi yhdyskäytävä. |Yhdyskäytävän nimi, yhdyskäytävän tyyppi |
| Poistettu Power BI -yhdyskäytävä |Tämä toimi kirjataan aina, kun poistetaan yhdyskäytävä. |Yhdyskäytävän nimi, yhdyskäytävän tyyppi |
| Lisätty tietolähde Power BI -yhdyskäytävään |Tämä toimi kirjataan aina, kun tietolähde lisätään yhdyskäytävään |Yhdyskäytävän nimi, yhdyskäytävän tyyppi, tietolähteen nimi, tietolähteen tyyppi |
| Poistettu tietolähde Power BI -yhdyskäytävästä |Tämä toimi kirjataan aina, kun tietolähde poistetaan yhdyskäytävästä |Yhdyskäytävän nimi, yhdyskäytävän tyyppi, tietolähteen nimi, tietolähteen tyyppi |
| Muutettu Power BI -yhdyskäytävän järjestelmänvalvojia |Tämä toimi kirjataan aina, kun yhdyskäytävän järjestelmänvalvojia muutetaan (lisätään tai poistetaan) |Yhdyskäytävän nimi, lisätyt käyttäjät, poistetut käyttäjät |
| Muutettu Power BI -yhdyskäytävän tietolähteen käyttäjiä |Tämä toimi kirjataan aina, kun yhdyskäytävän käyttäjiä muutetaan (lisätään tai poistetaan) |Yhdyskäytävän nimi, lisätyt käyttäjät, poistetut käyttäjät |
| SetScheduledRefresh |Tämä toimi kirjataan aina, kun tietojoukolle ajoitetaan uusi päivitys |Tietojoukon nimi, päivitystaajuus (minuuteissa) |

## <a name="using-powershell-to-search"></a>Haku PowerShellin avulla

PowerShellin avulla voit käyttää valvontalokeja kirjautumisesi perusteella. Tämä tehdään käyttämällä Exchange Onlinea. Tässä on esimerkki komennosta, jolla haetaan Power BI:n valvontalokimerkintöjä.

> [!NOTE]
> Jotta voisit käyttää New-PSSession-komentoa, tilillesi on oltava määritetty Exchange Online -lisenssi ja sinun on voitava käyttää vuokraajasi valvontalokia.

```
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2016 -EndDate 9/15/2016 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

Lisätietoja Exchange Onlineen yhdistämisestä on kohdassa [Yhdistäminen kohteeseen Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289\(v=exchg.160\).aspx).

Lisätietoja parametreista ja Search-UnifiedAuditLog-komennon käytöstä on kohdassa [Search-UnifiedAuditLog](https://technet.microsoft.com/library/mt238501\(v=exchg.160\).aspx).

Jos haluat nähdä esimerkin PowerShellin käytöstä valvontalokista hakua ja sitten Power BI Pro -käyttöoikeuksien myöntämistä varten merkintöjen perusteella, katso [Power BI:n valvontalokin ja PowerShellin käyttö Power BI Pro -käyttöoikeuksien myöntämiseen](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="export-the-power-bi-audit-log"></a>Vie Power BI -valvontaloki

Voit viedä Power BI -valvontalokin CSV-tiedostoon.

1. Valitse **Vie tulokset**.

2. Valitse joko **Tallenna ladatut tulokset** tai **Lataa kaikki tulokset**.
   
   ![](media/service-admin-auditing/export-auditing-results.png)

## <a name="record-and-user-types"></a>Tietue- ja käyttäjätyypit

Valvontalokimerkinnöillä on RecordType ja UserType osana merkinnän tietoja. Kaikilla Power BI -merkinnöillä RecordType on 20.

Täydellistä luetteloa varten katso [Office 365:n valvontalokin yksityiskohtaiset ominaisuudet](https://support.office.com/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)

## <a name="list-of-activities-audited-by-power-bi"></a>Luettelo Power BI:n valvomista toimista

| Toimi | Kuvaus | Lisätiedot |
| --- | --- | --- |
| CreateDashboard |Tämä toimi kirjataan aina, kun luodaan uusi koontinäyttö. |- Koontinäytön nimi. |
| EditDashboard |Tämä toimi kirjataan aina, kun nimetään koontinäyttö uudelleen. |- Koontinäytön nimi. |
| DeleteDashboard |Tämä toimi kirjataan aina, kun poistetaan koontinäyttö. |- Koontinäytön nimi. |
| PrintDashboard |Tämä tapahtuma kirjataan aina, kun tulostetaan koontinäyttö. |- Koontinäytön nimi.<br/>- Tietojoukon nimi |
| ShareDashboard |Tämä toimi kirjataan aina, kun jaetaan koontinäyttö. |- Koontinäytön nimi.<br/>- Vastaanottajan sähköpostiosoite.<br/>- Tietojoukon nimi.<br>- Oikeudet jakaa uudelleen. |
| ViewDashboard |Tämä toimi kirjataan aina, kun koontinäyttöä katsellaan. |- Koontinäytön nimi. |
| ExportTile |Tämä tapahtuma kirjataan aina, kun tietoja viedään koontinäyttöruudusta. |- Ruudun nimi.<br/>- Tietojoukon nimi. |
| DeleteReport |Tämä toimi kirjataan aina, kun raportti poistetaan. |- Raportin nimi. |
| ExportReport |Tämä tapahtuma kirjataan aina, kun tietoja viedään raporttiruudusta. |- Raportin nimi.<br/>- Tietojoukon nimi. |
| PrintReport |Tämä tapahtuma kirjataan aina, kun raportti tulostetaan. |- Raportin nimi.<br/>- Tietojoukon nimi. |
| PublishToWebReport |Tämä tapahtuma kirjataan aina, kun raportti julkaistaan verkkoon. |- Raportin nimi.<br/>- Tietojoukon nimi. |
| ViewReport |Tämä toimi kirjataan aina, kun raporttia katsellaan. |- Raportin nimi. |
| ExploreDataset |Tämä tapahtuma kirjataan aina, kun tutkit tietojoukkoa valitsemalla sen. |- Tietojoukon nimi |
| DeleteDataset |Tämä tapahtuma kirjataan aina, kun poistetaan tietojoukko. |- Tietojoukon nimi. |
| CreateOrgApp |Tämä toimi kirjataan aina, kun luodaan organisaation sisältöpaketti. |- Organisaation sisältöpaketin nimi.<br/>- Koontinäyttöjen nimet.<br/>- Raporttien nimet.<br/>- Tietojoukkojen nimet. |
| CreateGroup |Tämä toimi käynnistetään aina, kun ryhmä luodaan. |- Ryhmän nimi. |
| AddGroupMembers |Tämä toimi kirjataan aina, kun Power BI -ryhmätyötilaan lisätään jäsen. |- Ryhmän nimi.<br/>- Sähköpostiosoitteet. |
| UpdatedAdminFeatureSwitch |Tämä tapahtuma kirjataan aina, kun järjestelmänvalvojan ominaisuusvalitsinta muutetaan. |- Valitsimen nimi.<br/>- Uusi valitsintila. |
| OptInForProTrial |Tämä tapahtuma kirjataan, kun käyttäjä päättää kokeilla Power BI Pro:ta palvelussa. |- sähköpostiosoite |

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI -hallintaportaali](service-admin-portal.md)  
[Power BI Premium – mikä se on?](service-premium.md)  
[Power BI Pron ostaminen](service-admin-purchasing-power-bi-pro.md)  
[Exchange Onlinen käyttöoikeudet](https://technet.microsoft.com/library/jj200692\(v=exchg.150\).aspx)  
[Yhdistäminen kohteeseen Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289\(v=exchg.160\).aspx)  
[Search-UnifiedAuditLog](https://technet.microsoft.com/library/mt238501\(v=exchg.160\).aspx)  
[Office 365:n valvontalokin yksityiskohtaiset ominaisuudet](https://support.office.com/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)