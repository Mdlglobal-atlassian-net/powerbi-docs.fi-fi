---
title: Tietojoukon hakeminen rivien lisäämiseksi
description: Vaiheittaiset ohjeet tietojen työntämiseen – tietojoukon hankkiminen rivien lisäämiseksi Power BI -taulukkoon
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: fcb06e2b61fc1beb6ff5409256e5c54e68bb8f34
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
ms.locfileid: "30973137"
---
# <a name="step-4-get-a-dataset-to-add-rows-into-a-power-bi-table"></a>Vaihe 4: Tietojoukon hankkiminen rivien lisäämiseksi Power BI -taulukkoon
Tämä artikkeli on osa vaiheittaisia ohjeita, joilla [tiedot työnnetään tietojoukkoon](walkthrough-push-data.md).

Tietojen tietojoukkoon työntämisen **vaiheessa 3**, [Tietojoukon luominen Power BI:ssä](walkthrough-push-data-create-dataset.md), kutsuit [Luo tietojoukko](https://msdn.microsoft.com/library/mt203562.aspx) -toiminnon tietojoukon luomiseksi Power BI:ssä. Tässä vaiheessa käytät [Nouda tietojoukkoja](https://msdn.microsoft.com/library/mt203567.aspx) -toimintoa ja Newtonsoft.Json-komentoa tietojoukon tunnuksen saamiseksi. Lisää rivejä tietojoukkoon käyttämällä vaiheen 4 tietojoukon tunnusta. 

Jotta voit työntää tietoja Power BI:n tietojoukkoon, sinun on viitattava tietojoukossa olevaan taulukkoon. Jotta voit viitata tietojoukossa olevaan taulukkoon, sinun on saatava **tietojoukon tunnus**. Saat **tietojoukon tunnuksen** käyttämällä [Nouda tietojoukko](https://msdn.microsoft.com/library/mt203567.aspx) -toimintoa. **Nouda tietojoukko** -toiminto palauttaa JSON-merkkijonon, joka sisältää luettelon kaikista Power BI:n tietojoukoista. Suositeltu tapa JSON-merkkijonon sarjoituksen poistamiseen on [Newtonsoft.Json](http://www.newtonsoft.com/json).

Saat tietojoukon seuraavasti.

## <a name="get-a-power-bi-dataset"></a>Power BI:n tietojoukon hankkiminen
> **HUOMAUTUS**: varmista ennen aloittamista, että olet noudattanut edellisiä vaiheita [tietojen tietojoukkoon työntämisen](walkthrough-push-data.md) vaiheittaisissa ohjeissa.
> 
> 

1. Asenna Newtonsoft.Json NuGet -paketti konsolisovellusprojektissa, jonka loit vaiheessa 2: Vaiheittaiset ohjeet tietojen työntämiseen, [Todennustunnuksen hankkiminen](walkthrough-push-data-get-token.md). Asenna paketti seuraavasti:
   
     a. Valitse Visual Studio 2015:ssä **Tools** > **NuGet Package Manager** > **Package Manager Console**.
   
     b. Syötä **Package Manager Consolessa** Install-Package Newtonsoft.Json.
2. Kun paketti on asennettu, lisää teksti **using Newtonsoft.Json;** kohtaan Program.cs.
3. Lisää kohdassa Program.cs alla oleva koodi, jotta saat **tietojoukon tunnuksen**.
4. Suorita konsolisovellus ja kirjaudu Power BI -tiliisi. Konsoli-ikkunassa pitäisi näkyä **Tietojoukon tunnus:** ja sen jälkeen tunnus.

**Esimerkki tietojoukon noutamisesta**

Lisää tämä koodi kohtaan Program.cs.

* Kohdassa static void Main(string[] args):
  
  ```
  static void Main(string[] args)
  {
  
    //Get an authentication access token
    token = GetToken();
  
    //Create a dataset in Power BI
    CreateDataset();
  
    //Get a dataset to add rows into a Power BI table
    string datasetId = GetDataset();
  }
  ```
* Lisää GetDatset()-menetelmä:
  
  ```
    #region Get a dataset to add rows into a Power BI table
    private static string GetDataset()
    {
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "GET";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        string datasetId = string.Empty;
        //Get HttpWebResponse from GET request
        using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get StreamReader that holds the response stream
            using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
            {
                string responseContent = reader.ReadToEnd();
  
                //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                //and add using Newtonsoft.Json
                var results = JsonConvert.DeserializeObject<dynamic>(responseContent);
  
                //Get the first id
                datasetId = results["value"][0]["id"];
  
                Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                Console.ReadLine();
  
                return datasetId;
            }
        }
    }
    #endregion
  ```

Seuraavaksi kerrotaan, miten [voit lisätä rivejä Power BI -taulukkoon](walkthrough-push-data-add-rows.md).

Alla on [Kattava koodiluettelo](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Kattava koodiluettelo
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;
    using Newtonsoft.Json;

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

                //Get a dataset to add rows into a Power BI table
                string datasetId = GetDataset();

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
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

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

            #region Get a dataset to add rows into a Power BI table
            private static string GetDataset()
            {
                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "GET";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                string datasetId = string.Empty;
                //Get HttpWebResponse from GET request
                using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
                {
                    //Get StreamReader that holds the response stream
                    using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                    {
                        string responseContent = reader.ReadToEnd();

                        //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                        //and add using Newtonsoft.Json
                        var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                        //Get the first id
                        datasetId = results["value"][0]["id"];

                        Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                        Console.ReadLine();

                        return datasetId;
                    }
                }
            }
            #endregion
        }
    }

[Seuraava vaihe >](walkthrough-push-data-add-rows.md)

## <a name="next-steps"></a>Seuraavat vaiheet
[Rivien lisääminen Power BI -taulukkoon](walkthrough-push-data-add-rows.md)  
[Newtonsoft.Json](http://www.newtonsoft.com/json)  
[Nouda tietojoukot](https://msdn.microsoft.com/library/mt203567.aspx)  
[Tietojen työntäminen Power BI:hin](walkthrough-push-data.md)  
[Power BI:n REST-ohjelmointirajapinnan yleiskatsaus](overview-of-power-bi-rest-api.md)  
[Power BI:n REST-ohjelmointirajapinnan viite](https://msdn.microsoft.com/library/mt147898.aspx)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

