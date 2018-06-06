---
title: Koontinäytön integrointi sovellukseen organisaatiolle
description: Lue, miten voit integroida tai upottaa koontinäytön verkkosovellukseen Power BI -ohjelmointirajapintojen avulla.
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
ms.openlocfilehash: e85b745798fd33ffbb5061f4c156054d2218bfb1
ms.sourcegitcommit: 2ceea44d3606c15b57142c37649c9d481ec4becc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/15/2018
ms.locfileid: "30973617"
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>Koontinäytön integrointi sovellukseen organisaatiolle
Lue, miten voit integroida tai upottaa koontinäytön verkkosovellukseen REST-ohjelmointirajapinnan kutsujen ja Power BI JavaScript -ohjelmointirajapinnan avulla organisaatiolle.

![Upotettu koontinäyttö](media/integrate-dashboard/powerbi-embed-dashboard.png)

Jotta voit käydä läpi nämä vaiheittaiset ohjeet, tarvitset **Power BI** -tilin. Jos sinulla ei ole tiliä, voit [rekisteröidä Power BI -tilin maksutta](../service-self-service-signup-for-power-bi.md) tai luoda oman [Azure Active Directory -vuokraajan](create-an-azure-active-directory-tenant.md) testausta varten.

> [!NOTE]
> Haluatko ennemmin upottaa koontinäytön asiakkaitasi varten, upotustunnuksen avulla? Katso artikkelia [Koontinäytön, ruudun tai raportin integrointi sovellukseen asiakkaille](embed-sample-for-customers.md).
> 
> 

Voit integroida koontinäytön verkkosovellukseen **Power BI** REST -ohjelmointirajapinnan tai Power BI C# SDK:n avulla ja noutaa koontinäytön käyttämällä Azure Active Directory (AD) -valtuutuksen **käyttöoikeustietuetta**. Voit sitten ladata koontinäytön käyttämällä samaa käyttöoikeustietuetta. **Power BI** -ohjelmointirajapinta tarjoaa ohjelmallisen käyttöoikeuden tiettyihin **Power BI** -resursseihin. Katso lisätietoja artikkelista [Power BI REST -ohjelmointirajapinnan yleiskatsaus](https://msdn.microsoft.com/library/dn877544.aspx) ja [Power BI JavaScript -ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Mallin lataaminen
Tässä artikkelissa näytetään koodi, jota käytetään [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)-mallissa GitHubissa. Voit ladata mallin, jonka avulla voit noudattaa näitä vaiheittaisia ohjeita.

## <a name="step-1---register-an-app-in-azure-ad"></a>Vaihe 1 – Rekisteröi sovellus Azure AD:ssä
Sinun on rekisteröitävä sovellus Azure AD:ssä REST-ohjelmointirajapinnan kutsujen tekemiseksi. Saat lisätietoja artikkelista [Azure AD -sovelluksen rekisteröinti Power BI -sisällön upottamista varten](register-app.md).

Jos latasit [koontinäytön integrointimallin](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), käytä rekisteröinnin jälkeen saamaasi **asiakastunnusta** ja **asiakkaan salaista koodia**, jotta Azure AD voi todentaa mallin. Jos haluat konfiguroida mallia, vaihda **asiakastunnus** ja **asiakkaan salainen koodi** *cloud.config*-tiedostossa.

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Vaihe 2 – Hanki käyttöoikeustietue Azure AD:stä
Sinun on hankittava sovelluksessa **käyttöoikeustietue** Azure AD:stä, ennen kuin voit lähettää kutsuja Power BI REST -ohjelmointirajapintaan. Saat lisätietoja artikkelista [Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen hankkiminen Power BI -sovellukselle](get-azuread-access-token.md).

## <a name="step-3---get-a-dashboard"></a>Vaihe 3 – Hanki koontinäyttö
Voit hankkia **Power BI** -koontinäytön käyttämällä [Hanki koontinäytöt](https://msdn.microsoft.com/library/mt465739.aspx) -toimintoa, joka antaa luettelon **Power BI** -koontinäytöistä. Koontinäyttöjen luettelosta saat koontinäytön tunnuksen.

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>Koontinäytön hankkiminen käyttöoikeustietueen avulla
Voit kutsua [Hanki koontinäytöt](https://msdn.microsoft.com/library/mt465739.aspx) ‑toimintoa [vaiheessa 2](#step-2-get-an-access-token-from-azure-ad) hankkimasi **käyttöoikeustietueen** avulla. [Hanki koontinäytöt](https://msdn.microsoft.com/library/mt465739.aspx) ‑toiminto palauttaa luettelon koontinäytöistä. Voit noutaa yksittäisen koontinäytön koontinäyttöjen luettelosta. Alla on koontinäytön hankkimisen koko C#-metodi. 

REST-ohjelmointirajapinnan kutsu edellyttää, että sisällytät siihen määritteen *Authorization*, joka on muotoa *Bearer {käyttöoikeustietue}*.

#### <a name="get-dashboards-with-the-rest-api"></a>Koontinäytön hankkiminen REST-ohjelmointirajapinnan avulla
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>Koontinäytön hankkiminen .NET SDK:n avulla
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
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>Vaihe 4 – Lataa koontinäyttö käyttämällä JavaScriptiä
JavaScriptin avulla voit ladata koontinäytön verkkosivusi jakoelementtiin.

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Jos latasit ja suoritit [koontinäytön integrointimallin](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), se näyttää seuraavanlaiselta.

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>Ruutujen napsautustapahtumat
Havaitsit ehkä edellä näytetyssä mallissa voivasi käsitellä tapahtumia, jotka tulevat esiin, kun ruutua napsautetaan. Lisätietoja tapahtumista saat ohjeaiheesta [Tapahtumien käsittely JavaScript-ohjelmointirajapinnan kautta](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

Jos latasit ja suoritit [koontinäytön integrointimallin](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app), ruudun napsauttaminen tulostaa tekstin koontinäytön alle. Teksti näyttää samalta kuin kuvassa jäljempänä. Sen avulla voit merkitä ruudun napsauttamisen lokiin ja johdattaa sitten käyttäjän oikeaan paikkaan.

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>Ryhmien käsitteleminen (sovelluksen työtilat)
Jotta voit upottaa koontinäytön ryhmästä (sovelluksen työtila), sinun kannattaa noutaa ryhmän sisältämien kaikkien saatavilla olevien koontinäyttöjen luettelo seuraavan REST-ohjelmointirajapinnan kutsun avulla. Katso lisätietoja tästä REST-ohjelmointirajapinnan kutsusta ohjeaiheesta [Koontinäyttöjen hankkiminen](https://msdn.microsoft.com/library/mt465739.aspx). Tarvitset ryhmässä käyttöoikeuden pyynnölle, jotta tulokset voidaan palauttaa.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

Edellä oleva ohjelmointirajapinta palauttaa saatavilla olevien koontinäyttöjen luettelon. Jokaisessa koontinäytössä on EmbedUrl-ominaisuus, joka on jo suunniteltu tukemaan ryhmän upottamista.

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>Rajoitukset
* Upotettuja koontinäyttöjä käyttävillä loppukäyttäjillä on oltava Power BI ‑tili sekä käyttöoikeus koontinäyttöön. Loppukäyttäjän on oltava koontinäytön omistaja tai koontinäyttö on pitänyt jakaa hänelle.
* Tällä hetkellä upotetuissa koontinäytöissä ei ole tukea Q&A-toiminnolle.
* Tilapäinen rajoitus: kun koontinäyttö jaetaan käyttöoikeusryhmälle, käyttäjän on ensin käytettävä koontinäyttöä PowerBI.comissa ennen kuin hän voi nähdä sen upotettuna.

## <a name="next-steps"></a>Seuraavat vaiheet
GitHubissa on saatavilla mallisovellus, jota voit hyödyntää. Edellä olevat esimerkit perustuvat tähän malliin. Katso lisätietoja artikkelista [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app).

Katso lisätietoja JavaScript-ohjelmointirajapinnasta artikkelista [Power BI JavaScript -ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

