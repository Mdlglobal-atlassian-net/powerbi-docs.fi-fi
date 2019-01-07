---
title: Power BI Embeddedin suorituskykyä parantavat parhaat käytännöt
description: Tässä artikkelissa annetaan ohjeita upotettujen analyysitoimintojen parhaisiin käytäntöihin
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: d0f4ca29e30e5f6e6176f036dc535601eb580471
ms.sourcegitcommit: 298db44200b78b1281b3ae6dfe7cce7a89865ec9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/13/2018
ms.locfileid: "53329874"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Power BI Embeddedin suorituskykyä parantavat parhaat käytännöt

Tässä artikkelissa on suosituksia, joiden avulla nopeutat sovelluksesi raporttien, koontinäyttöjen, ja ruutujen hahmontamista

## <a name="embed-parameters"></a>Upotetut parametrit

Powerbi.embed()-menetelmä vastaanottaa muutamia parametreja raportin, koontinäytön tai ruudun upottamista varten. Nämä parametrit vaikuttavat suorituskykyyn.

### <a name="embed-url"></a>Upota URL-osoite

Vältä upotetun URL-osoitteen muodostamista itse. Varmista sen sijaan, että hankit upotetun URL-osoitteen kutsumalla [raporttien](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Freports%2Fgetreportsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=22lkqRM2w1MQfrM8dooedaPqqIU8PufTq9TT4VDzRo0%3D&reserved=0), [koontinäyttöjen](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgetdashboardsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=nfWRgbSoXVF42Rg%2Ba9491u19uksXp%2FAyz%2Fa%2Ba7%2FCtdA%3D&reserved=0) tai [ruutujen](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgettilesingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256178318&sdata=LgZ27TynNpqQJDrb3aHWGQXIS%2FzichAO9De5M2uhF1Q%3D&reserved=0) kutsumisen ohjelmointirajapintaa. Olemme lisänneet URL-osoitteeseen uuden **_config_**-nimisen parametrin, jota käytetään suorituskyvyn parantamiseen.

### <a name="permissions"></a>Käyttöoikeudet

Anna **tarkasteluoikeudet**, jos et aio upottaa raporttia **muokkaustilassa**. Näin upotuskoodi ei alusta osia, joita käytetään muokkaustilassa.

### <a name="filters-bookmarks-and-slicers"></a>Suodattimet, kirjanmerkit ja osittajat

Yleensä raportin visualisoinnit tallennetaan välimuistiin tallennettujen tietojen kanssa. Välimuistiin tallennettuja tietoja käytetään halutun suorituskyvyn varmistamiseen. Raportit hahmontavat välimuistiin tallennettuja tietoja, kun kyselyjä suoritetaan. Jos käytetään suodattimia, kirjanmerkkejä tai osittajia, välimuistiin tallennetuilla tiedoilla ei ole merkitystä. Silloin visualisoinnit hahmonnetaan vasta visualisointikyselyn suorittamisen jälkeen.

Jos upotat raporttien kanssa samoja suodattimia, sinun ei tarvitse välittää latauskokoonpanossa suodatinluetteloa, kun tallennat raportin suodattimet valmiiksi käytössä.

## <a name="preload"></a>Esilataus

Käytä JavaScript-ohjelmointirajapinnan *esilatausta* suorituskyvyn parantamiseksi loppukäyttäjän kannalta.
Powerbi.preload()-menetelmä lataa Javascriptin, CSS-tiedostot ja muut artefaktit, joita käytetään myöhemmin raporttiin upottamisessa.

Kutsu esilataus, jos et ole upottamassa raporttia heti. Jos esimerkiksi upotat raportin painiketta napsauttamalla, esilataus kannattaa kutsua, kun edellinen sivu latautuu. Kun sovelluksen käyttäjä sitten napsauttaa painiketta, hahmontaminen on nopeampaa.

## <a name="measure-performance"></a>Mittaa suorituskykyä

Mittaa suorituskykyä käyttämällä seuraavia tapahtumia:

1. Loaded: aika raportin alustamiseen (käyttäjä ei näe pyörivää kuvaketta).
2. Rendered: aika raportin täyteen hahmontamiseen todellisia tietoja käyttämällä. Rendered-tapahtuma käynnistetään aina, kun raportti hahmonnetaan uudelleen (suodatinten käyttämisen jälkeen). Jos haluat mitata raportin ensin, suorita laskelmat ensimmäisessä käynnistettävässä tapahtumassa.

Välimuistiin tallennetut tiedot hahmonnetaan, kun ne ovat käytettävissä, mutta näille tiedoille ei ole vielä tapahtumaa.

## <a name="update-tools-and-sdk-packages"></a>Työkalujen ja SDK-pakettien päivittäminen

Pidä työkalut ja SDK-paketit ajan tasalla.

* Käytä aina [Power BI Desktopin](https://powerbi.microsoft.com/en-us/desktop/) uusinta versiota.

* Asenna [Power BI -asiakasohjelman SDK-paketin](https://github.com/Microsoft/PowerBI-JavaScript) uusin versio. Jatkamme parannusten julkaisemista, joten tarkista tilanne aina välillä.

* Asennettavat paketit:
    * Npm-paketti: powerbi-client
    * NuGet-paketti: Microsoft.PowerBI.JavaScript

> [!Note]
> Muista, että latausaika riippuu pääasiassa raportille ja itse tiedoille relevanteista elementeistä. Niitä ovat esimerkiksi visualisointien määrä, tietojen koko sekä kyselyjen ja laskettujen mittayksikköjen monimutkaisuus. Paranna raportin latausaikaa noudattamalla [parhaita käytäntöjä](../power-bi-reports-performance.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Raportin suorituskyky](../power-bi-reports-performance.md)
* [Power BI Embeddedin ongelmien vianmääritys](embedded-troubleshoot.md)
* [Power BI Embedded: usein kysytyt kysymykset](embedded-faq.md)
