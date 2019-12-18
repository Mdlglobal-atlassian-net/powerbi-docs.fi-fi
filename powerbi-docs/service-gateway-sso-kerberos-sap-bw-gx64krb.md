---
title: Kerberoksen käyttäminen kertakirjautumista (SSO) varten SAP BW:ssä gx64krb5:n avulla
description: SAP BW -palvelimen määrittäminen ottamaan kertakirjautuminen käyttöön Power BI -palvelussa gx64krb5:n avulla
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 6c8b62cf798d2fbbd09dab0603d216448d04487c
ms.sourcegitcommit: 5bb62c630e592af561173e449fc113efd7f84808
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/11/2019
ms.locfileid: "75000131"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-bw-using-gx64krb5"></a>Kerberoksen käyttäminen kertakirjautumista (SSO) varten SAP BW:ssä gx64krb5:n avulla

Tässä artikkelissa kerrotaan, miten voit määrittää SAP BW -tietolähteesi ottamaan käyttöön kertakirjautumisen Power BI -palvelusta gx64krb5:n avulla.

> [!NOTE]
> Voit suorittaa tämän artikkelin vaiheet [Kerberos-kertakirjautumisen määrittäminen](service-gateway-sso-kerberos.md) -kohdan vaiheiden lisäksi, jotta voit ottaa käyttöön kertakirjautumispohjaisen päivityksen SAP BW:n sovelluspalvelinpohjaisia raporteissa Power BI -palvelussa. Microsoft suosittelee kuitenkin CommonCryptoLibin käyttämistä SNC-kirjastona gx64krb5:n sijasta. SAP ei enää tue gx64krb5:ttä, ja sen määrittämiseen tarvittavat vaiheet yhdyskäytävää varten ovat huomattavasti monimutkaisempia CommonCryptoLibiin verrattuna. Lisätietoa kertakirjautumisen määrittämisestä CommonCryptoLibin avulla on artikkelissa [SAP BW:n määrittäminen kertakirjautumista varten CommonCryptoLibiä käyttämällä](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md). Käytä sen sijaan CommonCryptoLib- _tai_ gx64krb5-kirjastoa SNC-kirjastona. Älä suorita molempien kirjastojen määritysvaiheita.

Tämä opas on kattava. Jos olet jo suorittanut joitakin kuvattuja vaiheita, voit ohittaa ne. Olet esimerkiksi saattanut jo määrittää SAP BW -palvelimesi kertakirjautumista varten gx64krb5:n avulla.

## <a name="set-up-gx64krb5-on-the-gateway-machine-and-the-sap-bw-server"></a>gx64krb5:n määrittäminen yhdyskäytäväkoneeseen ja SAP BW -palvelimelle

> [!NOTE]
> SAP ei enää tue gx64krb5-kirjastoa. Katso lisätietoja artikkelista [SAP-huomautus 352295](https://launchpad.support.sap.com/#/notes/352295). Huomaathan, että gx64krb5 ei salli kertakirjautumisyhteyksiä tietoyhdyskäytävistä SAP BW -viestipalvelimiin. Vain yhteydet SAP BW -sovelluspalvelimiin sallitaan. Tätä rajoitusta ei ole, jos käytät [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md)-kirjastoa SNC-kirjastonasi. Vaikka muut SNC-kirjastot saattavat toimia BW-kertakirjautumisen kanssa, Microsoft ei virallisesti tue niitä.

gx64krb5-kirjastoa on käytettävä sekä asiakaskoneessa että palvelimella SSO-yhteyden muodostamiseksi yhdyskäytävän kautta. Sekä asiakkaan että palvelimen on siis käytettävä samaa SNC-kirjastoa.

1. Lataa gx64krb5.dll [SAP-huomautuksesta 2115486](https://launchpad.support.sap.com/) (SAP s-käyttäjä vaaditaan). Varmista, että sinulla on vähintään versio 1.0.11.x. Lataa myös gsskrb5.dll (kirjaston 32-bittinen versio), jos haluat testata SAP GUI:n kertakirjautumisyhteyden ennen kertakirjautumisyhteyden muodostamista yhdyskäytävän kautta (suositus). 32-bittinen versio vaaditaan SAP GUI:n testaamiseen, koska SAP GUI on vain 32-bittisessä versiossa.

1. Sijoita gx64krb5.dll yhdyskäytäväkoneesi sijaintiin, jota yhdyskäytäväpalvelusi käyttäjä voi käyttää. Jos haluat testata kertakirjautumisyhteyttä SAP-käyttöliittymän avulla, sijoita kopio gsskrb5.dll-tiedostosta koneeseesi ja aseta **SNC_LIB**-ympäristömuuttuja osoittamaan siihen. Sekä yhdyskäytäväpalvelun käyttäjä että Active Directory (AD) -käyttäjä, joksi palvelun käyttäjä tekeytyy, tarvitsee luku- ja suoritusoikeudet gx64krb5.dll-kopioon. Suosittelemme käyttöoikeuksien myöntämistä .dll-tiedostolle Todennetut käyttäjät -ryhmälle. Testausta varten voit myös erikseen myöntää nämä oikeudet sekä yhdyskäytäväpalvelun käyttäjälle että Active Directory -käyttäjälle, joita käytät testissä.

1. Jos BW-palvelintasi ei ole vielä määritetty kertakirjautumista varten gx64krb5.dll-tiedoston avulla, sijoita toinen .dll-tiedoston kopio SAP BW -palvelinkoneeseesi sijaintiin, jota SAP BW -palvelin voi käyttää. 

    Lisätietoja gx64krb5.dll-tiedoston määrittämisestä käyttöön SAP BW -palvelimen kanssa löytyy [SAP-dokumentaatiosta](https://launchpad.support.sap.com/#/notes/2115486) (s-käyttäjä vaaditaan).

1. Määritä asiakas- ja palvelinkoneissa **SNC_LIB-** ja **SNC_LIB_64**-ympäristömuuttujat: 
    - Jos käytössäsi on gsskrb5.dll, määritä **SNC_LIB**-muuttuja sen absoluuttiseen polkuun. 
    - Jos käytössäsi on gx64krb5.dll, määritä **SNC_LIB_64**-muuttuja sen absoluuttiseen polkuun.

## <a name="configure-an-sap-bw-service-user-and-enable-snc-communication-on-the-bw-server"></a>Määritä SAP BW -palvelun käyttäjä ja ota SNC-yhteys käyttöön BW-palvelimessa

Käy läpi tämä osio, jos et ole vielä määrittänyt SAP BW -palvelinta SNC-viestintää varten (esimerkiksi kertakirjautuminen) gx64krb5:n avulla.

> [!NOTE]
> Tässä osiossa oletetaan, että olet jo määrittänyt palvelun käyttäjän BW:lle ja sitonut siihen sopivan palvelun päänimen (eli nimen, joka alkaa merkkijonolla *SAP/* ).

1. SAP BW -sovelluspalvelimen käyttöoikeuksien antaminen palvelukäyttäjälle:

    1. Lisää palvelun käyttäjä SAP BW -palvelimella paikalliseen järjestelmänvalvojaryhmään. Avaa **Tietokoneen hallinta** -ohjelma ja määritä palvelimen paikallinen järjestelmänvalvojaryhmä. 

        ![Tietokoneen hallinta -ohjelma](media/service-gateway-sso-kerberos/computer-management.png)

    1. Kaksoisnapsauta paikallista järjestelmänvalvojaryhmää ja lisää sitten palvelun käyttäjä ryhmään valitsemalla **Lisää**. 

    1. Valitse **Tarkista nimet** varmistaaksesi, että olet kirjoittanut nimen oikein, ja valitse sitten **OK**.

1. Määritä SAP BW -palvelimen palvelukäyttäjä siksi käyttäjäksi, joka käynnistää SAP BW -palvelinpalvelun SAP BW -palvelinkoneessa:

    1. Avaa **Suorita** ja kirjoita sitten **Services.msc**. 

    1. Etsi SAP BW -sovelluspalvelinesiintymääsi vastaava palvelu, napsauta sitä hiiren kakkospainikkeella ja valitse sitten **Ominaisuudet**.

        ![Näyttökuva palveluista, ominaisuudet korostettuna](media/service-gateway-sso-kerberos/server-properties.png)

    1. Vaihda **Kirjaudu**-välilehteen ja muuta käyttäjä SAP BW -palvelukäyttäjäksi. 

    1. Kirjoita käyttäjän salasana ja valitse sitten **OK**.

1. Kirjaudu sisään palvelimeesi SAP-kirjautumisen kautta ja määritä seuraavat profiiliparametrit RZ10-tapahtuman avulla:

    1. Määritä **snc/identity/as**-profiiliparametrin arvoksi *p:&lt;SAP BW -palvelukäyttäjä&gt;* . Esimerkiksi *p:BWServiceUser\@MYDOMAIN.COM*. Huomaathan, että palvelun käyttäjän täydellisen käyttäjätunnuksen edessä on *p:* , kun taas etuliitettä *p:CN =* käytetään, jos SNC-kirjastona on CommonCryptoLib.

    1. Määritä **snc/gssapi\_lib** -profiiliparametrin arvoksi *&lt;polku gx64krb5.dll-tiedostoon BW-palvelimessa&gt;* . Aseta kirjasto sellaiseen paikkaan, jota SAP BW -sovelluspalvelin voi käyttää.

    1. Muuta seuraavia profiilin lisäparametrien arvoja niin, että ne vastaavat tarpeitasi. Viimeisellä viidellä asetuksella voit antaa asiakkaittesi muodostaa yhteyden SAP BW -palvelimeen SAP-kirjautumisen avulla ilman, että heille on määritetty SNC:tä.

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

    1. Määritä **snc/enable**-omaisuuden arvoksi 1.

1. Kun olet määrittänyt nämä profiiliparametrit, avaa palvelinkoneen SAP-hallintakonsoli ja käynnistä SAP BW -esiintymä uudelleen. 

   Jos palvelin ei käynnisty, tarkista, että olet määrittänyt profiilin parametrit oikein. Lisätietoja profiiliparametriasetuksista löytyy [SAP-dokumentaatiosta](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm). Voit myös tutustua tämän artikkelin [Vianmääritys](#troubleshooting)-osioon.

## <a name="map-an-sap-bw-user-to-an-active-directory-user"></a>SAP BW -käyttäjän yhdistäminen Active Directory -käyttäjään

Liitä Active Directory -käyttäjä SAP BW -sovelluspalvelimen käyttäjään ja testaa kertakirjautumisyhteyttä SAP-kirjautumisessa, jos et ole vielä tehnyt niin.

1. Kirjaudu sisään SAP BW -palvelimeen käyttämällä SAP-kirjautumista. Suorita tapahtuma SU01.

1. **Käyttäjälle**: anna SAP BW -käyttäjä, jolle haluat ottaa käyttöön kertakirjautumisen. Valitse **Muokkaa**-kuvake (kynäkuvake), joka löytyy SAP-kirjautumisikkunan vasemmasta yläkulmasta.

    ![SAP BW:n käyttäjien hallintaruutu](media/service-gateway-sso-kerberos/user-maintenance.png)

1. Valitse **SNC**-välilehti. Kirjoita SNC-nimisyöteruutuun *p:&lt;Active Directory -käyttäjä&gt;@&lt;toimialueesi&gt;* . SNC-nimessä ennen Active Directory -käyttäjän täydellistä käyttäjätunnusta on oltava *p:* . Huomaathan, että UPN:ssä kirjainkoko on merkitsevä.

   Määrittämäsi Active Directory -käyttäjän on kuuluttava henkilölle tai organisaatiolle, jolle haluat myöntää kertakirjautumiskäyttöoikeuden SAP BW -sovelluspalvelimeen. Jos haluat esimerkiksi myöntää kertakirjautumiskäyttöoikeuden käyttäjälle testuser\@TESTDOMAIN.COM, kirjoita *p:testuser\@TESTDOMAIN.COM*.

    ![SAP BW:n käyttäjien ylläpitoruutu](media/service-gateway-sso-kerberos/maintain-users.png)

1. Valitse **Tallenna**-kuvake (levykkeen kuva) näytön vasemmasta yläkulmasta.

## <a name="test-sign-in-via-sso"></a>Testaa sisäänkirjautuminen kertakirjautumisen kautta

Varmista, että voit kirjautua palvelimeen SAP-kirjautumisen kautta kertakirjautumisen avulla sen Active Directory -käyttäjän tunnuksilla, jolle myönsit kertakirjautumiskäyttöoikeuden:

1. Käytä sen Active Directory -käyttäjän tunnuksia, jolle otit kertakirjautumisen juuri käyttöön, ja kirjaudu toimialueellasi tietokoneelle, jossa SAP-kirjautuminen on käytössä. Käynnistä SAP-kirjautuminen ja muodosta uusi yhteys.

1. Kopioi aiemmin lataamasi gsskrb5.dll-tiedosto sijaintiin koneessa, johon kirjauduit sisään. Määritä **SNC_LIB**-ympäristömuuttuja tämän sijainnin absoluuttiseen polkuun.

1. Käynnistä SAP-kirjautuminen ja muodosta uusi yhteys.

1. Valitse **Luo uusi järjestelmän merkintä** -ikkunassa **Käyttäjän määrittämä järjestelmä** ja valitse sitten **Seuraava**.

    ![Luo uusi järjestelmän merkintä -näyttö](media/service-gateway-sso-kerberos/new-system-entry.png)

1. Täytä tarvittavat tiedot seuraavalla sivulla, mukaan lukien sovelluspalvelin, esiintymän numero ja järjestelmätunnus. Valitse lopuksi **Valmis**.

1. Napsauta hiiren kakkospainikkeella uutta yhteyttä, valitse **Ominaisuudet** ja valitse sitten **Verkko**-välilehti. 

1. Kirjoita **SNC-nimi**-tekstiruutuun *p:&lt;SAP BW -palvelukäyttäjän täydellinen käyttäjätunnus&gt;* . Esimerkiksi *p:BWServiceUser\@MYDOMAIN.COM*. Valitse **OK**.

    ![Järjestelmän merkintäominaisuudet -näyttö](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. Kaksoisnapsauta juuri luomaasi yhteyttä muodostaaksesi kertakirjautumisyhteyden SAP BW -palvelimeen. 

   Jos tämä yhteys toimii, jatka seuraavaan osioon. Muussa tapauksessa tarkista tässä ohjeessa olevat aiemmat vaiheet. Varmista, että suoritit ne oikein, tai tarkista [Vianmääritys](#troubleshooting)-osio. Jos et voi muodostaa yhteyttä SAP BW -palvelimeen kertakirjautumisen avulla tässä kontekstissa, et voi muodostaa yhteyttä SAP BW -palvelimeen kertakirjautumisen avulla yhdyskäytäväkontekstissakaan.

## <a name="add-registry-entries-to-the-gateway-machine"></a>Rekisterimerkintöjen lisääminen yhdyskäytäväkoneeseen

Lisää tarvittavat rekisterimerkinnät sen tietokoneen rekisteriin, johon yhdyskäytävä on asennettu, ja niihin tietokoneisiin, joiden on tarkoitus olla yhteydessä Power BI Desktopiin. Jos haluat lisätä nämä rekisterimerkinnät, suorita seuraavat komennot:

- ```REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG_DWORD /d 1 /f```

- ```REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG_DWORD /d 1 /f```

## <a name="add-a-new-sap-bw-application-server-data-source-to-the-power-bi-service-or-edit-an-existing-one"></a>Uuden SAP BW -sovelluspalvelimen tietolähteen lisääminen Power BI -palveluun tai aiemmin luodun tietolähteen muokkaaminen

1. Kirjoita tietolähteen määritysikkunassa SAP BW -sovelluspalvelimen **Isäntänimi**, **Järjestelmänumero** ja **asiakastunnus** samalla tavalla kuin silloin, kun kirjaudut sisään SAP BW -palvelimeesi Power BI Desktopin kautta.

1. Syötä **SNC-kumppanin nimi** -kenttään *p:&lt;SPN, jonka yhdistit SAP BW -palvelukäyttäjään&gt;* . Jos SPN on esimerkiksi SAP/BWServiceUser\@MYDOMAIN.COM, kirjoita *p:SAP/BWServiceUser\@MYDOMAIN.COM* **SNC-kumppanin nimi** -kenttään.

1. Valitse SNC-kirjastoksi **SNC\_LIB** tai **SNC\_LIB\_64**. Varmista, että yhdyskäytäväkoneen **SNC\_LIB\_64** osoittaa gx64krb5.dll-tiedostoon. Vaihtoehtoisesti voit valita **Mukautettu**-vaihtoehdon ja antaa absoluuttisen polun gx64krb5.dll-tiedostolle yhdyskäytäväkoneessa.

1. Valitse **Käytä kertakirjautumista Kerberosin kautta DirectQuery-kyselyille**, ja valitse sitten **Käytä**. Jos testiyhteys ei toimi, tarkista, että suoritit aiemmat asennus- ja määritysvaiheet oikein.

1. [Power BI -raportin suorittaminen](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>Vianmääritys

### <a name="troubleshoot-gx64krb5-configuration"></a>gx64krb5-määrityksen vianmääritys

Jos kohtaat jonkin seuraavista ongelmista, toimi seuraavasti määrittääksesi viat gx64krb5-asennuksessa ja kertakirjautumisyhteyksissä:

* Kohtaat virheitä gx64krb5-määrityksen aikana. Esimerkiksi SAP BW -palvelin ei käynnisty, kun olet muuttanut profiiliparametreja. Tarkastele palvelinlokeja (…work\dev\_w0 palvelinkoneella) määrittääksesi virheiden syyn. 

* Et voi käynnistää SAP BW -palvelua sisäänkirjautumisvirheen vuoksi. Olet saattanut antaa väärän salasanan määrittäessäsi SAP BW:n *aloituskäyttäjää*. Vahvista salasana kirjautumalla sisään SAP BW -palvelukäyttäjänä Active Directory -ympäristössäsi olevaan tietokoneeseen.

* Saat taustalla oleviin tietolähteen tunnistetietoihin (esimerkiksi SQL Serveriin) liittyviä virheilmoituksia, jotka estävät palvelinta käynnistymästä, varmista, että olet myöntänyt palvelukäyttäjälle käyttöoikeuden SAP BW -tietokantaan.

* Näyttöön tulee seuraava sanoma: *(GSS-API) määritetty kohde on tuntematon tai siihen ei saada yhteyttä*. Tämä virhe tarkoittaa yleensä sitä, että määritetty SNC-nimi on virheellinen. Muista, että asiakassovelluksessa tulee käyttää palvelukäyttäjän täydellisen käyttäjätunnuksen lisäksi vain merkkijonoa *p:* merkkijonon *p:CN=* sijaan.

* Näyttöön tulee seuraava sanoma: *(GSS-API) Annettiin virheellinen nimi*. Varmista, että palvelimen SNC-identiteetin profiiliparametrin arvo on *p:* .

* Näyttöön tulee seuraava sanoma: *(SNC-virhe) määritettyä moduulia ei löytynyt*. Tämä virhe johtuu usein siitä, että olet sijoittanut gx64krb5.dll-tiedoston sijaintiin, jonka käyttö edellyttää laajennettuja käyttöoikeuksia (järjestelmänvalvojan oikeuksia).

### <a name="troubleshoot-gateway-connectivity-issues"></a>Yhdyskäytävän yhteysongelmien vianmääritys

1. Tarkista yhdyskäytävän lokit. Avaa yhdyskäytävän kokoonpanosovellus ja valitse **Diagnostiikka** ja **Vie lokit**. Viimeisimmät virheet ovat lokitiedostojen lopussa.

    ![Paikallisen tietoyhdyskäytävän sovellus, jossa diagnostiikka korostettuna](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. Ota SAP BW -jäljitys käyttöön ja tarkista luodut lokitiedostot. Käytettävissä on useita erilaisia SAP BW -jäljitysvaihtoehtoja (esimerkiksi CPIC-jäljitys):

   a. Jos haluat ottaa CPIC-jäljityksen käyttöön, määritä kaksi ympäristömuuttujaa: **CPIC\_TRACE** ja **CPIC\_TRACE\_DIR**.

      Ensimmäinen muuttuja määrittää jäljitystason, ja toinen muuttuja määrittää jäljitystiedoston hakemiston. Hakemiston on oltava sijainti, johon Todennetut käyttäjät -ryhmän jäsenet voivat kirjoittaa. 
 
    b. Määritä **CPIC\_TRACE** arvoon *3* ja **CPIC\_TRACE\_DIR** mihin tahansa hakemistoon, jonne haluat kirjoittaa jäljitystiedostot. Esimerkki:

      ![CPIC-jäljitys](media/service-gateway-sso-kerberos/cpic-tracing.png)

    c. Yritä toistaa ongelma ja varmista, että **CPIC\_TRACE\_DIR** sisältää jäljitystiedostoja. 
    
    d. Selvitä estämisen syy tarkastelemalla jäljitystiedostojen sisältöä. Saatat esimerkiksi huomata, että gx64krb5. dll-tiedosto ei latautunut oikein tai että SSO-yhteysyrityksen käynnisti jokin muu Active Directory ‑käyttäjä kuin mitä odotit.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja paikallisesta tietoyhdyskäytävästä ja DirectQuerysta on seuraavissa resursseissa:

* [Mikä paikallinen tietoyhdyskäytävä on?](/data-integration/gateway/service-gateway-onprem)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
