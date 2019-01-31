---
title: Todennustunnuksen hankkiminen
description: Vaiheittaiset ohjeet tietojen työntämiseen – todennustunnuksen hankkiminen
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 1381706801a1a817927c891fcc205950cef24cbb
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/31/2019
ms.locfileid: "55430851"
---
# <a name="step-2-get-an-authentication-access-token"></a>Vaihe 2: Todennustunnuksen hankkiminen
Tämä artikkeli on osa vaiheittaisia ohjeita, joilla [tiedot työnnetään tietojoukkoon](walkthrough-push-data.md).

Tietojen tietojoukkoon työntämisen **vaiheessa 1**, [Sovelluksen Azure AD -rekisteröinti](walkthrough-push-data-register-app-with-azure-ad.md), asiakassovellus rekisteröitiin Azure AD:ssa. Tässä vaiheessa hankitaan todennustunnus. Power BI -sovellukset on integroitu **Azure AD:hen**, jotta sovellukselle voidaan tarjota suojattu kirjautuminen ja käyttöoikeuksien myöntäminen. Tunnuksen avulla voit todentautua **Azure AD:ssa** ja käyttää Power BI:n resursseja.

Voit hankkia todennustunnuksen seuraavasti.

## <a name="get-an-authentication-access-token"></a>Todennustunnuksen hankkiminen
> **HUOMAUTUS**: Varmista ennen aloittamista, että olet noudattanut edellisiä vaiheita [tietojen tietojoukkoon työntämisen](walkthrough-push-data.md) vaiheittaisissa ohjeissa.
> 
> 

1. Luo Visual Studio 2015:ssä **Konsolisovellus**-projekti.
2. Asenna [Azure AD -todentamiskirjasto .NET NuGet -paketille](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/). Jos haluat saada todentamisen suojaustunnuksen .NET-sovelluksessa, käytä tätä pakettia. Asenna paketti seuraavasti:
   
     a. Valitse Visual Studio 2015:ssä **Tools** > **NuGet Package Manager** > **Package Manager Console**.
   
     b. Kirjoita **Package Manager Consolessa** Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612.
3. Lisää alla oleva koodi luokkaan Program {...}.
4. Korvaa "{ClientID}" sovellusta rekisteröidessäsi saamallasi **Client ID** -tunnuksella. Katso [Sovelluksen Azure AD -rekisteröinti](walkthrough-push-data-register-app-with-azure-ad.md).
5. Kun olet asentanut Microsoft.IdentityModel.Clients.ActiveDirectory-paketin, lisää **using Microsoft.IdentityModel.Clients.ActiveDirectory;** kohtaan Program.cs.
6. Suorita konsolisovellus ja kirjaudu Power BI -tiliisi. Tunnusmerkkijonon pitäisi näkyä konsoli-ikkunassa.

**Esimerkkikoodi todentamisen suojaustunnuksen saamista varten**

Lisää tämä koodi kohtaan Program {...}.

* Kutsutoimintojen tunnusmuuttuja:
  
  ```
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* Kohdassa static void Main(string[] args):
  
  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Lisää GetToken()-menetelmä:

```
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

Kun olet saanut todennustunnuksen, voit kutsua mitä tahansa Power BI:n toimintoa. Seuraavaksi näytetään, miten voit kutsua [Julkaise tietojoukko](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) -toiminnon ja luoda tietojoukon tietojen työntämiseksi raporttinäkymään.

Seuraavassa vaiheessa näytetään, miten voit [luoda tietojoukon Power BI:ssä](walkthrough-push-data-create-dataset.md).

Alla on [Kattava koodiluettelo](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Kattava koodiluettelo
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

        }
    }


[Seuraava vaihe >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojoukon luominen Power BI:ssä](walkthrough-push-data-create-dataset.md)  
[Sovelluksen Azure AD -rekisteröinti](walkthrough-push-data-register-app-with-azure-ad.md)  
[Azure AD -todentamiskirjasto .NET NuGet -paketille](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Tietojen työntäminen Power BI -tietojoukkoon](walkthrough-push-data.md)  
[Power BI:n REST-ohjelmointirajapinnan yleiskatsaus](overview-of-power-bi-rest-api.md)  
[Power BI:n REST-ohjelmointirajapinnan viite](https://docs.microsoft.com/rest/api/power-bi/)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

