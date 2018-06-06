---
title: Power BI -ruudun integrointi sovellukseen organisaatiolle
description: Ruudun integrointi sovellukseen vaihe vaiheelta, mallikoodi
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
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: c4c1b9223554491968a541c9d6b698a9655eded5
ms.sourcegitcommit: 2ceea44d3606c15b57142c37649c9d481ec4becc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2018
ms.locfileid: "30973622"
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>Ruudun integrointi sovellukseen (käyttäjä omistaa tiedot)
Lue, miten voit integroida tai upottaa ruudun verkkosovellukseen REST-ohjelmointirajapinnan kutsujen ja Power BI JavaScript -ohjelmointirajapinnan avulla organisaatiolle.

![Upotettu ruutu verkkosovelluksessa](media/integrate-tile/powerbi-embedded-tile.png)

Jotta voit käydä läpi nämä vaiheittaiset ohjeet, tarvitset **Power BI** -tilin. Jos sinulla ei ole tiliä, voit [rekisteröityä maksuttomalle Power BI -tilille](../service-self-service-signup-for-power-bi.md) tai luoda oman [Azure Active Directory -vuokraajan ](create-an-azure-active-directory-tenant.md) testausta varten.

> [!NOTE]
> Haluatko upottaa ruudun asiakkaillesi sen sijaan upotetun käyttöoikeustietueen avulla? Katso artikkelia [Koontinäytön, ruudun tai raportin integrointi sovellukseen asiakkaille](embed-sample-for-customers.md).
> 
> 

Voit integroida ruudun verkkosovellukseen **Power BI** REST -ohjelmointirajapinnan tai Power BI C# SDK:n avulla ja saada ruudun Azure Active Directory (AD) -valtuutuksen **käyttöoikeustietueen** avulla. Voit sitten ladata ruudun käyttämällä samaa käyttöoikeustietuetta. **Power BI** -ohjelmointirajapinta tarjoaa ohjelmallisen käyttöoikeuden tiettyihin **Power BI** -resursseihin. Katso lisätietoja artikkelista [Power BI REST -ohjelmointirajapinnan yleiskatsaus](https://msdn.microsoft.com/library/dn877544.aspx) ja [Power BI JavaScript -ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Mallin lataaminen
Tässä artikkelissa näytetään koodi, jota käytetään [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)-mallissa GitHubissa. Voit ladata mallin, jonka avulla voit noudattaa näitä vaiheittaisia ohjeita.

## <a name="step-1---register-an-app-in-azure-ad"></a>Vaihe 1 – rekisteröi sovellus Azure AD:ssä
Sinun on rekisteröitävä sovellus Azure AD:ssä REST-ohjelmointirajapinnan kutsujen tekemiseksi. Saat lisätietoja artikkelista [Azure AD -sovelluksen rekisteröinti Power BI -sisällön upottamista varten](register-app.md).

Jos olet ladannut [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)-mallin, voit rekisteröinnin jälkeen saamasi **asiakastunnuksen** ja **asiakkaan salasanan** avulla todentaa mallin Azure AD:hen. Voit konfiguroida mallin muuttamalla **asiakastunnusta** ja **asiakkaan salasanaa** *cloud.config*-tiedostossa.

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Vaihe 2 – hanki käyttöoikeustietue Azure AD:stä
Sinun on hankittava sovelluksessa **käyttöoikeustietue** Azure AD:stä, ennen kuin voit lähettää kutsuja Power BI REST -ohjelmointirajapintaan. Saat lisätietoja artikkelista [Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen hankkiminen Power BI -sovellukselle](get-azuread-access-token.md).

## <a name="step-3---get-a-tile"></a>Vaihe 3 – hanki ruutu
Voit hankkia **Power BI** -ruudun käyttämällä [Hanki ruudut](https://msdn.microsoft.com/library/mt465741.aspx) -toimintoa, joka antaa luettelon **Power BI** -ruuduista kyseisellä koontinäytöllä. Ruutujen luettelosta saat ruudun tunnuksen hankkiminen ja upotetun URL-osoitteen.

Koontinäyttötunnus on noudettava ensin, ennen kuin voit saada ruutua. Lisätietoja siitä, miten voit noutaa koontinäytön, on annettu kohdassa [Koontinäytön integrointi sovellukseen (käyttäjä omistaa tiedot)](integrate-dashboard.md).

### <a name="get-tiles-using-an-access-token"></a>Ruutujen hankkiminen käyttöoikeustietueen avulla
Voit [vaiheessa 2](#step-2-get-an-access-token-from-azure-ad) saadun **käyttöoikeustietueen** avulla kutsua [Hanki ruudut](https://msdn.microsoft.com/library/mt465741.aspx) -toiminnon. [Hanki ruudut](https://msdn.microsoft.com/library/mt465741.aspx) -toiminto palauttaa ruutuluettelon. Voit noutaa yksittäisen ruudun ruutuluettelosta. Alla on täydellinen C#-menetelmä ruudun hankkimiseksi. 

Jotta voit lähettää REST-ohjelmointirajapinnan kutsun, sinun on sisällytettävä *Valtuutus*-otsikko *Haltija {käyttöoikeustietue}* -muodossa.

#### <a name="get-tiles-with-the-rest-api"></a>Ruutujen hankinta REST-ohjelmointirajapinnan avulla
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>Ruutujen hankinta .NET SDK:n avulla
.NET SDK:n avulla voit noutaa koontinäyttöluettelon lähettämättä kutsua suoraan REST-ohjelmointirajapintaan.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>Vaihe 4 – Lataa ruutu JavaScriptin avulla
Voit JavaScriptin avulla ladata ruudun verkkosivun jako-elementtiin.

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Jos latasit ja suoritit[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)-mallin, se näyttää seuraavanlaiselta.

![Upotettu ruutu verkkosovelluksessa](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>Ryhmien käsitteleminen (sovelluksen työtilat)
Jotta voit upottaa ruudun ryhmästä (sovelluksen työtila), voit noutaa kaikkien saatavilla olevien ruutujen luettelon ryhmän koontinäytöstä seuraavan REST-ohjelmointirajapinnan kutsun avulla. Katso lisätietoja tästä REST-ohjelmointirajapinnan kutsusta artikkelista [Hanki ruudut](https://msdn.microsoft.com/library/mt465741.aspx). Tarvitset käyttöoikeuden ryhmässä pyynnölle tulosten palauttamiseksi.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

Yllä oleva ohjelmointirajapinta palauttaa saatavilla olevien ruutujen luettelon. Jokaisessa ruudussa on EmbedUrl-ominaisuus, joka on jo suunniteltu tukemaan ryhmän upottamista.

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>Seuraavat vaiheet
[Ruudun upotus](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed) Power BI-JavaScript Wikiin

[Power BI JavaScript-ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) -malli GitHubissa.

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

