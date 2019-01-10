---
title: Upota raportin verkko-osa SharePoint Onlinessa
description: Power BI:n uuden, SharePoint Onlineen tarkoitetun raportin verkko-osan avulla voit helposti upottaa vuorovaikutteisia Power BI -raportteja SharePoint Onlinen sivuille.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 11/01/2018
ms.openlocfilehash: 3ad4335cabac159aee38d54fbfff0f689009fd68
ms.sourcegitcommit: b3af4f7ef486c95cea173caea5a31d0472816ddd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/09/2019
ms.locfileid: "54136595"
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>Upota raportin verkko-osa SharePoint Onlinessa

Power BI:n uuden, SharePoint Onlineen tarkoitetun raportin verkko-osan avulla voit helposti upottaa vuorovaikutteisia Power BI -raportteja SharePoint Onlinen sivuille.

Kun käytetään uutta **Upota SharePoint Onlinessa** -asetusta, upotetut raportit ovat täysin suojattuja, jotta voit helposti luoda suojattuja sisäisiä portaaleja.

## <a name="requirements"></a>Vaatimukset

**Upota SharePoint Onlinessa** -raporttien käyttöön liittyy joitakin vaatimuksia.

* Tarvitset Power BI Pro -käyttöoikeuden tai [Power BI Premium -kapasiteetin (EM tai P SKU)](service-premium.md#premium-capacity-nodes) ja Power BI -käyttöoikeuden.
* Power BI -verkko-osa SharePoint Onlineen edellyttää [moderneja sivuja](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b).

## <a name="embed-your-report"></a>Upota raportti

Voit upottaa raporttisi SharePoint Onlineen hankkimalla ensin raportin URL-osoitteen ja käyttämällä sitten URL-osoitetta uuden Power BI -verkko-osan kanssa SharePoint Onlinessa.

### <a name="get-a-url-to-your-report"></a>Hanki raportin URL-osoite

1. Näytä raportti Power BI -palvelussa.

2. Valitse **Tiedosto**-valikkokohde.

3. Valitse **Upota SharePoint Onlinessa**.

    ![Tiedosto-valikko](media/service-embed-report-spo/powerbi-file-menu.png)

4. Kopioi URL-osoite valintaikkunasta.

    ![Upota linkki](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Lisää Power BI -raportti SharePoint Online -sivuun

1. Avaa haluamasi sivu SharePoint Onlinessa ja valitse **Muokkaa**.

    ![SP: muokkaussivu](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    Voit halutessasi luoda uuden modernin sivuston sivun valitsemalla **+ Uusi** SharePoint Onlinessa.

    ![SP: uusi sivu](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. Valitse **+** ja valitse **Power BI** -verkko-osa.

    ![SP: uusi verkko-osa](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. Valitse **Lisää raportti**.

    ![SP: uusi raportti](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)

4. Liitä raportin URL-osoite ominaisuusruutuun. Tämä raportin URL-osoite on aiemmassa vaiheessa kopioitu URL-osoite. Raportti latautuu automaattisesti.

    ![SP: uuden verkko-osan ominaisuudet](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. Valitse **Julkaise**, jotta muutos näkyy SharePoint Onlinen käyttäjille.

    ![SP: raportti ladattu](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="grant-access-to-reports"></a>Raporttien käyttöoikeuksien myöntäminen

Kun raportti upotetaan SharePoint Onlineen, käyttäjät eivät saa automaattisesti raportin katseluoikeutta. Raportin katseluoikeudet määritetään Power BI -palvelussa.

> [!IMPORTANT]
> Katso Power BI -palvelussa, kuka saa nähdä raportin, ja myönnä käyttöoikeudet niille, jotka eivät ole luettelossa.

Raportin käyttöoikeuden voi myöntää kahdella tavalla Power BI -palvelussa. Jos käytät Office 365 -ryhmää SharePoint Online -työryhmäsivuston luomiseen, lisää käyttäjä **Power BI -palvelun** ja **SharePoint-sivun sovellustyötilan** jäseneksi. Jos haluat lisätietoja, katso, miten voit [hallita sovelluksen työtilaa](service-manage-app-workspace-in-power-bi-and-office-365.md).

Vaihtoehtoisesti voit jakaa raportin suoraan käyttäjien kanssa upottamalla raportin sovellukseen. Voit upottaa raportin sovellukseen parin vaiheen avulla.  

1. Sovelluksen laatija on Pro-käyttäjä.

2. Laatija luo raportin sovelluksen työtilassa. Jotta sovelluksen työtila *voidaan jakaa **Power BI:n maksuttomien käyttäjien kanssa**, sovelluksen työtila on määritettävä **Premium-työtilaksi**.*

3. Laatija julkaisee sovelluksen ja sitten asentaa sen. *Tekijän on varmistettava, että sovellus on asennettu, jotta hänellä on käyttöoikeus raportin URL-osoitteeseen, jota käytetään SharePoint Onlineen upottamisessa.*

4. Kaikkien loppukäyttäjien on myös nyt asennettava sovellus. Voit kuitenkin määrittää, että loppukäyttäjät voivat esiasentaa sovelluksen **Asenna sovellus automaattisesti** -ominaisuuden avulla, joka voidaan ottaa käyttöön [Power BI -hallintaportaalissa](service-admin-portal.md).

   ![Asenna sovellus automaattisesti](media/service-embed-report-spo/install-app-automatically.png)

5. Laatija avaa sovelluksen ja siirtyy raporttiin.

6. Laatija kopioi upotetun raportin URL-osoitteen sovelluksen asentamasta raportista. *Älä käytä alkuperäisen raportin URL-osoitetta sovelluksen työtilasta.*

7. Luo uusi työryhmäsivusto SharePoint Onlinessa.

8. Lisää vaiheessa 6 kopioitu raportin URL-osoite Power BI -verkko-osaan.

9. Lisää kaikki loppukäyttäjät ja/tai ryhmät, jotka käyttävät tietoja SharePoint Online -sivulla ja Power BI -sovelluksessa, jonka olet luonut.

    > [!NOTE]
    > **Käyttäjien tai ryhmien on saatava käyttöoikeus sekä SharePoint Online -sivulle että Power BI -sovellukseen, jotta ne näkevät raportin SharePoint-sivulla.**

10. Loppukäyttäjä voi nyt siirtyä työryhmäsivustolle SharePoint Onlinessa ja tarkastella raportteja sivulla.

## <a name="multi-factor-authentication"></a>Monimenetelmäinen todentaminen

Jos Power BI -ympäristösi edellyttää kirjautumista monimenetelmäistä todentamista käyttäen, sinua voidaan pyytää kirjautumaan suojauslaitteelta henkilöllisyytesi varmistamiseksi. Näin tapahtuu, jos et kirjautunut SharePoint Onlineen monimenetelmäistä todentamista käyttäen, mutta Power BI -ympäristösi vaatii suojauslaitteella vahvistettua tiliä.

> [!NOTE]
> Monimenetelmäistä todentamista ei vielä tueta Azure Active Directory 2.0 -versiossa. Käyttäjät näkevät viestin, jossa lukee *virhe*. Jos käyttäjä kirjautuu uudelleen SharePoint Onlineen suojauslaitetta käyttäen, hän saattaa nähdä raportin.

## <a name="web-part-settings"></a>Verkko-osan asetukset

Alla on kuvaus niistä SharePoint Onlinen Power BI -verkko-osan asetuksista, joita voi muuttaa.

![SP: verkko-osan ominaisuudet](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Ominaisuus | Kuvaus |
| --- | --- |
| Sivun nimi |Määrittää oletussivun, joka näkyy verkko-osassa. Valitse arvo avattavasta luettelosta. Jos sivuja ei näy, raportissasi on vain yksi sivu tai liittämäsi URL-osoite sisältää sivun nimen. Valitse tietty sivu poistamalla raporttiosa URL-osoitteesta. |
| Näytä |Voit valita, miten raportti sovitetaan SharePoint Online -sivulle. |
| Näytä siirtymisruutu |Näyttää tai piilottaa sivun siirtymisruudun. |
| Näytä suodatusruutu |Näyttää tai piilottaa suodatusruudun. |

## <a name="reports-that-do-not-load"></a>Raportit, joiden lataaminen ei onnistu

Raporttisi ei välttämättä lataudu Power BI -verkko-osaan, jolloin näet seuraavan viestin.

*Tämä sisältö ei ole käytettävissä.*

![Raporttia ei löydy -viesti](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Tähän viestiin on kaksi yleistä syytä.

1. Sinulla ei ole raportin käyttöoikeuksia.
2. Raportti on poistettu.

Ota yhteyttä SharePoint Online -sivun omistajaan ratkaistaksesi ongelman.

## <a name="licensing"></a>Käyttöoikeudet

Raporttia SharePointissa tarkastelevat käyttäjät tarvitsevat **Power BI Pro -käyttöoikeuden** tai sisällön on oltava työtilassa, joka on **[Power BI Premium -kapasiteetissa (EM- tai P-varastointiyksikkö)](service-admin-premium-purchase.md)**.

## <a name="known-issues-and-limitations"></a>Tunnetut ongelmat ja rajoitukset

* Virhe: ”Ilmeni virhe, kirjaudu ulos ja uudelleen sisään ja yritä avata tämä sivu uudelleen. Korrelaatiotunnus: määrittämätön, http-vastauksen tila: 400, palvelimen virhekoodi 10001, viesti: Päivitystunnus puuttuu”
  
  Jos saat tämän virheviestin, kokeile alla olevia vianmääritysohjeita.
  
  1. Kirjaudu ulos SharePointista ja kirjaudu uudelleen sisään. Muista sulkea kaikki selainikkunat, ennen kuin kirjaudut uudelleen sisään.

  2. Jos käyttäjätilisi edellyttää monimenetelmäistä todentamista (MFA), kirjaudu sisään SharePointiin käyttäen monimenetelmäisen todentamisen laitetta (esim. puhelinsovellus tai älykortti).
  
  3. Azuren B2B -vieraiden käyttäjätilejä ei tueta. Käyttäjät näkevät Power BI -logon, joka näyttää osan latautuvan, mutta raporttia ei näytetä.

* Power BI ei tue samoja lokalisoituja kieliä kuin SharePoint Online. Sen vuoksi et välttämättä näe oikeaa lokalisointia upotetussa raportissa.

* Ongelmia saattaa ilmetä, jos käytät Internet Explorer 10:tä. Voit tarkastella [Power BI:n](consumer/end-user-browsers.md) ja [Office 365:n](https://products.office.com/office-system-requirements#Browsers-section) tuettuja selaimia.

* Power BI -verkko-osa ei ole käytettävissä [maakohtaisissa pilvipalveluissa](https://powerbi.microsoft.com/en-us/clouds/).

* Perinteistä SharePoint-palvelinta ei tueta tässä verkko-osassa.

* [URL-suodattimia](service-url-filters.md) ei tueta SPO-verkko-osan kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Modernin sivuston sivujen luomisen salliminen tai estäminen käyttäjille](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
* [Sovelluksen luominen ja jakaminen Power BI:ssä](service-create-distribute-apps.md)  
* [Koontinäytön jakaminen työtovereille ja muille](service-share-dashboards.md)  
* [Mikä on Power BI Premium?](service-premium.md)
* [Raportin upottaminen turvalliseen portaaliin tai sivustoon](service-embed-secure.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)