---
title: Tunnistetietojen salaaminen
description: Ohjeet paikallisten yhdyskäytävätietolähteiden tunnistetietojen salaamiseen
author: mahirdiab
manager: eligr
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 04/02/2019
ms.author: mahirdiab
ms.openlocfilehash: 79ab3731abfdf972de1ee9d40456ebb0c5ebfa62
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223509"
---
# <a name="encrypt-credentials"></a>Tunnistetietojen salaaminen
Kun kutsut [tietolähteen luomista](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) tai [tietolähteen päivitystä](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) **yrityksen paikallisessa yhdyskäytävässä** [Power BI REST API:n](https://docs.microsoft.com/rest/api/power-bi/) avulla, tunnistetietoarvon täytyy olla salattu yhdyskäytävän julkisella avaimella.

Alla olevasta koodiesimerkistä näet, miten tunnistetiedot salataan .NET:issä.

EncodeCredentials-menetelmälle alla toimitettujen tunnistetietojen täytyy olla jossain seuraavista muodoista (tunnistetietotyypin mukaan):

**perustunnistetiedot tai Windows-tunnistetiedot**
```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

**avaintunnistetiedot**
```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

**OAuth2-tunnistetiedot**
```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```


**avaintunnistetiedot**
```csharp
var credentials = "{\"credentialData\":\"\"}";
```

**salaustunnistetiedot.**
```csharp
public static class AsymmetricKeyEncryptionHelper
{

    private const int SegmentLength = 85;
    private const int EncryptedLength = 128;

    public static string EncodeCredentials(string credentials, string publicKeyExponent, string publicKeyModulus)
    {
        using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
        {
            var parameters = rsa.ExportParameters(false);
            parameters.Exponent = Convert.FromBase64String(publicKeyExponent);
            parameters.Modulus = Convert.FromBase64String(publicKeyModulus);
            rsa.ImportParameters(parameters);
            return Encrypt(credentials, rsa);
        }
    }

    private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
    {
        byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

        // Split the message into different segments, each segment's length is 85. So the result may be 85,85,85,20.
        bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0;

        int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length / SegmentLength) + 1);

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
```
