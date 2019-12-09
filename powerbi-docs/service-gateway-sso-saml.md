---
title: Security Assertion Markup Languagen (SAML) käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin
description: Määritä yhdyskäytävä Security Assertion Markup Languagen (SAML) avulla kertakirjautumisen (SSO) käyttöön ottamiseksi Power BI:stä paikallisiin tietolähteisiin.
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: bbb0584843f79445c4e5cca073f9c4b953d346aa
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74699356"
---
# <a name="use-security-assertion-markup-language-saml-for-sso-from-power-bi-to-on-premises-data-sources"></a>Security Assertion Markup Languagen (SAML) käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin

Kun otat kertakirjautumisen käyttöön, Power BI -raportit ja -koontinäytöt voivat helposti päivittää tiedot, jotka ovat peräisin paikallisista lähteistä. Samalla niissä noudatetaan kyseisissä lähteissä määritettyjä käyttäjätason käyttöoikeuksia. Käytä [Security Assertion Markup Languagea (SAML)](https://www.onelogin.com/pages/saml) ottaaksesi saumattoman kertakirjautumisen käyttöön. 

## <a name="supported-data-sources"></a>Tuetut tietolähteet

Tuemme tällä hetkellä SAP HANA:a SAML:n kanssa. Lisätietoja kertakirjautumisen määrittämisestä SAP HANA:ssa SAML:n avulla on artikkelissa [SAML SSO for BI Platform to HANA (SAML-kertakirjautuminen BI-alustasta HANA:an)](https://wiki.scn.sap.com/wiki/display/SAPHANA/SAML+SSO+for+BI+Platform+to+HANA).

Tuemme muita tietolähteitä [Kerberoksen](service-gateway-sso-kerberos.md) avulla (SAP HANA mukaan luettuna).

SAP HANA suosittelee, että otat salauksen käyttöön ennen SAML-pohjaisen kertakirjautumisyhteyden muodostamista. Jos haluat ottaa salauksen käyttöön, määritä HANA-palvelin hyväksymään salatut yhteydet ja määritä yhdyskäytävä käyttämään salausta yhteyden muodostamiseen HANA-palvelimesi kanssa. Koska HANA ODBC -ohjain ei oletuksena salaa SAML-vahvistuksia, allekirjoitetut SAML-vahvistukset lähetetään yhdyskäytävästä HANA-palvelimeen *näkyvillä*, jolloin kolmas osapuoli voi pysäyttää ne ja käyttää niitä uudelleen. Lisätietoja salauksen ottamisesta käyttöön HANAlle OpenSSL-kirjaston avulla on kohdassa [Ota SAP HANAn salaus käyttöön](/power-bi/desktop-sap-hana-encryption).

## <a name="configuring-the-gateway-and-data-source"></a>Yhdyskäytävän ja tietolähteen määrittäminen

Jotta voit käyttää SAML:ää, on muodostettava luottamussuhde HANA-palvelimen, jolle haluat ottaa SSO:n käyttöön, ja yhdyskäytävän välille. Tässä tilanteessa yhdyskäytävä toimii SAML-tunnistetietopalveluna (IdP). On monia tapoja muodostaa tämä suhde, kuten tuomalla yhdyskäytävän IdP:n x509-varmenne HANA-palvelimen luottamussäilöön tai määrittämällä HANA-palvelin luottamaan varmenteen päämyöntäjän allekirjoittamaan yhdyskäytävän X509-varmenteeseen. Vaikka tässä oppaassa kuvataan jälkimmäinen lähestymistapa, voit käyttää toista menetelmää, jos se on kätevämpää.

Vaikka tässä oppaassa käytetään OpenSSL:ää HANA-palvelimen salauspalveluna, SAP suosittelee käyttämään OpenSSL:n asemesta SAP-salauskirjastoa (tunnetaan myös nimillä CommonCryptoLib tai sapcrypto) luottamussuhteen muodostamisen vaiheisiin. Katso lisätietoja SAP:n virallisesta dokumentaatiosta.

Seuraavissa vaiheissa kuvataan, miten voit muodostaa luottamussuhteen HANA-palvelimen ja yhdyskäytävän IdP:n välillä allekirjoittamalla yhdyskäytävän IdP:n X509-varmenteen HANA-palvelimen luottamalla varmenteen päämyöntäjällä. Luot tämän päämyöntäjän:

1. Luo päämyöntäjän X509-varmenne ja yksityinen avain. Voit esimerkiksi luoda päämyöntäjän X509-varmenteen ja yksityisen avaimen .pem-muodossa tällä komennolla:

   ```
   openssl req -new -x509 -newkey rsa:2048 -days 3650 -sha256 -keyout CA_Key.pem -out CA_Cert.pem -extensions v3_ca
   ```

    Varmista, että varmenteen päämyöntäjän yksityinen avain on suojattu oikein. Jos se tulee kolmannelta osapuolelta, sen avulla voi päästä luvattomasti HANA-palvelimelle. 

 1. Lisää varmenne (esimerkiksi CA_Cert.pem) HANA-palvelimen luottamussäilöön niin, että HANA-palvelin luottaa mihin tahansa luomasi päämyöntäjän allekirjoittamaan varmenteeseen. 

    Löydät HANA-palvelimen luottamussäilön sijainnin tarkastelemalla **ssltruststore**-määrityksiä. Jos olet noudattanut SAP-dokumentaation ohjeita OpenSSL:n määrittämisessä, HANA-palvelin saattaa jo luottaa päämyöntäjään, jota voit käyttää uudelleen. Katso lisätietoja [OpenSSL:n määrittämisestä SAP HANA Studion SAP HANA -palvelimeen](https://archive.sap.com/documents/docs/DOC-39571). Jos sinulla on useita HANA-palvelimia, joille haluat ottaa SAML SSO:n käyttöön, varmista, että kaikki palvelimet luottavat tähän päämyöntäjään.

1. Luo yhdyskäytävän IdP:n X509-varmenne. 

   Jos haluat esimerkiksi luoda varmenteen allekirjoituspyynnön (IdP_Req.pem) ja yksityisen avaimen (IdP_Key.pem), jotka ovat voimassa vuoden, suorita seuraava komento:

   ```
   openssl req -newkey rsa:2048 -days 365 -sha256 -keyout IdP_Key.pem -out IdP_Req.pem -nodes
   ```

 1. Allekirjoita varmenteen allekirjoituspyyntö käyttämällä sitä päämyöntäjää, johon HANA-palvelin on määritetty luottamaan. 

    Voit esimerkiksi allekirjoittaa IdP_Req.pem:n käyttämällä CA_Cert.pem:tä ja CA_Key.pem:tä (varmenne ja päämyöntäjän avain), suorittamalla seuraavan komennon:

    ```
    openssl x509 -req -days 365 -in IdP_Req.pem -sha256 -extensions usr_cert -CA CA_Cert.pem -CAkey CA_Key.pem -CAcreateserial -out IdP_Cert.pem
    ```

     Tuloksena oleva IdP-varmenne on voimassa vuoden ajan (katso -days-asetusta). 

Luo uusi SAML-tunnistetietopalvelu tuomalla IdP-varmenne HANA Studioon:

1. Napsauta SAP HANA Studiossa SAP HANA -palvelimesi nimeä hiiren kakkospainikkeella ja siirry kohtaan **Tietoturva** &gt; **Avaa tietoturvakonsoli** &gt; **SAML-tunnistetietopalvelu** &gt; **OpenSSL-salauskirjasto**.

    ![Tunnistetietopalvelut](media/service-gateway-sso-saml/identity-providers.png)

1. Valitse **Tuo**, etsi IdP_Cert.pem-tiedosto ja tuo se.

1. Valitse SAP HANA Studiossa **Tietoturva**kansio.

    ![Tietoturvakansio](media/service-gateway-sso-saml/security-folder.png)

1. Laajenna **Käyttäjät** ja valitse sitten käyttäjä, johon haluat yhdistää Power BI -käyttäjäsi.

1. Valitse **SAML**, ja valitse sitten **Määritä**.

    ![SAML:n määrittäminen](media/service-gateway-sso-saml/configure-saml.png)

1. Valitse tunnistetietopalvelu, jonka loit vaiheessa 2. Anna **Ulkoinen tunnus** -kohtaan Power BI -käyttäjän UPN (yleensä sähköpostiosoite, jolla käyttäjä kirjautuu Power BI:hin) ja valitse **Lisää**. Jos olet määrittänyt yhdyskäytävän käyttämään *ADUserNameReplacementProperty*-määritysasetusta, anna arvo, joka korvaa Power BI -käyttäjän alkuperäisen UPN:n. 

   Jos esimerkiksi asetat *ADUserNameReplacementProperty*-asetuksen arvoksi **SAMAccountName**, anna käyttäjän **SAMAccountName**.

    ![Tunnistetietopalvelun valitseminen](media/service-gateway-sso-saml/select-identity-provider.png)

Nyt kun olet määrittänyt yhdyskäytävän varmenteen ja käyttäjätiedot, muunna varmenne pfx-muotoon ja määritä yhdyskäytävä käyttämään varmennetta:

1. Voit muuntaa varmenteen pfx-muotoon suorittamalla seuraavan komennon. Tämä komento antaa tulokseksi saatavan .pfx-tiedoston nimeksi samlcert.pfx ja asettaa sen salasanaksi *root*:

    ```
    openssl pkcs12 -export -out samltest.pfx -in IdP_Cert.pem -inkey IdP_Key.pem -passin pass:root -passout pass:root
    ```

1. Kopioi pfx-tiedosto yhdyskäytäväkoneeseen:

    1. Kaksoisnapsauta samltest.pfx-tiedostoa ja valitse sitten **Paikallinen tietokone** &gt; **Seuraava**.

    1. Anna salasana ja valitse sitten **Seuraava**.

    1. Valitse **Sijoita kaikki varmenteet seuraavaan paikkaan** ja valitse sitten **Selaa** &gt; **Henkilökohtainen** &gt; **OK**.

    1. Valitse **Seuraava** ja sitten **Valmis**.

       ![Varmenteen tuonti](media/service-gateway-sso-saml/import-certificate.png)

1. Myönnä yhdyskäytävän palvelutilille käyttöoikeus varmenteen yksityisavaimeen:

    1. Suorita yhdyskäytäväkoneessa Microsoft Management Console (MMC).

        ![MMC:n suorittaminen](media/service-gateway-sso-saml/run-mmc.png)

    1. Kohdassa **Tiedosto**, valitse **Lisää/poista laajennus**.

        ![Laajennuksen lisääminen](media/service-gateway-sso-saml/add-snap-in.png)

    1. Valitse **Varmenteet** &gt; **Lisää** ja valitse sitten **Tietokonetili** &gt; **Seuraava**.

    1. Valitse **Paikallinen tietokone** &gt; **Valmis** &gt; **OK**.

    1. Laajenna **Varmenteet** &gt; **Henkilökohtainen** &gt; **Varmenteet** ja etsi haluamasi varmenne.

    1. Napsauta varmennetta hiiren kakkospainikkeella ja siirry kohtaan **Kaikki tehtävät** &gt; **Yksityisten avainten hallinta**.

        ![Yksityisten avainten hallinta](media/service-gateway-sso-saml/manage-private-keys.png)

    1. Lisää yhdyskäytävän palvelutili luetteloon. Tili on oletusarvoisesti **NT SERVICE\PBIEgwService**. Voit selvittää, mikä tili suorittaa yhdyskäytäväpalvelun suorittamalla **services.msc**:n ja etsimällä **Paikallinen tietoyhdyskäytävä -palvelun**.

        ![Yhdyskäytäväpalvelu](media/service-gateway-sso-saml/gateway-service.png)

Lopuksi seuraa näitä ohjeita lisätäksesi varmenteen allekirjoituksen yhdyskäytävän määritykseen:

1. Suorita seuraava PowerShell-komento, jotta saat luettelon tietokoneessasi olevista varmenteista:

    ```powershell
    Get-ChildItem -path cert:\LocalMachine\My
    ```

1. Kopioi luomasi varmenteen allekirjoitus.

1. Siirry yhdyskäytävän hakemistoon, joka on oletusarvoisesti C:\Program Files\On-premises data gateway.

1. Avaa tiedosto PowerBI.DataMovement.Pipeline.GatewayCore.dll.config ja etsi osio nimeltä *SapHanaSAMLCertThumbprint*. Liitä kopioimasi allekirjoitus.

1. Käynnistä yhdyskäytäväpalvelu uudelleen.

## <a name="running-a-power-bi-report"></a>Power BI -raportin suorittaminen

Nyt voit käyttää Power BI:n **yhdyskäytävän hallintasivua** SAP HANA -tietolähteen määrittämiseen. Ota sen **Lisäasetukset**-kohdassa käyttöön kertakirjautuminen SAML:n kautta. Tämän jälkeen voit julkaista kyseiseen tietolähteeseen liittyvät raportit ja tietojoukot.

   ![Lisäasetukset](media/service-gateway-sso-saml/advanced-settings.png)

## <a name="troubleshooting"></a>Vianmääritys

Kun olet määrittänyt SAML-pohjaisen kertakirjautumisen, saatat saada seuraavan virheilmoituksen Power BI -portaalista: *Annettuja tunnistetietoja ei voida käyttää SapHana-lähteelle.* Tämä virheilmoitus merkitsee, että SAP HANA on hylännyt SAML-tunnistetiedon.

Palvelinpuolen todentamisen jäljityksistä saa yksityiskohtaisia tietoja SAP HANA:n tunnistetieto-ongelmien vianmääritystä varten. Määritä SAP HANA -palvelimen seuranta oheisella tavalla:

1. Käynnistä todentamisen jäljitys SAP HANA -palvelimella suorittamalla seuraava kysely:

    ```
    ALTER SYSTEM ALTER CONFIGURATION ('indexserver.ini', 'SYSTEM') set ('trace', 'authentication') = 'debug' with reconfigure 
    ```

1. Yritä toistaa ongelma.

1. Avaa HANA Studion hallintakonsoli ja valitse **Diagnoositiedostot**-välilehti.

1. Avaa viimeisin index server -jäljitys ja hae *SAMLAuthenticator.cpp*.

    Sinun pitäisi löytää yksityiskohtainen virheilmoitus, joka ilmaisee pääsyyn, esimerkiksi:

    ```
    [3957]{-1}[-1/-1] 2018-09-11 21:40:23.815797 d Authentication   SAMLAuthenticator.cpp(00091) : Element '{urn:oasis:names:tc:SAML:2.0:assertion}Assertion', attribute 'ID': '123123123123123' is not a valid value of the atomic type 'xs:ID'.
    [3957]{-1}[-1/-1] 2018-09-11 21:40:23.815914 i Authentication   SAMLAuthenticator.cpp(00403) : No valid SAML Assertion or SAML Protocol detected
    ```

1. Kun vianetsintä on valmis, poista todentamisen jäljitys käytöstä suorittamalla seuraava kysely:

    ```
    ALTER SYSTEM ALTER CONFIGURATION ('indexserver.ini', 'SYSTEM') UNSET ('trace', 'authentication');
    ```

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja paikallisesta tietoyhdyskäytävästä ja DirectQuerysta on seuraavissa resursseissa:

* [Mikä paikallinen tietoyhdyskäytävä on?](/data-integration/gateway/service-gateway-onprem)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
