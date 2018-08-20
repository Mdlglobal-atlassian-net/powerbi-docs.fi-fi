---
title: Power BI:n URL-osoitteet
description: Päätepisteiden tulee olla Power BI:tä käyttävien asiakkaiden ulottuvilla
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/13/2018
ms.openlocfilehash: 8e29fa0c9471bb865619102247f38776208c3d87
ms.sourcegitcommit: 8990028a348b642ba5c96f001fe3a4280f0166ee
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/14/2018
ms.locfileid: "40101123"
---
# <a name="power-bi-urls"></a>Power BI:n URL-osoitteet

**Power BI -verkkopalvelu** eli Power BI SaaS (Software as a Service) -sovellus edellyttää Internet-yhteyttä. Alla olevien päätepisteiden tulee olla Power BI -verkkopalvelua käyttävien asiakkaiden ulottuvilla.

Jotta voit käyttää Power BI -verkkopalvelua, sinun on voitava yhdistää päätepisteisiin, jotka on merkitty **pakollisiksi** alla olevissa taulukoissa ja päätepisteisiin, jotka on merkitty **pakollisiksi** linkitetyissä sivustoissa. Jos linkki ulkoiseen sivustoon viittaa tiettyyn osioon, sinun tarvitsee vain tarkistaa tämän osion päätepisteet.

**Valinnaisiksi** merkityt päätepisteet voidaan myös **lisätä sallittujen kohteiden luetteloon**, jotta tietty toiminto toimisi.

Power BI -verkkopalvelu edellyttää vain TCP-portin 443 avaamista luetteloiduille päätepisteille.

Yleismerkit (*) edustavat juuritason toimialueen alaisia kaikkia tasoja. Kun tietoja ei ole saatavilla, se on osoitettu merkillä –. **Kohteet**-sarakeluettelossa on täydellisiä toimialuenimiä/toimialueita ja linkkejä ulkoisiin sivustoihin, jotka sisältävät lisätietoja päätepisteistä.

>[!Important]
>Alla olevien taulukoiden tiedot eivät kata **Yhdysvaltojen hallituksen pilvipalvelua**, **Saksan pilvipalvelua** ja **Kiinan pilvipalvelua**.

## <a name="authentication"></a>Todentaminen

Power BI riippuu Office 365:n todentamisen ja tunnistetietojen osioissa vaadituista päätepisteistä. Jotta voit käyttää Power BI:tä, sinun on voitava yhdistää alla olevassa linkitetyssä sivustossa mainittuihin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Pakollinen:** todentaminen ja tunnistetiedot | Katso [Office 365:n todentaminen ja tunnistetiedot - osiota](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_identity) Office 365:n sallittujen kohteiden luettelon sivustosta | – |

## <a name="general-site-usage"></a>Yleinen sivuston käyttö

Power BI:n yleistä käyttöä varten sinun on voitava yhdistää taulukossa ja alla olevissa linkitetyissä sivustoissa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Pakollinen:** taustan ohjelmointirajapinnat | *.analysis.windows.net | TCP 443 |
| 2 | **Pakollinen:** Office 365:n integrointi | Katso [Office 365 -portaali ja jakaminen -osiota](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) Office 365:n sallittujen kohteiden luettelon sivustosta | – |
| 3 | **Pakollinen:** portaali | app.powerbi.com | TCP 443 |
| 4 | **Pakollinen:** palvelutelemetria | dc.services.visualstudio.com | TCP 443 |
| 5 | **Pakollinen:** tietoviestit | dynmsg.modpim.com | TCP 443 |
| 6 | **Pakollinen:** NPS-kyselyt | nps.onyx.azure.net | TCP 443 |

## <a name="administration"></a>Hallinta

Jotta voit suorittaa järjestelmänvalvojan toimintoja Power BI:llä, sinun on voitava yhdistää alla linkitetyissä sivustoissa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Pakollinen:** käyttäjien hallintaan ja valvontalokien tarkasteluun | Katso [Office 365 -portaali ja jakaminen -osiota](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) Office 365:n sallittujen kohteiden luettelon sivustosta | – |

## <a name="get-data"></a>Nouda tiedot

Jotta voit saada tietoja tietyistä tietolähteistä, kuten OneDrivesta, sinun on voitava yhdistää alla olevassa taulukossa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Pakollinen:** AppSource (Power BI:n sisäiset tai ulkoiset sovellukset) | appsource.microsoft.com | TCP 443 |
| 2 | **Pakollinen:** tuo tiedostoja henkilökohtaisesta OneDrivesta | Katso [OneDrive-sivuston pakolliset URL-osoitteet ja portit](https://support.office.com/en-ie/article/required-urls-and-ports-for-onedrive-ce15d2cc-52ef-42cd-b738-d9c6f9b03f3a) | – |
| 3 | **Valinnainen:** Power BI:n 60 sekunnin opetusohjelmavideo | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 4 | **Valinnainen:** PubNub-suoratoiston tietolähteet | Katso [PubNub-dokumentaatio](https://support.pubnub.com/support/solutions/articles/14000043522) | – |

## <a name="dashboard-and-report-integration"></a>Koontinäyttö ja raportin integrointi 

Power BI riippuu tietyistä päätepisteistä, jotta se voi tukea koontinäyttöjä ja raportteja. Sinun on voitava yhdistää taulukossa ja alla olevissa linkitetyissä sivustoissa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Pakollinen:** Excelin integrointi | Katso [Office Online -osiota](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) Office 365:n sallittujen kohteiden luettelon sivustosta | – |

## <a name="custom-visuals"></a>Mukautetut visualisoinnit

Power BI riippuu tietyistä päätepisteistä mukautettujen visualisointien tarkastelemiseksi ja käyttämiseksi. Sinun on voitava yhdistää taulukossa ja alla olevissa linkitetyissä sivustoissa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Pakollinen:** tuo mukautettu visualisointi Marketplace-liittymästä ja tiedostosta | *.microsoft.com </br> *.bing.com </br> *.msecnd.net </br> *.osi.office.net </br> *.azureedge.net </br> ajax.aspnetcdn.com </br> nexus.ensighten.com </br> store.office.com | TCP 443 |
| 2 | **Pakollinen:** Bing-kartat | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **Valinnainen:** PowerApps | Katso [Pakolliset palvelut -osiota](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) PowerApps-järjestelmän vaatimukset -sivustosta | – |
| 4 | **Valinnainen:** Visio | Katso [Office Online -osiota](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) Office 365:n sallittujen kohteiden luettelon sivustosta | – |