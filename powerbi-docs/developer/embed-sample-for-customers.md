---
title: Power BI -sisällön upottaminen sovellukseen asiakkaille
description: Lue, miten voit integroida tai upottaa koontinäytön, ruudun tai raportin verkkosovellukseen Power BI -ohjelmointirajapintojen avulla asiakkaille.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/11/2018
ms.author: maghan
ms.openlocfilehash: c6b9edb929934a80886874fe421f11cc7462dbd8
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application"></a>Power BI -koontinäytön, -ruudun tai -raportin upottaminen sovellukseen
Lue, miten voit integroida tai upottaa koontinäytön, ruudun tai raportin verkkosovellukseen Power BI .NET SDK:n ja Power BI JavaScript -ohjelmointirajapinnan avulla upotuksen aikana asiakkaille. Tämä on yleensä ISV-skenaario.

![Upotettu koontinäyttö](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

Jotta voit käydä läpi nämä vaiheittaiset ohjeet, tarvitset **Power BI Pro** -tilin. Jos sinulla ei ole tiliä, voit [rekisteröityä maksuttomalle Power BI -tilille](../service-self-service-signup-for-power-bi.md) ja rekisteröityä sitten [Power BI Pro -kokeiluversioon](../service-self-service-signup-for-power-bi.md#in-service-power-bi-pro-60-day-trial) tai luoda oman [Azure Active Directory -vuokraajan ](create-an-azure-active-directory-tenant.md) testausta varten.

> [!NOTE]
> Haluatko sen sijaan upottaa koontinäytön organisaatiolle? Katso artikkelia [Koontinäytön integrointi sovellukseen organisaatiolle](integrate-dashboard.md).
> 
> 

Voit integroida koontinäytön verkkosovellukseen **Power BI** -ohjelmointirajapinnan ja saada koontinäytön Azure Active Directory (AD) -valtuutuksen **käyttöoikeustietueen** avulla. Lataa sitten koontinäyttö upotetun käyttöoikeustietueen avulla. **Power BI** -ohjelmointirajapinta tarjoaa ohjelmallisen käyttöoikeuden tiettyihin **Power BI** -resursseihin. Katso lisätietoja artikkelista [Power BI REST -ohjelmointirajapinnan yleiskatsaus](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI .NET SDK](https://github.com/Microsoft/PowerBI-CSharp) ja [Power BI JavaScript -ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Mallin lataaminen
Tässä artikkelissa näytetään koodi, jota käytetään [organisaation mallin upotukseen](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) GitHubissa. Näiden vaiheittaisten ohjeiden noudattamiseksi voit ladata mallin.

## <a name="step-1---register-an-app-in-azure-ad"></a>Vaihe 1 – Rekisteröi sovellus Azure AD:ssä
Sinun on rekisteröitävä sovellus Azure AD:ssä REST-ohjelmointirajapinnan kutsujen tekemiseksi. Katso lisätietoja artikkelista [Azure AD -sovelluksen rekisteröinti upotettuun Power BI -sisältöön](register-app.md).

Jos olet ladannut [Upottaminen organisaatiolle -mallin](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data), voit rekisteröinnin jälkeen saamasi **asiakastunnuksen** avulla todentaa mallin Azure AD:hen. Voit konfiguroida mallin muuttamalla **asiakastunnusta** *web.config*-tiedostossa.

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Vaihe 2 – Hanki käyttöoikeustietue Azure AD:stä
Sinun on ensin saatava sovelluksessa **käyttöoikeustietue** Azure AD:stä ennen kuin voit lähettää kutsuja Power BI REST -ohjelmointirajapintaan. Katso lisätietoja artikkelista [Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen saanti Power BI -sovellukselle](get-azuread-access-token.md).

Näet esimerkkejä tästä jokaisessa sisältökohdetehtävässä kohdasta **Controllers\HomeController.cs**.

## <a name="step-3---get-a-content-item"></a>Vaihe 3 – Hae sisältökohde
Jos haluat upottaa Power BI -sisältöä, sinun on varmistettava parin asian avulla, että upotus suoritetaan oikein. Vaikka nämä kaikki vaiheet voidaan tehdä suoraan REST-ohjelmointirajapinnassa, mallisovellus ja tässä olevat esimerkit tehdään .NET SDK:ssä.

### <a name="create-the-power-bi-client-with-your-access-token"></a>Power BI -asiakasohjelman luonti käyttöoikeustietueen avulla
Voit käyttöoikeustietueen avulla luoda Power BI -asiakasohjelmaobjektin, jotta voit käsitellä Power BI -ohjelmointirajapintoja. Tämä tehdään sijoittamalla käyttöoikeustietue *Microsoft.Rest.TokenCredentials*-objektiin.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Upotettavan sisältökohteen hankinta
Voit Power BI -asiakasohjelmaobjektin avulla noutaa viitteen upotettavalle kohteelle. Voit upottaa koontinäyttöjä, ruutuja tai raportteja. Tässä on esimerkki siitä, miten voit noutaa ensimmäisen koontinäytön, ruudun tai raportin tietystä työtilasta.

Malli tästä on saatavilla [App Owns Data -mallin](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) kohteesta **Controllers\HomeController.cs**.

**Koontinäytöt**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**Ruutu**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**Raportti**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Upotetun tunnuksen luominen
Sinun on luotava upotettu tunnus, jota voidaan käyttää JavaScript-ohjelmointirajapinnasta. Upotettu tunnus liittyy erityisesti upotettavaan kohteeseen. Tämä tarkoittaa sitä, että kun upotat tietyn Power BI -sisällön, sinun on luotava sille uusi upotettu tunnus. Katso lisätietoja tästä ja käytettävästä **käyttöoikeustasosta** artikkelista [GenerateToken-ohjelmointirajapinta](https://msdn.microsoft.com/library/mt784614.aspx).

> [!IMPORTANT]
> Koska upotetut tunnukset on tarkoitettu vain kehitystestaukseen, Power BI -päätilin luomien upotettujen tunnusten määrää on rajoitettu. [Sinun on ostettava kapasiteettia](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) upotusskenaarioiden tuottamiseksi. Kun kapasiteettia on ostettu, voit luoda upotettuja tunnuksia rajattomasti.

Malli tästä on saatavilla artikkelin [Organisaation mallin upotus](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) kohdasta **Controllers\HomeController.cs**.

Tämä edellyttää luokan luomista kohteille **EmbedConfig** ja **TileEmbedConfig**. Malli näistä on saatavilla kohteissa **Models\EmbedConfig.cs** ja **Models\TileEmbedConfig.cs**.

**Koontinäyttö**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**Ruutu**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**Raportti**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```



## <a name="step-4---load-an-item-using-javascript"></a>Vaihe 4 – Lataa kohde JavaScriptin avulla
Voit JavaScriptin avulla ladata koontinäytön verkkosivun jako-elementtiin. Malli käyttää EmbedConfig/TileEmbedConfig-mallia yhdessä koontinäytön, ruudun tai raportin näkymien kanssa. Jos haluat täydellisen mallin JavaScript-ohjelmointirajapinnan käytöstä, voit käyttää [Microsoft Power BI:n upotettua mallia](https://microsoft.github.io/PowerBI-JavaScript/demo).

Sovellusmalli tästä on saatavilla artikkelista [Organisaation mallin upotus](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**Views\Home\EmbedDashboard.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```
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

## <a name="next-steps"></a>Seuraavat vaiheet
GitHubissa on saatavilla mallisovellus, jota voit tarkastella. Edellä olevat esimerkit perustuvat tähän malliin. Katso lisätietoja artikkelista [Organisaation mallin upotus](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

Katso lisätietoja JavaScript-ohjelmointirajapinnasta artikkelista [Power BI JavaScript -ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

