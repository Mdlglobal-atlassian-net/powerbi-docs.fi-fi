---
title: Omatoimisen rekisteröitymisen ja ostamisen ottaminen käyttöön tai poistaminen käytöstä
description: Järjestelmänvalvojien ohjeet siihen, miten käyttäjien mahdollisuus Power BI:tä varten rekisteröitymiseen ja käyttöoikeuden ostamiseen poistetaan käytöstä.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/08/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 561d8b6cd0e17e885ced984315a04376400a2a58
ms.sourcegitcommit: b2cb0b02bdc451bf11a92a68f2c4d560a811f563
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/16/2020
ms.locfileid: "81447506"
---
# <a name="enable-or-disable-self-service-sign-up-and-purchasing"></a>Omatoimisen rekisteröitymisen ja ostamisen ottaminen käyttöön tai poistaminen käytöstä

Useimmissa organisaatioissa omatoiminen kirjautuminen on oletusarvoisesti käytössä. Organisaatiosi eri käyttäjät voivat rekisteröityä Power BI:tä varten työpaikan tai oppilaitoksen tilinsä avulla. Käyttäjille voidaan myös tarjota mahdollisuus ostaa Power BI Pro -käyttöoikeus suoraan, jos he yrittävät käyttää Pro-käyttöoikeutta vaativaa ominaisuutta. Järjestelmänvalvojana voit määrittää, otetaanko omatoimisen palvelun rekisteröinti käyttöön vai poistetaanko se käytöstä. Voit myös määrittää, voivatko organisaatiosi käyttäjät ostaa oman käyttöoikeutensa omatoimisesti.

> [!NOTE]
>Jos olet hankkinut Power BI:n Microsoft pilvipalveluratkaisujen toimittajan kautta, asetus voidaan poistaa käytöstä, jotta käyttäjät eivät voi rekisteröityä omatoimisesti. Pilvipalveluratkaisujen toimittajasi voi toimia myös organisaatiosi yleisenä järjestelmänvalvojana, jolloin sinun on otettava toimittajaan yhteyttä, jotta voit muuttaa tätä asetusta.
>
>

Asetuksia, jotka ohjaavat omatoimista rekisteröitymistä ja ostamista, muutetaan PowerShell-komentojen avulla. On olemassa kaksi asetusta, jotka ohjaavat sitä, voivatko organisaatiosi käyttäjät rekisteröityä tai tehdä ostoksia omatoimisesti.

- Jos haluat poistaa käytöstä kaikki omatoimiset kirjautumiset, muuta Azure Active Directoryssa asetusta nimeltä **AllowAdHocSubscriptions** Azure AD PowerShell -komentojen avulla. [Ota käyttöön tai poista käytöstä omatoiminen rekisteröityminen](#enable-or-disable-self-service-signup) noudattamalla tämän artikkelin ohjeita. Tämä asetus poistaa käytöstä omatoimisen rekisteröitymisen *kaikissa* Microsoftin pilvipohjaisissa sovelluksissa ja palveluissa.

- Jos haluat estää käyttäjiä ostamasta omia Pro-käyttöoikeuksiaan, muuta **AllowSelfServicePurchase**-asetusta MSCommercen PowerShell -komentojen avulla. Tämän asetuksen avulla voit poistaa käytöstä tiettyjen tuotteiden omatoimisen ostamisen. [Ota käyttöön tai poista käytöstä Power BI Pro -käyttöoikeuksien omatoiminen ostaminen](#enable-or-disable-self-service-purchase) noudattamalla tämän artikkelin ohjeita.

## <a name="enable-or-disable-self-service-signup"></a>Omatoimisen rekisteröitymisen ottaminen käyttöön tai poistaminen käytöstä

Jos omatoiminen rekisteröityminen on käytössä, **AllowAdHocSubscriptions**-arvona on *true*. Katsotaan, mitä tapahtuu, kun muutat tämän asetuksen arvoksi vaihtoehdon *false*:

- Jos muutat asetuksen arvon true arvoksi false, organisaatiosi uudet käyttäjät eivät voi rekisteröityä omatoimisesti. Käyttäjät, jotka ovat rekisteröityneet Power BI:hin, ennen kuin muutat asetusta, säilyttävät käyttöoikeutensa.

- Jos muutat asetuksen arvoksi vaihtoehdon false, käyttäjät, joilla on (ilmainen) Power BI -käyttöoikeus jo ennestään, voivat yhä rekisteröityä yksityishenkilölle tarkoitettuun Power BI Pro -kokeilutilaukseen.

- Järjestelmänvalvojan on määritettävä kaikki Power BI -käyttöoikeudet niitä tarvitseville uusille käyttäjille.

### <a name="before-you-begin"></a>Alkutoimet

Näissä ohjeissa **AllowAdHocSubscriptions**-asetuksen arvoa muutetaan Azure Active Directoryn PowerShell-komennoilla. Sinulla on oltava Azure AD:n PowerShell -moduuli asennettuna, jotta nämä komennot ovat käytettävissä. Lisätietoja PowerShellin käyttämisestä on artikkelissa [Windows PowerShellin käytön aloittaminen](https://docs.microsoft.com/powershell/scripting/getting-started/getting-started-with-windows-powershell?view=powershell-7).

Jos haluat asentaa Azure AD -moduulin, käynnistä Windows PowerShell järjestelmänvalvojana. Varmista, että paikallinen suorituskäytäntö sallii komentosarjojen suorittamisen. Jos kohtaat ongelmia, katso artikkelista [PowerShellin suorituskäytännöt](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7#powershell-execution-policies) tietoja paikallisen käytännön muuttamisesta.

Asenna Azure AD -moduuli suorittamalla seuraava komento:

```powershell
Install-Module MSOnline
```

### <a name="change-the-self-service-signup-policy"></a>Omatoimisen rekisteröitymiskäytännön muuttaminen

Muodosta yhteys Azure AD:hen suorittamalla seuraava komento PowerShellissä:

```powershell
Connect-MsolService
```

Anna järjestelmänvalvojan tunnistetietosi kirjautumisvalintaikkunassa ja anna mahdollisesti tarvittavat kaksivaiheisen todentamisen tiedot. Vahvistuksen jälkeen sinut palautetaan PowerShell-ikkunaan.

Saat käytössä olevan asetuksen näkyviin suorittamalla seuraavan komennon. Tulos johdetaan muotoiltuun luetteloon fl-valitsimen avulla.

```powershell
Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
```

Jos haluat muuttaa käytössä olevaa asetusta, suorita tämä komento:

```powershell
Set-MsolCompanySettings -AllowAdHocSubscriptions $false
```

Tämän komennon suorittamisen jälkeen omatoiminen rekisteröinti on poissa käytöstä kaikilla käyttäjillä. Jos haluat ottaa sen uudelleen käyttöön, suorita tämä komento uudelleen ja määritä arvoksi $true.

## <a name="enable-or-disable-self-service-purchase"></a>Omatoimisen ostamisen ottaminen käyttöön tai poistaminen käytöstä

Jos omatoiminen ostaminen on käytössä, **AllowSelfServicePurchase**-arvona on *true*. Katsotaan, mitä tapahtuu, kun muutat tämän asetuksen arvoksi vaihtoehdon *false*:

- Jos muutat asetuksen arvon true arvoksi false, organisaatiosi käyttäjät eivät voi ostaa omaa Power BI Pro -käyttöoikeutta. Käyttäjät, jotka ovat ostaneet käyttöoikeuden, ennen kuin muutat asetusta, säilyttävät käyttöoikeutensa.

- Jos muutat asetuksen arvoksi vaihtoehdon false, käyttäjät, joilla on (ilmainen) Power BI -käyttöoikeus, eivät voi hankkia yksityishenkilölle tarkoitettua Power BI Pro -käyttöoikeutta. 

- Järjestelmänvalvojan on määritettävä Pro-käyttöoikeus kaikille käyttäjille, jotka tarvitsevat sen.

### <a name="before-you-begin"></a>Alkutoimet

Näissä ohjeissa käytetään MSCommercen PowerShell -komentoja **AllowSelfServicePurchase**-asetuksen arvon muuttamiseen. Sinulla on oltava MSCommercen PowerShell -moduuli asennettuna, jotta nämä komennot ovat käytettävissä. Lisätietoja PowerShellin käyttämisestä on artikkelissa [Windows PowerShellin käytön aloittaminen](https://docs.microsoft.com/powershell/scripting/getting-started/getting-started-with-windows-powershell?view=powershell-7).

Jos haluat asentaa MSCommerce-moduulin, käynnistä Windows PowerShell järjestelmänvalvojana. Varmista, että paikallinen suorituskäytäntö sallii komentosarjojen suorittamisen. Jos kohtaat ongelmia, katso artikkelista [PowerShellin suorituskäytännöt](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7#powershell-execution-policies) tietoja paikallisen käytännön muuttamisesta.

Asenna MSCommerce-moduuli suorittamalla seuraava komento:

```powershell
Install-Module -name MSCommerce
```

### <a name="change-the-self-service-signup-policy"></a>Omatoimisen rekisteröitymiskäytännön muuttaminen

Muodosta yhteys suorittamalla seuraava komento PowerShellissä:

```powershell
Connect-MSCommerce
```

Anna järjestelmänvalvojan tunnistetietosi kirjautumisvalintaikkunassa ja anna mahdollisesti tarvittavat kaksivaiheisen todentamisen tiedot. Yhteyden muodostamisen onnistuminen näkyy PowerShell-ikkunassa vahvistuksen jälkeen.

Saat käytössä olevan asetuksen näkyviin suorittamalla seuraavan komennon. Tulos johdetaan muotoiltuun luetteloon fl-valitsimen avulla tekstin katkeamisen välttämistä varten.

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase | fl
```

Voit poistaa käytöstä asetuksen, joka sallii yksittäisen tuotteen omatoimisen ostamisen **ProductId**-tunnuksen avulla. Jos haluat muuttaa Power BI -palvelun käytössä olevaa asetusta, suorita tämä komento:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0L3PB -Enabled $False
```

Tämän komennon suorittamisen jälkeen omatoiminen Power BI:n ostaminen on poissa käytöstä kaikilla käyttäjillä. Jos haluat ottaa sen uudelleen käyttöön, suorita tämä komento uudelleen ja määritä arvoksi $true.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja omatoimisen ostamisen käytöstä poistamisesta Power BI:ssä ja Power Platformin muissa osissa on seuraavissa artikkeleissa:

- [Omaehtoisen ostamisen usein kysytyt kysymykset](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide#admin-capabilities)
- [MSCommercen PowerShell -moduulin AllowSelfServicePurchase-asetuksen käyttäminen](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell?view=o365-worldwide)
