---
title: Kerberoksen käyttäminen kertakirjautumista (SSO) varten SAP HANAssa
description: SAP HANA -palvelimen määrittäminen ottamaan kertakirjautuminen käyttöön Power BI -palvelussa
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 4e94781b3a424e894e0f0e2209ec48efb25c5db5
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/18/2019
ms.locfileid: "71106304"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-hana"></a>Kerberoksen käyttäminen kertakirjautumista (SSO) varten SAP HANAssa

Tässä artikkelissa kerrotaan, miten voit määrittää SAP HANA -palvelimesi ottamaan käyttöön kertakirjautumisen Power BI -palvelusta.

> [!NOTE]
> Suorita tässä artikkelissa olevat vaiheet [Kerberos-kertakirjautumisen määrittäminen](service-gateway-sso-kerberos.md) -kohdan vaiheiden lisäksi, ennen kuin yrität päivittää SAP HANA -pohjaista raporttia, jossa on käytössä Kerberos-kertakirjautuminen.

## <a name="enable-sso-for-sap-hana"></a>Kertakirjautumisen ottaminen käyttöön SAP HANAssa

Ota kertakirjautuminen käyttöön SAP HANA:ssa toimimalla seuraavasti:

* Varmista, että SAP HANA -palvelin käyttää vaadittua vähimmäisversiota, joka riippuu SAP HANA -palvelimesi ympäristön tasosta:
  * [HANA 2 SP 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
  * [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
  * [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)
* Asenna yhdyskäytävätietokoneeseen SAP:n uusin HANA ODBC -ohjain.  Vähimmäisversio on HANA ODBC 2.00.020.00 elokuulta 2017.

Varmista, että SAP HANA -palvelin on määritetty Kerberos-pohjaista kertakirjautumista varten. Katso lisätietoja SSO-kirjautumisen määrittämisestä Kerberoksen avulla SAP HANA:lle SAP HANA -suojausoppaan [Kertakirjautuminen Kerberoksen avulla](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) -kohdasta. Tutustu myös sivulla oleviin linkkeihin, erityisesti SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory.

Suosittelemme myös seuraamaan seuraavia vaiheita, jotka voivat parantaa suorituskykyä jonkin verran.

1. Etsi ja avaa seuraava määritystiedosto yhdyskäytävän asennushakemistosta: *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*.

2. Etsi *FullDomainResolutionEnabled*-ominaisuus ja muuta sen arvoksi *True*.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

Sitten [Suorita Power BI -raportti](service-gateway-sso-kerberos.md#run-a-power-bi-report).

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja **paikallisesta tietoyhdyskäytävästä** ja **DirectQuerysta** on seuraavissa resursseissa:

* [Mikä paikallinen tietoyhdyskäytävä on?](/data-integration/gateway/service-gateway-getting-started)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
