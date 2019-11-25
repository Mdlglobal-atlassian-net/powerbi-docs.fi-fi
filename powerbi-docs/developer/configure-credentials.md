---
title: Tunnistetietojen määrittäminen Power BI:hin ohjelmallisesti
description: Tunnistetietojen määrittäminen Power BI:hin ohjelmallisesti automatisointitarkoituksessa
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/25/2019
ms.openlocfilehash: 73ef45b5dbed8535b13aa557cb52929d4eea0e46
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/21/2019
ms.locfileid: "74265602"
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

3. Salaa tunnistemerkkijono yhdyskäytävän julkisella avaimella käyttämällä RSA-salausalgoritmia.

    Käytä salaukseen seuraavaa aputoimintoluokkaa:

    ```csharp
        public static class AsymmetricKeyEncryptionHelper
        {
            private const int SegmentLength = 85;
            private const int EncryptedLength = 128;

            /// <summary>

            /// Encrypts credentials using the RSA algorithm

            /// </summary>

            public static string EncodeCredentials(string credentialData, string publicKeyExponent, string publicKeyModulus)
            {
                using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
                {
                    var parameters = rsa.ExportParameters(false);

                    parameters.Exponent = Convert.FromBase64String(publicKeyExponent);

                    parameters.Modulus = Convert.FromBase64String(publicKeyModulus);

                    rsa.ImportParameters(parameters);

                    return Encrypt(credentialData, rsa);
                }
            }

             private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
            {

                byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

                // Split the message into different segments, each segment's length is 85. So, the result may be 85,85,85,20. 

                bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0; 

                int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length SegmentLength) + 1);

                byte[] encryptedData = new byte[segmentNumber * EncryptedLength];

                int encryptedDataPosition = 0;

                for (var i = 0; i < segmentNumber; i++)
                {
                    int lengthToCopy;

                    if (i == segmentNumber - 1 && hasIncompleteSegment)

                        lengthToCopy = plainTextArray.Length % SegmentLength;

                    else

                        lengthToCopy = SegmentLength;

                    var segment = new byte[lengthToCopy];

                    Array.Copy(plainTextArray, i * SegmentLength, segment, 0, lengthToCopy);

                    var segmentEncryptedResult = rsa.Encrypt(segment, true);

                    Array.Copy(segmentEncryptedResult, 0, encryptedData, encryptedDataPosition, segmentEncryptedResult.Length);

                    encryptedDataPosition += segmentEncryptedResult.Length;

                }

                return Convert.ToBase64String(encryptedData);

            }

        }

        var encryptedCredentials = AsymmetricKeyEncryptionHelper.EncodeCredentials(credentials);
    ```

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
