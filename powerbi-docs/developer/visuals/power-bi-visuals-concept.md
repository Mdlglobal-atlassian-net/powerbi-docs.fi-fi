---
title: Power BI:n visualisointien käsitteet
description: Artikkelissa kuvataan, miten visualisoinnit integroituvat Power BI:hin ja miten käyttäjä voi käsitellä visualisointia Power BI:ssä.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: bb0834527ba23c6cfcc155cc65cd0318b296ba84
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/04/2020
ms.locfileid: "75925607"
---
# <a name="visuals-in-power-bi"></a>Visualisoinnit Power BI:ssä

Artikkelissa kuvataan, miten visualisoinnit integroituvat Power BI:hin ja miten käyttäjä voi käsitellä visualisointia Power BI:ssä. 

Seuraavassa kuvassa esitetään se, miten tavalliset käyttäjän suorittamat visualisointitoiminnot, kuten kirjanmerkin valitseminen, käsitellään Power BI:ssä.

![Power BI:n visualisoinnin toimintokaavio](./media/visual-concept.svg)

## <a name="visuals-get-updates-from-power-bi"></a>Visualisoinnit saavat päivityksiä Power BI:stä

Visualisointi kutsuu `update`-menetelmää päivitysten saamiseksi Power BI:stä. `update`-menetelmä sisältää visualisoinnin päälogiikan, ja se on vastuussa kaavion hahmontamisesta tai tietojen visualisoinnista.

Päivitykset käynnistyvät, kun visualisointi kutsuu `update`-menetelmää.

## <a name="action-and-update-patterns"></a>Toiminto- ja päivitysmallit

Power BI visualisointien toiminnot ja myöhemmät päivitykset esiintyvät jossakin seuraavista kolmesta malleista:

* Käyttäjä on vuorovaikutuksessa visualisoinnin kanssa Power BI:n kautta.
* Käyttäjä on vuorovaikutuksessa visualisoinnin kanssa suoraan.
* Visualisointi on vuorovaikutuksessa Power BI:n kanssa.

### <a name="user-interacts-with-a-visual-through-power-bi"></a>Käyttäjä on vuorovaikutuksessa visualisoinnin kanssa Power BI:n kautta

* Käyttäjä avaa visualisoinnin ominaisuuspaneelin.

    Kun käyttäjä avaa visualisoinnin ominaisuuspaneelin, Power BI hakee tuetut objektit ja ominaisuudet visualisoinnin *capabilities.json*-tiedostosta. Ominaisuuksien todellisten arvojen hakemiseksi Power BI kutsuu visualisoinnin `enumerateObjectInstances`-menetelmää. Visualisointi palauttaa ominaisuuksien todelliset arvot.

    Lisätietoja on artikkelissa [Power BI:n visualisointien toiminnot ja ominaisuudet](capabilities.md).

* Käyttäjä [voi muuttaa visualisoinnin ominaisuutta](../../visuals/power-bi-visualization-customize-title-background-and-legend.md) muotoilupaneelissa.

    Kun käyttäjä muuttaa ominaisuuden arvoa muotoilupaneelissa, Power BI kutsuu visualisoinnin `update`-menetelmää. Power BI siirtyy uudessa `options`-objektissa `update`-menetelmään. Objektit sisältävät uudet arvot.

    Lisätietoja on artikkelissa [Power BI:n visualisointien objektit ja ominaisuudet](objects-properties.md).

* Käyttäjä muuttaa visualisoinnin kokoa.

    Kun käyttäjä muuttaa visualisoinnin kokoa, Power BI kutsuu `update`-metodia uudella `options`-objektilla. `options`-objekteissa on sisäkkäisiä `viewport`-objekteja, jotka sisältävät visualisoinnin uuden leveyden ja korkeuden.

* Käyttäjä käyttää suodatinta raportti-, sivu- tai visualisointitasolla.

    Power BI suodattaa tiedot suodatusehtojen perusteella. Power BI kutsuu visualisoinnin `update`-menetelmää visualisoinnin päivittämiseksi uusilla tiedoilla.

    Visualisointi saa uuden `options`-objektien päivityksen, kun jossakin sisäkkäisessä objektissa on uutta tietoa. Päivityksen toimintatapa määräytyy visualisoinnin tietonäkymän yhdistämismäärityksen mukaan.

    Lisätietoja on artikkelissa [Power BI -visualisointien tietonäkymän yhdistämismääritykset](dataview-mappings.md).

* Käyttäjä valitsee arvopisteen raportin toisesta visualisoinnista.

    Kun käyttäjä valitsee arvopisteen raportin toisesta visualisoinnista, Power BI suodattaa tai korostaa valittuja arvopisteitä ja kutsuu visualisoinnin `update`-menetelmää. Visualisointi saa uutta suodatettua tietoa, tai se saa samat tiedot, jotka sisältävät valikoiman korostuksia.

    Lisätietoja on artikkelissa [Arvopisteiden korostaminen Power BI:n visualisoinneissa](highlight.md).

* Käyttäjä valitsee kirjanmerkin raportin kirjanmerkkipaneelista.

    Kun käyttäjä valitsee kirjanmerkin raportin kirjanmerkkipaneelista, voi tapahtua yksi kahdesta toiminnosta:

    * Power BI kutsuu funktiota, joka välitetään ja rekisteröidään `registerOnSelectionCallback`-menetelmällä. Takaisinkutsufunktio hakee valikoiman vastaavan kirjanmerkin valintoja.

    * Power BI kutsuu sitä `update`-menetelmää, jossa on vastaava `filter`-objekti `options`-objektin sisällä.

    Molemmissa tapauksissa visualisoinnin on muutettava tilaansa vastaanotettujen valintojen tai `filter`-objektin mukaan.

    Lisätietoja kirjanmerkeistä ja suodattimista saat kohdasta [Visual Filters -ohjelmointirajapinta Power BI -visualisoinneissa](filter-api.md).

### <a name="user-interacts-with-the-visual-directly"></a>Käyttäjä on suoraan vuorovaikutuksessa visualisoinnin kanssa

* Käyttäjä siirtää hiiren osoittimen tietoelementin kohdalle.

    Visualisointi voi näyttää lisätietoja arvopisteestä Power BI -työkaluvihjeiden ohjelmointirajapinnan kautta. Kun käyttäjä siirtää hiiren osoittimen visuaalisen elementin kohdalle, visualisointi voi käsitellä tapahtumaa ja näyttää tietoja asiaan liittyvästä työkaluvihje-elementistä. Visualisointi voi näyttää joko vakiotyökaluvihjeen tai raporttisivun työkaluvihjeen.

    Katso lisätietoja kohdasta [Power BI:n visualisointien työkaluvihjeet](add-tooltips.md).

* Käyttäjä muuttaa visuaalisia ominaisuuksia. (Käyttäjä voi esimerkiksi laajentaa puuta ja visualisointi säilyttää tilan visuaalisissa ominaisuuksissa.)

    Visualisointi voi tallentaa ominaisuuksien arvot Power BI -ohjelmointirajanpinnan kautta. Jos käyttäjä esimerkiksi käsittelee visualisointia ja visualisoinnin täytyy tallentaa tai päivittää ominaisuuksien arvot, visualisointi voi kutsua `presistProperties`-menetelmää.

* Käyttäjä valitsee URL-osoitteen.

    Oletusarvona on, että visualisointi ei voi suoraan avata URL-osoitetta. Sen sijaan visualisointi voi avata URL-osoitteen uuteen välilehteen kutsumalla `launchUrl`-menetelmää ja välittämällä URL-osoitteen parametrina.

    Lisätietoja on kohdassa [URL-käynnistysosoitteen luominen](launch-url.md).

* Käyttäjä käyttää suodatinta visualisoinnin kautta.

    Visualisointi voi kutsua `applyJsonFilter`-menetelmää ja välittää ehtoja tietojen suodattamiselle muissa visualisoinneissa. Saatavissa on useita eri suodatintyyppejä, kuten perus-, lisä- ja moninkertaiset suodattimet.

    Lisätietoja on artikkelissa [Visual Filters -ohjelmointirajapinta Power BI:n visualisoinneissa](filter-api.md).

* Käyttäjä valitsee elementtejä visualisoinnissa.

    Lisätietoja Power BI -visualisoinnin valinnoista saat kohdasta [Vuorovaikutteisuuden lisääminen käytettäessä Power BI -visualisoinnin valinnoissa](selection-api.md).

### <a name="visual-interacts-with-power-bi"></a>Visualisointi vuorovaikutuksessa Power BI:n kanssa

* Visualisointi pyytää lisätietoja Power BI:ltä.

    Visualisointi käsittelee tietoja osa osalta. `fetchMoreData`-ohjelmointirajapintamenetelmä pyytää tietojoukon seuraavaa osaa.

    Katso lisätietoja kohdasta [Lisätietojen noutaminen Power BI:stä](fetch-more-data.md).

* Tapahtumapalvelun käynnistimet.

    Power BI voi viedä raportin PDF-muotoon tai lähettää raportin sähköpostitse (koskee vain sertifioituja visualisointeja). Visualisoinnin tulee kutsua hahmontamistapahtumien ohjelmointirajapintaa sen ilmaisemiseksi Power BI:lle, että hahmontaminen on valmis ja että visualisointi voidaan vangita PDF- tai sähköpostimuotoon.

    Katso lisätietoja kohdasta [Raporttien vieminen Power BI:stä PDF-muotoon](../../consumer/end-user-pdf.md).

    Lisätietoja tapahtumapalvelusta saat kohdasta [Tapahtumien hahmontaminen Power BI -visualisoinneissa](event-service.md).

## <a name="next-steps"></a>Seuraavat vaiheet

Oletko kiinnostunut luomaan visualisointeja ja lisäämään niitä Microsoft AppSourceen? Tutustu näihin artikkeleihin:

* [Power BI -visualisoinnin kehittäminen](./custom-visual-develop-tutorial.md)
* [Power BI -visualisointien julkaiseminen kumppanikeskuksessa](../office-store.md)
