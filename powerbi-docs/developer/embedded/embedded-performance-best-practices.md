---
title: Power BI Embeddedin suorituskykyä parantavat parhaat käytännöt
description: Tässä artikkelissa annetaan ohjeita upotettujen analyysitoimintojen parhaisiin käytäntöihin
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: c619f37ac062eec02eb379ba7cd97731254a171a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279384"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Power BI Embeddedin suorituskykyä parantavat parhaat käytännöt

Tässä artikkelissa on suosituksia, joiden avulla nopeutat sovelluksesi raporttien, koontinäyttöjen, ja ruutujen hahmontamista.

> [!Note]
> Muista, että latausaika riippuu pääasiassa raporttiin ja itse tietoihin liittyvistä elementeistä, kuten visualisoinneista, tietojen koosta ja kyselyjen ja laskettujen mittareiden monimutkaisuudesta. Lisätietoja on artikkelissa [Power BI:n optimointiopas](../../guidance/power-bi-optimization.md).

## <a name="update-tools-and-sdk-packages"></a>Työkalujen ja SDK-pakettien päivittäminen

Pidä työkalut ja SDK-paketit ajan tasalla.

* Käytä aina [Power BI Desktopin](https://powerbi.microsoft.com/desktop/) uusinta versiota.

* Asenna [Power BI -asiakasohjelman SDK-paketin](https://github.com/Microsoft/PowerBI-JavaScript) uusin versio. Julkaisemme parannuksia jatkuvasti, joten tarkista tilanne aina välillä.

## <a name="embed-parameters"></a>Upotetut parametrit

`powerbi.embed(element, config)`-menetelmä vastaanottaa elementin ja määrityksen. Määritysparametri sisältää kenttiä, joilla on vaikutuksia suorituskykyyn.

### <a name="embed-url"></a>Upota URL-osoite

Vältä upotetun URL-osoitteen muodostamista itse. Varmista sen sijaan, että hankit upotetun URL-osoitteen kutsumalla [raporttien](/rest/api/power-bi/reports/getreportsingroup), [koontinäyttöjen](/rest/api/power-bi/dashboards/getdashboardsingroup) tai [ruutujen](/rest/api/power-bi/dashboards/gettilesingroup) kutsumisen ohjelmointirajapintaa. Olemme lisänneet URL-osoitteeseen uuden **_config_** -nimisen parametrin, jota käytetään suorituskyvyn parantamiseen.

### <a name="permissions"></a>Käyttöoikeudet

Anna **tarkasteluoikeudet**, jos et aio upottaa raporttia muokkaustilassa. Näin upotuskoodi ei alusta osia, joita käytetään muokkaustilassa.

### <a name="filters-bookmarks-and-slicers"></a>Suodattimet, kirjanmerkit ja osittajat

Yleensä raportin visualisoinnit tallennetaan välimuistiin tallennettujen tietojen kanssa. Välimuistiin tallennettuja tietoja käytetään halutun suorituskyvyn varmistamiseen. Raportit hahmontavat välimuistiin tallennettuja tietoja, kun kyselyjä suoritetaan. Jos käytössä on suodattimia, kirjanmerkkejä tai osittajia, välimuistiin tallennetut tiedot eivät ole olennaisia ja visualisoinnit hahmonnetaan vasta sen jälkeen, kun visuaalinen kysely on päättynyt.

Jos upotat raportteja samoilla suodattimella, kirjanmerkeillä ja osittajilla, voit parantaa suorituskykyä tallentamalla raportti jo siinä käytetyillä suodattimilla, kirjanmerkeillä ja osittajilla. Tämä hahmontaa raportin välimuistissa olevilla tiedoilla, jotka sisältävät suodattimet, kirjanmerkit ja osittajat.

## <a name="switching-between-reports"></a>Raporttien välillä siirtyminen

Kun upotat useita raportteja samaan iframe-kehykseen, älä luo uutta iframea kullekin raportille. Käytä sen sijaan `powerbi.embed(element, config)`-kohdetta eri määrityksellä uuden raportin upottamiseen.

> [!NOTE]
> "Sovellus omistaa tiedot" -skenaarion välillä siirtyminen ei välttämättä ole kovin tehokasta, koska uuden upotustunnuksen luominen on välttämätöntä.

## <a name="query-caching"></a>Kyselyn tallentaminen välimuistiin

Power BI Premiumi -kapasiteettia tai Power BI Embedded -kapasiteettia käyttävät organisaatiot voivat hyödyntää kyselyn tallentamista välimuistiin tietojoukkoon liittyvien raporttien nopeuttamiseksi.

[Lue lisätietoja kyselyiden tallentamisesta välimuistiin Power BI:ssä](../../connect-data/power-bi-query-caching.md).

## <a name="preload"></a>Esilataus

Voit parantaa suoritustehoa loppukäyttäjällä käyttämällä `powerbi.preload()`-menetelmää. `powerbi.preload()`-menetelmä lataa Javascriptin, CSS-tiedostot ja muut artefaktit, joita käytetään myöhemmin raporttiin upottamisessa.

Kutsu `powerbi.preload()`, jos et ole upottamassa raporttia heti. Jos esimerkiksi upotettua Power BI -sisältöä ei näy aloitussivulla, lataa ja tallenna välimuistiin sisällön upottamiseen käytettävät artefaktit `powerbi.preload()`-menetelmän avulla.

## <a name="bootstrapping-the-iframe"></a>iframe-kehyksen käynnistäminen

> [!NOTE]
> [Power BI -asiakkaan SDK](https://github.com/Microsoft/PowerBI-JavaScript) versio 2.9 vaaditaan iframe-kehyksen käynnistämiseen.

`powerbi.bootstrap(element, config)`-menetelmän avulla voit aloittaa upottamisen, ennen kuin kaikki vaaditut parametrit ovat käytettävissä. Käynnistyksen ohjelmointirajapinta valmistelee ja alustaa iframe-kehyksen.
Kun käytät käynnistyksen ohjelmointirajapintaa, sinun on silti kutsuttava saman HTML-elementin `powerbi.embed(element, config)`-menetelmää.

Yksi tämän ominaisuuden käyttötapa on esimerkiksi iframe-kehyksen käynnistyksen ja upottamisen taustakutsujen suorittaminen rinnakkain.
> [!TIP]
> Käytä käynnistyksen ohjelmointirajapintaa, kun iframe-kehys voidaan luoda ennen sen näkymistä käyttäjälle.

[Lue lisätietoja iframe-käynnistyksestä](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bootstrap-For-Better-Performance).

## <a name="measure-performance"></a>Mittaa suorituskykyä

### <a name="performance-events"></a>Suorituskykytapahtumat

Jos haluat mitata upotettua suorituskykyä, voit käyttää kahta tapahtumaa:

1. Ladattu tapahtuma: Aika raportin alustamiseen (Power BI -logo katoaa näkyvistä, kun lataus on valmis).
2. Hahmonnettu tapahtuma: Aika raportin täyteen hahmontamiseen todellisia tietoja käyttämällä. Hahmonnettu tapahtuma käynnistetään aina, kun raportti hahmonnetaan uudelleen (esimerkiksi suodatinten käyttämisen jälkeen). Jos haluat mitata raportin, suorita laskelmat ensimmäisessä käynnistettävässä tapahtumassa.

Välimuistissa olevat tiedot hahmonnetaan, kun ne ovat käytettävissä, mutta lisätapahtumaa ei luoda.

[Lue lisätietoja tapahtumien käsittelystä](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

### <a name="performance-analyzer"></a>Suorituskyvyn analysointi

Jos haluat tarkastella raporttielementtien suorituskykyä, voit käyttää Power BI Desktopin suorityskyvyn analysointia.
Suorityskyvyn analysointi -toiminnon avulla voit tarkastella ja kirjata lokeja, jotka mittaavat kunkin raporttielementin suorityskyvyn.

[Lue lisätietoja suorityskyvyn analysoinnista](../../create-reports/desktop-performance-analyzer.md).

> [!NOTE]
> Muista aina verrata upotetun raportin suorituskykyä suorituskykyyn powerbi.comissa. Tämä saattaa auttaa ymmärtämään suorituskykyyn liittyvien ongelmien alkuperän.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Power BI:n optimointiopas](../../guidance/power-bi-optimization.md)
* [Power BI Embeddedin ongelmien vianmääritys](embedded-troubleshoot.md)
* [Power BI Embedded: usein kysytyt kysymykset](embedded-faq.md)
