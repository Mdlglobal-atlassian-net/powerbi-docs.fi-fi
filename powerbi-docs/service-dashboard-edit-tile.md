---
title: Koontinäytön yksittäisen ruudun muokkaaminen
description: Tässä opetusohjelmassa opastetaan ruudun luomisessa ja kiinnittämisessä koontinäyttöön sekä koontinäytön ruudun muokkaamisessa – ruudun siirtämisessä, koon muuttamisessa, nimen vaihtamisessa, kiinnittämisessä, poistamisessa ja hyperlinkin lisäämisessä.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: lJKgWnvl6bQ
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 07db52bd2ffd881417f7ff59647c6779f7dc6bce
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34248338"
---
# <a name="edit-or-remove-a-dashboard-tile"></a>Koontinäytön ruudun muokkaaminen tai poistaminen

## <a name="dashboard-owners-versus-dashboard-consumers"></a>Koontinäytön *omistajat* verrattuna koontinäytön *kuluttajiin*
Kun luot koontinäytön tai olet sen omistaja, käytettävissäsi on paljon asetuksia, joilla voit muokata koontinäytön ruutujen ulkoasua ja oletusarvoista käyttäytymistä. Alla esiteltyjen asetusten ja strategioiden avulla voit suunnitella koontinäytön käyttökokemuksen työtovereillesi, jotka ovat koontinäytön *kuluttajia*.  Avaako ruudun valitseminen näytölle ruutuun liittyvän raportin, mukautetun URL-osoitteen vai toisen koontinäytön? Haluatko [lisätä ruudun, joka näyttää videota tai tietovirtaa](service-dashboard-add-widget.md)? Ehkä haluat [tehdä ruudun, jossa on vuorovaikutteisia osittajia](service-dashboard-pin-live-tile-from-report.md). Koontinäytön *tekijänä* käytettävissäsi on useita asetusvaihtoehtoja. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

Tässä artikkelissa käsitellään vaihtoehdoista seuraavat:

* [Visualisoinnin luominen ja kiinnittäminen koontinäyttöön](#create)
* [Ruudun siirtäminen toiseen paikkaan](#move)
* [Ruudun koon muuttaminen](#resize)
* [Ruudun nimeäminen uudelleen](#rename)
* [Hyperlinkin lisääminen ruutuun](#hyperlink)
* [Ruudun kiinnittäminen toiseen koontinäyttöön](#different)
* [Ruudun poistaminen](#delete)
  
 > [!TIP]
 > Jos haluat vaihtaa ruudussa näytettävän visualisoinnin, poista ruutu ja lisää uusi [koontinäytön ruutu](service-dashboard-tiles.md).
 > 

 ### <a name="prerequisites"></a>Edellytykset
 1. Voidaksesi tehdä opastuksen mukana samat vaiheet itse, avaa Power BI -palvelu (ei Power BI Desktop) ja [lataa itsellesi IT-kulutusanalyysimalli](sample-it-spend.md). Kun näkyviin tulee onnistumissanoma, valitse **Siirry koontinäyttöön**

- - -
<a name="create"></a>

## <a name="create-a-new-visualization-and-pin-it-to-the-dashboard"></a>Uuden visualisoinnin luominen ja kiinnittäminen koontinäyttöön
1. Valitse IT-kulutusanalyysin koontinäyttö ja avaa raportti valitsemalla Määrä-ruutu.

    ![Määrä-ruutu](media/service-dashboard-edit-tile/power-bi-amount-tile.png)

2. Avaa raportti muokkausnäkymässä valitsemalla yläreunan valikkoriviltä **Muokkaa raporttia**.

3. Lisää uusi raporttisivu valitsemalla plusmerkki (+) raportin alareunasta.

    ![plus-kuvake](media/service-dashboard-edit-tile/power-bi-add-page.png)

4. Valitse KENTÄT-paneelista **Fakta > Määrä** ja **Liiketoiminta-alue > Liiketoiminta-alue**.
 
5. Muunna visualisointi rengaskaavioksi valitsemalla VISUALISOINTI-paneelista rengaskaavion kuvake.

    ![Visualisoinnit-paneeli](media/service-dashboard-edit-tile/power-bi-donut-chart.png)

5. Valitse Kiinnitä-kuvake ja kiinnitä rengaskaavio IT-kulutusanalyysimallin koontinäyttöön.

   ![hiiren osoitin ruudun kohdalla](media/service-dashboard-edit-tile/power-bi-pin.png)

6. Kun näkyviin tulee onnistumissanoma, valitse **Siirry koontinäyttöön**. Ohjelma pyytää tallentamaan muutokset. Valitse **Tallenna**.

- - -
<a name="move"></a>

## <a name="move-the-tile"></a>Ruudun siirtäminen toiseen paikkaan
Etsi koontinäytöstä luomasi uusi ruutu. Paina ruutua pitkään ja vedä se koontinäytön taustalla uuteen kohtaan.

- - -
<a name="resize"></a>

## <a name="resize-the-tile"></a>Ruudun koon muuttaminen
Voit tehdä ruuduista erikokoisia: koko voi olla pienimmillään 1×1 ruutuyksikköä ja suurimmillaan 5×5. Muuta ruudun kokoa valitsemalla kahvaa (ruudun oikeasta alakulmasta) ja vetämällä sitä.

![video](media/service-dashboard-edit-tile/pbigif_resizetile4.gif)

- - -
## <a name="the-ellipses--menu"></a>Kolmen pisteen valikko (...)

1. Valitse ruudun oikeasta yläkulmasta kolme pistettä (...). 
   
   ![ruudun kolme pistettä](media/service-dashboard-edit-tile/power-bi-tile.png)

2. Vie hiiren osoitin Tili-ruudun kohdalle ja valitse kolme pistettä, jolloin asetukset tulevat esiin. Esiin tulevat asetukset vaihtelevat ruudun tyypin mukaan.  Esimerkiksi reaaliaikaiselle ruudulle on saatavilla erilaiset asetukset kuin tavalliselle visualisointiruudulle. Lisäksi jos sinulle on jaettu koontinäyttö (eli et ole sen omistaja), käytettävissäsi on vähemmän asetusvaihtoehtoja.

   ![kolme pistettä ‑asetusvalikko](media/service-dashboard-edit-tile/power-bi-tile-menu-new.png)

3. Avaa Ruudun tiedot ‑ikkuna valitsemalla **Muokkaa tietoja**. 

    Voit muokata ruudun otsikkoa ja oletusarvoista toimintaa.  Voit esimerkiksi päättää, että kun *kuluttaja* valitsee ruudun, ruudun luomiseen käytetyn raportin sijasta näkyviin tuleekin uusi koontinäyttö.  
   


<a name="rename"></a>

### <a name="rename-the-tile"></a>Ruudun nimen vaihtaminen
Vaihda Ruudun tiedot ‑ikkunan yläreunasta **Otsikko**-asetukseksi **Kulutettu summa**.

![Ruudun tiedot ‑ikkuna](media/service-dashboard-edit-tile/power-bi-tile-title.png)


<a name="hyperlink"></a>

### <a name="change-the-default-hyperlink"></a>Oletusarvoisen hyperlinkin muuttaminen
Oletusarvoisesti ruudun valitseminen siirtää käyttäjän raporttiin, josta ruutu luotiin, tai Q&A:han (jos ruutu luotiin Q&A:lla). Jos haluat linkittää ruudun toiseen koontinäyttöön tai raporttiin (samassa työtilassa), SSRS-raporttiin tai muuhun verkkosisältöön, lisää mukautettu linkki.

1. Valitse Toiminnot-otsikon alta asetus **Aseta mukautettu linkki**.

2. Valitse tyypiksi **Linkitä koontinäyttöön tai raporttiin nykyisessä työtilassa** ja valitse sitten kohde avattavasta valikosta.  Tässä esimerkissä valitaan henkilöstöhallintomallin koontinäyttö. Jos sinulla ei ole kyseistä mallia valmiina työtilassasi, voit lisätä sen ja palata tähän vaiheeseen tai voit valita jonkin toisen koontinäytön. 

    ![Toiminnot-näkymä](media/service-dashboard-edit-tile/power-bi-custom-link.png)

3. Valitse **Käytä**.

4. Uusi otsikko tulee näkyviin ruutuun.  Kun valitset ruudun, Power BI avaa Henkilöstöhallinto-koontinäytön. 

    ![ruudun otsikko](media/service-dashboard-edit-tile/power-bi-title.png)

<a name="different"></a>

### <a name="pin-the-tile-to-a-different-dashboard"></a>Ruudun kiinnittäminen toiseen koontinäyttöön
1. Valitse kolmen pisteen valikosta **Kiinnitä ruutu** ![Kiinnitä-kuvake](media/service-dashboard-edit-tile/pinnooutline.png) .
2. Päätä, haluatko kiinnittää ruudun kaksoiskappaleen aiemmin luotuun vai uuteen koontinäyttöön. 
   
   ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-edit-tile/pbi_pintoanotherdash.png)
3. Valitse **Kiinnitä**.

<a name="delete"></a>

### <a name="delete-the-tile"></a>Ruudun poistaminen
1. Jos haluat poistaa ruudun pysyvästi koontinäytöstä, valitse kolmen pisteen valikosta **Poista ruutu** ![Poista-kuvake](media/service-dashboard-edit-tile/power-bi-delete-tile-icon.png). 

2. Ruudun poistaminen ei poista sen perustana toimivaa visualisointia. Voit avata perustana olevan raportin valitsemalla Summa-ruudun. Kun avaat raportin viimeisen sivun, niin nähdä, ettei alkuperäistä visualisointia ole poistettu raportista. 

- - -
## <a name="next-steps"></a>Seuraavat vaiheet
[Koontinäyttöruudut Power BI:ssä](service-dashboard-tiles.md)

[Koontinäytöt Power BI:ssä](service-dashboards.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

