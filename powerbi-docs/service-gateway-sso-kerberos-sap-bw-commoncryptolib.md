---
title: Käytä Kerberos-SSO-kertakirjautumista SAP BW:hen CommonCryptoLibin (sapcrypto. dll) avulla
description: SAP BW -palvelimen määrittäminen ottamaan kertakirjautuminen käyttöön Power BI -palvelussa CommonCryptoLibin (sapcrypto.dll) avulla
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 6c4f2b0d8856d5e68e02b9b33cf393ca85ecb580
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/18/2019
ms.locfileid: "71106281"
---
# <a name="use-kerberos-single-sign-on-for-sso-to-sap-bw-using-commoncryptolib-sapcryptodll"></a>Käytä Kerberos-SSO-kertakirjautumista SAP BW:hen CommonCryptoLibin (sapcrypto. dll) avulla

Tässä artikkelissa kerrotaan, miten voit määrittää SAP BW -palvelimesi ottamaan käyttöön kertakirjautumisen Power BI -palvelusta CommonCryptoLibin (sapcrypto.dll) avulla.

> [!NOTE]
> Suorita tässä artikkelissa olevat vaiheet [Kerberos-kertakirjautumisen määrittäminen](service-gateway-sso-kerberos.md) -kohdan vaiheiden lisäksi, ennen kuin yrität päivittää SAP BW -pohjaista raporttia, jossa on käytössä Kerberos-kertakirjautuminen. Käyttämällä CommonCryptoLibiä SNC-kirjastonasi mahdollistaa kertakirjautumisyhteydet sekä SAP BW -sovelluspalvelimiin että SAP BW -viestipalvelimiin.

## <a name="configure-sap-bw-server-to-enable-sso-using-commoncryptolib"></a>SAP BW -palvelimen määrittäminen kertakirjautumista varten CommonCryptoLibiä käyttämällä

> [!NOTE]
> Paikallinen tietoyhdyskäytävä on 64-bittinen ohjelmisto, ja se edellyttää siksi 64-bittistä versiota CommonCryptoLibistä (sapcrypto. dll). Jos suunnittelet kertakirjautumisyhteyden testaamista SAP BW -palvelimeen SAP GUIssa ennen kertakirjautumisyhteyden muodostamista yhdyskäytävän kautta (suositus), tarvitset myös CommonCryptoLibin 32-bittisen version, koska SAP GUI on 32-bittinen ohjelmisto.

1. Varmista, että BW-palvelimesi on määritetty oikein Kerberos-kertakirjautumista varten CommonCryptoLibin avulla. Jos näin on, sinun pitäisi päästä BW-palvelimeen kertakirjautumista käyttämällä (joko suoraan tai SAP BW -viestipalvelimen kautta) SAP GUIn kaltaisella SAP-työkalulla, joka on määritetty käyttämään CommonCryptoLibiä. Lisätietoja asennusvaiheista on kohdassa [SAP-kertakirjautuminen: Todentaminen Kerberosin/SPNEGOn kanssa](https://blogs.sap.com/2017/07/27/sap-single-sign-on-authenticate-with-kerberosspnego/). BW-palvelimesi tulee käyttää CommonCryptoLibiä sen SNC-kirjastona, ja sillä pitää olla SNC-nimi, joka alkaa merkkijonolla "CN=", esimerkiksi "CN=BW1". Lisätietoja SNC-nimen vaatimuksista on kohdassa [Kerberos-määrityksen SNC-parametrit](https://help.sap.com/viewer/df185fd53bb645b1bd99284ee4e4a750/3.0/en-US/360534094511490d91b9589d20abb49a.html) (erityisesti snc/identity/as parameter).

1. Jos et ole vielä tehnyt niin, asenna [SAP .NET Connectorin](https://support.sap.com/en/product/connectors/msnet.html) x64-versio tietokoneeseen, johon yhdyskäytävä on asennettu. Voit tarkistaa, onko osa asennettu, yrittämällä muodostaa yhteyden BW-palvelimeen Power BI Desktopissa. Jos et voi muodostaa yhteyttä 2.0-toteutuksen avulla, .NET Connectoria ei ole asennettu.

1. Varmista, että SAP Secure Login Client (SLC) ei ole käynnissä tietokoneessa, johon yhdyskäytävä on asennettu. SLC tallentaa Kerberos-liput välimuistiin tavalla, joka voi häiritä yhdyskäytävän kykyä käyttää Kerberos-kertakirjautumista. Jos SLC on asennettu, poista sen asennus tai varmista, että suljet SAP Secure Login Clientin: napsauta hiiren kakkospainikkeella ilmaisinalueella olevaa kuvaketta ja valitse Kirjaudu ulos ja Lopeta, ennen kuin yrität kertakirjautumisyhteyttä yhdyskäytävän avulla. SLC:n käyttöä ei tueta Windows Server -koneissa. Katso lisätietoja artikkelista [SAP-huomautus 2780475](https://launchpad.support.sap.com/#/notes/2780475) (s-käyttäjä vaaditaan).

    ![SAP Secure Login Client](media/service-gateway-sso-kerberos/sap-secure-login-client.png)

    Jos poistat SLC-asennuksen tai valitset **Kirjaudu ulos** ja **Lopeta**, avaa cmd-ikkuna ja kirjoita `klist purge` poistaaksesi välimuistissa olevat Kerberos-liput, ennen kuin yrität kertakirjautumisyhteyden muodostamista yhdyskäytävän kautta.

1. Lataa 64-bittinen CommonCryptoLib (sapcrypto.dll) -versio **8.5.25 tai uudempi** SAP Launchpadista ja kopioi se yhdyskäytäväkoneesi kansioon. Luo samassa hakemistossa, johon kopioit sapcrypto.dll-tiedoston, tiedosto nimeltä sapcrypto.ini käyttäen seuraavaa sisältöä:

    ```
    ccl/snc/enable_kerberos_in_client_role = 1
    ```

    .ini-tiedosto sisältää CommonCryptoLibin edellyttämät määritystiedot, jotka mahdollistavat kertakirjautumisen yhdyskäytäväskenaariossa.

    > [!NOTE]
    > Nämä tiedostot on tallennettava samaan sijaintiin. Toisin sanoen kohteen _/path/to/sapcrypto/_ tulee sisältää sekä sapcrypto.ini että sapcrypto.dll.

    Sekä yhdyskäytäväpalvelun käyttäjä että Active Directory (AD) -käyttäjä, joksi palvelun käyttäjä tekeytyy, tarvitsee luku- ja suoritusoikeudet molempiin tiedostoihin. Suosittelemme käyttöoikeuksien myöntämistä sekä .ini- että .dll-tiedostoille Todennetut käyttäjät -ryhmälle. Testausta varten voit myös erikseen myöntää nämä oikeudet sekä yhdyskäytäväpalvelun käyttäjälle että Active Directory -käyttäjälle, joita käytät testissä. Alla olevassa näyttökuvassa olemme myöntäneet Todennetut käyttäjät -ryhmälle **luku- &amp; suoritus**oikeudet sapcrypto.dll-kohteelle:

    ![Todennetut käyttäjät](media/service-gateway-sso-kerberos/authenticated-users.png)

1. Jos sinulla ei ole SAP BW -palvelimen tietolähdettä, lisää tietolähde Power BI -palvelun **Yhdyskäytävien hallinta** -sivulla. Jos sinulla on jo yhdyskäytävään liitetty BW-tietolähde, jonka läpi haluat SSO-yhteyden virtaavan, valmistaudu muokkaamaan sitä. Valitse **SAP Business Warehouse** **tietolähteen tyypiksi**, jos haluat luoda kertakirjautumisyhteyden BW-sovelluspalvelimeen. Valitse **Sap Business Warehouse -viestipalvelin**, jos haluat luoda kertakirjautumisyhteyden BW-viestipalvelimeen.

    **SNC-kirjaston** kohdalla valitse joko **SNC\_LIB- tai SNC\_LIB\_64-ympäristömuuttuja** tai **Mukautettu**. Jos valitset **SNC\_LIB**-vaihtoehdon aseta **SNC\_LIB\_64**-ympäristömuuttujan arvo yhdyskäytäväkoneessa sapcrypto.dll-kohteen 64-bittisen version absoluuttiseen polkuun, esim. C:\Users\Test\Desktop\sapcrypto.dll. Jos valitset **Mukautettu**, liitä sapcrypto.dll-kohteen absoluuttinen polku Mukautetun SNC-kirjaston polku -kenttään, joka näkyy **Yhdyskäytävien hallinta** -sivulla. Jos kyseessä on **SNC-kumppanin nimi**, anna BW-palvelimen SNC-nimi. Varmista **Lisäasetukset** -kohdassa, että **Käytä DirectQuery-kyselyissä kertakirjautumista Kerberoksen kautta** -kohta on valittuna. Muut kentät tulee täyttää samalla tavalla kuin Windows-todentamisen yhteyttä muodostettaessa PBI Desktopista.

1. Luo CCL\_PROFILE-järjestelmän ympäristömuuttuja ja osoita sitä sapcrypto.ini-tiedostossa:

    ![CCL\_PROFILE-järjestelmän ympäristömuuttuja](media/service-gateway-sso-kerberos/ccl-profile-variable.png)

    Muista, että sapcrypto.dll- ja. -ini-tiedostojen on sijaittava samassa sijainnissa. Yllä olevassa esimerkissä, jossa sapcrypto.ini sijaitsee työpöydällä, sapcrypto.dll-tiedoston pitäisi sijaita myös työpöydällä.

1. Käynnistä yhdyskäytäväpalvelu uudelleen:

    ![Käynnistä yhdyskäytäväpalvelu uudelleen](media/service-gateway-sso-kerberos/restart-gateway-service.png)

1. [Power BI -raportin suorittaminen](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>Vianmääritys

Jos et pysty päivittämään raporttia Power BI -palvelussa, voit käyttää ongelman diagnosoinnissa yhdyskäytävän jäljitystä, CPIC-jäljitystä ja CommonCryptoLib-jäljitystä. CPIC-jäljitys ja CommonCryptoLib ovat SAP-tuotteita, joten Microsoft ei tarjoa niille suoraa tukea. Active Directory -käyttäjien kohdalla, joille myönnetään BW-kertakirjautumisoikeus, jotkin Active Directory -määritykset saattavat edellyttää, että käyttäjät ovat Järjestelmänvalvojat-ryhmän jäseniä koneessa, johon yhdyskäytävä on asennettu.

1. **Yhdyskäytävän lokit:** Voit vain toistaa ongelman avaamalla [yhdyskäytäväsovelluksen](https://docs.microsoft.com/data-integration/gateway/service-gateway-app), siirtymällä **Diagnostiikka**-välilehteen ja valitsemalla **Vie lokit**:

    ![Vie yhdyskäytävän lokit](media/service-gateway-sso-kerberos/export-gateway-logs.png)

1. **CPIC-jäljitys:** Jos haluat ottaa CPIC-jäljityksen käyttöön, määritä kaksi ympäristömuuttujaa: CPIC\_TRACE ja CPIC\_TRACE\_DIR. Ensimmäinen muuttuja määrittää jäljitystason, ja toinen muuttuja määrittää jäljitystiedoston hakemiston. Hakemiston on oltava sijainti, johon Todennetut käyttäjät -ryhmän jäsenet voivat kirjoittaa. Määritä CPIC\_TRACE arvoon 3 ja CPIC\_TRACE\_DIR mihin tahansa hakemistoon, jonne haluat kirjoittaa jäljitystiedostot.

    ![CPIC-jäljitys](media/service-gateway-sso-kerberos/cpic-tracing.png)

    Yritä toistaa ongelma ja tarkista, että CPIC\_TRACE\_DIR sisältää jäljitystiedostoja.

1. **CommonCryptoLib-jäljitys:** Ota CommonCryptoLib-jäljitys käyttöön lisäämällä kaksi riviä aiemmin luomaasi sapcrypto.ini-tiedostoon:

    ```
    ccl/trace/level=5
    ccl/trace/directory=<drive>:\logs\sectrace
    ```

    Varmista, että muutat _ccl/trace/directory_-asetuksen sijaintiin, jonne Todennetut käyttäjät -ryhmän jäsenet voivat kirjoittaa. Vaihtoehtoisesti voit luoda uuden .ini-tiedoston, jos haluat muuttaa tätä toimintaa. Luo samassa hakemistossa, jossa sapcrypto.ini ja sapcrypto.dll sijaitsevat, tiedosto nimeltä sectrace.ini käyttäen alla olevaa sisältöä. Korvaa HAKEMISTO-asetus tietokoneessasi olevalla sijainnilla, jonne todennettu käyttäjä voi kirjoittaa:

    ```
    LEVEL = 5

    DIRECTORY = <drive>:\logs\sectrace
    ```

    Nyt voit toistaa ongelman ja tarkistaa, että HAKEMISTOON määritetty sijainti sisältää jäljitystiedostoja. Varmista, että poistat CPIC- ja CCL-jäljityksen käytöstä, kun olet valmis.

    Lisätietoja CommonCryptoLib-jäljityksestä on kohdassa [SAP-huomautus 2491573](https://launchpad.support.sap.com/#/notes/2491573) (s-käyttäjä vaaditaan).

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja **paikallisesta tietoyhdyskäytävästä** ja **DirectQuerysta** on seuraavissa resursseissa:

* [Mikä paikallinen tietoyhdyskäytävä on?](/data-integration/gateway/service-gateway-getting-started)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
