---
title: Power BI -hallintaportaali
description: Hallintaportaalissa voit hallita organisaatiosi Power BI -vuokraajia. Hallintaportaali sisältää esimerkiksi käyttömittareita ja asetuksia. Sen kautta voit käyttää myös Office 365 -hallintakeskusta.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 04/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: a604f50889d4443ba7c8e7da580275e579f69d15
ms.sourcegitcommit: 4b61588e3ab3c8bbb17276402dbf7fa00085a266
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/11/2018
ms.locfileid: "35301822"
---
# <a name="power-bi-admin-portal"></a>Power BI -hallintaportaali

Hallintaportaalissa voit hallita organisaatiosi Power BI -vuokraajia. Hallintaportaali sisältää esimerkiksi käyttömittareita ja asetuksia. Sen kautta voit käyttää myös Office 365 -hallintakeskusta.

Voit hallita yrityksesi Power BI -vuokraajia Power BI -hallintaportaalissa. Hallintaportaalia voivat käyttää kaikki Office 365:n yleiset järjestelmänvalvojat ja käyttäjät, joille on määritetty Power BI -palvelun järjestelmänvalvojan rooli. Jos haluat lisätietoja Power BI -palvelun järjestelmänvalvojan roolista, lue ohjeartikkeli [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md).

Kaikki käyttäjät näkevät **hallintaportaalin** hammasrataskuvakkeen alla. Jos käyttäjä ei ole järjestelmänvalvoja, hän näkee vain **Premium-asetusten** kohdan ja vain ne kapasiteetit, joiden hallintaan hänellä on oikeudet.

## <a name="how-to-get-to-the-admin-portal"></a>Hallintaportaaliin siirtyminen

Tililläsi täytyy olla **yleisen järjestelmänvalvojan** oikeudet Office 365:ssä tai Azure Active Directoryssa tai Power BI -palvelun järjestelmänvalvojan oikeudet, jotta voit käyttää Power BI -hallintaportaalia. Jos haluat lisätietoja Power BI -palvelun järjestelmänvalvojan roolista, lue ohjeartikkeli [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md). Voit siirtyä Power BI -hallintaportaaliin alla annettujen ohjeiden mukaisesti.

1. Napsauta asetusten hammasrataskuvaketta Power BI -palvelun oikeassa yläkulmassa.
2. Valitse **Hallintaportaali**.

![](media/service-admin-portal/powerbi-admin-settings.png)

Portaalissa on kuusi välilehteä. Ne on lueteltu alla:

* [Käyttömittarit](#usage-metrics)
* [Käyttäjät](#users)
* [Valvontalokit](#audit-logs)
* [Vuokraaja-asetukset](#tenant-settings)
* [Premium-asetukset](#premium-settings)
* [Upotuskoodit](#embed-codes)
* [Organisaation visualisoinnit.](#Organization-visuals)

![](media/service-admin-portal/powerbi-admin-landing-page.png)

## <a name="usage-metrics"></a>Käyttömittarit
Hallintaportaalin ensimmäinen välilehti on nimeltään **Käyttömittarit**. Käyttömittariraporttien avulla voit seurata organisaatiosi Power BI -käyttöä. Niistä näet myös, mitkä käyttäjät ja ryhmät käyttävät eniten Power BI:tä organisaatiossasi.

> [!NOTE]
> Kun siirryt koontinäyttöön ensimmäistä kertaa tai käyt siellä ensimmäistä kertaa pitkään aikaan, näet luultavasti latausnäytön, kun koontinäyttöä ladataan.

Kun koontinäyttö on ladattu, näet kaksi ruutuosiota. Ensimmäinen osio sisältää organisaatiosi yksittäisten käyttäjien käyttötiedot ja toinen organisaatiosi ryhmien käyttötiedot.

Näet ruuduissa seuraavat tiedot:

* Näet käyttäjän työtilan kaikkien koontinäyttöjen, raporttien ja tietojoukkojen määrän.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Näet käytetyimmän koontinäytön ja sen käyttäjien määrän. Jos sinulla on esimerkiksi kolmelle käyttäjälle jakamasi koontinäyttö, jonka olet lisännyt myös sisältöpakettiin, johon on yhdistetty kaksi eri käyttäjää, koontinäytön käyttäjämäärä on 6 (1+3+2).
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Näet suosituimmat sisällöt, joihin käyttäjät ovat muodostaneet yhteyksiä. Tämä sisältö voi olla mitä tahansa sisältöä, johon käyttäjät muodostavat yhteyden Nouda tiedot -toiminnolla (esimerkiksi SaaS-sisältöpaketteja, organisaation sisältöpaketteja, tiedostoja tai tietokantoja).
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* Näet käyttäjät, joilla on eniten koontinäyttöjä (sekä heidän itse luomansa koontinäytöt että heille jaetut koontinäytöt).
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* Näet käyttäjät, joilla on eniten raportteja.
  
    ![](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

Toinen osio sisältää samat tiedot ryhmille. Näiden tietojen avulla näet, mitkä organisaatiosi ryhmät ovat aktiivisimpia ja mitä tietoja he käyttävät.

Näin saat tarkan kuvan siitä, kuinka organisaatiosi käyttäjät käyttävät Power BI:tä, ja näet organisaatiosi aktiivisimmat käyttäjät sekä ryhmät.

## <a name="users"></a>Käyttäjät

Hallintaportaalin toinen välilehti on nimeltään **Käyttäjien hallinta**. Power BI:n käyttäjiä hallitaan Office 365:n hallintakeskuksessa, joten tässä osiossa pääset nopeasti paikkaan, jossa voit hallita käyttäjiä, järjestelmänvalvojia ja ryhmiä Office 365:ssä.

![](media/service-admin-portal/powerbi-admin-manage-users.png)

Kun napsautat **Siirry O365-hallintakeskukseen**, sinut siirretään Office 365 -hallintakeskuksen aloitussivulle, jossa voit hallita vuokraajatilisi käyttäjiä.

![](media/service-admin-portal/powerbi-admin-o365-admin-center.png)

## <a name="audit-logs"></a>Valvontalokit

Hallintaportaalin kolmas välilehti on nimeltään **Valvontalokit**. Lokit sijaitsevat Office 365:n tietoturva- ja yhteensopivuuskeskuksessa. Tämän osion kautta pääset nopeasti tietoturva- ja yhteensopivuuskeskukseen Office 365:ssä.

Saat lisätietoja valvontalokeista ohjeartikkeleista [Organisaation Power BI:n valvonta](service-admin-auditing.md).

## <a name="tenant-settings"></a>Vuokraaja-asetukset

Hallintaportaalin neljäs välilehti on nimeltään **Vuokraaja-asetukset**. Vuokraaja-asetusten avulla voit hallita tarkemmin organisaatiossasi käyttöön tarjottavia toimintoja. Jos olet huolissasi luottamuksellisista tiedoista, jotkin toiminnoista eivät ehkä sovellu organisaatiollesi. Tai kenties ehkä haluat tarjota tietyn toiminnon vain tietylle ryhmälle. Tällaisissa tapauksissa voit poistaa toimintoja käytöstä vuokraajatililläsi.

![](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Asetuksen käyttöönotto kaikille vuokraajatilisi käyttäjille voi kestää jopa 10 minuuttia.

Voit määrittää asetuksia kolmeen eri tilaan.

### <a name="disabled-for-the-entire-organization"></a>Poistettu käytöstä koko organisaatiossa

Voit poistaa toiminnon käytöstä, jolloin käyttäjät eivät voi käyttää sitä.

![](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

### <a name="enabled-for-the-entire-organization"></a>Otettu käyttöön koko organisaatiolle

Voit ottaa toiminnon käyttöön koko organisaatiolle, jolloin kaikki käyttäjät voivat käyttää sitä.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

### <a name="enabled-for-a-subset-of-the-organization"></a>Otettu käyttöön organisaation alijoukolle

Voit ottaa toiminnon käyttöön tietyille organisaatiosi käyttäjille. Voit tehdä tämän muutamin eri tavoin. Voit ottaa toiminnon käyttöön koko organisaatiolle tiettyä käyttäjäryhmää lukuun ottamatta.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

Voit myös ottaa toiminnon käyttöön vain tietylle käyttäjäryhmälle tai poistaa sen käytöstä tietyltä käyttäjäryhmältä. Näin voit varmistaa, että tietyt käyttäjät eivät voi käyttää toimintoa, vaikka he olisivat sallitussa ryhmässä.

![](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

## <a name="export-and-sharing-settings"></a>Vienti- ja jakoasetukset

### <a name="share-content-to-external-users"></a>Sisällön jakaminen ulkoisille käyttäjille

Organisaation käyttäjät voivat jakaa koontinäkymiä organisaation ulkopuolisten käyttäjien kanssa.

![](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

Näet seuraavan ilmoituksen, kun jaat ulkoiselle käyttäjälle.

![](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Verkkoon julkaiseminen

Organisaation käyttäjät voivat julkaista raportteja verkossa. [Lue lisätietoja.](service-publish-to-web.md)

![](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Käyttäjät näkevät käyttöliittymässä eri asetuksia sen mukaan, mikä heidän verkkoon julkaisemisen asetuksensa on.

|Toiminto |Otettu käyttöön koko organisaatiolle |Otettu käyttöön koko organisaatiolle |Tietyt käyttöoikeusryhmät   |
|---------|---------|---------|---------|
|Raportin **Tiedosto**-valikon **Julkaise verkkoon** -toiminto|Käytössä kaikille|Ei näkyvissä kaikille|Näkyvissä vain valtuutetuille käyttäjille tai ryhmille.|
|**Asetukset**-valikon **Upotuskoodien hallinta**|Käytössä kaikille|Käytössä kaikille|Käytössä kaikille<br><br>* **Poista**-vaihtoehto vain valtuutetuille käyttäjille tai ryhmille.<br>* **Hae koodit** käytössä kaikille.|
|**Upotuskoodit** hallintaportaalissa|Tila ilmaisee jotain seuraavista:<br>* Aktiivinen<br>* Ei tuettu<br>* Estetty|Tilana näytetään **Ei käytössä**|Tila ilmaisee jotain seuraavista:<br>* Aktiivinen<br>* Ei tuettu<br>* Estetty<br><br>Jos käyttäjälle ei ole annettu oikeuksia vuokraaja-asetuksissa, tilana näytetään **Loukannut**.|
|Aiemmin luodut julkaistut raportit|Kaikki käytössä|Kaikki poissa käytöstä|Raportit näytetään jatkossakin kaikille.|

### <a name="export-data"></a>Tietojen vieminen

Organisaation käyttäjät voivat viedä tietoja ruudusta tai visualisoinnista. [Lue lisätietoja.](power-bi-visualization-export-data.md)

![](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Jos poistat **Vie tiedot** -toiminnon käytöstä, käyttäjät eivät voi käyttää myöskään **Analysoi Excelissä** -toimintoa tai Power BI -palvelun reaaliaikaista yhteyttä.

### <a name="export-reports-as-powerpoint-presentations"></a>Raporttien vieminen PowerPoint-esityksinä

Organisaation käyttäjät voivat viedä Power BI -raportteja PowerPoint-tiedostoina. [Lue lisätietoja.](service-publish-to-powerpoint.md)

![](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Koontinäyttöjen ja raporttien tulostaminen

Organisaation käyttäjät voivat tulostaa koontinäyttöjä ja raportteja. [Lue lisätietoja.](service-print.md)

![](media/service-admin-portal/powerbi-admin-print-dashboard.png)

![](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-settings"></a>Sisältöpakettiasetukset

### <a name="publish-content-packs-to-the-entire-organization"></a>Sisältöpakettien julkaiseminen koko organisaatiolle

Organisaation käyttäjät voivat julkaista sisältöpaketteja koko organisaatiolle.

![](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs"></a>Organisaation mallisisältöpaketin luominen

Organisaation käyttäjät voivat luoda mallisisältöpaketteja, jotka käyttävät yhteen tietolähteeseen perustuvia tietojoukkoja Power BI Desktopissa.

### <a name="push-apps-to-end-users"></a>Sovellusten lähettäminen käyttäjille

Vuokraajatilisi järjestelmävalvoja voi lähettää sovelluksia **vuokraaja-asetuksissa**.

   ![Sovellusten lähettämisen käyttöön ottaminen](media/service-create-distribute-apps/power-bi-apps-pushapps01.png)

Voit vaihtaa asetuksen tilaksi **Käytössä** ja määrittää sitten, ketkä voivat käyttää tätä toimintoa (koko organisaatio tai tietyt käyttöoikeusryhmät).

> [!NOTE]
> Muista, että vuokraaja-asetusten käyttöönotossa voi kestää jonkin aikaa.

Täältä voit lukea lisätietoja [sovellusten lähettämisestä](service-create-distribute-apps.md#how-to-install-an-app-automatically-for-end-users).

## <a name="integration-settings"></a>Integrointiasetukset

### <a name="ask-questions-about-data-using-cortana"></a>Kysymysten esittäminen tiedoille Cortanan avulla
Organisaation käyttäjät voivat kysyä kysymyksiä tiedoistaan Cortanan avulla.

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Analysoi Excelissä -toiminnon käyttäminen paikallisten tietojoukkojen kanssa
Organisaation käyttäjät voivat käyttää paikallisia Power BI -tietojoukkoja Excelillä. [Lue lisätietoja.](service-analyze-in-excel.md)

> [!NOTE]
> Jos poistat **Vie tiedot** -toiminnon käytöstä, estät käyttäjiä käyttämästä myös **Analysoi Excelissä** -toimintoa.

### <a name="use-arcgis-maps-for-power-bi"></a>ArcGIS Maps for Power BI:n käyttäminen

Organisaation käyttäjät voivat käyttää Esrin tarjoamaa ArcGIS Maps for Power BI -visualisointia. [Lue lisää](power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Power BI:n yleisen haun käyttäminen (esikatselu)

Organisaation käyttäjät voivat käyttää Azure-hausta riippuvaisia ulkoisia hakutoimintoja. Käyttäjät voivat esimerkiksi käyttää Cortanaa avaintietojen noutamiseen suoraan Power BI -koontinäytöistä ja raporteista. [Lue lisää](service-cortana-intro.md)

## <a name="custom-visuals-settings"></a>Mukautettujen visualisointien asetukset
### <a name="enable-custom-visuals-for-the-entire-organization"></a>Mukautettujen visualisointien käyttöön ottaminen koko organisaatiossa
Organisaation käyttäjät voivat käyttää mukautettuja visualisointeja ja jakaa niitä. [Lue lisää](power-bi-custom-visuals.md)

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="r-visuals-settings"></a>R-visualisointien asetukset

### <a name="interact-with-an-dshare-r-visuals"></a>R-visualisointien käyttäminen

Organisaation käyttäjät voivat käyttää R-komentosarjoilla luotuja visualisointeja ja jakaa niitä. [Lue lisää](service-r-visuals.md)

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="audit-settings"></a>Valvonta-asetukset

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Valvontalokien luominen sisäisen toiminnan valvonnan ja vaatimustenmukaisuuden tarpeisiin

Organisaation käyttäjät voivat valvoa muiden käyttäjien Power BI:ssä tekemiä toimia. [Lue lisätietoja.](service-admin-auditing.md)

Tämän asetuksen täytyy olla käytössä, jotta valvontalokiin kirjataan merkintöjä. Valvonnan käyttöönoton ja valvontatietojen tarkastelumahdollisuuden välillä voi olla jopa 48 tunnin viive. Jos et näe tietoja välittömästi, tarkista valvontalokit myöhemmin. Jos haet oikeuksia hallintalokien tarkasteluun, samanlainen viive voi esiintyä, ennen kuin oikeudet on myönnetty.

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="dashboard-settings"></a>Koontinäytön asetukset

### <a name="data-classification-for-dashboards"></a>Koontinäyttöjen tietojen luokittelu

Organisaation käyttäjät voivat merkitä koontinäyttöjä luokituksilla, jotka ilmaisevat koontinäyttöjen suojaustasoja. [Lue lisää](service-data-classification.md)

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="developer-settings"></a>Kehittäjäasetukset

### <a name="embed-content-in-apps"></a>Sisällön upottaminen sovelluksiin

Organisaation käyttäjät voivat upottaa Power BI -koontinäyttöjä ja -raportteja SaaS-sovelluksiin (palveluina tarjottaviin sovelluksiin). Jos poistat tämän asetuksen käytöstä, käyttäjät eivät näe REST-ohjelmointirajapintoja, joilla he voivat upottaa Power BI -sisältöä sovelluksiin.

## <a name="premium-settings"></a>Premium-asetukset

Premium-asetusten välilehdessä voit hallita mitä tahansa organisaatiollesi ostettua Power BI Premium -kapasiteettia. Kaikki organisaation käyttäjät näkevät Premium-asetusten välilehden, mutta sen sisällön näkevät vain käyttäjät, joilla on **kapasiteetin järjestelmänvalvojan** oikeudet tai määrityskäyttöoikeudet. Jos käyttäjällä ei ole mitään oikeuksia, hän näkee seuraavan ilmoituksen.

![](media/service-admin-portal/premium-settings-no-access.png "Ei Premium-asetusten käyttöoikeutta")

Jos haluat lisätietoja Premium-asetusten hallinnasta, lue ohjeartikkeli [Power BI Premiumin hallinta](service-admin-premium-manage.md).

## <a name="embed-codes"></a>Upotuskoodit

![Upotuskoodit Power BI -hallintaportaalissa](media/service-admin-portal/embed-codes.png)

Järjestelmänvalvojana voit tarkastella vuokraajatilillesi luotuja upotuskoodeja. Voit tarkastella raporttia tai poistaa upotuskoodin kumotaksesi sen.

## <a name="organization-visuals"></a>Organisaation visualisoinnit

Organisaation visualisointien välilehdessä voit ottaa käyttöön ja hallita organisaatiosi mukautettuja visualisointeja. Näin voittaa ottaa helposti käyttöön organisaatiossa luotuja mukautettuja visualisointeja, joita raportteja tekevät käyttäjät voivat tuoda suoraan Power BI Desktopista raportteihinsa.
 
Tältä sivulta näet kaikki mukautetut visualisoinnit, jotka on tällä hetkellä otettu käyttöön organisaation säilössä.
 
![](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Uuden mukautetun visualisoinnin lisääminen

Jos haluat lisätä luetteloon uuden mukautetun visualisoinnin, valitse **Lisää mukautettu visualisointi**.

![](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

> [!WARNING]
> Mukautettu visualisointi voi sisältää koodia, jolla on tietoturva- tai tietosuojariskejä. Varmista siis, että luotat mukautetun visualisoinnin tekijään ja lähteeseen, ennen kuin otat sen käyttöön organisaation säilössä.
> 

Täytä kentät:
 
* Valitse .pbiviz-tiedosto (pakollinen): Valitse ladattava mukautetun visualisoinnin tiedosto. Vain versioituja ohjelmointirajapinnan mukautettuja visualisointeja tuetaan (lue täältä lisätietoja siitä, mitä tämä tarkoittaa).
Tarkista ennen visualisoinnin lataamista, että sen tietoturva ja tietosuoja täyttävät organisaatiosi vaatimukset. Lue lisätietoja mukautettujen visualisointien tietoturvasta.
 
* Nimeä mukautetut visualisoinnit (pakollinen): anna visualisoinnille lyhyt nimi, jotta Power BI Desktopin käyttäjät tietävät, mitä se tekee.
 
* Kuvake (pakollinen): tämä on Power BI Desktopin käyttöliittymässä näytettävä kuvake.
 
* Kuvaus: anna visualisoinnille lyhyt kuvaus, joka kertoo käyttäjille sen toiminnasta.
 
Aloita latauspyyntö valitsemalla Käytä. Jos lataus onnistuu, näet uuden kohteen luettelossa. Jos lataus epäonnistuu, saat virheilmoituksen.
 
### <a name="delete-a-custom-visual-from-the-list"></a>Mukautetun visualisoinnin poistaminen luettelosta

Jos haluat poistaa visualisoinnin säilöstä pysyvästi, valitse roskakorikuvake.
Ota huomioon, että poistamista ei voi kumota. Kun visualisointi poistetaan, sen näyttäminen olemassa olevissa raporteissa lopetetaan heti. Vaikka lataat saman visualisoinnin uudelleen, se ei korvaa aiempaa poistettua visualisointia. Käyttäjien täytyy tuoda uusi visualisointi uudelleen ja korvata raporteissaan käytetty esiintymä.
 
### <a name="how-to-update-a-visual"></a>Visualisoinnin lataaminen

Jos haluat ladata säilöön visualisoinnin, koska siitä on saatavilla uusi versio (esimerkiksi virheitä on korjattu, uusia toimintoja lisätty jne.), napsauta **latauskuvaketta** ja lataa uusi tiedosto. Varmista, että visualisoinnin tunnus pysyy samana. Uusi tiedosto korvaa aiemmin tiedoston kaikissa organisaation raporteissa. Jos visualisoinnin uusi versio rikkoo minkä tahansa sen aiemman version käyttö- tai tietorakenteen, älä korvaa aiempaa versiota. Lue sen sijaan visualisoinnista uusi versio, joka luetellaan erikseen. Voit esimerkiksi lisätä uuden luetteloidun visualisoinnin nimeen versionumeron (versio X.X). Näin käyttäjät tietävät, että kyseessä on saman visualisoinnin päivitetty versio, ja voivat välttää olemassa olevien raporttien toimintojen virheet sekä ongelmat. Varmista taas, että visualisoinnin tunnus pysyy samana. Kun käyttäjä sitten seuraavan kerran siirtyy organisaatioon säilöön Power BI Desktopista, hän voi tuoda uuden version. Tässä yhteydessä häneltä kysytään, haluaako hän korvata raportissa olevan nykyisen version.

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md)  
[Organisaation Power BI:n valvonta](service-admin-auditing.md)  
[Power BI Premiumin hallinta](service-admin-premium-manage.md)  
[Power BI:n hallinta organisaatiossa](service-admin-administering-power-bi-in-your-organization.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
