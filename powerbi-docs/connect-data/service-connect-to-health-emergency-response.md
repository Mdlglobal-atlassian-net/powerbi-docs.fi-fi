---
title: Yhdistäminen Hospital Emergency Response Decision Support Dashboard -sovellukseen
description: Terveydenhuollon hätävalmiuden COVID-19 Decision Support Dashboard -mallisovelluksen hankkiminen
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: b951e96a5d81603dc91e4fc47a2b412d4140f85d
ms.sourcegitcommit: 34cca70ba84f37b48407d5d8a45c3f51fb95eb3c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2020
ms.locfileid: "80752046"
---
# <a name="connect-to-the-hospital-emergency-response-decision-support-dashboard"></a>Yhdistäminen Hospital Emergency Response Decision Support Dashboard -sovellukseen
Hospital Emergency Response Decision Support Dashboard -mallisovellus on [Microsoft Power Platform -ratkaisun terveydenhuollon hätävasteen ](https://powerapps.microsoft.com/blog/emergency-response-solution-a-microsoft-power-platform-solution-for-healthcare-emergency-response/) raportointiosa. Koontinäytössä näytetään valmiuspäälliköille koostettuja tietoja heidän terveysjärjestelmästään, jotta he voivat tehdä oikeita päätöksiä oikeaan aikaan.

![Hospital Emergency Response Decision Support Dashboard -sovelluksen raportti](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-report.png)

Tässä artikkelissa kerrotaan, miten voit sovellus asennetaan ja miten muodostetaan yhteys tietolähteisiin. Jos haluat tietää, miten voit käyttää tämän sovelluksen yhteydessä näkyvää raporttia, katso [Hospital Emergency Response Decision Support Dashboard -ohjeita](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#view-the-power-bi-dashboard).

Kun olet asentanut mallisovelluksen ja muodostanut yhteyden tietolähteisiin, voit mukauttaa raporttia tarpeidesi mukaan. Voit sen jälkeen jakaa sen sovelluksena työtovereille organisaatiossasi.

## <a name="prerequisites"></a>Edellytykset

Ennen kuin asennat tämän mallisovelluksen, sinun on ensin asennettava ja määritettävä [Hospital Emergency Response Power Platform -ratkaisu](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure). Tämän ratkaisun asentaminen luo tietolähdeviittaukset, joita tarvitaan sovelluksen täyttämiseen tiedoilla.

Kun asennat Hospital Emergency Response Power Platform -ratkaisun, kirjoita muistiin [Common Data Service ympäristö esiintymäsi URL-osoite](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#publish-the-power-bi-dashboard). Tarvitset sitä mallisovelluksen yhdistämisessä tietoihin.

## <a name="install-the-app"></a>Sovelluksen asentaminen

1. Siirry sovellukseen napsauttamalla seuraavaa linkkiä: [Hospital Emergency Response Decision Support Dashboard -mallisovellus](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.powerapps_healthcare)

1. Valitse sovelluksen AppSource-sivulla [**HANKI SE NYT**](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.powerapps_healthcare).

    [![Hospital Emergency Response Decision Support Dashboard -sovellus AppSourcessa](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-appsource-get-it-now.png)](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.powerapps_healthcare)

1. Lue tiedot kohdassa **Vielä yksi asia** ja valitse **Jatka**.

    ![Hospital Emergency Response Decision Support Dashboard -sovellus, Vielä yksi asia](media/service-connect-to-health-emergency-response/service-health-emergency-response-1-more-thing.png)

1. Valitse **Asenna**. 

    ![Hospital Emergency Response Decision Support Dashboard -sovelluksen asentaminen](media/service-connect-to-health-emergency-response/service-health-emergency-response-select-install.png)

    Kun sovellus on asennettu, se näkyy Sovellukset-sivullasi.

   ![Hospital Emergency Response Decision Support Dashboard -sovellus Sovellukset-sivulla](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Muodosta yhteys tietolähteisiin.

1. Avaa sovellus valitsemalla kuvake Sovellukset-sivullasi.

1. Valitse käynnistysnäytössä **Tutki**.

   ![Mallisovelluksen käynnistysnäyttö](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-splash-screen.png)

   Sovellus avautuu, ja mallitiedot tulevat näkyviin.

1. Valitse **Yhdistä tietosi** -linkki sivun yläreunassa olevassa ilmoituspalkissa.

   ![Hospital Emergency Response Decision Support Dashboard -sovellus, tietolinkin yhdistäminen](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-connect-data.png)

1. Toimi valintaikkunassa seuraavasti:
   1. Kirjoita organisaation nimikenttään organisaatiosi nimi, esimerkiksi Contoso Health Systems. Tämä kenttä on valinnainen. Tämä nimi näkyy koontinäytön vasemmassa yläkulmassa.
   1. Kirjoita CDS_base_solution-kentässä [Common Data Service -ympäristöesiintymän URL-osoite](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#publish-the-power-bi-dashboard). Esimerkki: https://[myenv].crm.dynamics.com. Kun olet valmis, valitse **Seuraava**.

   ![Hospital Emergency Response Decision Support Dashboard -sovelluksen URL-valintaikkuna](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-url-dialog.png)

1. Valitse seuraavassa avautuvassa valintaikkunassa todentamismenetelmäksi **OAuth2**. Sinun ei tarvitse tehdä mitään yksityisyys tasoasetukselle.

   Valitse **Kirjaudu sisään**.

   ![Hospital Emergency Response Decision Support Dashboard -sovelluksen todennusvalintaikkuna](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-authentication-dialog.png)

1. Kirjaudu sisään Power BI:hin Microsoftin sisäänkirjautumisnäytössä.

   ![Microsoftin sisäänkirjautumisnäyttö](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-microsoft-login.png)

   Kun olet kirjautunut sisään, raportista muodostetaan yhteys tietolähteisiin ja se täytetään ajantasaisilla tiedoilla. Tässä vaiheessa toiminnan valvonta muuttuu.

   ![Hospital Emergency Response Decision Support Dashboard -sovelluksen päivittäminen käynnissä](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>Raportin päivityksen ajoittaminen

Kun tietojen päivitys on valmis, [määritä päivitysaikataulu](../refresh-scheduled-refresh.md), jotta raportin tiedot pysyvät ajan tasalla.

1. Valitse yläreunan otsikkorivillä **Power BI**.

   ![Power BI -navigointipolku](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-powerbi-breadcrumb.png)

1. Etsi vasemmasta siirtymisruudusta Hospital Emergency Response Decision Support Dashboard -työtila kohdasta **Työtilat** ja noudata ohjeita artikkelissa[Ajoitetun päivityksen määrittäminen](../refresh-scheduled-refresh.md).

## <a name="customize-and-share"></a>Mukauta ja jaa

Lisätietoja on artikkelissa [Sovelluksen mukauttaminen ja jakaminen](../service-template-apps-install-distribute.md#customize-and-share-the-app). Tarkista [raportin vastuuvapausilmoitus](../create-reports/sample-covid-19-us.md#disclaimers) ennen sovelluksen julkaisemista tai jakelemista.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Hospital Emergency Response -sovelluksen raportin ymmärtäminen](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#view-the-power-bi-dashboard)
* [Power Appsin Crisis Communication -mallisovelluksen määrittäminen ja siihen tutustuminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
* [Mitä Power BI -mallisovellukset ovat?](../service-template-apps-overview.md)
* [Mallisovellusten asentaminen ja jakaminen organisaatiossa](../service-template-apps-install-distribute.md)
