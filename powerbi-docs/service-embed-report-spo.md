---
title: Upota raportin verkko-osa SharePoint Onlinessa
description: Power BI:n uuden, SharePoint Onlineen tarkoitetun raportin verkko-osan avulla voit helposti upottaa vuorovaikutteisia Power BI -raportteja SharePoint Onlinen sivuille.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/19/2017
ms.author: maghan
LocalizationGroup: Share your work
ms.openlocfilehash: 11b1d2c1c5205fd1346e9350b0a814b7d76d4135
ms.sourcegitcommit: 85d18d9f11a4ce4d4ed65e4544d13da6c2d9b1d4
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/08/2018
ms.locfileid: "30816019"
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>Upota raportin verkko-osa SharePoint Onlinessa

Power BI:n uuden, SharePoint Onlineen tarkoitetun raportin verkko-osan avulla voit helposti upottaa vuorovaikutteisia Power BI -raportteja SharePoint Onlinen sivuille.

Kun käytetään uutta **Upota SharePoint Onlinessa** -asetusta, upotetut raportit ovat täysin suojattuja, jotta voit helposti luoda suojattuja sisäisiä portaaleja.

## <a name="requirements"></a>Vaatimukset

**Upota SharePoint Onlinessa** -raporttien käyttöön liittyy joitakin vaatimuksia.

* Power BI -verkko-osa SharePoint Onlineen edellyttää [moderneja sivuja](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b).

## <a name="embed-your-report"></a>Upota raportti

Voit upottaa raporttisi SharePoint Onlinessa hankkimalla ensin raportin URL-osoitteen ja käyttämällä sitten URL-osoitetta uuden Power BI -verkko-osan kanssa SharePoint Onlinessa.

### <a name="get-a-url-to-your-report"></a>Hanki raportin URL-osoite

1. Näytä raportti Power BI -palvelussa.

2. Valitse **Tiedosto**-valikkokohde.

3. Valitse **Upota SharePoint Onlinessa**.
   
    ![](media/service-embed-report-spo/powerbi-file-menu.png)

4. Kopioi URL-osoite valintaikkunasta.

    ![](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

   > [!NOTE]
   > Voit käyttää myös selaimen osoiterivillä raportin tarkastelun aikana näkyvää URL-osoitetta. Kyseinen URL-osoite sisältää parhaillaan tarkastelemasi raporttisivun. Poista raporttiosa URL-osoitteesta, jos haluat käyttää eri sivua.

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Lisää Power BI -raportti SharePoint Online -sivuun

1. Avaa haluamasi sivu SharePoint Onlinessa ja valitse **Muokkaa**.

    ![](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    Voit halutessasi luoda uuden modernin sivuston sivun valitsemalla **+ Uusi** SharePoint Onlinessa.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. Valitse **+** ja valitse **Power BI** -verkko-osa.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. Valitse **Lisää raportti**.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)

4. Liitä raportin URL-osoite ominaisuusruutuun. Tämä on aiemmassa vaiheessa kopioitu URL-osoite. Raportti latautuu automaattisesti.

    ![](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. Valitse **Julkaise**, jotta muutos näkyy SharePoint Onlinen käyttäjille.

    ![](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="granting-access-to-reports"></a>Raporttien käyttöoikeuksien myöntäminen

Kun raportti upotetaan SharePoint Onlineen, käyttäjät eivät saa automaattisesti raportin katseluoikeutta. Raportin katseluoikeudet määritetään Power BI -palvelussa.

> [!IMPORTANT]
> Katso Power BI -palvelussa, kuka saa nähdä raportin, ja myönnä käyttöoikeudet niille, jotka eivät ole luettelossa.

Raportin käyttöoikeuden voi myöntää kahdella tavalla Power BI -palvelussa. Jos käytät Office 365 -ryhmää SharePoint Online -työryhmäsivuston luomiseen, lisää käyttäjä Power BI -palvelun sovellustyötilan jäseneksi. Näin voit varmistaa, että käyttäjät voivat tarkastella ryhmän sisältöä. Lisätietoja on ohjeartikkelissa [Sovelluksen luominen ja jakaminen Power BI:ssä](service-create-distribute-apps.md).

Vaihtoehtoisesti voit myöntää käyttäjille raportin käyttöoikeuden seuraavasti.

1. Lisää ruutu raportista koontinäyttöön.

2. Jaa koontinäyttö käyttäjille, jotka tarvitsevat raportin käyttöoikeudet. Jos haluat lisätietoja, katso [Koontinäytön jakaminen työtovereille ja muille](service-share-dashboards.md).

## <a name="web-part-settings"></a>Verkko-osan asetukset

Alla on kuvaus niistä SharePoint Onlinen Power BI -verkko-osan asetuksista, joita voi muuttaa.

![](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Ominaisuus | Kuvaus |
| --- | --- |
| Sivun nimi |Määrittää oletussivun, joka näkyy verkko-osassa. Valitse arvo avattavasta luettelosta. Jos sivuja ei näy, raportissasi on vain yksi sivu tai liittämäsi URL-osoite sisältää sivun nimen. Valitse tietty sivu poistamalla raporttiosa URL-osoitteesta. |
| Näytä |Voit valita, miten raportti sovitetaan SharePoint Online -sivulle. |
| Näytä siirtymisruutu |Näyttää tai piilottaa sivun siirtymisruudun. |
| Näytä suodatusruutu |Näyttää tai piilottaa suodatusruudun. |

## <a name="multi-factor-authentication"></a>Monimenetelmäinen todentaminen

Jos Power BI -ympäristösi edellyttää kirjautumista monimenetelmäistä todentamista käyttäen, sinua voidaan pyytää kirjautumaan suojauslaitteelta henkilöllisyytesi varmistamiseksi. Näin tapahtuu, jos et kirjautunut SharePoint Onlineen monimenetelmäistä todentamista käyttäen, mutta Power BI -ympäristösi vaatii suojauslaitteella vahvistettua tiliä.

> [!NOTE]
> Monimenetelmäistä todentamista ei vielä tueta Azure Active Directory 2.0 -versiossa. Käyttäjät näkevät viestin, jossa lukee *virhe*. Jos käyttäjä kirjautuu uudelleen SharePoint Onlineen suojauslaitetta käyttäen, hän saattaa nähdä raportin.

## <a name="reports-that-do-not-load"></a>Raportit, joiden lataaminen ei onnistu

Raporttisi ei välttämättä lataudu Power BI -verkko-osaan, jolloin näet seuraavan viestin.

*Tämä sisältö ei ole käytettävissä.*

![](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Tähän viestiin on kaksi yleistä syytä.

1. Sinulla ei ole raportin käyttöoikeuksia.
2. Raportti on poistettu.

Yritä ratkaista ongelma ottamalla yhteyttä SharePoint Online -sivun omistajaan.

## <a name="known-issues-and-limitations"></a>Tunnetut ongelmat ja rajoitukset

* **Virhe: ”Ilmeni virhe, kirjaudu ulos ja uudelleen sisään ja yritä avata tämä sivu uudelleen. Korrelaatiotunnus: määrittämätön, HTTP-vastauksen tila: 400, palvelimen virhekoodi 10001, viesti: päivitystunnus puuttuu”**
  
  Jos saat tämän virheviestin, yritä jotakin seuraavista.
  
  1. Kirjaudu ulos SharePointista ja kirjaudu uudelleen sisään. Muista sulkea kaikki selainikkunat, ennen kuin kirjaudut uudelleen sisään.

  2. Jos käyttäjätilisi edellyttää monimenetelmäistä todentamista (MFA), kirjaudu sisään SharePointiin käyttäen monimenetelmäisen todentamisen laitetta (esim. puhelinsovellus, älykortti).

* Power BI ei tue samoja lokalisoituja kieliä kuin SharePoint Online. Sen vuoksi et välttämättä näe oikeaa lokalisointia upotetussa raportissa.

* Ongelmia saattaa ilmetä, jos käytät Internet Explorer 10:tä. Voit tarkastella [Power BI:n](service-browser-support.md) ja [Office 365:n](https://products.office.com/office-system-requirements#Browsers-section) tuettuja selaimia.

* Power BI -verkko-osa ei ole käytettävissä [kansallisissa pilvipalveluissa](https://powerbi.microsoft.com/en-us/clouds/). 

## <a name="next-steps"></a>Seuraavat vaiheet

[Modernin sivuston sivujen luomisen salliminen tai estäminen käyttäjille](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
[Sovelluksen luominen ja jakaminen Power BI:ssä](service-create-distribute-apps.md)  
[Koontinäytön jakaminen työtovereille ja muille](service-share-dashboards.md)  
[Power BI Premium – mikä se on?](service-premium.md)  

Ilmenikö muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/) 
