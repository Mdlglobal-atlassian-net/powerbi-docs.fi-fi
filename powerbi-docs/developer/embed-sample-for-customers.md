---
title: Upotetut analyysitoiminnot ja Power BI -sisällön upottaminen sovellukseen asiakkaille
description: Opi integroimaan tai upottamaan raportteja, raporttinäkymiä tai ruutuja sovellukseen asiakkaita varten käyttämällä upotetuissa analyysitoiminnoissa Power BI -ohjelmointirajapintoja. Lue, miten voit integroida Power BI:n sovellukseesi käyttämällä upotetun analysoinnin ohjelmistoa, upotetun analysoinnin työkaluja tai upotetun liiketoimintatiedon työkaluja.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: nishalit
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: seodec18
ms.date: 02/05/2019
ms.openlocfilehash: 5bb4a739b6a333ecaf0ddc3ee2596fc210033470
ms.sourcegitcommit: 8fda7843a9f0e8193ced4a7a0e5c2dc5386059a6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/18/2019
ms.locfileid: "58174955"
---
# <a name="tutorial-embed-power-bi-content-into-an-application-for-your-customers"></a>Opetusohjelma: Power BI -sisällön upottaminen sovellukseen asiakkaille

**Azuren Power BI Embeddedin** avulla voit upottaa sovellukseen raportteja, raporttinäkymiä tai ruutuja käyttämällä app owns data -hakemiston malleja. **App owns data**-hakemiston malleja käytetään kun kyseessä on sovellus, joka käyttää Power BI:tä upotettuna analyysiympäristönään. **ISV-kehittäjänä** voit luoda Power BI -sisältöä, joka näyttää raportit, raporttinäkymät tai ruudut sovelluksessa, joka on täysin integroitu ja vuorovaikutteinen, edellyttämättä käyttäjiltä Power BI -käyttöoikeutta. Tämä opetusohjelma esittelee, miten raportti integroidaan sovellukseen Power BI .NET SDK:n ja Power BI JavaScript -ohjelmointirajapinnan avulla, kun asiakkaiden käytössä on **Azuren Power BI Embedded**.

![Power BI -raportin upottaminen](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

Tässä opetusohjelmassa opit:
> [!div class="checklist"]
> * Rekisteröimään sovelluksen Azuressa.
> * Upottamaan Power BI -raportin sovellukseen.

## <a name="prerequisites"></a>Edellytykset

Tarvitset seuraavat:

* Tarvitset [Power BI Pro -tilin](../service-self-service-signup-for-power-bi.md) (päätili, jonka käyttäjänimellä ja salasanalla kirjaudut Power BI Pro -tilille) tai [palvelun päänimen (sovellustunnus)](embed-service-principal.md).
* Tarvitset [Microsoft Azure](https://azure.microsoft.com/) -tilauksen.
* Sinulla on oltava oma [Azure Active Directory -vuokraaja ](create-an-azure-active-directory-tenant.md) käyttövalmiina.

Jos et ole rekisteröitynyt **Power BI:hin**, [rekisteröi ilmainen kokeiluversio](https://powerbi.microsoft.com/pricing/) ennen aloittamista.

Jos sinulla ei ole Azure-tilausta, luo [ilmainen tili](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) ennen aloittamista.

## <a name="set-up-your-embedded-analytics-development-environment"></a>Upotettujen analyysitoimintojen kehitysympäristön määrittäminen

Ennen kuin ryhdyt upottamaan raportteja, raporttinäkymiä tai ruutuja sovellukseesi, varmista, että ympäristösi sallii upottamisen Power BI:n avulla.

Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup/AppOwnsData). Sillä pääset nopeasti alkuun ja sillä voit ladata mallisovelluksen, jossa käydään läpi sekä käyttöympäristön luominen että raportin upottaminen.

Jos haluat määrittää ympäristön manuaalisesti, jatka lukemista.

### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Sovelluksen rekisteröiminen Azure Active Directoryyn (Azure AD)

[Rekisteröi sovellus](register-app.md) Azure Active Directoryyn, jotta sovellus saa käyttöoikeuden [Power BI REST -ohjelmointirajapintoihin](https://docs.microsoft.com/rest/api/power-bi/). Kun rekisteröit sovelluksesi, voit määrittää sovelluksen käyttäjätiedot ja käyttöoikeudet Power BI REST -resursseihin. Se, käytätkö päätiliä vai [palvelun päänimeä](embed-service-principal.md), määrittää, miten voit aloittaa sovelluksen rekisteröimisen.

Valitsemasi tapa määrittää, millaisen sovelluksen rekisteröit Azureen.

Jos käytät päätiliä, rekisteröi **alkuperäinen** sovellus. Alkuperäistä sovellusta käytetään, koska käytät ei-vuorovaikutteista kirjautumista.

Jos käytät palvelun päänimeä, sinun täytyy rekisteröidä **palvelinpuolen verkkosovellus**. Rekisteröimällä palvelinpuolen verkkosovelluksen luot sovellussalaisuuden.

## <a name="set-up-your-power-bi-environment"></a>Power BI -ympäristön määrittäminen

### <a name="create-an-app-workspace"></a>Sovelluksen työtilan luominen

Jos upotat asiakkaille raportteja, raporttinäkymiä tai ruutuja, sisältö tulee sijoittaa sovelluksen työtilaan. Voit ottaa käyttöön erityyppisiä työtiloja: [perinteisiä työtiloja](../service-create-workspaces.md) tai [uusia työtiloja](../service-create-the-new-workspaces.md). Jos käytät *päätiliä*, käyttämiesi työtilojen tyypillä ei ole väliä. Jos kirjaudut sovellukseesi *[palvelun päänimellä](embed-service-principal.md)*, sinun täytyy käyttää uusia työtiloja. Molemmissa tapauksissa *päätilin* tai *palvelun päänimen* täytyy olla sovellukseesi liittyvien sovellustyötilojen järjestelmänvalvoja.

### <a name="create-and-publish-your-reports"></a>Luo ja julkaise raportteja

Voit luoda Power BI Desktopia käyttämällä raportteja ja tietojoukkoja ja julkaista raportit sitten sovellustyötilassa. Voit tehdä tämän kahdella tavalla: Loppukäyttäjänä voit julkaista raportteja perinteiseen sovellustyötilaan päätilillä (Power BI Pro -käyttöoikeutta). Jos käytät palvelun päänimeä, voit julkaista raportteja uusiin työtiloihin [Power BI REST -ohjelmointirajapinnoilla](https://docs.microsoft.com/rest/api/power-bi/imports/postimportingroup).

Alla annetaan ohjeet siihen, miten voit julkaista PBIX-raportin Power BI -työtilassasi.

1. Lataa malli [blogiesittely](https://github.com/Microsoft/powerbi-desktop-samples) GitHubista.

    ![raporttimalli](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. Avaa PBIX-raportti **Power BI Desktopissa**.

   ![PBI desktop -raportti](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. Julkaise **sovellustyötiloihin**. Tämä prosessi on erilainen siitä riippuen, käytätkö päätiliä (Power BI Pro -käyttöoikeus) vai palvelun päänimeä. Jos käytät päätiliä, voit julkaista raportin Power BI Desktopissa.  Jos käytät palvelun päänimeä, sinun täytyy käyttää Power BI REST -ohjelmointirajapintoja.

## <a name="embed-content-using-the-sample-application"></a>Sisällön upottaminen mallisovelluksen avulla

Tämä malli on tarkoituksellisesti yksinkertainen esittelyä varten. Sovellussalaisuuden tai päätilin tunnistetietojen suojaaminen on sinun ja sovelluskehittäjiesi vastuulla.

Voit aloittaa sisällön upottamisen mallisovelluksen avulla alla annettujen ohjeiden mukaisesti.

1. Lataa [Visual Studio](https://www.visualstudio.com/) (2013 tai uudempi versio). Muista ladata uusin [NuGet-paketti](https://www.nuget.org/profiles/powerbi).

2. Lataa ensin [App Owns Data -malli](https://github.com/Microsoft/PowerBI-Developer-Samples) GitHubista.

    ![App Owns Data -sovellusmalli](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

3. Avaa **Web.config**-tiedosto mallisovelluksessa. Sinun on täytettävä joitain kenttiä, jotta sovellus voidaan suorittaa. Voit valita **AuthenticationType**-asetuksen arvoksi **MasterUser** tai **ServicePrincipal**. Sinun täytyy käyttää eri kenttiä käyttämästäsi todennustavasta riippuen.

    > [!Note]
    > **AuthenticationType**-asetuksen oletusarvo tässä mallissa on MasterUser.

    <center>

    | **MasterUser** <br> (Power BI Pro -käyttöoikeus) | **ServicePrincipal** <br> (sovellustunnus)|
    |---------------|-------------------|
    | [applicationId](#application-id) | [applicationId](#application-id) |
    | [workspaceId](#workspace-id) | [workspaceId](#workspace-id) |
    | [reportId](#report-id) | [reportId](#report-id) |
    | [pbiUsername](#power-bi-username-and-password) |  |
    | [pbiPassword](#power-bi-username-and-password) |  |
    |  | [applicationsecret](#application-secret) |
    |  | [tenant](#tenant) |

   </center>

    ![Web.config-tiedosto](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

### <a name="application-id"></a>Sovelluksen tunnus

Tämä määrite on pakollinen molemmilla todennustavoilla (päätili ja [palvelun päänimi](embed-service-principal.md)).

Täytä **applicationId**-tiedot **Sovellustunnuksilla** **Azuresta**. **applicationID**:n avulla sovellus tunnistautuu käyttäjille, joilta pyydät käyttöoikeuksia.

Saat **ApplicationID**:n seuraavasti:

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

2. Valitse vasemmassa siirtymisruudussa **Kaikki palvelut** ja sitten **Sovelluksen rekisteröinnit**.

    ![Sovelluksen rekisteröinnin etsintä](media/embed-sample-for-customers/embed-sample-for-customers-003.png)

3. Valitse sovellus, joka tarvitsee **applicationId**-arvon.

    ![Sovelluksen valitseminen](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

4. Näet **sovellustunnuksen**, joka on merkitty GUID-tunnuksena. Käytä tätä **Sovellustunnusta** sovelluksen **applicationId**:nä.

    ![applicationID](media/embed-sample-for-customers/embed-sample-for-customers-007.png)

### <a name="workspace-id"></a>Työtilan tunnus

Tämä määrite on pakollinen molemmilla todennustavoilla (päätili ja [palvelun päänimi](embed-service-principal.md)).

Anna **workspaceId**-kohtaan Power BI:n sovelluksen työtilan GUID. Voit hakea nämä tiedot joko URL-osoitteesta, kun olet kirjautunut Power BI -palveluun, tai PowerShellin avulla.

URL-OSOITE <br>

![workspaceId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

Powershell <br>

```powershell
Get-PowerBIworkspace -name "App Owns Embed Test"
```

   ![workspaceId powershellistä](media/embed-sample-for-customers/embed-sample-for-customers-031-ps.png)

### <a name="report-id"></a>Raporttitunnus

Tämä määrite on pakollinen molemmilla todennustavoilla (päätili ja [palvelun päänimi](embed-service-principal.md)).

Anna **reportId**-kohtaan Power BI:n raportin GUID. Voit hakea nämä tiedot joko URL-osoitteesta, kun olet kirjautunut Power BI -palveluun, tai PowerShellin avulla.

URL-OSOITE<br>

![Raporttitunnus](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

Powershell <br>

```powershell
Get-PowerBIworkspace -name "App Owns Embed Test" | Get-PowerBIReport
```

![reportId powershellistä](media/embed-sample-for-customers/embed-sample-for-customers-032-ps.png)

### <a name="power-bi-username-and-password"></a>Power BI -käyttäjänimi ja -salasana

Näitä määritteitä tarvitaan vain, kun todennustyyppinä on päätili.

Jos todennat [palvelun päänimellä](embed-service-principal.md), sinun ei tarvitse antaa käyttäjänimen ja salasanan määritteitä.

* Lisää **pbiUsername**-kohtaan Power BI -päätili.
* Lisää **pbiPassword**-kohtaan Power BI -päätilin salasana.

### <a name="application-secret"></a>Sovellussalaisuus

Tämä määrite on pakollinen vain, kun käytät todennustyyppinä [palvelun päänimeä](embed-service-principal.md).

Täytä **ApplicationSecret** -tiedot **Avaimet**-osiosta **Sovelluksen rekisteröinnit** -kohdasta **Azuressa**.  Tämä määrite toimii, kun käytät [palvelun päänimeä](embed-service-principal.md).

Saat **ApplicationSecretin** seuraavasti:

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

2. Valitse vasemmassa siirtymisruudussa **Kaikki palvelut** ja sitten **Sovelluksen rekisteröinnit**.

    ![Sovelluksen rekisteröinnin etsintä](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

3. Valitse sovellus, joka käyttää **ApplicationSecretiä**.

    ![Sovelluksen valitseminen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

4. Valitse **Asetukset**.

    ![Valitse Asetukset](media/embed-sample-for-your-organization/embed-sample-for-your-organization-038.png)

5. Valitse **Avaimet**.

    ![Valitse Avaimet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-039.png)

6. Kirjoita nimi **Kuvaus**-ruutuun ja valitse kesto. Valitse sitten **Tallenna** saadaksesi sovellukselle **arvon**. Kun suljet **Avaimet**-ruudun avainarvon tallentamisen jälkeen, arvokenttä näkyy vain piilotettuna. Tässä vaiheessa et pysty noutamaan avaimen arvoa. Jos kadotat avainarvon, luo uusi Azure-portaalissa.

    ![Avainarvo](media/embed-sample-for-your-organization/embed-sample-for-your-organization-031.png)

### <a name="tenant"></a>Vuokraaja

Tämä määrite on pakollinen vain, kun käytät todennustyyppinä [palvelun päänimeä](embed-service-principal.md).

Lisää **tenant**-kohtaan Azure-vuokraajatunnuksesi. Voit hakea nämä tiedot [Azure AD -hallintakeskuksesta](/onedrive/find-your-office-365-tenant-id), kun olet kirjautunut Power BI -palveluun, tai PowerShellin avulla.

### <a name="run-the-application"></a>Suorita sovellus

1. Valitse **Suorita** **Visual Studiossa**.

    ![Suorita sovellus](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

2. Valitse sitten **Upota raportti**. Riippuen siitä mitä sisältöä valitset testattavaksi - raportteja, raporttinäkymiä vai ruutuja - valitse kyseinen vaihtoehto sovelluksessa .

    ![Sisällön valitseminen](media/embed-sample-for-customers/embed-sample-for-customers-034.png)

3. Voit nyt tarkastella raporttia mallisovelluksessa.

    ![Näytä sovellus](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

## <a name="embed-content-within-your-application"></a>Sisällön upottaminen sovellukseen

Vaikka sisältöä upotetaan [Power BI REST -ohjelmointirajapintojen](https://docs.microsoft.com/rest/api/power-bi/) avulla, tässä artikkelissa kuvatut esimerkkikoodit on luotu **.NET SDK:n** avulla.

Jos haluat upottaa sovellukseen sisältöä asiakkaillesi, tarvitset päätilillesi **käyttöoikeustietueen** tai [palvelun päänimen](embed-service-principal.md) **Azure AD:stä**. Sinun täytyy hankkia [Azure AD -käyttöoikeustietue](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) Power BI-sovelluksellesi, ennen kuin voit kutsua [Power BI REST -ohjelmointirajapintoja](https://docs.microsoft.com/rest/api/power-bi/).

Jotta voit luoda Power BI -asiakasohjelman **käyttöoikeustietueen** avulla, sinun on luotava Power BI -asiakasohjelmaobjekti, joka mahdollistaa vuorovaikutuksen [Power BI REST -ohjelmointirajapintojen](https://docs.microsoft.com/rest/api/power-bi/) kanssa. Power BI -asiakasohjelmaobjekti luodaan sijoittamalla **käyttöoikeustietue** ***Microsoft.Rest.TokenCredentials***-objektiin.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. it's used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Upotettavan sisältökohteen hankkiminen

Power BI -asiakasohjelmaobjektin avulla voit noutaa viitteen upotettavalle kohteelle.

Tässä on koodimalli siitä, miten voit noutaa ensimmäisen raportin tietystä työtilasta.

*Malli sisältökohteen hankkimisesta sen mukaan, onko upotettava sisältökohde raportti, raporttinäkymä vai ruutu, on saatavilla [mallisovelluksen](https://github.com/Microsoft/PowerBI-Developer-Samples) Services\EmbedService.cs-tiedostosta.*

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You need to provide the workspaceId where the dashboard resides.
ODataResponseListReport reports = await client.Reports.GetReportsInGroupAsync(workspaceId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Upotustunnuksen luominen

Luo upotustunnus, jota voidaan käyttää JavaScript-ohjelmointirajapinnasta. Upotustunnus on yksilöllinen upotettavalle kohteelle. Siten kun upotat tietyn Power BI -sisältökohteen, sinun on luotava sille uusi upotustunnus. Saat lisätietoja tästä ja käytettävästä **käyttöoikeustasosta** artikkelista [GenerateToken-ohjelmointirajapinta](https://msdn.microsoft.com/library/mt784614.aspx).

*Malli sisältökohteen upotustunnuksen luomisesta sen mukaan, onko upotettava sisältökohde raportti, raporttinäkymä vai ruutu, on saatavilla [mallisovelluksen](https://github.com/Microsoft/PowerBI-Developer-Samples) Services\EmbedService.cs-tiedostosta.*

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(workspaceId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```

Luokka luodaan kohteille **EmbedConfig** ja **TileEmbedConfig**. Malli on saatavilla **Models\EmbedConfig.cs**-tiedostossa ja **Models\TileEmbedConfig.cs-tiedostossa**.

### <a name="load-an-item-using-javascript"></a>Lataa kohde JavaScriptin avulla

Voit JavaScriptin avulla ladata raportin verkkosivun jako-elementtiin.

[Playground-työkalun](https://microsoft.github.io/PowerBI-JavaScript/demo) avulla saat kokonaisen mallin JavaScript-ohjelmointirajapinnan käytöstä. Tämä Playground-työkalu on nopea tapa kokeilla erilaisia Power BI Embedded -malleja. Saat lisätietoja JavaScript-ohjelmointirajapinnasta myös vierailemalla [Power BI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) -sivulla.

Tässä mallissa käytetään **EmbedConfig**-mallia ja **TileEmbedConfig**-mallia yhdessä raportin näkymien kanssa.

*Malli näkymän lisäämisestä raporttia, koontinäyttöä tai ruutua varten on saatavilla [mallisovelluksen](#embed-content-using-the-sample-application) Views\Home\EmbedReport.cshtml-, Views\Home\EmbedDashboard.cshtml- tai Views\Home\Embedtile.cshtml-tiedostoissa.*

```javascript
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="move-to-production"></a>Siirry tuotantoon

Kun olet nyt kehittänyt sovelluksesi, on aika varata sovelluksen työtilalle kapasiteettia. 

> [!Important]
> Varattua kapasiteettia tarvitaan kun siirrytään tuotantoon.

### <a name="create-a-dedicated-capacity"></a>Luo varattua kapasiteettia

Luomalla varattua kapasiteettia voit hyötyä siitä, että asiakkaalle varataan tietty resurssi. Voit ostaa varattua kapasiteettia [Microsoft Azure -portaalissa](https://portal.azure.com). Lisätietoa Power BI Embedded ‑kapasiteetin luomisesta saat ohjeaiheesta [Power BI Embedded -kapasiteetin luominen Azure-portaalissa](azure-pbie-create-capacity.md).

Seuraavan taulukon avulla voit määrittää, mikä Power BI Embedded -kapasiteetti sopii parhaiten tarpeisiisi.

| Kapasiteetin solmu | Ytimiä yhteensä<br/>*(Tausta ja edusta)* | Taustan ytimet | Edustan ytimet | DirectQueryn/live-yhteyden rajoitukset|
| --- | --- | --- | --- | --- | --- |
| A1 |1 näennäisydin |0,5 ydintä, 3 Gt RAM |0,5 ydintä |0,5 sekunnissa |
| A2 |2 näennäisydintä |1 ydin, 5 Gt RAM |1 ydin | 10 sekunnissa |
| A3 |4 näennäisydintä |2 ydintä, 10 Gt RAM |2 ydintä | 15 sekunnissa |
| A4 |8 näennäisydintä |4 ydin(tä), 25 Gt RAM |4 ydintä |30 sekunnissa |
| A5 |16 näennäisydintä |8 ydintä, 50 Gt RAM |8 ydintä |60 sekunnissa |
| A6 |32 näennäisydintä |16 ydintä, 100 Gt RAM |16 ydintä |120 sekunnissa |

**_A-varastointiyksiköillä et pysty käyttämään Power BI -sisältöä ilmaisella Power BI -käyttöoikeudella._**

Upotustunnusten käyttö PRO-käyttöoikeudella on tarkoitettu kehitystestaukseen, joten Power BI -päätili tai palvelun päänimi voi luoda vain rajallisen määrän upotettavia tunnuksia. Hyötykäyttöympäristössä upottamista varten täytyy ostaa varattua kapasiteettia. Varatun kapasiteetin avulla luotavien upotettavien tunnuksien määrää ei ole rajoitettu. Siirry [Käytettävissä olevat ominaisuudet](https://docs.microsoft.com/rest/api/power-bi/availablefeatures/getavailablefeatures) -kohtaan tarkistaaksesi käyttöarvon, joka ilmaisee nykyisen upotetun käytön prosenttilukuna. Käytettävä määrä on päätilikohtainen.

Lisätietoja on ohjeaiheessa [Upotetun analytiikan kapasiteetin suunnittelun tekninen raportti](https://aka.ms/pbiewhitepaper).

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>Määritä sovellustyötila varattuun kapasiteettiin

Kun olet luonut varatun kapasiteetin, voit määrittää sovellustyötilan kyseiselle varatulle kapasiteetille.

Jos haluat määrittää varatun kapasiteetin työtilalle [palvelun päänimellä](embed-service-principal.md), käytä [Power BI REST -ohjelmointirajapintaa](https://docs.microsoft.com/rest/api/power-bi/capacities/groups_assigntocapacity). Kun käytät Power BI REST -ohjelmointirajapintoja, muista käyttää [palvelun päänimen objektitunnusta](embed-service-principal.md#how-to-get-the-service-principal-object-id).

Voit määrittää varatun kapasiteetin työtilalle **päätilillä** alla annettujen ohjeiden mukaisesti.

1. Laajenna **Power BI -palvelussa** työtiloja ja valitse ellipsikuvake työtilalle, jotka käytät sisällön upottamiseen. Valitse **Muokkaa työtiloja**.

    ![Muokkaa työtilaa](media/embed-sample-for-customers/embed-sample-for-customers-036.png)

2. Avaa **Lisäasetukset**, ota sitten käyttöön **Varattu kapasiteetti**, ja valitse luomasi varattu kapasiteetti. Valitse **Tallenna**.

    ![Määritä varattu kapasiteetti](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

3. **Tallennuksen** jälkeen sovellustyötilan nimen vieressä pitäisi näkyä **vinoneliö**.

    ![sovellustyötila sidottuna kapasiteettiin](media/embed-sample-for-customers/embed-sample-for-customers-037.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa olet oppinut, miten voit upottaa Power BI-sisältöä sovellukseen asiakkaillesi. Voit myös yrittää upottaa Power BI -sisältöä organisaatiollesi.

> [!div class="nextstepaction"]
>[Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
