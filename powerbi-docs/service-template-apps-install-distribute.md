---
title: Mallisovellusten asentaminen ja jakaminen organisaatiossa - Power BI
description: Lue lisätietoja siitä, miten voit asentaa, mukauttaa ja jakaa mallisovelluksia organisaatiossa Power BI:n välityksellä.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 03/15/2020
ms.author: painbar
ms.openlocfilehash: 08aadc3027c5b265194e4239b150ea5d27fe2e43
ms.sourcegitcommit: abc8419155dd869096368ba744883b865c5329fa
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/17/2020
ms.locfileid: "79436107"
---
# <a name="install-and-distribute-template-apps-in-your-organization"></a>Mallisovellusten asentaminen ja jakaminen organisaatiossa

Oletko Power BI -analyytikko? Jos olet, tässä artikkelissa kerrotaan, miten voit asentaa [mallisovelluksia](service-template-apps-overview.md), joiden avulla voit yhdistää moniin liiketoiminnassa käyttämiisi palveluihin. Tällaisia palveluita ovat esimerkiksi Salesforce, Microsoft Dynamics ja Google Analytics. Sitten voit muokata mallisovelluksen valmiiksi luotua raporttinäkymää ja raportteja organisaatiosi tarpeiden mukaiseksi ja jakaa ne työtovereillesi [sovelluksina](consumer/end-user-apps.md). 

![Asennetut Power BI -sovellukset](media/service-template-apps-install-distribute/power-bi-get-apps.png)

Jos olet kiinnostunut luomaan mallisovelluksia itse ja jakamaan niitä organisaatiosi ulkopuolella, katso [Mallisovelluksen luominen Power BI:ssä](service-template-apps-create.md). Power BI -kumppanit voivat muodostaa Power BI -sovelluksia ja ottaa ne käyttöön Power BI -asiakkaille. Koodausta tarvitaan hyvin vähän tai ei lainkaan. 

## <a name="prerequisites"></a>Edellytykset  

Mallisovelluksen asentamiseen, mukauttamiseen ja jakamiseen tarvitset seuraavat asiat: 

* [Power BI Pro -käyttöoikeus](service-self-service-signup-for-power-bi.md)
* oikeudet asentaa mallisovelluksia vuokraajaan
* sovelluksen kelvollinen asennuslinkki, jonka saat joko AppSourcesta tai sovelluksen luojalta
* [Power BI-peruskäsitteiden](service-basic-concepts.md) hyvä tuntemus.

## <a name="install-a-template-app"></a>Mallisovelluksen asentaminen

1. Valitse Power BI -palvelun siirtymisruudussa **Sovellukset** > **Hanki sovelluksia**.

    ![Hanki sovelluksia](media/service-template-apps-install-distribute/power-bi-get-apps-arrow.png)

1. Valitse näyttöön tulevassa AppSource-ikkunassa **Sovellukset**. Selaa haluamaasi sovellukseen tai hae sovellus ja valitse sitten **Hanki se nyt**.

    ![Haku AppSourcessa](media/service-template-apps-install-distribute/power-bi-appsource.png)

1. Valitse avautuvassa valintaikkunassa **Asenna**.

    ![Asenna sovellus](media/service-template-apps-install-distribute/power-install-dialog.png)
    
    Sovellus asennetaan siihen liittyvän työtilan kanssa. **Jos päätät mukauttaa sovellusta, mukautus tehdään tässä liittyvässä työtilassa**.

    > [!NOTE]
    > Jos käytät sellaisen sovelluksen asennuslinkkiä, jota ei ole AppSourcessa, näyttöön tulee vahvistusvalintaikkuna, joka pyytää sinua vahvistamaan valintasi.
    >
    >Jotta voit asentaa mallisovelluksen, jota ei ole AppSourcessa, sinun on pyydettävä tarvittavat käyttöoikeudet järjestelmänvalvojaltasi. Lisätietoja on Power BI:n hallintaportaalin kohdassa [Mallisovelluksen asetukset](service-admin-portal.md#template-apps-settings).

    Kun asennus on valmis, ilmoitus kertoo, että uusi sovelluksesi on valmis.

    ![Siirry sovellukseen](media/service-template-apps-install-distribute/power-bi-go-to-app.png)

## <a name="connect-to-data"></a>Tietoihin yhdistäminen

1. Valitse **Siirry sovellukseen**. Näkyviin tulee **Aloita uuden sovelluksesi käyttö** -ikkuna.

   ![Aloita sovelluksesi käyttö](media/service-template-apps-install-distribute/power-bi-template-app-get-started.png)

1. Napsauta **Yhdistä**.
    
    Tämä avaa yhden tai useita valintaikkunoita, joissa voit vaihtaa tietolähteen mallitiedoista omaan tietolähteeseesi. Tämä tarkoittaa yleensä tietojoukon parametrien ja tietolähteen tunnistetietojen määrittämistä uudelleen. Katso kohta [Tunnetut rajoitukset](service-template-apps-tips.md#known-limitations).
    
    Alla olevassa esimerkissä tietoihin yhdistäminen tuo esiin kaksi valintaikkunaa.

   ![Muodosta yhteys tietojen valintaikkunoihin](media/service-template-apps-install-distribute/power-bi-template-app-connect-to-data-dialogs.png)

    Kun olet täyttänyt yhteyden valintaikkunat, yhteyden muodostamisprosessi alkaa. Ilmoituspalkissa ilmoitetaan, että tarkastelet mallitietoja.

    ![Mallitietojen tarkasteleminen](media/service-template-apps-install-distribute/power-bi-template-app-viewing-sample-data.png)

    Odota, että tietojen yhdistäminen ja päivittäminen on valmis. Edistymisen ilmaisin tietojoukon rivillä (uusi ulkoasu) tai välilehdessä (vanha ulkoasu) kertoo, milloin prosessi on valmis.

   Kun yhteyksien ja tietojen päivittäminen on valmis, päivitä selaimesi. Ilmoituspalkissa ilmoitetaan nyt, että sinun on päivitettävä sovellus, jotta voit ottaa käyttöön sovellukseen tekemäsi muutokset ja jakaa sen.

    ![Sovelluksen mukauttaminen ja jakaminen](media/service-template-apps-install-distribute/power-bi-template-app-customize-share.png)

## <a name="customize-and-share-the-app"></a>Sovelluksen mukauttaminen ja jakaminen

Kun olet päivittänyt selaimen tietojen yhdistämisen ja päivittämisen jälkeen, näet nyt sovellukseen liittyvän työtilan. Tässä vaiheessa voit muokata siellä olevia artefakteja samalla tavalla kuin missä tahansa työtilassa. Muista kuitenkin, että tekemäsi muutokset korvataan, kun päivität sovelluksen uuteen versioon, ellet tallenna muuttamiasi kohteita eri nimillä. [Katso lisätietoja korvaamisesta](#overwrite-behavior).

Lisätietoja artefaktien muokkaamisesta työtilassa on kohdassa
* [Power BI -raporttieditoriin tutustuminen](service-the-report-editor-take-a-tour.md)
* [Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

Kun olet tehnyt haluamasi muutokset työtilassa oleviin artefakteihin, olet valmis julkaisemaan ja jakamaan sovelluksen. Lisätietoja on artikkelissa [Sovelluksen julkaiseminen](service-create-distribute-apps.md#publish-your-app).

## <a name="update-a-template-app"></a>Mallisovelluksen päivittäminen

Mallisovellusten luojat julkaisevat ajoittain uusia parannettuja versioita mallisovelluksistaan joko AppSourcen, suoran linkin tai molempien kautta.

Jos olet alun perin ladannut sovelluksen AppSourcesta, kun mallisovelluksen uusi versio tulee saataville, Power BI -palvelussa näkyviin tulevassa ilmoituspalkissa kerrotaan, että uusi sovellusversio on saatavilla.

  ![Mallisovelluksen päivitysilmoitus](media/service-template-apps-install-distribute/power-bi-new-app-version-notification.png)

>[!NOTE]
>Jos olet alun perin hankkinut sovelluksen suoran linkin kautta AppSourcen sijaan, ainoa tapa saada tietää, milloin uusi versio on saatavilla, on ottaa yhteyttä mallisovelluksen luojaan.

  Jos haluat asentaa päivityksen, valitse ilmoituspalkissa **Hanki se** tai etsi sovellus uudelleen AppSourcesta ja valitse **Hanki se nyt**. Jos olet saanut suoran linkin päivitykseen mallinsovelluksen luojalta, napsauta linkkiä.
  
  Sinulta kysytään, haluatko korvata nykyisen version vai asentaa uuden version uuteen työtilaan. Korvaaminen on valittuna oletusarvoisesti.

  ![Mallisovelluksen päivittäminen](media/service-template-apps-install-distribute/power-bi-update-app-overwrite.png)

- **Korvaa olemassa oleva versio:** Korvaa olemassa olevan työtilan mallisovelluksen päivitetyllä versiolla. [Katso lisätietoja korvaamisesta](#overwrite-behavior).

- **Asenna uuteen työtilaan:** Asentaa työtilan ja sovelluksen uuden version, joka on määritettävä uudelleen (eli tietoihin yhdistäminen, siirtymisen ja käyttöoikeuksien määrittäminen).

### <a name="overwrite-behavior"></a>Korvaamisen toiminta

* Korvaaminen päivittää raportit, koontinäytöt ja työtilassa olevan tietojoukon, ei sovellusta. Korvaaminen ei muuta sovelluksen siirtymistä, asennusta ja käyttöoikeuksia.
* Kun olet päivittänyt työtilan, sinun on **päivitettävä sovellus, jotta muutokset otetaan käyttöön työtilasta sovellukseen**.
* Korvaaminen säilyttää määritetyt parametrit ja todentamisen. Päivityksen jälkeen automaattinen tietojoukon päivitys alkaa. **Tämän päivityksen aikana sovelluksessa, raporteissa ja koontinäytöissä näkyvät mallitiedot**.

  ![Mallitiedot](media/service-template-apps-install-distribute/power-bi-sample-data.png)

* Korvaaminen esittää aina mallitiedot, kunnes päivitys on valmis. Jos mallisovelluksen tekijä on tehnyt muutoksia tietojoukkoon tai parametreihin, työtilan ja sovelluksen käyttäjät eivät näe uusia tietoja ennen päivityksen valmistumista. Niiden sijaan he näkevät edelleen mallitiedot.
* Korvaaminen ei koskaan poista uusia raportteja eikä koontinäyttöjä, jotka olet lisännyt työtilaan. Se korvaa ainoastaan alkuperäiset raportit ja koontinäytöt ja alkuperäisen tekijän tekemät muutokset.

>[!IMPORTANT]
>Muista [päivittää sovellus](#customize-and-share-the-app) korvaamisen jälkeen, jotta muutokset tulevat voimaan organisaation sovelluksen käyttäjien raporteissa ja koontinäytössä.

## <a name="next-steps"></a>Seuraavat vaiheet

[Työtilojen luominen työtovereiden kanssa Power BI:ssä](service-create-workspaces.md)
