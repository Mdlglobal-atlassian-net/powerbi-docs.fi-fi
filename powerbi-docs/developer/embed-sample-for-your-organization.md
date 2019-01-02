---
title: Upotettu analysointi Power BI:n sisällön upottamiseksi sovellukseen organisaatiollesi
description: Lue, miten voit integroida tai upottaa raportteja, koontinäyttöjä tai ruutuja organisaatiotasi varten käyttämällä upotetussa analysoinnissa Power BI -ohjelmointirajapintoja. Lue, miten voit integroida Power BI:n sovellukseesi käyttämällä upotetun analysoinnin ohjelmistoa, upotetun analysoinnin työkaluja tai upotetun liiketoimintatiedon työkaluja.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: tutorial
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: ea4292fd95fa72a553d9f91b39ff0bc5de71a584
ms.sourcegitcommit: 9913c213d40b45ba83c6c3b3a7ef0b757800e3ad
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/12/2018
ms.locfileid: "53301846"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-organization"></a>Opetusohjelma: Power BI -raportin, koontinäytön tai ruudun upottaminen sovellukseen organisaatiollesi

Power BI:ssä voit upottaa sovellukseen raportteja, koontinäyttöjä tai ruutuja käyttämällä **user owns data** -malleja. **User owns data** -mallien avulla sovelluksesi voi laajentaa Power BI -palvelun käyttämään upotettua analysointia. Tässä opetusohjelmassa näytetään, miten voit integroida raportin sovellukseen. Voit käyttää Power BI .NET SDK:ta sekä Power BI JavaScript -ohjelmointirajapintaa Power BI:n upottamiseksi sovellukseen organisaatiollesi.

![Power BI -raportin upottaminen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

Tässä opetusohjelmassa opit tekemään seuraavat asiat:
> [!div class="checklist"]
> * Rekisteröimään sovelluksen Azuressa.
> * Upottamaan Power BI -raportin sovellukseen.

## <a name="prerequisites"></a>Edellytykset

Tarvitset Power BI Pro -tilin ja Microsoft Azure -tilauksen aloittaaksesi:

* Jos et ole rekisteröitynyt Power BI Prohon, [rekisteröi ilmainen kokeiluversio](https://powerbi.microsoft.com/en-us/pricing/) ennen aloittamista.
* Jos sinulla ei ole Azure-tilausta, luo [ilmainen tili](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) ennen aloittamista.
* Määritä oma [Azure Active Directory (Azure AD) -vuokraaja](create-an-azure-active-directory-tenant.md).
* Asenna [Visual Studio](https://www.visualstudio.com/) 2013 tai uudempi versio.

## <a name="set-up-your-embedded-analytics-development-environment"></a>Upotettujen analyysitoimintojen kehitysympäristön määrittäminen

Ennen kuin ryhdyt upottamaan raportteja, koontinäyttöjä tai ruutuja sovellukseesi, varmista, että ympäristösi on määritetty niin, että upottaminen on siinä sallittu. Tee jokin seuraavista toimista osana asennusta:

* Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup/UserOwnsData) päästäksesi nopeasti alkuun ja ladataksesi mallisovelluksen, jossa käydään läpi sekä käyttöympäristön luominen että raportin upottaminen.

* Jos haluat määrittää ympäristön manuaalisesti, suorita seuraavissa osioissa olevat vaiheet.

### <a name="register-an-application-in-azure-active-directory"></a>Sovelluksen rekisteröiminen Azure Active Directoryyn

Rekisteröi sovellus Azure Active Directoryyn, jotta sovellus saa käyttöoikeuden Power BI REST -ohjelmointirajapintoihin. Tämän jälkeen voit määrittää sovelluksen käyttäjätiedot ja käyttöoikeudet Power BI REST -resursseihin.

1. Hyväksy [Microsoft Power BI -ohjelmointirajapinnan ehdot](https://powerbi.microsoft.com/api-terms).

2. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

    ![Azuren koontinäyttö](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

3. Valitse vasemmassa siirtymisruudussa **Kaikki palvelut** ja sitten **Sovelluksen rekisteröinnit**. Valitse sitten **Uuden sovelluksen rekisteröinti**.

    ![Sovelluksen rekisteröinnin etsintä](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)</br>

    ![Uuden sovelluksen rekisteröinti](media/embed-sample-for-your-organization/embed-sample-for-your-organization-004.png)

4. Noudata kehotteita ja luo uusi sovellus. **User owns data** -mallien kanssa käytä **verkkosovellus/ohjelmointirajapinta**-**sovellustyyppiä**. Sinun täytyy antaa myös **URL-kirjautumisosoite**, jota Azure AD käyttää palauttaessaan tunnusvastauksia. Anna sovellukseen liittyvä arvo. Esimerkiksi `http://localhost:13526/`.

    ![Luo sovellus](media/embed-sample-for-your-organization/embed-sample-for-your-organization-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Määritä sovellukselle käyttöoikeudet Azure Active Directorystä

Sinun on otettava käyttöön sovellukselle käyttöoikeuksia sovelluksen rekisteröintisivulla annettujen käyttöoikeuksien lisäksi. Kirjaudu sisään yleisen järjestelmänvalvojan tilillä ottaaksesi oikeudet käyttöön.

### <a name="use-the-azure-active-directory-portal"></a>Azure Active Directory -portaalin käyttäminen

1. Selaa kohtaan [Sovelluksen rekisteröinnit](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) Azure-portaalissa ja valitse sovellus, jota käytät upottamiseen.

    ![Sovelluksen valitseminen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

2. Valitse **Asetukset**. Valitse sitten **Ohjelmointirajapinnan käyttöoikeudet** -kohdassa **Vaaditut käyttöoikeudet**.

    ![Vaaditut käyttöoikeudet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-008.png)

3. Valitse **Windows Azure Active Directory**. Varmista sitten, että **Käytä hakemistoa kirjautuneena käyttäjänä** on valittuna. Valitse **Tallenna**.

    ![Windows Azure AD -käyttöoikeudet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-011.png)

4. Valitse **Lisää**.

    ![Lisää käyttöoikeuksia](media/embed-sample-for-your-organization/embed-sample-for-your-organization-012.png)

5. Valitse **Valitse ohjelmointirajapinta**.

    ![Lisää API-käyttöoikeuksia](media/embed-sample-for-your-organization/embed-sample-for-your-organization-013.png)

6. Valitse **Power BI -palvelu**. Valitse sitten **Valitse**.

    ![Valitse Power BI -palvelu.](media/embed-sample-for-your-organization/embed-sample-for-your-organization-014.png)

7. Valitse kaikki käyttöoikeudet kohdasta **Delegoidut käyttöoikeudet**. Valitse ne yksi kerrallaan valintojen tallentamiseksi. Kun olet valmis, valitse **Tallenna**.

    ![Valitse delegoidut käyttöoikeudet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-015.png)

## <a name="set-up-your-power-bi-environment"></a>Power BI -ympäristön määrittäminen

### <a name="create-an-app-workspace"></a>Sovelluksen työtilan luominen

Jos upotat asiakkaille raportteja, raporttinäkymiä tai ruutuja, sinun tulee sijoittaa sisältösi sovelluksen työtilaan:

1. Aloita luomalla työtila. Valitse **Työtilat** > **Luo sovelluksen työtila**. Tähän työtilaan sijoitetaan sisältö, johon sovelluksesi on päästävä.

    ![Luo työtila](media/embed-sample-for-your-organization/embed-sample-for-your-organization-020.png)

2. Anna työtilalle nimi. Jos vastaava **työtilan tunnus** ei ole käytettävissä, muokkaa nimeä niin, että saat yksilöllisen tunnuksen. Nimen on oltava myös sovelluksen nimi.

    ![Nimeä työtila](media/embed-sample-for-your-organization/embed-sample-for-your-organization-021.png)

3. Sinun täytyy määrittää joitakin asetuksia. Jos valitset vaihtoehdon **Julkinen**, kuka tahansa organisaatiossasi voi nähdä, mitä työtilassa on. **Yksityinen** tarkoittaa, että vain työtilan jäsenet voivat nähdä sen sisällön.

    ![Valitse Yksityinen tai Julkinen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-022.png)

    Julkinen- tai Yksityinen-asetusta ei voi enää muuttaa, kun olet kerran luonut ryhmän.

4. Voit myös valita, onko jäsenillä muokkaus- vai vain tarkastelu ‑käyttöoikeudet.

    ![Valitse jäsenen käyttöoikeudet](media/embed-sample-for-your-organization/embed-sample-for-your-organization-023.png)

5. Lisää niiden ihmisten sähköpostiosoitteet, joille haluat antaa työtilan käyttöoikeudet, ja valitse **Lisää**. Et voi lisätä ryhmien aliaksia, vain yksittäisiä ihmisiä.

6. Päätä, onko kukin henkilö jäsen vai järjestelmänvalvoja. Järjestelmänvalvojat voivat muokata työtilaa itse ja muun muassa lisätä muita jäseniä. Jäsenet voivat muokata sisältöä työtilassa, ellei heillä ole käyttöoikeuksia pelkästään tarkasteluun. Sekä järjestelmänvalvojat että jäsenet voivat julkaista sovelluksen.

    Voit nyt tarkastella uutta työtilaa. Power BI luo työtilan ja avaa sen. Työtila ilmestyy luetteloon työtiloista, joiden jäsen olet. Järjestelmänvalvojana voit valita kolme pistettä (...) ja palata takaisin tekemään työtilaan muutoksia, lisäämään uusia jäseniä ja muuttamaan jäsenten käyttöoikeuksia.

    ![Luo sovellustyötila](media/embed-sample-for-your-organization/embed-sample-for-your-organization-025.png)

### <a name="create-and-publish-your-reports"></a>Luo ja julkaise raportteja

Voit luoda raportteja ja tietojoukkoja käyttämällä Power BI Desktopia. Voit sitten julkaista raportit sovellustyötilassa. Raportit julkaiseva loppukäyttäjä tarvitsee Power BI Pro ‑käyttöoikeudet sovellustyötilassa julkaisemiseen.

1. Lataa malli [blogiesittely](https://github.com/Microsoft/powerbi-desktop-samples) GitHubista.

    ![Lataa esittely](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026-1.png)

2. Avaa .pbix-raporttimalli Power BI Desktopissa.

   ![Power BI Desktop -raportin malli](media/embed-sample-for-your-organization/embed-sample-for-your-organization-027.png)

3. Julkaise sovelluksen työtilassa.

   ![Julkaise Power BI Desktop -raportti](media/embed-sample-for-your-organization/embed-sample-for-your-organization-028.png)

    Voit nyt tarkastella raporttia verkossa Power BI -palvelussa.

   ![Tarkastele Power BI Desktop -raporttia](media/embed-sample-for-your-organization/embed-sample-for-your-organization-029.png)

## <a name="embed-your-content-by-using-the-sample-application"></a>Upota sisältöä mallisovelluksen avulla

Seuraa näitä ohjeita aloittaaksesi sisällön upottamisen mallisovelluksen avulla:

1. Lataa [User Owns Data -malli](https://github.com/Microsoft/PowerBI-Developer-Samples) GitHubista aloittaaksesi. On olemassa kolme eri mallisovellusta, yksi [raportteja](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), yksi [koontinäyttöjä](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) ja yksi[ruutuja](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) varten. Tämä artikkeli viittaa **raportti**-sovellukseen.

    ![User Owns Data -sovellusmalli](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026.png)

2. Avaa mallisovelluksessa **Cloud.config**-tiedosto. Jotta sovellus voitaisiin suorittaa, sinun on täytettävä pari kenttää: **ApplicationID** ja **ApplicationSecret**.

    ![Cloud.config-tiedosto](media/embed-sample-for-your-organization/embed-sample-for-your-organization-030.png)

    Täytä **ApplicationID**-tiedot **Sovellustunnuksilla** Azuresta. **ApplicationID**:n avulla sovellus tunnistautuu käyttäjille, joilta pyydät käyttöoikeuksia.

    Saat **ApplicationID**:n seuraavasti:

    1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

       ![Azure-portaalin koontinäyttö](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    2. Valitse vasemmassa siirtymisruudussa **Kaikki palvelut** ja sitten **Sovelluksen rekisteröinnit**.

       ![Sovelluksen rekisteröinnin etsintä](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    3. Valitse sovellus, joka käyttää **ApplicationID**:tä.

       ![Sovelluksen valitseminen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    4. Sinun pitäisi nähdä **Sovellustunnus**, joka on merkitty GUID-tunnuksena. Käytä tätä **Sovellustunnusta** sovelluksen **ApplicationID**:nä.

        ![ApplicationID](media/embed-sample-for-your-organization/embed-sample-for-your-organization-007.png)

    Täytä **ApplicationSecret** -tiedot **Avaimet**-osiosta **Sovelluksen rekisteröinnit** -kohdasta **Azuressa**.

    Saat **ApplicationSecretin** seuraavasti:

    1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

       ![Azure-portaali](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

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

    7. Anna **groupId**-kohtaan Power BI:n sovelluksen työtila GUID.

       ![Anna groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    8. Anna **reportId**-kohtaan Power BI:n raportti GUID.

       ![Anna reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

3. Suorita sovellus:

    Valitse **Suorita** **Visual Studiossa**.

    ![Suorita sovellus](media/embed-sample-for-your-organization/embed-sample-for-your-organization-033.png)

    Valitse **Hae raportti**.

    ![Valitse sisältö](media/embed-sample-for-your-organization/embed-sample-for-your-organization-034.png)

    Voit nyt tarkastella raporttia mallisovelluksessa.

    ![Tarkastele raporttia sovelluksessa](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

## <a name="embed-your-content-within-your-application"></a>Upota sisältö sovellukseen

Vaikka sisältöä voidaan upottaa [Power BI REST -ohjelmointirajapintojen](https://docs.microsoft.com/rest/api/power-bi/) avulla, tässä artikkelissa kuvatut esimerkkikoodit on luotu .NET SDK:n avulla.

Voit integroida raportin verkkosovellukseen käyttämällä Power BI REST -ohjelmointirajapintaa tai Power BI C# SDK:ta. Voit käyttää myös Azure Active Directory -käyttöoikeustietuetta raportin saamiseen. Voit sitten ladata raportin käyttämällä samaa käyttöoikeustietuetta. Power BI -ohjelmointirajapinta tarjoaa ohjelmallisen käyttöoikeuden tiettyihin Power BI -resursseihin. Katso lisätietoja artikkeleista [Power BI REST -ohjelmointirajapinta](https://docs.microsoft.com/rest/api/power-bi/) ja [Power BI JavaScript -ohjelmointirajapinta](https://github.com/Microsoft/PowerBI-JavaScript).

### <a name="get-an-access-token-from-azure-ad"></a>Hanki käyttöoikeustietue Azure AD:stä

Sinun on hankittava sovelluksessa käyttöoikeustietue Azure AD:stä, ennen kuin voit lähettää kutsuja Power BI REST -ohjelmointirajapintaan. Saat lisätietoja artikkelista [Käyttäjien todentaminen ja Azure AD -käyttöoikeustietueen hankkiminen Power BI -sovellukselle](get-azuread-access-token.md).

### <a name="get-a-report"></a>Hanki raportti

Voit hankkia Power BI -raportin käyttämällä [Hanki raportit](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) -toimintoa, joka antaa Power BI -raporttien luettelon. Saat raporttien luettelosta raporttitunnuksen.

### <a name="get-reports-by-using-an-access-token"></a>Hanki raportit käyttöoikeustietueen avulla

[Hanki raportit](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) -toiminto palauttaa raporttiluettelon. Voit noutaa yksittäisen raportin raporttiluettelosta.

Jotta voit lähettää REST-ohjelmointirajapinnan kutsun, sinun on sisällytettävä *Valtuutus*-otsikko *Haltija {käyttöoikeustietue}* -muodossa.

#### <a name="get-reports-with-the-rest-api"></a>Raporttien hankinta REST-ohjelmointirajapinnan avulla

Seuraava koodiesimerkki näyttää, miten voit noutaa raportteja **REST-ohjelmointirajapinnan** avulla:

> [!NOTE]  
> Esimerkki siitä, miten saat haluamasi sisältöyksikön, on nähtävissä **Default.aspx.cs** -tiedostossa [mallisovelluksessa](#embed-your-content-using-the-sample-application). Esimerkkejä ovat raportti, koontinäyttö tai ruutu.

```csharp
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

#### <a name="get-reports-by-using-the-net-sdk"></a>Raporttien hankinta .NET SDK:n avulla

.NET SDK:n avulla voit noutaa raporttiluettelon sen sijaan, että lähetät kutsun suoraan REST-ohjelmointirajapintaan. Seuraava koodiesimerkki näyttää, miten voit luetteloida raportteja:

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It is used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

### <a name="load-a-report-by-using-javascript"></a>Lataa raportti JavaScriptin avulla

Voit JavaScriptin avulla ladata raportin verkkosivun jako-elementtiin. Seuraava koodiesimerkki näyttää, miten voit noutaa raportin tietystä työtilasta:

> [!NOTE]  
> Esimerkki siitä, miten voit ladata upotettavan sisältöyksikön, on nähtävissä **Default.aspx.cs** -tiedostossa [mallisovelluksessa](#embed-your-content-using-the-sample-application). Esimerkkejä ovat raportti, koontinäyttö tai ruutu.

```javascript
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

#### <a name="sitemaster"></a>Site.master

```javascript
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
    }
  );
}
```

## <a name="using-a-power-bi-premium-dedicated-capacity"></a>Power BI Premiumille varatun kapasiteetin käyttö

Kun olet nyt kehittänyt sovelluksesi, on aika varata sovelluksen työtilalle kapasiteettia.

### <a name="create-a-dedicated-capacity"></a>Luo varattua kapasiteettia

Luomalla varattua kapasiteettia voit hyödyntää sitä, että sovellustyötilan sisällölle varataan tietty resurssi. Voit luoda varattua kapasiteettia käyttämällä [Power BI Premiumia](../service-premium.md).

Seuraavassa taulukossa esitetään Power BI Premiumin SKU:t, jotka ovat käytettävissä [Microsoft Office 365:ssä](../service-admin-premium-purchase.md):

| Kapasiteetin solmu | Näennäisytimiä yhteensä<br/>(tausta ja edusta) | Taustan näennäisytimet | Edustan näennäisytimet | DirectQueryn/live-yhteyden rajoitukset |
| --- | --- | --- | --- | --- | --- |
| EM1 |1 näennäisydin |0,5 näennäisydintä, 10 Gt RAM |0,5 näennäisydintä |3,75 sekunnissa |
| EM2 |2 näennäisydintä |1 näennäisydin, 10 Gt RAM |1 näennäisydin |7,5 sekunnissa |
| EM3 |4 näennäisydintä |2 näennäisydintä, 10 Gt RAM |2 näennäisydintä |15 sekunnissa |
| P1 |8 näennäisydintä |4 näennäisydintä, 25 Gt RAM |4 näennäisydintä |30 sekunnissa |
| P2 |16 näennäisydintä |8 näennäisydintä, 50 Gt RAM |8 näennäisydintä |60 sekunnissa |
| P3 |32 näennäisydintä |16 näennäisydintä, 100 Gt RAM |16 näennäisydintä |120 sekunnissa |
| P4 |64 näennäisydintä |32 näennäisydintä, 200 Gt RAM |32 näennäisydintä |240 sekunnissa |
| P5 |128 näennäisydintä |64 näennäisydintä, 400 Gt RAM |64 näennäisydintä |480 sekunnissa |
> [!NOTE]
> - Kun yrität upottaa Microsoft Office -sovelluksilla, EM SKU:iden avulla voit käyttää maksuttoman Power BI -käyttöoikeuden sisältöä. Et kuitenkaan voi käyttää sisältöä maksuttomalla Power BI -käyttöoikeudella, kun käytössäsi on Powerbi.com tai Power BI -mobiilisovellus.
> - Kun yrität upottaa Microsoft Office -sovelluksilla, Powerbi.comin tai Power BI -mobiilisovellusten avulla voit käyttää maksuttoman Power BI -käyttöoikeuden sisältöä.

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>Määritä sovellustyötila varattuun kapasiteettiin

Kun olet luonut varatun kapasiteetin, voit määrittää sovellustyötilan kyseiselle varatulle kapasiteetille. Seuraa näitä ohjeita:

1. Laajenna Power BI -palvelussa työtiloja ja valitse ellipsikuvake työtilalle, jota käytät sisällön upottamiseen. Valitse **Muokkaa työtiloja**.

    ![Muokkaa työtilaa](media/embed-sample-for-your-organization/embed-sample-for-your-organization-036.png)

2. Laajenna **Lisäasetukset**-kohta ja ota käyttöön **Varattu kapasiteetti**. Valitse luomasi varattu kapasiteetti. Valitse **Tallenna**.

    ![Määritä varattu kapasiteetti](media/embed-sample-for-your-organization/embed-sample-for-your-organization-024.png)

3. **Tallennuksen** jälkeen sovellustyötilan nimen vieressä pitäisi näkyä vinoneliö.

    ![Sovellustyötila sidottuna kapasiteettiin](media/embed-sample-for-your-organization/embed-sample-for-your-organization-037.png)

## <a name="admin-settings"></a>Järjestelmänvalvojan asetukset

Yleiset järjestelmänvalvojat eli Power BI -palvelun järjestelmänvalvojat voivat ottaa käyttöön REST-ohjelmointirajapintojen käytön vuokraajassa ja poistaa sen käytöstä. Power BI ‑järjestelmänvalvojat voivat määrittää asetuksen koskemaan koko organisaatiota tai yksittäisiä käyttöoikeusryhmiä. Oletusarvoisesti se on käytössä koko organisaatiolle. Voit tehdä nämä muutokset [Power BI -hallintaportaalissa](../service-admin-portal.md).

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa olet oppinut, miten voit upottaa Power BI-sisältöä sovellukseen Power BI -organisaatiotiliä käyttämällä. Voit nyt yrittää upottaa Power BI -sisältöä sovellukseen sovellusten avulla. Voit myös yrittää upottaa Power BI -sisältöä asiakkaillesi:

> [!div class="nextstepaction"]
> [Upottaminen sovelluksista](embed-from-apps.md)

> [!div class="nextstepaction"]
>[Upottaminen asiakkaillesi](embed-sample-for-customers.md)

Jos sinulla on lisää kysymyksiä, [voit esittää niitä Power BI -yhteisössä](http://community.powerbi.com/).
