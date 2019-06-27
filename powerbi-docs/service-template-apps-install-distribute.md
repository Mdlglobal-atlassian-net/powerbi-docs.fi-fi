---
title: Mallisovellusten jakaminen organisaatiossa - Power BI (esikatselu)
description: Lue lisätietoja siitä, miten voit asentaa, mukauttaa ja jakaa mallisovelluksia organisaatiossa Power BI:n välityksellä.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/19/2019
ms.author: maggies
ms.openlocfilehash: 0671dfb324b3d66a9dee9585f94d3cb6825fb5eb
ms.sourcegitcommit: 81ba3572531cbe95ea0b887b94e91f94050f3129
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/06/2019
ms.locfileid: "66751242"
---
# <a name="install-and-distribute-template-apps-in-your-organization---power-bi-preview"></a>Mallisovellusten asentaminen ja jakaminen organisaatiossa - Power BI (esikatselu)

Oletko Power BI -analyytikko? Jos olet, tässä artikkelissa kerrotaan, miten voit asentaa *mallisovelluksia*, joiden avulla voit yhdistää moniin liiketoiminnassa käyttämiisi palveluihin. Tällaisia palveluita ovat esimerkiksi Salesforce, Microsoft Dynamics ja Google Analytics. Voit muokata raporttinäkymää ja raportteja organisaatiosi tarpeiden mukaiseksi ja jakaa ne työtovereillesi *sovelluksena*. 

![Asennetut Power BI -sovellukset](media/service-template-apps-install-distribute/power-bi-get-apps.png)

Jos olet kiinnostunut luomaan mallisovelluksia ja jakamaan niitä itse, katso [Mallisovelluksen luominen Power BI:ssä](service-template-apps-create.md). Power BI -kumppanit voivat muodostaa Power BI -sovelluksia ja ottaa ne käyttöön Power BI -asiakkaille. Koodausta tarvitaan hyvin vähän tai ei lainkaan. 

## <a name="prerequisites"></a>Edellytykset  

Mallisovelluksen asentamiseen, mukauttamiseen ja jakamiseen liittyvät seuraavat vaatimukset: 

- [Power BI Pro -käyttöoikeus](service-self-service-signup-for-power-bi.md)
- [Power BI-peruskäsitteiden](service-basic-concepts.md) tuntemus
- kelvollinen asennuslinkki mallisovelluksen luojalta tai AppSourcesta 
- oikeudet asentaa mallisovelluksia. 

## <a name="install-a-template-app"></a>Mallisovelluksen asentaminen

Saatat saada linkin mallisovellukseen. Muussa tapauksessa voit etsiä AppSourcesta mallisovelluksen, josta olet kiinnostunut. Kummassakin tapauksessa voit asentamisen jälkeen muokata mallisovellusta ja jakaa sen organisaatioosi.

### <a name="search-appsource-from-a-browser"></a>Hae AppSourcesta selaimella

Valitse selaimessa tämä linkki, niin AppSource avautuu ja Power BI -sovellukset näkyvät suodatettuina:

- https://appsource.microsoft.com/marketplace/apps?product=power-bi

### <a name="search-appsource-from-the-power-bi-service"></a>AppSource-haku Power BI -palvelusta

1. Valitse Power BI -palvelun vasemmassa siirtymisruudussa **Sovellukset** > **Hanki sovelluksia**.

    ![Hanki sovelluksia](media/service-template-apps-install-distribute/power-bi-get-apps-arrow.png)

2. Valitse AppSourcessa **Sovellukset**.

    ![Haku AppSourcessa](media/service-template-apps-install-distribute/power-bi-appsource.png)

3. Selaa sovellukseen tai hae sovellus ja valitse sitten **Hanki se nyt**.

2. Valitse valintaikkunassa **Asenna**.

    Jos sinulla on Power BI Pro -käyttöoikeus, sovellus asennetaan siihen liittyvän sovellustyötilan kanssa. Sovellusta mukautetaan siihen liittyvässä työtilassa.

    Kun asennus on valmis, näkyviin tulee ilmoitus, että uusi sovelluksesi on valmis. 

3. Valitse **Siirry sovellukseen**.
4. Valitse **Aloita uuden sovelluksesi käyttö** -kohdassa jokin kolmesta vaihtoehdosta:

    ![Aloita sovelluksesi käyttö](media/service-template-apps-create/power-bi-template-app-get-started.png)

    - **Tarkastele sovellusta**: Mallitietojen perustarkastelua. Aloita tästä, niin saat perustuntuman sovelluksen ulkoasusta ja käytöstä. 
    - **Yhdistä tiedot**: Vaihda tietolähde mallitiedoista omaan tietolähteeseesi. Voit määrittää tietojoukon parametrit ja tietolähteen tunnistetiedot uudelleen. Katso [Tunnetut rajoitukset](service-template-apps-tips.md#known-limitations) mallisovellusten vinkkejä sisältävästä artikkelista. 
    - **Siirry työtilaan** (edistynein vaihtoehto): Voit tehdä mitä tahansa sovelluskehittäjän sallimia muutoksia.

    Voit myös ohittaa tämän valintaikkunan ja siirtyä suoraan sovellukseen liittyvään työtilaan käyttämällä vasemman siirtymisruudun **Työtilat**-vaihtoehtoa.   
 
5. Ennen kuin mallisovellusta jaetaan työtovereille, kannattaa muodostaa yhteys omiin tietoihin. Haluat ehkä myös muokata raporttia tai koontinäyttöä, niin että se toimii mahdollisimman hyvin organisaatiossasi. Tässä vaiheessa voit myös lisätä muita raportteja tai raporttinäkymiä.

## <a name="update-and-distribute-the-app"></a>Sovelluksen päivittäminen ja jakaminen

Kun olet päivittänyt sovelluksen organisaatiotasi varten, voit julkaista sen. Vaiheet ovat samat kuin mitä tahansa sovellusta julkaistaessa. 

1. Kun olet lopettanut mukauttamisen, valitse työtilan luettelonäkymän oikeasta yläkulmasta **Päivitä sovellus**.  

    ![Aloita sovelluksen asennus](media/service-template-apps-install-distribute/power-bi-start-install-app.png)

2. **Tiedot**-kohdassa voit muokata kuvausta ja taustaväriä.

   ![Määritä sovelluksen kuvaus ja väri](media/service-template-apps-install-distribute/power-bi-install-app-details.png)

3. **Sisältö**-kohdassa voit valita aloitussivuksi joko koontinäytön tai raportin.

   ![Määritä sovelluksen aloitussivu](media/service-template-apps-install-distribute/power-bi-install-app-content.png)

4. **Käyttöoikeus**-kohdassa annat käyttöoikeuden joko valituille käyttäjille tai koko organisaatiolle.  

   ![Määritä sovelluksen käyttöoikeus](media/service-template-apps-install-distribute/power-bi-install-access.png)

5. Valitse **Päivitä sovellus**. 

6. Kun sovellus on julkaistu, voit kopioida linkin ja jakaa sen käyttäjille, joille olet antanut käyttöoikeudet. Jos olet jakanut linkin käyttäjille, hekin näkevät sovelluksen AppSourcen **Oma organisaatio** -välilehdellä.

## <a name="next-steps"></a>Seuraavat vaiheet 

[Työtilojen luominen työtovereiden kanssa Power BI:ssä](service-create-workspaces.md)





￼ 

 
