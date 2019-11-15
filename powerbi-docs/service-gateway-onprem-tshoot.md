---
title: Yhdyskäytävien vianmääritys – Power BI
description: Tästä artikkelista saat vianmääritysohjeita paikalliselle tietoyhdyskäytävälle ja Power BI:lle. Se tarjoaa ohjeita tunnettujen ongelmien kiertämiseen sekä työkaluja, joista on apua.
author: mgblythe
ms.author: mblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: troubleshooting
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: b420c827df3c18796d0d46514f81170f202eafbd
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73881566"
---
# <a name="troubleshoot-gateways---power-bi"></a>Yhdyskäytävien vianmääritys – Power BI

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Tässä artikkelissa käsitellään joitakin yleisiä ongelmia käytettäessä paikallista tietoyhdyskäytävää ja Power BI:tä. Jos kohtaat ongelman, jota ei ole lueteltu tässä, voit käyttää Power BI [-yhteisöjen](https://community.powerbi.com) sivustoa. Voit myös luoda [tukipalvelupyynnön](https://powerbi.microsoft.com/support).

## <a name="configuration"></a>Määrittäminen

### <a name="error-power-bi-service-reported-local-gateway-as-unreachable-restart-the-gateway-and-try-again"></a>Virhe: Power BI -palvelu ilmoittaa, että paikalliseen yhdyskäytävään ei saada yhteyttä. Käynnistä yhdyskäytävä uudelleen ja yritä uudelleen.

Power BI -palvelua kutsutaan uudelleen määrityksen lopussa yhdyskäytävän vahvistamiseksi. Power BI ei ilmoita yhdyskäytävän olevan käytettävissä. Windows-palvelun uudelleenkäynnistäminen saattaa mahdollistaa tiedonsiirron onnistumisen. Voit hankkia lisätietoja keräämällä ja tarkastelemalla lokeja kohdassa [Lokien kerääminen paikallisen tietoyhdyskäytävän sovelluksesta](/data-integration/gateway/service-gateway-tshoot#collect-logs-from-the-on-premises-data-gateway-app) kuvatulla tavalla.

## <a name="data-sources"></a>Tietolähteet

### <a name="error-unable-to-connect-details-invalid-connection-credentials"></a>Virhe: Yhteyttä ei voi muodostaa. Tiedot: Virheelliset yhteyden tunnistetiedot

**Näytä tiedot** -kohdassa näkyy tietolähteestä saatu virheilmoitus. Jos kyseessä on SQL Server, näet jotakin seuraavankaltaista:

    Login failed for user 'username'.

Varmista, että käyttäjänimi ja salasana ovat oikein. Varmista myös, että näillä tunnistetiedoilla saadaan yhteys tietolähteeseen. Varmista, että käytetty tili täsmää todennusmenetelmän kanssa.

### <a name="error-unable-to-connect-details-cannot-connect-to-the-database"></a>Virhe: Yhteyttä ei voi muodostaa. Tiedot: Yhteyden muodostaminen tietokantaan ei onnistu

Palvelimeen saadaan yhteys, mutta annettuun tietokantaan ei. Tarkista tietokannan nimi ja se, että käyttäjätunnistetiedoilla on oikeat oikeudet tietokantaan.

**Näytä tiedot** -kohdassa näkyy tietolähteestä saatu virheilmoitus. Jos kyseessä on SQL Server, näet jotakin seuraavankaltaista:

    Cannot open database "AdventureWorks" requested by the login. The login failed. Login failed for user 'username'.

### <a name="error-unable-to-connect-details-unknown-error-in-data-gateway"></a>Virhe: Yhteyttä ei voi muodostaa. Tiedot: Tuntematon virhe tietoyhdyskäytävässä

Tämä virhe voi johtua eri syistä. Muista varmistaa, että voit muodostaa yhteyden tietolähteeseen sillä koneella, joka isännöi yhdyskäytävää. Tämä tilanne saattaa johtua siitä, että palvelin ei ole käytettävissä.

Näet **Näytä tiedot** -kohdassa virhekoodin **DM_GWPipeline_UnknownError**.

Saat lisätietoja myös kohdasta **Tapahtumalokit** > **Sovellusten ja palveluiden lokit** > **Paikallinen tietoyhdyskäytäväpalvelu**.

### <a name="error-we-encountered-an-error-while-trying-to-connect-to-server-details-we-reached-the-data-gateway-but-the-gateway-cant-access-the-on-premises-data-source"></a>Virhe: \<Palvelimeen\> yhdistettäessä ilmeni virhe. Tiedot: Kyseiseen tietoyhdyskäytävään saatiin yhteys, mutta yhdyskäytävä ei pysty käyttämään paikallista tietolähdettä.

Määritettyyn tietolähteeseen ei saada yhteyttä. Muista tarkistaa tälle tietolähteelle annetut tiedot.

Näet **Näytä tiedot** -kohdassa virhekoodin **DM_GWPipeline_Gateway_DataSourceAccessError**.

Jos taustalla oleva virheilmoitus on samankaltainen kuin seuraava, tämä tarkoittaa sitä, että tietolähteelle käyttämäsi tili ei ole palvelimen järjestelmänvalvoja kyseiselle Analysis Services -esiintymälle. Lisätietoja on ohjeaiheessa [Palvelimen järjestelmänvalvojan käyttöoikeuksien myöntäminen Analysis Services -esiintymälle](https://docs.microsoft.com/sql/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance).

    The 'CONTOSO\account' value of the 'EffectiveUserName' XML for Analysis property is not valid.

Jos taustalla oleva virheilmoitus on samankaltainen kuin seuraava, tämä saattaa tarkoittaa sitä, että Analysis Servicesin palvelutililtä saattaa puuttua hakemistomäärite [token-groups-global-and-universal](https://msdn.microsoft.com/library/windows/desktop/ms680300.aspx) (TGGAU).

    The username or password is incorrect.

Toimialueilla, jotka ovat yhteensopivia Windows 2000:ta vanhempien käyttöjärjestelmien kanssa, on käytössä TGGAU-määrite. Useimmat vastaluodut toimialueet eivät oletusarvoisesti käytä tätä määritettä. Lisätietoja on ohjeaiheessa [Jotkin sovellukset ja ohjelmointirajapinnat edellyttävät käyttöoikeustietojen käyttöä tilin objektien kohdalla](https://support.microsoft.com/kb/331951).

Voit vahvistaa, onko määrite käytössä, toimimalla seuraavasti.

1. Muodosta yhteys Analysis Services -koneeseen SQL Server Management Studiossa. Liitä Advanced Connection Properties -kohdassa kyseessä olevan käyttäjän EffectiveUserName ja tarkista, toistuuko ongelma.
2. Dsacls Active Directory -työkalulla voit tarkistaa, onko määrite lueteltu. Tämä työkalu löytyy toimialueen ohjauskoneesta. Sinun täytyy tietää tilin toimialueen erillinen nimi ja välittää nimi työkalulle.

        dsacls "CN=John Doe,CN=UserAccounts,DC=contoso,DC=com"

    Tavoitteena on nähdä jotain samankaltaista tuloksissa:

            Allow BUILTIN\Windows Authorization Access Group
                                          SPECIAL ACCESS for tokenGroupsGlobalAndUniversal
                                          READ PROPERTY

Tämän ongelman korjaamiseksi sinun täytyy ottaa TGGAU käyttöön tilillä, jota käytetään Analysis Servicesin Windows-palvelussa.

#### <a name="another-possibility-for-the-username-or-password-is-incorrect"></a>Toinen mahdollisuus Käyttäjänimi tai salasana on virheellinen -virheelle.

Tämä virhe saattaa johtua myös siitä, jos Analysis Services -palvelin on eri toimialueella kuin käyttäjät ja kaksisuuntaista luottamusta ei ole määritetty.

Varmista toimialueiden välinen luottamussuhde yhdessä toimialueiden järjestelmänvalvojien kanssa.

#### <a name="unable-to-see-the-data-gateway-data-sources-in-the-get-data-experience-for-analysis-services-from-the-power-bi-service"></a>Tietoyhdyskäytävän tietolähteitä ei näy Power BI -palvelun Analysis Servicesin Nouda tiedot -näkymässä

Varmista, että tilisi on lueteltu tietolähteen **Käyttäjät**-välilehdellä yhdyskäytävän määrityksissä. Jos sinulla ei ole käyttöoikeuksia yhdyskäytävään, pyydä yhdyskäytävän järjestelmänvalvojaa antamaan ne. Vain **Käyttäjät**-luettelossa luetelluilla tileillä nähdään tietolähteet, jotka on lueteltu Analysis Services -luettelossa.

### <a name="error-you-dont-have-any-gateway-installed-or-configured-for-the-data-sources-in-this-dataset"></a>Virhe: Sinulla ei ole yhdyskäytävää asennettuna tai määritettynä tämän tietojoukon tietolähteille.

Varmista, että olet lisännyt yhden tai useamman tietolähteen yhdyskäytävään kohdassa [Tietolähteen lisääminen](service-gateway-data-sources.md#add-a-data-source) kuvatulla tavalla. Jos yhdyskäytävä ei näy hallintaportaalin kohdassa **Yhdyskäytävien hallinta**, tyhjennä selaimen välimuisti tai kirjaudu ulos palvelusta ja sitten takaisin sisään.

## <a name="datasets"></a>Tietojoukot

### <a name="error-there-is-not-enough-space-for-this-row"></a>Virhe: Tälle riville ei ole tarpeeksi tilaa.

Tämä virhe ilmenee, jos yksittäisen rivin koko on yli 4 Mt. Määritä, mikä tietolähteen rivi on kyseessä, ja yritä suodattaa se pois tai pienentää tämän rivin kokoa.

### <a name="error-the-server-name-provided-doesnt-match-the-server-name-on-the-sql-server-ssl-certificate"></a>Virhe: Annettu palvelimen nimi ei vastaa SQL Serverin SSL-varmenteessa olevaa nimeä.

Tämä virhe voi ilmetä, jos varmenteessa oleva nimi on palvelimen täydellinen toimialuenimi (FQDN), mutta annoit vain palvelimen NetBIOS-nimen. Tämän vuoksi varmenne ei täsmää. Voit korjata tämän ongelman vaihtamalla palvelimen nimen yhdyskäytävän tietolähteessä ja PBIX-tiedostossa palvelimen täydelliseksi toimialuenimeksi (FQDN).

### <a name="error-you-dont-see-the-on-premises-data-gateway-present-when-you-configure-scheduled-refresh"></a>Virhe: Et näe paikallista tietoyhdyskäytävää, kun määrität ajoitettua päivitystä.

Tämä virhe voi johtua muutamasta eri syystä:

- Palvelimen ja tietokannan nimi eivät täsmää Power BI Desktopin ja yhdyskäytävälle määritetyn tietolähteen kanssa. Näiden nimien on oltava samat. Niissä ei huomioida kirjainkokoa.
- Tiliäsi ei luetella tietolähteen **Käyttäjät**-välilehdellä yhdyskäytävämäärityksessä. Yhdyskäytävän järjestelmänvalvojan pitää lisätä tilisi luetteloon.
- Power BI Desktop -tiedostossasi on useita tietolähteitä eikä kaikkia näitä ole määritetty yhdyskäytävälle. Sinun täytyy määrittää kaikki tietolähteet yhdyskäytävälle, jotta yhdyskäytävä näkyy ajoitetussa päivityksessä.

### <a name="error-the-received-uncompressed-data-on-the-gateway-client-has-exceeded-the-limit"></a>Virhe: Yhdyskäytäväasiakkaan vastaanottamat pakatut tiedot ylittävät rajoituksen.

Tarkka rajoitus on 10 Gt pakkaamatonta tietoa per taulukko. Jos törmäät tähän ongelmaan, käytettävissä on hyviä optimointitapoja sen välttämiseksi. Voit pienentää kokoa etenkin vähentämällä usein toistuvien pitkien merkkijonoarvojen käyttöä käyttämällä niiden sijaan normalisoitua avainta. Voit myös poistaa sarakkeen, jos se ei ole käytössä.

## <a name="reports"></a>Raportit

### <a name="error-report-could-not-access-the-data-source-because-you-do-not-have-access-to-our-data-source-via-an-on-premises-data-gateway"></a>Virhe: Raportti ei voi käyttää tietolähdettä, koska sinulla ei ole käyttöoikeutta tietolähteeseemme paikallisen tietoyhdyskäytävän kautta.

Tämä virhe johtuu yleensä jostain alla mainituista syistä:

- Tietolähdetiedot eivät täsmää taustalla olevan tietojoukon kanssa. Palvelimen ja tietokannan nimen täytyy täsmätä paikalliselle tietoyhdyskäytävälle määritetyn tietolähteen ja Power BI Desktopissa annettujen kanssa. Jos käytät IP-osoitetta Power BI Desktopissa, myös paikallisen tietoyhdyskäytävän tietolähteen täytyy käyttää IP-osoitetta.
- Millekään organisaatiosi yhdyskäytävälle ei ole tietolähdettä käytettävissä. Voit määrittää tietolähteen uudessa tai olemassa olevassa paikallisessa tietoyhdyskäytävässä.

### <a name="error-data-source-access-error-please-contact-the-gateway-administrator"></a>Virhe: Tietolähteen käyttövirhe. Ota yhteyttä yhdyskäytävän järjestelmänvalvojaan.

Jos tämä raportti käyttää reaaliaikaista Analysis Services -yhteyttä, saatat törmätä ongelmaan, jossa EffectiveUserNamelle välitetty arvo on joko epäkelpo tai sillä ei ole oikeuksia Analysis Services -koneessa. Yleensä todennusongelma johtuu siitä, että EffectiveUserNamelle välitetty arvo ei täsmää paikallisen täydellisen käyttäjätunnuksen (UPN) kanssa.

Vahvista voimassa oleva käyttäjänimi toimimalla seuraavasti.

1. Etsi käytössä oleva käyttäjänimi [yhdyskäytävälokeista](/data-integration/gateway/service-gateway-tshoot#collect-logs-from-the-on-premises-data-gateway-app).
2. Kun sinulla on välitettävä arvo, tarkista, että se on oikea. Jos se on käyttäjäsi arvo, voit tarkistaa seuraavalla komentokehotteen komennolla, mikä täydellisen käyttäjätunnuksen tulisi olla. Se näyttää sähköpostiosoitteelta.

        whoami /upn

Voit myös tarkistaa, mitä Power BI hakee Azure Active Directorysta.

1. Siirry osoitteeseen [https://developer.microsoft.com/graph/graph-explorer](https://developer.microsoft.com/graph/graph-explorer).
2. Valitse oikeassa yläkulmassa **Kirjaudu sisään**.
3. Suorita seuraava kysely. Saat melko suuren JSON-vastauksen.

        https://graph.windows.net/me?api-version=1.5
4. Etsi **userPrincipalName**.

Jos Azure Active Directoryn täydellinen käyttäjänimi ei täsmää paikallisen Active Directoryn täydellisen käyttäjänimen kanssa, voit korvata sen kelvollisella arvolla [käyttäjänimien yhdistämistoiminnolla](service-gateway-enterprise-manage-ssas.md#map-user-names-for-analysis-services-data-sources). Voit myös pyytää täydellisen käyttäjänimen vaihtamista tilauksesi järjestelmänvalvojalta tai paikallisen Active Directoryn järjestelmänvalvojalta.

## <a name="kerberos"></a>Kerberos

Jos pohjana olevaa tietokantapalvelinta ja paikallista tietoyhdyskäytävää ei ole määritetty oikein [rajoitetun Kerberos-delegoinnin](service-gateway-sso-kerberos.md) osalta, ota yhdyskäytävässä käyttöön [yksityiskohtainen kirjaaminen](/data-integration/gateway/service-gateway-performance#slow-performing-queries). Tarkista sitten yhdyskäytävän lokitiedostosta virheet ja jäljitystiedot. Näin voit aloittaa vianmäärityksen. Jos haluat kerätä yhdyskäytävälokeja tarkastelua varten, katso [Lokien kerääminen paikallisen tietoyhdyskäytävän sovelluksesta](/data-integration/gateway/service-gateway-tshoot#collect-logs-from-the-on-premises-data-gateway-app).

### <a name="impersonationlevel"></a>ImpersonationLevel

ImpersonationLevel-asetus liittyy palvelun päänimen asetuksiin tai paikalliseen käytäntöasetukseen.

```
[DataMovement.PipeLine.GatewayDataAccess] About to impersonate user DOMAIN\User (IsAuthenticated: True, ImpersonationLevel: Identification)
```

**Ratkaisu**

Voit korjata ongelman seuraavasti.

1. Määritä paikallisen yhdyskäytävän palvelun päänimi.
2. Määritä rajoitettu delegointi Active Directoryssä.

### <a name="failedtoimpersonateuserexception-failed-to-create-windows-identity-for-user-userid"></a>FailedToImpersonateUserException: Windows-käyttäjätietojen luominen käyttäjälle userid epäonnistui

FailedToImpersonateUserException ilmenee, jos et voi tekeytyä toiseksi käyttäjäksi. Tämä virhe voi ilmetä myös silloin, jos tili, joksi yrität tekeytyä, on toisesta toimialueesta kuin yhdyskäytäväpalvelu. Tämä on rajoitus.

**Ratkaisu**

* Vahvista, että määritykset ovat oikein edellä olevan ImpersonationLevel-osan ohjeiden mukaisesti.
* Varmista, että käyttäjätunnus, joksi yritetään tekeytyä, on kelvollinen Active Directory -tili.

### <a name="general-error-1033-error-while-you-parse-the-protocol"></a>Yleinen virhe: 1033-virhe protokollaa jäsennettäessä

Saat 1033-virheen, kun ulkoinen SAP HANA:ssa määritetty tunnus ei täsmää kirjautumistunnuksen kanssa, jos käyttäjäksi tekeydytään täydellisellä käyttäjätunnuksella (alias@domain.com). Näet virhelokien alusta, että alkuperäinen täydellinen käyttäjätunnus alias@domain.com on korvattu uudella täydellisellä käyttäjätunnuksella alias@domain.com seuraavassa näytetyn mukaisesti:

```
[DM.GatewayCore] SingleSignOn Required. Original UPN 'alias@domain.com' replaced with new UPN 'alias@domain.com.'
```

**Ratkaisu**

* SAP HANA edellyttää, että tekeydytty käyttäjä käyttää sAMAccountName-määritettä Active Directoryssä (käyttäjäalias). Jos tämä ominaisuus ei ole oikein, saat 1033-virheen.

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount.png)

* Sinun pitäisi nähdä lokeissa sAMAccountName (alias), ei täydellistä käyttäjätunnusta. Se on alias, jonka perässä on toimialue (alias@doimain.com).

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount-02.png)

```xml
      <setting name="ADUserNameReplacementProperty" serializeAs="String">
        <value>sAMAccount</value>
      </setting>
      <setting name="ADServerPath" serializeAs="String">
        <value />
      </setting>
      <setting name="CustomASDataSource" serializeAs="String">
        <value />
      </setting>
      <setting name="ADUserNameLookupProperty" serializeAs="String">
        <value>AADEmail</value>
```

### <a name="sap-aglibodbchdb-dllhdbodbc-communication-link-failure-10709-connection-failed-rte-1-kerberos-error-major-miscellaneous-failure-851968-minor-no-credentials-are-available-in-the-security-package"></a>[SAP AG][LIBODBCHDB DLL][HDBODBC] Communication link failure:-10709 Connection failed (RTE:[-1] Kerberos error. Major: "Miscellaneous failure [851968]." Minor: "No credentials are available in the security package."

Saat 10709-virheen yhteyden epäonnistumisesta, jos delegointia ei ole määritetty oikein Active Directoryssä.

**Ratkaisu**

* Varmista, että SAP Hana -palvelin on mukana Active Directoryn delegointivälilehdellä yhdyskäytäväpalvelutilille.

   ![Delegointivälilehti](media/service-gateway-onprem-tshoot/delegation-in-AD.png)

## <a name="refresh-history"></a>Päivityshistoria

Kun käytät yhdyskäytävän ajoitettua päivitystä, **päivityshistoriasta** näet ilmenneet virheet. Se voi myös tarjota hyödyllisiä tietoja, jos sinun täytyy luoda tukipyyntö. Voit tarkistaa ajoitetut päivitykset ja pyynnöstä suoritetut päivitykset. Seuraavissa vaiheissa esitetään, miten pääset päivityshistoriaan.

1. Valitse yksi tietojoukoista Power BI -siirtymisruudun kohdasta **Tietojoukot**. Avaa valikko ja valitse **Ajoita päivitys**.

    ![Ajoitetun päivityksen valitseminen](media/service-gateway-onprem-tshoot/scheduled-refresh.png)

2. Valitse **Asetukset kohteelle...** &gt; **Ajoita päivitys** > **Päivityshistoria**.

    ![Päivityshistorian valitseminen](media/service-gateway-onprem-tshoot/scheduled-refresh-2.png)

    ![Päivityshistorian näyttäminen](media/service-gateway-onprem-tshoot/refresh-history.png)

Lisätietoja päivitystilanteiden vianmäärityksestä on kohdassa [Päivitystilanteiden vianmääritys](refresh-troubleshooting-refresh-scenarios.md).

## <a name="fiddler-trace"></a>Fiddler-jäljitys

[Fiddler](https://www.telerik.com/fiddler) on Telerikin ilmainen työkalu, joka valvoo HTTP-liikennettä. Voit tarkastella Power BI -palvelun tiedonsiirtoa asiakaskoneelta. Tämä liikenneluettelo saattaa näyttää virheitä ja muita olennaisia tietoja.

![Fiddler-jäljityksen käyttäminen](media/service-gateway-onprem-tshoot/fiddler.png)

## <a name="next-steps"></a>Seuraavat vaiheet

* [Paikallisen tietoyhdyskäytävän vianmääritys](/data-integration/gateway/service-gateway-tshoot)
* [Paikallisen tietoyhdyskäytävän välityspalvelinasetusten määrittäminen](/data-integration/gateway/service-gateway-proxy)  
* [Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [Tietolähteen hallinta – SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [Tietolähteen hallinta – SQL Server](service-gateway-enterprise-manage-sql.md)  
* [Tietolähteen hallinta – tuonti ja ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md)  

Onko sinulla kysyttävää? Kokeile [Power BI -yhteisöä](https://community.powerbi.com/).
