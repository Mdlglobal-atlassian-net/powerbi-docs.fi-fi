---
title: Tietojoukon luominen
description: Vaihe vaiheelta – Tietojen työntäminen tietojoukkoon – Tietojoukon luominen Power BI:ssä
author: rkarlin
ms.author: rkarlin
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 3b0a1f2234490ae1c887b77395d87e41deb3319d
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875476"
---
# <a name="step-3-create-a-dataset-in-power-bi"></a>Vaihe 3: Tietojoukon luominen Power BI:ssä
Tämä artikkeli on osa vaiheittaisia ohjeita, joilla [tiedot työnnetään tietojoukkoon](walkthrough-push-data.md).

Tietojen tietojoukkoon työntämisen **vaiheessa 2**, [Todennustunnuksen hankkiminen](walkthrough-push-data-get-token.md), sait tunnuksen **Microsoft Azure Active Directoryyn** todentamista varten. Tässä vaiheessa tunnusta käytetään [Julkaise tietojoukko](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) -toiminnon kutsumiseen.

REST-resurssin kutsumista varten käytät URL-osoitetta, jossa resurssi sijaitsee, ja lähetät JavaScript Object Notation (JSON) -merkkijonon, joka kuvailee tietojoukon, Power BI -palvelun resurssiin. REST-resurssi yksilöi käsiteltävän Power BI -palvelun osan. Tietojen työntämiseksi tietojoukkoon kohderesurssi on **Tietojoukko**. Tietojoukon tunnistava URL-osoite on https://api.PowerBI.com/v1.0/myorg/datasets. Jos olet työntämässä tietoja ryhmässä, URL-osoite on https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets.

Power BI:n REST-toiminnon todentamiseksi lisäät [Todennustunnuksen hankkiminen](walkthrough-push-data-get-token.md) -vaiheessa saamasi tunnuksen pyynnön otsikkoon:

Kun kutsut [Julkaise tietojoukko](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) -toiminnon, uusi tietojoukko luodaan. 

![](media/walkthrough-push-data-create-dataset/powerbi-developer-create-dataset.png)

Tietojoukko luodaan seuraavasti Power BI:ssä.

## <a name="create-a-dataset-in-power-bi"></a>Tietojoukon luominen Power BI:ssä
> [!NOTE]
> Varmista ennen aloittamista, että olet noudattanut edellisiä vaiheita [tietojen tietojoukkoon työntämisen](walkthrough-push-data.md) vaiheittaisissa ohjeissa.
> 
> 

1. Lisää [vaiheessa 2, Todennustunnuksen hankkiminen](walkthrough-push-data-get-token.md), luomassasi Konsolisovellus-projektissa tekstit **using System.Net;** ja **using System.IO;** kohtaan Program.cs.
2. Lisää kohdassa Program.cs alla oleva koodi.
3. Suorita konsolisovellus ja kirjaudu Power BI -tiliisi. **Tietojoukko luotu** pitäisi näkyä konsolin ikkunassa. Voit myös kirjautua Power BI:hin, jos haluat nähdä uuden tietojoukon.

**Esimerkki tietojen työntämisestä tietojoukkoon**

Lisää tämä koodi kohtaan Program.cs.

* Kohdassa static void Main(string[] args):
  
    ```csharp
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();
  
        //Create a dataset in Power BI
        CreateDataset();
    }
    ```
* Lisää CreateDataset()-menetelmä:
  
    ```csharp
    #region Create a dataset in Power BI
    private static void CreateDataset()
    {
        //TODO: Add using System.Net and using System.IO
  
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "POST";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        //Create dataset JSON for POST request
        string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
            "[{\"name\": \"Product\", \"columns\": " +
            "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
            "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
            "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
            "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
            "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
            "]}]}";
  
        //POST web request
        byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
        request.ContentLength = byteArray.Length;
  
        //Write JSON byte[] into a Stream
        using (Stream writer = request.GetRequestStream())
        {
            writer.Write(byteArray, 0, byteArray.Length);
  
            var response = (HttpWebResponse)request.GetResponse();
  
            Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));
  
            Console.ReadLine();
        }
    }
    #endregion
    ```

Seuraavaksi kerrotaan, miten [saat tietojoukon lisäämään rivejä Power BI -taulukkoon](walkthrough-push-data-get-datasets.md).

Alla on [Kattava koodiluettelo](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Kattava koodiluettelo

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System.Net;
using System.IO;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

            //Create a dataset in Power BI
            CreateDataset();

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


        #region Create a dataset in Power BI
        private static void CreateDataset()
        {
            //TODO: Add using System.Net and using System.IO

            string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
            //POST web request to create a dataset.
            //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
            HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
            request.KeepAlive = true;
            request.Method = "POST";
            request.ContentLength = 0;
            request.ContentType = "application/json";

            //Add token to the request header
            request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

            //Create dataset JSON for POST request
            string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                "[{\"name\": \"Product\", \"columns\": " +
                "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                "]}]}";

            //POST web request
            byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
            request.ContentLength = byteArray.Length;

            //Write JSON byte[] into a Stream
            using (Stream writer = request.GetRequestStream())
            {
                writer.Write(byteArray, 0, byteArray.Length);

                var response = (HttpWebResponse)request.GetResponse();

                Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                Console.ReadLine();
            }
        }
        #endregion
    }
}
```

[Seuraava vaihe >](walkthrough-push-data-get-datasets.md)

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojoukon hankkiminen rivien lisäämiseksi Power BI -taulukkoon](walkthrough-push-data-get-datasets.md)  
[Todennustunnuksen hankkiminen](walkthrough-push-data-get-token.md)  
[Julkaise tietojoukko](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)  
[PostDatasetInGroup](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdatasetingroup)  
[Tietojen työntäminen Power BI -raporttinäkymään](walkthrough-push-data.md)  
[Power BI REST -ohjelmointirajapinnan yleiskatsaus](overview-of-power-bi-rest-api.md)  
[Power BI:n REST-ohjelmointirajapinnan viite](https://docs.microsoft.com/rest/api/power-bi/)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

