---
title: Mitä on Power BI:n hallinta?
description: Lue lisätietoja Power BI:n hallintakäytäntöjen määrityksestä, käytön valvonnasta sekä käyttöoikeuksien, kapasiteettien ja organisaatioresurssien valmistelusta.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: overview
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: cfe877d6fac96124badc19f6ab685523077132fc
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2020
ms.locfileid: "79381280"
---
# <a name="what-is-power-bi-administration"></a>Mitä on Power BI:n hallinta?

Power BI:n hallinta on Power BI -vuokraajan hallintaa, mukaan lukien hallintakäytäntöjen määritys, käytön valvonta sekä käyttöoikeuksien, kapasiteettien ja organisaatioresurssien valmistelu. Tässä artikkelissa on yleiskatsaus hallinnan rooleista, tehtävistä ja työkaluista. Lisäksi saat linkkejä artikkeleihin, joissa on tarkempia tietoja.

![Power BI -hallintaportaali](media/service-admin-administering-power-bi-in-your-organization/admin-portal.png)

Power BI on suunniteltu omatoimiseen liiketoimintatietojen hallintaan, ja järjestelmänvalvoja on vastuussa Power BI -vuokraajan tiedoista, prosesseista ja käytännöistä. Power BI -järjestelmänvalvoja on keskeinen jäsen tiimissä, joka sisältää BI-kehittäjiä, analyytikoita ja muita rooleja. Järjestelmänvalvoja voi auttaa organisaatiota varmistamaan, että kriittiset tavoitteet täyttyvät:

- Ymmärtämään suorituskykyilmaisimet ja mittarit, joita käyttäjät _todellisuudessa_ tarvitsevat
- Lyhentämään IT-lähtöisen yritysraportoinnin toimitusaikaa
- Parantamaan Power BI -käyttöönoton omaksumista ja sijoitetun pääoman tuottoa

Tehtävänä on parantaa yrityskäyttäjien tuottavuutta sekä varmistaa suojaus ja lakien ja asetusten noudattaminen. Vastuualueet voivat sisältää ohjeita ja tukea, ja useissa tapauksissa ne auttavat yrityskäyttäjiä toimimaan oikein.

## <a name="administrator-roles-related-to-power-bi"></a>Power BI:hin liittyvät järjestelmänvalvojaroolit

Power BI:n hallintaan liittyy useita rooleja, jotka on kuvattu seuraavassa taulukossa.

| **Järjestelmänvalvojan tyyppi** | **Hallinnollinen laajuus** | **Power BI -laajuus** |
| --- | --- | --- |
| Office 365:n yleinen järjestelmänvalvoja | Office 365 | Voi hallita kaikkia Power BI -vuokraajan ominaisuuksia ja muita palveluja. |
| Office 365:n laskutuksen järjestelmänvalvoja | Office 365 | Voi hankkia Power BI -käyttöoikeuksia Office 365 -tilausten kautta. |
| Power BI -palvelun järjestelmänvalvoja | Power BI -vuokraaja | Omaa täydet Power BI -vuokraajan ja sen hallintaominaisuuksien oikeudet (paitsi käyttöoikeus). |
| Power BI Premium -kapasiteetin järjestelmänvalvoja | Yksittäinen Premium-kapasiteetti | Omaa täydet Premium-kapasiteetin ja sen hallintaominaisuuksien oikeudet. |
| Power BI Embedded -kapasiteetin järjestelmänvalvoja | Yksittäinen upotettu kapasiteetti | Omaa täydet upotetun kapasiteetin ja sen hallintaominaisuuksien oikeudet. |

Office 365:n tai Azure Active Directoryn yleisillä järjestelmänvalvojilla on hallintaoikeudet Power BI:ssä. Office 365:n yleinen järjestelmänvalvoja voi määrittää muille käyttäjille Power BI -palvelun järjestelmänvalvojan roolin, joka myöntää järjestelmänvalvojan oikeudet vain Power BI -ominaisuuksiin.

Power BI -palvelun järjestelmänvalvojilla on pääsyoikeus Power BI -hallintaportaaliin, joka sisältää useita vuokraajatason asetuksia, jotka liittyvät toimintoihin, suojaukseen ja valvontaan. Palvelun järjestelmänvalvojilla on täydet käyttöoikeudet kaikkiin Power BI -vuokraajan resursseihin. Useimmissa tapauksissa palvelun järjestelmänvalvojat voivat tunnistaa ongelmia ja korjata ne yhdessä resurssien omistajien kanssa.

Power BI -palvelun järjestelmänvalvojan rooli ei anna oikeuksia määrittää käyttäjälle käyttöoikeuksia tai tarkastella Office 365:n valvontalokeja. Power BI:n hallintaa ei siten voida tällä hetkellä suorittaa vain Power BI -palvelun järjestelmänvalvojan roolilla.

## <a name="administrative-tasks"></a>Hallintatehtävät

Järjestelmänvalvojat suorittavat monia tehtäviä, jotka tukevat Power BI -vuokraajaa organisaatiossa. Tehtävät on kuvattu seuraavassa taulukossa.

| **Tehtävän alue** | **Tavalliset tehtävät** |
| --- | --- |
| Power BI -vuokraajan hallinta |<ul><li>Power BI:n pääominaisuuksien ottaminen käyttöön ja pois käytöstä<br><li>Raportointi käytöstä ja suorituskyvystä<br><li>Tapahtumien valvonnan arviointi ja hallinta</ul>|
| Power BI -käyttöoikeuksien hankinta ja hallinta |<ul><li>Käyttäjien rekisteröitymisen hallinta<br><li>Pro-käyttöoikeuksien hankinta ja määritys<br><li>Power BI:n käytön estäminen käyttäjiltä</ul>|
| Premium-kapasiteetin hallinta |<ul><li>Premium-kapasiteetin hankinta ja käsittely<br><li>Palvelun laadun varmistaminen|
| Upotetun kapasiteetin hallinta |<ul><li>Upotetun kapasiteetin hallinta, jotta riippumattomat ohjelmistokehittäjät ja muut kehittäjät voivat käyttää Power BI -ominaisuuksia helpommin</ul>|
| Sisäisten käytäntöjen, lakien ja säädösten noudattamisen varmistaminen | <ul><li>Yritystietojen luokittelun hallinta<br><li>Sisällön julkaisemisen ja jakamisen käytäntöjen valvonnan tukeminen</ul>|
| Power BI -resurssien hallinta |<ul><li>Työtilojen hallinta<br><li>Power BI -visualisointien julkaiseminen<br><li>Power BI:n muihin sovelluksiin upottamiseen käytettyjen koodien vahvistaminen|
| Vuokraajan käyttäjien auttaminen ja tukeminen |<ul><li>Tietojen käytön ja muiden ongelmien vianmääritys</ul>|
| Muut tehtävät |<ul><li>Power BI Desktopin käyttöönotto, esim. Microsoft Endpoint Configuration Managerin avulla<br><li>Power BI -mobiilisovelluksen käyttöönoton hallinta Intunella<br><li>Tietosuojan ja tietoturvan hallinta, kuten lähdetietojen suojauksen hallinta</ul>|

## <a name="administrative-tools"></a>Hallintatyökalut

Power BI:n hallintaan liittyy useita työkaluja, jotka on kuvattu seuraavassa taulukossa. Järjestelmänvalvojat käyttävät yleensä suurimman osan työajastaan Power BI -hallintaportaalissa ja muiden tarvittavien työkalujen parissa.

| **Työkalu** | **Tavalliset tehtävät** |
| --- | --- |
| Power BI -hallintaportaali |<ul><li>Premium-kapasiteetin hankinta ja käsittely</li><li>Palvelun laadun varmistaminen</li><li>Yritystietojen luokittelun hallinta</li><li>Sisällön julkaisemisen ja jakamisen käytäntöjen valvonnan tukeminen</li><li>Työtilojen hallinta<br><li>Power BI -visualisointien julkaiseminen</li><li>Power BI:n muihin sovelluksiin upottamiseen käytettyjen koodien vahvistaminen</li><li>Tietojen käytön ja muiden ongelmien vianmääritys</li></ul>|
| Microsoft 365 -hallintakeskus |<ul><li>Käyttäjien rekisteröitymisen hallinta</li><li>Pro-käyttöoikeuksien hankinta ja määritys</li><li>Power BI:n käytön estäminen käyttäjiltä</li></ul>|
| Office 365:n tietoturva- ja yhteensopivuuskeskus |<ul><li>Tapahtumien valvonnan arviointi ja hallinta</li></ul>|
| Azure Active Directory (AAD) Azure-portaalissa |<ul><li>Power BI -resurssien ehdollisen käyttöoikeuden määrittäminen AAD:n kautta</li><li>Power BI Embedded -kapasiteetin valmistelu</li></ul>|
| PowerShellin cmdlet-komennot |<ul><li>Työtilojen ja muiden Power BI:n ominaisuuksien hallinta komentosarjojen hallinta</li></ul>|
| Hallinnolliset ohjelmointirajapinnat ja SDK |<ul><li>Mukautettujen työkalujen laatiminen Power BI -järjestelmänvalvojan työtä varten. Esimerkiksi Power BI Desktop voi käyttää näitä ohjelmointirajapintoja hallinnollisiin tietoihin perustuvien raporttien laatimiseen</li></ul>|

## <a name="next-steps"></a>Seuraavat vaiheet

Toivomme, että tämä artikkeli tarjosi sinulle yleiskuvan Power BI -järjestelmänvalvojan työstä sekä siihen liittyvistä rooleista, tehtävistä ja työkaluista. Suosittelemme, että syvennät tietämystäsi seuraavien artikkelien avulla.

- [Power BI -hallintaportaalin käyttäminen](service-admin-portal.md)
- [Vuokraajan järjestelmänvalvojan asetuksia koskevat ohjeet](guidance/admin-tenant-settings.md)
- [PowerShellin cmdlet-komentojen käyttäminen](/powershell/power-bi/overview)
- [Power BI:n hallinnan usein kysytyt kysymykset](service-admin-faq.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
