---
title: SAML:n käyttäminen kertakirjautumiseen (SSO) paikallisiin tietolähteisiin
description: Määritä yhdyskäytävä Security Assertion Markup Languagen (SAML) avulla kertakirjautumisen (SSO) käyttöön ottamiseksi Power BI:stä paikallisiin tietolähteisiin.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
ms.openlocfilehash: 8762e575574b717965ac55d4cf32a5c925c298ab
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507780"
---
# <a name="use-security-assertion-markup-language-saml-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Security Assertion Markup Languagen (SAML) käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin

Käytä [Security Assertion Markup Languagea (SAML)](https://www.onelogin.com/pages/saml) ottaaksesi saumattoman kertakirjautumisen käyttöön. Kun otat kertakirjautumisen käyttöön, Power BI -raportit ja -koontinäytöt voivat helposti päivittää tiedot, jotka ovat peräisin paikallisista lähteistä.

## <a name="supported-data-sources"></a>Tuetut tietolähteet

Tuemme tällä hetkellä SAP HANA:a SAML:n kanssa. Lisätietoja kertakirjautumisen määrittämisestä SAP HANA:ssa SAML:n avulla on aiheessa [SAML SSO for BI Platform to HANA (SAML-kertakirjautuminen BI-alustasta HANA:an)](https://wiki.scn.sap.com/wiki/display/SAPHANA/SAML+SSO+for+BI+Platform+to+HANA) SAP HANA -dokumentaatiossa.

Tuemme muita tietolähteitä [Kerberoksen](service-gateway-sso-kerberos.md) avulla.

## <a name="configuring-the-gateway-and-data-source"></a>Yhdyskäytävän ja tietolähteen määrittäminen

Jotta voit käyttää SAML:a, luo ensin varmenne SAML-tunnistetietopalvelua varten ja yhdistä sitten Power BI -käyttäjä käyttäjätietoihin.

1. Luo varmenne. Varmista, että käytät SAP HANA -palvelimen täydellistä toimialuenimeä kun täytät *kutsumanimen*. Varmenne vanhenee 365 päivässä.

    ```
    openssl req -newkey rsa:2048 -nodes -keyout samltest.key -x509 -days 365 -out samltest.crt
    ```

1. Napsauta SAP HANA Studiossa SAP HANA -palvelintasi hiiren kakkospainikkeella ja siirry kohtaan **Tietoturva** > **Avaa tietoturvakonsoli** > **SAML-tunnistetietopalvelu** > **OpenSSL-salauskirjasto**.

1. Valitse **Tuo**, etsi samltest.crt-tiedosto ja tuo se.

    ![Tunnistetietopalvelut](media/service-gateway-sso-saml/identity-providers.png)

1. Valitse SAP HANA Studiossa **Tietoturva**kansio.

    ![Tietoturvakansio](media/service-gateway-sso-saml/security-folder.png)

1. Laajenna **Käyttäjät** ja valitse sitten käyttäjä, johon haluat yhdistää Power BI -käyttäjäsi.

1. Valitse **SAML** ja sitten **Määritä**.

    ![SAML:n määrittäminen](media/service-gateway-sso-saml/configure-saml.png)

1. Valitse tunnistetietopalvelu, jonka loit vaiheessa 2. Syötä kohtaan **Ulkoiset käyttäjätiedot** Power BI -käyttäjän täydellinen käyttäjätunnus ja valitse sitten **Lisää**.

    ![Tunnistetietopalvelun valitseminen](media/service-gateway-sso-saml/select-identity-provider.png)

Vahvista seuraavaksi asennus *SAML-vahvistuksella* [xmlsec1-työkalun](http://sgros.blogspot.com/2013/01/signing-xml-document-using-xmlsec1.html) avulla.

1. Tallenna alla oleva vahvistus nimellä assertion-template.xml. Vaihda \<MyUserId\>:n tilalle saman Power BI -käyttäjän täydellinen käyttäjätunnus, jota käytit vaiheessa 7.

    ```xml
    <?xml version="1.0" encoding="UTF-8" ?>
    <saml2:Assertion ID="Assertion12345789" IssueInstant="2015-07-16T04:47:49.858Z" Version="2.0" xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">
      <saml2:Issuer></saml2:Issuer> 
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
        <SignedInfo>
          <CanonicalizationMethod Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315"/>
          <SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#rsa-sha1"/>
          <Reference URI="">
            <Transforms>
              <Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/>
              <Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>
            </Transforms>
            <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
            <DigestValue />
          </Reference>
        </SignedInfo>
        <SignatureValue />
        <KeyInfo>
          <X509Data />
        </KeyInfo>
      </Signature>
      <saml2:Subject>
        <saml2:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified"><MyUserId></saml2:NameID>
      </saml2:Subject>
      <saml2:Conditions NotBefore="2010-01-01T00:00:00Z" NotOnOrAfter="2050-01-01T00:00:00Z"/>
    </saml2:Assertion>
    ```

1. Suorita seuraava komento. saltest.key ja samltest.crt ovat avain ja varmenne, jotka loit vaiheessa 1.

    ```
    xmlsec1 --sign --privkey-pem samltest.key, samltest.crt --output signed.xml assertion-template.xml
    ```

1. Avaa SQL-konsoli-ikkuna SAP HANA Studiossa ja suorita seuraava komento. Korvaa \<SAMLAssertion\> edellisen vaiheen xml-tiedoston sisällöllä.

    ```SQL
    CONNECT WITH SAML ASSERTION '<SAMLAssertion>'
    ```

Jos kysely onnistuu, se tarkoittaa, että SAP HANA SAML SSO -määrityksesi on onnistunut.

Nyt kun olet onnistuneesti määrittänyt varmenteen ja käyttäjätiedot, muunna varmenne pfx-muotoon ja määritä yhdyskäytäväkone käyttämään varmennetta.

1. Voit muuntaa varmenteen pfx-muotoon suorittamalla seuraavan komennon.

    ```
    openssl pkcs12 -inkey samltest.key -in samltest.crt -export -out samltest.pfx
    ```

1. Kopioi pfx-tiedosto yhdyskäytäväkoneeseen:

    1. Kaksoisnapsauta samltest.pfx-tiedostoa ja valitse sitten **Paikallinen tietokone** > **Seuraava**.

    1. Anna salasana ja valitse sitten **Seuraava**.

    1. Valitse **Sijoita kaikki varmenteet seuraavaan paikkaan** ja valitse sitten **Selaa** > **Henkilökohtainen** > **OK**.

    1. Valitse **Seuraava** ja sitten **Valmis**.

    ![Varmenteen tuonti](media/service-gateway-sso-saml/import-certificate.png)

1. Myönnä yhdyskäytävän palvelutilille käyttöoikeus varmenteen yksityisavaimeen:

    1. Suorita yhdyskäytäväkoneessa Microsoft Management Console (MMC).

        ![MMC:n suorittaminen](media/service-gateway-sso-saml/run-mmc.png)

    1. Kohdassa **Tiedosto**, valitse **Lisää/poista laajennus**.

        ![Laajennuksen lisääminen](media/service-gateway-sso-saml/add-snap-in.png)

    1. Valitse **Varmenteet** > **Lisää** ja valitse sitten **Tietokonetili** > **Seuraava**.

    1. Valitse **Paikallinen tietokone** > **Valmis** > **OK**.

    1. Laajenna **Varmenteet** > **Henkilökohtainen** > **Varmenteet** ja etsi haluamasi varmenne.

    1. Napsauta varmennetta hiiren kakkospainikkeella ja siirry kohtaan **Kaikki tehtävät** > **Yksityisten avainten hallinta**.

        ![Yksityisten avainten hallinta](media/service-gateway-sso-saml/manage-private-keys.png)

    1. Lisää yhdyskäytävän palvelutili luetteloon. Tili on oletusarvoisesti **NT SERVICE\PBIEgwService.** Voit selvittää, mitä tili suorittaa yhdyskäytäväpalvelua suorittamalla **services.msc** ja etsimällä **Paikallinen tietoyhdyskäytävä -palvelun**.

        ![Yhdyskäytäväpalvelu](media/service-gateway-sso-saml/gateway-service.png)

Lopuksi seuraa näitä ohjeita lisätäksesi varmenteen allekirjoituksen yhdyskäytävän määritykseen.

1. Suorita seuraava PowerShell-komento, jotta saat luettelon tietokoneessasi olevista varmenteista.

    ```powershell
    Get-ChildItem -path cert:\LocalMachine\My
    ```
1. Kopioi luomasi varmenteen allekirjoitus.

1. Siirry yhdyskäytävän hakemistoon, joka on oletusarvoisesti C:\Program Files\On-premises data gateway.

1. Avaa tiedosto PowerBI.DataMovement.Pipeline.GatewayCore.dll.config ja etsi osio nimeltä \*SapHanaSAMLCertThumbprint\*. Liitä kopioimasi allekirjoitus.

1. Käynnistä yhdyskäytäväpalvelu uudelleen.

## <a name="running-a-power-bi-report"></a>Power BI -raportin suorittaminen

Nyt voit käyttää Power BI:n **yhdyskäytävän hallintasivua** tietolähteen määrittämiseen. Ota sen **Lisäasetukset**-kohdassa kertakirjautuminen käyttöön. Sitten voit julkaista kyseiseen tietolähteeseen liittyvät raportit ja tietojoukot.

![Lisäasetukset](media/service-gateway-sso-saml/advanced-settings.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja **paikallisesta tietoyhdyskäytävästä** ja **DirectQuerystä** on seuraavissa resursseissa:

* [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)