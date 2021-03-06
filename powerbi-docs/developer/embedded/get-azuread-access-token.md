---
title: Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen hankkiminen sovellukselle
description: Lue ohjeet siihen, miten voit rekisteröidä sovelluksen Azure Active Directoryssä Power BI -sisällön upottamiseksi.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/04/2019
ms.openlocfilehash: cac59a4689eecd75c53ca1c62d7b097438b2ae53
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80114516"
---
# <a name="get-an-azure-ad-access-token-for-your-power-bi-application"></a>Azure AD -käyttöoikeustietueen hankkiminen Power BI -sovellukselle

Tässä artikkelissa näytetään, miten voit todentaa käyttäjiä Power BI -sovelluksessa ja noutaa käyttöoikeustietueen [Power BI:n REST-ohjelmointirajapinnassa](https://docs.microsoft.com/rest/api/power-bi/) käytettäväksi.

Ennen kuin sovelluksesi kutsuu REST -ohjelmointirajapintaa, sinun on haettava Azure Active Directoryn (Azure AD) **todennuksen käyttöoikeustietue**. Käyttöoikeustietueella annetaan sovellukselle oikeus käyttää Power BI:n raporttinäkymiä, ruutuja ja raportteja. Lisätietoja on kohdassa [Azure Active Directoryn verkkosovelluksen määrittäminen käyttämään OAuth 2.0 -koodinmyöntämistyönkulkua](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).

Käyttöoikeustietueen hakemistapa riippuu siitä, miten upotat sisältöä. Tässä artikkelissa näytetään kaksi eri lähestymistapaa.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Power BI -käyttäjien käyttöoikeustietue (käyttäjä omistaa tiedot)

Tämä esimerkki on tarkoitettu tilanteeseen, jossa käyttäjäsi kirjautuvat Azure AD:hen manuaalisesti organisaatiotunnuksillaan. Tätä tehtävää käytetään upotettaessa sisältöä käyttäjille, joilla on Power BI -palvelun käyttöoikeus.

### <a name="get-an-azure-ad-authorization-code"></a>Azure AD -valtuutuskoodin noutaminen

Ensimmäinen vaihe **käyttöoikeustietueen** hankkimiseksi on valtuutuskoodin hankkiminen **Azure AD:stä**. Muodosta kyselymerkkijono seuraavilla ominaisuuksilla ja ohjaa se uudelleen **Azure AD:hen**.

#### <a name="authorization-code-query-string"></a>Valtuutuskoodin kyselymerkkijono

```csharp
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
    {"redirect_uri", "https://localhost:13526/Redirect"}
};
```

Kun olet muodostanut kyselymerkkijonon, ohjaa uudelleen **Azure AD:hen** saadaksesi **valtuutuskoodin**.  Alla on valmis C#-menetelmä **valtuutuskoodia** koskevan kyselymerkkijonon muodostamiseen ja ohjaamiseen uudelleen **Azure AD:hen**. Voit sen jälkeen käyttää **valtuutuskoodia** **käyttöoikeustietueen** noutamiseen.

[AuthenticationContext.AcquireTokenByAuthorizationCode](https://docs.microsoft.com/dotnet/api/microsoft.identitymodel.clients.activedirectory.authenticationcontext.acquiretokenbyauthorizationcodeasync?view=azure-dotnet#Microsoft_IdentityModel_Clients_ActiveDirectory_AuthenticationContext_AcquireTokenByAuthorizationCodeAsync_System_String_System_Uri_Microsoft_IdentityModel_Clients_ActiveDirectory_ClientCredential_System_String_) tekee kutsun kohteessa redirect.aspx.cs tietueen luomiseksi.

#### <a name="get-authorization-code"></a>Valtuutuskoodin hankkiminen

```csharp
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
        {"redirect_uri", "https://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.microsoftonline.com/common/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Käyttöoikeustietueen hankkiminen valtuutuskoodista

Kun **Azure AD** tekee uudelleenohjauksen takaisin verkkosovellukseen **varmennuskoodilla**, voit käyttää sitä käyttöoikeustietueen noutamiseen. Alla on C#-esimerkki, jota voit käyttää uudelleenohjaussivullasi sekä default.aspx-sivusi tapahtumassa `Page_Load`.

Nimitila **Microsoft.IdentityModel.Clients.ActiveDirectory** on noudettavissa [Active Directory -todentamiskirjaston](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet-paketista.

```powershell
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

#### <a name="redirectaspxcs"></a>Redirect.aspx.cs

```csharp
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

#### <a name="defaultaspx"></a>Default.aspx

```csharp
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

Tätä lähestymistapaa käytetään yleensä sellaisia ISV-tyyppisiä sovelluksia varten, joissa sovellus omistaa tietojen käyttöoikeudet. Käyttäjät eivät välttämättä ole Power BI -käyttäjiä, ja sovellus hallitsee käyttäjien todentamista ja käyttöoikeuksia.

### <a name="access-token-with-a-master-account"></a>Käyttöoikeustietue ja päätili

Tässä tavassa käytetään yksittäistä *päätiliä*, joka on Power BI Pro -käyttäjä. Tilin tunnistetiedot tallennetaan sovellukseen. Sovellus todennetaan Azure AD:stä kyseisten tallennettujen tunnistetietojen avulla. Alla oleva esimerkkikoodi on peräisin [sovellus omistaa tiedot -mallista](https://github.com/guyinacube/PowerBI-Developer-Samples)

### <a name="access-token-with-service-principal"></a>Käyttöoikeustietue ja palvelun päänimi

Tässä tavassa käytetään [palvelun päänimeä](embed-service-principal.md), joka on **vain sovelluksen** käyttämä tunnus. Sovellus todennetaan Azure AD:stä palvelun päänimellä. Alla oleva esimerkkikoodi on peräisin [sovellus omistaa tiedot -mallista](https://github.com/guyinacube/PowerBI-Developer-Samples)

#### <a name="embedservicecs"></a>EmbedService.cs

```csharp
var authenticationContext = new AuthenticationContext(AuthorityUrl);
       AuthenticationResult authenticationResult = null;
       if (AuthenticationType.Equals("MasterUser"))
       {
              // Authentication using master user credentials
              var credential = new UserPasswordCredential(Username, Password);
              authenticationResult = authenticationContext.AcquireTokenAsync(ResourceUrl, ApplicationId, credential).Result;
       }
       else
       {
             // Authentication using app credentials
             var credential = new ClientCredential(ApplicationId, ApplicationSecret);
             authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, credential);
       }


m_tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

## <a name="troubleshoot"></a>Vianmääritys

Virheilmoitus: "'AuthenticationContext' ei sisällä 'AcquireToken'-määritettä, eikä löytynyt käytettävissä olevaa 'AcquireToken'-tunnistetta, joka hyväksyisi 'AuthenticationContext'-arvon (puuttuuko using-direktiivi tai kokoonpanoviittaus?)”.

   Yritä ladata [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727), jos näet tämän virheen.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun sinulla on käyttöoikeustietue, voit kutsua Power BI REST -ohjelmointirajapinnan upottamaan sisältöä. Katso lisätiedot kohdasta [Power BI -sisällön upottaminen](embed-sample-for-customers.md#embed-content-within-your-application).

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
