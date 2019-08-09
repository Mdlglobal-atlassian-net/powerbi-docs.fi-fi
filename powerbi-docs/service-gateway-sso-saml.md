---
title: SAML:n käyttäminen kertakirjautumiseen (SSO) paikallisiin tietolähteisiin
description: Määritä yhdyskäytävä Security Assertion Markup Languagen (SAML) avulla kertakirjautumisen (SSO) käyttöön ottamiseksi Power BI:stä paikallisiin tietolähteisiin.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: a240d84b20f63542c33bb7cbbb9a9c97af7db2f7
ms.sourcegitcommit: d74aca333595beaede0d71ba13a88945ef540e44
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/03/2019
ms.locfileid: "68757687"
---
# <a name="use-security-assertion-markup-language-saml-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Security Assertion Markup Languagen (SAML) käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin

Käytä [Security Assertion Markup Languagea (SAML)](https://www.onelogin.com/pages/saml) ottaaksesi saumattoman kertakirjautumisen käyttöön. Kun otat kertakirjautumisen käyttöön, Power BI -raportit ja -koontinäytöt voivat helposti päivittää tiedot, jotka ovat peräisin paikallisista lähteistä.

## <a name="supported-data-sources"></a>Tuetut tietolähteet

Tuemme tällä hetkellä SAP HANA:a SAML:n kanssa. Lisätietoja kertakirjautumisen määrittämisestä SAP HANA:ssa SAML:n avulla on aiheessa [SAML SSO for BI Platform to HANA (SAML-kertakirjautuminen BI-alustasta HANA:an)](https://wiki.scn.sap.com/wiki/display/SAPHANA/SAML+SSO+for+BI+Platform+to+HANA) SAP HANA -dokumentaatiossa.

Tuemme muita tietolähteitä [Kerberoksen](service-gateway-sso-kerberos.md) avulla.

Huomaa, että HANA:n käytössä on **erittäin** suositeltavaa, että salaus otetaan käyttöön ennen SAML SSO -yhteyden muodostamista (eli HANA-palvelin tulisi määrittää hyväksymään salattuja yhteyksiä ja myös yhdyskäytävä tulisi määrittää käyttämään salausta HANA-palvelimen kanssa kommunikoitaessa). HANA ODBC -ohjain **ei** oletuksena voi salata SAML-vahvistuksia, ja ilman salausta allekirjoitetut SAML-vahvistukset lähetetään yhdyskäytävästä HANA-palvelimeen ”näkyvillä”, jolloin kolmas osapuoli voi pysäyttää ne ja käyttää niitä uudelleen.

## <a name="configuring-the-gateway-and-data-source"></a>Yhdyskäytävän ja tietolähteen määrittäminen

Jotta voit käyttää SAML:ää, on muodostettava luottamussuhde HANA-palvelimen, jolle haluat ottaa SSO:n käyttöön, ja yhdyskäytävän välille, joka toimii tässä tilanteessa SAML-tunnistetietopalveluna (IdP). On monia tapoja muodostaa tämä suhde, kuten tuomalla yhdyskäytävän IdP:n x509-varmenne HANA-palvelimen luottamussäilöön tai määrittämällä HANA-palvelin luottamaan varmenteen päämyöntäjän allekirjoittamaan yhdyskäytävän X509-varmenteeseen. Tässä oppaassa kuvataan jälkimmäinen lähestymistapa, mutta voit käyttää toista menetelmää, jos se on kätevämpää.

Huomaa myös, että vaikka tässä oppaassa käytetään OpenSSL:ää HANA-palvelimen salauspalveluna, SAP suosittelee käyttämään OpenSSL:n asemesta SAP-salauskirjastoa (tunnetaan myös nimillä CommonCryptoLib tai sapcrypto) luottamussuhteen muodostamisen vaiheisiin. Katso lisätietoja virallisesta SAP-dokumentaatiosta.

Seuraavissa vaiheissa kuvataan, miten voit muodostaa luottamussuhteen HANA-palvelimen ja yhdyskäytävän IdP:n välillä allekirjoittamalla yhdyskäytävän IdP:n X509-varmenteen HANA-palvelimen luottamalla varmenteen päämyöntäjällä.

1. Luo päämyöntäjän X509-varmenne ja yksityinen avain. Voit esimerkiksi luoda päämyöntäjän X509-varmenteen ja yksityisen avaimen .pem-muodossa näin:

   ```
   openssl req -new -x509 -newkey rsa:2048 -days 3650 -sha256 -keyout CA_Key.pem -out CA_Cert.pem -extensions v3_ca
   ```
  Varmista, että päämyöntäjän varmenne on suojattu oikein – kolmannet osapuolet voivat päästä HANA-palvelimeen luvattomasti, jos varmenne päätyy vääriin käsiin. 

  Lisää varmenne (esimerkiksi CA_Cert.pem) HANA-palvelimen luottamussäilöön niin, että HANA-palvelin luottaa mihin tahansa juuri luomasi päämyöntäjän allekirjoittamaan varmenteeseen. HANA-palvelimen luottamussäilön sijainti löytyy tarkastelemalla **ssltruststore**-määrityksiä. Jos olet noudattanut SAP-dokumentaatiota OpenSSL:n määrittämisessä, HANA-palvelin saattaa jo luottaa päämyöntäjään, jota voit käyttää uudelleen. Katso lisätietoja [OpenSSL:n määrittämisestä SAP HANA Studion SAP HANA -palvelimeen](https://archive.sap.com/documents/docs/DOC-39571). Jos sinulla on useita HANA-palvelimia, joille haluat ottaa SAML SSO:n käyttöön, varmista, että kaikki palvelimet luottavat tähän päämyöntäjään.

1. Luo yhdyskäytävän IdP:n X509-varmenne. Jos haluat esimerkiksi luoda varmenteen allekirjoituspyynnön (IdP_Req.pem) ja yksityisen avaimen (IdP_Key.pem), jotka ovat voimassa vuoden, suorita seuraava komento:

   ```
   openssl req -newkey rsa:2048 -days 365 -sha256 -keyout IdP_Key.pem -out IdP_Req.pem -nodes
   ```

   Allekirjoita varmenteen allekirjoituspyyntö käyttämällä sitä päämyöntäjää, johon HANA-palvelin on määritetty luottamaan. Voit esimerkiksi allekirjoittaa IdP_Req.pem:n käyttämällä CA_Cert.pem:tä ja CA_Key.pem:tä (varmenne ja päämyöntäjän avain), suorittamalla seuraavan komennon:

   ```
   openssl x509 -req -days 365 -in IdP_Req.pem -sha256 -extensions usr_cert -CA CA_Cert.pem -CAkey CA_Key.pem -CAcreateserial -out IdP_Cert.pem
   ```

Tuloksena oleva IdP-varmenne on voimassa vuoden ajan (katso -days-asetusta). Luo seuraavaksi uusi SAML-tunnistetietopalvelu tuomalla IdP-varmenne HANA Studioon.

1. Napsauta SAP HANA Studiossa SAP HANA -palvelintasi hiiren kakkospainikkeella ja siirry kohtaan **Tietoturva** > **Avaa tietoturvakonsoli** > **SAML-tunnistetietopalvelu** > **OpenSSL-salauskirjasto**.

    ![Tunnistetietopalvelut](media/service-gateway-sso-saml/identity-providers.png)

1. Valitse **Tuo**, etsi IdP_Cert.pem-tiedosto ja tuo se.

1. Valitse SAP HANA Studiossa **Tietoturva**kansio.

    ![Tietoturvakansio](media/service-gateway-sso-saml/security-folder.png)

1. Laajenna **Käyttäjät** ja valitse sitten käyttäjä, johon haluat yhdistää Power BI -käyttäjäsi.

1. Valitse **SAML** ja sitten **Määritä**.

    ![SAML:n määrittäminen](media/service-gateway-sso-saml/configure-saml.png)

1. Valitse tunnistetietopalvelu, jonka loit vaiheessa 2. Anna **Ulkoinen tunnus** -kohtaan Power BI -käyttäjän UPN (yleensä sähköpostiosoite, jossa käyttäjä kirjautuu Power BI:hin) ja valitse **Lisää**. Ota huomioon, että jos olet määrittänyt yhdyskäytävän käyttämään *ADUserNameReplacementProperty*-määritysasetusta, anna arvo, joka korvaa Power BI -käyttäjän alkuperäisen UPN:n. Jos esimerkiksi asetat *ADUserNameReplacementProperty*-asetuksen arvoksi **SAMAccountName**, anna käyttäjän **SAMAccountName**.

    ![Tunnistetietopalvelun valitseminen](media/service-gateway-sso-saml/select-identity-provider.png)

Nyt kun olet määrittänyt yhdyskäytävän varmenteen ja käyttäjätiedot, muunna varmenne pfx-muotoon ja määritä yhdyskäytäväkone käyttämään varmennetta.

1. Voit muuntaa varmenteen pfx-muotoon suorittamalla seuraavan komennon. Huomaa, että tämä komento asettaa pfx-tiedoston salasanaksi ”root”.

    ```
    openssl pkcs12 -export -out samltest.pfx -in IdP_Cert.pem -inkey IdP_Key.pem -passin pass:root -passout pass:root
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

    1. Lisää yhdyskäytävän palvelutili luetteloon. Tili on oletusarvoisesti **NT SERVICE\PBIEgwService.** Voit selvittää, mikä tili suorittaa yhdyskäytäväpalvelun suorittamalla **services.msc**:n ja etsimällä **Paikallinen tietoyhdyskäytävä -palvelun**.

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

## <a name="troubleshooting"></a>Vianmääritys

Kun olet määrittänyt SSO:n, saatat saada seuraavan virheilmoituksen Power BI -portaalista: ”Annettuja tunnistetietoja ei voida käyttää SapHana-lähteelle.” Tämä virheilmoitus merkitsee, että SAP HANA on hylännyt SAML-tunnistetiedon.

Palvelinpuolen todentamisen jäljityksistä saa yksityiskohtaisia tietoja SAP HANA:n tunnistetieto-ongelmien vianmääritystä varten. Määritä SAP HANA -palvelimen seuranta oheisella tavalla.

1. Käynnistä todentamisen jäljitys SAP HANA -palvelimella suorittamalla seuraava kysely.

    ```
    ALTER SYSTEM ALTER CONFIGURATION ('indexserver.ini', 'SYSTEM') set ('trace', 'authentication') = 'debug' with reconfigure 
    ```

1. Toista kokemasi ongelma.

1. Avaa HANA Studion hallintakonsoli ja siirry **Diagnoositiedostot**-välilehteen.

1. Avaa viimeisin indexserver-jäljitys ja hae SAMLAuthenticator.cpp.

    Sinun pitäisi löytää yksityiskohtainen virheilmoitus, joka ilmaisee pääsyyn, kuten seuraava esimerkki.

    ```
    [3957]{-1}[-1/-1] 2018-09-11 21:40:23.815797 d Authentication   SAMLAuthenticator.cpp(00091) : Element '{urn:oasis:names:tc:SAML:2.0:assertion}Assertion', attribute 'ID': '123123123123123' is not a valid value of the atomic type 'xs:ID'.
    [3957]{-1}[-1/-1] 2018-09-11 21:40:23.815914 i Authentication   SAMLAuthenticator.cpp(00403) : No valid SAML Assertion or SAML Protocol detected
    ```

1. Kun vianetsintä on valmis, poista todentamisen jäljitys käytöstä suorittamalla seuraava kysely.

    ```
    ALTER SYSTEM ALTER CONFIGURATION ('indexserver.ini', 'SYSTEM') UNSET ('trace', 'authentication');
    ```

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja **paikallisesta tietoyhdyskäytävästä** ja **DirectQuerysta** on seuraavissa resursseissa:

* [Mikä paikallinen tietoyhdyskäytävä on?](/data-integration/gateway/service-gateway-onprem)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
