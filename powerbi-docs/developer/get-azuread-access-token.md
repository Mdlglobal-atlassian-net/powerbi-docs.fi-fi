---
title: Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen hankkiminen sovellukselle
description: Lue ohjeet siihen, miten voit rekisteröidä sovelluksen Azure Active Directoryssä Power BI -sisällön upottamiseksi.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: a38547807fbbcf3c76366f32caa46945e57ca8bc
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710311"
---
# <a name="get-an-azure-ad-access-token-for-your-power-bi-application"></a>Azure AD -käyttöoikeustietueen hankkiminen Power BI -sovellukselle

Lue ohjeet siihen, miten voit todentaa käyttäjiä Power BI -sovelluksessa ja noutaa käyttöoikeustietueen REST-ohjelmointirajapinnassa käytettäväksi.

Ennen kuin voit kutsua Power BI REST -ohjelmointirajapintaa, sinun on saatava Azure Active Directoryn (Azure AD) **todennuksen käyttöoikeustietue** (käyttöoikeustietue). **Käyttöoikeustietueella** annetaan sovellukselle oikeus käyttää **Power BI:n** koontinäyttöjä, ruutuja ja raportteja. Katso lisätietoja Azure Active Directoryn **käyttöoikeustietuetta** koskevasta työnkulusta kohdasta [Azure AD -valtuutuskoodin myöntämistä koskeva työnkulku](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).

Käyttöoikeustietueen hakemistapa riippuu siitä, miten upotat sisältöä. Tässä artikkelissa käytetään kahta eri tapaa.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Power BI -käyttäjien käyttöoikeustietue (käyttäjä omistaa tiedot)

Tämä esimerkki on tarkoitettu tilanteeseen, jossa käyttäjäsi kirjautuvat Azure AD:hen manuaalisesti organisaatiotunnuksillaan. Tätä käytetään, kun upotat sisältöä Power BI -käyttäjille, jotka käyttävät sisältöä, joka voi hyödyntää Power BI -palvelua.

### <a name="get-an-authorization-code-from-azure-ad"></a>Valtuutuskoodin hankkiminen Azure AD:stä

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
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

Kun olet muodostanut kyselymerkkijonon, ohjaa uudelleen **Azure AD:hen** saadaksesi **valtuutuskoodin**.  Alla on valmis C#-menetelmä **valtuutuskoodia** koskevan kyselymerkkijonon muodostamiseen ja ohjaamiseen uudelleen **Azure AD:hen**. Kun sinulla on valtuutuskoodi, saat **käyttöoikeustietueen** käyttämällä **valtuutuskoodia**.

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
        {"redirect_uri", "http://localhost:13526/Redirect"}
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

Sinulla pitäisi nyt olla valtuutuskoodi Azure AD:stä. Kun **Azure AD** tekee uudelleenohjauksen takaisin verkkosovellukseen **varmennuskoodilla**, voit käyttää **valtuutuskoodia** saadaksesi käyttöoikeustietueen. Alla on C#-esimerkki, jota voit käyttää uudelleenohjaussivullasi sekä default.aspx-sivusi tapahtumassa Page_Load.

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

Tätä lähestymistapaa käytetään yleensä sellaisia ISV-tyyppisiä sovelluksia varten, joissa sovellus omistaa tietojen käyttöoikeudet. Käyttäjät eivät välttämättä ole Power BI -käyttäjiä, ja sovellus hallitsee loppukäyttäjien todentamista ja käyttöoikeuksia.

### <a name="access-token-with-a-master-account"></a>Käyttöoikeustietue ja päätili

Tässä tavassa käytetään yksittäistä *päätiliä*, joka on Power BI Pro -käyttäjä. Tämän tilin tunnistetiedot tallennetaan sovellukseen. Sovellus todennetaan Azure AD:stä kyseisten tallennettujen tunnistetietojen avulla. Alla oleva esimerkkikoodi on peräisin [sovellus omistaa tiedot -mallista](https://github.com/guyinacube/PowerBI-Developer-Samples)

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

* Lataa [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727) Jos kohtaat ”” AuthenticationContext' ei sisällä määritelmää 'AcquireToken' ja ei voi käyttää 'AcquireToken' hyväksymällä ensimmäisen argumentin tyyppi ” AuthenticationContext' löydy (Voit puuttuu using direktiivin tai kokoonpanoviittausta?) ”virhe.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun sinulla on käyttöoikeustietue, voit kutsua Power BI REST -ohjelmointirajapinnan upottamaan sisältöä. Jos haluat lisätietoja sisällön upottamisesta, lue ohjeartikkeli [Power BI -sisällön upottaminen](embed-sample-for-customers.md#embed-content-within-your-application).

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)