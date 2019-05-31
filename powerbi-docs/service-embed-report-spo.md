---
title: Upota raportin verkko-osa SharePoint Onlinessa
description: Power BI:n uuden, SharePoint Onlineen tarkoitetun raportin verkko-osan avulla voit helposti upottaa vuorovaikutteisia Power BI -raportteja SharePoint Onlinen sivuille.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 05/16/2019
ms.openlocfilehash: c8789d47ed1b67f9fd6808865514120457a29dfe
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051280"
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>Upota raportin verkko-osa SharePoint Onlinessa

Power BI:n uuden, SharePoint Onlineen tarkoitetun raportin verkko-osan avulla voit helposti upottaa vuorovaikutteisia Power BI -raportteja SharePoint Onlinen sivuille.

Kun käytetään uutta **Upota SharePoint Onlinessa** asetusta, upotetut raportit ovat täysin suojattuja, jotta voit helposti luoda suojattuja sisäisiä portaaleja.

## <a name="requirements"></a>Vaatimukset

- **Upota SharePoint Onlinessa** raporttien käyttöön, seuraavat vaaditaan:

* Power BI Pro-käyttöoikeus tai [Power BI Premium-kapasiteetti (EM tai P-Varastointiyksikköä)](service-premium-what-is.md) ja Power BI-käyttöoikeus.
* Power BI -verkko-osa SharePoint Onlineen edellyttää [moderneja sivuja](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b).

## <a name="embed-your-report"></a>Upota raportti
Jos haluat upottaa raporttisi SharePoint Onlineen, sinun on raportin URL-osoite ja käyttää sitä SharePoint Onlinen uuden Power BI-verkko-osan.

### <a name="get-a-report-url"></a>Hanki raportin URL-osoite

1. Tarkastele raporttia Power BI sisällä.

2. Valitse **tiedoston** valikosta, valitse **Upota SharePoint Onlinessa**.

    ![Tiedosto-valikko](media/service-embed-report-spo/powerbi-file-menu.png)

3. Kopioi raportin URL-osoite valintaikkunasta.

    ![Upota linkki](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Lisää Power BI -raportti SharePoint Online -sivuun

1. Avaa kohdesivu SharePoint Onlinessa ja valitse **Muokkaa**.

    ![SP: muokkaussivu](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    Tai Sharepoint Onlineen, valitse **+ uusi** luoda uuden modernin sivuston sivun.

    ![SP: uusi sivu](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. Valitse **+** avattava valikko ja valitse sitten **Power BI**.

    ![SP: uusi verkko-osa](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. Valitse **Lisää raportti**.

    ![SP: uusi raportti](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)  

4. Liitä aiemmin kopioitu raportin URL-osoite **Power BI-Raporttilinkki** ruudussa. Raportti latautuu automaattisesti.

    ![SP: uuden verkko-osan ominaisuudet](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. Valitse **Julkaise**, jotta muutos näkyy SharePoint Onlinen käyttäjille.

    ![SP: raportti ladattu](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="grant-access-to-reports"></a>Raporttien käyttöoikeuksien myöntäminen

Raportin upottaminen SharePoint Onlinessa ei automaattisesti antaa käyttäjille oikeuden raportin – sinun on asetettava tarkasteluoikeuksia Power BI.

> [!IMPORTANT]
> Katso Power BI -palvelussa, kuka saa nähdä raportin, ja myönnä käyttöoikeudet niille, jotka eivät ole luettelossa.

Power BI-raportin käyttöoikeuden kahdella eri tavalla. Ensimmäinen tapa, jos käytät Office 365-ryhmä SharePoint Online-työryhmäsivuston luomiseen, Lisää jäsen käyttäjä on **Power BI-palvelun sovellustyötilan** ja **SharePoint-sivuun**. Jos haluat lisätietoja, katso, miten voit [hallita sovelluksen työtilaa](service-manage-app-workspace-in-power-bi-and-office-365.md).

Toinen tapa on sovelluksen sisällä raportin upottaminen ja jakaa sen suoraan käyttäjien kanssa:  

1. Tekijä (on oltava Pro-käyttäjä) luo raportin sovelluksen työtilassa. Jakaminen **Power BI: n maksuttoman version käyttäjien**, sovelluksen työtilan on asetettava **Premium-työtila**.

2. Tekijä julkaisee sovelluksen ja asentaa sen. Tekijä on varmistaa, että asennat sovelluksen käyttöoikeudet raportin URL-osoite, jota käytetään upottaminen SharePoint Onlineen.

3. Kaikkien loppukäyttäjien on myös nyt asennettava sovellus. Voit myös käyttää **Asenna sovellus automaattisesti** toiminto, jonka haluat ottaa [Power BI-hallintaportaalissa](service-admin-portal.md), joka on asennettu valmiiksi käyttäjille sovelluksen.

   ![Asenna sovellus automaattisesti](media/service-embed-report-spo/install-app-automatically.png)

4. Laatija avaa sovelluksen ja siirtyy raporttiin.

5. Tekijä Kopioi raportti sovellus asennettuna Upota raportin URL-osoite. **Älä käytä alkuperäisen raportin URL-osoite sovelluksen työtilasta.**

6. Luo uusi työryhmäsivusto SharePoint Onlinessa.

7. Lisää Power BI-verkko-osa aiemmin kopioitu raportin URL-osoite.

8. Lisää kaikki loppukäyttäjät ja/tai ryhmät, jotka käyttävät tietoja SharePoint Online -sivulla ja Power BI -sovelluksessa, jonka olet luonut.

    > [!NOTE]
    > **Käyttäjien tai ryhmien on saatava käyttöoikeus sekä SharePoint Online -sivulle että Power BI -sovellukseen, jotta ne näkevät raportin SharePoint-sivulla.**

Loppukäyttäjä voi nyt siirtyä työryhmäsivustolle SharePoint Onlinessa ja tarkastella raportteja sivulla.

## <a name="multi-factor-authentication"></a>Monimenetelmäinen todentaminen

Jos Power BI -ympäristösi edellyttää kirjautumista monimenetelmäistä todentamista käyttäen, sinua voidaan pyytää kirjautumaan suojauslaitteelta henkilöllisyytesi varmistamiseksi. Näin tapahtuu, jos ei Kirjaudu sisään SharePoint Onlineen käyttäen monimenetelmäistä todentamista, mutta Power BI-ympäristösi edellyttää suojauslaitetta vahvistaminen tiliä.

> [!NOTE]
> Azure Active Directory 2.0 ei tue multi-factor authentication-palvelun - käyttäjät näkevät virhesanoman. Jos käyttäjä kirjautuu uudelleen SharePoint Onlineen suojauslaitetta käyttäen, hän saattaa nähdä raportin.

## <a name="web-part-settings"></a>Verkko-osan asetukset

Alla ovat käytettävissä, voit säätää Power BI-verkko-osan SharePoint Onlineen.

![SP: verkko-osan ominaisuudet](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Ominaisuus | Kuvaus |
| --- | --- |
| Sivun nimi |Määrittää verkko-osa sivun. Valitse arvo avattavasta luettelosta. Jos sivuja ei näy, raportissasi on vain yksi sivu tai liittämäsi URL-osoite sisältää sivun nimen. Valitse tietty sivu poistamalla raporttiosa URL-osoitteesta. |
| Näytä |Määrittää, miten raportti mahtuu SharePoint Online-sivulle. |
| Näytä siirtymisruutu |Näyttää tai piilottaa sivun siirtymisruudun. |
| Näytä suodatusruutu |Näyttää tai piilottaa suodatusruudun. |

## <a name="reports-that-do-not-load"></a>Raportit, joiden lataaminen ei onnistu

Jos raportti ei lataudu Power BI-verkko-osa, saatat nähdä seuraavan sanoman:

![Tämä sisältö ei ole käytettävissä viesti](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Tähän viestiin on kaksi yleistä syytä.

1. Sinulla ei ole raportin käyttöoikeudet.
2. Raportti on poistettu.

Omistajalta SharePoint Onlinen sivun ratkaisemaan ongelman.

## <a name="licensing"></a>Käyttöoikeudet

Raporttia SharePointissa tarkastelevat käyttäjät tarvitsevat **Power BI Pro -käyttöoikeuden** tai sisällön on oltava työtilassa, joka on **[Power BI Premium -kapasiteetissa (EM- tai P-varastointiyksikkö)](service-admin-premium-purchase.md)** .

## <a name="known-issues-and-limitations"></a>Tunnetut ongelmat ja rajoitukset

* Virhe: ”Ilmeni virhe, kirjaudu ulos ja uudelleen sisään ja yritä avata tämä sivu uudelleen. Korrelaatiotunnus: määrittämätön, http-vastauksen tila: 400, palvelimen virhekoodi 10001, viesti: Päivitystunnus puuttuu”
  
  Jos saat tämän virheviestin, kokeile alla olevia vianmääritysohjeita.
  
  1. Kirjaudu ulos SharePointista ja kirjaudu uudelleen sisään. Muista sulkea kaikki selainikkunat, ennen kuin kirjaudut uudelleen sisään.

  2. Jos käyttäjätilisi edellyttää monimenetelmäisen todennuksen (MFA), kirjaudu sisään SharePointiin MFA laitteesi (esimerkiksi puhelinsovellus, älykortin) käyttämistä.
  
  3. Azuren B2B -vieraiden käyttäjätilejä ei tueta. Käyttäjät näkevät Power BI -logon, joka näyttää osan latautuvan, mutta raporttia ei näytetä.

* Power BI ei tue samoja lokalisoituja kieliä kuin SharePoint Online. Sen vuoksi et välttämättä näe oikeaa lokalisointia upotetussa raportissa.

* Ongelmia saattaa ilmetä, jos käytät Internet Explorer 10:tä. Voit tarkastella [Power BI:n](consumer/end-user-browsers.md) ja [Office 365:n](https://products.office.com/office-system-requirements#Browsers-section) tuettuja selaimia.

* Power BI -verkko-osa ei ole käytettävissä [kansallisissa pilvipalveluissa](https://powerbi.microsoft.com/clouds/).

* Perinteistä SharePoint-palvelinta ei tueta tässä verkko-osassa.

* [URL-suodattimia](service-url-filters.md) ei tueta SPO-verkko-osan kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Modernin sivuston sivujen luomisen salliminen tai estäminen käyttäjille](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
* [Sovelluksen luominen ja jakaminen Power BI:ssä](service-create-distribute-apps.md)  
* [Koontinäytön jakaminen työtovereille ja muille](service-share-dashboards.md)  
* [Mikä on Power BI Premium?](service-premium-what-is.md)
* [Raportin upottaminen turvalliseen portaaliin tai sivustoon](service-embed-secure.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)