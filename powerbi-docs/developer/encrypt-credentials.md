---
title: Tunnistetietojen salaaminen
description: Ohjeet paikallisten yhdyskäytävätietolähteiden tunnistetietojen salaamiseen
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: b1fc4a505aa993c606743eefb6e8fb8c0379317d
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836618"
---
# <a name="encrypt-credentials"></a>Tunnistetietojen salaaminen

Kun kutsut [tietolähteen luomista](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) tai [tietolähteen päivitystä](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)**yrityksen paikallisessa yhdyskäytävässä**[Power BI REST API:n](https://docs.microsoft.com/rest/api/power-bi/) avulla, tunnistetietoarvon täytyy olla salattu yhdyskäytävän julkisella avaimella.

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

Salaa tunnistetiedot-arvo käyttämällä yhdyskäytävän julkista avainta. Erilaisten yhdyskäytäväversioiden julkisten avainten koot voivat vaihdella.

Katso esimerkki SDK-koodista, joka on saatavilla PowerBI-CSharp GitHub -säilöstä, [PowerBI-CSharp/sdk/PowerBI.Api/Extensions/V2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2).

- [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
- [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
- [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
- [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)