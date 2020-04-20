---
title: Power BI raporttien ohjelmointirajapinnan vieminen
description: Lue ohjeet upotetun sivutetun Power BI -raportin viemiseen
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 04/05/2020
ms.openlocfilehash: acb13a70ea4693f447b70aa59da07cd91639de25
ms.sourcegitcommit: 81407c9ccadfa84837e07861876dff65d21667c7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/13/2020
ms.locfileid: "81268761"
---
# <a name="export-paginated-report-to-file-preview"></a>Sivutetun raportin vienti tiedostoon (esiversio)

`exportToFile` -ohjelmointirajapinta mahdollistaa sivutetun Power BI -raportin viemisen REST-kutsun avulla. Seuraavia tiedostomuotoja tuetaan:
* **.pptx** (PowerPoint)
* **.pdf**
* **.xlsx** (Excel)
* **.dox** (Word)
* **.csv**
* **.xml**
* **.mhtml**
* **kuva**.
    * Kun viet kuvaa, määritä kuvan tiedostomuoto muotoasetuksella `OutputFormat`.
    * Tuettuja OutputFormat-arvoja ovat .bmp, .emf, .gif, .jpeg, .png ja .tiff (oletus)

## <a name="usage-examples"></a>Käyttöesimerkit

Voit käyttää vientiominaisuutta monella eri tavalla. Tässä on pari esimerkkiä:

* **Lähetä tulostukseen -painike** – Luo sovelluksessa painike, joka käynnistää napsautettaessa vientityön. Työ voi viedä tarkasteltavan raportin .pdf- tai .pptx-muodossa. Kun vienti on valmis, käyttäjä voi vastaanottaa tiedoston latauksena. Raporttiparametreilla ja muotoasetuksilla voit viedä raportin tietyssä tilassa (mukaan lukien suodatetut tiedot, mukautetut sivukoot ja muut muotokohtaiset asetukset). Koska ohjelmointirajapinta on asynkroninen, saattaa kestää jonkin aikaa, ennen kuin tiedosto on käytettävissä.

* **Sähköpostin liite**: lähetä määritetyin väliajoin automatisoitu sähköpostiviesti, jossa on liitteenä .pdf-raportti. Tästä skenaariosta voi olla hyötyä, jos haluat automatisoida viikkoraportin lähettämisen johtoportaalle.

## <a name="using-the-api"></a>Ohjelmointirajapinnan käyttäminen

Ohjelmointirajapinta on asynkroninen. Kun [exportToFile](https://docs.microsoft.com/rest/api/power-bi/reports/exporttofile)-ohjelmointirajapintaa kutsutaan, vientityö käynnistyy. Kun vientityö on käynnistetty, voit seurata työtä [kyselyllä](https://docs.microsoft.com/rest/api/power-bi/reports/getexporttofilestatus), kunnes työ on valmis.

Kun vienti on valmis, kyselyn ohjelmointirajapintakutsu palauttaa [Power BI URL-osoitteen](https://docs.microsoft.com/rest/api/power-bi/reports/getfileofexporttofile), josta tiedoston voi noutaa. URL-osoite on käytettävissä 24 tunnin ajan.

## <a name="supported-features"></a>Tuetut ominaisuudet

### <a name="format-settings"></a>Muotoasetukset

Määritä kullekin tiedostomuodolle tietyt muotoasetukset. Tuetut ominaisuudet ja arvot vastaavat sivutetun raportin URL-parametrien [laitetietoparametreja](../../paginated-reports/report-builder-url-parameters.md#report-commands-rdl).

Tässä on kaksi esimerkkiä: Ensimmäinen vie raportin neljä ensimmäistä sivua raporttisivun koon avulla .pptx-tiedostoon. Toinen vie raportin kolmannen sivun .jpeg-tiedostoon.

**Neljän ensimmäisen sivun vieminen .pptx-tiedostoon**

```json
{
      "format": "PPTX",
      "paginatedReportConfiguration":{
            "formatSettings":{
                  "UseReportPageSize": "true",
                  "StartPage": "1",
                  "EndPage": "4"
            }
      }
}
```

**Kolmannen sivun vieminen .jpeg-tiedostoon**

```json
{
      "format": "IMAGE",
      "paginatedReportConfiguration":{
            "formatSettings":{
                  "OutputFormat": "JPEG",
                  "StartPage": "3",
                  "EndPage": "3"
            }
      }
}
```

### <a name="report-parameters"></a>Raportin parametrit

`exportToFile`-ohjelmointirajapinnan avulla voit viedä raportin ohjelmallisesti tietyillä raporttiparametreilla. Tämä tehdään [raporttiparametrien](../../paginated-reports/paginated-reports-parameters.md) ominaisuuden avulla.

Tässä on esimerkki raporttiparametrien arvojen määrittämisestä.

```json
{
      "format": "PDF",
      "paginatedReportConfiguration":{
            "parameterValues":[
                  {"name": "State", "value": "WA"},
                  {"name": "City", "value": "Seattle"},
                  {"name": "City", "value": "Bellevue"},
                  {"name": "City", "value": "Redmond"}
            ]
      }
}
```

### <a name="authentication"></a>Todentaminen

Voit todentaa vain käyttäjän (tai pääkäyttäjän) tai [palvelun päänimen](embed-service-principal.md).

### <a name="row-level-security-rls"></a>Rivitason suojaus (RLS)

Kun käytät Power BI -tietojoukkoa, jonka lähteeksi on määritetty rivitason suojaus, voit viedä raportin, jossa näkyy vain tietyille käyttäjille näkyviä tietoja. Jos olet esimerkiksi viemässä myyntiraporttia, joka on määritetty alueellisten roolien perusteella, voit suodattaa raportin ohjelmallisesti niin, että vain tietty alue näytetään.

Jos haluat viedä RLS:n avulla, sinulla täytyy olla lukuoikeudet siihen Power BI -tietojoukkoon, jota raportti käyttää tietolähteenä.

Tässä on esimerkki RLS:n käyttäjänimen määrittämisestä.

```json
{
      "format": "PDF",
      "paginatedReportConfiguration":{
            "identities": [
                  {"username": "john@contoso.com"}            
            ]
      }
}
```

## <a name="code-examples"></a>Koodiesimerkit

Koodiesimerkeissä käytettävä Power BI API SDK on ladattavissa [täältä](https://www.nuget.org/packages/Microsoft.PowerBI.Api).

Kun luot vientityön, noudatettavia vaiheita on kolme:

1. Vientipyynnön lähettäminen.
2. Kysely.
3. Tiedoston noutaminen.

Tässä osiossa annetaan esimerkkejä jokaisesta vaiheesta.

### <a name="step-1---sending-an-export-request"></a>Vaihe 1 – vientipyynnön lähettäminen

Ensimmäinen vaihe on vientipyynnön lähettäminen. Tässä esimerkissä vientipyyntö lähetetään tietylle sivualueelle ja koolle sekä tietyille raporttiparametriarvoille.

```csharp
private async Task<string> PostExportRequest(
    Guid reportId,
    Guid groupId)
{
    // For documentation purposes the export configuration is created in this method
    // Ordinarily, it would be created outside and passed in
    var paginatedReportExportConfiguration = new PaginatedReportExportConfiguration()
    {
        FormatSettings = new Dictionary<string, string>()
        {
            {"PageHeight", "14in"},
            {"PageWidth", "8.5in" },
            {"StartPage", "1"},
            {"EndPage", "4"}
        },
        ParameterValues = new List<ParameterValue>()
        {
            { new ParameterValue() {Name = "State", Value = "WA"} },
            { new ParameterValue() {Name = "City", Value = "Redmond"} }
        }
    };

    var exportRequest = new ExportReportRequest
    {
        Format = FileFormat.PDF,
        PaginatedReportExportConfiguration = paginatedReportExportConfiguration,
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
    const int secToMillisec = 1000;
    do
    {
        if (DateTime.UtcNow.Subtract(startTime).TotalMinutes > timeOutInMinutes || token.IsCancellationRequested)
        {
            // Error handling for timeout and cancellations
            return null;
        }

        var httpMessage = 
            await Client.Reports.GetExportToFileStatusInGroupWithHttpMessagesAsync(groupId, reportId, exportId);
            
        exportStatus = httpMessage.Body;
        if (exportStatus.Status == ExportState.Running || exportStatus.Status == ExportState.NotStarted)
        {
            // The recommended waiting time between polling requests can be found in the RetryAfter header
            // Note that this header is only populated when the status is either Running or NotStarted
            var retryAfter = httpMessage.Response.Headers.RetryAfter;
            var retryAfterInSec = retryAfter.Delta.Value.Seconds;

            await Task.Delay(retryAfterInSec * secToMillisec);
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
        var httpMessage = 
            await Client.Reports.GetFileOfExportToFileInGroupWithHttpMessagesAsync(groupId, reportId, export.Id);

        return new ExportedFile
        {
            FileStream = httpMessage.Body,
            ReportName = export.ReportName,
            FileExtension = export.ResourceFileExtension,
        };
    }

    return null;
}

public class ExportedFile
{
    public Stream FileStream;
    public string ReportName;
    public string FileExtension;
}
```

### <a name="end-to-end-example"></a>Esimerkki koko prosessista

Tämä on esimerkki raportin koko vientiprosessista. Tämä esimerkki sisältää seuraavat vaiheet:
1. [Vientipyynnön lähettäminen](#step-1---sending-an-export-request).
2. [Kysely](#step-2---polling).
3. [Tiedoston noutaminen](#step-3---getting-the-file).

```csharp
private async Task<ExportedFile> ExportPaginatedReport(
    Guid reportId,
    Guid groupId,
    int pollingtimeOutInMinutes,
    CancellationToken token)
{
    try
    {
        var exportId = await PostExportRequest(reportId, groupId);

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
>[Raportin vieminen tiedostoon](export-to.md)

> [!div class="nextstepaction"]
>[Upottaminen asiakkaillesi](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)