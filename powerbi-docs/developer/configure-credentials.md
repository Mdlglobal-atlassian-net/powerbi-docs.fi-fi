---
title: Tunnistetietojen määrittäminen Power BI:hin ohjelmallisesti
description: Tunnistetietojen määrittäminen Power BI:hin ohjelmallisesti automatisointitarkoituksessa
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: 222edd901409fa71d98308f27407838d54564834
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836588"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>Tunnistetietojen määrittäminen Power BI:hin ohjelmallisesti

Voit määrittää Power BI:hin tunnistetiedot ohjelmallisesti noudattamalla seuraavia ohjeita.

## <a name="configure-a-credential-flow-for-data-sources"></a>Tunnistetietojen saaminen tietolähteistä

1. Hae tietojoukon tietolähteet käyttämällä kutsua [Nouda tietolähteet](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasourcesingroup). Vastausten viestirungossa esitetään kunkin tietolähteen tyyppi, yhteyden tiedot, yhdyskäytävä ja tietolähteen tunnus.

    ```csharp
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First(); // select a datasource
    ```

2. Koosta tunnistemerkkijono tunnistetietojen tyypin perusteella artikkelin [Tietolähde-esimerkkien päivittäminen](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) mukaisesti.

    ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

3. Luo tunnistetiedot loppuun muiden tietojen osalta.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    credentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.None,
                    PrivacyLevelEnum.Private);
    ```

4. Lisää tunnistetiedot järjestelmään käyttämällä kutsua [Päivitä tietolähde](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) ja käyttämällä vaiheessa 1 noudettua yhdyskäytävää ja tietolähteen tunnusta sekä vaiheessa 4 luotuja tietoja.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

### <a name="expired-on-premises-data-source-credentials-flow"></a>Tunnistetietojen saaminen vanhentuneesta paikallisesta tietolähteestä

1. [Noudata edellisen esimerkin vaiheita 1 ja 2](#configure-a-credential-flow-for-data-sources).

2. Nouda yhdyskäytävän julkinen avain käyttämällä kutsua [Nouda yhdyskäytävä](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways).

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. Salaa tunnistemerkkijono yhdyskäytävän julkisella avaimella. Erilaisten yhdyskäytäväversioiden julkisten avainten koot voivat vaihdella.
    
    Katso esimerkki SDK-koodista, joka on saatavilla PowerBI-CSharp GitHub -säilöstä, [PowerBI-CSharp/sdk/PowerBI.Api/Extensions/V2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2).
    * [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
    * [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
    * [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
    * [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)

4. Luo salatuilla tunnistetiedoilla muut tunnistetietojen tarvitsemat tiedot.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    encryptedCredentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.RSA-OAEP,
                    PrivacyLevelEnum.Private);
    ```

5. Lisää tunnistetiedot järjestelmään käyttämällä kutsua [Päivitä tietolähde](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource).

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>Uuden tietolähteen määrittäminen tietoyhdyskäytävälle

1. Asenna koneellesi [paikallinen tietoyhdyskäytävä](https://powerbi.microsoft.com/gateway/).

2. Nouda yhdyskäytävän tunnus ja julkinen avain käyttämällä kutsua [Nouda yhdyskäytävät](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways).

    ```csharp
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First(); // select a gateway
    ```

3. Luo muut tunnistetietojen tarvitsemat tiedot edellisessä esimerkissä annettujen ohjeiden mukaisesti käyttämällä yhdyskäytävän julkista avainta, joka noudettiin vaiheessa [Tunnistetietojen saaminen vanhentuneesta paikallisesta tietolähteestä](#expired-on-premises-data source-credentials-flow-on-premises-data-gateway).

4. Pyynnön rungon luominen

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

## <a name="troubleshooting"></a>Vianmääritys

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>Yhdyskäytävää ja tietolähteen tunnusta ei löydy Nouda tietolähteet ‑kutsua käyttämällä

Tämä ongelma tarkoittaa, ettei tietojoukkoa ole sidottu mihinkään yhdyskäytävään. Aina kun luodaan uusi tietojoukko, kutakin pilviyhteyttä varten luodaan automaattisesti käyttäjän pilviyhdyskäytävään tietolähde, jolla ei ole tunnistetietoja. Tähän yhdyskäytävään tallennetaan pilviyhteyksien tunnistetiedot.

Kun olet luonut tietojoukon, se sidotaan automaattisesti sopivaan yhdyskäytävään, joka sisältää vastaavat tietolähteet kaikkien yhteyksien osalta. Jos sopivaa yhdyskäytävää ei ole saatavilla tai käytettävissä on useita vaihtoehtoja, automaattinen sitominen epäonnistuu.

Luo paikalliset tietolähteet, jos sellaisia puuttuu, ja sido tietojoukko yhdyskäytävään manuaalisesti käyttämällä [Sido yhdyskäytävään](https://docs.microsoft.com/rest/api/power-bi/datasets/bindtogateway) ‑toimintoa.

Voit etsiä sitomiseen soveltuvat yhdyskäytävät [Etsi yhdyskäytävät](https://docs.microsoft.com/rest/api/power-bi/datasets/discovergateways) ‑toiminnolla.