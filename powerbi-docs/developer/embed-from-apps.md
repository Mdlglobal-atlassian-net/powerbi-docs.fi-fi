---
title: Upota raportteja tai koontinäyttöjä sovelluksista
description: Opi integroimaan tai upottamaan raportti tai koontinäyttö Power BI -sovelluksesta, tai muualta, työtilaan.
author: rkarlin
ms.author: rkarlin
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: mvc
manager: kfile
ms.date: 11/27/2018
ms.openlocfilehash: 5a988eb160ce772d2c2e70e8cba2c01d3f0a36a9
ms.sourcegitcommit: 81ba3572531cbe95ea0b887b94e91f94050f3129
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/06/2019
ms.locfileid: "66750889"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>Upota raportteja tai koontinäyttöjä sovelluksista

Voit luoda Power BI:ssä sovelluksia, jotka kokoavat toisiinsa liittyvät koontinäytöt ja raportit yhteen paikkaan. Sen jälkeen voit julkaista raportit ja koontinäytöt suurelle määrälle ihmisiä organisaatiossasi. Kyseisten sovellusten käyttö on tärkeää, kun kaikki käyttäjät ovat Power BI -käyttäjiä. Tällöin voit jakaa sisältöä heille Power BI -sovellusten avulla. Tässä artikkelissa kerrotaan, miten voit muutaman nopean vaiheen avulla upottaa sisältöä julkaistusta Power BI -sovelluksesta kolmannen osapuolen sovellukseen.

## <a name="grab-a-report-embedurl-for-embedding"></a>Hae raportin embedURL-osoite upottamista varten

1. Käynnistä sovelluksen istunto käyttäjän työtilassa, **Oma työtilassa**. Jaa sisältö itsellesi tai opasta toista käyttäjä tämän työnkulun suorittamisessa.

2. Avaa haluamasi raportti Power BI -palvelussa.

3. Valitse **Tiedosto** > **Upota SharePoint Onlinessa** ja hae raportin embedURL-osoite. Alla olevassa kuvassa näytetään embedURL-esimerkkiosoite. Halutessasi voit myös kutsua GetReports/GetReport REST -ohjelmointirajapintaa ja tarkistaa raportin embedURL-kentän vastauksesta. REST-kutsun URL-osoitteella ei pitäisi olla työtilan tunnusta, koska sovellusistunto käynnistettiin käyttäjän työtilassa.

    ![Upottaminen sovelluksista](media/embed-from-apps/embed-from-app.png)

4. Käytä vaiheessa 3 noudettua embedURL-osoitetta JavaScript SDK:n kanssa.

## <a name="grab-a-dashboard-embedurl-for-embedding"></a>Hae raporttinäkymän embedURL-osoite upottamista varten

1. Käynnistä sovelluksen istunto käyttäjän työtilassa, **Oma työtilassa**. Jaa sisältö itsellesi tai opasta toista käyttäjä tämän työnkulun suorittamisessa.

2. Kutsu GetDashboards REST -ohjelmointirajapinta ja pura vastauksesta raportin embedURL-kenttä. REST-kutsun URL-osoitteella ei pitäisi olla työtilan tunnusta, koska sovellusistunto käynnistettiin käyttäjän työtilassa.

3. Käytä vaiheessa 2 noudettua embedURL-osoitetta JavaScript SDK:n kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

Katso, miten voit upottaa sovelluksen työtiloista kolmannen osapuolten asiakkaille ja organisaatiollesi:

> [!div class="nextstepaction"]
>[Upottaminen kolmannen osapuolten asiakkaille](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)
