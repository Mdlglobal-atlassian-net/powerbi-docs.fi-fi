---
title: Upottaminen Power BI:llä
description: Power BI tarjoaa ohjelmointirajapintoja, jotka mahdollistavat koontinäyttöjen ja raporttien upottamisen sovelluksiin.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: overview
ms.date: 07/31/2018
ms.openlocfilehash: 2889345c5e4a5e93602c51baa27bf2c7e28e138f
ms.sourcegitcommit: 16098be04df05bc8e3d44a99b4d143b622759c59
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/07/2018
ms.locfileid: "39616024"
---
# <a name="embedding-with-power-bi"></a>Upottaminen Power BI:llä

Power BI -palvelu (SaaS) ja Power BI Embedded -palvelu Azuressa (PaaS) sisältävät ohjelmointirajapintoja raporttinäkymien ja raporttien upottamista varten. Se tarkoittaa, että saat tarvittavat ominaisuudet ja oikeudet käyttää uusimpia Power BI -toimintoja, kuten koontinäyttöjä, yhdyskäytäviä ja sovellustyötiloja, sisältöjen upottamiseen.

Voit käyttää [Perehdyttämiskokemustyökalua](https://aka.ms/embedsetup) aloittaaksesi ja ladataksesi mallisovelluksen nopeasti.

Valitse ratkaisu, joka sopii sinulle:

* [Organisaatiolle tarkoitettu upotus](embedding.md#embedding-for-your-organization) mahdollistaa Power BI -palvelun laajentamisen. Suorita [organisaatiolle tarkoitettu upotus](https://aka.ms/embedsetup/UserOwnsData).
* [Asiakkaille tarkoitettu upotus](embedding.md#embedding-for-your-customers) mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Suorita [asiakkaille tarkoitettu upotus](https://aka.ms/embedsetup/AppOwnsData).

![PBIE-malli](media/what-can-you-do/what-can-you-do-02.png)

## <a name="using-apis"></a>Ohjelmointirajapintojen käyttäminen

Power BI-sisällön upottamisessa on kaksi pääskenaariota:  upottaminen organisaation käyttäjien (joilla on Power BI -käyttöoikeudet) käyttöön sekä upottaminen käyttäjille ja asiakkaille, joilta ei edellytetä Power BI-käyttöoikeutta. Power BI REST -ohjelmointirajapinta sallii molemmat skenaariot.

Niitä asiakkaita ja käyttäjiä varten, joilla ei ole Power BI-käyttöoikeuksia, voit upottaa koontinäyttöjä ja raportteja mukautettuun sovellukseen käyttäen samaa ohjelmointirajapintaa joko organisaatiosi tai asiakkaiden palvelemiseen. Asiakkaasi näkevät tiedot, joita sovellus hallitsee. Power BI -käyttäjät organisaatiossasi voivat lisäksi tarkastella *omia tietojaan* suoraan Power BI:ssä tai upotetun sovelluksen kontekstissa. Voit hyödyntää JavaScriptia ja REST-ohjelmointirajapintoja täysipainoisesti upotustarpeisiisi.

Näyte siitä, kuinka upottaminen toimii, annetaan artikkelissa [JavaScript-upotuksen näyte](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Upottaminen organisaation käyttöön

**Organisaatiolle tarkoitettu upotus** mahdollistaa Power BI -palvelun laajentamisen. Organisaatiolle tarkoitettu upotus edellyttää, että sovelluksesi käyttäjät kirjautuvat Power BI -palveluun, kun he haluavat tarkastella sisältöään. Kun käyttäjä organisaatiossasi kirjautuu sisään, hän voi käyttää vain koontinäyttöjä ja raportteja, jotka hän omistaa tai jotka on jaettu hänen kanssaan Power BI -palvelussa.

*Sisäinen sovellus, [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [Microsoft Teams -integrointi (sinulla on oltava järjestelmänvalvojan oikeudet)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) ja [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) ovat esimerkkejä upottamisesta organisaation käyttöön.*

Organisaation käyttöön upottamisen osalta katso seuraavia ohjeaiheita:

* [Raportin integrointi sovellukseen](embed-sample-for-your-organization.md)

Itsepalvelutoiminnot, kuten muun muassa muokkaus ja tallennus, ovat käytettävissä [JavaScript-ohjelmointirajapinnassa](https://github.com/Microsoft/PowerBI-JavaScript), kun käytetään upotusta Power BI -käyttäjien käyttöön.

Voit käyttää [yrityksesi käytössä olevaa upottamiseen tarkoitettua perehdyttämistyökalua](https://aka.ms/embedsetup/UserOwnsData), jonka avulla pääset nopeasti alkuun ja voit ladata mallisovelluksen, joka opastaa, miten raportti integroidaan yrityksessäsi.

## <a name="embedding-for-your-customers"></a>Upottaminen asiakkaiden käyttöön

**Asiakkaille tarkoitettu upotus** mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Upottamista asiakkaiden käyttöön kutsutaan myös nimellä **Power BI Embedded**.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) on **Microsoft Azure** -palvelu, jonka avulla riippumattomat ohjelmistotoimittajat ja -kehittäjät voivat upottaa nopeasti upeita visualisointeja, raportteja ja raporttinäkymiä sovelluksiin kapasiteettipohjaisen, tunneittain käytön mukaan laskutettavan mallin kautta.

![Asiakkaiden käyttöön upottamisen työnkulku](media/embedding/powerbi-embed-flow.png)

Power BI Embeddedistä on hyötyä riippumattomille ohjelmistotoimittajille, niiden kehittäjille ja asiakkaille. Esimerkiksi riippumaton ohjelmistotoimittaja voi aloittaa visualisointien luomisen ilmaiseksi Power BI Desktopilla. Riippumattomat ohjelmistotoimittajat voivat päästä nopeammin markkinoille vähentämällä visuaalista analyyttistä kehitystyötä ja erottumalla kilpailijoista eriytetyillä kokemuksilla tiedoista. Riippumattomat ohjelmistotoimittajat voivat halutessaan veloittaa palkkion upotettujen analyysitoimintojen avulla luodusta lisäarvosta.

Power BI Embeddedin ansiosta asiakkaiden ei tarvitse tietää mitään Power BI:stä. Upotetun sovelluksen luomiseen tarvitaan vain yksi Power BI Pro -tili. Power BI Pro -tili toimii sovelluksesi päätilinä (tätä voi pitää eräänlaisena välitystilinä). Power BI Pro -tilin avulla voit luoda myös upotustunnuksia, jotka mahdollistavat pääsyn sovelluksesi omistamiin/hallitsemiin koontinäyttöihin ja raportteihin Power BI -palvelussa.

Power BI Embeddedia käyttävät kehittäjät voivat keskittyä kehittämään sovelluksen keskeisiä toimintoja visualisointien ja analytiikan kehittämisen sijaan. Kehittäjät voivat nopeasti vastata asiakkaan raporttiin ja koontinäyttöön liittyviin vaatimuksiin ja upottaa helposti täysin dokumentoituja ohjelmointirajapintoja ja SDK:ita. Riippumattomat ohjelmistotoimittajat mahdollistavat asiakkaiden nopeiden ja tietoon perustuvien päätösten tekemisen kontekstissa mistä tahansa laitteesta, sillä tietojen välillä siirtyminen on sovelluksissa helppoa.

> [!IMPORTANT]
> Vaikka upottaminen on riippuvaista Power BI-palvelusta, asiakkaasi eivät ole riippuvaisia Power BI:stä. Heidän ei tarvitse rekisteröityä Power BI -käyttäjiksi, jotta he voisivat tarkastella upotettua sisältöä sovelluksessasi.

Kun olet valmis siirtymään tuotantoon, sovellustyötilallesi täytyy määrittää erillinen kapasiteetti. Microsoft Azureen sisältyvä Power BI Embedded tarjoaa sinulle [varattua kapasiteettia](azure-pbie-create-capacity.md) käyttöön sovellustesi kanssa.

Saat upottamista koskevia yksityiskohtaisia tietoja artikkelista [Power BI:n koontinäyttöjen, raporttien ja ruutujen upottaminen](embed-sample-for-customers.md).

## <a name="next-steps"></a>Seuraavat vaiheet

Voit nyt kokeilla Power BI -sisällön upottamista sovellukseen tai asiakkaillesi.

> [!div class="nextstepaction"]
> [Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Mikä Power BI Embedded on?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Upottaminen asiakkaillesi](embed-sample-for-customers.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)