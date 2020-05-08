---
title: Crisis Communication -läsnäoloraporttiin yhdistäminen
description: COVID-19 Crisis Communication Presence Report -mallisovelluksen hankkiminen, asentaminen ja yhdistäminen tietoihin
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: f637bb10ed7ec27dcb3da07fc04cae39328ffebe
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "80752253"
---
# <a name="connect-to-the-crisis-communication-presence-report"></a>Crisis Communication -läsnäoloraporttiin yhdistäminen

Tämä Power BI -sovellus on Crisis Communicationin Microsoft Power Platform -ratkaisun raportti/koontinäyttöartefakti. Se seuraa Crisis Communication -sovelluksen käyttäjien työntekijäsijaintia. Ratkaisussa yhdistyvät Power Appsin, Power Automaten, Teamsin, SharePointin ja Power BI :n toiminnot. Sitä voi käyttää verkossa, mobiililaitteissa tai Teamsissa.

![Crisis Communication -läsnäoloraporttisovelluksen raportti](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report.png)

Koontinäytössä näytetään valmiuspäälliköille koostettuja tietoja heidän terveysjärjestelmästään, jotta he voivat tehdä oikeita päätöksiä oikeaan aikaan.

Tässä artikkelissa kerrotaan, miten voit sovellus asennetaan ja miten muodostetaan yhteys tietolähteisiin. Lisätietoja Crisis Communication -sovelluksesta on artikkelissa [Power Appsin Crisis Communication -mallisovelluksen määrittäminen ja siihen tutustuminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app)

Kun olet asentanut mallisovelluksen ja muodostanut yhteyden tietolähteisiin, voit mukauttaa raporttia tarpeidesi mukaan. Voit sen jälkeen jakaa sen sovelluksena työtovereille organisaatiossasi.

## <a name="prerequisites"></a>Edellytykset

Ennen kuin asennat tämän mallisovelluksen, sinun on ensin asennettava ja määritettävä [Crisis Communication -malli](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app). Tämän ratkaisun asentaminen luo tietolähdeviittaukset, joita tarvitaan sovelluksen täyttämiseen tiedoilla.

Kun asennat Crisis Communication -mallin, kirjoita muistiin [CI_Employee Status -SharePoint-luettelon kansiopolku ja luettelotunnus](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app#monitor-office-absences-with-power-bi).

## <a name="install-the-app"></a>Sovelluksen asentaminen

1. Siirry sovellukseen napsauttamalla seuraavaa linkkiä: [Crisis Communication -läsnäoloraporttimallisovellus](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.crisiscomms)

1. Valitse sovelluksen AppSource-sivulla [**HANKI SE NYT**](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.crisiscomms).

    [![Crisis Communication -läsnäoloraporttimallisovellus AppSourcessa](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-appsource-get-it-now.png)](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.crisiscomms)

1. Lue tiedot kohdassa **Vielä yksi asia** ja valitse **Jatka**.

    ![Crisis Communication -läsnäoloraporttimalli, Vielä yksi asia](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-1-more-thing.png)

1. Valitse **Asenna**. 

    ![Asenna Crisis Communication -läsnäoloraporttisovellus](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-select-install.png)

    Kun sovellus on asennettu, se näkyy Sovellukset-sivullasi.

   ![Crisis Communication -läsnäoloraporttisovellus Sovellukset-sivulla](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Muodosta yhteys tietolähteisiin.

1. Avaa sovellus valitsemalla kuvake Sovellukset-sivullasi.

1. Valitse käynnistysnäytössä **Tutki**.

   ![Mallisovelluksen käynnistysnäyttö](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-splash-screen.png)

   Sovellus avautuu, ja mallitiedot tulevat näkyviin.

1. Valitse **Yhdistä tietosi** -linkki sivun yläreunassa olevassa ilmoituspalkissa.

   ![Crisis Communication -läsnäoloraporttisovellus, yhdistä tietolinkki](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-connect-data.png)

1. Toimi valintaikkunassa seuraavasti:
   1. Kirjoita SharePoint_Folder-kenttään [CI_Employee Status -SharePoint-luettelon polku](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app#monitor-office-absences-with-power-bi).
   1. Kirjoita List_ID-kenttään luettelosi tunnus, jonka sait luettelon asetuksista. Kun olet valmis, valitse **Seuraava**.

   ![Crisis Communication -läsnäoloraporttisovelluksen URL-valintaikkuna](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-url-dialog.png)

1. Valitse seuraavassa avautuvassa valintaikkunassa todentamismenetelmäksi **OAuth2**. Sinun ei tarvitse tehdä mitään yksityisyys tasoasetukselle.

   Valitse **Kirjaudu sisään**.

   ![Crisis Communication -läsnäoloraporttisovelluksen todennusvalintaikkuna](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-authentication-dialog.png)

1. Kirjaudu sisään Power BI:hin Microsoftin sisäänkirjautumisnäytössä.

   ![Microsoftin sisäänkirjautumisnäyttö](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-microsoft-login.png)

   Kun olet kirjautunut sisään, raportista muodostetaan yhteys tietolähteisiin ja se täytetään ajantasaisilla tiedoilla. Tässä vaiheessa toiminnan valvonta muuttuu.

   ![Crisis Communication -läsnäoloraporttisovelluksen päivitys käynnissä](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>Raportin päivityksen ajoittaminen

Kun tietojen päivitys on valmis, [määritä päivitysaikataulu](../refresh-scheduled-refresh.md), jotta raportin tiedot pysyvät ajan tasalla.

1. Valitse yläreunan otsikkorivillä **Power BI**.

   ![Power BI -navigointipolku](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-powerbi-breadcrumb.png)

1. Etsi vasemmasta siirtymisruudusta Hospital Emergency Response Decision Support Dashboard -työtila kohdasta **Työtilat** ja noudata ohjeita artikkelissa[Ajoitetun päivityksen määrittäminen](../refresh-scheduled-refresh.md).

## <a name="customize-and-share"></a>Mukauta ja jaa

Lisätietoja on artikkelissa [Sovelluksen mukauttaminen ja jakaminen](../service-template-apps-install-distribute.md#customize-and-share-the-app). Tarkista [raportin vastuuvapausilmoitus](../create-reports/sample-covid-19-us.md#disclaimers) ennen sovelluksen julkaisemista tai jakelemista.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Power Appsin Crisis Communication -mallisovelluksen määrittäminen ja siihen tutustuminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
* [Mitä Power BI -mallisovellukset ovat?](../service-template-apps-overview.md)
* [Mallisovellusten asentaminen ja jakaminen organisaatiossa](../service-template-apps-install-distribute.md)
