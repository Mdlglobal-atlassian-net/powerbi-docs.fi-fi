---
title: Power BI -hallintaportaali
description: Hallintaportaalissa voit hallita organisaatiosi Power BI -vuokraajia. Hallintaportaali sisältää esimerkiksi käyttömittareita ja asetuksia. Sen kautta voit käyttää myös Microsoft 365 -hallintakeskusta.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/27/2020
ms.author: kfollis
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 8ff022c09fc58f5ebeadbb869039c00c6dd28533
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83275589"
---
# <a name="administering-power-bi-in-the-admin-portal"></a>Power BI:n hallinta hallintaportaalissa

Hallintaportaalissa voit hallita organisaatiosi Power BI *-vuokraajaa*. Portaali sisältää esimerkiksi käyttömittareita ja asetuksia. Sen kautta voit käyttää myös Microsoft 365 -hallintakeskusta.

Hallintaportaalin kaikkia toimintoja voivat käyttää kaikki Office 365:n yleiset järjestelmänvalvojat ja käyttäjät, joille on määritetty Power BI -palvelun järjestelmänvalvojan rooli. Jos et ole tällainen käyttäjä, näet portaalissa vain **kapasiteettiasetukset**. Jos haluat lisätietoja Power BI -palvelun järjestelmänvalvojan roolista, lue ohjeartikkeli [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md).

## <a name="how-to-get-to-the-admin-portal"></a>Hallintaportaaliin siirtyminen

Tililläsi täytyy olla **yleisen järjestelmänvalvojan** oikeudet Office 365:ssä tai Azure Active Directoryssa (Azure AD) tai Power BI -palvelun järjestelmänvalvojan oikeudet, jotta voit käyttää Power BI -hallintaportaalia. Jos haluat lisätietoja Power BI -palvelun järjestelmänvalvojan roolista, lue ohjeartikkeli [Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md). Voit siirtyä Power BI -hallintaportaaliin alla annettujen ohjeiden mukaisesti.

1. Napsauta asetusten hammasrataskuvaketta Power BI -palvelun oikeassa yläkulmassa.

1. Valitse **Hallintaportaali**.

    ![Hallintaportaalin asetukset](media/service-admin-portal/powerbi-admin-settings.png)

Portaalissa on yhdeksän välilehteä. Tässä artikkelissa kerrotaan lisätietoja näistä välilehdistä.

![Siirtyminen hallintaportaalissa](media/service-admin-portal/powerbi-admin-landing-page.png)

* [Käyttömittarit](#usage-metrics)
* [Käyttäjät](#users)
* [Valvontalokit](#audit-logs)
* [Vuokraaja-asetukset](#tenant-settings)
* [Kapasiteettiasetukset](#capacity-settings)
* [Upotuskoodit](#embed-codes)
* [Organisaation visualisoinnit.](#organizational-visuals)
* [Tietovuon tallennustila (esikatselu)](#dataflowStorage)
* [Työtilat](#workspaces)
* [Mukautus](#custom-branding)

## <a name="usage-metrics"></a>Käyttömittarit

**Käyttömittareiden** avulla voit seurata organisaatiosi Power BI -käyttöä. Niistä näet myös, mitkä käyttäjät ja ryhmät käyttävät eniten Power BI:tä organisaatiossasi. 

> [!NOTE]
> Kun siirryt koontinäyttöön ensimmäistä kertaa tai käyt siellä ensimmäistä kertaa pitkään aikaan, näet luultavasti latausnäytön, kun koontinäyttöä ladataan.

Kun koontinäyttö on ladattu, näet kaksi ruutuosiota. Ensimmäinen osio sisältää organisaatiosi yksittäisten käyttäjien käyttötiedot ja toinen organisaatiosi ryhmien käyttötiedot.

Näet ruuduissa seuraavat tiedot:

* Näet käyttäjän työtilassa kaikkien koontinäyttöjen, raporttien ja tietojoukkojen määrän.
  
    ![Koontinäyttöjen, raporttien ja tietojoukkojen määrät](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Näet käytetyimmän koontinäytön ja sen käyttäjien määrän. Jos sinulla on esimerkiksi kolmelle käyttäjälle jakamasi koontinäyttö, jonka olet lisännyt myös sisältöpakettiin, johon on yhdistetty kaksi eri käyttäjää, koontinäytön käyttäjämäärä on 6 (1 + 3 + 2).
  
    ![Käytetyimmät koontinäytöt](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Näet suosituimmat sisällöt, joihin käyttäjät ovat muodostaneet yhteyksiä. Tämä sisältö voi olla mitä tahansa sisältöä, johon käyttäjät muodostavat yhteyden Nouda tiedot -toiminnolla (esimerkiksi SaaS-sisältöpaketteja, organisaation sisältöpaketteja, tiedostoja tai tietokantoja).
  
    ![Käytetyimmät paketit](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* Näet käyttäjät, joilla on eniten koontinäyttöjä (sekä heidän itse luomansa koontinäytöt että heille jaetut koontinäytöt).
  
    ![Aktiivisimmat käyttäjät – koontinäytöt](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* Näet käyttäjät, joilla on eniten raportteja.
  
    ![Aktiivisimmat käyttäjät – raportit](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

Toinen osio sisältää samat tiedot ryhmille. Näiden tietojen avulla näet, mitkä organisaatiosi ryhmät ovat aktiivisimpia ja mitä sisältöä he käyttävät.

Näin saat tarkan kuvan siitä, kuinka organisaatiosi käyttäjät käyttävät Power BI:tä, ja näet organisaatiosi aktiivisimmat käyttäjät sekä ryhmät.

## <a name="control-usage-metrics"></a>Käyttötietojen hallinta

Käyttötietoraportit ovat ominaisuus, jonka Power BI:n tai Office 365:n järjestelmänvalvoja voi ottaa käyttöön tai poistaa käytöstä. Järjestelmänvalvojat hallitsevat tarkkaan sitä, kellä käyttäjillä on oikeus käyttötietoihin. Ne ovat oletusarvoisesti **käytössä** organisaation kaikilla käyttäjillä.

Järjestelmänvalvojat voivat myös määrittää, voivatko sisällön luojat nähdä käyttötietojen käyttäjäkohtaiset tiedot. 

Lue lisätietoja itse raporteista osiosta [Power BI:n koontinäyttöjen ja raporttien käyttötietojen valvonta](../collaborate-share/service-usage-metrics.md).

### <a name="usage-metrics-for-content-creators"></a>Käyttötiedot sisällöntekijöille

1. Valitse hallintaportaalissa **Vuokraaja-asetukset** > **Käyttötiedot sisällöntekijöille**.

    ![Hallintaportaalin vuokraajan asetukset, käyttötiedot](media/service-admin-portal/power-bi-admin-usage-metrics.png)

1. Ota käyttötiedot käyttöön (tai poista ne käytöstä) > **Käytä**.

    ![Käyttötiedot otettu käyttöön](../collaborate-share/media/service-usage-metrics/power-bi-tenant-settings-updated.png)


### <a name="per-user-data-in-usage-metrics"></a>Käyttäjäkohtaiset tiedot käyttömittareissa

Oletusarvoisesti käyttäjäkohtaiset tiedot on otettu käyttöön käyttötiedoille ja sisällön kuluttajan tilitiedot sisältyvät tietoraporttiin. Jos et halua sisällyttää näitä tietoja joillekin tai kaikille käyttäjille, poista ominaisuus käytöstä määritetyiltä käyttöoikeusryhmiltä tai koko organisaatiolta. Tilitiedot näkyvät sitten raportissa *nimettöminä*.

![Käyttäjäkohtaiset käyttötiedot](media/service-admin-portal/power-bi-admin-per-user-usage-data.png)

### <a name="delete-all-existing-usage-metrics-content"></a>Poista kaikki olemassa oleva käyttömittarien sisältö

Kun käyttötietoja poistetaan koko organisaation käytöstä, järjestelmänvalvojat voivat käyttää yhtä tai kumpaakin seuraavista asetuksista:

- **Poista kaikki olemassa oleva käyttömittarien sisältö**. Asetus poistaa kaikki aiemmin luodut raportit ja koontinäytön ruudut, jotka on luotu käyttämällä käyttötietoraportteja ja tietojoukkoja. Tämä vaihtoehto poistaa käyttöoikeuden käyttötietoihin kaikilta organisaation käyttäjiltä, jotka tietoja ehkä jo käyttävät. 
- **Poista kaikki olemassa olevat käyttäjäkohtaiset tiedot nykyisten käyttömittarien sisällössä** Tämä vaihtoehto poistaa käyttöoikeuden käyttäjäkohtaisiin tietoihin kaikilta organisaation käyttäjiltä, jotka tietoja ehkä jo käyttävät. 

Ole varovainen, sillä aiemmin luodun käyttötietosisällön ja käyttäjäkohtaisten tietojen sisällön poistamista ei voi peruuttaa.

## <a name="users"></a>Käyttäjät

Voit hallita Power BI -käyttäjiä, -ryhmiä ja -järjestelmänvalvojia Microsoft 365 -hallintakeskuksessa. **Käyttäjät**-välilehdessä on linkki vuokraajasi hallintakeskukseen.

![Siirry Microsoft 365 -hallintakeskukseen](media/service-admin-portal/powerbi-admin-manage-users.png)

## <a name="audit-logs"></a>Valvontalokit

Voit hallita Power BI -valvontalokeja Office 365:n tietoturva- ja yhteensopivuuskeskuksessa. **Valvontalokit**-välilehdessä on linkki vuokraajasi tietoturva- ja yhteensopivuuskeskukseen. [Lisätietoja](service-admin-auditing.md)

Jotta voit käyttää valvontalokeja, varmista, että [**Valvontalokien luominen sisäisen toiminnan valvonnan ja vaatimustenmukaisuuden tarpeisiin**](#create-audit-logs-for-internal-activity-auditing-and-compliance) -asetus on käytössä.

## <a name="tenant-settings"></a>Vuokraaja-asetukset

**Vuokraaja-asetukset**-välilehdessä voit hallita yksityiskohtaisemmin organisaatiossasi käyttöön tarjottavia toimintoja. Jos olet huolissasi luottamuksellisista tiedoista, jotkin toiminnoista eivät ehkä sovellu organisaatiollesi. Tai kenties ehkä haluat tarjota tietyn toiminnon vain tietylle ryhmälle.

Seuraavassa kuvassa näytetään useita asetuksia **Vuokraaja-asetukset**-välilehdellä.

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

## <a name="help-and-support-settings"></a>Ohjeiden ja tuen asetukset

### <a name="publish-get-help-information"></a>Julkaise ”Hanki apua” -tiedot

Organisaation käyttäjät voivat siirtyä sisäisiin ohje- ja tukiresursseihin Power BI:n ohjevalikosta. Tarkemmin sanottuna nämä parametrit muuttavat Lue-, Yhteisö- ja Hanki apua -valikkokohtien toimintaa.

Kun määrität URL-osoitteen käyttöoikeuspyyntöjä varten, voit mukauttaa **Päivitä tili** -painikkeen URL-kohdeosoitetta. Käyttäjät, joilla ei ole Power BI Pro -käyttöoikeutta, näkevät tämän painikkeen **Päivitä Power BI Pro** -valintaikkunassa ja **Hallitse henkilökohtaista tallennustilaa** -sivulla. Lisäksi Power BI ei enää näytä **Kokeile Prota ilmaiseksi** -painiketta tässä valintaikkunassa tai tallennussivulla. Näin varmistat, että Power BI ohjaa käyttäjäsi luotettavasti organisaatiosi määrittämien prosessien kautta käyttöoikeuksien hallintaratkaisun läpi.

![Lukuun ottamatta -asetus otettu käyttöön](media/service-admin-portal/powerbi-admin-tenant-settings-gethelp.png)

### <a name="receive-email-notifications-for-service-outages-or-incidents"></a>Ota vastaan sähköposti-ilmoituksia palvelukatkoista tai -tapauksista

Sähköpostia käyttävät käyttöoikeusryhmät saavat sähköposti-ilmoituksia, jos palvelukatkos tai tapaus vaikuttaa tähän vuokraajaan. Lue lisätietoja [palvelun keskeytymisilmoituksista](service-interruption-notifications.md).

## <a name="workspace-settings"></a>Työtilan asetukset

**Vuokraaja-asetuksissa** hallinta portaalissa on kaksi osaa työtilojen hallintaa varten:

- Luo uusia työtilakokemuksia.
- Käytä tietojoukkoja eri työtiloissa.

### <a name="create-the-new-workspaces"></a>Uusien työtilojen luominen

Työtilat ovat paikkoja, joissa käyttäjät voivat tehdä yhteistyötä koontinäyttöjen, raporttien ja muun sisällön parissa. Järjestelmänvalvojat voivat **Luo työtiloja (uusi työtilakokemus)** -asetuksen avulla ilmoittaa, ketkä organisaation käyttäjät voivat luoda työtiloja. Järjestelmänvalvojat voivat sallia sen, että kaikki organisaation työntekijät voivat luoda uusia työtilakokemusten työtiloja tai että yksikään heistä ei voi luoda niitä. He voivat myös rajoittaa luomisen tiettyjen käyttöoikeusryhmien jäsenille. Lue lisää [työtiloista](../collaborate-share/service-new-workspaces.md).

:::image type="content" source="media/service-admin-portal/power-bi-admin-workspace-settings.png" alt-text="Luo uusia työtilakokemuksia":::

Office 365 -ryhmiin perustuvissa perinteisissä työtiloissa hallinta tapahtuu edelleen Office 365 -hallintaportaalissa ja Azure Active Directoryssä.

> [!NOTE]
> **Luo työtiloja (uusi työtilakokemus)** -oletusasetuksen mukaan uusia Power BI -työtiloja saavat luoda vain ne käyttäjät, jotka voivat luoda Office 365 -ryhmiä. Muista määrittää arvo Power BI -hallintaportaalissa sen varmistamiseksi, että asianmukaiset käyttäjät voivat luoda niitä.

**Luettelo työtiloista**

Hallintaportaalissa on toinen asetusosio työtiloista vuokraajassa. Voit tässä osiossa lajitella ja suodattaa työtilojen luetteloja ja näyttää kunkin työtilan tiedot. Katso lisätietoja tämän artikkelin kohdasta [Työtilat](#workspaces).

**Julkaise sisältöpaketteja ja sovelluksia**

Voit hallintaportaalissa myös hallita sitä, keillä käyttäjillä on oikeus jakaa sovelluksia organisaatiossa. Katso lisätietoja tämän artikkelin kohdasta [Julkaise sisältöpaketteja ja sovelluksia koko organisaatiolle](#publish-content-packs-and-apps-to-the-entire-organization).

### <a name="use-datasets-across-workspaces"></a>Tietojoukkojen käyttö kaikissa työtiloissa

Järjestelmänvalvojat voivat hallita, ketkä organisaation käyttäjät voivat käyttää tietojoukkoja eri työtiloissa. Kun tämä asetus on käytössä, käyttäjät tarvitsevat silti tietyn tietojoukon koontiversion käyttöoikeuden.

:::image type="content" source="media/service-admin-portal/power-bi-admin-datasets-workspaces.png" alt-text="Tietojoukkojen käyttö kaikissa työtiloissa":::

Lisätietoja on artikkelissa [Johdanto tietojoukkojen käyttöön eri työtiloissa](../connect-data/service-datasets-across-workspaces.md).


## <a name="export-and-sharing-settings"></a>Vienti- ja jakamisasetukset

### <a name="share-content-with-external-users"></a>Jaa sisältöä ulkoisten käyttäjien kanssa

Organisaation käyttäjät voivat jakaa koontinäkymiä, raportteja ja sovelluksia organisaation ulkopuolisten käyttäjien kanssa. Lue lisätietoja [jakamisesta ulkoisesti](../collaborate-share/service-share-dashboards.md#share-a-dashboard-or-report-outside-your-organization).

![Ulkoiset käyttäjät -asetus](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

Seuraavassa kuvassa näet esiin tulevan ilmoituksen, kun jaat ulkoiselle käyttäjälle.

![Jaa ulkoisen käyttäjän kanssa](media/service-admin-portal/powerbi-admin-sharing-external.png)  

> [!IMPORTANT]
> Tämä asetus määrittää, voivatko Power BI -käyttäjät kutsua ulkoisia käyttäjiä Azure Active Directory B2B (Azure AD B2B) -vieraskäyttäjiksi organisaatiossasi Power BI:n kautta. Kun asetus on käytössä, käyttäjät, joilla on vieraskutsujan rooli Azure AD:ssä, voivat lisätä ulkoisia sähköpostiosoitteita jakaessaan raportteja, koontinäyttöjä ja Power BI -sovelluksia. Ulkoinen vastaanottaja kutsutaan liittymään organisaatioosi Azure AD B2B -vieraskäyttäjänä. Huomaa, että jos tämä asetus poistetaan käytöstä, organisaatioon aiemmin Azure AD B2B -vieraskäyttäjiksi lisätyt ulkoiset käyttäjät näkyvät edelleen henkilöiden valitsimen käyttöliittymissä Power BI:ssä ja heille voidaan antaa käyttöoikeudet eri kohteisiin, työtiloihin ja sovelluksiin.

### <a name="publish-to-web"></a>Julkaise verkkoon

Power BI -vuokraajan järjestelmänvalvojana **Julkaise verkkoon** -asetus tarjoaa sinulle vaihtoehtoja, joiden avulla käyttäjät voivat luoda upotuskoodeja ja julkaista niiden avulla raportteja verkossa. Tämä toiminto tuo raportin ja sen tiedot kaikkien saataville verkossa. Lue lisää [verkossa julkaisemisesta](../collaborate-share/service-publish-to-web.md).

> [!NOTE]
> Vain Power BI -järjestelmänvalvojat voivat sallia uusien Julkaise verkkoon -upotuskoodien luomisen. Organisaatioilla voi olla olemassa olevia upotuskoodeja. Voit tarkistaa parhaillaan julkaistavat raportit hallintaportaalin [Upotuskoodit](service-admin-portal.md#embed-codes)-osasta.

Seuraavassa kuvassa näkyy raportin **Lisää vaihtoehtoja (...)** -valikko, kun **Julkaise verkkoon** -asetus on käytössä.

![Lisää vaihtoehtoja -valikon Julkaise verkkoon -vaihtoehto](media/service-admin-portal/power-bi-more-options-publish-web.png)

Hallintaportaalin **Julkaise verkkoon** -asetus sisältää vaihtoehtoja upotuskoodien luomiseen.

![Julkaise verkkoon -asetus](media/service-admin-portal/powerbi-admin-publish-to-web-setting.png)

Järjestelmänvalvojat voivat määrittää, **Julkaise verkko** -asetukseksi**Käytössä**-vaihtoehdon ja **Valitse, miten upotuskoodit toimivat** -asetukseksi vaihtoehdon**Salli vain olemassa olevat upotuskoodit**. Tällöin käyttäjät voivat luoda upotuskoodeja, mutta heidän on sitä varten otettava yhteyttä Power BI -järjestelmänvalvojaan.

![Julkaise verkkoon -kehote](../collaborate-share/media/service-publish-to-web/publish_to_web_admin_prompt.png)

Käyttäjät näkevät käyttöliittymässä eri asetuksia sen mukaan, mikä heidän **Julkaise verkkoon** -asetuksensa on.

|Ominaisuus |Otettu käyttöön koko organisaatiolle |Otettu käyttöön koko organisaatiolle |Tietyt käyttöoikeusryhmät   |
|---------|---------|---------|---------|
|Raportin **Tiedosto**-valikon **Lisää vaihtoehtoja (...)** -toiminto|Käytössä kaikille|Ei näkyvissä kaikille|Näkyvissä vain valtuutetuille käyttäjille tai ryhmille.|
|**Asetukset**-valikon **Upotuskoodien hallinta**|Käytössä kaikille|Käytössä kaikille|Käytössä kaikille<br><br>* **Poista**-vaihtoehto vain valtuutetuille käyttäjille tai ryhmille.<br>* **Hae koodit** käytössä kaikille.|
|**Upotuskoodit** hallintaportaalissa|Tila ilmaisee jotain seuraavista:<br>* Aktiivinen<br>* Ei tuettu<br>* Estetty|Tilana näytetään **Ei käytössä**|Tila ilmaisee jotain seuraavista:<br>* Aktiivinen<br>* Ei tuettu<br>* Estetty<br><br>Jos käyttäjälle ei ole annettu oikeuksia vuokraaja-asetuksissa, tilana näytetään **Loukannut**.|
|Aiemmin luodut julkaistut raportit|Kaikki käytössä|Kaikki poissa käytöstä|Raportit näytetään jatkossakin kaikille.|

### <a name="export-data"></a>Vie tiedot

Organisaation käyttäjät voivat viedä tietoja ruudusta tai visualisoinnista. Tämä hallitsee Analysoi Excelissä-, Vie .csv-tiedostoon-, tietojoukkojen lataaminen (.pbix)- ja Power BI -palvelun reaaliaikainen yhteys ‑ominaisuuksia. Lue lisätietoja [tietojen viemisestä ruudusta tai visualisoinnista](../visuals/power-bi-visualization-export-data.md).

>[!NOTE]
> Ennen Vie Exceliin ‑asetuksen julkaisua tämä asetus hallitsi myös tietojen viemistä Excel-tiedostoihin. Lisätietoja on [Vie Exceliin ‑kohdan huomautuksessa](#export-to-excel).

![Vie tietoja ‑asetus](media/service-admin-portal/powerbi-admin-portal-export-data-setting.png)

Seuraavassa kuvassa näkyy tietojen vieminen ruudusta.

![Tietojen vieminen ruudusta](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Jos poistat **Vie tiedot** -toiminnon käytöstä, käyttäjät eivät voi käyttää myöskään [Analysoi Excelissä](../collaborate-share/service-analyze-in-excel.md) -toimintoa tai Power BI -palvelun reaaliaikaista yhteyttä.

### <a name="export-to-excel"></a>Vie Exceliin

Organisaation käyttäjät voivat viedä tietoja visualisoinnista Excel-tiedostoon.

![Vie Exceliin ‑asetus](media/service-admin-portal/powerbi-admin-portal-export-to-excel-setting.png)

>[!IMPORTANT]
> Ennen Vie Exceliin ‑asetuksen julkaisua Vie tietoja ‑asetus hallitsi tietojen viemistä Excel-tiedostoon. Sen vuoksi sellaisten vuokraajien järjestelmänvalvojille, jotka olivat olemassa ennen Vie Exceliin -asetuksen julkaisua, näkyy Vie Exceliin ‑asetuksen ensimmäisellä näyttökerralla *muutoksia, joita ei ole otettu käyttöön*. Järjestelmänvalvojien on otettava kyseiset muutokset käyttöön, jotta uusi asetus tulee voimaan. Muussa tapauksessa Excel-tiedostoon viemiseen sovelletaan jatkossakin Vie tietoja ‑asetusta.

### <a name="export-reports-as-powerpoint-presentations-or-pdf-documents"></a>Vie raportit PowerPoint-esityksinä tai PDF-tiedostoina

Organisaation käyttäjät voivat viedä Power BI -raportteja PowerPoint-tiedostoina tai PDF-tiedostoina. [Lisätietoja](../consumer/end-user-powerpoint.md)

Seuraavassa kuvassa näkyy raportin **Tiedosto**-valikko, kun **Vie raportit PowerPoint-esityksinä tai PDF-tiedostoina** -asetus on käytössä.

![Vie raportit PowerPoint-esityksinä](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Tulosta raporttinäkymiä ja raportteja

Organisaation käyttäjät voivat tulostaa koontinäyttöjä ja raportteja. [Lisätietoja](../consumer/end-user-print.md)

Seuraavassa kuvassa näkyy koontinäytön tulostaminen.

![Tulosta koontinäyttö](media/service-admin-portal/powerbi-admin-print-dashboard.png)

Seuraavassa kuvassa näkyy raportin **Tiedosto**-valikko, kun **Tulosta koontinäyttöjä ja raportteja** -asetus on käytössä.

![Raportin tulostaminen](media/service-admin-portal/powerbi-admin-print-report.png)

### <a name="allow-external-guest-users-to-edit-and-manage-content-in-the-organization"></a>Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa

Azure AD B2B -vieraskäyttäjät voivat muokata ja hallita sisältöä organisaatiossa. [Lisätietoja](service-admin-azure-ad-b2b.md)

Seuraava kuva näyttää asetuksen Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa.

![Salli ulkoisten vieraskäyttäjien muokata ja hallita sisältöä organisaatiossa](media/service-admin-portal/powerbi-admin-tenant-settings-b2b-guest-edit-manage.png)

Voit hallintaportaalissa myös hallita sitä, keillä käyttäjillä on oikeus kutsua ulkoisia käyttäjiä organisaatioon. Lisätietoja on artikkelissa [Jaa sisältöä ulkoisten käyttäjien kanssa](#export-and-sharing-settings).

### <a name="email-subscriptions"></a>Sähköpostitilaukset
Organisaatiosi käyttäjät voivat luoda sähköpostitilauksia. Lue lisää [tilauksista](../collaborate-share/service-publish-to-web.md).

![Ota käyttöön sähköpostitilaukset](media/service-admin-portal/power-bi-manage-email-subscriptions.png)

### <a name="featured-content"></a>Esitelty sisältö

Salli joidenkin tai kaikkien organisaatiosi raportin tekijöiden esitellä sisältöään Power BI -aloitussivun Esitelty-osiossa. Uudet käyttäjät näkevät esitellyn sisällön Power BI -aloitussivunsa yläreunassa. Esitelty sisältö siirtyy kotisivulla alaspäin sitä mukaa kun käyttäjät lisäävät **suosikkeja**, **usein käytettyjä** ja **viimeaikaisia**. 

Suosittelemme aloittamaan pienellä joukolla vetäjiä. Jos annetaan koko organisaation esitellä sisältöä kotisivulla, voi olla vaikeaa seurata kaikkea ylennettyä sisältöä. 

Kun olet ottanut käyttöön esitellyn sisällön, voit hallita sitä myös järjestelmänvalvojan portaalissa. Katso tästä artikkelista kohtaa [Esitellyn sisällön hallinta](#manage-featured-content), kun haluat lisätietoja toimialasi esitellyn sisällön hallinnasta.

## <a name="content-pack-and-app-settings"></a>Sisältöpaketin ja sovelluksen asetukset

### <a name="publish-content-packs-and-apps-to-the-entire-organization"></a>Julkaise sisältöpaketteja ja sovelluksia koko organisaatiolle

Järjestelmänvalvojat voivat tämän asetuksen avulla päättä, ketkä käyttäjät voivat julkaista sisältöpaketteja ja sovelluksia koko organisaatiolle vain tietyille ryhmille julkaisemisen sijasta. Lue lisää [sovellusten julkaisemisesta](../collaborate-share/service-create-distribute-apps.md).

Seuraavassa kuvassa näkyy **Koko organisaatio** -vaihtoehto sisältöpaketin luomisessa.

![Sisältöpaketin julkaiseminen organisaatiolle](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-apps-and-organizational-content-packs"></a>Luo mallisovelluksia ja organisaation sisältöpaketteja

Organisaation käyttäjät voivat luoda mallisovelluksia ja organisaation sisältöpaketteja, jotka käyttävät yhteen tietolähteeseen perustuvia tietojoukkoja Power BI Desktopissa. Lue lisää [mallisovelluksista](../template-content-pack-authoring.md).

### <a name="push-apps-to-end-users"></a>Lähetä sovellukset käyttäjille

Raporttien luojat voivat jakaa sovelluksia suoraan käyttäjien kanssa ilman asennusta [AppSourcesta](https://appsource.microsoft.com). Lue lisää [sovellusten automaattisesta asentamisesta loppukäyttäjille](../collaborate-share/service-create-distribute-apps.md#automatically-install-apps-for-end-users).

## <a name="integration-settings"></a>Integrointiasetukset

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Analysoi Excelissä -toiminnon käyttäminen paikallisten tietojoukkojen kanssa

Organisaation käyttäjät voivat käyttää paikallisia Power BI -tietojoukkoja Excelillä. [Lisätietoja](../collaborate-share/service-analyze-in-excel.md)

> [!NOTE]
> Jos poistat **Vie tiedot** -toiminnon käytöstä, estät käyttäjiä käyttämästä myös **Analysoi Excelissä** -toimintoa.

### <a name="use-arcgis-maps-for-power-bi"></a>ArcGIS Maps for Power BI:n käyttäminen

Organisaation käyttäjät voivat käyttää Esrin tarjoamaa ArcGIS Maps for Power BI -visualisointia. [Lisätietoja](../visuals/power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Power BI:n yleisen haun käyttäminen (esikatselu)

Organisaation käyttäjät voivat käyttää Azure-hausta riippuvaisia ulkoisia hakutoimintoja.

## <a name="power-bi-visuals-settings"></a>Power BI -visualisointien asetukset

### <a name="add-and-use-power-bi-visuals"></a>Power BI -visualisointien lisääminen ja käyttäminen

Organisaation käyttäjät voivat käyttää Power BI -visualisointeja ja jakaa niitä. [Lisätietoja](../developer/visuals/power-bi-custom-visuals.md)

> [!NOTE]
> Tämä asetus voidaan ulottaa koskemaan koko organisaatiota tai rajoittaa määrättyihin ryhmiin.

Power BI Desktop (alkaen maaliskuun 2019 julkaisusta) tukee **ryhmäkäytäntöä** Power BI -visualisointien poistamiseksi käytöstä organisaation käyttöön otetuilla tietokoneilla.

<table>
<tr><th>Määrite</th><th>Arvo</th>
</tr>
<td>avain</td>
    <td>Software\Policies\Microsoft\Power BI Desktop\</td>
<tr>
<td>valueName</td>
<td>EnableCustomVisuals</td>
</tr>
</table>

Arvo 1 (desimaalimuotoinen) ottaa käyttöön Power BI -visualisoinnit Power BI:ssä (tämä on oletusarvo).

Arvo 0 (desimaalimuotoinen) poistaa käytöstä Power BI -visualisoinnit Power BI:ssä.

### <a name="allow-only-certified-visuals"></a>Salli vain sertifioidut visualisoinnit

Organisaation käyttäjät, joille on annettu oikeudet lisätä ja käyttää Power BI -visualisointeja ”Lisää ja käytä Power BI -visualisointeja” -asetuksen mukaisesti, saavat käyttää ainoastaan [sertifioituja Power BI -visualisointeja](https://go.microsoft.com/fwlink/?linkid=2002010) (sertifioimattomat visualisoinnit estetään ja käyttöyritys johtaa virheilmoitukseen). 


Power BI Desktop (alkaen maaliskuun 2019 julkaisusta) tukee **ryhmäkäytäntöä** sertifioimattomien Power BI -visualisointien poistamiseksi käytöstä organisaation käyttöön otetuilla tietokoneilla.

<table>
<tr><th>Määrite</th><th>Arvo</th>
</tr>
<td>avain</td>
    <td>Software\Policies\Microsoft\Power BI Desktop\</td>
<tr>
<td>valueName</td>
<td>EnableUncertifiedVisuals</td>
</tr>
</table>

Arvo 1 (desimaalimuotoinen) ottaa käyttöön sertifioimattomat Power BI -visualisoinnit Power BI:ssä (tämä on oletusarvo).

Arvo 0 (desimaalimuotoinen) poistaa käytöstä sertifioimattomat Power BI -visualisoinnit Power BI:ssä (tämä asetus sallii vain [sertifioidut Power BI -visualisoinnit](https://go.microsoft.com/fwlink/?linkid=2002010)).

## <a name="r-visuals-settings"></a>R-visualisointien asetukset

### <a name="interact-with-and-share-r-visuals"></a>Tee toimia R-visualisointien kanssa ja jaa niitä

Organisaation käyttäjät voivat käyttää R-komentosarjoilla luotuja visualisointeja ja jakaa niitä. [Lisätietoja](../visuals/service-r-visuals.md)

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="audit-and-usage-settings"></a>Valvonta- ja käyttöasetukset

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Valvontalokien luominen sisäisen toiminnan valvonnan ja vaatimustenmukaisuuden tarpeisiin

Organisaation käyttäjät voivat valvoa muiden käyttäjien Power BI:ssä tekemiä toimia. [Lisätietoja](service-admin-auditing.md)

Tämän asetuksen täytyy olla käytössä, jotta valvontalokiin kirjataan merkintöjä. Valvonnan käyttöönoton ja valvontatietojen tarkastelumahdollisuuden välillä voi olla jopa 48 tunnin viive. Jos et näe tietoja välittömästi, tarkista valvontalokit myöhemmin. Jos haet oikeuksia hallintalokien tarkasteluun, samanlainen viive voi esiintyä, ennen kuin oikeudet on myönnetty.

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

### <a name="usage-metrics-for-content-creators"></a>Käyttötiedot sisällöntekijöille

Organisaation käyttäjät voivat tarkastella luomiensa koontinäyttöjen ja raporttien käyttötietoja. [Lisätietoja](../collaborate-share/service-usage-metrics.md)

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>Käyttäjäkohtaiset tiedot sisällöntekijöille tarkoitetuissa käyttötiedoissa

Sisällöntekijöille tarkoitetut käyttötiedot paljastavat sisällön käyttäjien näyttönimet ja sähköpostiosoitteet. [Lisätietoja](../collaborate-share/service-usage-metrics.md)

Oletusarvoisesti käyttäjäkohtaiset tiedot on otettu käyttöön käyttötiedoille ja sisällöntekijän tilitiedot sisältyvät tietoraporttiin. Jos et halua kerätä näitä tietoja kaikille käyttäjille, voit poistaa ominaisuuden käytöstä määritetyille käyttöoikeusryhmille tai koko organisaatiolle. Tilitiedot näkyvät sitten raportissa pois jätetyille käyttäjille *nimettöminä*.

## <a name="dashboard-settings"></a>Koontinäytön asetukset

### <a name="data-classification-for-dashboards"></a>Koontinäyttöjen tietojen luokittelu

Organisaation käyttäjät voivat merkitä koontinäyttöjä luokituksilla, jotka ilmaisevat koontinäyttöjen suojaustasoja. [Lisätietoja](../create-reports/service-data-classification.md)

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="developer-settings"></a>Kehittäjäasetukset

### <a name="embed-content-in-apps"></a>Sisällön upottaminen sovelluksiin

Organisaation käyttäjät voivat upottaa Power BI -koontinäyttöjä ja -raportteja SaaS-sovelluksiin (palveluina tarjottaviin sovelluksiin). Jos poistat tämän asetuksen käytöstä, käyttäjät eivät näe REST-ohjelmointirajapintoja, joilla he voivat upottaa Power BI -sisältöä sovelluksiin. [Lisätietoja](../developer/embedded/embedding.md)

### <a name="allow-service-principals-to-use-power-bi-apis"></a>Salli palvelun päänimien käyttää Power BI -ohjelmointirajapintoja

Azure Active Directoryyn (Azure AD) rekisteröidyt verkkosovellukset käyttävät määritettyä palvelun päänimeä Power BI -ohjelmointirajapintojen käyttöön ilman sisäänkirjautunutta käyttäjää. Jotta sovellus voi käyttää todennustyyppinä palvelun päänimeä, sen palvelun päänimen on sisällyttävä sallittuun käyttöoikeusryhmään. [Lisätietoja](../developer/embedded/embed-service-principal.md)

> [!NOTE]
> Palvelun päänimet perivät käyttöoikeudet kaikkiin Power BI -vuokraaja-asetuksiin käyttöoikeusryhmästään. Jos haluat rajoittaa käyttöoikeuksia, luo erillinen käyttöoikeusryhmä palvelun päänimille ja lisää se asianmukaisten käyttöön otettujen Power BI -asetusten Lukuun ottamatta tiettyjä käyttöoikeusryhmiä -luetteloon.

## <a name="dataflow-settings"></a>Tietovuon asetukset

### <a name="create-and-use-dataflows"></a>Tietovoiden luominen ja käyttäminen

Organisaatiosi käyttäjät voivat luoda ja käyttää tietovoita. Saat yleiskatsauksen tietovoista artikkelista [Omatoiminen tietojen valmistelu Power BI:ssä](../transform-model/service-dataflows-overview.md). Jos haluat ottaa tietovuot käyttöön Premium-kapasiteetissa, tutustu artikkeliin [Kuormitusten määrittäminen](service-admin-premium-workloads.md).

> [!NOTE]
> Tämä asetus koskee koko organisaatiota, joten sitä ei rajoittaa ryhmien avulla.

## <a name="template-apps-settings"></a>Mallisovellusten asetukset

Kolme asetusten hallinnan mallisovelluksen kyky julkaista tai asentaa mallisovelluksia.

![Power BI -hallintaportaalin mallisovellusten asetukset](media/service-admin-portal/power-bi-admin-portal-template-apps.png)

### <a name="publish-template-apps"></a>Julkaise mallisovellukset

Organisaation käyttäjät voivat luoda mallisovellusten työtiloja. Ohjausobjekti, jonka avulla käyttäjät voivat julkaista mallisovelluksia tai jakaa niitä organisaatiosi ulkopuolisille asiakkaille [AppSourcen](https://appsource.microsoft.com) tai jonkin muun jakelumenetelmän kautta.

![Power BI -hallintaportaali, Luo mallisovelluksia -asetus](media/service-admin-portal/power-bi-admin-portal-template-app-settings.png)

### <a name="install-template-apps-listed-on-appsource"></a>Asenna AppSourcessa luetellut mallisovellukset

Organisaation käyttäjät voivat ladata ja asentaa mallisovelluksia mallin **vain**[AppSourcesta](https://appsource.microsoft.com). Ohjausobjekti, jonka avulla tietyt käyttäjät tai käyttöoikeusryhmät voivat asentaa mallisovelluksia AppSourcesta.

![Power BI -hallintaportaali, Asenna mallisovelluksia -asetus](media/service-admin-portal/power-bi-admin-portal-template-app-settings-installer-appsource.png)

### <a name="install-template-apps-not-listed-on-appsource"></a>Asenna mallisovellukset, joita ei ole lueteltu AppSourcessa

Ohjausobjekti, jonka avulla organisaation käyttäjät voivat ladata ja asentaa mallisovelluksia, **joita ei ole lueteltu [AppSourcessa](https://appsource.microsoft.com)** .

![Power BI -hallintaportaali, Asenna mallisovelluksia -asetus](media/service-admin-portal/power-bi-admin-portal-template-app-settings-installer-nonappsource.png)

## <a name="capacity-settings"></a>Kapasiteettiasetukset

### <a name="power-bi-premium"></a>Power BI Premium

**Power BI Premium** -välilehdessä voit hallita mitä tahansa organisaatiollesi ostettua Power BI Premium -kapasiteettia (EM- tai P-varastointiyksikkö). Kaikki organisaation käyttäjät näkevät **Power BI Premium** -asetusten välilehden, mutta sen sisällön näkevät vain käyttäjät, joilla on *kapasiteetin järjestelmänvalvojan* oikeudet tai määrityskäyttöoikeudet. Jos käyttäjällä ei ole mitään oikeuksia, näyttöön tulee seuraava ilmoitus.

![Ei Premium-asetusten käyttöoikeutta](media/service-admin-portal/premium-settings-no-access.png)

### <a name="power-bi-embedded"></a>Power BI Embedded

**Power BI Embedded** -välilehden avulla voit tarkastella Power BI Embedded (A-varastointiyksikkö) -kapasiteetteja, jotka olet ostanut asiakkaalle. Koska voit ostaa A-varastointiyksikköjä vain Azuresta, voit [hallita Azuren upotettuja kapasiteetteja](../developer/embedded/azure-pbie-create-capacity.md)**Azure-portaalista**.

Lisätietoja siitä, miten voit hallita Power BI Embedded (A-varastointiyksikkö) -asetuksia, on artikkelissa [Mikä on Power BI Embedded](../developer/embedded/azure-pbie-what-is-power-bi-embedded.md).

## <a name="embed-codes"></a>Upotuskoodit

Järjestelmänvalvojana voit tarkastella vuokraajatilillesi raporttien julkista jakamista varten luotuja upotuskoodeja. Voit myös kumota tai poista koodeja. [Lisätietoja](../collaborate-share/service-publish-to-web.md)

![Upotuskoodit Power BI -hallintaportaalissa](media/service-admin-portal/embed-codes.png)

 ## <a name=""></a><a name="organizational-visuals">Organisaation visualisoinnit.</a> 

**Organisaation visualisoinnit** -välilehden avulla voit ottaa käyttöön ja hallita organisaatiosi Power BI -visualisointeja. Organisaation visualisointien avulla voit helposti käyttää omia visualisointeja organisaatiossa, ja raporttien tekijät voivat sitten hakea ja tuoda niitä raportteihinsa Power BI Desktopista. [Lisätietoja](../developer/visuals/power-bi-custom-visuals-organization.md)

> [!WARNING]
> Mukautettu visualisointi voi sisältää koodia, jolla on tietoturva- tai tietosuojariskejä. Varmista siis, että luotat mukautetun visualisoinnin tekijään ja lähteeseen, ennen kuin otat sen käyttöön organisaation säilössä.

Seuravasta kuvasta näet kaikki Power BI -visualisoinnit, jotka on tällä hetkellä otettu käyttöön organisaation säilössä.

![Organisaation järjestelmänvalvojan visualisointi](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Uuden mukautetun visualisoinnin lisääminen

Jos haluat lisätä luetteloon uuden mukautetun visualisoinnin, toimi seuraavasti. 

1. Valitse oikeanpuoleisessa ruudussa **Lisää mukautettu visualisointi**.

    ![Power BI:n visualisointien lomake](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

1. Täytä **Mukautetun visualisoinnin lisääminen** -lomake:

    * **Valitse .pbiviz-tiedosto** (pakollinen): valitse ladattava mukautetun visualisoinnin tiedosto. Vain versioituja ohjelmointirajapinnan Power BI -visualisointeja tuetaan (lue täältä lisätietoja siitä, mitä tämä tarkoittaa).

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

Saat lisätietoja [organisaation Power BI -visualisointien usein kysytyistä kysymyksistä](../developer/visuals/power-bi-custom-visuals-faq.md#organizational-power-bi-visuals)

## <a name=""></a><a name="dataflowStorage">Tietovuon tallennustila (esikatselu)</a>

Oletusarvon mukaan Power BI:ssä käytetyt tiedot tallennetaan Power BI:n tarjoamaan sisäiseen tallennustilaan. Tietovoiden ja Azure Data Lake Storage Gen2 (ADLS Gen2) -järjestelmän integroinnin myötä voit tallentaa tietovuot organisaatiosi Azure Data Lake Storage Gen2 -tilille. Lisätietoja on kohdassa [Tietovuot ja Azure Data Lake -integrointi (esikatselu)](../transform-model/service-dataflows-azure-data-lake-integration.md).

## <a name="workspaces"></a>Työtilat

Järjestelmänvalvojana voit tarkastella vuokraajassa olevia työtiloja. Voit lajitella ja suodattaa työtilojen luetteloja ja näyttää kunkin työtilan tiedot. Taulukon sarakkeet vastaavat [Power BI -järjestelmänvalvojan REST-ohjelmointirajapinnan](/rest/api/power-bi/admin) palauttamia ominaisuuksia työtiloille. Henkilökohtaiset työtilat ovat tyyppiä **PersonalGroup**, perinteiset työtilat tyyppiä **Group** ja uuden työtilakokemuksen työtilat tyyppiä **Workspace**. Lisätietoja on kohdassa [Työn järjestäminen uusiin työtiloihin](../collaborate-share/service-new-workspaces.md).

Järjestelmänvalvojat voivat myös hallita ja palauttaa työtiloja käyttämällä joko hallintaportaalia tai PowerShellin CmdLet-komentoja. 

![Työtilojen luettelo](media/service-admin-portal/workspaces-list.png)

**Työtilat**-välilehdessä näkyy jokaisen työtilan *tila*. Seuraavassa taulukossa on lisätietoja näiden tilojen merkityksestä.

|Osavaltio  |Kuvaus  |
|---------|---------|
| Aktiivinen | Normaali työtila. Tämä ei kerro mitään käytöstä tai sisällöstä, vaan vain sen, että työtila itsessään on ”normaali”. |
| Yhteydetön | Työtila, jolla ei ole järjestelmänvalvojakäyttäjää. |
| Poistettu | Poistettu työtila. Metatietoja säilytetään riittävä määrä enintään 90 päivän ajan, jotta työtila voidaan palauttaa tarvittaessa. |
| Poistetaan | Työtila, jota ollaan poistamassa, mutta jota ei vielä ole poistettu. Käyttäjät voivat poistaa omat työtilansa, jolloin ne siirtyvät Poistetaan- tai Poistettu-tilaan. |

## <a name="custom-branding"></a>Mukautus

Järjestelmänvalvojana voit mukauttaa Power BI:n ulkoasua koko organisaatiolle. Tällä hetkellä on kolme päävaihtoehtoa:

![Mukautusvaihtoehdot](media/service-admin-portal/power-bi-custom-branding.png)

* **Lataa logo**: Saat parhaat tulokset lataamalla logon, joka on tallennettu muodossa .png, joka on kooltaan enintään 10 Kt ja joka on vähintään 200 x 30 kuvapistettä.

* **Lataa kansikuva**: Saat parhaat tulokset lataamalla kansikuvan, joka on tallennettu muodossa .jpg tai .png, joka on kooltaan enintään 1 Mt ja joka on vähintään 1 920 x 160 kuvapistettä.

* **Valitse teeman väri**: Voit valita teeman heksakoodin tai RGB-arvon perusteella, tai voit valita sen annetusta värivalikoimasta.


Katso lisätietoja artikkelista [Organisaation mukautus](https://aka.ms/orgBranding).

![Työtilojen luettelo](media/service-admin-portal/workspaces-list.png)

## <a name="manage-featured-content"></a>Esitellyn sisällön hallinta

Vuokraajan järjestelmänvalvojana voit hallita kaikkia raportteja, koontinäyttöjä ja sovelluksia, jotka on ylennetty Esitellyt-osioon Power BI -aloitussivulle koko organisaatiossasi.

- Valitse hallintaportaalissa **Esitelty sisältö**.

Tässä näet yleiskatsauksen siitä, kuka esitteli sisällön ja milloin se esiteltiin, sekä kaikki sen oleelliset metatiedot. Jos jokin vaikuttaa epäilyttävältä tai jos haluat tyhjentää Esitellyt-osion, voit tarpeen mukaan poistaa ylennetyn sisällön.

Katso tämän artikkelin kohdasta [Esitelty sisältö](#featured-content) lisätietoja esitellyn sisällön käyttöönotosta.

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI:n hallinta organisaatiossa](service-admin-administering-power-bi-in-your-organization.md)  
[Power BI -järjestelmänvalvojaroolin kuvaus](service-admin-role.md)  
[Organisaation Power BI:n valvonta](service-admin-auditing.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)




