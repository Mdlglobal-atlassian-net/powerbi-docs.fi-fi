---
title: Upotettu analysointi Power BI:n avulla
description: Power BI tarjoaa ohjelmointirajapintoja, jotka mahdollistavat koontinäyttöjen ja raporttien upotetun analysoinnin käytön sovelluksissa. Lue lisää upottamisesta Power BI:n kanssa sekä PaaS-ympäristössä että SaaS-ympäristössä upotetun analysoinnin ohjelmiston, upotetun analysoinnin työkalujen tai upotetun liiketoimintatiedon työkalujen avulla.
author: rkarlin
ms.author: rkarlin
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
ms.date: 05/15/2019
ms.openlocfilehash: a212691f2af877e3b86e021a4f48644f4fa6e8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051055"
---
# <a name="embedded-analytics-with-power-bi"></a>Upotettu analysointi Power BI:n avulla

Power BI -palvelu (SaaS) ja Power BI Embedded -palvelu Azuressa (PaaS) sisältävät ohjelmointirajapintoja raporttinäkymien ja raporttien upottamista varten. Kun sisältöä upotetaan Tämä antaa sinulle käyttöoikeuden uusimpia Power BI-ominaisuuksia, kuten koontinäyttöjä, yhdyskäytäviä ja sovellustyötiloja.

Voit käyttää [upottamisen määritystyökalua](https://aka.ms/embedsetup) päästäksesi nopeasti alkuun ja ladataksesi mallisovelluksen.

Valitse ratkaisu, joka sopii sinulle:

* [Organisaatiolle tarkoitettu upotus](embedding.md#embedding-for-your-organization) mahdollistaa Power BI -palvelun laajentamisen. Voit tehdä tämän toteuttaa [organisaatiolle tarkoitettua](https://aka.ms/embedsetup/UserOwnsData) ratkaisu.
* [Upottaminen asiakkaiden käyttöön](embedding.md#embedding-for-your-customers) avulla voit upottaa koontinäyttöjä ja raportteja käyttäjille, joilla ei ole Power BI-tiliä. Voit tehdä tämän toteuttaa [asiakkaille tarkoitettua](https://aka.ms/embedsetup/AppOwnsData) ratkaisu.

![PBIE-malli](media/what-can-you-do/what-can-you-do-02.png)

## <a name="use-apis"></a>API-liittymien

On kaksi pääskenaariota: Power BI-sisällön upottamista varten:
- Upottaminen organisaation käyttäjien (joilla on Power BI-käyttöoikeudet). 
 
- Upottaminen käyttäjille ja asiakkaille, joilla ei välttämättä tarvitse Power BI-käyttöoikeuksia. 

[Power BI REST-Ohjelmointirajapinnan](https://docs.microsoft.com/rest/api/power-bi/) sallii molemmat skenaariot.

Niitä asiakkaita ja käyttäjiä varten, joilla ei ole Power BI-käyttöoikeuksia, voit upottaa koontinäyttöjä ja raportteja mukautettuun sovellukseen käyttäen samaa ohjelmointirajapintaa joko organisaatiosi tai asiakkaiden palvelemiseen. Asiakkaasi näkevät sovelluksen hallitsemille tiedoille. Lisäksi organisaation Power BI-käyttäjillä on tarkastella *tietonsa* suoraan Power BI-tai upotetun sovelluksen kontekstissa. Voit hyödyntää JavaScriptia ja REST-ohjelmointirajapintoja täysipainoisesti upotustarpeisiisi.

Ymmärtää, kuinka upottaminen toimii, näet [JavaScript-upotuksen näyte](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Upottaminen organisaation käyttöön

**Organisaatiolle tarkoitettu upotus** mahdollistaa Power BI -palvelun laajentamisen. Tämä upottaminen edellyttää sovelluksesi käyttäjät tarkastella sisältöä Power BI-palveluun. Kun organisaatiosi käyttäjä kirjautuu sisään, hän voi käyttää vain koontinäyttöjä ja raportteja, jotka hän omistaa tai jotka joku on jakanut hänen kanssaan Power BI -palvelussa.

Organisaation upottamisen esimerkkejä sisäinen sovellusten kuten [SharePoint Onlinen](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [Microsoft Teams-integrointi (edellyttää järjestelmänvalvojan oikeuksia)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/), ja [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard).

Jos haluat upottaa organisaatiollesi, katso [opetusohjelma: Power BI-sisällön upottaminen sovellukseen organisaatiosi](embed-sample-for-your-organization.md).

Itsepalvelutoiminnot, kuten muokkaus ja tallennus, ovat käytettävissä [JavaScript-ohjelmointirajapinnassa](https://github.com/Microsoft/PowerBI-JavaScript), kun käytetään upotusta Power BI -käyttäjille.

Voit käydä läpi [Embedding asennustyökalu](https://aka.ms/embedsetup/UserOwnsData) pääset alkuun ja ladata mallisovelluksen, joka opastaa, miten organisaatiosi raportti integroidaan.

## <a name="embedding-for-your-customers"></a>Upottaminen asiakkaiden käyttöön

**Upottaminen asiakkaiden käyttöön** avulla voit upottaa koontinäyttöjä ja raportteja käyttäjille, joilla ei ole Power BI-tiliä. Tämä upottaminen on tunnetaan myös *Power BI Embedded*.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) on **Microsoft Azure-** palvelu, jonka avulla ohjelmistotoimittajat (ISV) ja kehittäjille nopeasti upottaminen visualisointeja, raportteja ja koontinäyttöjä. Tämä upottaminen on valmis kapasiteettipohjainen, tunneittain käytön mukaan laskutettava mallin kautta.

![Asiakkaiden käyttöön upottamisen työnkulku](media/embedding/powerbi-embed-flow.png)

Power BI Embeddedistä on hyötyä riippumattomille ohjelmistotoimittajille, niiden kehittäjille ja asiakkaille. Esimerkiksi riippumaton ohjelmistotoimittaja voi aloittaa visualisointien luomisen ilmaiseksi Power BI Desktopilla. Pienentämällä visual analyyttisten kehitystyötä Ohjelmistotoimittajille saavuttaa nopeammin markkinoille ja kilpailijoihin erottuva tietojen kokemuksen erottuvat. Riippumattomille Ohjelmistotoimittajille myös päättää tehdä, jolta he luovat ja upotetut analyysitoiminnot muita arvon premium.

Power BI Embeddedin ansiosta asiakkaiden ei tarvitse tietää mitään Power BI:stä. Voit luoda upotetun sovelluksen kahdella eri tavalla:
- Power BI Pro-tili 
- Palvelun päänimi 

Power BI Pro-tili toimii sovelluksesi päätili (Voit ajatella sitä eräänlaisena välityspalvelimen tilinä). Tämän tilin avulla voit luoda upotettavia tunnuksia, jotka mahdollistavat pääsyn sovelluksesi Power BI-koontinäyttöjä ja raportteja.

[Palvelun päänimi](embed-service-principal.md) voi upottaa Power BI -sisältöä sovellukseen **sovelluksen** tunnuksen avulla. Sen avulla voit luoda myös upotustunnuksia, jotka mahdollistavat pääsyn sovelluksesi Power BI-koontinäyttöjä ja raportteja.

Kehittäjien Power BI Embedded voi käyttää keskittyy niiden sovelluksen perustoiminnot sijaan kulujen aika kehittämiseen visualisointeja ja analytics aikaa. Ne vastata asiakkaan raportin ja koontinäytön nopeasti ja helposti upottaa täysin dokumentoitu ohjelmointirajapintoja ja SDK-paketteja. Riippumattomat ohjelmistotoimittajat mahdollistavat asiakkaiden nopeiden ja tietoon perustuvien päätösten tekemisen kontekstissa mistä tahansa laitteesta, sillä tietojen välillä siirtyminen on sovelluksissa helppoa.

> [!IMPORTANT]
> Vaikka upottaminen edellyttää, että Power BI-palvelu, asiakkaiden ei tarvitse Power BI-tili, voit tarkastella sovelluksesi upotettua sisältöä. 

Kun olet valmis siirtymään tuotantoon, sovellustyötilallesi täytyy määrittää erillinen kapasiteetti. Microsoft Azureen sisältyvä Power BI Embedded tarjoaa sinulle [varattua kapasiteettia](azure-pbie-create-capacity.md) käyttöön sovellustesi kanssa.

Katso upottaa tiedot, [opit upottamaan Power BI-sisältöä](embed-sample-for-customers.md).

## <a name="next-steps"></a>Seuraavat vaiheet

Voit nyt kokeilla Power BI -sisällön upottamista sovellukseen tai asiakkaillesi.

> [!div class="nextstepaction"]
> [Upottaminen organisaatiollesi](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Mikä Power BI Embedded on?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Upottaminen asiakkaillesi](embed-sample-for-customers.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
