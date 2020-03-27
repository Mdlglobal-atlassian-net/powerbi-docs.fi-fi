---
title: Power BI raporttien ohjelmointirajapinnan vieminen
description: Lue, miten voit viedä upotetun Power BI -raportin
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 03/24/2020
ms.openlocfilehash: 35b5c5f05a9c0ae5a36875671a919df12843e295
ms.sourcegitcommit: ad638d553d5f7f5831587791ffa7aa37a47dd6ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/26/2020
ms.locfileid: "80273290"
---
# <a name="export-power-bi-report-to-file-preview"></a>Power BI ‑raportin vieminen tiedostoon (esikatselu)

`exportToFile`-ohjelmointirajapinta mahdollistaa Power BI -raportin viemisen REST-kutsun avulla. Seuraavia tiedostomuotoja tuetaan:
* **PPTX** (PowerPoint)
* **PDF**
* **PNG**
    * PNG-tiedostoon vietäessä useita sivuja sisältävä raportti pakataan zip-tiedostoksi
    * Kukin PNG-paketin tiedosto edustaa yhtä raportin sivua
    * Sivujen nimet ovat samat kuin [Hae sivuja](https://docs.microsoft.com/rest/api/power-bi/reports/getpages)- tai [Hae sivuja ryhmästä](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup) -ohjelmointirajapintojen palautusarvot

## <a name="usage-examples"></a>Käyttöesimerkit

Voit käyttää vientiominaisuutta monella eri tavalla. Tässä on pari esimerkkiä:

* **Lähetä tulostukseen -painike** – Luo sovelluksessa painike, joka käynnistää napsautettaessa vientityön. Työ voi viedä esillä olevan raportin PDF- tai PPTX-muodossa, ja kun vienti on valmis, käyttäjä voi vastaanottaa tiedoston latauksena. Kirjanmerkkien avulla raportin voi viedä tietyssä tilassa, mukaan lukien määritetyt suodattimet, osittajat ja lisäasetukset. Koska ohjelmointirajapinta on asynkroninen, saattaa kestää jonkin aikaa, ennen kuin tiedosto on käytettävissä.

* **Sähköpostin liite** – Lähetä määritetyin väliajoin automatisoitu sähköpostiviesti, jossa on liitteenä PDF-raportti. Tästä skenaariosta voi olla hyötyä, jos haluat automatisoida viikkoraportin lähettämisen johtoportaalle.

## <a name="using-the-api"></a>Ohjelmointirajapinnan käyttäminen

Varmista ennen ohjelmointirajapinnan käyttämistä, että seuraavat [järjestelmänvalvojan vuokraajan asetukset](../../service-admin-portal.md#tenant-settings) ovat käytössä:
* **Vie raportit PowerPoint-esityksinä tai PDF-tiedostoina** – oletusarvoisesti käytössä.
* **Vie raportit kuvatiedostoina** – Pakollinen vain PNG-tiedostoille ja oletusarvoisesti poissa käytöstä.

Ohjelmointirajapinta on asynkroninen. Kun [exportToFile](https://docs.microsoft.com/rest/api/power-bi/reports/exporttofile)-ohjelmointirajapintaa kutsutaan, vientityö käynnistyy. Kun vientityö on käynnistetty, voit seurata työtä [kyselyllä](https://docs.microsoft.com/rest/api/power-bi/reports/getexporttofilestatus), kunnes työ on valmis.

Kyselyn aikana ohjelmointirajapinta palauttaa luvun, joka osoittaa valmiin työn määrän. Kunkin vientityön työmäärä lasketaan raportin sivujen määrän perusteella. Kaikilla sivuilla on sama painoarvo. Jos esimerkiksi olet viemässä raporttia, jossa on kymmenen sivua, ja kysely palauttaa arvon 70, ohjelmointirajapinta on käsitellyt seitsemän vientityön kymmenestä sivusta.

Kun vienti on valmis, kyselyn ohjelmointirajapintakutsu palauttaa [Power BI URL-osoitteen](https://docs.microsoft.com/rest/api/power-bi/reports/getfileofexporttofile), josta tiedoston voi noutaa. URL-osoite on käytettävissä 24 tunnin ajan.

## <a name="supported-features"></a>Tuetut ominaisuudet

### <a name="selecting-which-pages-to-print"></a>Tulostettavien sivujen valitseminen

Määritä ne sivut, jotka haluat tulostaa [Hae sivuja](https://docs.microsoft.com/rest/api/power-bi/reports/getpages)- tai [Hae sivuja ryhmästä](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup) -palautusarvon mukaan. Voit myös määrittää vietävien sivujen järjestyksen.

### <a name="bookmarks"></a>Kirjanmerkit

 `exportToFile`-ohjelmointirajapinnan avulla voit viedä raportin ohjelmallisesti tietyssä tilassa sen jälkeen, kun olet lisännyt siihen suodattimia. Tämä tehdään [Kirjanmerkit](../../consumer/end-user-bookmarks.md)-ominaisuuden avulla. Voit viedä raportin kirjanmerkkien avulla käyttämällä [kirjanmerkkien JavaScript-ohjelmointirajapintaa](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bookmarks).

 Voit esimerkiksi käyttää kirjanmerkin `capturedBookmark.state`-menetelmää, kun haluat valita tietyn käyttäjän raporttiin tekemät muutokset ja viedä sen sitten nykyisessä tilassa.

[Henkilökohtaisia kirjanmerkkejä](../../consumer/end-user-bookmarks.md#personal-bookmarks) ja [pysyviä suodattimia](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) ei tueta.

### <a name="authentication"></a>Todentaminen

Voit todentaa vain käyttäjän (tai pääkäyttäjän) tai [palvelun päänimen](embed-service-principal.md).

### <a name="row-level-security-rls"></a>Rivitason suojaus (RLS)

[Rivitason suojauksen (RLS)](embedded-row-level-security.md) avulla voit viedä raportin, jossa näkyy vain tietyille käyttäjille näkyviä tietoja. Jos olet esimerkiksi viemässä myyntiraporttia, joka on määritetty alueellisten roolien perusteella, voit suodattaa raportin ohjelmallisesti niin, että vain tietty alue näytetään.

Jos haluat viedä RLS:n avulla, sinulla on oltava seuraavat oikeudet:
* Kirjoitus- ja uudelleenjakamisoikeudet siihen tietojoukkoon, johon raportti on yhdistetty
* Jos raportti sijaitsee v1-työtilassa, sinun on oltava työtilan järjestelmänvalvoja
* Jos raportti sijaitsee v2-työtilassa, sinun on oltava työtilan jäsen tai järjestelmänvalvoja

### <a name="data-protection"></a>Tietojen suojaus

PDF- ja PPTX-muodot tukevat [luottamuksellisuustunnisteita](../../admin/service-security-data-protection-overview.md#sensitivity-labels-in-power-bi). Jos viet luottamuksellisuustunnisteen sisältävän raportin PDF- tai PPTX-tiedostoon, viety tiedosto näyttää raportin luottamuksellisuustunnisteineen.

Luottamuksellisuustunnisteella merkittyä raporttia ei voi viedä PDF- tai PPTX-muotoon [palvelun päänimen](embed-service-principal.md) avulla.

### <a name="localization"></a>Lokalisointi

Kun käytät `exportToFile`-ohjelmointirajapintaa, voit valita halutun sijainnin. Lokalisointiasetukset vaikuttavat siihen, miten raportti näytetään, esimerkiksi muuttamalla muotoilun valitun sijainnin mukaan.

## <a name="concurrent-requests"></a>Samanaikaiset pyynnöt

`exportToFile` tukee samanaikaisia vientityöpyyntöjä. Alla olevassa taulukossa näkyy niiden töiden määrä, jotka voidaan suorittaa samanaikaisesti sen mukaan, missä SKU:ssa raportti sijaitsee. Samanaikaiset pyynnöt viittaavat raporttisivuihin. Esimerkiksi yhden vientipyynnön 20 sivua A6-SKU:ssa käsitellään samanaikaisesti. Tämä kestää suunnilleen yhtä kauan kuin kahdenkymmenen yksisivuisen vientipyynnön lähettäminen.

Työ, joka ylittää samanaikaisten pyyntöjen määrän, ei pääty. Jos esimerkiksi viet kolme sivua A1-SKU:ssa, ensimmäinen työ suoritetaan, ja jälkimmäiset kaksi sivua odottavat kahta seuraavaa suoritusjaksoa.

|Azure-SKU  |Office-SKU  |Samanaikaisten raporttisivujen enimmäismäärä  |
|-----------|------------|-----------|
|A1         |EM1         |1          |
|A2         |EM2         |2          |
|A3         |EM3         |3          |
|A4         |P1          |6          |
|A5         |P2          |12         |
|A6         |P3          |24         |

## <a name="limitations"></a>Rajoitukset

* Vietävän raportin on sijaittava Premium- tai Embedded-kapasiteetissa.
* Vietävän raportin tietojoukon on sijaittava Premium- tai Embedded-kapasiteetissa.
* Julkisen esikatselun tunnissa vietävien Power BI -raporttisivujen kapasiteettikohtainen rajoitus on 50.
* Vietyjen raporttien tiedostokoko ei voi olla yli 250 Mt.
* Luottamuksellisuusselitteitä ei tueta PNG-tiedostoon vietäessä.
* Luottamuksellisuustunnisteella merkittyä raporttia ei voi viedä PDF- tai PPTX-muotoon [palvelun päänimen](embed-service-principal.md) avulla.
* Vietyyn raporttiin voi sisällyttää 30 sivua. Jos raportissa on enemmän sivuja, ohjelmointirajapinta palauttaa virheen ja vientityö peruutetaan.
* [Henkilökohtaisia kirjanmerkkejä](../../consumer/end-user-bookmarks.md#personal-bookmarks) ja [pysyviä suodattimia](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) ei tueta.
* Alla lueteltuja Power BI -visualisointeja ei tueta. Kun näitä visualisointeja sisältävä raportti viedään, raportin visualisointeja sisältäviä osia ei hahmonneta, ja ne näyttävät virhesymbolin.
    * Sertifioimattomat Power BI -visualisoinnit
    * R-visualisoinnit
    * PowerApps
    * Python-visualisoinnit
    * Visio

## <a name="code-examples"></a>Koodiesimerkit

Kun luot vientityön, noudatettavia vaiheita on kolme:

1. Vientipyynnön lähettäminen.
2. Kysely.
3. Tiedoston noutaminen.

Tässä osiossa annetaan esimerkkejä jokaisesta vaiheesta.

### <a name="step-1---sending-an-export-request"></a>Vaihe 1 – vientipyynnön lähettäminen

Ensimmäinen vaihe on vientipyynnön lähettäminen. Tässä esimerkissä vientipyyntö lähetetään tietystä sivusta.

```csharp
/////// Export sample ///////
private async Task<string> PostExportRequest(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    IList<string> pageNames = null /* Get the page names from the GetPages API */)
{
    var powerBIReportExportConfiguration = new PowerBIReportExportConfiguration
    {
        Settings = new ExportReportSettings
        {
            Locale = "en-us",
        },
        // Note that page names differ from the page display names.
        // To get the page names use the GetPages API.
        Pages = pageNames?.Select(pn => new ExportReportPage(Name = pn)).ToList(),
    };
    var exportRequest = new ExportReportRequest
    {
        Format = format,
        PowerBIReportConfiguration = powerBIReportExportConfiguration,
    };
    var export = await Client.Reports.ExportToFileInGroupAsync(groupId, reportId, exportRequest);
    // Save the export ID, you'll need it for polling and getting the exported file
    return export.Id;
}
```

### <a name="step-2---polling"></a>Vaihe 2 – kysely

Kun olet lähettänyt vientipyynnön, määritä kyselyn avulla, milloin se vientitiedosto on valmis, jota odotat.

```csharp
private async Task<Export> PollExportRequest(
    Guid reportId,
    Guid groupId,
    string exportId /* Get from the ExportToAsync response */,
    int timeOutInMinutes,
    CancellationToken token)
{
    Export exportStatus = null;
    DateTime startTime = DateTime.UtcNow;
    const int c_secToMillisec = 1000;
    do
    {
        if (DateTime.UtcNow.Subtract(startTime).TotalMinutes > timeOutInMinutes || token.IsCancellationRequested)
        {
            // Error handling for timeout and cancellations 
            return null;
        }
        var httpMessage = await Client.Reports.GetExportToFileStatusInGroupWithHttpMessagesAsync(groupId, reportId, exportId);
        exportStatus = httpMessage.Body;
        // You can track the export progress using the PercentComplete that's part of the response
        SomeTextBox.Text = string.Format("{0} (Percent Complete : {1}%)", exportStatus.Status.ToString(), exportStatus.PercentComplete);
        if (exportStatus.Status == ExportState.Running || exportStatus.Status == ExportState.NotStarted)
        {
            // The recommended waiting time between polling requests can be found in the RetryAfter header
            // Note that this header is only populated when the status is either Running or NotStarted
            var retryAfter = httpMessage.Response.Headers.RetryAfter;
            var retryAfterInSec = retryAfter.Delta.Value.Seconds;
            await Task.Delay(retryAfterInSec * c_secToMillisec);
        }
    }
    // While not in a terminal state, keep polling
    while (exportStatus.Status != ExportState.Succeeded && exportStatus.Status != ExportState.Failed);
    return exportStatus;
}
```

### <a name="step-3---getting-the-file"></a>Vaihe 3 – tiedoston noutaminen

Kun kysely palauttaa URL-osoitteen, nouda vastaanotetut tiedostot tämän esimerkin avulla.

```csharp
private async Task<ExportedFile> GetExportedFile(
    Guid reportId,
    Guid groupId,
    Export export /* Get from the GetExportStatusAsync response */)
{
    if (export.Status == ExportState.Succeeded)
    {
        var fileStream = await Client.Reports.GetFileOfExportToFileAsync(groupId, reportId, export.Id);
        return new ExportedFile
        {
            FileStream = fileStream,
            FileSuffix = export.ResourceFileExtension,
        };
    }
    return null;
}
public class ExportedFile
{
    public Stream FileStream;
    public string FileSuffix;
}
```

### <a name="end-to-end-example"></a>Esimerkki koko prosessista

Tämä on esimerkki raportin koko vientiprosessista. Tämä esimerkki sisältää seuraavat vaiheet:
1. [Vientipyynnön lähettäminen](#step-1---sending-an-export-request).
2. [Kysely](#step-2---polling).
3. [Tiedoston noutaminen](#step-3---getting-the-file).

```csharp
private async Task<ExportedFile> ExportPowerBIReport(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    int pollingtimeOutInMinutes,
    CancellationToken token,
    IList<string> pageNames = null /* Get the page names from the GetPages API */)
{
    try
    {
        var exportId = await PostExportRequest(reportId, groupId, format, pageNames);
        var export = await PollExportRequest(reportId, groupId, exportId, pollingtimeOutInMinutes, token);
        if (export == null || export.Status != ExportState.Succeeded)
        {
            // Error, failure in exporting the report
            return null;
        }
        return await GetExportedFile(reportId, groupId, export);
    }
    catch
    {
        // Error handling
        throw;
    }
}
```

## <a name="next-steps"></a>Seuraavat vaiheet

Lue, miten voit upottaa asiakkaille ja organisaatiolle tarkoitettua sisältöä:

> [!div class="nextstepaction"]
>[Upottaminen asiakkaillesi](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)
