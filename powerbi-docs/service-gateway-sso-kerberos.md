---
title: Määritä kertakirjautuminen (SSO) – Kerberos
description: Kerberoksen määrittäminen yhdyskäytävään SSO:n käyttöön ottamiseksi Power BI:stä paikallisiin tietolähteisiin
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 9958059fcf0d86323fc95f44f6fcfcb08fe7b52b
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/18/2019
ms.locfileid: "71100487"
---
# <a name="configure-kerberos-based-sso-from-power-bi-service-to-on-premises-data-sources"></a>Kerberos-pohjaisen kertakirjautumisen määrittäminen Power BI -palvelusta paikallisiin tietolähteisiin

Käytä [rajoitettua Kerberos-delegointia](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) ottaaksesi saumattoman kertakirjautumisen käyttöön. Kun otat kertakirjautumisen käyttöön, Power BI -raportit ja -koontinäytöt voivat helposti päivittää tiedot, jotka ovat peräisin paikallisista lähteistä.

Useita kohteita on määritettävä, jotta rajoitettu Kerberos-delegointi toimisi oikein, muun muassa _palvelun päänimet_ (SPN) ja palvelutilien delegointiasetukset.

### <a name="prerequisite-1-install-and-configure-the-microsoft-on-premises-data-gateway"></a>Edellytys 1: Asenna ja määritä paikallinen Microsoft-tietoyhdyskäytävä

Tämä paikallinen tietoyhdyskäytävä tukee suoraa päivitystä ja aiemmin luotujen yhdyskäytävien _asetusten haltuunottoa_.

### <a name="prerequisite-2-run-the-gateway-windows-service-as-a-domain-account"></a>Edellytys 2: Suorita yhdyskäytävän Windows-palvelu toimialuetilinä

Normaalissa asennuksessa yhdyskäytävä toimii tietokoneen paikallisena palvelutilinä (tarkemmin _NT Service\PBIEgwService_) seuraavan kuvan mukaisesti:

![Näyttökuva palvelutilistä](media/service-gateway-sso-kerberos/service-account.png)

Jotta rajoitettu Kerberos-delegointi voidaan ottaa käyttöön, yhdyskäytävän on toimittava toimialuetilinä, ellei Azure Active Directorya (Azure AD) ole jo synkronoitu paikallisen Active Directory -esiintymän kanssa (käyttämällä Azure AD DirSynciä/Connectia). Jos haluat vaihtaa toimialuetiliin, katso [Yhdyskäytävän palvelutilin muuttaminen](/data-integration/gateway/service-gateway-service-account).

> [!NOTE]
> Jos Azure AD Connect on määritetty ja käyttäjätilit synkronoidaan, yhdyskäytäväpalvelun ei tarvitse tehdä paikallisia hakuja Azure AD:stä suorituksen aikana. Sen sijaan voit vain käyttää paikallista palvelun suojaustunnusta yhdyskäytäväpalvelussa suorittaaksesi kaikki vaaditut määritykset Azure Active Directoryssa. Tässä artikkelissa kuvatut rajoitetun Kerberos-delegoinnin määritysvaiheet ovat samat kuin Azure Active Directory -kontekstissa vaaditut määritysvaiheet. Niitä sovelletaan Azure AD:ssä yhdyskäytävän tietokoneobjektiin (paikallisen palvelun suojaustunnuksen mukaan) toimialuetilin sijaan.

### <a name="prerequisite-3-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>Edellytys 3: Toimialueen järjestelmänvalvojan oikeuksien hankkiminen päänimien (SetSPN) ja rajoitetun Kerberos-delegoinnin asetusten määrittämiseksi

Emme suosittele, että toimialueen järjestelmänvalvoja antaa jollekulle muulle väliaikaiset tai pysyvät oikeudet määrittää palvelun päänimiä ja Kerberos-delegointiasetuksia ilman, että kyseisellä henkilöllä on toimialueen järjestelmänvalvojan oikeudet. Suositellut määritysvaiheet käsitellään seuraavassa osiossa.

## <a name="configure-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>Rajoitetun Kerberos-delegoinnin määrittäminen yhdyskäytävälle ja tietolähteelle

Määritä toimialueen järjestelmänvalvojana palvelun päänimi yhdyskäytävän palvelutilille (tarvittaessa) ja määritä sitten yhdyskäytäväpalvelun toimialuetilin delegointiasetukset.

### <a name="configure-an-spn-for-the-gateway-service-account"></a>SPN:n määrittäminen yhdyskäytävän palvelutilille

Selvitä ensin, onko yhdyskäytävän palvelutilinä käytetylle toimialuetilille luotu jo palvelun päänimi:

1. Käynnistä **Active Directory -käyttäjät ja -tietokoneet** toimialueen järjestelmänvalvojana.

2. Napsauta toimialuetta hiiren kakkospainikkeella, valitse **Etsi** ja kirjoita yhdyskäytävän palvelutilin nimi.

3. Napsauta hakutuloksissa yhdyskäytävän palvelutiliä hiiren kakkospainikkeella ja valitse **Ominaisuudet**.

4. Jos **Delegointi**-välilehti näkyy **Ominaisuudet**-valintaikkunassa, palvelun päänimi on jo luotu ja voit siirtyä kohtaan [Valitse resurssipohjainen tai vakiomuotoinen rajoitettu Kerberos-delegointi](#decide-on-resource-based-or-standard-kerberos-constrained-delegation).

    Jos **Delegointi**-välilehteä ei näy **Ominaisuudet**-valintaikkunassa, voit luoda palvelun päänimen kyseiselle tilille manuaalisesti ottaaksesi sen käyttöön. Käytä [setspn-työkalua](https://technet.microsoft.com/library/cc731241.aspx), joka sisältyy Windowsiin (palvelun päänimen luominen edellyttää toimialueen järjestelmänvalvojan oikeuksia).

    Kuvitellaan esimerkiksi, että yhdyskäytävän palvelutili on **Contoso\GatewaySvc**) ja yhdyskäytäväpalvelua suorittavan tietokoneen nimi on **OmaYhdyskäytäväkone**. Jotta yhdyskäytävän palvelutilille voidaan määrittää palvelun päänimi, on suoritettava seuraava komento:

    ![Kuva palvelun päänimen määrittämiskomennosta](media/service-gateway-sso-kerberos/set-spn.png)

    Voit myös määrittää palvelun päänimen MMC-konsolin Active Directory -käyttäjät ja -tietokoneet -laajennuksen avulla.

### <a name="decide-on-resource-based-or-standard-kerberos-constrained-delegation"></a>Valitse resurssipohjainen tai vakiomuotoinen rajoitettu Kerberos-delegointi

Delegointiasetukset voidaan määrittää _joko_ resurssipohjaiselle rajoitetulle Kerberos-delegoinnille tai vakiomuotoiselle rajoitetulle Kerberos-delegoinnille. Käytä resurssipohjaista delegointia, jos tietolähteesi kuuluu eri toimialueeseen kuin yhdyskäytäväsi, mutta huomioi, että tämä lähestymistapa edellyttää Windows Server 2012:ta tai uudempaa versiota. Lisätietoja näiden kahden delegointitavan eroista on [rajoitetun Kerberos-delegoinnin yleiskatsaussivulla](/windows-server/security/kerberos/kerberos-constrained-delegation-overview).

 Kun olet päättänyt, mitä lähestymistapaa haluat käyttää, siirry _joko_ [Määritä yhdyskäytävän palvelutili vakiomuotoiselle rajoitetulle Kerberos-delegoinnille](#configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation)- _tai_ [Määritä yhdyskäytävän palvelutili resurssipohjaiselle rajoitetulle Kerberos-delegoinnille](#configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation) -osaan. Älä suorita molempia aliosia.

## <a name="configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation"></a>Määritä yhdyskäytävän palvelutili vakiomuotoiselle rajoitetulle Kerberos-delegoinnille

> [!NOTE]
> Suorita tämän osion vaiheet, jos haluat ottaa käyttöön vakiomuotoisen rajoitetun Kerberos-delegoinnin. Jos haluat ottaa käyttöön resurssipohjaisen rajoitetun Kerberos-delegoinnin, suorita vaiheet [Määritä yhdyskäytävän palvelutili resurssipohjaiselle rajoitetulle Kerberos-delegoinnille](#configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation) -aliosassa.

Määritämme nyt yhdyskäytävän palvelutilin delegointiasetukset. Voit suorittaa nämä vaiheet useilla eri työkaluilla. Tässä esimerkissä käytetään Active Directory Users and Computers -työkalua, joka on Microsoft Management Console (MMC) -laajennus. Sen avulla voit hallita ja julkaista tietoja hakemistossa. Se on käytettävissä oletusarvoisesti toimialueen ohjauskoneissa, mutta voit myös ottaa sen käyttöön Windowsin toimintojen määrityksen kautta toisissa tietokoneissa.

Rajoitettu Kerberos-delegointi on määritettävä protokollan siirtämisellä. Rajoitetussa delegoinnissa on määritettävä tarkasti, mille palveluille haluat sallia yhdyskäytävän delegoitujen tunnistetietojen esittelyn. Esimerkiksi vain SQL Server tai SAP HANA -palvelin hyväksyy delegointikutsuja yhdyskäytävän palvelutililtä.

Tässä osassa oletetaan, että olet jo määrittänyt palvelun päänimet pohjana oleville tietolähteille (kuten SQL Server, SAP HANA, SAP BW, Teradata tai Spark). Lisätietoja kyseisten tietolähteiden palvelimen palvelun päänimien määrittämisestä löytyy vastaavan tietokantapalvelimen teknisessä dokumentaatiossa. Voit myös tutustua kohtaan *What SPN does your app require?* blogikirjoituksessa [My Kerberos Checklist](https://techcommunity.microsoft.com/t5/SQL-Server-Support/My-Kerberos-Checklist-8230/ba-p/316160).

Seuraavissa vaiheissa oletuksena on paikallinen ympäristö, jossa on kaksi konetta: yhdyskäytäväkone ja SQL Serveriä käyttävä tietokantapalvelin, joka on jo määritetty Kerberos-pohjaiselle kertakirjautumiselle. Vaiheet voidaan hyväksyä jossakin muussa tuetussa tietolähteessä, kunhan tietolähde on jo määritetty Kerberos-pohjaiselle kertakirjautumiselle. Esimerkissä käytetään seuraavia asetuksia ja nimiä:

* Active Directory -toimialue (Netbios): Contoso
* Yhdyskäytäväkoneen nimi: **OmaYhdyskäytäväkone**
* Yhdyskäytävän palvelutili: **Contoso\GatewaySvc**
* SQL Serverin tietolähteen koneen nimi: **TestSQLServer**
* SQL Serverin tietolähteen palvelutili: **Contoso\SQLService**

Voit määrittää delegoinnin asetukset seuraavasti:

1. Käynnistä **Active Directory Users and Computers** toimialueen järjestelmänvalvojan oikeuksilla.

2. Napsauta yhdyskäytävän palvelutiliä (**Contoso\GatewaySvc**) hiiren kakkospainikkeella ja valitse **Ominaisuudet**.

3. Valitse **Delegointi**-välilehti.

4. Valitse **Luota tähän tietokoneeseen vain määritettyihin palveluihin delegointia varten** >  ja valitse sitten **Käytä mitä tahansa todennusprotokollaa**.

5. Valitse **Palvelut, joille tämä tili voi esittää delegoidut tunnistetiedot** -kohdassa **Lisää**.

6. Valitse uudessa valintaikkunassa **Käyttäjät tai tietokoneet**.

7. Anna tietolähteen palvelutili. Esimerkiksi SQL Server -tietolähteen palvelutili voi olla **Contoso\SQLService**. Kun tili on lisätty, valitse **OK**.

8. Valitse SPN, jonka loit tietokantapalvelimelle. Tässä esimerkissä SPN:n alussa on **MSSQLSvc**. Jos olet lisännyt tietokantapalvelulle sekä FQDN- että NetBIOS-SPN:n, valitse molemmat. Saatat nähdä näistä vain toisen.

9. Valitse **OK**. Palvelun päänimen pitäisi näkyä nyt luettelossa.

    ![Näyttökuva Yhdyskäytävän liittimen ominaisuudet -valintaikkunasta](media/service-gateway-sso-kerberos/gateway-connector-properties.png)

Nyt voit siirtyä kohtaan [Myönnä paikallisen käytännön oikeudet yhdyskäytävän palvelutilille yhdyskäytäväkoneessa](#grant-the-gateway-service-account-local-policy-rights-on-the-gateway-machine) jatkaaksesi määritysprosessia.

## <a name="configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation"></a>Määritä yhdyskäytävän palvelutili resurssipohjaiselle rajoitetulle Kerberos-delegoinnille

> [!NOTE]
> Suorita tämän osion vaiheet, jos haluat ottaa käyttöön resurssipohjaisen rajoitetun Kerberos-delegoinnin. Jos haluat ottaa käyttöön vakiomuotoisen rajoitetun Kerberos-delegoinnin, suorita vaiheet [Määritä yhdyskäytävän palvelutili vakiomuotoiselle rajoitetulle Kerberos-delegoinnille](#configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation) -aliosassa.

Käytä [resurssipohjaista rajoitettua Kerberos-delegointia](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) kertakirjautumisyhteyden käyttöönottamiseksi Windows Server 2012:lle ja uudemmille versioille, jotta edusta- ja taustapalvelut voivat olla eri toimialueilla. Jotta tämä toimisi, taustapalvelun toimialueen on luotettava edustapalvelun toimialueeseen.

Seuraavissa vaiheissa oletuksena on paikallinen ympäristö, jossa on kaksi konetta eri toimialueilla: yhdyskäytäväkone ja SQL Serveriä käyttävä tietokantapalvelin, joka on jo määritetty Kerberos-pohjaiselle kertakirjautumiselle. Vaiheet voidaan hyväksyä jossakin muussa tuetussa tietolähteessä, kunhan tietolähde on jo määritetty Kerberos-pohjaiselle kertakirjautumiselle. Tässä esimerkissä käytetään seuraavia asetuksia ja nimiä:

* Yhdyskäytäväkoneen nimi: **OmaYhdyskäytäväkone**
* Yhdyskäytävän palvelutili: **ContosoFrontEnd\GatewaySvc**
* SQL Serverin tietolähteen koneen nimi: **TestSQLServer**
* SQL Serverin tietolähteen palvelutili: **ContosoBackEnd\SQLService**

Suorita seuraavat määritysvaiheet näitä esimerkkinimiä ja asetuksia käyttäen:

1. Kun käytät MMC-konsolin **Active Directory -käyttäjät ja -tietokoneet** -laajennusta toimialueen ohjauskoneessa **ContosoFrontEnd**-toimialueelle, varmista, että yhdyskäytävän palvelutiliin ei sovelleta delegointiasetuksia.

    ![Yhdyskäytävän liittimen ominaisuudet](media/service-gateway-sso-kerberos-resource/gateway-connector-properties.png)

2. Kun käytät **Active Directory -käyttäjät ja -tietokoneet** -laajennusta toimialueen ohjauskoneessa **ContosoBackEnd**-toimialueelle, varmista, että taustapalvelutiliin ei sovelleta delegointiasetuksia. Varmista myös, ettei tämän tilin **msDS-AllowedToActOnBehalfOfOtherIdentity**-määritettä ole määritetty. Löydät tämän määritteen **Määrite-editorista** seuraavassa kuvassa esitetyllä tavalla:

    ![SQL-palvelun ominaisuudet](media/service-gateway-sso-kerberos-resource/sql-service-properties.png)

3. Luo ryhmä **Active Directory -käyttäjät ja -tietokoneet** -laajennuksessa toimialueen ohjauskoneessa **ContosoBackEnd**-toimialueelle. Lisää yhdyskäytävän palvelutili tälle ryhmälle seuraavassa kuvassa esitetyllä tavalla. Kuvassa näkyy uusi ryhmä nimeltä _ResourceDelGroup_, ja tähän ryhmään lisätty yhdyskäytävän palvelutili **GatewaySvc**.

    ![Ryhmän ominaisuudet](media/service-gateway-sso-kerberos-resource/group-properties.png)

4. Avaa komentokehote ja suorita seuraavat komennot toimialueen ohjauskoneessa **ContosoBackEnd**-toimialueelle taustapalvelutilin **msDS-AllowedToActOnBehalfOfOtherIdentity**-määritteen päivittämiseksi:

    ```powershell
    $c = Get-ADGroup ResourceDelGroup
    Set-ADUser SQLService -PrincipalsAllowedToDelegateToAccount $c
    ```

5. Voit tarkistaa, että päivitys näkyy taustapalvelutilin ominaisuuksien ”Määrite-editori”-välilehdessä **Active Directory -käyttäjät ja -tietokoneet** -laajennuksessa.

## <a name="grant-the-gateway-service-account-local-policy-rights-on-the-gateway-machine"></a>Myönnä paikallisen käytännön oikeudet yhdyskäytävän palvelutilille yhdyskäytäväkoneessa

Lopuksi koneessa, joka suorittaa yhdyskäytäväpalvelua (esimerkissämme **OmaYhdyskäytäväkone**), yhdyskäytävän palvelutilille on myönnettävä paikalliset käytännöt **Asiakkaaksi tekeytyminen todentamisen jälkeen** ja **Käyttöjärjestelmän osana toimiminen (SeTcbPrivilege)** . Voit suorittaa ja tarkistaa tämän määrityksen paikallisessa ryhmäkäytäntöeditorissa (**gpedit**).

1. Suorita yhdyskäytäväkoneessa *gpedit.msc*.

2. Siirry kohtaan **Paikallisen tietokoneen käytäntö** > **Tietokoneen määritys** > **Windows-asetukset** > **Suojausasetukset** > **Paikalliset käytännöt** > **Järjestelmäoikeuksien osoitus**.

    ![Näyttökuva paikallisen tietokoneen käytäntöjen kansiorakenteesta](media/service-gateway-sso-kerberos/user-rights-assignment.png)

3. Valitse **Järjestelmäoikeuksien osoitus** -kohdan käytäntöluettelosta **Asiakkaaksi tekeytyminen todentamisen jälkeen**.

    ![Näyttökuva Asiakkaaksi tekeytyminen todentamisen jälkeen -käytännöstä](media/service-gateway-sso-kerberos/impersonate-client.png)

    Napsauta **Ominaisuudet**-kohtaa hiiren kakkospainikkeella ja avaa se. Tarkista tililuettelo. Sen on sisällettävä yhdyskäytävän palvelutili (**Contoso\GatewaySvc**).

4. Valitse **Järjestelmäoikeuksien osoitus** -kohdan käytäntöluettelosta **Käyttöjärjestelmän osana toimiminen (SeTcbPrivilege)** . Varmista, että yhdyskäytävän palvelutili sisältyy myös tililuetteloon.

5. Käynnistä **Paikallinen tietoyhdyskäytävä** -palveluprosessi uudelleen.

### <a name="set-user-mapping-configuration-parameters-on-the-gateway-machine-if-required"></a>Määritä käyttäjien yhdistämisen määritysparametrit yhdyskäytäväkoneessa tarvittaessa

Jos Azure AD Connectia ei ole määritetty, noudata seuraavia toimia yhdistääksesi Power BI -palvelukäyttäjän paikalliseen Active Directory -käyttäjään. Jokaisella tällä tavalla yhdistetyllä Active Directory -käyttäjällä on oltava tietolähteesi kertakirjautumisoikeudet. Jos haluat lisätietoja, katso tämä [Kaveri kuutiossa -video](https://www.youtube.com/watch?v=NG05PG9aiRw).

1. Avaa ensisijainen yhdyskäytävän määritystiedosto `Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll`. Tämä tiedosto löytyy oletusarvoisesti sijainnista C:\Program Files\On-premises data gateway.

1. Valitse **ADUserNameLookupProperty**-arvo käyttämättömälle Active Directory -määritteelle. Oletamme, että seuraavissa vaiheissa käytössä on `msDS-cloudExtensionAttribute1`, tosin tämä määrite on käytettävissä vain Windows Server 2012:ssa ja uudemmissa versioissa. Määritä **ADUserNameReplacementProperty** kohteelle `SAMAccountName`. Tallenna määritystiedosto.

1. Voit käynnistää yhdyskäytäväpalvelun uudelleen Tehtävienhallinnan **Palvelut**-välilehden kautta napsauttamalla hiiren kakkospainikkeella **Käynnistä uudelleen**.

    ![Näyttökuva Tehtävienhallinnan palvelut-välilehdestä](media/service-gateway-sso-kerberos/restart-gateway.png)

1. Määritä jokaiselle Power BI -palvelun käyttäjälle, jolle haluat ottaa käyttöön Kerberos-kertakirjautumisen, paikallisen Active Directory käyttäjän `msDS-cloudExtensionAttribute1`-ominaisuus (kertakirjautumisoikeuksilla tietolähteeseen) Power BI- palvelu käyttäjän täydelliseksi käyttäjänimeksi. Jos esimerkiksi kirjaudut Power BI -palveluun nimellä `test@contoso.com` ja haluat yhdistää tämän käyttäjän paikalliseen Active Directory -käyttäjään, jolla on kertakirjautumisoikeudet (esimerkiksi `test@LOCALDOMAIN.COM`), määritä käyttäjän `test@LOCALDOMAIN.COM` `msDS-cloudExtensionAttribute1`-määritteeksi `test@contoso.com`.

Voit määrittää `msDS-cloudExtensionAttribute1`-ominaisuuden MMC-konsolin Active Directory -käyttäjät ja -tietokoneet -laajennuksen avulla.

1. Käynnistä MMC-laajennus Active Directory -käyttäjät ja -tietokoneet toimialueen järjestelmänvalvojana.

1. Napsauta toimialuetta hiiren kakkospainikkeella, valitse Etsi ja kirjoita paikallisen Active Directory -käyttäjän nimi, johon haluat yhdistää.

1. Valitse **Ominaisuuseditori**-välilehti.

    Etsi `msDS-cloudExtensionAttribute1`-ominaisuus ja kaksoisnapsauta sitä. Määritä sen arvoksi sen käyttäjän täydellinen käyttäjänimi, jolla kirjaudut sisään Power BI -palveluun.

1. Valitse **OK**.

    ![Näyttökuva Merkkijonomäärite-editorin valintaikkunasta](media/service-gateway-sso-kerberos/edit-attribute.png)

1. Valitse **Käytä**. Varmista, että olet määrittänyt oikean arvon **Arvo**-sarakkeeseen.

## <a name="complete-data-source-specific-configuration-steps"></a>Viimeistele tietolähdekohtaiset määritysvaiheet

SAP HANA ja SAP BW sisältävät ylimääräisiä tietolähdekohtaisia määritystä koskevia vaatimuksia ja edellytyksiä, joiden on täytyttävä, ennen kuin voit muodostaa kertakirjautumisyhteyden yhdyskäytävän kautta näihin tietolähteisiin. Lisätietoja on [SAP HANA -määrityssivulla](service-gateway-sso-kerberos-sap-hana.md) ja [SAP BW–- CommonCryptoLib (sapcrypto.dll) -määrityssivulla](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md). On myös mahdollista [määrittää SAP BW käytettäväksi gx64krb5 SNC -kirjaston](service-gateway-sso-kerberos-sap-bw-gx64krb.md) kanssa, mutta Microsoft ei suosittele tätä kirjastoa, koska SAP ei enää tue sitä. Käytä sen sijaan CommonCryptoLib- _tai_ gx64krb5-kirjastoa SNC-kirjastona. Älä suorita molempien kirjastojen määritysvaiheita.

> [!NOTE]
> Myös muut SNC-kirjastot saattavat toimia BW-kertakirjautumisen kanssa, mutta Microsoft ei virallisesti tue niitä.

## <a name="run-a-power-bi-report"></a>Power BI -raportin suorittaminen

Kun kaikki määritysvaiheet on suoritettu, voit käyttää Power BI:n **yhdyskäytävän hallintasivua** kertakirjautumisessa käytettävän tietolähteen määrittämiseen. Jos käytössäsi on useita yhdyskäytäviä, varmista, että valitset yhdyskäytävän, jonka olet määrittänyt Kerberos-kertakirjautumiselle. Varmista sitten tietolähteen kohdalla **Lisäasetukset** -kohdassa, että Käytä DirectQuery-kyselyissä kertakirjautumista Kerberoksen kautta -kohta on valittuna.

![Näyttökuva Lisäasetukset-vaihtoehdosta](media/service-gateway-sso-kerberos/advanced-settings.png)

 Julkaise **DirectQuery-pohjainen** raportti Power BI Desktopista. Tämän raportin on käytettävä tietoja, joita käyttäjä voi käyttää ja jotka on yhdistetty (Azure) Active Directory -käyttäjään, joka kirjautuu Power BI -palveluun. Sinun täytyy käyttää DirectQueryä tuonnin sijaan päivityksen toimintotavan vuoksi. Kun päivität tuontipohjaisia raportteja, yhdyskäytävä käyttää **Käyttäjänimi**- ja **Salasana**-kenttiin syöttämiäsi tunnistetietoja tietolähteen luonnin aikana. Toisin sanoen Kerberos-kertakirjautumista **ei** käytetä. Kun julkaiset, varmista myös, että valitset yhdyskäytävän, jonka olet määrittänyt kertakirjautumiselle, jos sinulla on useita yhdyskäytäviä. Power BI -palvelussa sinun pitäisi nyt pystyä päivittämään raportti tai luomaan uusi raportti julkaistun tietojoukon perusteella.

Tämä määritys toimii useimmissa tapauksissa. Kerberoksessa voi kuitenkin olla eri määrityksiä ympäristösi mukaan. Jos raportti ei kuitenkaan lataudu, ota yhteyttä toimialueen järjestelmänvalvojaan asian selvittämiseksi. Jos tietolähteesi on SAP BW, saat lisätietoja myös tietolähdekohtaisista vianmääritysosiosta [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md#troubleshooting)- ja [gx64krb5/gsskrb5](service-gateway-sso-kerberos-sap-bw-gx64krb.md#troubleshooting)-kirjastoille.

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja **paikallisesta tietoyhdyskäytävästä** ja **DirectQuerysta** on seuraavissa resursseissa:

* [Mikä paikallinen tietoyhdyskäytävä on?](/data-integration/gateway/service-gateway-getting-started)
* [DirectQuery Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet](desktop-directquery-data-sources.md)
* [DirectQuery ja SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ja SAP HANA](desktop-directquery-sap-hana.md)
