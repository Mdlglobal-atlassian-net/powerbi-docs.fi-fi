---
title: Upotetun sovelluksen vianmääritys
description: Tässä artikkelissa käsitellään joitain yleisiä ongelmia, joita saattaa ilmetä, kun upotat sisältöä Power BI:stä.
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 2/26/2018
ms.author: maghan
ms.openlocfilehash: 78e3361578b82a9ebf69feae1f7a8ac54966bbc9
ms.sourcegitcommit: 0a16dc12bb2d39c19e6b0002b673a8c1d81319c9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/02/2018
ms.locfileid: "30974787"
---
# <a name="troubleshooting-your-embedded-application"></a>Upotetun sovelluksen vianmääritys

Tässä artikkelissa käsitellään joitain yleisiä ongelmia, joita saattaa ilmetä upotettaessa sisältöä Power BI:stä.

## <a name="tools-for-troubleshooting"></a>Työkalut vianmääritykseen

### <a name="fiddler-trace"></a>Fiddler-jäljitys

[Fiddler](http://www.telerik.com/fiddler) on Telerikin ilmainen työkalu, joka valvoo HTTP-liikennettä.  Voit tarkastella Power BI -ohjelmointirajapinnan tiedonsiirtoa asiakaskoneelta. Tämä saattaa näyttää virheitä ja muita olennaisia tietoja.

![Fiddler-jäljitys](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>F12 selainpuolen virheenkorjausta varten

F12 käynnistää kehittäjä-ikkunan selaimeltasi. Tämä mahdollistaa verkkoliikenteen ja muiden tietojen tarkastelun.

![F12 selaimen virheenkorjaus](media/embedded-troubleshoot/browser-f12.png)

### <a name="extracting-error-details-from-power-bi-response"></a>Virhetietojen poimiminen Power BI:n vastauksesta

Tämä koodikatkelma näyttää, miten voit poimia virhetiedot HTTP:n poikkeamasta:

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
Suosittelemme kirjaamaan pyyntötunnukset (sekä virhetiedot vianmääritystä varten).
Anna pyyntötunnus, kun otat yhteyttä Microsoft-tukeen.

## <a name="app-registration"></a>Sovelluksen rekisteröinti

**Virhe sovelluksen rekisteröinnissä**

Virheilmoitukset Azure-portaalissa tai Power BI -sovelluksen rekisteröintisivulla ilmoittavat puutteellisista käyttöoikeuksista. Voidaksesi rekisteröidä sovelluksen sinun on oltava Azure AD -vuokraajan järjestelmänvalvoja tai sovellusten rekisteröiminen pitää sallia erikseen myös muille kuin järjestelmänvalvojille.

**Power BI Service ei tule esiin Azure-portaalissa uutta sovellusta rekisteröitäessä**

Vähintään yhden käyttäjän on oltava rekisteröitynyt Power BI:hin. Jos et näe **Power BI -palvelua** ohjelmointirajapinta-luettelossa, kukaan käyttäjistä ei ole rekisteröitynyt Power BI:hin.

## <a name="rest-api"></a>REST-ohjelmointirajapinta

**Ohjelmointirajapinnan kutsuminen ilmoittaa 401**

Fiddler-sieppaus saattaa vaatia tarkempaa tutkimusta. Rekisteröidyn sovelluksen käyttöön vaadittavien käyttöoikeuksien laajuus saattaa olla puutteellinen Azure AD:ssa. Varmista Azure-portaalista, että käyttölaajuus on vaadittavalla tasolla Azure AD:n sovellusten rekisteröinnissä.

**Ohjelmointirajapinnan kutsuminen ilmoittaa 403**

Fiddler-sieppaus saattaa vaatia tarkempaa tutkimusta. 403-virheeseen voi olla useita syitä.

* Käyttäjä on ylittänyt niiden upotettujen tunnusten määrän, jotka voidaan luoda jaettuun kapasiteettiin. Sinun on ostettava Azure-kapasiteetit luodaksesi upotettavia tunnuksia ja määritettävä työtila kyseiselle kapasiteetille. Katso [Power BI Embedded -kapasiteetin luominen Azure-portaalissa](https://docs.microsoft.com/en-us/azure/power-bi-embedded/create-capacity).
* Azure AD:n todennustunnus on vanhentunut.
* Todennettu käyttäjä ei ole ryhmän jäsen (sovellus-työtila).
* Todennettu käyttäjä ei ole ryhmän järjestelmänvalvoja (sovellus-työtila).
* Käyttöoikeuksien myöntämisen otsikkoa ei ehkä ole lueteltu oikein. Varmista, että kirjoitusvirheitä ei ole.

Sovelluksen taustatietokanta saattaa joutua päivittämään todennustunnuksen ennen GenerateTokenin kutsumista.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

**Voimassa olevista käyttäjätiedoista huolimatta tunnussanoman luominen epäonnistuu**

Vaikka käyttäjätiedot olisivat voimassa GenerateToken voi epäonnistua muutamasta eri syystä.

* Tietojoukko ei tue voimassa olevia käyttäjätietoja
* Käyttäjänimeä ei ole annettu
* Roolia ei ole annettu
* Tietojoukon tunnusta ei ole annettu
* Käyttäjällä ei ole tarvittavia oikeuksia

Selvittääksesi syyn, kokeile seuraavaa.

* Suorita [tietojoukon hakeminen](https://msdn.microsoft.com/library/mt784653.aspx). Onko ominaisuus IsEffectiveIdentityRequired tosi?
* Mikä tahansa EffectiveIdentity vaatii käyttäjänimen.
* Mikäli IsEffectiveIdentityRolesRequired on tosi, rooli vaaditaan.
* Tietojoukon tunnus on pakollinen, minkä tahansa EffectiveIdentityn kanssa.
* Pääkäyttäjän on oltava yhdyskäytävän järjestelmänvalvoja käyttääkseen Analysis Servicesiä.

## <a name="data-sources"></a>Tietolähteet

**ISV haluaa eri tunnistetiedot samalle tietolähteelle**

Tietolähteellä voi olla vain yhdet tunnistetiedot yhtä pääkäyttäjää kohden. Mikäli haluat käyttää eri tunnistetietoja, luo ylimääräisiä pääkäyttäjiä. Seuraavaksi määritä eri tunnistetiedot kunkin pääkäyttäjän kohdalla ja upota ne käyttämällä käyttäjän Azure AD -tunnusta.

## <a name="content-rendering"></a>Sisällön hahmontaminen

**Upotetun sisällön hahmontaminen tai kuluttaminen epäonnistuu tai aika katkeaa**

Varmista, että upotettu tunnus ei ole vanhentunut. Tarkista upotetun tunnuksen voimassaoloaika ja päivitä se. Jos tarvitset lisätietoja, katso [päivitä tunnus JavaScript SDK:n avulla](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example).

**Raportti tai raporttinäkymä ei lataudu**

Jos käyttäjä ei näe raporttia tai raporttinäyttöä, varmista että ne latautuvat oikein powerbi.comissa. Raportti tai raporttinäkymä ei toimi sovelluksessasi, jos se ei lataudu powerbi.comissa.

**Raportti tai raporttinäkymä toimii hitaasti**

Avaa tiedosto Power BI Desktopissa tai powerbi.comissa ja varmista, että suorituskyky on hyväksyttävällä tasolla sulkeaksesi ulos sovelluksiisi tai upottaviin ohjelmointirajapintoihin liittyvät ongelmat.


Usein kysyttyihin kysymyksiin löydät vastauksia kohdasta [Power BI Embedded usein kysytyt kysymykset](embedded-faq.md).

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
