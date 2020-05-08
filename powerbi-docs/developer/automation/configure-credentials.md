---
title: Tunnistetietojen määrittäminen Power BI:hin ohjelmallisesti
description: Tunnistetietojen määrittäminen ohjelmallisesti Power BI:n automatisoinnissa
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/23/2020
ms.openlocfilehash: bd7758be32d18fd3be06a7847edc7795c2b5f9e1
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80114769"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>Tunnistetietojen määrittäminen Power BI:hin ohjelmallisesti

Voit määrittää Power BI:hin tunnistetiedot ohjelmallisesti noudattamalla seuraavia ohjeita.

## <a name="update-credentials-flow-for-data-sources"></a>Tietolähteiden tunnistetietojen saamisen päivittäminen

1. Hae tietojoukon tietolähteet käyttämällä kutsua [Nouda tietolähteet](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasourcesingroup). Kunkin tietolähteen vastausten viestirungossa on sen tyyppi, yhteyden tiedot, yhdyskäytävä ja tietolähteen tunnus.

    ```csharp
    // Select a datasource
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First();
    ```

2. Koosta tunnistemerkkijono tunnistetietojen tyypin perusteella artikkelin [Tietolähde-esimerkkien päivittäminen](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) mukaisesti.

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    ```csharp
    var credentials =  new BasicCredentials(username: "username", password :"*****");
    ```

    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

     ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

    ---

2. Nouda yhdyskäytävän julkinen avain käyttämällä kutsua [Nouda yhdyskäytävä](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways).

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. Salaa tunnistetiedot.

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    ```csharp
    var credentialsEncryptor = new AsymmetricKeyEncryptor(gateway.publicKey);
    ```

    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

    Salaa tunnistemerkkijono vaiheessa 2 noudetulla yhdyskäytävän julkisella avaimella. Erilaisten yhdyskäytäväversioiden julkisten avainten koot voivat vaihdella. Katso seuraavat SDK-koodin esimerkit, jotka ovat saatavilla [PowerBI-CSharp GitHub -säilöstä](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions):
    * [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AsymmetricKeyEncryptor.cs)
    * [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/Asymmetric1024KeyEncryptionHelper.cs)
    * [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AsymmetricHigherKeyEncryptionHelper.cs)
    * [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AuthenticatedEncryption.cs) 

    ---  

4. Luo salatuilla tunnistetiedoilla muut tunnistetietojen tarvitsemat tiedot.

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    Käytä AssymetricKeyEncriptor-luokkaa **vaiheessa 3** noudetun julkisen avaimen kanssa.

    ```csharp
    var credentialDetails = new CredentialDetails(
            credentials,
            PrivacyLevel.Private,
            EncryptedConnection.Encrypted,
            credentialsEncryptor);
    ```


    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

    ```csharp
    var credentialDetails = new CredentialDetails(
            credentials,
            CredentialTypeEnum.Basic,
            EncryptedConnectionEnum.Encrypted,
            EncryptionAlgorithmEnum.None,
            PrivacyLevelEnum.Private);
    ```

    ---

5. Lisää tunnistetiedot järjestelmään käyttämällä kutsua [Päivitä tietolähde](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource).

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>Uuden tietolähteen määrittäminen tietoyhdyskäytävälle

1. Asenna koneellesi [paikallinen tietoyhdyskäytävä](https://powerbi.microsoft.com/gateway/).

2. Nouda yhdyskäytävän tunnus ja julkinen avain käyttämällä kutsua [Nouda yhdyskäytävät](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways).

    ```csharp
    // Select a gateway
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First();
    ```

3. Luo tunnistetiedot samalla tavalla kuin kohdassa [Tietolähteiden tunnistetietojen saamisen päivittäminen](#update-credentials-flow-for-data-sources) käyttämällä **vaiheessa 2** noudettua yhdyskäytävän julkista avainta.

4. Luo pyynnön runko.

    ```csharp
    var request = new PublishDatasourceToGatewayRequest(
            dataSourceType: "SQL",
            connectionDetails: "{\"server\":\"myServer\",\"database\":\"myDatabase\"}",
            credentialDetails: credentialDetails,
            dataSourceName: "my sql datasource");
    ```

5. Kutsu [Luo tietolähde](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) ‑ohjelmointirajapintaa.

    ```csharp
    pbiClient.Gateways.CreateDatasource(gateway.Id, request);
    ```

## <a name="credential-types"></a>Tunnistetietotyypit

Kun kutsut [tietolähteen luomista](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) tai [tietolähteen päivitystä](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)**yrityksen paikallisessa yhdyskäytävässä**[Power BI REST API:n](https://docs.microsoft.com/rest/api/power-bi/) avulla, tunnistetietoarvon täytyy olla salattu yhdyskäytävän julkisella avaimella.

>[!NOTE]
>.NET SDK v3 voi myös suorittaa alla luetellut .NET SDK v2 -esimerkit.

### <a name="windows-and-basic-credentials"></a>Windows ja perustunnistetiedot

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
// Windows credentials
var credentials = new WindowsCredentials(username: "john", password: "*****");

// Or

// Basic credentials
var credentials = new BasicCredentials(username: "john", password: "*****");

var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

---

### <a name="key-credentials"></a>Avaintunnistetiedot

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new KeyCredentials("TestKey");
var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

---

**OAuth2-tunnistetiedot**

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new OAuth2Credentials("TestToken");
var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```

---

**avaintunnistetiedot**

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new AnonymousCredentials();
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.NotEncrypted);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":\"\"}";
```

---

## <a name="troubleshooting"></a>Vianmääritys

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>Yhdyskäytävää ja tietolähteen tunnusta ei löydy Nouda tietolähteet ‑kutsua käyttämällä

Tämä ongelma tarkoittaa, ettei tietojoukkoa ole sidottu mihinkään yhdyskäytävään. Aina kun uusi tietojoukko luodaan, kutakin pilviyhteyttä varten luodaan automaattisesti käyttäjän pilviyhdyskäytävään tietolähde, jolla ei ole tunnistetietoja. Tähän yhdyskäytävään tallennetaan pilviyhteyksien tunnistetiedot.

Kun olet luonut tietojoukon, se sidotaan automaattisesti sopivaan yhdyskäytävään, joka sisältää vastaavat tietolähteet kaikkien yhteyksien osalta. Jos sopivaa yhdyskäytävää ei ole saatavilla tai käytettävissä on useita vaihtoehtoja, automaattinen sitominen epäonnistuu.

Jos käytät paikallisia tietojoukkoja, luo puuttuvat paikalliset tietolähteet ja sido tietojoukko yhdyskäytävään manuaalisesti käyttämällä [Sido yhdyskäytävään](https://docs.microsoft.com/rest/api/power-bi/datasets/bindtogateway) ‑toimintoa.

Voit etsiä sitomiseen soveltuvat yhdyskäytävät [Etsi yhdyskäytävät](https://docs.microsoft.com/rest/api/power-bi/datasets/discovergateways) ‑toiminnolla.