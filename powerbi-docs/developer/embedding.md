---
title: Upotettu analysointi Power BI:n avulla
description: Power BI tarjoaa ohjelmointirajapintoja, jotka mahdollistavat koontinäyttöjen ja raporttien upotetun analysoinnin käytön sovelluksissa. Lue lisää upottamisesta Power BI:n kanssa sekä PaaS-ympäristössä että SaaS-ympäristössä upotetun analysoinnin ohjelmiston, upotetun analysoinnin työkalujen tai upotetun liiketoimintatiedon työkalujen avulla.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
helpviewer_keywords:
- embedded analytics
- embedding
- Power BI embedding
- app owns data
- user owns data
- Power BI APIs
ms.custom: seodec18
ms.date: 02/05/2019
ms.openlocfilehash: 0a4b43bd02697472a0bbdf16171ba655fc014dbc
ms.sourcegitcommit: 3a05f34dbeabac62ea8c35c12a045284271971bc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/03/2019
ms.locfileid: "58872704"
---
# <a name="embedded-analytics-with-power-bi"></a>Upotettu analysointi Power BI:n avulla

Power BI -palvelu (SaaS) ja Power BI Embedded -palvelu Azuressa (PaaS) sisältävät ohjelmointirajapintoja raporttinäkymien ja raporttien upottamista varten. Tämä ominaisuus tarkoittaa, että saat tarvittavat ominaisuudet ja oikeudet käyttää uusimpia Power BI -toimintoja, kuten koontinäyttöjä, yhdyskäytäviä ja sovellustyötiloja, sisältöjen upottamiseen.

Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup) päästäksesi nopeasti alkuun ja ladataksesi mallisovelluksen.

Valitse ratkaisu, joka sopii sinulle:

* [Organisaatiolle tarkoitettu upotus](embedding.md#embedding-for-your-organization) mahdollistaa Power BI -palvelun laajentamisen. Suorita [organisaatiolle tarkoitettu upotus](https://aka.ms/embedsetup/UserOwnsData).
* [Asiakkaille tarkoitettu upotus](embedding.md#embedding-for-your-customers) mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Suorita [asiakkaille tarkoitettu upotus](https://aka.ms/embedsetup/AppOwnsData).

![PBIE-malli](media/what-can-you-do/what-can-you-do-02.png)

## <a name="using-apis"></a>Ohjelmointirajapintojen käyttäminen

Power BI-sisällön upottamisessa on kaksi pääskenaariota: upottaminen organisaation käyttäjien (joilla on Power BI -käyttöoikeudet) käyttöön sekä upottaminen käyttäjille ja asiakkaille, joilta ei edellytetä Power BI-käyttöoikeutta. Power BI REST -ohjelmointirajapinta sallii molemmat skenaariot.

Niitä asiakkaita ja käyttäjiä varten, joilla ei ole Power BI-käyttöoikeuksia, voit upottaa koontinäyttöjä ja raportteja mukautettuun sovellukseen käyttäen samaa ohjelmointirajapintaa joko organisaatiosi tai asiakkaiden palvelemiseen. Asiakkaasi näkevät tiedot, joita sovellus hallitsee. Organisaatiosi Power BI -käyttäjät voivat lisäksi tarkastella *omia tietojaan* suoraan Power BI:ssä tai upotetun sovelluksen kontekstissa. Voit hyödyntää JavaScriptia ja REST-ohjelmointirajapintoja täysipainoisesti upotustarpeisiisi.

Näyte siitä, kuinka upottaminen toimii, annetaan artikkelissa [JavaScript-upotuksen näyte](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Upottaminen organisaation käyttöön

**Organisaatiolle tarkoitettu upotus** mahdollistaa Power BI -palvelun laajentamisen. Organisaatiolle tarkoitettu upotus edellyttää, että sovelluksesi käyttäjät kirjautuvat Power BI -palveluun, kun he haluavat tarkastella sisältöään. Kun organisaatiosi käyttäjä kirjautuu sisään, hän voi käyttää vain koontinäyttöjä ja raportteja, jotka hän omistaa tai jotka joku on jakanut hänen kanssaan Power BI -palvelussa.

*Sisäiset sovellukset, kuten [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [Microsoft Teams -integrointi (sinulla on oltava järjestelmänvalvojan oikeudet)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) ja [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard), ovat esimerkkejä upottamisesta organisaation käyttöön.*

Organisaatiolle tarkoitetun upottamisen osalta katso seuraavia ohjeaiheita:

* [Raportin integrointi sovellukseen](embed-sample-for-your-organization.md)

Itsepalvelutoiminnot, kuten muokkaus ja tallennus, ovat käytettävissä [JavaScript-ohjelmointirajapinnassa](https://github.com/Microsoft/PowerBI-JavaScript), kun käytetään upotusta Power BI -käyttäjille.

Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup/UserOwnsData), jonka avulla pääset alkuun ja jolla voit ladata mallisovelluksen. Se opastaa, miten raportti integroidaan organisaatiollesi.

## <a name="embedding-for-your-customers"></a>Upottaminen asiakkaiden käyttöön

**Asiakkaille tarkoitettu upotus** mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Upottamista asiakkaiden käyttöön kutsutaan myös nimellä **Power BI Embedded**.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) on **Microsoft Azure** -palvelu, jonka avulla riippumattomat ohjelmistotoimittajat ja -kehittäjät voivat upottaa nopeasti upeita visualisointeja, raportteja ja raporttinäkymiä sovelluksiin kapasiteettipohjaisen, tunneittain käytön mukaan laskutettavan mallin kautta.

![Asiakkaiden käyttöön upottamisen työnkulku](media/embedding/powerbi-embed-flow.png)

Power BI Embeddedistä on hyötyä riippumattomille ohjelmistotoimittajille, niiden kehittäjille ja asiakkaille. Esimerkiksi riippumaton ohjelmistotoimittaja voi aloittaa visualisointien luomisen ilmaiseksi Power BI Desktopilla. Riippumattomat ohjelmistotoimittajat voivat päästä nopeammin markkinoille vähentämällä visuaalista analyyttistä kehitystyötä ja erottumalla kilpailijoista eriytetyillä kokemuksilla tiedoista. Riippumattomat ohjelmistotoimittajat voivat halutessaan veloittaa palkkion upotettujen analyysitoimintojen avulla luodusta lisäarvosta.

Power BI Embeddedin ansiosta asiakkaiden ei tarvitse tietää mitään Power BI:stä. Voit luoda upotetun sovelluksen kahdella eri tavalla. Voit käyttää Power BI Pro -tiliä. Voit käyttää myös palvelun päänimeä. 

Power BI Pro -tili toimii sovelluksesi päätilinä (tätä päätiliä voi pitää eräänlaisena välitystilinä). Power BI Pro -tilin avulla voit luoda upotustunnuksia, jotka mahdollistavat sovelluksesi omistamien ja hallitsemien koontinäyttöjen sekä raporttien käytön Power BI -palvelussa.

[Palvelun päänimi](embed-service-principal.md) voi upottaa Power BI -sisältöä sovellukseen **sovelluksen** tunnuksen avulla. Palvelun päänimen avulla voit luoda upotustunnuksia, jotka mahdollistavat sovelluksesi omistamien ja hallitsemien koontinäyttöjen sekä raporttien käytön Power BI -palvelussa.

Power BI Embeddedia käyttävät kehittäjät voivat keskittyä kehittämään sovelluksen keskeisiä toimintoja visualisointien ja analytiikan kehittämisen sijaan. Kehittäjät voivat nopeasti vastata asiakkaan raporttiin ja koontinäyttöön liittyviin vaatimuksiin ja upottaa helposti täysin dokumentoituja ohjelmointirajapintoja ja SDK:ita. Riippumattomat ohjelmistotoimittajat mahdollistavat asiakkaiden nopeiden ja tietoon perustuvien päätösten tekemisen kontekstissa mistä tahansa laitteesta, sillä tietojen välillä siirtyminen on sovelluksissa helppoa.

> [!IMPORTANT]
> Vaikka upottaminen on riippuvaista Power BI-palvelusta, asiakkaasi eivät ole riippuvaisia Power BI:stä. Heidän ei tarvitse rekisteröityä Power BI -käyttäjiksi, jotta he voisivat tarkastella upotettua sisältöä sovelluksessasi.

Kun olet valmis siirtymään tuotantoon, sovellustyötilallesi täytyy määrittää erillinen kapasiteetti. Microsoft Azureen sisältyvä Power BI Embedded tarjoaa sinulle [varattua kapasiteettia](azure-pbie-create-capacity.md) käyttöön sovellustesi kanssa.

Jos haluat lisätietoja upottamisesta, lue ohjeartikkeli [Power BI -sisällön upottaminen](embed-sample-for-customers.md).

## <a name="next-steps"></a>Seuraavat vaiheet

Voit nyt kokeilla Power BI -sisällön upottamista sovellukseen tai asiakkaillesi.

> [!div class="nextstepaction"]
> [Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Mikä Power BI Embedded on?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Upottaminen asiakkaillesi](embed-sample-for-customers.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
