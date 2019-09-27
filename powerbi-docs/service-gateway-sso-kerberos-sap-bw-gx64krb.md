---
title: Kerberoksen käyttäminen kertakirjautumista (SSO) varten SAP BW:ssä gx64krb5:n avulla
description: SAP BW -palvelimen määrittäminen ottamaan kertakirjautuminen käyttöön Power BI -palvelussa gx64krb5:n avulla
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 5dd31dc4333dc03100370100e16eadab6012c1f0
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/18/2019
ms.locfileid: "71106327"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-bw-using-gx64krb5"></a>Kerberoksen käyttäminen kertakirjautumista (SSO) varten SAP BW:ssä gx64krb5:n avulla

Tässä artikkelissa kerrotaan, miten voit määrittää SAP BW -palvelimesi ottamaan käyttöön kertakirjautumisen Power BI -palvelusta gx64krb5:n avulla.

> [!NOTE]
> Voit suorittaa tämän artikkelin vaiheet [Kerberos-kertakirjautumisen määrittäminen](service-gateway-sso-kerberos.md) -kohdan vaiheiden lisäksi, jotta voit ottaa käyttöön päivityksen SAP BW:n sovelluspalvelinpohjaisia raporteissa, joissa on käytössä Kerberos-kertakirjautuminen Power BI -palvelussa. Microsoft suosittelee kuitenkin CommonCryptoLibin käyttämistä SNC-kirjastona. SAP ei enää tarjoa tukea gx64krb5:lle, ja sen määrittämiseen tarvittavat vaiheet yhdyskäytävän kanssa käyttöä varten ovat huomattavasti monimutkaisempia CommonCryptoLibiin verrattuna. Lisätietoa kertakirjautumisen määrittämisestä CommonCryptoLibin avulla on kohdassa [SAP BW:n määrittäminen kertakirjautumista varten CommonCryptoLibiä käyttämällä](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md). Viimeistele CommonCryptoLib- _tai_ gx64krb5-määritys. Älä suorita molempien kirjastojen määritysvaiheita.

### <a name="set-up-gx64krb5gsskrb5-on-gateway-machine-and-the-sap-bw-server"></a>gx64krb5/gsskrb5:n määrittäminen yhdyskäytäväkoneeseen ja SAP BW -palvelimelle

> [!NOTE]
> SAP ei enää aktiivisesti tue kohteita `gx64krb5` ja `gsskrb5`. Katso lisätietoja artikkelista [SAP-huomautus 352295](https://launchpad.support.sap.com/#/notes/352295). Huomaa myös, ettei `gx64krb5` salli SSO-yhteyksiä tietoyhdyskäytävästä SAP BW -viestipalvelimiin. Vain yhteydet SAP BW -sovelluspalvelimiin sallitaan. Tätä sovelluspalvelinkohtaista rajoitusta ei ole, jos käytät [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md)-kirjastoa SNC-kirjastonasi. Myös muut SNC-kirjastot saattavat toimia BW-kertakirjautumisen kanssa, mutta Microsoft ei virallisesti tue niitä.

`gx64krb5` \ `gsskrb5` on oltava käytössä sekä asiakaskoneessa että palvelimella kertakirjautumisyhteyden muodostamiseksi yhdyskäytävän kautta, eli sekä asiakkaan että palvelimen täytyy käyttää samaa SNC-kirjastoa.

1. Lataa `gx64krb5` [SAP-huomautuksesta 2115486](https://launchpad.support.sap.com/) (SAP s-käyttäjä vaaditaan). Varmista, että sinulla on vähintään versio 1.0.11.x. Lataa myös `gsskrb5` (kirjaston 32-bittinen versio), jos haluat testata SAP GUI:n kertakirjautumisyhteyden ennen kertakirjautumisyhteyden muodostamista yhdyskäytävän kautta (suositus). 32-bittinen versio vaaditaan SAP GUI:n testaamiseen, koska SAP GUI on käytettävissä vain 32-bittisessä versiossa.

1. Sijoita `gx64krb5` sellaiseen paikkaan yhdyskäytäväkoneessa, jossa se on yhdyskäytäväpalvelun käyttäjän käytettävissä (ja myös SAP GUI:n, jos haluat testata kertakirjautumisyhteyttä SAP-kirjautumisen avulla). Sekä yhdyskäytäväpalvelun käyttäjä että Active Directory (AD) -käyttäjä, joksi palvelun käyttäjä tekeytyy, tarvitsee luku- ja suoritusoikeudet .dll-tiedostoon. Suosittelemme käyttöoikeuksien myöntämistä .dll-tiedostolle Todennetut käyttäjät -ryhmälle. Testausta varten voit myös erikseen myöntää nämä oikeudet sekä yhdyskäytäväpalvelun käyttäjälle että Active Directory -käyttäjälle, joita käytät testissä.

1. Jos BW-palvelintasi ei ole vielä määritetty kertakirjautumista varten gx64krb5/gsskrb5:n avulla, sijoita toinen kopio SAP BW -palvelinkoneeseesi sijaintiin, jota SAP BW -palvelin voi käyttää. 

1. Määritä asiakas- ja palvelin koneissa `SNC_LIB`- tai `SNC_LIB_64`-ympäristömuuttujat. Jos käytössäsi on gsskrb5, määritä `SNC_LIB`-muuttuja gsskrb5.dll-tiedoston absoluuttiseen polkuun. Jos käytössäsi on gx64krb5, määritä `SNC_LIB_64`-muuttuja gx64krb5.dll-tiedoston absoluuttiseen polkuun.

### <a name="configure-an-sap-bw-service-user-and-enable-snc-communication"></a>Määritä SAP BW -palvelun käyttäjä ja ota SNC-yhteys käyttöön

Käy läpi tämä osio, jos et ole vielä määrittänyt SAP BW -palvelinta SNC-viestintää varten (esim. kertakirjautuminen) gx64krb5/gsskrb5:n avulla.

> [!NOTE]
> Tässä osiossa oletetaan, että olet jo määrittänyt palvelun käyttäjän BW:lle ja sitonut siihen sopivan palvelun päänimen (esimerkiksi jotain, joka alkaa merkkijonolla `SAP/`).

1. SAP BW -sovelluspalvelimen käyttöoikeuksien antaminen palvelukäyttäjälle:

    1. Lisää palvelun käyttäjä SAP BW -palvelimella paikalliseen järjestelmänvalvojaryhmään. Avaa Tietokoneen hallinta -ohjelma ja kaksoisnapsauta palvelimen paikallista järjestelmänvalvojaryhmää.

        ![Näyttökuva Tietokoneen hallinta -ohjelmasta](media/service-gateway-sso-kerberos/computer-management.png)

    1. Kaksoisnapsauta paikallista järjestelmänvalvojaryhmää ja lisää sitten palvelun käyttäjä ryhmään valitsemalla **Lisää**. Valitse **Tarkista nimet** varmistaaksesi, että olet kirjoittanut nimen oikein. Valitse **OK**.

1. Määritä SAP BW -palvelimen palvelukäyttäjä siksi käyttäjäksi, joka käynnistää SAP BW -palvelinpalvelun SAP BW -palvelinkoneessa.

    1. Avaa **Suorita** ja kirjoita ”Services.msc”. Etsi palvelu, joka vastaa SAP BW -sovelluspalvelimen esiintymää. Napsauta sitä hiiren kakkospainikkeella ja valitse **Ominaisuudet**.

        ![Näyttökuva palveluista, ominaisuudet korostettuna](media/service-gateway-sso-kerberos/server-properties.png)

    1. Vaihda **Kirjaudu**-välilehteen ja muuta käyttäjä SAP BW -palvelukäyttäjäksi. Kirjoita käyttäjän salasana ja valitse **OK**.

1. Kirjaudu sisään palvelimeesi SAP-kirjautumisen kautta ja määritä seuraavat profiiliparametrit RZ10-tapahtuman avulla:

    1. Määritä snc/identity/as-profiiliparametrin arvoksi p:\<luomasi SAP BW -palvelukäyttäjä\>, esimerkiksi p:BWServiceUser@MYDOMAIN.COM. Huomaa merkkijono ”p:” ennen palvelukäyttäjän täydellistä käyttäjätunnusta. Merkkijono ei ole p:CN= kuten käytettäessä yleistä salauskirjastoa SNC-kirjastona.

    1. Määritä snc/gssapi\_lib-profiiliparametrin arvoksi \<gsskrb5.dll- tai gx64krb5.dll-tiedoston polku BW-palvelinkoneessa (käyttämäsi kirjasto määräytyy käyttöjärjestelmän bittimäärän mukaan)\>. Muista asettaa kirjasto sellaiseen paikkaan, jota SAP BW -sovelluspalvelin voi käyttää.

    1. Muuta myös seuraavia profiilin lisäparametrien arvoja niin, että ne vastaavat tarpeitasi. Huomaa, että viimeisellä viidellä asetuksella voit antaa asiakkaittesi muodostaa yhteyden SAP BW -palvelimeen SAP-kirjautumisen avulla ilman, että heille on määritetty SNC:tä.

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

1. Kun olet määrittänyt nämä profiiliparametrit, avaa palvelinkoneen SAP-hallintakonsoli ja käynnistä SAP BW -esiintymä uudelleen. Jos palvelin ei käynnisty, tarkista, että olet määrittänyt profiilin parametrit oikein. Lisätietoja profiiliparametriasetuksista löytyy [SAP-dokumentaatiosta](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm). Voit myös tarvittaessa tutustua vianmääritystietoihin, jotka esitellään myöhemmin tässä osiossa.

### <a name="map-a-sap-bw-user-to-an-active-directory-user"></a>SAP BW -käyttäjän yhdistäminen Active Directory -käyttäjään

Liitä Active Directory -käyttäjä SAP BW -sovelluspalvelimen käyttäjään ja testaa kertakirjautumisyhteyttä SAP-kirjautumisessa, jos et ole vielä tehnyt niin.

1. Kirjaudu sisään SAP BW -palvelimeen käyttämällä SAP-kirjautumista. Suorita tapahtuma SU01.

1. Syötä **Käyttäjä**-kohtaan SAP BW -käyttäjä, jolle haluat ottaa kertakirjautumisyhteydet käyttöön (edellisessä näyttökuvassa osoitamme käyttöoikeudet käyttäjälle BIUSER). Valitse **Muokkaa**-kuvake, joka löytyy SAP-kirjautumisikkunan vasemmasta yläkulmasta (kynän kuva).

    ![Näyttökuva SAP BW:n käyttäjien hallintaruudusta](media/service-gateway-sso-kerberos/user-maintenance.png)

1. Valitse **SNC**-välilehti. Kirjoita SNC-nimisyöteruutuun p:\<Active Directory -käyttäjä\>@\<toimialueesi\>. Huomaa pakollinen p:, jonka on tultava ennen Active Directory -käyttäjän täydellistä käyttäjätunnusta. Määrittämäsi Active Directory -käyttäjän on kuuluttava henkilölle tai organisaatiolle, jolle haluat myöntää kertakirjautumiskäyttöoikeuden SAP BW -sovelluspalvelimeen. Jos haluat esimerkiksi myöntää kertakirjautumiskäyttöoikeuden käyttäjälle testuser\@TESTDOMAIN.COM, syötä p:testuser@TESTDOMAIN.COM.

    ![Näyttökuva SAP BW:n käyttäjien ylläpitoruudusta](media/service-gateway-sso-kerberos/maintain-users.png)

1. Valitse **Tallenna**-kuvake (levyke) näytön vasemmasta yläkulmasta.

### <a name="test-sign-in-by-using-sso"></a>Sisäänkirjautumisen testaaminen kertakirjautumisen avulla

Varmista, että voit kirjautua palvelimeen SAP-kirjautumisen kautta kertakirjautumisen avulla sen Active Directory -käyttäjän tunnuksilla, jolle juuri myönsit kertakirjautumiskäyttöoikeuden.

1. Käytä sen Active Directory -käyttäjän tunnuksia, jolle otit kertakirjautumisen juuri käyttöön, ja kirjaudu tietokoneelle, jolla SAP-kirjautuminen on käytössä. Käynnistä SAP-kirjautuminen ja muodosta uusi yhteys.

1. Valitse **Luo uusi järjestelmän merkintä** -ikkunassa **Käyttäjän määrittämä järjestelmä** > **Seuraava**.

    ![Näyttökuva Luo uusi järjestelmän merkintä -ruudusta](media/service-gateway-sso-kerberos/new-system-entry.png)

1. Täytä tarvittavat tiedot seuraavalla sivulla, mukaan lukien sovelluspalvelin, esiintymän numero ja järjestelmätunnus. Valitse lopuksi **Valmis**.

1. Napsauta uutta yhteyttä hiiren kakkospainikkeella ja valitse **Ominaisuudet**. Valitse **Verkko**-välilehti. Kirjoita **SNC-nimi**-tekstiruutuun p:\<SAP BW -palvelukäyttäjän täydellinen käyttäjätunnus\>, kuten p:BWServiceUser@MYDOMAIN.COM. Valitse **OK**.

    ![Näyttökuva Järjestelmän merkintäominaisuudet -ruudusta](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. Kaksoisnapsauta juuri luomaasi yhteyttä muodostaaksesi kertakirjautumisyhteyden SAP BW -palvelimeen. Jos tämä yhteys toimii, siirry seuraavaan vaiheeseen. Muussa tapauksessa tarkista tässä ohjeessa olevat aiemmat vaiheet. Varmista, että suoritit ne oikein, tai tarkista alla oleva vianmääritysosio. Huomaa, että jos et voi muodostaa yhteyttä SAP BW -palvelimeen kertakirjautumisen avulla tässä kontekstissa, et voi muodostaa yhteyttä SAP BW -palvelimeen kertakirjautumisen avulla yhdyskäytäväkontekstissakaan.

### <a name="add-registry-entries-to-the-gateway-machine"></a>Rekisterimerkintöjen lisääminen yhdyskäytäväkoneeseen

Lisää tarvittavat rekisterimerkinnät sen tietokoneen rekisteriin, johon yhdyskäytävä on asennettu, sekä niihin tietokoneisiin, joiden on tarkoitus olla yhteydessä Power BI Desktopiin. Suorita seuraavat komennot:

1. REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

1. REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

### <a name="add-a-new-sap-bw-application-server-data-source-to-the-power-bi-service-or-edit-an-existing-one"></a>Uuden SAP BW -sovelluspalvelimen tietolähteen lisääminen Power BI -palveluun tai aiemmin luodun tietolähteen muokkaaminen

1. Kirjoita tietolähteen määritysikkunassa sovelluspalvelimen **Isäntänimi**, **Järjestelmänumero** ja **asiakastunnus** samalla tavalla kuin silloin, kun kirjaudut sisään SAP BW -palvelimeesi Power BI Desktopin kautta.

1. Syötä **SNC-kumppanin nimi** -kenttään p: \<SPN, jonka yhdistit SAP BW -palvelukäyttäjään\>. Esimerkiksi jos SPN on SAP/BWServiceUser@MYDOMAIN.COM, syötä p:SAP/BWServiceUser@MYDOMAIN.COM **SNC-kumppanin nimi** -kenttään.

1. Valitse SNC-kirjastoksi **SNC_LIB** tai **SNC_LIB_64**. Varmista, että yhdyskäytäväkoneen SNC_LIB_64 osoittaa gx64krb5.dll-tiedostoon. Vaihtoehtoisesti voit valita Mukautettu-vaihtoehdon ja antaa absoluuttisen polun gx64krb5.dll-tiedostolle (yhdyskäytäväkoneessa).

1. Valitse **Käytä kertakirjautumista Kerberosin kautta DirectQuery-kyselyille** -ruutu ja valitse **Käytä**. Jos testiyhteys ei toimi, tarkista, että suoritit aiemmat asennus- ja määritysvaiheet oikein.

1. [Power BI -raportin suorittaminen](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>Vianmääritys

### <a name="troubleshoot-gx64krb5gsskrb5-configuration"></a>gx64krb5/gsskrb5-määrityksen vianmääritys

Jos kohtaat ongelmia, toimi seuraavasti määrittääksesi viat gx64krb5/gsskrb5-asennuksessa ja SAP-kirjautumisen kertakirjautumisyhteyksissä.

* Palvelimen lokien tarkastelemisesta (...work\dev\_w0 palvelinkoneessa) voi olla hyötyä, kun yrität määrittää gx64krb5/gsskrb5-asennuksen yhteydessä ilmeneviä virheitä. Tästä on hyötyä erityisesti, jos SAP BW -palvelin ei käynnisty profiiliparametrien muuttamisen jälkeen.

* Jos et pysty käynnistämään SAP BW -palvelua kirjautumisvirheen vuoksi, on mahdollista, että syötit väärän salasanan, kun määritit SAP BW:n aloituskäyttäjää. Vahvista salasana kirjautumalla sisään Active Directory -ympäristössäsi olevaan tietokoneeseen SAP BW -palvelukäyttäjänä.

* Jos saat SQL-tunnistetietoihin liittyviä virheilmoituksia, jotka estävät palvelinta käynnistymästä, varmista, että olet myöntänyt palvelukäyttäjälle käyttöoikeuden SAP BW -tietokantaan.

* Saatat saada seuraavan sanoman: ”(GSS-API) määritetty kohde on tuntematon tai siihen ei saada yhteyttä”. Tämä tarkoittaa yleensä sitä, että määritetty SNC-nimi on virheellinen. Muista, että asiakassovelluksessa tulee käyttää palvelukäyttäjän täydellisen käyttäjätunnuksen lisäksi vain merkkijonoa ”p:” merkkijonon ”p:CN=” tai vastaavien sijaan.

* Saatat saada seuraavan sanoman: ”(GSS-API) Annettiin virheellinen nimi”. Varmista, että palvelimen SNC-identiteetin profiiliparametrin arvo on ”p:”.

* Voit saada seuraavan sanoman: ”(SNC-virhe) määritettyä moduulia ei löytynyt”. Tämä johtuu yleensä siitä, että `gsskrb5.dll/gx64krb5.dll` sijaitsee paikassa, joka edellyttää korkeita (järjestelmänvalvojan) käyttöoikeuksia.

### <a name="troubleshoot-gateway-connectivity-issues"></a>Yhdyskäytävän yhteysongelmien vianmääritys

1. Tarkista yhdyskäytävän lokit. Avaa yhdyskäytävän kokoonpanosovellus ja valitse **Diagnostiikka** > **Vie lokit**. Viimeisimmät virheet ovat lokitiedostojen alareunassa.

    ![Näyttökuva paikallisen tietoyhdyskäytävän sovelluksesta, jossa diagnostiikka korostettuna](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. Ota SAP BW -jäljitys käyttöön ja tarkista luodut lokitiedostot. Käytettävissä on useita erilaisia SAP BW -jäljitysvaihtoehtoja. Lisätietoja löytyy SAP-dokumentaatiosta.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja **paikallisesta tietoyhdyskäytävästä** ja **DirectQuerysta** on seuraavissa resursseissa:

* [Mikä paikallinen tietoyhdyskäytävä on?](/data-integration/gateway/service-gateway-getting-started)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
