---
title: Power BI -raporttipalvelinten uudet ominaisuudet
description: Lue Power BI -raporttipalvelimen uusista ominaisuuksista. Tämä koskee tärkeimpiä ominaisuuksia, ja tietoja päivitetään uusien julkaisujen myötä.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: maggies
ms.openlocfilehash: 07c393425d2a04376a4fcf81c2c35a0e115eeaee
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34481949"
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI -raporttipalvelinten uudet ominaisuudet
Lue Power BI -raporttipalvelimen uusista ominaisuuksista. Tämä koskee tärkeimpiä ominaisuuksia, ja tietoja päivitetään uusien julkaisujen myötä.

Lataa Power BI -raporttipalvelin ja Power BI -raporttipalvelimelle optimoitu Power BI Desktop tutustumalla ohjeaiheeseen [Paikallinen raportointi Power BI -raporttipalvelimella](https://powerbi.microsoft.com/report-server/).

Katso myös seuraavat lähteet, joiden avulla pysyt ajan tasalla Power BI -raporttipalvelimen uusista ominaisuuksista.

* [Microsoftin Power BI ‑blogi](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services -tiimin blogi](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Guy in a Cube ‑YouTube-kanava](https://aka.ms/guyinacube)

Lisätietoja Power BI:hin liittyvistä uusista ominaisuuksista:

* [Power BI -palvelun uudet ominaisuudet](../service-whats-new.md)
* [Power BI Desktopin uudet ominaisuudet](../desktop-latest-update.md)
* [Power BI -mobiilisovellusten uudet ominaisuudet](../mobile-whats-new-in-the-mobile-apps.md)

## <a name="may-2018"></a>Toukokuu 2018

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>Power BI -iOS-mobiilisovellusten etämäärittäminen raporttipalvelimia varten

IT-ylläpitäjänä voit käyttää organisaatiosi ydintietojen hallintatyökalua etämäärittääksesi raporttipalvelimen käyttöoikeudet Power BI -iOS-mobiilisovellukselle. Lisätietoja on kohdassa [Power BI -iOS-mobiilisovellusten etämäärittäminen raporttipalvelimia varten](configure-powerbi-mobile-apps-remote.md).

## <a name="march-2018-release"></a>Maaliskuun 2018 julkaisu

Maaliskuussa 2018 Power BI -raporttipalvelimelle optimoituun Power BI Desktop -versioon lisättiin paljon uusia ominaisuuksia. Alueittain eriteltynä ne ovat seuraavat: 
- [Visualisoinnit](#visuals-updates)
- [Raportointi](#reporting)
- [Analysointi](#analytics)
- [Suorituskyky](#performance)
- [Raporttipalvelin](#report-server)
- [Muut](#other-improvements)

### <a name="highlights-of-this-release"></a>Julkaisun kohokohdat

Uusia ominaisuuksia on vino pino, mutta seuraavat ovat erityisen kiinnostavia.

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[Sääntöihin perustuva ehdollinen muotoilu taulukoissa ja matriiseissa](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)
 
Luo sääntöjä, joiden perusteella taustaväri tai sarakkeen fontin väri valitaan ehdollisesti taulukon tai matriisin liiketoimintalogiikan mukaan.

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[Sivujen näyttäminen ja piilottaminen](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Kuvitellaan, että haluat antaa lukijoillesi raporttisi käyttöoikeudet, mutta jotkut sivut eivät ole täysin valmiit. Nyt voit piilottaa ne, kunnes ne ovat valmiita. Voit myös piilottaa sivut normaalista siirtymisnäkymästä, jolloin lukijat voivat siirtyä sivulle kirjanmerkkien tai porautumisen avulla.

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[Kirjanmerkkien lisääminen](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Voit nyt luoda kirjanmerkkejä ja käyttää raporttisi tietoja kerronnan tukena.

- [Kirjanmerkkien ristiinkorostus](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): Kirjanmerkit säilyttävät ja näyttävät raportin sivun, joka korostettiin ristiin kirjanmerkin luontihetkellä.
- [Entistä joustavammat kirjanmerkit](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): Kirjanmerkit kuvastavat raporttiisi määritettyjä ominaisuuksia ja vaikuttavat ainoastaan valitsemiisi visualisointeihin.

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[Monivalinta-arvopisteet useiden kaavioiden välillä](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

Voit valita useita arvopisteitä useista kaavioista ja käyttää ristiinsuodatusta koko sivulla.

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[Osittajien synkronointi usealle raporttisivulle](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

Osittajaa voidaan käyttää yhdellä, kahdella tai useammalla raporttisivulla.

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[Pikamittarit](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

Luo uusia mittareita nykyisten mittareiden ja taulukon numeeristen sarakkeiden perusteella.

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[Muiden visualisointien suodattaminen poraamalla](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

Kun poraudut jonkin visualisoinnin valittuun luokkaan, voit suodattaa kaikki kyseisen sivun visualisoinnit saman luokan mukaan.

### <a name="visuals-updates"></a>Visualisointien päivitykset

- [Solujen tasaus taulukoissa ja matriisissa](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [Taulukoiden ja matriisien sarakkeiden esitysyksiköt ja tarkka hallinta](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [Ylivuotoarvopisteiden otsikot palkki- ja sarakekaavioissa](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [Arvopisteiden taustavärin hallinta karteesisisten taulukoiden ja karttavisualisoinneissa](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [Palkkien/sarakkeiden täytön hallinta](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [Kaavioakseleiden otsikoiden alan suurentaminen](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [Pistevisualisointi x- ja y-akseliryhmittelyistä](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [Pituus- ja leveyspiireihin perustuva suuren tiheyden näytteenotto kartoissa](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [Reagoivat osittajat](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [Ankkuripäivämäärän lisääminen suhteellisten päivämääräosittajiin](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>Raportointi

- [Visualisoinnin otsikon poistaminen käytöstä raportin lukutilassa](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [Hitaiden tietolähteiden raporttiasetukset](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [Parannettu visualisointien oletussijainti](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [Visualisointien järjestyksen hallinta valintaruudun kautta](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [Raportin objektien lukitseminen](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [Haku muotoilu- ja analyysiruudusta](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [Kentän ominaisuudet -ruutu ja kenttien kuvaukset](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Analysointi

- [UTCNOW() ja UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [Mukautetun päivämäärätaulukon merkitseminen](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [Poraaminen suodattaa muut visualisoinnit](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [Solutason muotoilu monirivisten korttien moniulotteisissa AS-malleissa](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)
 
### <a name="performance"></a>Menestys

- [Suodatuksen suorituskyvyn parannuksia](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [DirectQuery-suorituskyvyn parannuksia](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [Avaamisen ja tallentamisen suorituskyvyn parannuksia](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [Parannuksia ”Näytä kohteet, joilla ei ole tietoja” -ominaisuuteen](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)
 
### <a name="report-server"></a>Raporttipalvelin 

#### <a name="export-to-accessible-pdf"></a>Helppokäyttöisen PDF-tiedoston vieminen

Kun viet sivutetun raportin (RDL) PDF-muotoon, saat nyt helppokäyttöisen/tunnisteellisen PDF-tiedoston. Tiedoston koko on tavallista suurempi, mutta tiedosto toimii paremmin näytönlukuohjelmien ja muiden käyttöä helpottavien toimintojen kanssa. Voit ottaa helppokäyttöiset PDF-tiedostot käyttöön määrittämällä **AccessiblePDF** -laitetietojen asetukseksi **Tosi**. Tutustu [PDF-laitetietojen asetusten](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings) ja [laitetietojen asetusten muuttamiseen](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings).


### <a name="other-improvements"></a>Muut parannukset

- [Parannuksia Lisää sarake esimerkeistä -toimintoon](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [Konsultointipalvelut -pikalinkki](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [Paranneltu virheraportointi](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [Aiemmin havaittujen virheiden tarkastelu](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

 
## <a name="october-2017-release"></a>Lokakuun 2017 julkaisu
### <a name="power-bi-report-data-sources"></a>Power BI -raporttien tietolähteet
Power BI-raporttipalvelimen Power BI -raportit voivat muodostaa yhteyden erilaisiin tietolähteisiin. Voit tuoda tietoja ja ajoittaa tietojen päivittämisen tai tehdä sille suoran kyselyn DirectQueryn tai reaaliaikaisen SQL Server Analysis Services -palvelun avulla. ”Power BI -raporttien tietolähteet Power BI -raporttipalvelimessa” -kohta sisältää tiedon ajoitettua päivittämistä ja DirectQuerya tukevista tietolähteistä.

### <a name="scheduled-data-refresh-for-imported-data"></a>Ajoitettu tuotujen tietojen päivitys
Power BI-raporttipalvelimen avulla voit määrittää ajoitetun tietojen päivittämisen, joka pitää Power BI-raporttien tiedot ajan tasalla upotetulla mallilla reaaliaikaisen yhteyden tai DirectQueryn asemesta. Tiedot tuodaan upotettuun malliin, joten se ei ole yhteydessä alkuperäiseen tietolähteeseen. Tietojen pitäminen ajan tasalla vaatii päivittämistä, mikä tapahtuu ajoitetun päivittämisen avulla. Lue lisätietoja ”Power BI -raporttien ajoitettu päivittäminen Power BI -raporttipalvelimessa” -kohdasta.

### <a name="editing-power-bi-reports-from-the-server"></a>Palvelimella olevien Power BI -raporttien muokkaaminen
Voit avata ja muokata palvelimella olevia Power BI -raporttitiedostoja (.pbix). Saat lataamasi alkuperäisen tiedoston itsellesi.  Tämä tarkoittaa, että **jos palvelin on päivittänyt tiedot, tietoja ei päivitetä, kun avaat tiedoston ensimmäistä kertaa**. Sinun on päivitettävä tiedosto manuaalisesti, jotta muutokset näkyvät.

### <a name="large-file-uploaddownload"></a>Suurten tiedostojen lataaminen palvelimelle tai palvelimelta
Voit ladata enintään 2 Gt:n kokoisia tiedostoja, mutta SQL Server Management Studiossa (SSMS) määritettävissä raporttipalvelimen asetuksissa koon oletusrajoitus on 1 Gt.  Nämä tiedostot on tallennettu tietokantaan samalla tavalla kuin SharePointiin. SQL Serverin luetteloa ei tarvitse määrittää erikseen.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Jaettujen tietojoukkojen käyttö OData-syötteinä
Voit käyttää jaettuja tietojoukkoja OData-syötteellisellä Power BI Desktopilla. Lisätietoja on kohdassa [jaettujen tietojoukkojen käyttö OData-syötteinä Power BI-raporttipalvelimessa](access-dataset-odata.md).

### <a name="scale-out"></a>Skaalattavuus
Tämä versio tukee skaalattavuutta. Kuormituksen tasauksen ja palvelimen affiniteettimäärityksen avulla takaat parhaan käyttökokemuksen. Huomaa, että skenaariota ei ole vielä optimoitu skaalattavuutta varten, joten mallit saatetaan replikoida useille solmuille. Skenaario toimii ilman verkon kuormituksen tasaustoimintoa ja kiinteitä istuntoja. Huomaa kuitenkin, että mallin N-kertaisen lataamisen vuoksi solmut käyttävät tavallista enemmän muistia. Lisäksi yhteyksien välinen suorituskyky heikkenee, kun virtautettu malli kohtaa uuden solmun pyyntöjen välillä.  

### <a name="administrator-settings"></a>Järjestelmänvalvojan asetukset
Järjestelmänvalvojat voivat määrittää seuraavat palvelinklusterin asetukset SSMS:n lisäasetuksista:

* EnableCustomVisuals: Tosi/Epätosi
* EnablePowerBIReportEmbeddedModels: Tosi/Epätosi
* EnablePowerBIReportExportData: Tosi/Epätosi
* MaxFileSizeMb: Oletus on nyt 1 000
* ModelCleanupCycleMinutes: Kuinka usein mallit tarkistetaan muistista poistamista varten
* ModelExpirationMinutes: Kuinka pitkän käyttämättömyysjakson jälkeen malli vanhenee ja poistetaan
* ScheduleRefreshTimeoutMinutes: Tietojen päivityksen enimmäiskesto mallille. Oletuksena tämä on kaksi tuntia.  Ylärajaa ei ole.

**Määritystiedosto rsreportserver.config**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Kehittäjien ohjelmointirajapinta
SSRS 2017:lle julkaistu kehittäjien ohjelmointirajapinta (REST API) on laajennettu Power BI -raporttipalvelimelle, ja se toimii sekä Excel- että .pbix-tiedostojen kanssa. Eräs mahdollinen käyttötapa on tiedostojen ohjelmallinen lataaminen palvelimelta, niiden päivittäminen ja uudelleenjulkaisu. Tämä esimerkki on ainoa tapa päivittää PowerPivot-malleja sisältävät Excel-työkirjat.

Huomaa, että suurille tiedostoille on uusi erillinen ohjelmointirajapinta, jota päivitetään Swaggerin Power BI -raporttipalvelinversiossa. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) -palvelun ja Power BI-raporttipalvelimen muistin käyttö
Power BI-raporttipalvelin toimii nyt sisäisesti SQL Server Analysis Services (SSAS) -palvelimen isäntänä. Tämä ei koske ainoastaan ajoitettua päivittämistä. SSAS:n isännöinti voi suurentaa raporttipalvelimen muistin käyttöä huomattavasti. Palvelinsolmuille on käytettävissä AS.ini-määritystiedosto. Jos SSAS:n käyttö on sinulle tuttua, haluat ehkä päivittää asetukset, kuten muistin käyttörajoituksen, levytilan välimuistiin tallentamisen jne. Katso lisätietoja kohdasta [Palvelinasetukset Analysis Services -palveluissa](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Excel-työkirjojen tarkasteleminen ja käsitteleminen
Excel ja Power BI sisältävät toimialalla ainutlaatuisia työkaluja. Yhdessä ne antavat liiketoiminta-analyytikoille valmiuden tietojen entistä helpompaan keräämiseen, muotoiluun, analyysiin ja visuaaliseen tutkimiseen. Yrityskäyttäjät voivat paitsi tarkastella Power BI -raportteja verkkoportaalissa, myös tehdä saman Excel-työkirjoille Power BI -raporttipalvelimella. Näin he voivat julkaista ja tarkastella itse tuottamaansa Microsoft BI -sisältöä samassa paikassa.

Olemme julkaisseet [vaiheittaisen ohjeet, jotka opastavat Office Onlinen Server (OOS) -palvelimen lisäämisessä Power BI -raporttipalvelimen esikatseluympäristön](excel-oos.md). Volume Licensing -tiliä käyttävät asiakkaat voivat ladata OOS:n Volume License Servicing Centeristä ilmaiseksi. He saavat käyttöönsä vain tarkastelutoiminnot. Kun määritys on valmis, käyttäjät voivat tarkastella ja käsitellä Excel-työkirjoja, jotka:

* ovat riippumattomia ulkoisista tietolähteistä
* ovat reaaliaikaisessa yhteydessä ulkoiseen SQL Server Analysis Services -tietolähteeseen
* sisältävät PowerPivot-tietomallin

### <a name="support-for-new-table-and-matrix-visuals"></a>tukevat uusia taulukko- ja matriisivisualisointeja.
Power BI-raporttipalvelin tukee nyt uusia Power BI -taulukko- ja matriisivisualisointeja. Power BI Desktop -versio on päivitettävä lokakuun 2017 julkaisuversioon, jotta voit luoda kyseisiä visualisointeja sisältäviä raportteja. Versio ei voi olla asennettuna rinnakkain Power BI Desktop (Kesäkuu 2017) -julkaisuversion kanssa. Saat Power BI Desktopin uusimman version [Power BI -raporttipalvelimen lataussivulta](https://powerbi.microsoft.com/report-server/) valitsemalla **lataamisen lisäasetukset**.

## <a name="june-2017"></a>Kesäkuu 2017
* Power BI -raporttipalvelimen GA-versio (generally available, yleisesti saatavana) tulee saataville.

## <a name="may-2017"></a>Toukokuu 2017
* Power BI -raporttipalvelimen esiversio tulee saataville
* Power BI -raporttien paikallinen julkaisemistoiminto
  * Mukautettujen visualisointien tuki
  * Vain reaaliaikaisten Analysis Services -yhteyksien tuki, lisää tietolähteitä tulossa.
  * Power BI -mobiilisovelluksen päivitys mahdollistaa Power BI -raporttipalvelimella isännöityjen Power BI -raporttien näyttämisen
* Parannellut yhteistyöominaisuudet kommentteja sisältävissä raporteissa

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä onPower BI -raporttipalvelin?](get-started.md) 
[Järjestelmänvalvojien opas](admin-handbook-overview.md)  
[Power BI -raporttipalvelimen asentaminen](install-report-server.md)  
[Raportin muodostimen asentaminen](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) -työkalujen lataaminen](http://go.microsoft.com/fwlink/?LinkID=616714)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

