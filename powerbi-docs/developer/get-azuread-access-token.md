---
title: Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen hankkiminen sovellukselle
description: Lue, miten voit rekisteröidä sovelluksen Azure Active Directoryssä Power BI -sisällön upottamiseksi.
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
ms.date: 08/11/2017
ms.author: maghan
ms.openlocfilehash: 3ff0fa3c83654ac577e98e730dc68ce3686e1198
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
ms.locfileid: "30973117"
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen hankkiminen Power BI -sovellukselle
Katso, miten voit todentaa käyttäjiä Power BI -sovelluksessa ja noutaa käyttöoikeustietueen REST-ohjelmointirajapinnassa käytettäväksi.

Ennen kuin voit kutsua Power BI REST -ohjelmointirajapintaa, sinun on saatava Azure Active Directoryn (Azure AD) **todennuksen käyttöoikeustietue** (käyttöoikeustietue). **Käyttöoikeustietuetta** käytetään sallimaan sovellukselle **Power BI** -koontinäyttöjen, -ruutujen ja -raporttien käyttö. Katso lisätietoja Azure Active Directoryn **käyttöoikeustietuetta** koskevasta työnkulusta kohdasta [Azure AD -valtuutuskoodin myöntämistä koskeva työnkulku](https://msdn.microsoft.com/library/azure/dn645542.aspx).

Käyttöoikeustietue haetaan eri tavoilla riippuen siitä, miten upotat sisältöä. Tässä artikkelissa käytetään kahta eri lähestymistapaa.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Power BI -käyttäjien käyttöoikeustietue (käyttäjä omistaa tiedot)
Tämä esimerkki on tilanteeseen, jossa käyttäjäsi kirjautuvat Azure AD:hen manuaalisesti organisaatiotunnuksillaan. Tätä käytetään upotettaessa sisältöä Power BI -käyttäjille, jotka käyttävät sisältöä, johon heillä on käyttöoikeus Power BI -palvelussa.

### <a name="get-an-authorization-code-from-azure-ad"></a>Valtuutuskoodin hankkiminen Azure AD:stä
Ensimmäinen vaihe **käyttöoikeustietueen** hankkimiseksi on valtuutuskoodin hankkiminen **Azure AD:stä**. Voit tehdä tämän muodostamalla kyselymerkkijonon, jossa on seuraavat ominaisuudet, ja ohjaamalla uudelleen **Azure AD:hen**.

**Valtuutuskoodin kyselymerkkijono**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

Kun olet muodostanut kyselymerkkijonon, ohjaa uudelleen **Azure AD:hen** saadaksesi **valtuutuskoodin**.  Alla on valmis C#-menetelmä **valtuutuskoodia** koskevan kyselymerkkijonon muodostamiseen ja ohjaamiseen uudelleen **Azure AD:hen**. Kun sinulla on valtuutuskoodi, saat **käyttöoikeustietueen** käyttämällä **valtuutuskoodia**.

Kohteessa redirect.aspx.cs [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) kutsutaan sitten muodostamaan tietue.

**Valtuutuskoodin hankkiminen**

```
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.windows.net/common/oauth2/authorize/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Käyttöoikeustietueen hankkiminen valtuutuskoodista
Sinulla pitäisi nyt olla valtuutuskoodi Azure AD:stä. Kun **Azure AD** tekee uudelleenohjauksen takaisin verkkosovellukseen **varmennuskoodilla**, voit käyttää **valtuutuskoodia** saadaksesi käyttöoikeustietueen. Alla on C#-esimerkki, jota voit käyttää uudelleenohjaussivullasi sekä default.aspx-sivusi tapahtumassa Page_Load.

Nimitila **Microsoft.IdentityModel.Clients.ActiveDirectory** on noudettavissa [Active Directory -todentamiskirjaston](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet-paketista.

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

**Default.aspx**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Muiden kuin Power BI -käyttäjien käyttöoikeustietue (sovellus omistaa tiedot)
Tätä lähestymistapaa käytetään yleensä sellaisia ISV-tyyppisiä sovelluksia varten, joissa sovellus omistaa tietojen käyttöoikeudet. Käyttäjät eivät välttämättä ole Power BI -käyttäjiä, ja sovellus hallinnoi loppukäyttäjien todentamista ja käyttöoikeuksia.

Tätä lähestymistapaa varten käytetään yksittäistä *pää*tiliä, joka on Power BI Pro -käyttäjä. Tämän tilin tunnistetiedot tallennetaan sovellukseen. Sovellus todentaa Azure AD:tä vasten kyseisten tallennettujen tunnistetietojen avulla. Alla oleva esimerkkikoodi on peräisin [sovellus omistaa tiedot -mallista](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

Lisätietoja **await**-operaattorin käytöstä on kohteessa [await (C#-viittaus)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)

## <a name="next-steps"></a>Seuraavat vaiheet
Nyt kun sinulla on käyttöoikeustietue, voit kutsua Power BI REST -ohjelmointirajapinnan upottamaan sisältöä. Saat sisältösi upottamista koskevia tietoja kohdasta [Power BI -koontinäyttöjen, -raporttien ja -ruutujen upottaminen](embedding-content.md#step-2-embed-your-content).

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

