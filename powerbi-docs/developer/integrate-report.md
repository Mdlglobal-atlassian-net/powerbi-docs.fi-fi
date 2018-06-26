---
title: Power BI -raportin integrointi sovellukseen organisaatiolle
description: Lue, miten voit integroida tai upottaa raportin verkkosovellukseen Power BI -ohjelmointirajapintojen avulla.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 032e0ed05d56d2d7f1e2b41cfd922999ff43ea94
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813361"
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>Raportin integrointi sovellukseen organisaatiolle
Lue, miten voit integroida tai upottaa raportin verkkosovellukseen REST-ohjelmointirajapinnan kutsujen ja Power BI JavaScript -ohjelmointirajapinnan avulla organisaatiolle.

![Upotetun raportin malli](media/integrate-report/powerbi-embedded-report.png)

Jotta voit käydä läpi nämä vaiheittaiset ohjeet, tarvitset **Power BI** -tilin. Jos sinulla ei ole tiliä, voit [rekisteröityä maksuttomalle Power BI -tilille](../service-self-service-signup-for-power-bi.md) tai luoda oman [Azure Active Directory -vuokraajan ](create-an-azure-active-directory-tenant.md) testausta varten.

> [!NOTE]
> Haluatko upottaa raportin asiakkaillesi sen sijaan upotetun käyttöoikeustietueen avulla? Katso artikkelia [Koontinäytön, ruudun tai raportin integrointi sovellukseen asiakkaille](embed-sample-for-customers.md).
> 
> 

Voit integroida raportin verkkosovellukseen **Power BI** REST -ohjelmointirajapinnan tai Power BI C# SDK:n avulla ja saada raportin Azure Active Directory (AD) -valtuutuksen **käyttöoikeustietueen** avulla. Voit sitten ladata raportin käyttämällä samaa käyttöoikeustietuetta. **Power BI** -ohjelmointirajapinta tarjoaa ohjelmallisen käyttöoikeuden tiettyihin **Power BI** -resursseihin. Katso lisätietoja artikkeleista [Power BI REST -ohjelmointirajapinta](https://docs.microsoft.com/rest/api/power-bi/) ja [Power BI JavaScript -ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Mallin lataaminen
Tässä artikkelissa näytetään koodi, jota käytetään [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)-mallissa GitHubissa. Voit ladata mallin, jonka avulla voit noudattaa näitä vaiheittaisia ohjeita.

Voit käyttää [Perehdyttämiskokemustyökalua](https://aka.ms/embedsetup/UserOwnsData) ladataksesi mallisovelluksen ja päästäksesi aloittamaan nopeasti.

Jos haluat määrittää ympäristön manuaalisesti, jatka lukemista.

## <a name="step-1---register-an-app-in-azure-ad"></a>Vaihe 1 – rekisteröi sovellus Azure AD:ssä
Sinun on rekisteröitävä sovellus Azure AD:ssä REST-ohjelmointirajapinnan kutsujen tekemiseksi. Katso lisätietoja artikkelista [Azure AD -sovelluksen rekisteröinti upotettuun Power BI -sisältöön](register-app.md).

Jos olet ladannut [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)-mallin, voit rekisteröinnin jälkeen saamasi **asiakastunnuksen** ja **asiakkaan salasanan** avulla todentaa mallin Azure AD:hen. Voit konfiguroida mallin muuttamalla **asiakastunnusta** ja **asiakkaan salasanaa** *cloud.config*-tiedostossa.

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Vaihe 2 – hanki käyttöoikeustietue Azure AD:stä
Sinun on hankittava sovelluksessa **käyttöoikeustietue** Azure AD:stä, ennen kuin voit lähettää kutsuja Power BI REST -ohjelmointirajapintaan. Katso lisätietoja artikkelista [Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen saanti Power BI -sovellukselle](get-azuread-access-token.md).

## <a name="step-3---get-a-report"></a>Vaihe 3 – Hanki raportti
Voit hankkia **Power BI** -raportin käyttämällä [Hanki raportit](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) -toimintoa, joka antaa **Power BI** -raporttien luettelon. Saat raporttien luettelosta raporttitunnuksen.

### <a name="get-reports-using-an-access-token"></a>Hanki raportit käyttöoikeustietueen avulla
Voit [vaiheessa 2](#step-2-get-an-access-token-from-azure-ad) saadun **käyttöoikeustietueen** avulla kutsua [Hanki raportit](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) -toiminnon. [Hanki raportit](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) -toiminto palauttaa raporttiluettelon. Voit noutaa yksittäisen raportin raporttiluettelosta. Alla on täydellinen C#-menetelmä raportin hankkimiseksi. 

Jotta voit lähettää REST-ohjelmointirajapinnan kutsun, sinun on sisällytettävä *Valtuutus*-otsikko *Haltija {käyttöoikeustietue}* -muodossa.

#### <a name="get-reports-with-the-rest-api"></a>Raporttien hankinta REST-ohjelmointirajapinnan avulla
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>Raporttien hankinta .NET SDK:n avulla
.NET SDK:n avulla voit noutaa raporttiluettelon sen sijaan, että lähetät kutsun suoraan REST-ohjelmointirajapintaan.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>Vaihe 4 – Lataa raportti JavaScriptin avulla
Voit JavaScriptin avulla ladata raportin verkkosivun jako-elementtiin.

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Jos latasit ja suoritit[integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)-mallin, se näyttää seuraavanlaiselta.

![Upotetun raportin malli](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>Ryhmien käsitteleminen (sovelluksen työtilat)
Jotta voit upottaa raportin ryhmästä (sovelluksen työtila), voit noutaa kaikkien saatavilla olevien raporttien luettelon ryhmän koontinäytöstä seuraavan REST-ohjelmointirajapinnan kutsun avulla. Katso lisätietoja tästä REST-ohjelmointirajapinnan kutsusta artikkelista [Hanki raportit](https://docs.microsoft.com/rest/api/power-bi/reports/getreports). Tarvitset käyttöoikeuden ryhmässä pyynnölle tulosten palauttamiseksi.

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

Yllä oleva ohjelmointirajapinta palauttaa saatavilla olevien raporttien luettelon. Jokaisessa raportissa on EmbedUrl-ominaisuus, joka on jo suunniteltu tukemaan ryhmän upottamista.

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>Seuraavat vaiheet
GitHubissa on saatavilla mallisovellus, jota voit tarkastella. Katso lisätietoja artikkelista [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app).

Katso lisätietoja JavaScript-ohjelmointirajapinnasta artikkelista [Power BI JavaScript -ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

