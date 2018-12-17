---
title: Upotetut analyysitoiminnot ja Power BI -sisällön upottaminen sovellukseen asiakkaille
description: Opi integroimaan tai upottamaan raportteja, raporttinäkymiä tai ruutuja sovellukseen asiakkaita varten käyttämällä upotetuissa analyysitoiminnoissa Power BI -ohjelmointirajapintoja. Lue, miten voit integroida Power BI:n sovellukseesi käyttämällä upotettujen analyysitoimintojen ohjelmistoa, upotettujen analyysitoimintojen työkaluja tai upotetun liiketoimintatiedon hallinnan työkaluja.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: e396f46987ef14aac9361e8f7ef41e90b2d8383e
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180871"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-customers"></a>Opetusohjelma: Power BI -raportin, raporttinäkymän tai ruudun upottaminen sovellukseen asiakkaita varten

**Azuren Power BI Embeddedin** avulla voit upottaa sovellukseen raportteja, raporttinäkymiä tai ruutuja käyttämällä app owns data -hakemiston malleja. **App owns data**-hakemiston malleja käytetään kun kyseessä on sovellus, joka käyttää Power BI:tä upotettuna analyysiympäristönään. **ISV-kehittäjänä** voit luoda Power BI -sisältöä, joka näyttää raportit, raporttinäkymät tai ruudut sovelluksessa, joka on täysin integroitu ja vuorovaikutteinen, edellyttämättä käyttäjiltä Power BI -käyttöoikeutta. Tämä opetusohjelma esittelee, miten raportti integroidaan sovellukseen käyttämällä Power BI .NET SDK:ta Power BI JavaScript -ohjelmointirajapinnan kanssa, kun asiakkaiden käytössä on **Azuren Power BI Embedded**.

Tässä opetusohjelmassa opit:
> [!div class="checklist"]
> * Rekisteröimään sovelluksen Azuressa.
> * Upottamaan Power BI -raportin sovellukseen.

## <a name="prerequisites"></a>Edellytykset

Sinulla täytyy olla **Power BI Pro** -tili (tämä tili on **päätilisi**) ja **Microsoft Azure** -tilaus aloittaaksesi.

* Jos et ole rekisteröitynyt **Power BI:hin**, [rekisteröi ilmainen kokeiluversio](https://powerbi.microsoft.com/en-us/pricing/) ennen aloittamista.
* Jos sinulla ei ole Azure-tilausta, luo [ilmainen tili](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) ennen aloittamista.
* Sinulla on oltava oma [Azure Active Directory -vuokraaja ](create-an-azure-active-directory-tenant.md) asetettuna.
* [Visual Studion](https://www.visualstudio.com/) (2013 tai uudempi versio) on oltava asennettuna.

## <a name="set-up-your-embedded-analytics-development-environment"></a>Upotettujen analyysitoimintojen kehitysympäristön määrittäminen

Ennen kuin ryhdyt upottamaan raportteja, raporttinäkymiä tai ruutuja sovellukseesi, varmista, että ympäristösi sallii upottamisen Power BI:n avulla.

Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup/AppOwnsData) päästäksesi nopeasti alkuun ja ladataksesi mallisovelluksen, jossa käydään läpi sekä käyttöympäristön luominen että raportin upottaminen.

Jos haluat määrittää ympäristön manuaalisesti, jatka lukemista.

### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Sovelluksen rekisteröiminen Azure Active Directoryyn (Azure AD)

Rekisteröi sovellus Azure Active Directoryyn, jotta sovellus saa käyttöoikeuden Power BI REST -ohjelmointirajapintoihin. Kun rekisteröit sovelluksesi, voit määrittää sovelluksen käyttäjätiedot ja käyttöoikeudet Power BI REST -resursseihin.

1. Hyväksy [Microsoft Power BI -ohjelmointirajapinnan ehdot](https://powerbi.microsoft.com/api-terms).

2. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

    ![Azure-pääportaali](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

3. Valitse vasemmassa siirtymisruudussa **Kaikki palvelut**, valitse **Sovelluksen rekisteröinti** ja valitse sitten **Uuden sovelluksen rekisteröinti**.

    ![Sovelluksen rekisteröinnin etsiminen](media/embed-sample-for-customers/embed-sample-for-customers-003.png)</br>
    ![Uuden sovelluksen rekisteröinti](media/embed-sample-for-customers/embed-sample-for-customers-004.png)

4. Noudata kehotteita ja luo uusi sovellus. App owns data -mallin kanssa on valittava **Alkuperäinen**-sovellustyyppi. Sinun täytyy myös antaa **Uudelleenohjaus -URL-osoite**, jota **Azure AD** käyttää palauttaessaan tunnusvastauksia. Anna sovellukselle määritetty arvo (esimerkiksi: `http://localhost:13526/Redirect`).

    ![Luo sovellus](media/embed-sample-for-customers/embed-sample-for-customers-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Määritä sovellukselle käyttöoikeudet Azure Active Directorystä

Ota käyttöön sovellukselle lisäkäyttöoikeuksia sovelluksen rekisteröintisivulla annettujen käyttöoikeuksien lisäksi. Kirjaudu sisään *päätilillä*, jota käytät upottamiseen. Päätilin on oltava yleinen järjestelmänvalvojan tili.

### <a name="use-the-azure-active-directory-portal"></a>Azure Active Directory -portaalin käyttäminen

1. Selaa kohtaan [Sovelluksen rekisteröinnit](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) Azure-portaalissa ja valitse sovellus, jota käytät upottamiseen.

    ![Sovelluksen valitseminen](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

2. Valitse **Asetukset**, valitse sitten **Ohjelmointirajapinnan käyttöoikeudet** ja valitse vielä **Tarvittavat käyttöoikeudet**.

    ![Vaaditut käyttöoikeudet](media/embed-sample-for-customers/embed-sample-for-customers-008.png)

3. Valitse **Windows Azure Active Directory** ja varmista sitten, että **Käytä hakemistoa kirjautuneena käyttäjänä** on valittuna. Valitse **Tallenna**.

    ![Windows Azure AD -käyttöoikeudet](media/embed-sample-for-customers/embed-sample-for-customers-011.png)

4. Valitse **Lisää**.

    ![Lisää käyttöoikeuksia](media/embed-sample-for-customers/embed-sample-for-customers-012.png)

5. Valitse **Valitse ohjelmointirajapinta**.

    ![Lisää API-käyttöoikeuksia](media/embed-sample-for-customers/embed-sample-for-customers-013.png)

6. Valitse **Power BI -palvelu** ja sitten **Valitse**.

    ![Valitse PBI -palvelut](media/embed-sample-for-customers/embed-sample-for-customers-014.png)

7. Valitse kaikki käyttöoikeudet kohdasta **Delegoidut käyttöoikeudet**. Kun olet valmis, valitse **Tallenna**.

    ![Valitse delegoidut käyttöoikeudet](media/embed-sample-for-customers/embed-sample-for-customers-015.png)

8. Valitse kohdasta **Tarvittavat käyttöoikeudet** **Myönnä käyttöoikeuksia**.

    **Myönnä käyttöoikeuksia** -toiminto edellyttää *päätiliä*, jotta Azure AD ei pyydä lupaa. Jos tämän toiminnon suorittava tili on yleinen järjestelmänvalvoja, tämän sovelluksen käyttöoikeudet on myönnettävä organisaation kaikille käyttäjille. Jos tämän toiminnon suorittava tili on *päätili* eikä se ole yleinen järjestelmänvalvoja, sovelluksen käyttöoikeudet on myönnettävä vain *päätilille*.

    ![Käyttöoikeuksien myöntäminen tarvittavassa käyttöoikeusikkunassa](media/embed-sample-for-customers/embed-sample-for-customers-016.png)

## <a name="set-up-your-power-bi-environment"></a>Power BI -ympäristön määrittäminen

### <a name="create-an-app-workspace"></a>Sovelluksen työtilan luominen

Jos upotat asiakkaille raportteja, raporttinäkymiä tai ruutuja, sisältö tulee sijoittaa sovelluksen työtilaan. *Päätilin* on oltava sovelluksen työtilan järjestelmänvalvoja.

1. Aloita luomalla työtila. Valitse **Työtilat** > **Luo sovelluksen työtila**. Sijoita Luo sovellus -työtilassa sisältö, johon sovelluksesi on päästävä.

    ![Työtilan luominen](media/embed-sample-for-customers/embed-sample-for-customers-020.png)

2. Anna työtilalle nimi. Jos vastaava **työtilan tunnus** ei ole käytettävissä, muokkaa nimeä niin, että saat yksilöllisen tunnuksen.

    ![Työtila nimeäminen](media/embed-sample-for-customers/embed-sample-for-customers-021.png)

3. Sinun täytyy määrittää joitakin asetuksia. Jos valitset vaihtoehdon **Julkinen**, kuka tahansa organisaatiossasi voi nähdä, mitä työtilassa on. Jos valitset vaihtoehdon **Yksityinen**, vain työtilan jäsenet voivat nähdä sen sisällön.

    ![Yksityinen/Julkinen](media/embed-sample-for-customers/embed-sample-for-customers-022.png)

    Julkinen/Yksityinen-asetusta ei voi enää muuttaa, kun olet kerran luonut ryhmän.

4. Voit myös valita, onko jäsenillä **muokkaus-** vai **vain tarkastelu** ‑käyttöoikeudet.

    ![Jäsenien lisääminen](media/embed-sample-for-customers/embed-sample-for-customers-023.png)

5. Lisää niiden ihmisten sähköpostiosoitteet, joille haluat antaa työtilan käyttöoikeudet, ja valitse **Lisää**. Et voi lisätä ryhmien aliaksia, vain yksittäisiä ihmisiä.

6. Päätä, onko kukin henkilö jäsen vai järjestelmänvalvoja. Järjestelmänvalvojat voivat muokata työtilaa itse ja muun muassa lisätä muita jäseniä. Jäsenet voivat muokata sisältöä työtilassa, ellei heillä ole käyttöoikeuksia pelkästään tarkasteluun. Sekä järjestelmänvalvojat että jäsenet voivat julkaista sovelluksen.

    Voit nyt tarkastella uutta työtilaa. Power BI luo työtilan ja avaa sen. Työtila ilmestyy luetteloon työtiloista, joiden jäsen olet. Järjestelmänvalvojana voit valita kolme pistettä (...) ja palata takaisin tekemään työtilaan muutoksia, lisäämään uusia jäseniä ja muuttamaan jäsenten käyttöoikeuksia.

    ![Uusi työtila](media/embed-sample-for-customers/embed-sample-for-customers-025.png)

### <a name="create-and-publish-your-reports"></a>Luo ja julkaise raportteja

Voit luoda Power BI Desktopia käyttämällä raportteja ja tietojoukkoja ja julkaista raportit sitten sovellustyötilassa. Raportit julkaiseva loppukäyttäjä tarvitsee Power BI Pro ‑käyttöoikeudet sovellustyötilassa julkaisemiseen.

1. Lataa malli [blogiesittely](https://github.com/Microsoft/powerbi-desktop-samples) GitHubista.

    ![raporttimalli](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. Avaa PBIX raporttimalli **Power BI Desktopissa**

   ![PBI desktop -raportti](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. Julkaise **sovelluksen työtilassa**

   ![Julkaise työpöydän raportti](media/embed-sample-for-customers/embed-sample-for-customers-028.png)

    Voit nyt tarkastella raporttia verkossa Power BI -palvelussa.

   ![PBI-työpöydän raporttinäkymä palvelussa](media/embed-sample-for-customers/embed-sample-for-customers-029.png)

## <a name="embed-your-content-using-the-sample-application"></a>Upota sisältöä saman mallisovelluksen avulla

Seuraa näitä ohjeita aloittaaksesi sisällön upottamisen mallisovelluksen avulla.

1. Lataa ensin [App Owns Data -malli](https://github.com/Microsoft/PowerBI-Developer-Samples) GitHubista.

    ![App Owns Data -sovellusmalli](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

2. Avaa mallisovelluksessa Web.config-tiedosto. Sinun on täytettävä viisi kenttää, jotta sovellus voidaan suorittaa onnistuneesti. Ne ovat **applicationId**, **workspaceId**, **reportId**, **pbiUsername** ja **pbiPassword**.

    ![Web.config-tiedosto](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

    Täytä **applicationId**-tiedot **Sovellustunnuksilla** **Azuresta**. **applicationID**:n avulla sovellus tunnistautuu käyttäjille, joilta pyydät käyttöoikeuksia. Saat **ApplicationID**:n seuraavasti:

    Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

    ![Azure-pääportaali](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

    Valitse vasemmassa siirtymisruudussa **Kaikki palvelut** ja sitten **Sovelluksen rekisteröinnit**.

    ![Sovelluksen rekisteröinnin etsintä](media/embed-sample-for-customers/embed-sample-for-customers-003.png)

    Valitse sovellus, jolle haluat **applicationId**:n.

    ![Sovelluksen valitseminen](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

    Sinun pitäisi nähdä **Sovellustunnus** , joka on merkitty GUID-tunnuksena. Käytä tätä **Sovellustunnusta** sovelluksen **applicationId**:nä.

    ![applicationID](media/embed-sample-for-customers/embed-sample-for-customers-007.png)

    Täytä **workspaceId** Power BI:n **sovelluksen työtilan GUID**-tiedoilla.

    ![workspaceId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    Täytä **raporttitunnus** Power BI:n **raportin GUID** -tiedoilla.

    ![Raporttitunnus](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

    * Täytä **pbikäyttäjätunnus** Power BI:n pääkäyttäjätilin tiedoilla.
    * Täytä **pbisalasana** Power BI:n pääkäyttäjätilin salasanalla.

3. Suorita sovellus!

    Valitse ensin **Suorita** **Visual Studiossa**.

    ![Suorita sovellus](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

    Valitse sitten **Upota raportti**. Riippuen siitä mitä sisältöä valitset testattavaksi - raportteja, raporttinäkymiä vai ruutuja - valitse kyseinen vaihtoehto sovelluksessa .

    ![Sisällön valitseminen](media/embed-sample-for-customers/embed-sample-for-customers-034.png)

    Voit nyt tarkastella raporttia mallisovelluksessa.

    ![Näytä sovellus](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

## <a name="embed-your-content-within-your-application"></a>Upota sisältö sovellukseen

Vaikka sisältöä voidaan upottaa [Power BI REST -ohjelmointirajapintojen](https://docs.microsoft.com/rest/api/power-bi/) avulla, tässä artikkelissa kuvatut esimerkkikoodit on luotu **.NET SDK**:n avulla.

Upottaaksesi sovellukseen sisältöä asiakkaillesi, tarvitset päätilillesi **käyttöoikeustietueen** **Azure AD:sta**. Sinun täytyy hankkia [Azure AD -käyttöoikeustietue](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) Power BI-sovelluksellesi **app owns data** -mallin avulla ennen kutsujen tekemistä [Power BI REST -ohjelmointirajapintoihin](https://docs.microsoft.com/rest/api/power-bi/).

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

*Malli sisältökohteen hankkimisesta sen mukaan, onko upotettava raportti, raporttinäkymä tai ruutu saatavilla [mallisovelluksen](#embed-your-content-within-a-sample-application) Controllers\HomeController.cs-tiedostossa.*

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

Tässä on malli upotustunnuksen lisäämisestä raporttia varten sovellukseen.

*Malli upotustunnuksen luomisesta raporttia, koontinäyttöä tai ruutua varten on saatavilla [mallisovelluksen](#embed-your-content-within-a-sample-application) Controllers\HomeController.cs-tiedostossa.*

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

*Malli näkymän lisäämisestä raporttia, koontinäyttöä tai ruutua varten on saatavilla [mallisovelluksen](#embed-your-content-within-a-sample-application) Views\Home\EmbedReport.cshtml-, Views\Home\EmbedDashboard.cshtml- tai Views\Home\Embedtile.cshtml-tiedostoissa.*

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

    // Embed configuration used to describe the what and how to embed.
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

Kun olet nyt kehittänyt sovelluksesi, on aika varata sovelluksen työtilalle kapasiteettia. Varattua kapasiteettia tarvitaan kun siirrytään tuotantoon.

### <a name="create-a-dedicated-capacity"></a>Luo varattua kapasiteettia

Luomalla varattua kapasiteettia voit hyötyä siitä, että asiakkaalle varataan tietty resurssi. Voit ostaa varattua kapasiteettia [Microsoft Azure -portaalissa](https://portal.azure.com). Lisätietoa Power BI Embedded ‑kapasiteetin luomisesta saat ohjeaiheesta [Power BI Embedded -kapasiteetin luominen Azure-portaalissa](azure-pbie-create-capacity.md).

Seuraavan taulukon avulla voit määrittää, mikä Power BI Embedded -kapasiteetti sopii parhaiten tarpeisiisi.

| Kapasiteetin solmu | Ytimiä yhteensä<br/>*(Tausta ja edusta)* | Taustan ytimet | Edustan ytimet | DirectQueryn/live-yhteyden rajoitukset | Sivun hahmonnuksia enintään huipputuntina |
| --- | --- | --- | --- | --- | --- |
| A1 |1 näennäisydin |0,5 ydintä, 3 Gt RAM |0,5 ydintä |0,5 sekunnissa |1–300 |
| A2 |2 näennäisydintä |1 ydin, 5 Gt RAM |1 ydin | 10 sekunnissa |301–600 |
| A3 |4 näennäisydintä |2 ydintä, 10 Gt RAM |2 ydintä | 15 sekunnissa |601–1 200 |
| A4 |8 näennäisydintä |4 ydin(tä), 25 Gt RAM |4 ydintä |30 sekunnissa |1 201–2 400 |
| A5 |16 näennäisydintä |8 ydintä, 50 Gt RAM |8 ydintä |60 sekunnissa |2 401–4 800 |
| A6 |32 näennäisydintä |16 ydintä, 100 Gt RAM |16 ydintä |120 sekunnissa |4 801–9 600 |

**_A-varastointiyksiköillä et pysty käyttämään Power BI -sisältöä ilmaisella Power BI -käyttöoikeudella._**

PRO-käyttöoikeuksien upotettavat tunnukset on tarkoitettu kehitystestaukseen, joten Power BI -päätili voi luoda vain rajallisen määrän upotettavia tunnuksia. Tuotantoympäristössä upottamista varten täytyy ostaa varattua kapasiteettia. Varatun kapasiteetin avulla luotavien upotettavien tunnuksien määrää ei ole rajoitettu. Siirry [Käytettävissä olevat ominaisuudet](https://docs.microsoft.com/rest/api/power-bi/availablefeatures/getavailablefeatures) -kohtaan tarkistaaksesi käyttöarvon, joka ilmaisee nykyisen upotetun käytön prosenttilukuna. Käytettävä määrä on päätilikohtainen.

Lisätietoja on ohjeaiheessa [Upotetun analytiikan kapasiteetin suunnittelun tekninen raportti](https://aka.ms/pbiewhitepaper).

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>Määritä sovellustyötila varattuun kapasiteettiin

Kun olet luonut varatun kapasiteetin, voit määrittää sovellustyötilan kyseiselle varatulle kapasiteetille. Määritä työtilan varattu kapasiteetti seuraavien ohjeiden mukaisesti.

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
