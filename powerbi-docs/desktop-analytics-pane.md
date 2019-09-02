---
title: Analytiikka-ruudun käyttäminen Power BI Desktopissa
description: Dynaamisten viiteviivojen luominen visualisointeihin Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 861a1d43f023e3ceba17fba90bcbc703e3195c84
ms.sourcegitcommit: c0f4d00d483121556a1646b413bab75b9f309ae9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/29/2019
ms.locfileid: "70160188"
---
# <a name="using-the-analytics-pane-in-power-bi-desktop"></a>Analytiikka-ruudun käyttäminen Power BI Desktopissa
**Power BI Desktopin** **Analytiikka**-ruudussa voit lisätä dynaamisia *viiteviivoja* visualisointeihin ja määrittää kohdistuksen tärkeille trendeille tai merkityksellisille tiedoille. **Analytiikka**-ruutu sijaitsee Power BI Desktopin **Visualisoinnit**-alueella.

![](media/desktop-analytics-pane/analytics-pane_1.png)

> [!NOTE]
> **Analytiikka**-ruutu näkyy ainoastaan, jos valitset visualisoinnin Power BI Desktop -pohjalla.

## <a name="search-within-the-analytics-pane"></a>Haku Analytiikka-ruudussa
Helmikuun 2018 **Power BI Desktop** -julkaisusta (versio 2.55.5010.201 tai uudempi) alkaen voit tehdä hakuja **Analytiikka**-ruudussa, joka on **Visualisoinnit** -ruudun alaosio. Hakuruutu tulee näkyviin, kun **Analytiikka**-ruutu valitaan, kuten alla olevassa kuvassa on esitetty.

![](media/desktop-analytics-pane/analytics-pane_1b.png)

## <a name="using-the-analytics-pane"></a>Analytiikka-ruudun käyttäminen
**Analytiikka**-ruudussa voit luoda seuraavanlaisia dynaamisia viiteviivoja (kaikki viivat eivät ole käytettävissä kaikkien visualisointityyppien tapauksessa):

* X-akselin yhtenäinen viiva
* Y-akselin yhtenäinen viiva
* Pienimmän arvon viiva
* Suurimman arvon viiva
* Keskiarvon viiva
* Mediaanin viiva
* Prosenttipisteviiva

Seuraavissa osiossa esitetään, kuinka voit käyttää **Analytiikka**-ruutua ja dynaamisia viiteviivoja visualisoinneissa.

Voit tarkastella tietylle visualisoinnille käytettävissä olevia dynaamisia viiteviivoja noudattamalla seuraavia ohjeita:

1. Valitse tai luo visualisointi ja valitse sitten **Analytiikka**-kuvake **Visualisoinnit**-osiosta.
   
   ![](media/desktop-analytics-pane/analytics-pane_2.png)
2. Valitse alanuoli luotavan viivatyypin kohdalla, jotta saat sen asetukset näkyviin. Tässä tapauksessa valitaan **Keskiarvon viiva**.
   
   ![](media/desktop-analytics-pane/analytics-pane_3.png)
3. Luo uusi viiva valitsemalla **+ Lisää**. Voit sitten määrittää viivalle nimen kaksoisnapsauttamalla tekstiruutua ja kirjoittamalla haluamasi nimen.
   
   Viivalle on mahdollista valita monenlaisia asetuksia, kuten *väri*, *läpinäkyvyys*, *tyyli* ja *sijainti* (suhteessa visualisoinnin tietoelementteihin) sekä mahdollisen otsikon sisällyttäminen. Voit myös valita, mihin visualisoinnin **mittariin** haluat viivan perustuvan, valitsemalla avattavan **Mittari**-luettelon, joka täyttyy automaattisesti visualisoinnin tietoelementeillä. Tässä esimerkkitapauksessa valitsemme mittarin *Sää*, annamme sille otsikon *Keskimääräinen sää* ja mukautamme muutamia muita asetuksia alla esitetyllä tavalla.
   
   ![](media/desktop-analytics-pane/analytics-pane_4.png)
4. Jos haluat arvopisteen otsikon näkyvän, liikuta **Arvopisteen otsikko** -liukusäädintä. Tekemällä niin saat näkyviin koko joukon arvopisteen otsikon lisäasetuksia, kuten seuraavassa kuvassa esitetään.
   
   ![](media/desktop-analytics-pane/analytics-pane_5.png)
5. Huomioi luku, joka näkyy **Keskiarvon viiva** -kohdan vieressä **Analytiikka**-ruudussa. Se kertoo sinulle, kuinka monta dynaamista viivaa sinulla on tällä hetkellä visualisoinnissa ja minkä tyyppisiä ne ovat. Jos lisäämme **suurimman arvon viivan** *Elinkustannukset*-visualisointiin, huomaat, että **Analytiikka**-ruudussa näkyy, että tässä visualisoinnissa on nyt käytössä myös dynaaminen **Suurimman arvon viiva** -viiteviiva.
   
   ![](media/desktop-analytics-pane/analytics-pane_6.png)

Jos valitsemassasi visualisoinnissa (Tässä tapauksessa **Kartta**-visualisoinnissa) ei voi käyttää dynaamisia viiteviivoja, näkyviin tulee seuraava viesti, kun valitset **Analytiikka**-ruudun.

![](media/desktop-analytics-pane/analytics-pane_7.png)

Voit korostaa kaikenlaisia merkityksellisiä tietoja luomalla dynaamisia viiteviivoja **Analytiikka**-ruudun avulla.

Aiomme lisätä enemmän ominaisuuksia ja toimintoja, muun muassa lisätä niiden visualisointien määrää, joissa voidaan käyttää dynaamisia viiteviivoja. Sinun kannattaa siksi tarkistaa uudet ominaisuudet tihein välein.

## <a name="apply-forecasting"></a>Ennusteiden käyttäminen
Voit käyttää **Ennuste**-ominaisuutta valitsemalla visualisoinnin ja laajentamalla sitten **Ennuste**-osion **Analytiikka**-ruudussa. Ennusteen muokkaamiseksi voidaan määrittää useita syötteitä, kuten *Ennusteen pituus* ja *Luottamusväli*. Seuraavassa kuvassa esitetään perusviivavisualisointi, jossa on käytetty ennustamista. Voit kuitenkin hyödyntää mielikuvitustasi ja kokeilla *ennustamis*toiminnon käyttöä eri tavoin nähdäksesi, miten se soveltuu malleihisi.

![](media/desktop-analytics-pane/analytics-pane_8.png)

## <a name="limitations"></a>Rajoitukset
Dynaamisten viiteviivojen käyttömahdollisuus perustuu käytössä olevan visualisoinnin tyyppiin. Seuraavassa luettelossa esitetään, mitkä dynaamiset viivat ovat tällä hetkellä käytettävissä eri visualisoinneissa:

Seuraavissa visualisoinneissa voidaan käyttää kaikkia dynaamisia viivoja:

* Aluekaavio
* Viivakaavio
* Pistekaavio
* Klusteroitu palkkikaavio

Seuraavissa visualisoinneissa voidaan käyttää vain *yhtenäistä viivaa* **Analytiikka**-ruudusta:

* Pinottu aluekaavio
* Pinottu palkkikaavio
* Pinottu pylväskaavio
* 100 % pinottu palkkikaavio
* 100 % pinottu pylväskaavio

Seuraavissa visualisoinneissa ainoa valittavissa oleva vaihtoehto on tällä hetkellä *trendiviiva*:

* Pinoamaton viiva
* Klusteroitu pylväskaavio

Lopuksi tulee huomioida, että **Analytiikka**-ruudusta valittavia dynaamisia viiteviivoja ei voida tällä hetkellä käyttää ei-karteesisissa visualisoinneissa, kuten seuraavissa:

* Matriisi
* Ympyräkaavio
* Ympyrä
* Taulukko

Prosenttipisteviiva on käytettävissä vain, kun käytetään tuotuja tietoja **Power BI Desktopissa** tai kun muodostetaan reaaliaikainen yhteys malliin palvelimessa, jossa on käytössä **Analysis Service 2016** tai uudempi, **Azure Analysis Services** -tietokantaan tai Power BI -palvelun tietojoukkoon. 

## <a name="next-steps"></a>Seuraavat vaiheet
Voit tehdä kaikenlaista Power BI Desktopilla. Saat lisätietoja sen toiminnoista seuraavista resursseista:

* [Power BI Desktopin uudet ominaisuudet](desktop-latest-update.md)
* [Lataa Power BI Desktop](desktop-get-the-desktop.md)
* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](desktop-query-overview.md)
* [Tietotyypit Power BI Desktopissa](desktop-data-types.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)    

