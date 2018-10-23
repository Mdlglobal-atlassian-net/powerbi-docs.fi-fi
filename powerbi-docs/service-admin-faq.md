---
title: Power BI:n hallinnointi - usein kysytyt kysymykset (UKK)
description: Lue vastauksia usein kysyttyihin kysymyksiin liittyen Power BI:n rekisteröintiin, vuokraajien hallinnointiin ja muihin hallintatehtäviin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: b77d20b8c9705e4b4cd811ea8dfa3008908a4438
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641685"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Power BI:n hallinnointi - usein kysytyt kysymykset (UKK)

Tämä artikkeli vastaa Power BI -hallinnoinnista usein kysyttyihin kysymyksiin. Yleiskatsaus Power BI -hallinnoinnista löytyy kohdasta [Mitä on Power BI:n hallinta](service-admin-administering-power-bi-in-your-organization.md).

## <a name="whats-in-this-article"></a>Tämän artikkelin sisältö
**Rekisteröidy Power BI -palveluun**

* [Miten käyttäjät voivat rekisteröityä Power BI:hin?](#how-do-users-sign-up-for-power-bi)
* [Miten organisaationi yksittäiset käyttäjät rekisteröityvät?](#how-do-individual-users-in-my-organization-sign-up)
* [Miten voin estää käyttäjiä liittymästä aiemmin luotuun Office 365 -vuokraajaan?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [Miten voin sallia käyttäjien liittyä aiemmin luotuun Office 365 -vuokraajaan?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [Miten voin vahvistaa, onko minulla lohko vuokraajassa?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [Miten voin estää olemassa olevilta käyttäjiltä Power BI:n käytön aloittamisen?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Miten voin sallia olemassa oleville käyttäjille Power BI:hin rekisteröitymisen?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Power BI:n hallinta**

* [Miten tämä muuttaa tapaa, jolla hallinnoin tällä hetkellä organisaationi käyttäjien käyttäjätietoja?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Miten Power BI:tä hallitaan?](#how-do-we-manage-power-bi)
* [Millä tavalla voin hallinnoida vuokraajaa, jonka Microsoft on luonut käyttäjiäni varten?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [Jos minulla on useita toimialueita, voinko hallinnoida Office 365 -vuokraajaa, johon käyttäjät on lisätty?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [Miten voin poistaa Power BI:n käyttäjiltä, jotka ovat jo rekisteröityneet?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Mistä tiedän, milloin uudet käyttäjät ovat liittyneet vuokraajaani?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Onko muita asioita, joihin minun kannattaa valmistautua?](#are-there-any-additional-things-i-should-be-prepared-for)
* [Missä Power BI -vuokraajani sijaitsee?](#where-is-my-power-bi-tenant-located)
* [Mikä on Power BI:n palvelutasosopimus?](#what-is-the-power-bi-sla)

**Suojaus Power BI:ssä**

* [Onko Power BI kansallisten, alueellisten ja alakohtaisten vaatimusten mukainen?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Miten suojaus toimii Power BI:ssä?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Rekisteröidy Power BI:hin
### <a name="how-do-users-sign-up-for-power-bi"></a>Miten käyttäjät voivat rekisteröityä Power BI:hin?
Voit rekisteröityä Power BI:hin [Power BI -sivuston](https://powerbi.microsoft.com) kautta. Voit myös rekisteröityä Office 365:n hallintakeskuksen Osta palveluita -sivun kautta. Kun järjestelmänvalvoja rekisteröityy Power BI:hin, hän voi määrittää käyttöoikeudet käyttäjille, jotka tarvitsevat käyttöoikeuden.

Lisäksi organisaation yksittäiset käyttäjät voivat ehkä rekisteröityä Power BI:hin [Power BI -sivuston](https://powerbi.microsoft.com) kautta. Kun organisaatiosi käyttäjä rekisteröityy Power BI:hin, hän saa automaattisesti Power BI -lisenssin. [Lue lisää](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Miten organisaationi yksittäiset käyttäjät rekisteröityvät?
Organisaation käyttäjiin saattaa liittyä kolme tilannetta:

Skenaario 1: Organisaatiolla on jo olemassa oleva Office 365 -ympäristö ja Power BI:hin rekisteröityvällä käyttäjällä on jo Office 365 -tili.
Tässä skenaariossa, jos käyttäjällä on jo työpaikan tai oppilaitoksen tili vuokraajassa (esimerkiksi contoso.com) mutta ei vielä Power BI:tä, Microsoft yksinkertaisesti aktivoi kyseisen sopimuksen tilille ja käyttäjälle ilmoitetaan automaattisesti, miten Power BI -palvelua voi käyttää.

Skenaario 2: Organisaatiolla on jo olemassa oleva Office 365 -ympäristö ja Power BI:hin rekisteröityvällä käyttäjällä ei ole Office 365 -tiliä.
Tässä skenaariossa käyttäjällä on sähköpostiosoite organisaatiosi toimialueella (esimerkiksi contoso.com) mutta ei vielä Office 365 -tiliä. Käyttäjä voi tässä tapauksessa rekisteröityä Power BI:hin ja hän saa automaattisesti tilin. Näin käyttäjä pääsee käyttämään Power BI -palvelua. Esimerkiksi jos työntekijä nimeltä Nancy käyttää rekisteröitymisessä työsähköpostiosoitettaan (esimerkiksi Nancy@contoso.com), Microsoft lisää automaattisesti Nancyn Contoson Office 365 -ympäristön käyttäjäksi ja aktivoi Power BI:n kyseiselle tilille.

Skenaario 3: Organisaatiollasi ei ole sähköpostisi toimialueeseen liitettyä Office 365 -ympäristöä.
Organisaatiolla ei ole suoritettavia järjestelmänvalvojan toimintoja, jotta Power BI:tä voidaan hyödyntää. Käyttäjät lisätään uuteen vain pilvi -käyttäjähakemistoon, ja sinulla on mahdollisuus ottaa vuokraajan järjestelmänvalvojan rooli ja hallinnoida tietoja.

> [!IMPORTANT]
> Jos organisaatiossa on useita sähköpostitoimialueita ja haluat kaikkien sähköpostiosoitteiden tunnisteiden olevan samassa vuokraajassa, lisää kaikki sähköpostiosoitteiden toimialueet Azure Active Directory -vuokraajaan ennen kuin käyttäjät rekisteröityvät. Ei ole olemassa automaattista mekanismia käyttäjien siirtämiseksi vuokraajien välillä käyttäjien luomisen jälkeen. Lisätietoja tästä prosessista on jäljempänä tämän artikkelin kohdassa [Jos minulla on useita toimialueita, voinko hallinnoida Office 365 -vuokraajaa, johon käyttäjät on lisätty?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) ja verkossa artikkelissa [Toimialueen lisääminen Office 365:een](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Miten voin estää käyttäjiä liittymästä aiemmin luotuun Office 365 -vuokraajaan?
Näillä toimenpiteillä voit järjestelmänvalvojana estää käyttäjiä liittymästä aiemmin luotuun Office 365 -vuokraajaasi. Jos estät liittymisen, käyttäjien rekisteröitymisyritykset epäonnistuvat ja heitä pyydetään ottamaan yhteyttä organisaation järjestelmänvalvojaan. Tätä prosessia ei tarvitse toistaa, jos olet jo poistanut automaattisen käyttöoikeuksien jakelun käytöstä (esim. Office 365 for Education opiskelijoille, opetushenkilöstölle ja muulle henkilöstölle).

Nämä vaiheet edellyttävät Windows PowerShellin käyttöä. Lisätietoja Windows PowerShellin käytön aloittamisesta on [PowerShellin aloitusoppaassa](http://go.microsoft.com/fwlink/p/?LinkID=286814).

Seuraavien vaiheiden suorittaminen edellyttää, että asennat [Windows PowerShellin Azure Active Directory -moduulin](http://go.microsoft.com/fwlink/p/?LinkID=236297) uusimman 64-bittisen version.

Kun olet valinnut linkin, suorita asennuspaketti valitsemalla **Suorita**.

**Automaattisen vuokraajaan liittymisen poistaminen käytöstä**: Estä uusia käyttäjiä liittymästä hallittuun vuokraajaan tämän Windows PowerShell -komennon avulla:

* Automaattisen vuokraajaan liittymisen poistaminen käytöstä uusilta käyttäjiltä:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
* Automaattisen vuokraajaan liittymisen ottaminen käyttöön uusille käyttäjille:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [!NOTE]
> Tämä estää organisaation uusilta käyttäjiltä rekisteröitymisen Power BI:hin. Käyttäjät, jotka rekisteröityvät Power BI:hin ennen uusien rekisteröitymisten poistamista käytöstä organisaatiossasi, säilyttävät käyttöoikeuden. Katso kohdasta [Miten käyttöoikeudet poistetaan?] ohjeet, miten voit poistaa Power BI:n käytöstä käyttäjiltä, jotka ovat jo rekisteröityneet palveluun.
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Miten voin sallia käyttäjien liittyä aiemmin luotuun Office 365 -vuokraajaan?
Jos haluat sallia vuokraajaan liittymisen käyttäjille, suorita yllä esitetyssä kysymyksessä olevan komennon vastakomento.

Seuraavien vaiheiden suorittaminen edellyttää, että asennat [Windows PowerShellin Azure Active Directory -moduulin](http://go.microsoft.com/fwlink/p/?LinkID=236297) uusimman 64-bittisen version.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Miten voin vahvistaa, onko minulla lohko vuokraajassa?
Käytä seuraavaa PowerShell-komentosarjaa.

Seuraavien vaiheiden suorittaminen edellyttää, että asennat [Windows PowerShellin Azure Active Directory -moduulin](http://go.microsoft.com/fwlink/p/?LinkID=236297) uusimman 64-bittisen version.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Miten voin estää olemassa olevilta käyttäjiltä Power BI:n käytön aloittamisen?
Näillä toimenpiteillä voit järjestelmänvalvojana estää käyttäjiä rekisteröitymästä Power BI:hin. Jos estät liittymisen, käyttäjien rekisteröitymisyritykset epäonnistuvat ja heitä pyydetään ottamaan yhteyttä organisaation järjestelmänvalvojaan. Tätä prosessia ei tarvitse toistaa, jos olet jo poistanut automaattisen käyttöoikeuksien jakelun käytöstä (esim. Office 365 for Education opiskelijoille, opetushenkilöstölle ja muulle henkilöstölle). [Lue lisää](service-admin-licensing-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

Tätä ohjaava AAD -asetus on **AllowAdHocSubscriptions**. Useimmissa vuokraajissa tämä asetus on true (tosi), mikä tarkoittaa, että se on käytössä. Jos hankit Power BI:n kumppanin kautta, asetuksen oletusarvo saattaa olla FALSE (epätosi), mikä tarkoittaa, että se on poistettu käytöstä.

Seuraavien vaiheiden suorittaminen edellyttää, että asennat [Windows PowerShellin Azure Active Directory -moduulin](http://go.microsoft.com/fwlink/p/?LinkID=236297) uusimman 64-bittisen version.

1. Sinun on ensin kirjauduttava Azure Active Directoryyn käyttämällä Office 365 -tunnistetietojasi. Ensimmäisellä rivillä pyydetään syöttämään tunnistetiedot. Toinen rivi muodostaa yhteyden Azure Active Directoryyn.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Kun olet kirjautunut sisään, voit suorittaa seuraavan komennon, jolla näet, mikä asetus vuokraajalla on tällä hetkellä määritettynä.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Voit komennon avulla ottaa käyttöön ($true) tai poistaa käytöstä ($false) AllowAdHocSubscriptions-asetuksen.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions-lippua käytetään useiden käyttäjäominaisuuksien ohjaamiseen organisaatiossa. Sillä ohjataan muun muassa käyttäjien mahdollisuutta rekisteröityä Azure Rights Management -palveluun. Tämän lipun muuttaminen vaikuttaa kaikkiin näihin ominaisuuksiin.
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Miten voin sallia olemassa oleville käyttäjille Power BI:hin rekisteröitymisen?
Jos haluat sallia Power BI:hin rekisteröitymisen olemassa oleville käyttäjille, suorita yllä olevassa kysymyksessä mainittu komento, mutta käytä komennon arvona true (tosi) false-arvon (epätosi) sijasta.

Seuraavien vaiheiden suorittaminen edellyttää, että asennat [Windows PowerShellin Azure Active Directory -moduulin](http://go.microsoft.com/fwlink/p/?LinkID=236297) uusimman 64-bittisen version.

1. Sinun on ensin kirjauduttava Azure Active Directoryyn käyttämällä Office 365 -tunnistetietojasi. Ensimmäisellä rivillä pyydetään syöttämään tunnistetiedot. Toinen rivi muodostaa yhteyden Azure Active Directoryyn.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Kun olet kirjautunut sisään, voit suorittaa seuraavan komennon, jolla näet, mikä asetus vuokraajalla on tällä hetkellä määritettynä.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Voit komennon avulla ottaa käyttöön ($true) tai poistaa käytöstä ($false) AllowAdHocSubscriptions-asetuksen.
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions-lippua käytetään useiden käyttäjäominaisuuksien ohjaamiseen organisaatiossa. Sillä ohjataan muun muassa käyttäjien mahdollisuutta rekisteröityä Azure Rights Management -palveluun. Tämän lipun muuttaminen vaikuttaa kaikkiin näihin ominaisuuksiin.
> 
> 

## <a name="administration-of-power-bi"></a>Power BI:n hallinta
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Miten tämä muuttaa tapaa, jolla hallinnoin tällä hetkellä organisaationi käyttäjien käyttäjätietoja?
Jos organisaatiossasi on jo käytössä Office 365 -ympäristö, ja kaikilla käyttäjillä organisaatiossasi on Office 365 -tilit, käyttäjätietojen hallinnointi ei muutu.

Jos organisaatiossasi on jo käytössä Office 365 -ympäristö, mutta kaikilla käyttäjillä organisaatiossasi ei ole Office 365 -tiliä, luomme käyttäjätilin vuokraajaan ja myönnämme lisenssejä käyttäjän työn tai koulun sähköpostiosoitteen perusteella. Tämä tarkoittaa, että niiden käyttäjien, joiden tietoja hallinnoit tietyllä hetkellä, lukumäärä kasvaa, kun organisaatiosi käyttäjät rekisteröityvät palveluun.

Jos organisaatiollasi ei ole sähköpostisi toimialueeseen liitettyä Office 365 -ympäristöä, käyttäjätietojen hallinnointitapa ei muutu. Käyttäjät lisätään uuteen vain pilvi -käyttäjähakemistoon, ja sinulla on mahdollisuus ottaa vuokraajan järjestelmänvalvojan rooli ja hallinnoida tietoja.

### <a name="how-do-we-manage-power-bi"></a>Miten Power BI:tä hallitaan?
Power BI sisältää hallintaportaalin, jossa on käyttötilastoja, linkki Office 365:n hallintakeskukseen käyttäjien ja ryhmien hallintaa varten ja mahdollisuus hallita koko vuokraajaa koskevia asetuksia. 

> [!NOTE]
> Tililläsi täytyy olla **yleisen järjestelmänvalvojan** oikeudet Office 365:ssä tai Azure Active Directoryssa tai Power BI -palvelun järjestelmänvalvojan oikeudet, jotta voit käyttää Power BI -hallintaportaalia. Jos haluat lisätietoja Power BI -palvelun järjestelmänvalvojan roolista, lue ohjeartikkeli [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md).
> 
> 

Jos haluat lisätietoja, katso [Power BI:n hallintaportaali](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Millä tavalla voin hallinnoida vuokraajaa, jonka Microsoft on luonut käyttäjiäni varten?
Jos Microsoft on luonut vuokraajan, voit vaatia vuokraajaa käyttöösi ja hallinnoida sitä toimimalla seuraavien vaiheiden mukaisesti:

1. Liity vuokraajaan kirjautumalla Power BI:hin sillä sähköpostiosoitteen toimialueella, joka vastaa sen vuokraajan toimialuetta, jota haluat hallinnoida. Jos Microsoft on esimerkiksi luonut contoso.com-vuokraajan, sinun on liityttävä vuokraajaan sähköpostiosoitteella, jonka lopussa on @contoso.com.
2. Ota järjestelmänvalvojan oikeutesi käyttöön vahvistamalla toimialueen omistajuus: kun olet kirjautunut sisään vuokraajaan, voit antaa itsellesi *yleisen järjestelmänvalvojan* oikeudet vahvistamalla toimialueen omistajuuden. Toimi seuraavasti:
   
   1. Siirry kohteeseen [https://portal.office.com](https://portal.office.com).
   2. Valitse sovelluksen käynnistyskuvake vasemmasta yläkulmasta, ja valitse sitten **Järjestelmänvalvoja**.
   3. Lue ohjeet sivulta **Ryhdy järjestelmänvalvojaksi**, ja valitse sitten **Kyllä, haluan ryhtyä järjestelmänvalvojaksi**.
      
      > [!NOTE]
      > Jos tämä vaihtoehto ei ole näkyvillä, Office 365 -järjestelmänvalvoja on jo määritetty.
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Jos minulla on useita toimialueita, voinko hallinnoida Office 365 -vuokraajaa, johon käyttäjät on lisätty?
Jos et tee mitään, jokaista käyttäjän sähköpostin toimialuetta ja alitoimialuetta varten luodaan vuokraaja.

Jos haluat, että kaikki käyttäjät sijaitsevat samassa vuokraajassa riippumatta käyttäjien sähköpostiosoitteen tunnisteista:

* Luo alivuokraaja etukäteen tai käytä olemassa olevaa vuokraajaa ja lisää sitten kaikki olemassa olevat toimialueet ja alitoimialueet, jotka haluat yhdistää kyseiseen vuokraajaan. Tällöin kaikki käyttäjät, joiden sähköpostiosoitteen pääte viittaa kyseisiin toimialueisiin ja alitoimialueisiin, liittyvät automaattisesti kohdevuokraajaan rekisteröitymisen yhteydessä.

> [!IMPORTANT]
> Ei ole olemassa tuettua automaattista mekanismia käyttäjien siirtämiseksi vuokraajien välillä, kun ne on luotu. Jos haluat tietää, miten yksittäiseen Office 365 -vuokraajaan lisätään toimialueita, lue ohjeet kohdasta [Käyttäjien ja toimialueen lisääminen Office 365:een](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Miten voin poistaa Power BI:n käyttäjiltä, jotka ovat jo rekisteröityneet?
Jos käyttäjä on rekisteröitynyt Power BI:hin, mutta et enää halua hänen käyttävän Power BI:tä, voit poistaa Power BI -käyttöoikeuden kyseiseltä käyttäjältä.

1. Siirry Office 365:n hallintakeskukseen.
2. Valitse vasemmassa siirtymispalkissa **Käyttäjät** > **Aktiiviset käyttäjä**.
3. Etsi käyttäjä, jolta haluat poistaa lisenssin, valitse hänen nimensä ja valitse **Muokkaa**.
4. Valitse käyttäjän tietosivun vasemmanpuoleisesta siirtymisruudusta **Lisenssit**.
5. Poista valinta kohdasta **Power BI (maksuton)** tai **Power BI Pro**sen mukaan, mikä lisenssi käyttäjän tilissä on käytössä.
6. Valitse **Tallenna**.

> [!NOTE]
> Voit hallita käyttäjien lisenssejä myös joukkomuodossa. Valitse tätä varten useita käyttäjiä ja valitse sitten **Muokkaa**.
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Mistä tiedän, milloin uudet käyttäjät ovat liittyneet vuokraajaani?
Käyttäjille, jotka ovat liittyneet vuokraajaan osana tätä ohjelmaa, määritetään yksilöivä lisenssi, jota voit käyttää suodattimessa järjestelmänvalvojan koontinäytön aktiivisen käyttäjän ruudussa.

Luo tämä uusi näkymä Office 365 -hallintakeskuksessa valitsemalla **Käyttäjät** > **Aktiiviset käyttäjät** ja valitse sitten **Valitse näkymä** -valikosta **Uusi näkymä**. Anna uudelle näkymälle nimi ja valitse sitten **Määritetty käyttöoikeus** -kohdasta joko **Power BI (maksuton)** tai **Power BI Pro**. Näkymässä voi olla valittuna vain yksi käyttöoikeus. Jos organisaatiossa on sekä **Power BI (maksuton)**- että **Power BI Pro** -käyttöoikeuksia, joudut luomaan kaksi näkymää. Kun uusi näkymä on luotu, voit nähdä kaikki vuokraajan käyttäjät, jotka ovat rekisteröityneet tähän ohjelmaan.

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Onko muita asioita, joihin minun kannattaa valmistautua?
Salasanan vaihtamispyyntöjä saattaa tulla enemmän. Lisätietoja tästä prosessista on artikkelissa [Käyttäjän salasanan vaihtaminen](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c).

Voit poistaa käyttäjän vuokraajasta tavalliseen tapaan Office 365:n hallintakeskuksen kautta. Jos käyttäjällä on edelleen aktiivinen sähköpostiosoite organisaatiossasi, hän voi liittyä takaisin, ellet estä kaikkia käyttäjiä liittymästä.

### <a name="where-is-my-power-bi-tenant-located"></a>Missä Power BI -vuokraajani sijaitsee?
Jos haluat tietää, missä Power BI -vuokraajasi sijaitsee (kutsutaan myös tietoalueeksi), tutustu kohtaan [Missä Power BI -vuokraajani sijaitsee?](service-admin-where-is-my-tenant-located.md).

### <a name="what-is-the-power-bi-sla"></a>Mikä on Power BI:n palvelutasosopimus?
Lisätietoja Power BI:n palvelutasosopimuksesta on Microsoft Licensing -sivuston [Käyttöoikeusehdot ja -ohjeet](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) -artikkelin **käyttöoikeuksia** käsittelevässä kohdassa.

## <a name="security-in-power-bi"></a>Suojaus Power BI:ssä
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Onko Power BI kansallisten, alueellisten ja alakohtaisten vaatimusten mukainen?
Lisätietoja Power BI:n vaatimustenmukaisuudesta on [Microsoft Trust Centerissä](http://go.microsoft.com/fwlink/?LinkId=785324).

### <a name="how-does-security-work-in-power-bi"></a>Miten suojaus toimii Power BI:ssä?
Power BI perustuu Office 365:een, joka puolestaan perustuu Azure-palveluihin, kuten Azure Active Directoryyn. Yleiskatsaus Power BI -arkkitehtuurista on kohdassa [Power BI:n suojaus](service-admin-power-bi-security.md). 

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI -hallintaportaali](service-admin-portal.md)  
[Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md)  
[Omatoiminen kirjautuminen Power BI:hin](service-self-service-signup-for-power-bi.md)  
[Power BI Pron ostaminen](service-admin-purchasing-power-bi-pro.md)  
[Mikä on Power BI Premium?](service-premium.md)  
[Ohjeet Power BI Premiumin ostamiseen](service-admin-premium-purchase.md)  
[Office 365:n käyttäjätilien hallinta](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Office 365:n ryhmän hallinta](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[Ryhmän hallinta Power BI:ssä ja Office 365:ssä](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Power BI Premiumin tekninen raportti](https://aka.ms/pbipremiumwhitepaper)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)