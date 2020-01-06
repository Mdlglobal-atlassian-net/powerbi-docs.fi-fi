---
title: Mallisovellusten jakaminen organisaatiossa - Power BI
description: Lue lisätietoja siitä, miten voit asentaa, mukauttaa ja jakaa mallisovelluksia organisaatiossa Power BI:n välityksellä.
author: teddybercovitz
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/14/2019
ms.author: tebercov
ms.openlocfilehash: dcb037fdf064611947719a57316f31d901e3b81d
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "73871412"
---
# <a name="install-and-distribute-template-apps-in-your-organization---power-bi"></a>Mallisovellusten asentaminen ja jakaminen organisaatiossa - Power BI

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

1. Valitse Power BI -palvelun siirtymisruudussa **Sovellukset** > **Hanki sovelluksia**.

    ![Hanki sovelluksia](media/service-template-apps-install-distribute/power-bi-get-apps-arrow.png)

2. Valitse AppSourcessa **Sovellukset**.

    ![Haku AppSourcessa](media/service-template-apps-install-distribute/power-bi-appsource.png)

3. Selaa sovellukseen tai hae sovellus ja valitse sitten **Hanki se nyt**.

4. Valitse valintaikkunassa **Asenna**.

    ![Asenna sovellus](media/service-template-apps-install-distribute/power-install-dialog.png) Jos sinulla on Power BI Pro -käyttöoikeus, sovellus asennetaan siihen liittyvän työtilan kanssa. Sovellusta mukautetaan siihen liittyvässä työtilassa.

    Kun asennus on valmis, näkyviin tulee ilmoitus, että uusi sovelluksesi on valmis.
4. Valitse **Siirry sovellukseen**.
5. Valitse **Aloita uuden sovelluksesi käyttö** -kohdassa jokin kolmesta vaihtoehdosta:

    ![Aloita sovelluksesi käyttö](media/service-template-apps-create/power-bi-template-app-get-started.png)

    - **Tarkastele sovellusta**: Mallitietojen perustarkastelua. Aloita tästä, niin saat perustuntuman sovelluksen ulkoasusta ja käytöstä. 
    - **Yhdistä tiedot**: Vaihda tietolähde mallitiedoista omaan tietolähteeseesi. Voit määrittää tietojoukon parametrit ja tietolähteen tunnistetiedot uudelleen. Katso [Tunnetut rajoitukset](service-template-apps-tips.md#known-limitations) mallisovellusten vinkkejä sisältävästä artikkelista. 
    - **Siirry työtilaan** (edistynein vaihtoehto): Voit tehdä mitä tahansa sovelluskehittäjän sallimia muutoksia.

    Voit myös ohittaa tämän valintaikkunan ja siirtyä suoraan sovellukseen liittyvään työtilaan käyttämällä siirtymisruudun **Työtilat**-vaihtoehtoa.
    >[!NOTE]
    >Mallisovelluksen asennus asentaa sekä *organisaation sovelluksen* että *työtilan*. Lue lisää [sovellusten jakamisesta Power BI:ssä](service-create-distribute-apps.md).
 
6. Ennen kuin mallisovellusta jaetaan työtovereille, kannattaa muodostaa yhteys omiin tietoihin. Haluat ehkä myös muokata raporttia tai koontinäyttöä, niin että se toimii mahdollisimman hyvin organisaatiossasi. Tässä vaiheessa voit myös lisätä muita raportteja tai raporttinäkymiä.

   Jos napsautat sellaisen sovelluksen asennuslinkkiä, jota ei ole AppSourcessa, näyttöön tulee vahvistusvalintaikkuna, joka pyytää sinua vahvistamaan valintasi.

   ![Asenna sovellus](media/service-template-apps-install-distribute/power-install-unvalidated-dialog.png)

   >[!NOTE]
   >Jotta voit asentaa mallisovelluksia, joita ei ole AppSourcessa, sinun on pyydettävä käyttöoikeudet järjestelmänvalvojaltasi. Lisätietoja on Power BI:n [hallintaportaalin kohdassa Mallisovelluksen asetukset](service-admin-portal.md#template-apps-settings).

## <a name="customize-and-publish-the-app"></a>Sovelluksen mukauttaminen ja julkaiseminen

Kun olet päivittänyt sovelluksen organisaatiotasi varten, voit julkaista sen. Vaiheet ovat samat kuin mitä tahansa sovellusta julkaistaessa.

1. Kun olet lopettanut mukauttamisen, valitse työtilan luettelonäkymän oikeasta yläkulmasta **Päivitä sovellus**.  

    ![Aloita sovelluksen asennus](media/service-template-apps-install-distribute/power-bi-start-install-app.png)

2. **Tiedot**-kohdassa voit muokata kuvausta ja taustaväriä.

   ![Määritä sovelluksen kuvaus ja väri](media/service-template-apps-install-distribute/power-bi-install-app-details.png)

3. **Siirtyminen**-kohdassa voit käyttää voit käyttää sovelluksessa uutta siirtymisen muodostinta tai valita aloitussivua varten koontinäytön tai raportin. Lisätietoja on kohdassa [Suunnittele siirtymistoiminnot](service-create-distribute-apps.md#design-the-navigation-experience).

   ![Määritä sovelluksen aloitussivu](media/service-template-apps-install-distribute/power-bi-install-app-content.png)

4. **Käyttöoikeus**-kohdassa annat käyttöoikeuden joko valituille käyttäjille tai koko organisaatiolle.  

   ![Määritä sovelluksen käyttöoikeus](media/service-template-apps-install-distribute/power-bi-install-access.png)

5. Valitse **Päivitä sovellus**. 

6. Kun sovellus on julkaistu, voit kopioida linkin ja jakaa sen käyttäjille, joille olet antanut käyttöoikeudet. Jos olet jakanut linkin käyttäjille, hekin näkevät sovelluksen AppSourcen **Oma organisaatio** -välilehdellä.

## <a name="update-a-template-app"></a>Mallisovelluksen päivittäminen

Mallisovellusten tekijät voivat julkaista mallisovellustensa uudet versiot AppSourcen tai suoran linkin kautta. Kun he tekevät tämän, voit päivittää mallisovelluksen, kun asennat sovelluksen saman tai uuden version uudelleen.

  >[!NOTE]
  >Uuden version asentaminen korvaa raportteihin ja koontinäyttöihin tekemäsi muutokset. Jos haluat säilyttää päivitetyt raporttisi ja koontinäyttösi, voit tallentaa ne eri nimellä tai eri sijaintiin ennen asentamista.

- **Korvaa olemassa oleva versio:** Korvaa olemassa olevan työtilan mallisovelluksen päivitetyllä versiolla.

   ![Mallisovelluksen päivittäminen](media/service-template-apps-install-distribute/power-bi-update-app-overwrite.png)

- **Asenna uuteen työtilaan:** Asentaa työtilan ja sovelluksen uuden version, joka on määritettävä uudelleen

### <a name="overwrite-behavior"></a>Korvaamisen toiminta

* Korvaaminen päivittää raportit, koontinäytöt ja *työtilassa* olevan tietojoukon, ei sovellusta. Korvaaminen ei muuta sovelluksen siirtymistä, asennusta ja käyttöoikeutta.
* Kun olet päivittänyt työtilan, sinun on *päivitettävä sovellus*, jotta muutokset otetaan käyttöön työtilasta organisaation sovellukseen.
* Korvaaminen säilyttää määritetyt parametrit ja todentamisen. Päivityksen jälkeen automaattinen tietojoukon päivitys alkaa. Sinä aikana organisaation sovellus, raportit ja koontinäytöt esittävät *mallitietojen* käyttökokemuksen.
  ![Mallitiedot](media/service-template-apps-install-distribute/power-bi-sample-data.png)
* Korvaaminen esittää aina mallitiedot, kunnes päivitys on valmis. Jos malli sovelluksen tekijä on tehnyt muutoksia tietojoukkoon tai parametreihin, työtilan ja sovelluksen käyttäjät voivat edelleen tarkastella *mallitietojen* käyttökokemusta.
* Korvaaminen ei koskaan poista *uusia* raportteja eikä koontinäyttöjä, jotka olet lisännyt työtilaan. Se korvaa alkuperäiset raportit ja koontinäytöt ja alkuperäisen tekijän tekemät muutokset.

>[!IMPORTANT]
>Muista [päivittää sovellus](#customize-and-publish-the-app) korvaamisen jälkeen, jotta muutokset tulevat voimaan organisaation sovelluksen käyttäjien raporteissa ja koontinäytössä.

## <a name="next-steps"></a>Seuraavat vaiheet

[Työtilojen luominen työtovereiden kanssa Power BI:ssä](service-create-workspaces.md)
