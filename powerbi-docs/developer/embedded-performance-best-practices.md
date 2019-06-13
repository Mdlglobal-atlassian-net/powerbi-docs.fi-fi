---
title: Power BI Embeddedin suorituskykyä parantavat parhaat käytännöt
description: Tässä artikkelissa annetaan ohjeita upotettujen analyysitoimintojen parhaisiin käytäntöihin
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: d2e4a29b3dd7e36081458ff6ca51b0006a10466f
ms.sourcegitcommit: 81ba3572531cbe95ea0b887b94e91f94050f3129
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/06/2019
ms.locfileid: "66750950"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Power BI Embeddedin suorituskykyä parantavat parhaat käytännöt

Tässä artikkelissa on suosituksia, joiden avulla nopeutat sovelluksesi raporttien, koontinäyttöjen, ja ruutujen hahmontamista

## <a name="embed-parameters"></a>Upotetut parametrit

Powerbi.embed()-menetelmä vastaanottaa muutamia parametreja raportin, koontinäytön tai ruudun upottamista varten. Nämä parametrit vaikuttavat suorituskykyyn.

### <a name="embed-url"></a>Upota URL-osoite

Vältä upotetun URL-osoitteen muodostamista itse. Varmista sen sijaan, että hankit upotetun URL-osoitteen kutsumalla [raporttien](/rest/api/power-bi/reports/getreportsingroup), [koontinäyttöjen](/rest/api/power-bi/dashboards/getdashboardsingroup) tai [ruutujen](/rest/api/power-bi/dashboards/gettilesingroup) kutsumisen ohjelmointirajapintaa. Olemme lisänneet URL-osoitteeseen uuden **_config_** -nimisen parametrin, jota käytetään suorituskyvyn parantamiseen.

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

* Käytä aina [Power BI Desktopin](https://powerbi.microsoft.com/desktop/) uusinta versiota.

* Asenna [Power BI -asiakasohjelman SDK-paketin](https://github.com/Microsoft/PowerBI-JavaScript) uusin versio. Jatkamme parannusten julkaisemista, joten tarkista tilanne aina välillä.

* Asennettavat paketit:
    * Npm-paketti: powerbi-client
    * NuGet-paketti: Microsoft.PowerBI.JavaScript

> [!Note]
> Muista, että latausaika riippuu pääasiassa raportille ja itse tiedoille relevanteista elementeistä. Niitä ovat esimerkiksi visualisointien määrä, tietojen koko sekä kyselyjen ja laskettujen mittarien monimutkaisuus. Paranna raportin latausaikaa noudattamalla [parhaita käytäntöjä](../power-bi-reports-performance.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* [Power BI -raportin suorituskyvyn parhaat käytännöt](../power-bi-reports-performance.md)
* [Power BI Embeddedin ongelmien vianmääritys](embedded-troubleshoot.md)
* [Power BI Embedded: usein kysytyt kysymykset](embedded-faq.md)
