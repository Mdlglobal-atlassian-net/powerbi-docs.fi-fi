---
title: Power BI -yhdyskäytävän asentaminen
description: Lue, miten voit asentaa yhdyskäytävän niin, että voit muodostaa yhteyden paikallisiin tietoihin Power BI:ssä.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 04/18/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: ecb5450c33500950336f08a8ca82812fb0850e0c
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54276005"
---
# <a name="install-a-gateway-for-power-bi"></a>Power BI -yhdyskäytävän asentaminen

Power BI -yhdyskäytävä on ohjelmisto, jonka asennat paikalliseen verkkoon; se helpottaa tietojen käyttöä kyseisessä verkossa. Kuten [yhteenvedossa](service-gateway-getting-started.md) on kuvattu, voit asentaa yhdyskäytävän henkilökohtaisessa tilassa tai normaalissa tilassa (suositus). Normaalissa tilassa voit asentaa erillisen yhdyskäytävän tai lisätä yhdyskäytävän *klusteriin*, joka on suositeltavaa suuren käytettävyyden kannalta. Tässä artikkelissa esittelemme miten normaali yhdyskäytävä asennetaan ja sitten miten klusteriin lisätään uusi yhdyskäytävä.

Jos et ole rekisteröitynyt Power BI:hin, [rekisteröidy ilmaiseen kokeiluversioon](https://app.powerbi.com/signupredirect?pbi_source=web) ennen aloittamista.


## <a name="download-and-install-a-gateway"></a>Yhdyskäytävän lataaminen ja asentaminen

Yhdyskäytävä toimii siinä tietokoneessa, johon sen asennat, joten varmista, että asennat sen sellaiselle tietokoneelle, joka on aina käytössä. Paremman suorituskyvyn ja luotettavuuden takaamiseksi suosittelemme, että tietokone on liitetty lankaverkkoon langattoman sijaan.

1. Valitse Power BI -palvelun oikeassa yläkulmassa **latauskuvake**![Latauskuvake](media/service-gateway-install/icon-download.png) > **Tietoyhdyskäytävä**.

    ![Tietoyhdyskäytävä](media/service-gateway-install/data-gateway.png)

2. Valitse lataussivulla **LATAA YHDYSKÄYTÄVÄ** -painike.

3. Valitse **Seuraava**.     

    ![Tietoyhdyskäytävän asennusohjelma](media/service-gateway-install/gateway-installer.png)

4. Valitse **Paikallinen tietoyhdyskäytävä (suositus)** > **Seuraava**.

    ![Yhdyskäytävän tyyppi](media/service-gateway-install/gateway-type.png)

5. Säilytä asennuksen oletuspolku ja hyväksy ehdot > **Asenna**.

    ![Asennuspolku](media/service-gateway-install/install-path.png)

6. Syötä tili, jolla kirjaudut Power BI:hin > **Kirjaudu sisään**.

    ![Sähköpostiosoite](media/service-gateway-install/email-address.png)

    Yhdyskäytävä liitetään Power BI -tiliisi ja hallinnoit yhdyskäytäviä Power BI -palvelun sisältä. Olet nyt kirjautuneena tilillesi.

7. Valitse **Rekisteröi uusi yhdyskäytävä tässä tietokoneessa** > **Seuraava**.

    ![Rekisteröi yhdyskäytävä](media/service-gateway-install/register-gateway.png)

8. Syötä yhdyskäytävän nimi (jonka tulee olla vuokraajalle ainutlaatuinen) ja palautusavain. Tarvitset tätä avainta, jos joskus haluat palauttaa tai siirtää yhdyskäytäväsi. Valitse **Määritä**.

    ![Määritä yhdyskäytävä](media/service-gateway-install/configure-gateway.png)

    Huomaa vaihtoehto **Lisää aiemmin luotuun yhdyskäytävän klusteriin**. Käytämme tätä vaihtoehtoa artikkelin seuraavassa osiossa.

9. Tarkasta viimeisen ikkunan tiedot. Huomaa, että yhdyskäytävä on käytettävissä Power BI:lle ja PowerAppsille sekä Flow:lle, koska käytän samaa tiliä kaikissa kolmessa. Valitse **Sulje**.

    ![Yhteenvetonäyttö](media/service-gateway-install/summary-screen.png)

Olet nyt asentanut onnistuneesti yhdyskäytävän ja voit lisätä toisen luodaksesi klusterin.


## <a name="add-another-gateway-to-create-a-cluster"></a>Lisää toinen yhdyskäytävä luodaksesi klusterin

Klusteri mahdollistaa yhdyskäytävien järjestelmänvalvojille yksittäinen vikaantumispisteen syntymisen paikallisten tietojen käytössä. Jos ensisijainen yhdyskäytävä ei ole käytettävissä, tietopyynnöt reititetään lisäämääsi toiseen yhdyskäytävään ja niin edelleen. Voit asentaa tietokoneelle vain yhden tavallisen yhdyskäytävän, joten klusterin toinen yhdyskäytävä täytyy asentaa toiseen tietokoneeseen. Tämä on järkevää, koska haluat klusterissa olevan redundanssia.

Suuren käytettävyyden yhdyskäytäväklusterit edellyttävät marraskuun 2017 päivityksen paikalliseen tietoyhdyskäytävään tai uudemman version.

1. Lataa yhdyskäytävä toiselle tietokoneelle ja asenna se.

2. Rekisteröi yhdyskäytävä, kun olet kirjautunut Power BI -tilillesi. Valitse **Lisää aiemmin luotuun yhdyskäytävän klusteriin**. Valitse kohdassa **Käytettävissä olevat yhdyskäytäväklusterit** ensimmäinen asentamasi yhdyskäytävä (*ensisijainen yhdyskäytävä*) ja syötä sen palautusavain. Valitse **Määritä**.

    ![Lisää aiemmin luotuun yhdyskäytävän klusteriin](media/service-gateway-install/add-cluster.png)


## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI -yhdyskäytävän hallinta](service-gateway-manage.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)