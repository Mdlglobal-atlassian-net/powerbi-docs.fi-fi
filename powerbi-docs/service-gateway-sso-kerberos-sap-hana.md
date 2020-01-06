---
title: Kerberoksen käyttäminen kertakirjautumista (SSO) varten SAP HANAssa
description: SAP HANA -palvelimen määrittäminen ottamaan kertakirjautuminen käyttöön Power BI -palvelussa
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 9c2eb554a4e3b3ec90d3fe17145e0ec277298e1b
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "74697493"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-hana"></a>Kerberoksen käyttäminen kertakirjautumista (SSO) varten SAP HANAssa

Tässä artikkelissa kerrotaan, miten voit määrittää SAP HANA -tietolähteesi ottamaan käyttöön kertakirjautumisen Power BI -palvelusta.

> [!NOTE]
> Ennen kuin yrität päivittää SAP HANA -pohjaisen raportin, joka käyttää Kerberos-kertakirjautumista, tee sekä tässä artikkelissa kuvatut vaiheet että artikkelissa [Kerberos-kertakirjautumisen määrittäminen](service-gateway-sso-kerberos.md) kuvatut vaiheet.

## <a name="enable-sso-for-sap-hana"></a>Kertakirjautumisen ottaminen käyttöön SAP HANAssa

Ota kertakirjautuminen käyttöön SAP HANA:ssa toimimalla seuraavasti:

1. Varmista, että SAP HANA -palvelin käyttää vaadittua vähimmäisversiota, joka riippuu SAP HANA -palvelimesi ympäristön tasosta:
   - [HANA 2 SP 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
   - [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
   - [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)

2. Asenna yhdyskäytävätietokoneeseen uusin SAP HANA ODBC -ohjain. Vähimmäisversio on HANA ODBC 2.00.020.00 elokuulta 2017.

3. Varmista, että SAP HANA -palvelin on määritetty Kerberos-pohjaista kertakirjautumista varten. Katso lisätietoja SSO-kirjautumisen määrittämisestä Kerberoksen avulla SAP HANA:lle SAP HANA -suojausoppaan [Kertakirjautuminen Kerberoksen avulla](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) -kohdasta. Tutustu myös sivulla oleviin linkkeihin, erityisesti SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory.

Suosittelemme myös seuraamaan seuraavia vaiheita, jotka voivat parantaa suorituskykyä jonkin verran:

1. Etsi ja avaa seuraava määritystiedosto yhdyskäytävän asennushakemistosta: Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config.

2. Etsi ominaisuus `FullDomainResolutionEnabled` ja muuta sen arvoksi `True`.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

Sitten [Suorita Power BI -raportti](service-gateway-sso-kerberos.md#run-a-power-bi-report).

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja paikallisesta tietoyhdyskäytävästä ja DirectQuerysta on seuraavissa resursseissa:

* [Mikä paikallinen tietoyhdyskäytävä on?](/data-integration/gateway/service-gateway-onprem)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
