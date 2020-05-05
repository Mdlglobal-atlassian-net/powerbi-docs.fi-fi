---
title: Regional Emergency Response Dashboard -sovellukseen yhdistäminen
description: Alueellisen hätävalmiuden COVID-19 Decision Support Dashboard -mallisovelluksen hankkiminen, asentaminen ja yhdistäminen tietoihin
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/24/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 6af8568dc39544ce064643c8dfb80fa2932cf13a
ms.sourcegitcommit: 834cad24901f7fd966c4010e36a7904bc120e57f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/24/2020
ms.locfileid: "82149666"
---
# <a name="connect-to-the-regional-emergency-response-dashboard"></a>Regional Emergency Response Dashboard -sovellukseen yhdistäminen
Regional Emergency Response Dashboard on [Microsoft Power Platform Regional Emergency Response -ratkaisun](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/overview) raportointikomponentti. Alueellisten organisaatioiden järjestelmänvalvojat voivat tarkastella koontinäyttöä Power BI -vuokraajassaan, jotta he voivat nopeasti tarkastella tärkeitä tietoja ja mittareita, joiden avulla he voivat tehdä tehokkaita päätöksiä.

![Regional Emergency Response Dashboard -sovelluksen raportti](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-report.png)

Tässä artikkelissa kerrotaan, miten Regional Emergency Response -sovellus asennetaan Regional Emergency Response Dashboard -mallisovelluksen avulla ja miten muodostetaan yhteys tietolähteisiin.

Jos haluat yksityiskohtaisia tietoja koontinäytössä esitetyistä tiedoista, lue artikkeli [Merkityksellisten tietojen hankkiminen](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/portals-admin-reporting#get-insights).

Kun olet asentanut mallisovelluksen ja muodostanut yhteyden tietolähteisiin, voit mukauttaa raporttia tarpeidesi mukaan. Voit sen jälkeen jakaa sen sovelluksena työtovereille organisaatiossasi.

## <a name="prerequisites"></a>Edellytykset

Ennen kuin asennat tämän mallisovelluksen, sinun on ensin asennettava ja määritettävä [Regional Emergency Response -ratkaisu](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/deploy). Tämän ratkaisun asentaminen luo tietolähdeviittaukset, joita tarvitaan sovelluksen täyttämiseen tiedoilla.

Kun asennat Regional Emergency Response -ratkaisun, kirjoita muistiin [Common Data Service -ympäristöesiintymäsi URL-osoite](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/deploy#step-5-configure-and-publish-power-bi-dashboard). Tarvitset sitä mallisovelluksen yhdistämisessä tietoihin.

## <a name="install-the-app"></a>Sovelluksen asentaminen

1. Siirry sovellukseen napsauttamalla seuraavaa linkkiä: [Regional Emergency Response Dashboard -mallisovellus](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response)

1. Valitse sovelluksen AppSource-sivulla [**HANKI SE NYT**](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response).

    [![Regional Emergency Response Dashboard -sovellus AppSourcessa](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-appsource-get-it-now.png)](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response)

1. Valitse **Asenna**. 

    ![Regional Emergency Response Dashboard -sovelluksen asentaminen](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-select-install.png)

    Kun sovellus on asennettu, se näkyy Sovellukset-sivullasi.

   ![Regional Emergency Response Dashboard -sovellus Sovellus-sivulla](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Muodosta yhteys tietolähteisiin.

1. Avaa sovellus valitsemalla kuvake Sovellukset-sivullasi.

1. Valitse käynnistysnäytössä **Tutki**.

   ![Mallisovelluksen käynnistysnäyttö](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-splash-screen.png)

   Sovellus avautuu, ja mallitiedot tulevat näkyviin.

1. Valitse **Yhdistä tietosi** -linkki sivun yläreunassa olevassa ilmoituspalkissa.

   ![Regional Emergency Response Dashboard -sovellus, tietolinkin yhdistäminen](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-connect-data.png)

1. Kirjoita näyttöön tulevassa valintaikkunassa [Common Data Service -ympäristöesiintymän URL-osoite](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#publish-the-power-bi-dashboard). Esimerkki: https://[myenv].crm.dynamics.com. Kun olet valmis, valitse **Seuraava**.

   ![Regional Emergency Response Dashboard -sovelluksen koontinäyttö](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-url-dialog.png)

1. Valitse seuraavassa avautuvassa valintaikkunassa todentamismenetelmäksi **OAuth2**. Sinun ei tarvitse tehdä mitään yksityisyys tasoasetukselle.

   Valitse **Kirjaudu sisään**.

   ![Regional Emergency Response Dashboard -sovelluksen todentamisvalintaikkuna](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-authentication-dialog.png)

1. Kirjaudu sisään Power BI:hin Microsoftin sisäänkirjautumisnäytössä.

   ![Microsoftin sisäänkirjautumisnäyttö](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-microsoft-login.png)

   Kun olet kirjautunut sisään, raportista muodostetaan yhteys tietolähteisiin ja se täytetään ajantasaisilla tiedoilla. Tässä vaiheessa toiminnan valvonta muuttuu.

   ![Regional Emergency Response Dashboard -sovelluksen päivittäminen käynnissä](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>Raportin päivityksen ajoittaminen

Kun tietojen päivitys on valmis, [määritä päivitysaikataulu](../refresh-scheduled-refresh.md), jotta raportin tiedot pysyvät ajan tasalla.

1. Valitse yläreunan otsikkorivillä **Power BI**.

   ![Power BI -navigointipolku](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-powerbi-breadcrumb.png)

1. Etsi vasemmasta siirtymisruudusta Regional Emergency Response Dashboard -työtila kohdasta **Työtilat** ja noudata ohjeita artikkelissa[Ajoitetun päivityksen määrittäminen](../refresh-scheduled-refresh.md).

## <a name="customize-and-share"></a>Mukauta ja jaa

Lisätietoja on artikkelissa [Sovelluksen mukauttaminen ja jakaminen](../service-template-apps-install-distribute.md#customize-and-share-the-app). Tarkista [raportin vastuuvapausilmoitus](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/overview#disclaimer) ennen sovelluksen julkaisemista tai jakelemista.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Regional Emergency Response Dashboard -koontinäytön ymmärtäminen](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/portals-admin-reporting#get-insights)
* [Power Appsin Crisis Communication -mallisovelluksen määrittäminen ja siihen tutustuminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
* [Mitä Power BI -mallisovellukset ovat?](../service-template-apps-overview.md)
* [Mallisovellusten asentaminen ja jakaminen organisaatiossa](../service-template-apps-install-distribute.md)
