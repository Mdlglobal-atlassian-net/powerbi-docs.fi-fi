---
title: Power BI:n hallinnointi - usein kysytyt kysymykset (UKK)
description: Lue vastauksia usein kysyttyihin kysymyksiin liittyen Power BI-rekisteröityminen, vuokraajien hallinnointiin ja muihin hallintatehtäviin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2e51017333a940bd9d7838e6a903c1a66ce2e342
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100757"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Power BI:n hallinnointi - usein kysytyt kysymykset (UKK)

Tämä artikkeli vastaa Power BI -hallinnoinnista usein kysyttyihin kysymyksiin. Yleiskatsaus Power BI -hallinnoinnista löytyy kohdasta [Mitä on Power BI:n hallinta](service-admin-administering-power-bi-in-your-organization.md).

## <a name="whats-in-this-article"></a>Tämän artikkelin sisältö

### <a name="sign-up-for-power-bi-section"></a>Rekisteröidy Power BI:hin -osio

* [PowerShellin käyttäminen](#using-powershell)
* [Miten käyttäjät voivat rekisteröityä Power BI:hin?](#how-do-users-sign-up-for-power-bi)
* [Miten organisaationi yksittäiset käyttäjät rekisteröityvät?](#how-do-individual-users-in-my-organization-sign-up)
* [Miten voin estää käyttäjiä liittymästä aiemmin luotuun Office 365 -vuokraajaan?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [Miten voin sallia käyttäjien liittyä aiemmin luotuun Office 365 -vuokraajaan?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [Miten voin tarkistaa, onko lohkon vuokraajaan?](#how-do-i-check-if-i-have-the-block-on-in-the-tenant)
* [Miten voin estää olemassa olevilta käyttäjiltä Power BI:n käytön aloittamisen?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Miten voin sallia olemassa oleville käyttäjille Power BI:hin rekisteröitymisen?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

### <a name="administration-of-power-bi-section"></a>Power BI:n hallinta -osio

* [Miten tämä muuttaa tapaa, jolla hallinnoin tällä hetkellä organisaationi käyttäjien käyttäjätietoja?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Miten Power BI:tä hallitaan?](#how-do-we-manage-power-bi)
* [Millä tavalla voin hallinnoida vuokraajaa, jonka Microsoft on luonut käyttäjiäni varten?](#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users)
* [Jos minulla on useita toimialueita, voinko hallinnoida Office 365-vuokraajaa, johon käyttäjät lisätään?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to)
* [Miten voin poistaa Power BI:n käyttäjiltä, jotka ovat jo rekisteröityneet?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Mistä tiedän, milloin uudet käyttäjät ovat liittyneet vuokraajaani?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Onko muita asioita, joihin minun kannattaa valmistautua?](#are-there-any-additional-things-i-should-prepare-for)
* [Missä Power BI -vuokraajani sijaitsee?](#where-is-my-power-bi-tenant-located)
* [Mikä on Power BI:n palvelutasosopimus?](#what-is-the-power-bi-sla)
* [Miten Power BI takaa suuren käytettävyyden ja vikasietoisuuden?](#how-does-power-bi-handle-high-availability-and-failover)

### <a name="security-in-power-bi-section"></a>Suojaus Power BI:ssä -osio

* [Onko Power BI kansallisten, alueellisten ja alakohtaisten vaatimusten mukainen?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Miten suojaus toimii Power BI:ssä?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Rekisteröidy Power BI:hin

### <a name="using-powershell"></a>PowerShellin käyttäminen

Jotkin tämän osion toimintosarjat edellyttävät Windows PowerShell -komentosarjoja. Jos et ole aiemmin käyttänyt PowerShelliä, sinun kannattaa tutustua [PowerShellin aloitusoppaaseen](http://go.microsoft.com/fwlink/p/?LinkID=286814). Jotta voit suorittaa komentosarjoja, asenna ensin [Azure Active Directory PowerShell for Graphin](/powershell/azure/active-directory/) uusin 64-bittinen versio.

### <a name="how-do-users-sign-up-for-power-bi"></a>Miten käyttäjät voivat rekisteröityä Power BI:hin?

Järjestelmänvalvojana voit rekisteröityä Power BI kautta [Power BI-WWW-sivuston](https://powerbi.microsoft.com) tai [Ostopalvelut](https://admin.microsoft.com/AdminPortal/Home#/catalog) Microsoft 365-hallintakeskuksen sivun. Kun järjestelmänvalvoja rekisteröityy Power BI-, hän voi määrittää käyttöoikeudet käyttäjille, jotka tarvitsevat käyttöoikeuden.

Lisäksi organisaation yksittäiset käyttäjät voivat ehkä rekisteröityä Power BI:hin [Power BI -sivuston](https://powerbi.microsoft.com) kautta. Kun organisaatiosi käyttäjä rekisteröityy Power BI-, palvelun määrittää automaattisesti Power BI-käyttöoikeus käyttäjälle. Katso lisätietoja, [Power BI yksityishenkilönä rekisteröityminen](service-self-service-signup-for-power-bi.md) ja [Power BI-käyttöoikeuksien organisaatiosi](service-admin-licensing-organization.md).

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Miten organisaationi yksittäiset käyttäjät rekisteröityvät?

Organisaation käyttäjiin saattaa liittyä kolme tilannetta:

* **Skenaario 1**: Organisaatiolla on jo Office 365 -ympäristö ja Power BI:hin rekisteröityvällä käyttäjällä on jo Office 365 -tili.
    Tässä skenaariossa, jos käyttäjä on jo työpaikan tai oppilaitoksen tili vuokraajassa (esimerkiksi contoso.com) mutta ei vielä Power BI-, Microsoft yksinkertaisesti Aktivoi sopimuksen tilille. Käyttäjälle ilmoitetaan automaattisesti tietoja siitä, miten voit käyttää Power BI-palvelun kanssa.

* **Skenaario 2**: Organisaatiolla on jo Office 365 -ympäristö, mutta Power BI:hin rekisteröityvällä käyttäjällä ei ole Office 365 -tiliä.
    Tässä skenaariossa käyttäjä on sähköpostiosoite organisaatiosi toimialueella (esimerkiksi contoso.com) mutta ei vielä ole Office 365-tiliä. Käyttäjä voi tässä tapauksessa rekisteröityä Power BI:hin, ja hän saa automaattisesti tilin. Tämän toiminnon avulla käyttäjä pääsee käyttämään Power BI-palvelua. Esimerkiksi jos työntekijä nimeltä Nancy käyttää työstään sähköpostiosoite (kuten nancy@contoso.com), Rekisteröidy Microsoft automaattisesti lisää Nancyn Contoson Office 365-ympäristön käyttäjäksi ja aktivoi Power BI-tilille.

* **Skenaario 3**: Organisaatiosi ei ole sähköpostin toimialueeseen liitettyä Office 365-ympäristöä.
    Suoritettavia järjestelmänvalvojan toimintoja ei ole organisaatiosi voi hyödyntää Power BI vaaditaan. Palvelun Lisää käyttäjät uuden, vain pilvessä olevaan hakemistoon. Voit myös ryhtyä vuokraajan järjestelmänvalvojaksi ja hallita niitä.

> [!IMPORTANT]
> Jos organisaatiossa on useita sähköpostitoimialueita ja haluat kaikkien sähköpostiosoitteiden tunnisteiden olevan samassa vuokraajassa, lisää kaikki sähköpostiosoitteiden toimialueet Azure Active Directory -vuokraajaan ennen kuin käyttäjät rekisteröityvät. Kun olet luonut käyttäjille, ei ole automaattista mekanismia käyttäjien siirtämiseksi vuokraajien välillä. Katso lisätietoja tästä prosessista [jos minulla on useita toimialueita, voinko hallinnoida Office 365-vuokraajaa, johon käyttäjät lisätään?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to) myöhemmin tässä artikkelissa ja [toimialueen lisääminen Office 365: n](/office365/admin/setup/add-domain/).

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Miten voin estää käyttäjiä liittymästä aiemmin luotuun Office 365 -vuokraajaan?

Näillä toimenpiteillä voit järjestelmänvalvojana estää käyttäjiä liittymästä aiemmin luotuun Office 365 -vuokraajaasi. Jos voit estää käytön, käyttäjien yrittää rekisteröidä epäonnistua, ja näyttöön tulee sanoma, joka ohjaa heidät yhteyttä organisaation järjestelmänvalvojaan. Sinun ei tarvitse toistaa tämän prosessin, jos jo poistanut automaattisen käyttöoikeuksien jakelun (esimerkiksi Office 365: n kautta for Education opiskelijoille, Opetushenkilöstölle ja tuelle).

Estä uusia käyttäjiä liittymästä hallittuun vuokraajaan seuraavan PowerShell-komentosarjan avulla. ([Lue lisätietoja PowerShellistä][1].)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
```

> [!NOTE]
> Käytön estäminen estää organisaation uusia käyttäjiä rekisteröitymästä Power BI:hin. Käyttäjät, jotka rekisteröityvät Power BI:hin ennen uusien rekisteröitymisten estämistä, säilyttävät käyttöoikeutensa. Jos haluat poistaa käyttäjän, katso kohta [Miten voin poistaa Power BI:n käyttäjiltä, jotka ovat jo rekisteröityneet?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) jäljempänä tässä artikkelissa.

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Miten voin sallia käyttäjien liittyä aiemmin luotuun Office 365 -vuokraajaan?

PowerShell-komentosarjan avulla voit antaa uusien käyttäjien liittyminen hallittuun vuokraajaan. ([Lue lisätietoja PowerShellistä][1].)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $true
```

### <a name="how-do-i-check-if-i-have-the-block-on-in-the-tenant"></a>Miten voin tarkistaa, onko lohkon vuokraajaan?

Tarkista asetukset PowerShell-komentosarjan avulla. *AllowEmailVerifiedUsers*-asetuksen tulee olla false (epätosi). ([Lue lisätietoja PowerShellistä][1].)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Get-MsolCompanyInformation | fl allow*
```

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Miten voin estää olemassa olevilta käyttäjiltä Power BI:n käytön aloittamisen?

Tätä ohjaava Azure AD -asetus on **AllowAdHocSubscriptions**. Useimmissa vuokraajissa on tämä asetus true, mikä tarkoittaa, että se on käytössä. Jos hankit Power BI-kumppanin kautta, tämä voi arvoksi epätosi, mikä tarkoittaa, että se on poistettu käytöstä.

Seuraavan PowerShell-komentosarjan avulla voit poistaa ad-hoc-tilaukset käytöstä. ([Lue lisätietoja PowerShellistä][1].)

1. Kirjaudu Azure Active Directoryyn käyttämällä Office 365 -tunnistetietojasi. PowerShell-komentosarjan ensimmäinen rivi kehottaa antamaan tunnistetiedot. Toinen rivi muodostaa yhteyden Azure Active Directoryyn.

    ```powershell
     $msolcred = get-credential
     connect-msolservice -credential $msolcred
    ```

   ![Kansion näyttökuva-Azure Active Directory-Kirjaudu sisään PowerShellin kautta](media/service-admin-licensing-organization/azure-ad-sign-in.png)

1. Kun kirjaudut sisään, suorita seuraava komento nähdäksesi, miten vuokraajan on tällä hetkellä määritetty.

    ```powershell
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
    ```

1. Suorita seuraava komento käyttöön (`$true`) tai poistaa käytöstä (`$false`) **AllowAdHocSubscriptions**.

    ```powershell
     Set-MsolCompanySettings -AllowAdHocSubscriptions $false
    ```

> [!NOTE]
> Käytä **AllowAdHocSubscriptions** merkintä, joka käyttäjäominaisuuksien ohjaamiseen organisaatiossa, mukaan lukien käyttäjät voivat rekisteröityä Azure Rights Management-palveluun. Tämän lipun muuttaminen vaikuttaa kaikkiin näihin ominaisuuksiin.

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Miten voin sallia olemassa oleville käyttäjille Power BI:hin rekisteröitymisen?

Jotta olemassa käyttäjille Power BI-, previous-kysymyksessä mainittu komento suorittaa rekisteröityä mutta välittää `$true` sijaan `$false` viimeisessä vaiheessa.

## <a name="administration-of-power-bi"></a>Power BI:n hallinta

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Miten tämä muuttaa tapaa, jolla hallinnoin tällä hetkellä organisaationi käyttäjien käyttäjätietoja?

Organisaation käyttäjiin saattaa liittyä kolme tilannetta:

* **Skenaario 1**: Jos organisaatiossasi on jo käytössä Office 365-ympäristö ja kaikilla käyttäjillä organisaatiossasi on Office 365-tilit, käyttäjätietojen hallinnointitapa ei muutu ei luotu.

* **Skenaario 2**: Jos organisaatiossasi on jo käytössä Office 365-ympäristö, mutta ei kaikilla käyttäjillä organisaatiossasi on Office 365-tilit, voimme luoda käyttäjän vuokraajaan ja määritämme käyttöoikeudet käyttäjän työ- tai oppilaitossähköpostiosoitteen perusteella.

    Näin ollen yrityksessäsi hallinnoit tietyllä hetkellä käyttäjien määrä kasvaa, kun organisaatiosi käyttäjät rekisteröityvät palveluun.

* **Skenaario 3**: Jos organisaatiollasi ei ole sähköpostin toimialueeseen liitettyä Office 365-ympäristöä, käyttäjätietojen hallinnointitapa ei muutu ei luotu.

    Palvelun Lisää käyttäjät uuden, vain pilvessä olevaan hakemistoon. Lisäksi voit ryhtyä vuokraajan järjestelmänvalvojaksi ja hallita niitä.

### <a name="how-do-we-manage-power-bi"></a>Miten Power BI:tä hallitaan?

Power BI tarjoaa, jonka avulla voit tarkastella käyttötilastoja, hallintaportaali sisältää linkin Microsoft 365-hallintakeskuksessa, jotta voit hallita käyttäjiä ja ryhmiä ja mahdollistaa koko vuokraajan-asetusten hallinta.

Jos haluat käyttää Power BI-hallintaportaalissa, merkitse tiliisi **yleisen järjestelmänvalvojan** Office 365: ssä tai Azure Active Directory tai joku on määritettävä Power BI-palvelun järjestelmänvalvojan rooli käyttäjätiliäsi. Katso lisätietoja, [Power BI-järjestelmänvalvojaroolin](service-admin-role.md) ja [Power BI-hallintaportaalissa](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Millä tavalla voin hallinnoida vuokraajaa, jonka Microsoft on luonut käyttäjiäni varten?

Kun omatoiminen käyttäjä rekisteröityy pilvipalveluun, joka käyttää Azure AD-palvelun lisää ne hallitsematon Azure AD-hakemisto perusteella niiden sähköpostitoimialueella. Voit hakea ja hallita vuokraajaa, johon joku luotu eli *järjestelmänvalvojan hallintaasi*. Voit tehdä hallintaasi tyyppi määräytyy onko olemassa hallitun vuokraajan toimialueen liittyvät:

* *Sisäisen haltuunoton* avulla voit luoda toimialueelle uuden hallitun vuokraajan.

* *Ulkoisen haltuunoton* avulla voit siirtää toimialueen aiemmin luotuun hallittuun vuokraajaan.

Katso lisätietoja, [ottaa Azure Active Directory-järjestelmänvalvojan hallitsemattoman directory](/azure/active-directory/users-groups-roles/domains-admin-takeover).

Ulkoinen haltuunotto tehdään, kun palvelu asettaa Power BI-sisällön, joka on luotu ennen hallintaasi [Power BI arkistoitu työtila](service-admin-power-bi-archived-workspace.md). Jos haluat käyttää sisältöä uudessa vuokraajassa, se täytyy siirtää käsin.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to"></a>Jos minulla on useita toimialueita, voinko hallinnoida Office 365-vuokraajaa, johon käyttäjät lisätään?

Jos et tee mitään, palvelu luo vuokraajan jokaista käyttäjän sähköpostin toimialuetta ja alitoimialuetta varten. Jos haluat, että kaikki käyttäjät sijaitsevat samassa vuokraajassa riippumatta käyttäjien sähköpostiosoitteen tunnisteista: Luo kohdevuokraaja etukäteen tai Käytä olemassa olevaa vuokraajaa. Lisää kaikki olemassa olevat toimialueet ja alitoimialueet, jotka haluat keskittää. Jokainen käyttäjä, joiden sähköpostiosoite päättyy näihin toimialueisiin tai alitoimialueisiin, liittyvät automaattisesti kohdevuokraajaan, kun he rekisteröityvät.

> [!IMPORTANT]
> Kun olet luonut käyttäjille, ei ole tuettu automaattista mekanismia käyttäjien siirtämiseksi vuokraajien välillä. Jos haluat tietää, miten yksittäiseen Office 365 -vuokraajaan lisätään toimialueita, lue ohjeet kohdasta [Käyttäjien ja toimialueen lisääminen Office 365:een](/office365/admin/setup/add-domain/).

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Miten voin poistaa Power BI:n käyttäjiltä, jotka ovat jo rekisteröityneet?

Jos käyttäjä on rekisteröitynyt Power BI:hin, mutta et enää halua hänen käyttävän Power BI:tä, voit poistaa Power BI -käyttöoikeuden kyseiseltä käyttäjältä.

1. Siirry [Microsoft 365 -hallintakeskukseen](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. Valitse vasemmassa siirtymispalkissa **Käyttäjät** > **Aktiiviset käyttäjä**.

1. Etsi käyttäjä, jolta haluat poistaa käyttöoikeuden, ja valitse hänen nimensä.

    Voit hallita käyttäjien lisenssejä myös joukkomuodossa. Valitse tätä varten useita käyttäjiä ja valitse sitten **Muokkaa tuotteiden käyttöoikeuksia**.

1. Valitse käyttäjätietosivun **Tuotteen käyttöoikeudet** -kohdassa **Muokkaa**.

1. Sen mukaan, mitä voit käyttöoikeuden käytössä hänen tilillään, Määritä **Power BI (ilmainen)** tai **Power BI Pro** - **käytöstä**.

1. Valitse **Tallenna**.

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Mistä tiedän, milloin uudet käyttäjät ovat liittyneet vuokraajaani?

Käyttäjät, jotka ovat liittyneet vuokraajaan osana tätä ohjelmaa saa määrittää yksilöivä lisenssi, jota voit käyttää suodattimessa järjestelmänvalvojan koontinäytön aktiivisen käyttäjän ruudussa. Luo tämä uusi näkymä seuraavien ohjeiden mukaan.

1. Siirry [Microsoft 365 -hallintakeskukseen](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. Valitse vasemmassa siirtymispalkissa **Käyttäjät** > **Aktiiviset käyttäjä**.

1. Valitse **Näkymät**-valikosta **Lisää mukautettu näkymä**.

1. Anna uudelle näkymälle nimi ja valitse sitten **Määritetty tuotekäyttöoikeus** -kohdasta joko **Power BI (maksuton)** tai **Power BI Pro**.

    Näkymässä voi olla valittuna vain yksi käyttöoikeus. Jos organisaatiossa on sekä **Power BI (maksuton)** - että **Power BI Pro** -käyttöoikeuksia, voit luoda kaksi näkymää.

1. Kirjoita haluamasi muut ehdot ja valitse **Lisää**.

1. Kun olet luonut uuden näkymän, on käytettävissä **näkymät** valikosta.

### <a name="are-there-any-additional-things-i-should-prepare-for"></a>Onko muita asioita, joihin minun kannattaa valmistautua?

Salasanan vaihtamispyyntöjä saattaa tulla enemmän. Katso tietoja tämän prosessin [käyttäjän salasanan vaihtaminen](/office365/admin/add-users/reset-passwords).

Voit poistaa käyttäjän vuokraajasta tavalliseen tapaan Microsoft 365 -hallintakeskuksen kautta. Jos käyttäjällä on edelleen aktiivinen sähköpostiosoite organisaatiossasi, hän voi liittyä takaisin, ellet estä kaikkia käyttäjiä liittymästä.

### <a name="where-is-my-power-bi-tenant-located"></a>Missä Power BI -vuokraajani sijaitsee?

Katso tietoja siitä, mitä tietoalueen Power BI-vuokraajasi sijaitsee, [missä Power BI-vuokraajani sijaitsee?](service-admin-where-is-my-tenant-located.md).

### <a name="what-is-the-power-bi-sla"></a>Mikä on Power BI:n palvelutasosopimus?

Katso tietoja Power BI-PALVELUTASOSOPIMUKSEN (palvelutasosopimus) [käyttöoikeusehdot ja ohjeet](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) artikkelia **käyttöoikeuksien** Microsoft Licensing-sivuston osasta.

### <a name="how-does-power-bi-handle-high-availability-and-failover"></a>Miten Power BI takaa suuren käytettävyyden ja vikasietoisuuden?

Katso tietoja suuren käytettävyyden ja failover [Power BI suuren käytettävyyden ja failover järjestelmäpalautuksen palautuksen usein kysytyt kysymykset](service-admin-failover.md).

## <a name="security-in-power-bi"></a>Suojaus Power BI:ssä

### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Onko Power BI kansallisten, alueellisten ja alakohtaisten vaatimusten mukainen?

Lisätietoja Power BI:n vaatimustenmukaisuudesta on [Microsoft Trust Centerissä](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/default.aspx).

### <a name="how-does-security-work-in-power-bi"></a>Miten suojaus toimii Power BI:ssä?

Microsoft rakennettu Power BI Office 365: een, joka puolestaan perustuu Azure-palveluja, kuten Azure Active Directory foundation. Yleiskatsaus Power BI -arkkitehtuurista on kohdassa [Power BI:n suojaus](service-admin-power-bi-security.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI -hallintaportaali](service-admin-portal.md)  
[Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md)  
[Omatoiminen kirjautuminen Power BI:hin](service-self-service-signup-for-power-bi.md)  
[Power BI Pron ostaminen](service-admin-purchasing-power-bi-pro.md)  
[Mikä on Power BI Premium?](service-premium-what-is.md)  
[Miten voit ostaa Power BI Premium](service-admin-premium-purchase.md)  
[Power BI Premiumin tekninen raportti](https://aka.ms/pbipremiumwhitepaper)  
[Ryhmän hallinta Power BI:ssä ja Office 365:ssä](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Office 365:n käyttäjätilien hallinta](/office365/servicedescriptions/office-365-platform-service-description/user-account-management/)  
[Office 365:n ryhmän hallinta](/office365/admin/email/create-edit-or-delete-a-security-group/)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

[1]: https://docs.microsoft.com/powershell/scripting/overview