---
title: COVID-19 US Tracking -raporttiin yhdistäminen
description: COVID-19 US Tracking -mallisovelluksen hankkiminen, asentaminen ja tietoihin yhdistäminen.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/05/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 90d5e48ca200a6817338ae6c44595905cc76bfed
ms.sourcegitcommit: 34cca70ba84f37b48407d5d8a45c3f51fb95eb3c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2020
ms.locfileid: "80752667"
---
# <a name="connect-to-the-covid-19-us-tracking-report"></a>COVID-19 US Tracking -raporttiin yhdistäminen
Tässä artikkelissa kerrotaan, miten COVID-19-seurantaraportin mallisovellus asennetaan ja miten muodostetaan yhteys tietolähteisiin.

![Yhdysvaltojen COVID-19-seurantaraportti](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-title-screen.png)

Tarkat tiedot itse raportista, mukaan lukien vastuuvapauslausekkeet ja muut tiedoista, ovat artikkelissa [COVID-19-seurantamalli Yhdysvaltain viranomaisille](../create-reports/sample-covid-19-us.md).

Kun olet asentanut mallisovelluksen ja muodostanut yhteyden tietolähteisiin, voit mukauttaa raporttia tarpeidesi mukaan. Voit sen jälkeen jakaa sen sovelluksena työtovereille organisaatiossasi.

## <a name="install-the-app"></a>Sovelluksen asentaminen

1. Siirry sovellukseen napsauttamalla seuraavaa linkkiä: [COVID-19 US Tracking -raporttimallisovellus](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.covid19ms)

1. Kun olet sovelluksen AppSource-sivulla, valitse [**HANKI SE NYT**](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.covid19ms).

    [![COVID-19 US Tracking -raporttisovellus AppSourcessa](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-appsource-icon.png)](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.covid19ms)

1. Valitse pyydettäessä **Asenna**. Kun sovellus on asennettu, näet sen Sovellukset-sivullasi.

   ![COVID-19 US Tracking -raporttisovellus Sovellukset-sivulla](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Muodosta yhteys tietolähteisiin.

1. Avaa sovellus napsauttamalla kuvaketta Sovellukset-sivullasi.

1. Valitse näyttöön tulevassa käynnistysnäytössä **Yhdistä**.

   ![Mallisovelluksen käynnistysnäyttö](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-splash-screen.png)

1. Näkyviin tulee peräkkäin kaksi kirjautumisvalintaikkunaa. Aseta kummassakin yksityisyystasoksi Julkinen.

   ![COVID-19 US Tracking -raporttisovelluksen kirjautumisvalintaikkuna](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-signin-dialog.png)

   Raportti yhdistetään tietolähteisiin ja täytetään ajantasaisilla tiedoilla. Tässä vaiheessa toiminnan valvonta muuttuu.

   ![COVID-19 US Tracking -raportin päivitys käynnissä](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>Raportin päivityksen ajoittaminen

Kun tiedot on päivitetty, olet sovellukseen liittyvässä työtilassa. [Määritä päivitysaikataulu](../refresh-scheduled-refresh.md), jotta raportin tiedot pysyvät ajan tasalla.

## <a name="customize-and-share"></a>Mukauta ja jaa

Lisätietoja on artikkelissa [Sovelluksen mukauttaminen ja jakaminen](../service-template-apps-install-distribute.md#customize-and-share-the-app). Tarkista [raportin vastuuvapausilmoitus](../create-reports/sample-covid-19-us.md#disclaimers) ennen sovelluksen julkaisemista tai jakelemista.

## <a name="next-steps"></a>Seuraavat vaiheet
* [COVID-19-seurantamalli Yhdysvaltain viranomaisille](../create-reports/sample-covid-19-us.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
* [Mitä Power BI -mallisovellukset ovat?](../service-template-apps-overview.md)
* [Mallisovellusten asentaminen ja jakaminen organisaatiossa](../service-template-apps-install-distribute.md)
