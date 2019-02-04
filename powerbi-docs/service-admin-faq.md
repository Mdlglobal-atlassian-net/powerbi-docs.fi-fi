---
title: Power BI:n hallinnointi - usein kysytyt kysymykset (UKK)
description: Lue vastauksia usein kysyttyihin kysymyksiin liittyen Power BI:n rekisteröintiin, vuokraajien hallinnointiin ja muihin hallintatehtäviin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 9002b1871f5e7db4ef67d4f2f77b6b8769aa1de6
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/31/2019
ms.locfileid: "55430276"
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
* [Miten voin vahvistaa, onko minulla lohko vuokraajassa?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [Miten voin estää olemassa olevilta käyttäjiltä Power BI:n käytön aloittamisen?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Miten voin sallia olemassa oleville käyttäjille Power BI:hin rekisteröitymisen?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

### <a name="administration-of-power-bi-section"></a>Power BI:n hallinta -osio

* [Miten tämä muuttaa tapaa, jolla hallinnoin tällä hetkellä organisaationi käyttäjien käyttäjätietoja?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Miten Power BI:tä hallitaan?](#how-do-we-manage-power-bi)
* [Millä tavalla voin hallinnoida vuokraajaa, jonka Microsoft on luonut käyttäjiäni varten?](#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users)
* [Jos minulla on useita toimialueita, voinko hallinnoida Office 365 -vuokraajaa, johon käyttäjät on lisätty?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [Miten voin poistaa Power BI:n käyttäjiltä, jotka ovat jo rekisteröityneet?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Mistä tiedän, milloin uudet käyttäjät ovat liittyneet vuokraajaani?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Onko muita asioita, joihin minun kannattaa valmistautua?](#are-there-any-additional-things-i-should-be-prepared-for)
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

Järjestelmänvalvojana voit rekisteröityä Power BI:hin [Power BI -sivuston](https://powerbi.microsoft.com) tai Office 365 -hallintakeskuksen[Ostopalvelut](https://admin.microsoft.com/AdminPortal/Home#/catalog)-sivun kautta. Kun järjestelmänvalvoja rekisteröityy Power BI:hin, hän voi määrittää käyttöoikeudet käyttäjille, jotka tarvitsevat käyttöoikeuden.

Lisäksi organisaation yksittäiset käyttäjät voivat ehkä rekisteröityä Power BI:hin [Power BI -sivuston](https://powerbi.microsoft.com) kautta. Kun organisaatiosi käyttäjä rekisteröityy Power BI:hin, hän saa automaattisesti Power BI -lisenssin. Lisätietoja on artikkeleissa [Rekisteröityminen Power BI:hin yksityishenkilönä](service-self-service-signup-for-power-bi.md) ja [Power BI -käyttöoikeudet organisaatiossasi](service-admin-licensing-organization.md).

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Miten organisaationi yksittäiset käyttäjät rekisteröityvät?

Organisaation käyttäjiin saattaa liittyä kolme tilannetta:

* **Skenaario 1**: Organisaatiolla on jo Office 365 -ympäristö ja Power BI:hin rekisteröityvällä käyttäjällä on jo Office 365 -tili.
    Tässä skenaariossa jos käyttäjällä on jo työpaikan tai oppilaitoksen tili vuokraajassa (esimerkiksi contoso.com) mutta ei vielä Power BI:tä, Microsoft aktivoi kyseisen tilin sopimuksen, ja käyttäjälle ilmoitetaan automaattisesti, miten Power BI -palvelua voi käyttää.

* **Skenaario 2**: Organisaatiolla on jo Office 365 -ympäristö, mutta Power BI:hin rekisteröityvällä käyttäjällä ei ole Office 365 -tiliä.
    Tässä skenaariossa käyttäjällä on sähköpostiosoite organisaatiosi toimialueella (esimerkiksi contoso.com) mutta ei vielä Office 365 -tiliä. Käyttäjä voi tässä tapauksessa rekisteröityä Power BI:hin, ja hän saa automaattisesti tilin. Näin käyttäjä pääsee käyttämään Power BI -palvelua. Esimerkiksi jos työntekijä nimeltä Noora käyttää rekisteröitymisessä työsähköpostiosoitettaan (esimerkiksi nancy@contoso.com), Microsoft lisää Nooran automaattisesti Contoson Office 365 -ympäristön käyttäjäksi ja aktivoi Power BI:n kyseiselle tilille.

* **Skenaario 3**: Organisaatiolla ei ole sähköpostisi toimialueeseen liitettyä Office 365 -ympäristöä.
    Organisaatiolla ei ole suoritettavia järjestelmänvalvojan toimintoja, jotta Power BI:tä voidaan hyödyntää. Käyttäjät lisätään uuteen vain pilvi -käyttäjähakemistoon, ja sinulla on mahdollisuus ottaa vuokraajan järjestelmänvalvojan rooli ja hallinnoida tietoja.

> [!IMPORTANT]
> Jos organisaatiossa on useita sähköpostitoimialueita ja haluat kaikkien sähköpostiosoitteiden tunnisteiden olevan samassa vuokraajassa, lisää kaikki sähköpostiosoitteiden toimialueet Azure Active Directory -vuokraajaan ennen kuin käyttäjät rekisteröityvät. Ei ole olemassa automaattista mekanismia käyttäjien siirtämiseksi vuokraajien välillä käyttäjien luomisen jälkeen. Lisätietoja tästä prosessista on jäljempänä tämän artikkelin kohdassa [Jos minulla on useita toimialueita, voinko hallinnoida Office 365 -vuokraajaa, johon käyttäjät on lisätty?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) ja artikkelissa [Toimialueen lisääminen Office 365:een](/office365/admin/setup/add-domain/).

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Miten voin estää käyttäjiä liittymästä aiemmin luotuun Office 365 -vuokraajaan?

Näillä toimenpiteillä voit järjestelmänvalvojana estää käyttäjiä liittymästä aiemmin luotuun Office 365 -vuokraajaasi. Jos estät käytön, käyttäjien rekisteröitymisyritykset epäonnistuvat ja heitä pyydetään ottamaan yhteyttä organisaation järjestelmänvalvojaan. Tätä prosessia ei tarvitse toistaa, jos olet jo poistanut automaattisen käyttöoikeuksien jakelun käytöstä (esim. Office 365 for Education opiskelijoille, opetushenkilöstölle ja muulle henkilöstölle).

Estä uusia käyttäjiä liittymästä hallittuun vuokraajaan seuraavan PowerShell-komentosarjan avulla. [Lisätietoja PowerShellistä](#basic-powershell-information)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
```

> [!NOTE]
> Käytön estäminen estää organisaation uusia käyttäjiä rekisteröitymästä Power BI:hin. Käyttäjät, jotka rekisteröityvät Power BI:hin ennen uusien rekisteröitymisten estämistä, säilyttävät käyttöoikeutensa. Jos haluat poistaa käyttäjän, katso kohta [Miten voin poistaa Power BI:n käyttäjiltä, jotka ovat jo rekisteröityneet?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) jäljempänä tässä artikkelissa.

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Miten voin sallia käyttäjien liittyä aiemmin luotuun Office 365 -vuokraajaan?

Salli uusien käyttäjien liittyminen hallittuun vuokraajaan seuraavan PowerShell-komentosarjan avulla. [Lisätietoja PowerShellistä](#basic-powershell-information)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $true
```

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Miten voin vahvistaa, onko minulla lohko vuokraajassa?

Tarkista asetukset seuraavan PowerShell-komentosarjan avulla. *AllowEmailVerifiedUsers*-asetuksen tulee olla false (epätosi). [Lisätietoja PowerShellistä](#basic-powershell-information)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Get-MsolCompanyInformation | fl allow*
```

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Miten voin estää olemassa olevilta käyttäjiltä Power BI:n käytön aloittamisen?

Tätä ohjaava Azure AD -asetus on **AllowAdHocSubscriptions**. Useimmissa vuokraajissa tämä asetus on true (tosi), mikä tarkoittaa, että se on käytössä. Jos hankit Power BI:n kumppanin kautta, asetuksena saattaa olla false (epätosi), mikä tarkoittaa, että se on poistettu käytöstä.

Seuraavan PowerShell-komentosarjan avulla voit poistaa ad-hoc-tilaukset käytöstä. [Lisätietoja PowerShellistä](#basic-powershell-information)

1. Kirjaudu Azure Active Directoryyn käyttämällä Office 365 -tunnistetietojasi. PowerShell-komentosarjan ensimmäinen rivi kehottaa antamaan tunnistetiedot. Toinen rivi muodostaa yhteyden Azure Active Directoryyn.

    ```powershell
     $msolcred = get-credential
     connect-msolservice -credential $msolcred
    ```

   ![Sisäänkirjautuminen Azure Active Directoryyn](media/service-admin-licensing-organization/aad-signin.png)

1. Kun olet kirjautunut sisään, suorita seuraava komento, jotta näet, mikä asetus vuokraajalla on tällä hetkellä määritettynä.

    ```powershell
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
    ```
1. Suorittamalla seuraavan komennon voit ottaa käyttöön ($true) tai poistaa käytöstä ($false) **AllowAdHocSubscriptions**-asetuksen.

    ```powershell
     Set-MsolCompanySettings -AllowAdHocSubscriptions $false
    ```

> [!NOTE]
> AllowAdHocSubscriptions-lippua käytetään useiden käyttäjäominaisuuksien ohjaamiseen organisaatiossa. Sillä ohjataan muun muassa käyttäjien mahdollisuutta rekisteröityä Azure Rights Management -palveluun. Tämän lipun muuttaminen vaikuttaa kaikkiin näihin ominaisuuksiin.

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Miten voin sallia olemassa oleville käyttäjille Power BI:hin rekisteröitymisen?

Jos haluat sallia Power BI:hin rekisteröitymisen olemassa oleville käyttäjille, suorita yllä olevassa kysymyksessä mainittu komento, mutta käytä komennon arvona true (tosi) false-arvon (epätosi) sijasta viimeisessä vaiheessa.

## <a name="administration-of-power-bi"></a>Power BI:n hallinta

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Miten tämä muuttaa tapaa, jolla hallinnoin tällä hetkellä organisaationi käyttäjien käyttäjätietoja?

Organisaation käyttäjiin saattaa liittyä kolme tilannetta:

* **Skenaario 1**: Jos organisaatiossasi on jo käytössä Office 365 -ympäristö ja kaikilla käyttäjillä organisaatiossasi on Office 365 -tilit, käyttäjätietojen hallinnointi ei muutu.

* **Skenaario 2**: Jos organisaatiossasi on jo käytössä Office 365 -ympäristö, mutta kaikilla käyttäjillä organisaatiossasi ei ole Office 365 -tiliä, vuokraajaan luodaan käyttäjätili ja käyttöoikeuksia myönnetään käyttäjän työpaikan tai oppilaitoksen sähköpostiosoitteen perusteella.

    Tämä tarkoittaa, että niiden käyttäjien, joiden tietoja hallinnoit tietyllä hetkellä, lukumäärä kasvaa, kun organisaatiosi käyttäjät rekisteröityvät palveluun.

* **Skenaario 3**: Jos organisaatiollasi ei ole sähköpostisi toimialueeseen liitettyä Office 365 -ympäristöä, käyttäjätietojen hallinnointitapa ei muutu.

    Käyttäjät lisätään uuteen vain pilvi -käyttäjähakemistoon, ja sinulla on mahdollisuus ottaa vuokraajan järjestelmänvalvojan rooli ja hallinnoida tietoja.

### <a name="how-do-we-manage-power-bi"></a>Miten Power BI:tä hallitaan?

Power BI sisältää hallintaportaalin, jossa on käyttötilastoja, linkki Office 365:n hallintakeskukseen käyttäjien ja ryhmien hallintaa varten ja mahdollisuus hallita koko vuokraajaa koskevia asetuksia.

Jotta voit käyttää Power BI -hallintaportaalia, tililläsi täytyy olla **yleisen järjestelmänvalvojan** oikeudet Office 365:ssä tai Azure Active Directoryssa tai Power BI -palvelun järjestelmänvalvojan oikeudet. Lisätietoja on artikkeleissa [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md) ja [Power BI -hallintaportaali](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Millä tavalla voin hallinnoida vuokraajaa, jonka Microsoft on luonut käyttäjiäni varten?

Kun omatoiminen käyttäjä rekisteröityy Azure AD:tä käyttävään pilvipalveluun, hänet lisätään hallitsemattomaan Azure AD -hakemistoon sähköpostin toimialueen perusteella. Voit vaatia luodun vuokraajan käyttöösi ja hallita sitä suorittamalla *järjestelmänvalvojan haltuunottoprosessin*. Suoritettavan haltuunoton tyyppi määräytyy sen mukaan, liittyykö toimialueeseen aiemmin luotu hallittu vuokraaja:

* *Sisäisen haltuunoton* avulla voit luoda toimialueelle uuden hallitun vuokraajan.

* *Ulkoisen haltuunoton* avulla voit siirtää toimialueen aiemmin luotuun hallittuun vuokraajaan.

Jos haluat lisätietoja, katso [Ota haltuun hallitsematon hakemisto järjestelmänvalvojana Azure Active Directoryssa](/azure/active-directory/users-groups-roles/domains-admin-takeover).

Kun suoritat ulkoisen haltuunoton, ennen haltuunottoa luotu Power BI -sisältö sijoitetaan [Power BI:n arkistoituun työtilaan](service-admin-power-bi-archived-workspace.md). Jos haluat käyttää sisältöä uudessa vuokraajassa, se täytyy siirtää käsin.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Jos minulla on useita toimialueita, voinko hallinnoida Office 365 -vuokraajaa, johon käyttäjät on lisätty?

Jos et tee mitään, jokaista käyttäjän sähköpostin toimialuetta ja alitoimialuetta varten luodaan vuokraaja. Jos haluat, että kaikki käyttäjät sijaitsevat samassa vuokraajassa riippumatta käyttäjien sähköpostiosoitteen tunnisteista: Luo alivuokraaja etukäteen tai käytä olemassa olevaa vuokraajaa ja lisää sitten kaikki olemassa olevat toimialueet ja alitoimialueet, jotka haluat yhdistää kyseiseen vuokraajaan. Tällöin kaikki käyttäjät, joiden sähköpostiosoitteen pääte viittaa kyseisiin toimialueisiin ja alitoimialueisiin, liittyvät automaattisesti kohdevuokraajaan rekisteröitymisen yhteydessä.

> [!IMPORTANT]
> Ei ole olemassa tuettua automaattista mekanismia käyttäjien siirtämiseksi vuokraajien välillä, kun ne on luotu. Jos haluat tietää, miten yksittäiseen Office 365 -vuokraajaan lisätään toimialueita, lue ohjeet kohdasta [Käyttäjien ja toimialueen lisääminen Office 365:een](/office365/admin/setup/add-domain/).

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Miten voin poistaa Power BI:n käyttäjiltä, jotka ovat jo rekisteröityneet?

Jos käyttäjä on rekisteröitynyt Power BI:hin, mutta et enää halua hänen käyttävän Power BI:tä, voit poistaa Power BI -käyttöoikeuden kyseiseltä käyttäjältä.

1. Siirry [Office 365:n hallintakeskukseen](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. Valitse vasemmassa siirtymispalkissa **Käyttäjät** > **Aktiiviset käyttäjä**.

1. Etsi käyttäjä, jolta haluat poistaa käyttöoikeuden, ja valitse hänen nimensä.

    Voit hallita käyttäjien lisenssejä myös joukkomuodossa. Valitse tätä varten useita käyttäjiä ja valitse sitten **Muokkaa tuotteiden käyttöoikeuksia**.

1. Valitse käyttäjätietosivun **Tuotteen käyttöoikeudet** -kohdassa **Muokkaa**.

1. Aseta **Power BI (maksuton)** tai **Power BI Pro** **Ei käytössä** -tilaan sen mukaan, mikä käyttäjän tilin käyttöoikeus on.

1. Valitse **Tallenna**.

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Mistä tiedän, milloin uudet käyttäjät ovat liittyneet vuokraajaani?

Käyttäjille, jotka ovat liittyneet vuokraajaan osana tätä ohjelmaa, määritetään yksilöivä lisenssi, jota voit käyttää suodattimessa järjestelmänvalvojan koontinäytön aktiivisen käyttäjän ruudussa. Luo tämä uusi näkymä seuraavien ohjeiden mukaan.

1. Siirry [Office 365:n hallintakeskukseen](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. Valitse vasemmassa siirtymispalkissa **Käyttäjät** > **Aktiiviset käyttäjä**.

1. Valitse **Näkymät**-valikosta **Lisää mukautettu näkymä**.

1. Anna uudelle näkymälle nimi ja valitse sitten **Määritetty tuotekäyttöoikeus** -kohdasta joko **Power BI (maksuton)** tai **Power BI Pro**.

    Näkymässä voi olla valittuna vain yksi käyttöoikeus. Jos organisaatiossa on sekä **Power BI (maksuton)**- että **Power BI Pro** -käyttöoikeuksia, voit luoda kaksi näkymää.

1. Kirjoita haluamasi muut ehdot ja valitse **Lisää**.

1. Kun uusi näkymä on luotu, se on käytettävissä **Näkymät**-valikosta.

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Onko muita asioita, joihin minun kannattaa valmistautua?

Salasanan vaihtamispyyntöjä saattaa tulla enemmän. Lisätietoja tästä prosessista on artikkelissa [Käyttäjän salasanan vaihtaminen](/office365/admin/add-users/reset-passwords).

Voit poistaa käyttäjän vuokraajasta tavalliseen tapaan Office 365:n hallintakeskuksen kautta. Jos käyttäjällä on edelleen aktiivinen sähköpostiosoite organisaatiossasi, hän voi liittyä takaisin, ellet estä kaikkia käyttäjiä liittymästä.

### <a name="where-is-my-power-bi-tenant-located"></a>Missä Power BI -vuokraajani sijaitsee?

Lisätietoja siitä, millä tietoalueella Power BI -vuokraajasi sijaitsee, on kohdassa [Missä Power BI -vuokraajani sijaitsee?](service-admin-where-is-my-tenant-located.md).

### <a name="what-is-the-power-bi-sla"></a>Mikä on Power BI:n palvelutasosopimus?

Lisätietoja Power BI:n palvelutasosopimuksesta on Microsoft Licensing -sivuston [Käyttöoikeusehdot ja -ohjeet](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) -artikkelin **käyttöoikeuksia** käsittelevässä kohdassa.

### <a name="how-does-power-bi-handle-high-availability-and-failover"></a>Miten Power BI takaa suuren käytettävyyden ja vikasietoisuuden?

Jos haluat lisätietoja suuresta käytettävyydestä ja vikasietoisuudesta, lue ohjeartikkeli [Power BI:n suuren käytettävyyden, vikasietoisuuden ja järjestelmäpalautuksen usein kysytyt kysymykset](service-admin-failover.md).

## <a name="security-in-power-bi"></a>Suojaus Power BI:ssä

### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Onko Power BI kansallisten, alueellisten ja alakohtaisten vaatimusten mukainen?

Lisätietoja Power BI:n vaatimustenmukaisuudesta on [Microsoft Trust Centerissä](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/default.aspx).

### <a name="how-does-security-work-in-power-bi"></a>Miten suojaus toimii Power BI:ssä?

Power BI perustuu Office 365:een, joka puolestaan perustuu Azure-palveluihin, kuten Azure Active Directoryyn. Yleiskatsaus Power BI -arkkitehtuurista on kohdassa [Power BI:n suojaus](service-admin-power-bi-security.md).

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI -hallintaportaali](service-admin-portal.md)  
[Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md)  
[Omatoiminen kirjautuminen Power BI:hin](service-self-service-signup-for-power-bi.md)  
[Power BI Pron ostaminen](service-admin-purchasing-power-bi-pro.md)  
[Mikä on Power BI Premium?](service-premium.md)  
[Ohjeet Power BI Premiumin ostamiseen](service-admin-premium-purchase.md)  
[Power BI Premiumin tekninen raportti](https://aka.ms/pbipremiumwhitepaper)  
[Ryhmän hallinta Power BI:ssä ja Office 365:ssä](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Office 365:n käyttäjätilien hallinta](/office365/servicedescriptions/office-365-platform-service-description/user-account-management/)  
[Office 365:n ryhmän hallinta](/office365/admin/email/create-edit-or-delete-a-security-group/)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
