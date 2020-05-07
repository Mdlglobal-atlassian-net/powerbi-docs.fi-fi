---
title: Verkkosovelluksen välityspalvelimen ja liitettyjen Active Directory -palvelujen käyttö – Power BI -raporttipalvelin
description: Opi käyttämään verkkosovelluksen välityspalvelinta (WAP) ja liitettyjä Active Directory -palveluja (AD FS) yhteyden muodostamiseksi Power BI -raporttipalvelimeen ja SQL-palvelimen raportointipalveluihin (SSRS), 2016 ja uudempiin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/14/2020
ms.openlocfilehash: 2caa96aceef90ad1d25a521cbf4a3f699a2a64e0
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "76042436"
---
# <a name="use-web-application-proxy-and-active-directory-federated-services---power-bi-report-server"></a>Verkkosovelluksen välityspalvelimen ja liitettyjen Active Directory -palvelujen käyttö – Power BI -raporttipalvelin

Tässä artikkelissa käsitellään verkkosovelluksen välityspalvelimen (WAP) ja liitettyjen Active Directory -palvelujen (AD FS) käyttöä yhteyden muodostamiseksi Power BI -raporttipalvelimeen sekä SQL-palvelimen raportointipalveluja (SSRS), 2016 ja uudempia. Tämän integraation avulla yritysverkon ulkopuolelle pääsevät käyttäjät voivat käyttää Power BI -raporttipalvelimen ja raportointipalvelun raportteja asiakasselaimilta ja pysyä suojassa AD FS -esitodennuksen avulla. Power BI -mobiilisovelluksissa sinun on myös [määritettävä OAuth muodostamaan yhteys Power BI -raporttipalvelimeen ja SSRS](../consumer/mobile/mobile-oauth-ssrs.md):ään.

## <a name="prerequisites"></a>Edellytykset

### <a name="domain-name-services-dns-configuration"></a>Nimipalvelujärjestelmien (DNS) määritys

- Määritä julkinen URL-osoite, johon käyttäjä muodostaa yhteyden. Se voi näyttää tämän esimerkin kaltaiselta: `https://reports.contosolab.com`.
- Määritä isäntänimen, esimerkiksi `reports.contosolab.com`, osoittamaan verkkosovelluksen välityspalvelimen (WAP) julkiseen IP-osoitteeseen osoittava DNS-tietue.
- Määritä julkinen DNS-tietue AD FS -palvelimellesi. Olet esimerkiksi ehkä määrittänyt ADFS-palvelimen käyttäen seuraavaa URL-osoitetta: `https://adfs.contosolab.com`.
- Määritä DNS-tietueesi osoittamaan verkkosovelluksen välityspalvelimen (WAP) julkiseen IP-osoitteeseen, esimerkiksi `adfs.contosolab.com`. Se julkaistaan osana WAP-sovellusta.

### <a name="certificates"></a>Varmenteet

Sinun täytyy määrittää varmenteet sekä WAP-sovellukselle että AD FS -palvelimelle. Molempien näiden varmenteiden on oltava peräisin hyväksytyltä varmenteiden myöntäjältä, jonka laitteesi tunnistavat.

## <a name="1-configure-the-report-server"></a>1. Määritä raporttipalvelin

On varmistettava, että palvelun päänimi (SPN) on kelvollinen. Kelvollinen palvelun päänimi mahdollistaa asianmukaisen Kerberos-todentamisen sekä todennuksen neuvottelun raporttipalvelimella.

### <a name="service-principal-name-spn"></a>Palvelun päänimi (SPN)

SPN eli palvelun päänimi on Kerberos-todennusta käyttävän palvelun yksilöivä tunniste. Varmista, että raporttipalvelimellasi on asianmukainen HTTP-palvelun päänimi.

Lisätietoja asianmukaisen palvelun päänimen (SPN) määrittämisestä raporttipalvelimelle on ohjeaiheessa [Palvelun päänimen (SPN) rekisteröiminen raporttipalvelimelle](https://docs.microsoft.com/sql/reporting-services/report-server/register-a-service-principal-name-spn-for-a-report-server).

### <a name="enabling-negotiate-authentication"></a>Todennuksen neuvottelun ottaminen käyttöön

Sinun on määritettävä raporttipalvelimen todennustyypiksi RSWindowsNegotiate, jos haluat määrittää raporttipalvelimen käyttämään Kerberos-todennusta. Voit määrittää sen rsreportserver.config-tiedostossa.

```
<AuthenticationTypes>

    <RSWindowsNegotiate />

    <RSWindowsNTLM />

</AuthenticationTypes>
```

Lisätietoja on artikkeleissa [Reporting Services -määritystiedoston muokkaaminen](https://docs.microsoft.com/sql/reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config) ja [Windows-todennuksen määrittäminen raporttipalvelimessa](https://docs.microsoft.com/sql/reporting-services/security/configure-windows-authentication-on-the-report-server).

## <a name="2-configure-active-directory-federation-services-ad-fs"></a>2. Määritä liitetyt Active Directory -palvelut (AD FS)

Sinun on määritettävä AD FS-järjestelmä Windows 2016 -palvelimeen käyttöympäristössäsi. Voit tehdä sen Palvelinten hallinnassa valitsemalla Hallinta-kohdassa Lisää rooleja ja ominaisuuksia -vaihtoehdon. Lisätietoja on artikkelissa [Active Directory -liittoutumispalvelut](https://docs.microsoft.com/windows-server/identity/active-directory-federation-services).

Suorita nämä vaiheet AD FS -palvelimessa AD FS -hallintasovelluksen avulla.

1. Napsauta hiiren kakkospainikkeella **Luottavan osapuolen luottamukset** > **Lisää luottavan osapuolen luottamus**.

    ![Luottavan osapuolen luottamuksen lisääminen](media/connect-adfs-wap-report-server/report-server-adfs-add-relying-party-trust.png)

2. Seuraa ohjatun toiminnon **Lisää luottavan osapuolen luottamus** vaiheita.

    Valitse vaihtoehto **Ei väitteistä tietoinen** Windowsin integroidun suojauksen käyttämiseksi todentamismekanismina.

    ![Tervetuloa ohjattuun toimintoon Lisää luottavan osapuolen luottamus](media/connect-adfs-wap-report-server/report-server-adfs-add-relying-party-trust-welcome.png)

    Anna haluamasi nimi kohtaan **Määritä näyttönimi** ja valitse **Seuraava**.
    Lisää luottavan osapuolen luottamuksen tunniste: `<ADFS\_URL>/adfs/services/trust`

    Esimerkiksi: `https://adfs.contosolab.com/adfs/services/trust`

    ![Raporttipalvelin](media/connect-adfs-wap-report-server/report-server-adfs-configure-identifiers.png)

    Valitse **käyttöoikeuskäytäntö**, joka soveltuu organisaatiosi tarpeisiin, ja valitse sitten **Seuraava**.

    ![Valitse käyttöoikeuksien valvonta](media/connect-adfs-wap-report-server/report-server-adfs-choose-access-control.png)
    
    Valitse **Seuraava** ja valitse sitten **Lopeta** ohjatun toiminnon **Lisää luottavan osapuolen luottamus** loppuun suorittamiseksi.

    Kun olet suorittanut toiminnon valmiiksi, luottavan osapuolten luottamusten ominaisuuksien tulisi näyttää seuraavanlaisilta.

    ![Luottavan osapuolen luottamukset](media/connect-adfs-wap-report-server/report-server-adfs-relying-party-trusts.png)

## <a name="3-configure-web-application-proxy-wap"></a>3. Verkkosovellusten välityspalvelimen (WAP) määrittäminen

Sinun kannattaa ottaa Web Application Proxy (Rooli) -Windows-rooli käyttöön ympäristösi palvelimessa. Tämä täytyy tehdä Windows 2016 -palvelimessa. Lisätietoja on artikkeleissa [Web Application Proxy Windows Server 2016:ssa](https://docs.microsoft.com/windows-server/remote/remote-access/web-application-proxy/web-application-proxy-windows-server) ja [Sovellusten julkaiseminen käyttäen AD FS -esitodennusta](https://docs.microsoft.com/windows-server/remote/remote-access/web-application-proxy/Publishing-Applications-using-AD-FS-Preauthentication).

### <a name="configure-constrained-delegation"></a>Rajoitetun delegoinnin määrittäminen

Lomaketodennuksesta Windows-todennukseen siirtyminen edellyttää rajoitetun delegoinnin ja protokollan siirron käyttämistä. Tämä vaihe on osa Kerberos-määritystä. Olemme jo määritelleet raporttipalvelimen päänimen osana raporttipalvelimen määritystä.

Tässä vaiheessa on määritettävä rajoitettu delegointi WAP-palvelimen konetilillä Active Directoryssa. Sinun on ehkä tarpeen tehdä yhteistyötä toimialueen järjestelmänvalvojan kanssa, jos sinulla ei ole Active Directory -käyttöoikeuksia.

Jos haluat määrittää rajoitetun delegoinnin, suorita seuraavat vaiheet.

1. Käynnistä **Active Directory Users and Computers** (Active Directory -käyttäjät ja -tietokoneet) -työkalu tietokoneessa, johon on asennettu Active Directory -työkalut.
2. Etsi WAP-palvelimesi konetili. Oletuksena se on **Tietokoneet**-säilössä.
3. Napsauta WAP-palvelinta hiiren kakkospainikkeella ja siirry **Ominaisuudet**-kohtaan.
4. Valitse **Delegointi**-välilehdeltä **Luota tähän tietokoneeseen vain määritettyihin palveluihin delegointia varten** ja valitse sitten **Käytä mitä tahansa todennusprotokollaa**.

    ![Luota tähän tietokoneeseen](media/connect-adfs-wap-report-server/report-server-adfs-delegation-use-any.png)

1. Tämä asetus määrittää rajoitetun delegoinnin tälle WAP-palvelinkoneen tilille. Tämän jälkeen täytyy määrittää palvelut, joihin tämän koneen sallitaan delegoida.
2. Valitse **Lisää** palveluruudun alapuolelta.

    ![AD FS Lisää luottamus](media/connect-adfs-wap-report-server/report-server-adfs-trust-add.png)

1. Valitse **Käyttäjät tai tietokoneet**.
2. Anna palvelutili, jota käytät raporttipalvelimessa. Tämä on sama tili, jota olet aikaisemmin käyttänyt HTTP-palvelun päänimen lisäämiseen osassa [Raporttipalvelimen määrittäminen](#1-configure-the-report-server). 

3. Valitse HTTP-palvelun päänimi ja valitse sitten **OK**.

    > [!NOTE]
    > Saatat nähdä vain NetBIOSin SPN:n. Todellisuudessa sekä NetBIOSin SPN että FQDN:n SPN valitaan.

1. Kun **Laajennettu**-valintaruutu on valittuna, tuloksen pitäisi näyttää seuraavanlaiselta.

    ![WAP-ominaisuudet](media/connect-adfs-wap-report-server/report-server-wap-properties.png)

### <a name="add-wap-application"></a>WAP-sovelluksen lisääminen

1. Avaa verkkosovelluksen välityspalvelimella **etäkäytön hallinnan** konsoli ja valitse siirtymisruudusta **Verkkosovelluksen välityspalvelin**. 

2. Valitse **Tehtävät**-ruudusta **Julkaise**.

2. Valitse aloitussivulta **Seuraava**.

    ![Tervetuloa julkaisemaan](media/connect-adfs-wap-report-server/report-server-welcome-publish-new-app-wizard.png)

3. Valitse **Esitodennus**-sivulta**Liitetyt Active Directory -palvelut (AD FS)** , valitse sitten **Seuraava**.

    ![Esitodennus](media/connect-adfs-wap-report-server/report-server-preauthentication-new-app-wizard.png)

4. Valitse **verkko- ja MSOFBA**-esitodennus, koska tarkoituksena on määrittää vain selaimen käyttöoikeudet raporttipalvelimelle, ei mobiilisovellusoikeuksia.

    ![Tuetut asiakkaat](media/connect-adfs-wap-report-server/report-server-supported-clients-publish-new-app-wizard.png)

5. Lisää **luottava osapuoli**, jonka olemme luoneet AD FS -palvelimella alla kuvatulla tavalla, ja valitse sitten **Seuraava**.

    ![Luottavan osapuolen julkaiseminen](media/connect-adfs-wap-report-server/report-server-relying-party-publish-new-app-wizard.png)

6. Syötä **Ulkoinen URL** -osassa WAP-palvelimelle määritetty julkisesti käytettävissä oleva URL-osoite. Lisää raporttipalvelimella määritetty URL-osoite (raporttipalvelimen määritysten hallinta) alla kuvatulla tavalla **Taustapalvelimen URL** -osassa. Lisää raporttipalvelimen palvelun päänimi **Taustapalvelimen SPN** -osassa.

    ![Asetusten julkaiseminen](media/connect-adfs-wap-report-server/report-server-publishing-settings-new-app-wizard.png)

7. Valitse **Seuraava** ja **Julkaise**.
8. Suorita seuraava PowerShell-komento WAP-määrityksen vahvistamiseksi.

    ```
    Get-WebApplicationProxyApplication "PBIRSBrowser" | FL
    ```

    ![PowerShell-komento](media/connect-adfs-wap-report-server/report-server-powershell-get-webapplication.png)

## <a name="connect-to-the-report-server-through-the-browser"></a>Muodosta yhteys raporttipalvelimeen selaimen kautta

Voit sitten käyttää julkista WAPin URL-osoitetta, esimerkiksi `https://reports.contosolab.com/ReportServer` verkkopalvelulle ja `https://reports.contosolab.com/Reports` verkkoportaalille, selaimelta. Kun olet suorittanut onnistuneen todennuksen, voit tarkastella raportteja.

![AD FS -kirjautuminen](media/connect-adfs-wap-report-server/report-server-adfs-sign-in.png)

## <a name="next-steps"></a>Seuraavat vaiheet

* [Määritä OAuth muodostamaan yhteys Power BI -raporttipalvelimeen ja SSRS:ään](../consumer/mobile/mobile-oauth-ssrs.md)
*[Mikä on Power BI -raporttipalvelin?](get-started.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

