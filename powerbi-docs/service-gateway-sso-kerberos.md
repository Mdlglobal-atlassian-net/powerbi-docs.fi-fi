---
title: Kerberoksen käyttäminen paikallisessa yhdyskäytävässä kertakirjautumista varten Power BI:stä paikallisiin tietolähteisiin
description: Kerberoksen määrittäminen yhdyskäytävään SSO:n käyttöön ottamiseksi Power BI:stä paikallisiin tietolähteisiin
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
ms.openlocfilehash: b66799df83095ce2104196b076482cc232c9bfae
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/25/2018
ms.locfileid: "50101619"
---
# <a name="use-kerberos-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Kerberoksen käyttäminen kertakirjautumista (SSO) varten Power BI:stä paikallisiin tietolähteisiin

Käytä [rajoitettua Kerberos-delegointia](https://technet.microsoft.com/library/jj553400.aspx) ottaaksesi saumattoman kertakirjautumisen käyttöön. Kun otat kertakirjautumisen käyttöön, Power BI -raportit ja -koontinäytöt voivat helposti päivittää tiedot, jotka ovat peräisin paikallisista lähteistä.

## <a name="supported-data-sources"></a>Tuetut tietolähteet

Tällä hetkellä tuemme seuraavia tietolähteitä:

* SQL Server
* SAP HANA
* Teradata
* Spark

Tuemme myös SAP HANA:a yhdessä [Security Assertion Markup Languagen (SAML)](service-gateway-sso-saml.md) kanssa.

### <a name="sap-hana"></a>SAP HANA

Ota kertakirjautuminen käyttöön SAP HANA:ssa toimimalla seuraavasti:

* Varmista, että SAP HANA -palvelin käyttää vaadittua vähimmäisversiota, joka riippuu SAP HANA -palvelimesi käyttöympäristötasosta:
  * [HANA 2 SP 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
  * [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
  * [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)
* Asenna yhdyskäytävätietokoneeseen SAP:n uusin HANA ODBC -ohjain.  Vähimmäisversio on HANA ODBC 2.00.020.00 elokuulta 2017.

Lisätietoja kertakirjautumisen määrittämisestä SAP HANAssa Kerberoksen avulla on aiheessa [Single Sign-on Using Kerberos (Kertakirjautuminen Kerberoksen avulla)](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/en-US/1885fad82df943c2a1974f5da0eed66d.html) SAP HANA -suojausoppaassa. Sivun linkit tarjoavat myös lisätietoja. Katso erityisesti SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory].

## <a name="preparing-for-kerberos-constrained-delegation"></a>Rajoitetun Kerberos-delegoinnin valmisteleminen

Useita kohteita on määritettävä, jotta rajoitettu Kerberos-delegointi toimii oikein, muun muassa *palvelun päänimet* (SPN) ja palvelutilien delegointiasetukset.

### <a name="prerequisite-1-install--configure-the-on-premises-data-gateway"></a>Edellytys 1: Asenna ja määritä paikallinen tietoyhdyskäytävä

Tämä paikallisen tietoyhdyskäytävän versio tukee suoraa päivitystä sekä aiemmin luotujen yhdyskäytävien asetuksien haltuunottoa.

### <a name="prerequisite-2-run-the-gateway-windows-service-as-a-domain-account"></a>Edellytys 2: Suorita yhdyskäytävän Windows-palvelu toimialuetilinä

Normaalissa asennuksessa yhdyskäytävä toimii tietokoneen paikallisena palvelutilinä (tarkemmin *NT Service\PBIEgwService*) seuraavan kuvan mukaisesti:

![Palvelutili](media/service-gateway-sso-kerberos/service-account.png)

Jotta **rajoitettu Kerberos-delegointi** voidaan ottaa käyttöön, yhdyskäytävän on toimittava toimialuetilinä, ellei Azure AD ole jo synkronoitu paikallisen Active Directoryn kanssa (käyttämällä Azure AD DirSynciä/Connectia). Jos haluat vaihtaa tilin toimialuetiliin, tutustu kohtaan [Yhdyskäytävän vaihtaminen toimialuetiliin](#switching-the-gateway-to-a-domain-account) myöhemmin tässä artikkelissa.

> [!NOTE]
> Jos määrität Azure AD DirSyncin / Connectin ja käyttäjätilit synkronoidaan, yhdyskäytäväpalvelun ei tarvitse tehdä hakuja paikallisesta AD:sta suorituksen aikana ja voit käyttää yhdyskäytäväpalvelussa paikallisen palvelun SID-tunnusta (toimialuetilin edellyttämisen sijaan). Tässä artikkelissa kuvatut rajoitetun Kerberos-delegoinnin määritysvaiheet ovat samat kuin kyseinen määritys (niitä sovelletaan yhdyskäytävän tietokoneobjektiin Active Directoryssa toimialuetilin sijaan).

### <a name="prerequisite-3-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>Edellytys 3: Toimialueen järjestelmänvalvojan oikeuksien hankkiminen päänimien (SetSPN) ja rajoitetun Kerberos-delegoinnin asetusten määrittämiseksi

Vaikka toimialueen järjestelmänvalvojan on teknisesti mahdollista antaa jollekulle muulle väliaikaiset tai pysyvät oikeudet määrittää palvelun päänimet ja Kerberos-delegointi ilman toimialueen järjestelmänvalvojan oikeuksia, tätä tapaa ei suositella. Seuraavassa osassa kerrotaan tarkemmin **edellytykseen 3** tarvittavat määritysvaiheet.

## <a name="configuring-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>Rajoitetun Kerberos-delegoinnin määrittäminen yhdyskäytävälle ja tietolähteelle

Jotta järjestelmä voidaan määrittää oikein, seuraavat kaksi kohdetta on määritettävä tai vahvistettava:

1. Määritä tarvittaessa palvelun päänimi yhdyskäytäväpalvelun toimialuetilille.

2. Määritä yhdyskäytäväpalvelun toimialuetilin delegointiasetukset.

Huomaa, että sinun on oltava toimialueen järjestelmänvalvoja, jotta voit suorittaa nämä kaksi määritysvaihetta.

Nämä vaiheet kuvataan seuraavissa osissa.

### <a name="configure-an-spn-for-the-gateway-service-account"></a>SPN:n määrittäminen yhdyskäytävän palvelutilille

Selvitä ensin, onko yhdyskäytävän palvelutilinä käytetylle toimialuetilille luotu jo SPN, noudattamalla näitä ohjeita:

1. Käynnistä **Active Directory -käyttäjät ja -tietokoneet** toimialueen järjestelmänvalvojana.

2. Napsauta toimialuetta hiiren kakkospainikkeella, valitse **Etsi** ja kirjoita yhdyskäytävän palvelutilin nimi

3. Napsauta hakutuloksissa yhdyskäytävän palvelutiliä hiiren kakkospainikkeella ja valitse **Ominaisuudet**.

4. Jos **Delegointi**-välilehti näkyy **Ominaisuudet**-valintaikkunassa, SPN on jo luotu ja voit siirtyä seuraavaan alakohtaan, joka koskee delegointiasetusten määrittämistä.

    Jos **Ominaisuudet**-valintaikkunassa ei ole **Delegointi**-välilehteä, voit luoda SPN:n kyseiselle tilille manuaalisesti, jolloin **Delegointi**-välilehti lisätään (välilehti on helpoin tapa määrittää delegointiasetukset). SPN voidaan luoda käyttämällä [setspn-työkalua](https://technet.microsoft.com/library/cc731241.aspx), joka sisältyy Windowsiin (SPN:n luominen edellyttää toimialueen järjestelmänvalvojan oikeuksia).

    Kuvitellaan esimerkiksi, että yhdyskäytävän palvelutili on ”PBIEgwTest\GatewaySvc”, ja yhdyskäytäväpalvelua suorittavan tietokoneen nimi on **Kone1**. Jotta esimerkin tietokoneen yhdyskäytävän palvelutilille voidaan määrittää SPN, on suoritettava seuraava komento:

    ![SPN:n määrittäminen](media/service-gateway-sso-kerberos/set-spn.png)

    Kun tämä vaihe on suoritettu, voidaan siirtyä delegointiasetusten määrittämiseen.

### <a name="configure-delegation-settings-on-the-gateway-service-account"></a>Yhdyskäytävän palvelutilin delegointiasetusten määrittäminen

Toinen vaadittava määritys on yhdyskäytävän palvelutilin delegointiasetusten määrittäminen. Voit suorittaa nämä vaiheet useilla eri työkaluilla. Tässä artikkelissa käytetään **Active Directory Users and Computers** -työkalua, joka on Microsoft Management Console (MMC) -laajennus. Sen avulla voit hallita ja julkaista tietoja hakemistossa. Se on käytettävissä toimialueen ohjauskoneissa oletusarvoisesti. Voit myös ottaa sen käyttöön **Windowsin toimintojen** määrityksen kautta toisissa tietokoneissa.

**Rajoitettu Kerberos-delegointi** on määritettävä protokollan siirtämisellä. Rajoitetussa delegoinnissa on määritettävä tarkasti, mihin palveluihin haluat delegoida. Esimerkiksi vain SQL Server tai SAP HANA -palvelin hyväksyy delegointikutsuja yhdyskäytävän palvelutililtä.

Tässä osassa oletetaan, että olet jo määrittänyt palvelun päänimet pohjana oleville tietolähteille (kuten SQL Server, SAP HANA, Teradata, Spark jne.). Lisätietoja kyseisten tietolähteiden palvelimen palvelun päänimien määrittämisestä löytyy vastaavan tietokantapalvelimen teknisessä dokumentaatiossa. Voit myös lukea blogikirjoituksen, jossa kerrotaan, [*mitä palvelun päänimeä sovelluksesi edellyttää*](https://blogs.msdn.microsoft.com/psssql/2010/06/23/my-kerberos-checklist/)

Seuraavissa vaiheissa oletuksena on paikallinen ympäristö, jossa on kaksi konetta: yhdyskäytäväkone ja tietokantapalvelin, joka käyttää SQL Serveriä. Esimerkissä käytetään seuraavia asetuksia ja nimiä:

* Yhdyskäytäväkoneen nimi: **PBIEgwTestGW**
* Yhdyskäytävän palvelutili: **PBIEgwTest\GatewaySvc** (tilin näyttönimi: Gateway Connector)
* SQL Server-tietolähteen koneen nimi: **PBIEgwTestSQL**
* SQL Server-tietolähteen palvelutili: **PBIEgwTest\SQLService**

Kyseisillä esimerkkinimillä ja -asetuksilla määritykset ovat seuraavat:

1. Käynnistä **Active Directory Users and Computers** toimialueen järjestelmänvalvojan oikeuksilla.

2. Napsauta yhdyskäytävän palvelutiliä (**PBIEgwTest\GatewaySvc**) hiiren kakkospainikkeella ja valitse **Ominaisuudet**.

3. Valitse **Delegointi**-välilehti.

4. Valitse **Luota tähän tietokoneeseen vain määritettyihin palveluihin delegointia varten.**

5. Valitse **Käytä mitä tahansa todennusprotokollaa.**

6. Valitse **Palvelut, joille tämä tili voi esittää delegoidut tunnistetiedot:** -kohdassa **Lisää**.

7. Valitse uudessa valintaikkunassa **Käyttäjät tai tietokoneet**.

8. Anna SQL Server -tietokantapalvelun palvelutili (**PBIEgwTest\SQLService**) ja valitse **OK**.

9. Valitse SPN, jonka loit tietokantapalvelimelle. Tässä esimerkissä SPN:n alussa on **MSSQLSvc**. Jos olet lisännyt tietokantapalvelulle sekä FQDN- että NetBIOS-SPN:n, valitse molemmat. Saatat nähdä vain toisen.

10. Valitse **OK**. Palvelun päänimen pitäisi näkyä nyt luettelossa.

11. Voit myös valita **Laajennettu**, jolloin näytetään sekä FQDN- että NetBIOS-SPN.

12. Valintaikkuna näyttää samalta kuin alla, jos valitsit **Laajennettu**. Valitse **OK**.

    ![Yhdyskäytävän liittimen ominaisuudet](media/service-gateway-sso-kerberos/gateway-connector-properties.png)

Lopuksi koneessa, joka suorittaa yhdyskäytäväpalvelua (esimerkissä **PBIEgwTestGW**), yhdyskäytävän palvelutilille on myönnettävä paikallinen käytäntö Asiakkaaksi tekeytyminen todentamisen jälkeen. Voit suorittaa tai tarkistaa tämän paikallisessa ryhmäkäytäntöeditorissa (**gpedit**).

1. Suorita yhdyskäytäväkoneessa *gpedit.msc*.

1. Siirry kohtaan **Paikallisen tietokoneen käytäntö > Tietokoneasetukset > Windowsin asetukset > Suojausasetukset > Paikalliset käytännöt > Järjestelmäoikeuksien osoitus** seuraavan kuvan mukaisesti.

    ![Käyttäjän oikeustehtävät](media/service-gateway-sso-kerberos/user-rights-assignment.png)

1. Valitse **Järjestelmäoikeuksien osoitus** -kohdan käytäntöluettelosta **Asiakkaaksi tekeytyminen todentamisen jälkeen**.

    ![Asiakkaaksi tekeytyminen](media/service-gateway-sso-kerberos/impersonate-client.png)

    Napsauta hiiren kakkospainikkeella ja avaa **Asiakkaaksi tekeytyminen todentamisen jälkeen** -kohdan **Ominaisuudet** ja tarkista tililuettelo. Sen on sisällettävä yhdyskäytävän palvelutili (**PBIEgwTest\GatewaySvc**).

1. Valitse **Järjestelmäoikeuksien osoitus** -kohdan käytäntöluettelosta **Käyttöjärjestelmän osana toimiminen (SeTcbPrivilege)**. Varmista, että yhdyskäytävän palvelutili sisältyy myös tililuetteloon.

18. Käynnistä **Paikallinen tietoyhdyskäytävä** -palveluprosessi uudelleen.

Jos käytät SAP HANA:a, suosittelemme seuraamaan seuraavia vaiheita, jotka voivat parantaa suorituskykyä jonkin verran.

1. Etsi ja avaa seuraava määritystiedosto yhdyskäytävän asennuskansiosta: *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*.

1. Etsi *FullDomainResolutionEnabled*-ominaisuus ja muuta sen arvoksi *True*.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

## <a name="running-a-power-bi-report"></a>Power BI -raportin suorittaminen

Kun kaikki aiemmin tässä artikkelissa kuvatut määritysvaiheet on suoritettu, voit käyttää Power BI:n **yhdyskäytävän hallintasivua** tietolähteen määrittämiseen. Ota sen **Lisäasetukset**-kohdassa kertakirjautuminen käyttöön ja julkaise kyseiseen tietolähteeseen liittyvät raportit ja tietojoukot.

![Lisäasetukset](media/service-gateway-sso-kerberos/advanced-settings.png)

Tämä määritys toimii useimmissa tapauksissa. Kerberoksessa voi kuitenkin olla eri määrityksiä ympäristösi mukaan. Jos raportti ei kuitenkaan lataudu, ota yhteyttä toimialueen järjestelmänvalvojaan asian selvittämiseksi.

## <a name="switching-the-gateway-to-a-domain-account"></a>Yhdyskäytävän vaihtaminen toimialuetiliin

Aiemmin tässä artikkelissa käsiteltiin yhdyskäytävän vaihtamista paikallisesta palvelutilistä toimialuetilinä suoritettavaksi **Paikallinen tietoyhdyskäytävä** -käyttöliittymän avulla. Seuraavassa on ohjeet tämän tekemiseksi.

1. Käynnistä **Paikallinen tietoyhdyskäytävä** -määritystyökalu.

   ![Yhdyskäytävän työpöytäsovellus](media/service-gateway-sso-kerberos/gateway-desktop-app.png)

2. Valitse **Kirjaudu sisään** -painike pääsivulla ja kirjaudu sisään Power BI -tililläsi.

3. Kun kirjautuminen on valmis, valitse **Palveluasetukset**-välilehti.

4. Käynnistä ohjattu määritys valitsemalla **Vaihda tili** seuraavan kuvan mukaisesti.

   ![Vaihda tili](media/service-gateway-sso-kerberos/change-account.png)

## <a name="configuring-sap-bw-for-sso"></a>SAP BW:n määrittäminen kertakirjautumista varten

Nyt kun ymmärrät, miten Kerberos toimii yhdyskäytävän kanssa, voit määrittää kertakirjautumisen SAP Business Warehousea (SAP BW) varten. Seuraavissa vaiheissa oletetaan, että olet jo [valmistellut rajoitetun Kerberos-delegoinnin](#preparing-for-kerberos-constrained-delegation) tässä artikkelissa aiemmin kuvatulla tavalla.

### <a name="install-sap-bw-components"></a>SAP BW:n osien asentaminen

Jos et ole määrittänyt SAP gsskrb5:ttä ja gx64krb5:ttä asiakaskoneeseen/asiakaskoneisiin sekä SAP BW -sovelluspalvelinta, suorita tämän osion vaiheet. Jos olet jo suorittanut asennuksen (olet luonut palvelukäyttäjän BW-palvelinta varten ja yhdistänyt SPN:n siihen), voit ohittaa osan tämän osion vaiheista.

1. Lataa gsskrb5/gx64krb5 [SAP-huomautuksesta 2115486](https://launchpad.support.sap.com/) (SAP s-käyttäjä vaaditaan). Varmista, että sinulla on vähintään versio 1.0.11.x tiedostoista gsskrb5.dll ja gx64krb5.dll.

1. Sijoita kirjasto sellaiseen paikkaan yhdyskäytäväkoneessa, jossa se on yhdyskäytävän esiintymän käytettävissä (ja myös SAP GUI:n, jos haluat testata kertakirjautumisyhteyttä SAP GUI:n / kirjautumisen avulla).

1. Aseta toinen kopio sellaiseen paikkaan BW-palvelinkoneessa, joka on BW-palvelimen käytettävissä.

1. Määritä SNC\_LIB- ja SNC\_LIB\_64 -ympäristömuuttujat asiakas- ja palvelinkoneissa osoittamaan niihin paikkoihin, joissa gsskrb5.dll ja gx64krb5.dll sijaitsevat (tässä mainitussa järjestyksessä).

### <a name="complete-the-gateway-configuration-for-sap-bw"></a>SAP BW:n yhdyskäytävän määrityksen viimeisteleminen

Tekemäsi yhdyskäytävän määrityksen lisäksi sinun tulee suorittaa muutama SAP BW -kohtainen vaihe. Ohjeiden osiossa [**Yhdyskäytävän palvelutilin delegointiasetusten määrittäminen**](#configure-delegation-settings-on-the-gateway-service-account) oletetaan, että olet jo määrittänyt SPN:t pohjana oleville tietolähteille. Viimeistele tämä SAP BW -määritys toimimalla seuraavasti:

1. Luo palvelukäyttäjä (aluksi vain tavallinen Active Directory -käyttäjä) Active Directory -toimialueen ohjauskoneessa Active Directory-ympäristössäsi olevaa BW-sovelluspalvelinta varten. Liitä sitten SPN siihen.

    Tämän määritetyn SPN:n **täytyy** alkaa merkkijonolla SAP/. Voit itse päättää, miten merkkijono jatkuu SAP/:n jälkeen – voit esimerkiksi käyttää BW-palvelimen palvelukäyttäjän käyttäjänimeä. Jos luot esimerkiksi palvelukäyttäjän BWPalvelukäyttäjä@\<TOIMIALUE\>, SPN:n voisi olla SAP/BWPalvelukäyttäjä. Yksi tapa määrittää SPN-yhdistämismääritys on käyttää setspn-komentoa. Voit esimerkiksi määrittää juuri luomasi palvelukäyttäjän SPN:n suorittamalla seuraavan komennon cmd-ikkunassa toimialueen ohjauskoneessa: `setspn -s SAP/ BWServiceUser DOMAIN\ BWServiceUser`.

1. Anna palvelukäyttäjälle käyttöoikeus BW-sovelluspalvelimen esiintymään:

    1. Lisää palvelukäyttäjä BW-palvelinkoneen BW-palvelimen paikalliseen järjestelmänvalvojaryhmään toimimalla seuraavasti: avaa Tietokoneen hallinta -ohjelma ja kaksoisnapsauta palvelimesi paikallista järjestelmänvalvojaryhmää.

        ![Tietokoneen hallinta](media/service-gateway-sso-kerberos/computer-management.png)

    1. Kaksoisnapsauta paikallista järjestelmänvalvojaryhmää ja lisää sitten BW-palvelukäyttäjän ryhmään valitsemalla **Lisää**. Käytä **Tarkista nimet** -painiketta varmistaaksesi, että olet kirjoittanut nimen oikein. Valitse **OK**.

1. Määritä BW-palvelimen palvelukäyttäjä siksi käyttäjäksi, joka käynnistää BW-palvelinpalvelun BW-palvelinkoneessa.

    1. Avaa ”Suorita”-ohjelma ja kirjoita komento ”Services.msc”. Etsi palvelu, joka vastaa BW-sovelluspalvelimen esiintymää. Napsauta sitä hiiren kakkospainikkeella ja valitse **Ominaisuudet**.

        ![Palvelinasetukset](media/service-gateway-sso-kerberos/server-properties.png)

    1. Vaihda **Kirjaudu**-välilehteen ja muuta käyttäjä BW-palvelukäyttäjäksi yllä esitetyllä tavalla. Kirjoita käyttäjän salasana ja valitse **OK**.

1. Kirjaudu sisään palvelimeesi SAP GUI:n / kirjautumisen kautta ja määritä seuraavat profiiliparametrit RZ10-tapahtuman avulla:

    1. Määritä snc/identity/as-profiiliparametrin arvoksi p:\<luomasi BW-palvelukäyttäjä\>, esimerkiksi p:BWServiceUser@MYDOMAIN.COM. Älä unohda lisätä merkkijonoa ”p:” ennen palvelukäyttäjän täydellistä käyttäjätunnusta.

    1. Määritä snc/gssapi\_lib-profiiliparametrin arvoksi \<gsskrb5.dll- tai gx64krb5.dll-tiedoston polku palvelinkoneessa (käyttämäsi kirjasto määräytyy käyttöjärjestelmän bittimäärän mukaan)\>. Muista asettaa kirjasto sellaiseen paikkaan, jota BW-sovelluspalvelin voi käyttää.

    1. Muuta myös seuraavia profiilin lisäparametrien arvoja niin, että ne vastaavat tarpeitasi. Huomaa, että viimeisellä viidellä asetuksella voit antaa asiakkaittesi muodostaa yhteyden BW-palvelimeen SAP-kirjautumisen / GUI:n avulla ilman, että heille on määritetty SNC:tä.

        | **Asetus** | **Arvo** |
        | --- | --- |
        | snc/data\_protection/max | 3 |
        | snc/data\_protection/min | 1 |
        | snc/data\_protection/use | 9 |
        | snc/accept\_insecure\_cpic | 1 |
        | snc/accept\_insecure\_gui | 1 |
        | snc/accept\_insecure\_r3int\_rfc | 1 |
        | snc/accept\_insecure\_rfc | 1 |
        | snc/permit\_insecure\_start | 1 |

    1. Määritä snc/enable-omaisuuden arvoksi 1.

1. Kun olet määrittänyt nämä profiiliparametrit, avaa palvelinkoneen SAP-hallintakonsoli ja käynnistä BW-esiintymä uudelleen. Jos palvelin ei käynnisty, tarkista, että olet määrittänyt profiilin parametrit oikein. Lisätietoja profiiliparametriasetuksista löytyy [SAP-dokumentaatiosta](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm). Voit myös tarvittaessa tutustua vianmääritystietoihin, jotka esitellään myöhemmin tässä osiossa.

### <a name="map-azure-ad-users-to-sap-bw-users"></a>Azure AD -käyttäjien liittäminen SAP BW -käyttäjiin

Liitä Active Directory -käyttäjä SAP BW -sovelluspalvelimen käyttäjään ja testaa kertakirjautumisyhteyttä SAP GUI:ssa / kirjautumisessa.

1. Kirjaudu sisään BW-palvelimeen käyttämällä SAP GUI:ta / kirjautumista. Suorita tapahtuma SU01.

1. Syötä **Käyttäjä**-kohtaan BW-käyttäjä, jolle haluat ottaa kertakirjautumisyhteydet käyttöön (yllä olevassa näyttökuvassa määritämme käyttöoikeudet käyttäjälle BIUSER). Valitse **Muokkaa**-kuvake, joka löytyy SAP-kirjautumisikkunan vasemmasta yläkulmasta (kuva kynästä).

    ![Käyttäjien ylläpito](media/service-gateway-sso-kerberos/user-maintenance.png)

1. Valitse **SNC**-välilehti. Syötä SNC-nimisyöteruutuun arvo p:\<Active Directory -käyttäjä\>@\<toimialue\>. Huomaa pakollinen p:, jonka on tultava ennen Active Directory -käyttäjän täydellistä käyttäjätunnusta. Määrittämäsi Active Directory -käyttäjän on kuuluttava henkilölle tai organisaatiolle, jolle haluat myöntää kertakirjautumiskäyttöoikeuden BW-sovelluspalvelimeen. Jos haluat esimerkiksi myöntää kertakirjautumiskäyttöoikeuden käyttäjälle [testuser@TESTDOMAIN.COM](mailto:testuser@TESTDOMAIN.COM), syötä p:testuser@TESTDOMAIN.COM.

    ![Käyttäjien ylläpitäminen](media/service-gateway-sso-kerberos/maintain-users.png)

1. Valitse tallenna-kuvake (näytön vasemmassa yläkulmassa oleva levyke).

### <a name="verify-sign-in-using-sso"></a>Sisäänkirjautumisen tarkistaminen kertakirjautumisen avulla

Varmista, että voit kirjautua palvelimeen SAP-kirjautumisen / SAP GUI:n kautta kertakirjautumisen avulla sen Active Directory -käyttäjän tunnuksilla, jolle juuri myönsit kertakirjautumiskäyttöoikeuden.

1. Kirjaudu sisään tietokoneeseen, johon on asennettu SAP-kirjautuminen. Käytä *sen Active Directory -käyttäjän tunnuksia, jolle otit kertakirjautumisen käyttöön* ja käynnistä SAP GUI/kirjautuminen. Luo uusi yhteys.

1. Valitse **Luo uusi järjestelmän merkintä** -ikkunassa **Käyttäjän määrittämä järjestelmä** ja valitse **Seuraava**.

    ![Uusi järjestelmän merkintä](media/service-gateway-sso-kerberos/new-system-entry.png)

1. Täytä tarvittavat tiedot seuraavalla sivulla, mukaan lukien sovelluspalvelin, esiintymän numero ja järjestelmätunnus, ja valitse sitten **Valmis**.

1. Napsauta uutta yhteyttä hiiren kakkospainikkeella ja valitse **Ominaisuudet**. Valitse **Verkko**-välilehti. Kirjoita **SNC-nimi**-ikkunassa p:\<BW-palvelukäyttäjän täydellinen käyttäjätunnus\>, kuten p:BWServiceUser@MYDOMAIN.COM.

    ![Järjestelmän merkintäominaisuudet](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. Valitse **OK**. Kaksoisnapsauta juuri luomaasi yhteyttä muodostaaksesi kertakirjautumisyhteyden palveluun. Jos tämä yhteys toimii, siirry seuraavaan vaiheeseen. Muussa tapauksessa tarkista tässä ohjeessa olevat aiemmat vaiheet. Varmista, että suoritit ne oikein, tai tarkista alla oleva vianmääritysosio. Huomaa, että jos et voi muodostaa yhteyttä BW-palvelimeen kertakirjautumisen avulla tässä kontekstissa, et voi muodostaa yhteyttä BW-palvelimeen kertakirjautumisen avulla yhdyskäytäväkontekstissakaan.

### <a name="troubleshoot-installation-and-connections"></a>Asennuksen ja yhteyksien vianmääritys

Jos kohtaat ongelmia, toimi seuraavasti määrittääksesi viat gsskrb5-asennuksessa ja SAP GUI:n / kirjautumisen kertakirjautumisyhteyksissä.

1. Palvelimen lokien tarkastelemisesta (...work\dev\_w0 palvelinkoneessa) voi olla hyötyä, kun yrität määrittää gsskrb5-asennuksen yhteydessä ilmeneviä virheitä, erityisesti jos BW-palvelin ei käynnisty profiiliparametrien muuttamisen jälkeen.

1. Jos et pysty käynnistämään BW-palvelua kirjautumisvirheen vuoksi, on mahdollista, että syötit väärän salasanan, kun määritit BW:n aloituskäyttäjäksi. Vahvista salasana kirjautumalla sisään Active Directory -ympäristössäsi olevaan tietokoneeseen BW-palvelukäyttäjänä.

1. Jos saat SQL-tunnistetietoihin liittyviä virheilmoituksia, jotka estävät palvelinta käynnistymästä, varmista, että olet myöntänyt palvelukäyttäjälle käyttöoikeuden BW-tietokantaan.

1. ”(GSS-API) määritetty kohde on tuntematon tai siihen ei saada yhteyttä”: Tämä tarkoittaa yleensä sitä, että olet määrittänyt väärän SNC-nimen. Muista, että asiakassovelluksessa tulee käyttää palvelukäyttäjän täydellisen käyttäjätunnuksen lisäksi vain merkkijonoa ”p:” merkkijonon ”p:CN=” tai vastaavien sijaan.

1. ”(GSS-API) Annettiin virheellinen nimi”: Varmista, että palvelimen SNC-identiteetin profiiliparametrin arvo on ”p:”.

1. ”(SNC-virhe) määritettyä moduulia ei löytynyt”: Tämä johtuu yleensä siitä, että gsskrb5.dll tai gx64krb5.dll on sijoitettu sellaiseen paikkaan, joka vaatii laajennettuja oikeuksia (järjestelmänvalvojan oikeuksia).

### <a name="add-registry-entries"></a>Rekisterimerkintöjen lisääminen

Lisää tarvittavat rekisterimerkinnät sen tietokoneen rekisteriin, johon yhdyskäytävä on asennettu. Aseta sitten vaaditut yhdyskäytävän määritysparametrit.

1. Suorita seuraavat komennot cmd-ikkunassa:

    1. REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

    1. REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

1. Avaa yhdyskäytävän päämääritystiedosto: Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll. Tämä tiedosto löytyy oletusarvoisesti sijainnista C:\Program Files\On-premises data gateway.

1. Määritä kohdan **ADUserNameLookupProperty** arvoksi msDS-cloudExtensionAttribute1 ja kohdan **ADUserNameReplacementProperty** arvoksi SAMAccountName. Tallenna määritystiedosto.

1. Käynnistä yhdyskäytäväpalvelu uudelleen Tehtävienhallinnan **Palvelut**-välilehden kautta (napsauta hiiren kakkospainikkeella, **Käynnistä uudelleen**).

    ![Yhdyskäytävän käynnistäminen uudelleen](media/service-gateway-sso-kerberos/restart-gateway.png)

### <a name="set-azure-ad-properties"></a>Azure AD:n ominaisuuksien määrittäminen

Määritä BW-käyttäjään yhdistetyn Active Directory -käyttäjän msDS-cloudExtensionAttribute1-ominaisuus (vaiheessa ”Azure AD -käyttäjien liittäminen SAP BW -käyttäjiin”) osoittamaan kohti sitä Power BI -palvelun käyttäjää, jolle haluat ottaa Kerberos SSO -kirjautumisen käyttöön. Voit asettaa msDS-cloudExtensionAttribute1-ominaisuuden käyttämällä esimerkiksi ”Active Directory -käyttäjät ja -tietokoneet MMC” -laajennusta (huomaa, että voit käyttää myös muita menetelmiä).

1. Kirjaudu sisään toimialueen ohjauskoneeseen järjestelmänvalvojakäyttäjänä.

1. Avaa **Käyttäjät**-kansio laajennuksen ikkunassa ja kaksoisnapsauta BW-käyttäjälle yhdistettyä Active Directory -käyttäjää.

1. Valitse **Ominaisuuseditori**-välilehti. Jos et näe tätä välilehteä, sinun tulee etsiä ohjeet sen käyttöönottoon tai käyttää toista tapaa, jolla voit määrittää msDS-cloudExtensionAttribute1-ominaisuuden. Valitse yksi määritteistä ja paina sitten ’m’-näppäintä siirtyäksesi Active Directory -ominaisuuksiin, jotka alkavat m-kirjaimella. Etsi msDS-cloudExtensionAttribute1-ominaisuus ja kaksoisnapsauta sitä. Määritä sen arvoksi käyttäjänimi, jolla kirjaudut sisään Power BI -palveluun. Valitse **OK**.

    ![Määritteen muokkaaminen](media/service-gateway-sso-kerberos/edit-attribute.png)

1. Valitse **Käytä**. Varmista, että olet määrittänyt oikean arvon Arvo-sarakkeeseen.

### <a name="add-a-new-bw-application-server-data-source-to-the-power-bi-service"></a>Uuden BW-sovelluspalvelimen tietolähteen lisääminen Power BI -palveluun

Lisää BW-tietolähde yhdyskäytävääsi: seuraa aiemmin tässä artikkelissa annettuja ohjeita [raportin suorittamisesta](#running-a-power-bi-report).

1. Kirjoita tietolähteen määritysikkunassa sovelluspalvelimen **Isäntänimi**, **Järjestelmänumero** ja **asiakastunnus** samalla tavalla kuin silloin, kun kirjaudut sisään BW-palvelimeesi Power BI Desktopin kautta. Valitse **todennusmenetelmäksi** **Windows**.

1. Syötä **SNC-kumppaninimi**-kenttään palvelimeen tallennetun snc/identity/as-profiiliparametrin arvo, *johon on lisätty merkkijono ”SAP/” kohdan ”p:” ja muiden käyttäjätietojen väliin.* Esimerkiksi jos palvelimen snc-käyttäjätieto on p:BWServiceUser@MYDOMAIN.COM, syötä p:SAP/BWServiceUser@MYDOMAIN.COM. SNC-kumppaninimen syöteruutuun.

1. Valitse SNC-kirjastoksi joko SNC\_LIB tai SNC\_LIB\_64.

1. **Käyttäjänimen** ja **salasanan** kohdalla tulee käyttää sellaisen Active Directory -käyttäjän käyttäjänimeä ja salasanaa, jolla on oikeus kirjautua BW-palvelimeen kertakirjautumisen avulla (Active Directory -käyttäjä, joka on yhdistetty BW-käyttäjään SU01-tapahtuman avulla). Näitä tunnistetietoja käytetään vain, jos **Käytä DirectQuery-kyselyissä kertakirjautumista Kerberoksen kautta** -ruutu *ei* ole valittuna.

1. Valitse **Käytä DirectQuery-kyselyissä kertakirjautumista Kerberoksen kautta** -ruutu ja valitse **Käytä**. Jos testiyhteys ei toimi, tarkista, että suoritit aiemmat asennus- ja määritysvaiheet oikein.

### <a name="test-your-setup"></a>Asennuksen testaaminen

Testaa asennuksesi julkaisemalla DirectQuery-raportti Power BI Desktopista Power BI -palveluun. Varmista, että olet kirjautunut sisään Power BI -palveluun sinä käyttäjänä, jonka asetit msDS-cloudExtensionAttribute1-ominaisuuden arvoksi. Jos asennus on suoritettu onnistuneesti, sinun pitäisi pystyä luomaan raportti, joka perustuu Power BI -palvelussa julkaistuun tietojoukkoon, sekä vastaanottamaan tietoja raportin visualisointien kautta.

### <a name="troubleshooting-gateway-connectivity-issues"></a>Yhdyskäytävän yhteysongelmien vianmääritys

1. Tarkista yhdyskäytävän lokit. Avaa yhdyskäytävän kokoonpanosovellus, valitse **Diagnostiikka** ja valitse **Vie lokit**. Viimeisimmät virheet löydät lokitiedostojen alareunasta.

    ![Yhdyskäytävän diagnostiikka](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. Ottaa BW-jäljitys käyttöön ja tarkastele luotoja lokitiedostoja. Käytettävissä on useita erilaisia BW-jäljitysvaihtoehtoja. Lisätietoja löytyy SAP-dokumentaatiosta.

## <a name="errors-from-an-insufficient-kerberos-configuration"></a>Puutteellisesta Kerberos-määrityksestä johtuvat virheet

Jos pohjana olevaa tietokantapalvelinta ja yhdyskäytävää ei ole määritetty oikein **rajoitetun Kerberos-delegoinnin** osalta, näyttöön saattaa tulla seuraava virhesanoma:

![Tietojen latausvirhe](media/service-gateway-sso-kerberos/load-data-error.png)

Virhesanomaan (DM_GWPipeline_Gateway_ServerUnreachable) liittyvät tekniset tiedot saattavat näyttää seuraavilta:

![Palvelimeen ei saa yhteyttä](media/service-gateway-sso-kerberos/server-unreachable.png)

Tuloksena on, että yhdyskäytävä ei voinut tekeytyä alkuperäiseksi käyttäjäksi oikein ja tietokantayhteyden muodostamisyritys epäonnistui.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja **paikallisesta tietoyhdyskäytävästä** ja **DirectQuerystä** on seuraavissa resursseissa:

* [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)