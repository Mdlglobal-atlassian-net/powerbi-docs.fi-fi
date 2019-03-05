---
title: Power BI -hallintaportaali
description: Hallintaportaalissa voit hallita organisaatiosi Power BI -vuokraajia. Hallintaportaali sisältää esimerkiksi käyttömittareita ja asetuksia. Sen kautta voit käyttää myös Office 365 -hallintakeskusta.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/24/2019
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: a4180f211a2b31a8610d410a74e0cca25dcdad15
ms.sourcegitcommit: d4d36b6b200f2693b545e4a3e66d94c77a3cfafb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/01/2019
ms.locfileid: "57014641"
---
# <a name="administering-power-bi-in-the-admin-portal"></a>Power BI:n hallinta hallintaportaalissa

Hallintaportaalissa voit hallita organisaatiosi Power BI *-vuokraajaa*. Hallintaportaali sisältää esimerkiksi käyttömittareita ja asetuksia. Sen kautta voit käyttää myös Office 365 -hallintakeskusta.

Hallintaportaalin kaikkia toimintoja voivat käyttää kaikki Office 365:n yleiset järjestelmänvalvojat ja käyttäjät, joille on määritetty Power BI -palvelun järjestelmänvalvojan rooli. Jos et ole tällainen käyttäjä, näet portaalissa vain **kapasiteettiasetukset**. Jos haluat lisätietoja Power BI -palvelun järjestelmänvalvojan roolista, lue ohjeartikkeli [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md).

## <a name="how-to-get-to-the-admin-portal"></a>Hallintaportaaliin siirtyminen

Tililläsi täytyy olla **yleisen järjestelmänvalvojan** oikeudet Office 365:ssä tai Azure Active Directoryssa tai Power BI -palvelun järjestelmänvalvojan oikeudet, jotta voit käyttää Power BI -hallintaportaalia. Jos haluat lisätietoja Power BI -palvelun järjestelmänvalvojan roolista, lue ohjeartikkeli [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md). Voit siirtyä Power BI -hallintaportaaliin alla annettujen ohjeiden mukaisesti.

1. Napsauta asetusten hammasrataskuvaketta Power BI -palvelun oikeassa yläkulmassa.

1. Valitse **Hallintaportaali**.

    ![Hallintaportaalin asetukset](media/service-admin-portal/powerbi-admin-settings.png)

Portaalissa on seitsemän välilehteä. Tässä artikkelissa kerrotaan lisätietoja näistä välilehdistä.

![Siirtyminen hallintaportaalissa](media/service-admin-portal/powerbi-admin-landing-page.png)

* [Käyttömittarit](#usage-metrics)
* [Käyttäjät](#users)
* [Valvontalokit](#audit-logs)
* [Vuokraaja-asetukset](#tenant-settings)
* [Premium-asetukset](#premium-settings)
* [Upotuskoodit](#embed-codes)
* [Organisaation visualisoinnit](#organization-visuals)

## <a name="usage-metrics"></a>Käyttömittarit

**Käyttömittareiden** avulla voit seurata organisaatiosi Power BI -käyttöä. Niistä näet myös, mitkä käyttäjät ja ryhmät käyttävät eniten Power BI:tä organisaatiossasi.

> [!NOTE]
> Kun siirryt koontinäyttöön ensimmäistä kertaa tai käyt siellä ensimmäistä kertaa pitkään aikaan, näet luultavasti latausnäytön, kun koontinäyttöä ladataan.

Kun koontinäyttö on ladattu, näet kaksi ruutuosiota. Ensimmäinen osio sisältää organisaatiosi yksittäisten käyttäjien käyttötiedot ja toinen organisaatiosi ryhmien käyttötiedot.

Näet ruuduissa seuraavat tiedot:

* Näet käyttäjän työtilan kaikkien koontinäyttöjen, raporttien ja tietojoukkojen määrän.
  
    ![Koontinäyttöjen, raporttien ja tietojoukkojen määrät](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Näet käytetyimmän koontinäytön ja sen käyttäjien määrän. Jos sinulla on esimerkiksi kolmelle käyttäjälle jakamasi koontinäyttö, jonka olet lisännyt myös sisältöpakettiin, johon on yhdistetty kaksi eri käyttäjää, koontinäytön käyttäjämäärä on 6 (1+3+2).
  
    ![Käytetyimmät koontinäytöt](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Näet suosituimmat sisällöt, joihin käyttäjät ovat muodostaneet yhteyksiä. Tämä sisältö voi olla mitä tahansa sisältöä, johon käyttäjät muodostavat yhteyden Nouda tiedot -toiminnolla (esimerkiksi SaaS-sisältöpaketteja, organisaation sisältöpaketteja, tiedostoja tai tietokantoja).
  
    ![Käytetyimmät paketit](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* Näet käyttäjät, joilla on eniten koontinäyttöjä (sekä heidän itse luomansa koontinäytöt että heille jaetut koontinäytöt).
  
    ![Aktiivisimmat käyttäjät – koontinäytöt](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* Näet käyttäjät, joilla on eniten raportteja.
  
    ![Aktiivisimmat käyttäjät – raportit](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

Toinen osio sisältää samat tiedot ryhmille. Näiden tietojen avulla näet, mitkä organisaatiosi ryhmät ovat aktiivisimpia ja mitä sisältöä he käyttävät.

Näin saat tarkan kuvan siitä, kuinka organisaatiosi käyttäjät käyttävät Power BI:tä, ja näet organisaatiosi aktiivisimmat käyttäjät sekä ryhmät.

## <a name="users"></a>Käyttäjät

Voit hallita Power BI -käyttäjiä, -ryhmiä ja -järjestelmänvalvojia Office 365 -hallintakeskuksessa. **Käyttäjät**-välilehdessä on linkki vuokraajasi hallintakeskukseen.

![Siirry O365-hallintakeskukseen](media/service-admin-portal/powerbi-admin-manage-users.png)

## <a name="audit-logs"></a>Valvontalokit

Voit hallita Power BI -valvontalokeja Office 365:n tietoturva- ja yhteensopivuuskeskuksessa. **Valvontalokit**-välilehdessä on linkki vuokraajasi tietoturva- ja yhteensopivuuskeskukseen. [Lue lisää](service-admin-auditing.md)

Jotta voit käyttää valvontalokeja, varmista, että [**Valvontalokien luominen sisäisen toiminnan valvonnan ja vaatimustenmukaisuuden tarpeisiin**](#create-audit-logs-for-internal-activity-auditing-and-compliance) -asetus on käytössä.

## <a name="tenant-settings"></a>Vuokraaja-asetukset

**Vuokraaja-asetukset**-välilehdessä voit hallita yksityiskohtaisemmin organisaatiossasi käyttöön tarjottavia toimintoja. Jos olet huolissasi luottamuksellisista tiedoista, jotkin toiminnoista eivät ehkä sovellu organisaatiollesi. Tai kenties ehkä haluat tarjota tietyn toiminnon vain tietylle ryhmälle.

Seuraavassa kuvassa näytetään **Vuokraaja-asetukset**-välilehden kaksi ensimmäistä osiota.

![Vuokraaja-asetukset](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Asetuksen muutoksen voimaan tuleminen kaikille vuokraajatilisi käyttäjille voi kestää 10 minuuttia.

Asetuksilla voi olla kolme tilaa:

* **Poistettu käytöstä koko organisaatiolle**: Kukaan organisaatiossasi ei voi käyttää tätä ominaisuutta.

    ![Kaikki-asetus poistettu käytöstä](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

* **Otettu käyttöön koko organisaatiolle**: Kaikki organisaatiossasi voivat käyttää tätä ominaisuutta.

    ![Kaikki-asetus otettu käyttöön](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

* **Otettu käyttöön organisaation alijoukolle**: Organisaatiosi erityinen käyttäjien tai ryhmien alijoukko voi käyttää tätä ominaisuutta.

    Voit ottaa toiminnon käyttöön koko organisaatiolle tiettyä käyttäjäryhmää lukuun ottamatta.

    ![Alijoukko-asetus otettu käyttöön](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

    Voit myös ottaa toiminnon käyttöön vain tietylle käyttäjäryhmälle tai poistaa sen käytöstä tietyltä käyttäjäryhmältä. Näin voit varmistaa, että tietyt käyttäjät eivät voi käyttää toimintoa, vaikka he olisivat sallitussa ryhmässä.

    ![Lukuun ottamatta -asetus otettu käyttöön](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

Seuraavissa osioissa luodaan yleiskatsaus vuokraaja-asetusten eri tyyppeihin.

## <a name="workspace-settings"></a>Työtilan asetukset

### <a name="create-workspaces-preview"></a>Työtilojen luominen (esiversio)

Organisaation käyttäjät voivat luoda sovelluksen työtiloja tehdäkseen yhteistyötä koontinäyttöjen, raporttien ja muun sisällön parissa. [Lue lisää](service-create-the-new-workspaces.md)

## <a name="export-and-sharing-settings"></a>Vienti- ja jakamisasetukset

### <a name="share-content-to-external-users"></a>Sisällön jakaminen ulkoisille käyttäjille

Organisaation käyttäjät voivat jakaa koontinäkymiä organisaation ulkopuolisten käyttäjien kanssa. [Lue lisää](service-share-dashboards.md#share-a-dashboard-or-report-with-people-outside-your-organization)

![Ulkoiset käyttäjät -asetus](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

Seuraavassa kuvassa näet esiin tulevan ilmoituksen, kun jaat ulkoiselle käyttäjälle.

![Jaa ulkoisen käyttäjän kanssa](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Julkaise verkkoon

Organisaation käyttäjät voivat julkaista raportteja verkossa. [Lue lisää](service-publish-to-web.md)

Seuraavassa kuvassa näkyy raportin **Tiedosto**-valikko, kun **Julkaise verkkoon** -asetus on käytössä.

![Julkaise verkkoon -asetus](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Käyttäjät näkevät käyttöliittymässä eri asetuksia sen mukaan, mikä heidän **Julkaise verkkoon** -asetuksensa on.

|Ominaisuus |Otettu käyttöön koko organisaatiolle |Otettu käyttöön koko organisaatiolle |Tietyt käyttöoikeusryhmät   |
|---------|---------|---------|---------|
|Raportin **Tiedosto**-valikon **Julkaise verkkoon** -toiminto|Käytössä kaikille|Ei näkyvissä kaikille|Näkyvissä vain valtuutetuille käyttäjille tai ryhmille.|
|**Asetukset**-valikon **Upotuskoodien hallinta**|Käytössä kaikille|Käytössä kaikille|Käytössä kaikille<br><br>* **Poista**-vaihtoehto vain valtuutetuille käyttäjille tai ryhmille.<br>* **Hae koodit** käytössä kaikille.|
|**Upotuskoodit** hallintaportaalissa|Tila ilmaisee jotain seuraavista:<br>* Aktiivinen<br>* Ei tuettu<br>* Estetty|Tilana näytetään **Ei käytössä**|Tila ilmaisee jotain seuraavista:<br>* Aktiivinen<br>* Ei tuettu<br>* Estetty<br><br>Jos käyttäjälle ei ole annettu oikeuksia vuokraaja-asetuksissa, tilana näytetään **Loukannut**.|
|Aiemmin luodut julkaistut raportit|Kaikki käytössä|Kaikki poissa käytöstä|Raportit näytetään jatkossakin kaikille.|

### <a name="export-data"></a>Tietojen vieminen

Organisaation käyttäjät voivat viedä tietoja ruudusta tai visualisoinnista. [Lue lisää](visuals/power-bi-visualization-export-data.md)

Seuraavassa kuvassa näkyy tietojen vieminen ruudusta.

![Tietojen vieminen ruudusta](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Jos poistat **Vie tiedot** -toiminnon käytöstä, käyttäjät eivät voi käyttää myöskään **Analysoi Excelissä** -toimintoa tai Power BI -palvelun reaaliaikaista yhteyttä.

### <a name="export-reports-as-powerpoint-presentations-or-pdf-documents"></a>Vie raportit PowerPoint-esityksinä tai PDF-tiedostoina

Organisaation käyttäjät voivat viedä Power BI -raportteja PowerPoint-tiedostoina tai PDF-tiedostoina. [Lue lisää](consumer/end-user-powerpoint.md)

Seuraavassa kuvassa näkyy raportin **Tiedosto**-valikko, kun **Vie raportit PowerPoint-esityksinä tai PDF-tiedostoina** -asetus on käytössä.

![Vie raportit PowerPoint-esityksinä](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Tulosta raporttinäkymiä ja raportteja

Organisaation käyttäjät voivat tulostaa koontinäyttöjä ja raportteja. [Lue lisää](consumer/end-user-print.md)

Seuraavassa kuvassa näkyy koontinäytön tulostaminen.

![Tulosta koontinäyttö](media/service-admin-portal/powerbi-admin-print-dashboard.png)

Seuraavassa kuvassa näkyy raportin **Tiedosto**-valikko, kun **Tulosta koontinäyttöjä ja raportteja** -asetus on käytössä.

![Raportin tulostaminen](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-and-app-settings"></a>Sisältöpaketin ja sovelluksen asetukset

### <a name="publish-content-packs-and-apps-to-the-entire-organization"></a>Julkaise sisältöpaketteja ja sovelluksia koko organisaatiolle

Organisaation käyttäjät voivat julkaista sisältöpaketteja ja sovelluksia koko organisaatiolle vain tietyille ryhmille julkaisemisen lisäksi. [Lue lisää](service-organizational-content-pack-manage-update-delete.md)

Seuraavassa kuvassa näkyy **Koko organisaatio** -vaihtoehto sisältöpaketin luomisessa.

![Sisältöpaketin julkaiseminen organisaatiolle](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-apps"></a>Luo mallisovelluksia

Organisaation käyttäjät voivat luoda mallisovelluksia, jotka käyttävät Power BI Desktopissa luotuja tietojoukkoja. Lue lisätietoja [mallisovelluksista](template-content-pack-authoring.md)

### <a name="push-apps-to-end-users"></a>Lähetä sovellukset käyttäjille

Käyttäjät voivat jakaa sovelluksia suoraan käyttäjien kanssa edellyttämättä asennusta AppSourcesta. [Lue lisää](service-create-distribute-apps.md)

## <a name="integration-settings"></a>Integrointiasetukset

### <a name="ask-questions-about-data-using-cortana"></a>Kysymysten esittäminen tiedoille Cortanan avulla

Organisaation käyttäjät voivat kysyä kysymyksiä tiedoistaan Cortanan avulla. [Lue lisää](service-cortana-enable.md)

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Analysoi Excelissä -toiminnon käyttäminen paikallisten tietojoukkojen kanssa

Organisaation käyttäjät voivat käyttää paikallisia Power BI -tietojoukkoja Excelillä. [Lue lisää](service-analyze-in-excel.md)

> [!NOTE]
> Jos poistat **Vie tiedot** -toiminnon käytöstä, estät käyttäjiä käyttämästä myös **Analysoi Excelissä** -toimintoa.

### <a name="use-arcgis-maps-for-power-bi"></a>ArcGIS Maps for Power BI:n käyttäminen

Organisaation käyttäjät voivat käyttää Esrin tarjoamaa ArcGIS Maps for Power BI -visualisointia. [Lue lisää](visuals/power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Power BI:n yleisen haun käyttäminen (esikatselu)

Organisaation käyttäjät voivat käyttää Azure-hausta riippuvaisia ulkoisia hakutoimintoja. Käyttäjät voivat esimerkiksi käyttää Cortanaa avaintietojen noutamiseen suoraan Power BI -koontinäytöistä ja raporteista. [Lue lisää](service-cortana-intro.md)

## <a name="custom-visuals-settings"></a>Mukautettujen visualisointien asetukset

### <a name="add-and-use-custom-visuals"></a>Lisää ja käytä mukautettuja visualisointeja

Organisaation käyttäjät voivat käyttää mukautettuja visualisointeja ja jakaa niitä. [Lue lisää](power-bi-custom-visuals.md)

> [!NOTE]
> Tämä asetus voidaan ulottaa koskemaan koko organisaatiota tai rajoittaa määrättyihin ryhmiin.

### <a name="allow-only-certified-visuals"></a>Salli vain sertifioidut visualisoinnit

Organisaation käyttäjät, joille on annettu oikeudet lisätä ja käyttää mukautettuja visualisointeja ”Lisää ja käytä mukautettuja visualisointeja” -asetuksen mukaisesti, saavat käyttää ainoastaan [sertifioituja mukautettuja visualisointeja](https://go.microsoft.com/fwlink/?linkid=2002010) (sertifioimattomat visualisoinnit estetään ja käyttöyritys johtaa virheilmoitukseen). 


## <a name="r-visuals-settings"></a>R-visualisointien asetukset

### <a name="interact-with-and-share-r-visuals"></a>Tee toimia R-visualisointien kanssa ja jaa niitä

Organisaation käyttäjät voivat käyttää R-komentosarjoilla luotuja visualisointeja ja jakaa niitä. [Lue lisää](visuals/service-r-visuals.md)

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="audit-and-usage-settings"></a>Valvonta- ja käyttöasetukset

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Valvontalokien luominen sisäisen toiminnan valvonnan ja vaatimustenmukaisuuden tarpeisiin

Organisaation käyttäjät voivat valvoa muiden käyttäjien Power BI:ssä tekemiä toimia. [Lue lisää](service-admin-auditing.md)

Tämän asetuksen täytyy olla käytössä, jotta valvontalokiin kirjataan merkintöjä. Valvonnan käyttöönoton ja valvontatietojen tarkastelumahdollisuuden välillä voi olla jopa 48 tunnin viive. Jos et näe tietoja välittömästi, tarkista valvontalokit myöhemmin. Jos haet oikeuksia hallintalokien tarkasteluun, samanlainen viive voi esiintyä, ennen kuin oikeudet on myönnetty.

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

### <a name="usage-metrics-for-content-creators"></a>Käyttötiedot sisällöntekijöille

Organisaation käyttäjät voivat tarkastella luomiensa koontinäyttöjen ja raporttien käyttötietoja. [Lue lisää](service-usage-metrics.md)

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>Käyttäjäkohtaiset tiedot sisällöntekijöille tarkoitetuissa käyttötiedoissa

Sisällöntekijöille tarkoitetut käyttötiedot paljastavat sisällön käyttäjien näyttönimet ja sähköpostiosoitteet. [Lue lisää](service-usage-metrics.md)

Oletusarvoisesti käyttäjäkohtaiset tiedot on otettu käyttöön käyttötiedoille ja sisällöntekijän tilitiedot sisältyvät tietoraporttiin. Jos et halua sisällyttää näitä tietoja joillekin tai kaikille käyttäjille, poista ominaisuus käytöstä määritetyille käyttöoikeusryhmille tai koko organisaatiolle. Tilitiedot näkyvät sitten raportissa *nimettöminä*.

## <a name="dashboard-settings"></a>Koontinäytön asetukset

### <a name="data-classification-for-dashboards"></a>Koontinäyttöjen tietojen luokittelu

Organisaation käyttäjät voivat merkitä koontinäyttöjä luokituksilla, jotka ilmaisevat koontinäyttöjen suojaustasoja. [Lue lisää](service-data-classification.md)

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="developer-settings"></a>Kehittäjäasetukset

### <a name="embed-content-in-apps"></a>Sisällön upottaminen sovelluksiin

Organisaation käyttäjät voivat upottaa Power BI -koontinäyttöjä ja -raportteja SaaS-sovelluksiin (palveluina tarjottaviin sovelluksiin). Jos poistat tämän asetuksen käytöstä, käyttäjät eivät näe REST-ohjelmointirajapintoja, joilla he voivat upottaa Power BI -sisältöä sovelluksiin. [Lue lisää](developer/embedding.md)

## <a name="dataflow-settings-preview"></a>Tietovuon asetukset (esikatselu)

### <a name="create-and-use-dataflows-preview"></a>Tietovoiden luominen ja käyttäminen (esikatselu)

Organisaatiosi käyttäjät voivat luoda ja käyttää tietovoita. Saat yleiskatsauksen tietovoista artikkelista [Omatoiminen tietojen valmistelu Power BI:ssä (esikatselu)](service-dataflows-overview.md). Jos haluat ottaa tietovuot käyttöön Premium-kapasiteetissa, tutustu artikkeliin [Kuormitusten määrittäminen](service-admin-premium-workloads.md).

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="template-apps-settings-preview"></a>Mallisovellusten asetukset (esikatselu)

Mallisovelluksiin vaikuttaa kaksi asetusta. 

![Power BI -hallintaportaalin mallisovellusten asetukset](media/service-admin-portal/power-bi-admin-portal-template-apps.png)

Ensimmäinen asetus, **Luo mallisovelluksia**, määrittää sen, ketkä organisaatiossa voivat luoda mallisovelluksia. Mallisovellusten kehittäjät voivat sitten jakaa mallisovellukset organisaatiosi ulkopuolisille asiakkaille AppSourcen tai jonkin muun jakelumenetelmän kautta.

![Power BI -hallintaportaali, Luo mallisovelluksia -asetus](media/service-admin-portal/power-bi-admin-portal-template-app-settings.png)

Toinen asetus, **Asenna mallisovellukset**, määrittää sen, ketkä organisaatiossa voivat ladata ja asentaa mallisovelluksia AppSourcesta tai muusta lähteestä

## <a name="capacity-settings"></a>Kapasiteettiasetukset

### <a name="power-bi-premium"></a>Power BI Premium

**Power BI Premium** -välilehdessä voit hallita mitä tahansa organisaatiollesi ostettua Power BI Premium -kapasiteettia (EM- tai P-varastointiyksikkö). Kaikki organisaation käyttäjät näkevät **Power BI Premium** -asetusten välilehden, mutta sen sisällön näkevät vain käyttäjät, joilla on *kapasiteetin järjestelmänvalvojan* oikeudet tai määrityskäyttöoikeudet. Jos käyttäjällä ei ole mitään oikeuksia, näyttöön tulee seuraava ilmoitus.

![Ei Premium-asetusten käyttöoikeutta](media/service-admin-portal/premium-settings-no-access.png)

### <a name="power-bi-embedded"></a>Power BI Embedded

**Power BI Embedded** -välilehden avulla voit tarkastella Power BI Embedded (A-varastointiyksikkö) -kapasiteetteja, jotka olet ostanut asiakkaalle. Koska voit ostaa A-varastointiyksikköjä vain Azuresta, voit [hallita Azuren upotettuja kapasiteetteja](developer/azure-pbie-create-capacity.md) **Azure-portaalissa**.

Lisätietoja siitä, miten voit hallita Power BI Embedded (A-varastointiyksikkö) -asetuksia, on artikkelissa [Mikä on Power BI Embedded](developer/azure-pbie-what-is-power-bi-embedded.md).

## <a name="embed-codes"></a>Upotuskoodit

Järjestelmänvalvojana voit tarkastella vuokraajatilillesi luotuja upotuskoodeja. Voit myös kumota tai poista koodeja. [Lue lisää](service-publish-to-web.md)

![Upotuskoodit Power BI -hallintaportaalissa](media/service-admin-portal/embed-codes.png)

## <a name="organizational-visuals"></a>Organisaation visualisoinnit

**Organisaation visualisoinnit** -välilehden avulla voit ottaa käyttöön ja hallita organisaatiosi mukautettuja visualisointeja. Organisaation visualisointien avulla voit helposti käyttää omia visualisointeja organisaatiossa, ja raporttien tekijät voivat sitten hakea ja tuoda niitä raportteihinsa Power BI Desktopista. [Lue lisää](power-bi-custom-visuals-organization.md)

> [!WARNING]
> Mukautettu visualisointi voi sisältää koodia, jolla on tietoturva- tai tietosuojariskejä. Varmista siis, että luotat mukautetun visualisoinnin tekijään ja lähteeseen, ennen kuin otat sen käyttöön organisaation säilössä.

Seuravasta kuvasta näet kaikki mukautetut visualisoinnit, jotka on tällä hetkellä otettu käyttöön organisaation säilössä.

![Organisaation järjestelmänvalvojan visualisointi](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Uuden mukautetun visualisoinnin lisääminen

Jos haluat lisätä luetteloon uuden mukautetun visualisoinnin, toimi seuraavasti. 

1. Valitse oikeanpuoleisessa ruudussa **Lisää mukautettu visualisointi**.

    ![Mukautettujen visualisointien lomake](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

1. Täytä **Mukautetun visualisoinnin lisääminen** -lomake:

    * **Valitse .pbiviz-tiedosto** (pakollinen): valitse ladattava mukautetun visualisoinnin tiedosto. Vain versioituja ohjelmointirajapinnan mukautettuja visualisointeja tuetaan (lue täältä lisätietoja siitä, mitä tämä tarkoittaa).

    Tarkista ennen visualisoinnin lataamista, että sen tietoturva ja tietosuoja täyttävät organisaatiosi vaatimukset.

    * **Nimeä mukautetut visualisoinnit** (pakollinen): anna visualisoinnille lyhyt nimi, jotta Power BI Desktopin käyttäjät tietävät, mitä se tekee.

    * **Kuvake**: Power BI Desktopin käyttöliittymässä näytettävä kuvaketiedosto.

    * **Kuvaus**: anna visualisoinnille lyhyt kuvaus, joka kertoo käyttäjille sen toiminnasta.

1. Aloita latauspyyntö valitsemalla **Käytä**. Jos lataus onnistuu, näet uuden kohteen luettelossa. Jos lataus epäonnistuu, saat virheilmoituksen.

### <a name="delete-a-custom-visual-from-the-list"></a>Mukautetun visualisoinnin poistaminen luettelosta

Jos haluat poistaa visualisoinnin pysyvästi, valitse visualisoinnin roskakorikuvake säilössä.

> [!IMPORTANT]
> Poistamista ei voi kumota. Kun visualisointi poistetaan, sen näyttäminen olemassa olevissa raporteissa lopetetaan heti. Vaikka lataat saman visualisoinnin uudelleen, se ei korvaa aiemmin poistettua. Käyttäjät voivat kuitenkin tuoda uuden visualisoinnin uudelleen ja korvata sillä raporteissaan esiintyvän visualisoinnin.

### <a name="disable-a-custom-visual-in-the-list"></a>Mukautetun visualisoinnin poistaminen käytöstä luettelossa

Jos haluat poistaa visualisoinnin käytöstä organisaation säilöstä, valitse rataskuvake. Poista mukautettu visualisointi käytöstä **Käyttö**-osiossa.

Kun olet poistanut visualisoinnin käytöstä, visualisointia ei hahmonneta olemassa oleviin raportteihin, ja näet alla olevan virhesanoman.

*Tämä mukautettu visualisointi ei ole enää käytettävissä. Saat lisätietoja ottamalla yhteyttä järjestelmänvalvojaasi.*

Suosikkeihin lisätyt visualisoinnit toimivat kuitenkin edelleen.

Päivitysten tai järjestelmänvalvojan muutoksen jälkeen Power BI Desktop -käyttäjien on käynnistettävä sovellus uudelleen tai päivitettävä selain Power BI -palvelussa, jotta päivitykset näkyvät.

### <a name="update-a-visual"></a>Visualisoinnin päivittäminen

Jos haluat päivittää visualisoinnin organisaation säilöstä, valitse rataskuvake. Hae uuden version visualisointi selaamalla ja lataa se.

Varmista, että visualisoinnin tunnus pysyy samana. Uusi tiedosto korvaa aiemman tiedoston kaikissa organisaation raporteissa. Jos visualisoinnin uusi versio rikkoo minkä tahansa sen aiemman version käyttö- tai tietorakenteen, älä korvaa aiempaa versiota. Lue sen sijaan visualisoinnista uusi versio, joka luetellaan erikseen. Voit esimerkiksi lisätä uuden luetteloidun visualisoinnin nimeen versionumeron (versio X.X). Näin käyttäjät tietävät, että kyseessä on saman visualisoinnin päivitetty versio, ja voivat välttää olemassa olevien raporttien toimintojen virheet sekä ongelmat. Varmista taas, että visualisoinnin tunnus pysyy samana. Kun käyttäjä sitten seuraavan kerran siirtyy organisaatioon säilöön Power BI Desktopista, hän voi tuoda uuden version. Tässä yhteydessä häneltä kysytään, haluaako hän korvata raportissa olevan nykyisen version.

Saat lisätietoja [organisaation mukautettujen visualisointien usein kysytyistä kysymyksistä](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#organizational-custom-visuals).

## <a name="dataflow-storage-preview"></a>Tietovuon tallennustila (esikatselu)

Oletusarvon mukaan Power BI:ssä käytetyt tiedot tallennetaan Power BI:n tarjoamaan sisäiseen tallennustilaan. Tietovoiden ja Azure Data Lake Storage Gen2 (ADLS Gen2) -järjestelmän integroinnin myötä voit tallentaa tietovuot organisaatiosi Azure Data Lake Storage Gen2 -tilille. Lisätietoja on kohdassa [Tietovuot ja Azure Data Lake -integrointi (esikatselu)](service-dataflows-azure-data-lake-integration.md).

## <a name="workspaces-preview"></a>Työtilat (esikatselu)

Järjestelmänvalvojana voit tarkastella vuokraajassa olevia työtiloja. Voit lajitella ja suodattaa työtilojen luetteloja ja näyttää kunkin työtilan tiedot. Huomaa, että taulukon sarakkeet vastaavat [Power BI -järjestelmänvalvojan Rest-ohjelmointirajapinnan](/rest/api/power-bi/admin) palauttamia ominaisuuksia. Omat työtilat ovat tyyppiä **PersonalGroup**, vanha työtilat tyyppiä **Group** ja nykyiset työtilat tyyppiä **Workspace**. Lisätietoja on kohdassa [Uusien työtilojen luominen (esiversio) Power BI:ssä](service-create-the-new-workspaces.md).

![Työtilojen luettelo](media/service-admin-portal/workspaces-list.png)

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI:n hallinta organisaatiossa](service-admin-administering-power-bi-in-your-organization.md)  [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md)  
[Organisaation Power BI:n valvonta](service-admin-auditing.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
