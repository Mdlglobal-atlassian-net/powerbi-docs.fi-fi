---
title: Upota raportteja tai koontinäyttöjä sovelluksista
description: Opi integroimaan tai upottamaan raportti tai koontinäyttö Power BI -sovelluksesta, tai muualta, työtilaan.
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: how-to
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 2817ccb25fc9aa6d3e8150c776558366dcf0ccb6
ms.sourcegitcommit: 0c870a006e525447497e678484874a2f137b9abd
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/17/2018
ms.locfileid: "39088835"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>Upota raportteja tai koontinäyttöjä sovelluksista

**Power BI:ssä** voit luoda sovelluksia kaikkien **koontinäyttöjen** ja **raporttien** tuomiseksi yhteen paikkaan ja sitten julkaista ne suurille ihmisryhmille organisaatiossasi. Näiden sovellusten käyttö on olennaista kun kaikki käyttäjät ovat Power BI -käyttäjiä, jolloin voit jakaa sisältöä heidän kanssaan Power BI -sovelluksia käyttämällä. Seuraavassa on kerrottu, miten voit muutaman nopean vaiheen avulla upottaa sisältöä julkaistusta Power BI -sovelluksesta kolmannen osapuolen sovellukseen.

## <a name="how-to-grab-report-embed-url-for-embedding"></a>Raporttiin upotetun URL-osoitteen poimiminen upottamista varten

1. Alusta sovellus käyttäjän työtilassa (‘Oma työtila’), joko jakamalla se itsesi kanssa tai ohjaamalla toinen käyttäjä tämän työnkulun läpi.

2. Avaa haluamasi raportti Power BI-palvelussa.

3. Siirry kohtaan Tiedosto -> Upota SharePoint Onlinessa ja tartu raportin upotettuun URL-osoitteeseen täällä (kuvattu alla olevassa tilannekuvassa) tai kutsu GetReports/GetReport REST -ohjelmointirajapinta ja poimi vastaava raportin embedURL-kenttä vastauksesta (huomaa, ettei REST-kutsussa tulisi olla työtilatunnusta URL-osoitteessaan, koska sovellus alustettiin käyttäjän työtilassa).

4. Käytä kohdassa 3 noudettua upotettua URL-osoitetta JS SDK:n kanssa.

    ![Upottaminen sovelluksista](media/embed-from-apps/embed-from-app.png)

## <a name="how-to-grab-dashboard-embed-url-for-embedding"></a>Raporttinäkymään upotetun URL-osoitteen poimiminen upottamista varten

1. Alusta sovellus käyttäjän työtilassa (‘Oma työtila’), joko jakamalla se itsesi kanssa tai ohjaamalla toinen käyttäjä tämän työnkulun läpi.

2. Kutsu GetDashboards REST -ohjelmointirajapinta ja poimi vastaava raporttinäkymän embedURL-kenttä vastauksesta (huomaa, ettei REST-kutsussa tulisi olla työtilatunnusta URL-osoitteessaan, koska sovellus alustettiin käyttäjän työtilassa).

3. Käytä vaiheessa 4 poimittua URL-osoitetta JS SDK:n kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

Katso myös, miten upotat sovelluksen työtiloista kolmannen osapuolten asiakkaille ja organisaatiollesi.

> [!div class="nextstepaction"]
>[Upottaminen kolmannen osapuolten asiakkaille](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)