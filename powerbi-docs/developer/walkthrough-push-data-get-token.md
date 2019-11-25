---
title: Todennustunnuksen hankkiminen
description: Vaiheittaiset ohjeet tietojen työntämiseen – todennustunnuksen hankkiminen
author: KesemSharabi
ms.author: kesharab
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/29/2019
ms.openlocfilehash: 5a96085791e8bd211ebe26b2d149c7b2ad92fc2f
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/21/2019
ms.locfileid: "74264837"
---
# <a name="step-2-get-an-authentication-access-token"></a>Vaihe 2: Todennustunnuksen hankkiminen

Tämä artikkeli on toinen vaihe [Tietojen työntäminen Power BI-tietojoukkoon](walkthrough-push-data.md) -sarjassa.

Vaiheessa 1 [rekisteröit asiakassovelluksen Azure AD:ssä](walkthrough-push-data-register-app-with-azure-ad.md). Tässä vaiheessa hankitaan todennustunnus. Power BI -sovellukset on integroitu Azure Active Directoryyn, jotta sovelluksessa voidaan käyttää suojattua kirjautumista ja todennusta. Tunnuksen avulla sovellus voi todentautua Azure AD:ssä ja käyttää Power BI -resursseja.

## <a name="get-an-authentication-access-token"></a>Todennustunnuksen hankkiminen

Ennen kuin aloitat, varmista, että olet suorittanut [Tietojen työntäminen Power BI -tietojoukkoon](walkthrough-push-data.md) -sarjan [edellisen vaiheen](walkthrough-push-data-register-app-with-azure-ad.md). 

Nämä toimenpiteet edellyttävät Visual Studio 2015:ttä tai uudempaa versiota.

1. Luo Visual Studio 2015:ssä C# **Konsolisovellus** -projekti.

2. Asenna [Azure AD -todentamiskirjasto .NET NuGet -paketille](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727). .NET-sovelluksesi tarvitsee tätä pakettia todentamisen suojaustunnuksen noutamiseen. 

     a. Valitse **Työkalut** > **NuGet Package Manager** > **Package Manager Console**.

     b. Kirjoita **Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612**

     c. Lisää Program.cs:ään `using Microsoft.IdentityModel.Clients.ActiveDirectory;`.

3. Lisää näiden vaiheiden jälkeen luetteloitu koodinäyte Program.cs:ään.

4. Korvaa ”{ClientID}” **Asiakastunnuksella**, jonka sait [sarjan edellisessä artikkelissa](walkthrough-push-data-register-app-with-azure-ad.md) sovelluksen rekisteröinnin yhteydessä.

5. Suorita konsolisovellus ja kirjaudu Power BI -tilillesi. 

   Tunnusmerkkijonon pitäisi näkyä konsolin ikkunassa.

**Esimerkkikoodi todentamisen suojaustunnuksen saamista varten**

Lisää tämä koodi kohtaan Program {...}.

* Kutsutoimintojen tunnusmuuttuja: 
  
  ```csharp
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* Kohdassa static void Main(string[] args):
  
  ```csharp
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Lisää GetToken()-menetelmä:

```csharp
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.microsoftonline.net/common/";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

Kun olet saanut todennustunnuksen, voit kutsua mitä tahansa Power BI:n toimintoa.

Seuraavassa artikkelissa näytetään, miten voit [luoda tietojoukon Power BI:ssä](walkthrough-push-data-create-dataset.md).


## <a name="complete-code-listing"></a>Kattava koodiluettelo

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

        }

        #region Get an authentication access token
        private static string GetToken()
        {
            // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
            // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

            //The client id that Azure AD created when you registered your client app.
            string clientID = "{Client_ID}";

            //RedirectUri you used when you register your app.
            //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
            // You can use this redirect uri for your client app
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            //OAuth2 authority Uri
            string authorityUri = "https://login.microsoftonline.com/common/";

            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            // AcquireToken will acquire an Azure access token
            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            Console.WriteLine(token);
            Console.ReadLine();

            return token;
        }

        #endregion

    }
}
```



## <a name="next-steps"></a>Seuraavat vaiheet

[Sarjan seuraava artikkeli > Tietojoukon luominen Power BI:ssä](walkthrough-push-data-create-dataset.md).

[Power BI REST -ohjelmointirajapinnan yleiskatsaus](overview-of-power-bi-rest-api.md)  
[Power BI:n REST-ohjelmointirajapinnat](https://docs.microsoft.com/rest/api/power-bi/)  

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)