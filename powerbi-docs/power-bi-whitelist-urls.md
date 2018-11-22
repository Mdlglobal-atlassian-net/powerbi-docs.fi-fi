---
title: Power BI:n URL-osoitteet
description: Tässä artikkelissa kuvataan päätepisteitä, joiden pitäisi olla Power BI -asiakkaiden tavoitettavissa.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/22/2018
ms.openlocfilehash: e62d39f13e2b171456d667ec9683acd4ebdc5516
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157122"
---
# <a name="power-bi-urls"></a>Power BI:n URL-osoitteet

**Power BI -verkkopalvelu**, joka tunnetaan myös nimellä Power BI SaaS (Software as a Service) -sovellus, edellyttää Internet-yhteyttä. Alla olevien päätepisteiden tulee olla Power BI -verkkopalvelua käyttävien asiakkaiden ulottuvilla.

Jotta voit käyttää Power BI -verkkopalvelua, sinun on voitava yhdistää päätepisteisiin, jotka on merkitty **pakollisiksi** alla olevissa taulukoissa ja päätepisteisiin, jotka on merkitty **pakollisiksi** linkitetyissä sivustoissa. Jos linkki ulkoiseen sivustoon viittaa tiettyyn osioon, sinun tarvitsee vain tarkistaa tämän osion päätepisteet.

**Valinnaisiksi** merkityt päätepisteet voidaan myös **lisätä sallittujen kohteiden luetteloon**, jotta tietty toiminto toimisi.

Power BI -verkkopalvelu edellyttää vain TCP-portin 443 avaamista luetteloiduille päätepisteille.

Yleismerkit (*) edustavat juuritason toimialueen alaisia kaikkia tasoja. Kun tietoja ei ole saatavilla, se on osoitettu merkillä –. **Kohteet**-sarakeluettelossa on täydellisiä toimialuenimiä/toimialueita ja linkkejä ulkoisiin sivustoihin, jotka sisältävät lisätietoja päätepisteistä.

>[!Important]
>Alla olevien taulukoiden tiedot eivät kata **Yhdysvaltojen hallituksen pilvipalvelua**, **Saksan pilvipalvelua** tai **Kiinan pilvipalvelua**.

## <a name="authentication"></a>Todentaminen

Power BI riippuu Office 365:n todentamisen ja tunnistetietojen osioissa vaadituista päätepisteistä. Jotta voit käyttää Power BI:tä, sinun on voitava yhdistää alla olevassa linkitetyssä sivustossa mainittuihin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
| --- | --- | --- | --- |
| 1 | **Pakollinen:** todentaminen ja tunnistetiedot | Tutustu Office 365 -ohjeeseen [Office Online ja yleiset URL-osoitteet](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)  | – |

## <a name="general-site-usage"></a>Yleinen sivuston käyttö

Power BI:n yleistä käyttöä varten sinun on voitava yhdistää taulukossa ja alla olevissa linkitetyissä sivustoissa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
| --- | --- | --- | --- |
| 1 | **Pakollinen:** taustan ohjelmointirajapinnat | *.analysis.windows.net | TCP 443 |
| 2 | **Pakollinen:** Office 365:n integrointi | Tutustu Office 365 -ohjeeseen [Office Online ja yleiset URL-osoitteet](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | – |
| 3 | **Pakollinen:** portaali | app.powerbi.com | TCP 443 |
| 4 | **Pakollinen:** palvelutelemetria | dc.services.visualstudio.com | TCP 443 |
| 5 | **Pakollinen:** tietoviestit | dynmsg.modpim.com | TCP 443 |
| 6 | **Pakollinen:** NPS-kyselyt | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>Hallinta

Jotta voit suorittaa järjestelmänvalvojan toimintoja Power BI:llä, sinun on voitava yhdistää alla linkitetyissä sivustoissa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
| --- | --- | --- | --- |
| 1 | **Pakollinen:** käyttäjien hallintaan ja valvontalokien tarkasteluun | Tutustu Office 365 -ohjeeseen [Office Online ja yleiset URL-osoitteet](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | – |
| | | |

## <a name="getting-data"></a>Tietojen hankkiminen

Jotta voit saada tietoja tietyistä tietolähteistä, kuten OneDrivesta, sinun on voitava yhdistää alla olevassa taulukossa oleviin päätepisteisiin. Saatat joutua käyttämään muita internet-toimialueita ja URL-osoitteita, jos organisaatiossasi käytetään muita tietolähteitä.

| Rivi | Tarkoitus | Kohteet | Portit |
| --- | --- | --- | --- |
| 1 | **Pakollinen:** AppSource (Power BI:n sisäiset tai ulkoiset sovellukset) | appsource.microsoft.com </br> *.s-microsoft.com  | TCP 443 |
| 2 | **Valinnainen:** kirjaudu sisään ja hanki sisältöpakettien tietoja | Riippuu käytetystä sisältöpaketista | Riippuu käytetystä sisältöpaketista |
| 3 | **Pakollinen:** tuo tiedostoja henkilökohtaisesta OneDrivesta | Katso [OneDrive-sivuston pakolliset URL-osoitteet ja portit](https://docs.microsoft.com/onedrive/required-urls-and-ports) | – |
| 4 | **Valinnainen:** Power BI:n 60 sekunnin opetusohjelmavideo | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 5 | **Valinnainen:** PubNub-suoratoiston tietolähteet | Katso [PubNub-dokumentaatio](https://support.pubnub.com/support/solutions/articles/14000043522) | – |
| | | |

## <a name="dashboard-and-report-integration"></a>Koontinäyttö ja raportin integrointi

Power BI riippuu tietyistä päätepisteistä, jotta se voi tukea koontinäyttöjä ja raportteja. Sinun on voitava yhdistää taulukossa ja alla olevissa linkitetyissä sivustoissa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
| --- | --- | --- | --- |
| 1 | **Pakollinen:** Excelin integrointi | Tutustu Office 365 -ohjeeseen [Office Online ja yleiset URL-osoitteet](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | – |
| | | |

## <a name="custom-visuals"></a>Mukautetut visualisoinnit

Power BI riippuu tietyistä päätepisteistä mukautettujen visualisointien tarkastelemiseksi ja käyttämiseksi. Sinun on voitava yhdistää taulukossa ja alla olevissa linkitetyissä sivustoissa oleviin päätepisteisiin.

| Rivi | Tarkoitus | Kohteet | Portit |
| --- | --- | --- | --- |
| 1 | **Pakollinen:** tuo mukautettu visualisointi Marketplace-liittymästä tai tiedostosta | *.azureedge.net </br> *.blob.core.windows.net </br> store.office.com | TCP 443 |
| 2 | **Pakollinen:** Bing-kartat | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **Valinnainen:** PowerApps | Katso [Pakolliset palvelut -osiota](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) PowerApps-järjestelmän vaatimukset -sivustosta | – |
| 4 | **Valinnainen:** Visio | Tutustu Office 365 -ohjeisiin [Office Online ja yleiset URL-osoitteet](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ja [SharePoint Online ja OneDrive for Business](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business) | – |
| | | |

## <a name="related-external-sites"></a>Aiheeseen liittyvät ulkoiset sivustot

Power BI -linkkejä muihin, aiheeseen liittyviin sivustoihin. Nämä verkkosivustot tarjoavat ohjeistusta, tukea, uusi ominaisuuspyyntöjä ja paljon muuta. Nämä sivustot eivät vaikuta Power BI:n toiminnallisuuteen, joten voit halutessasi lisätä ne sallittujen luetteloon.

| Rivi | Tarkoitus | Kohteet | Portit |
| --- | --- | --- | --- |
| 1 | **Valinnainen:** yhteisösivusto | community.powerbi.com </br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **Valinnainen:** dokumentaatiosivusto | docs.microsoft.com </br> img-prod-cms-rt-microsoft-com.akamaized.net </br> statics-uhf-eas.akamaized.net </br> cdnssl.clicktale.neting-district.clicktale.net | TCP 443 |
| 3 | **Valinnainen:** lataussivusto (Power BI Desktopille jne.) | download.microsoft.com | TCP 443 |
| 4 | **Valinnainen:** ulkoiset uudelleenohjaukset | aka.ms </br> go.microsoft.com | TCP 443 |
| 5 | **Valinnainen:** Ideas-palautesivusto| ideas.powerbi.com </br> powerbi.uservoice.com | TCP 443 |
| 6 | **Valinnainen:** Power BI -sivusto - aloitussivu, lue lisää -linkkejä, tukisivusto, latauslinkkejä, kumppanien esittelyjä jne. | powerbi.microsoft.com | TCP 443 |
| 7 | **Valinnainen:** Power BI -kehittäjäkeskus | dev.powerbi.com | TCP 443 |
| 8 | **Valinnainen:** tukisivusto | support.powerbi.com </br> s3.amazonaws.com </br> *.olark.com </br> logx.optimizely.com </br> mscom.demdex.net </br> tags.tiqcdn.com | TCP 443 |
| | | |