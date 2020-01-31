---
title: Power BI -visualisointikonsepti
description: Artikkelissa kuvataan, miten visualisointi integroituu Power BI:n kanssa
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 36742917829013a6efca9d74f88b01bc686437a8
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700842"
---
# <a name="power-bi-visual-concept"></a>Power BI -visualisointikonsepti

Artikkelissa kerrotaan, miten käyttäjä ja visualisointi toimivat yhdessä Power BI:ssä ja miten käyttäjä on vuorovaikutuksessa Power BI -visualisoinnin kanssa. Näet kaaviosta, mitkä toiminnot vaikuttavat suoraan visualisointiin tai Power BI:hin (esimerkiksi kun käyttäjä valitsee kirjanmerkit).

![Power BI -visualisointi](./media/visual-concept.svg)

## <a name="the-visual-gets-update-from-power-bi"></a>Visualisointi saa päivityksen Power BI:stä

Visualisoinnissa on `update`-menetelmä. Tämä menetelmä sisältää visualisoinnin päälogiikan, ja se on vastuussa kaavion hahmontamisesta tai tietojen visualisoinnista.

Lisää päivityksiä saa kutsumalla `update`-menetelmää.

### <a name="user-interacts-with-visual-through-power-bi"></a>Käyttäjä on vuorovaikutuksessa visualisoinnin kanssa Power BI:n kautta

* Käyttäjä avaa visualisoinnin ominaisuuspaneelin.

    Power BI noutaa tuetut objektit ja ominaisuudet visualisoinnista `capabilities.json` sekä ominaisuuksien todellisten arvojen vastaanottamiseksi Power BI-kutsuissa `enumerateObjectInstances` visualisointimenetelmässä.

    Visualisoinnin on palautettava ominaisuuksien todelliset arvot.

    Jos haluat lisätietoja, [lue visualisoinnin ominaisuuksista](capabilities.md).

* [Käyttäjä voi muuttaa visualisoinnin ominaisuutta](../../visuals/power-bi-visualization-customize-title-background-and-legend.md) muotoilupaneelissa.

    Kun olet muokannut ominaisuuden arvoa, Power BI kutsuu visualisoinnin `update`-menetelmää ja siirtää siihen uudet `options`-arvot objekteille.

    [Lue täältä lisätietoja visualisointien objekteista ja ominaisuuksista](objects-properties.md).

* Käyttäjä muuttaa visualisoinnin kokoa.

    Kun käyttäjä muuttaa visualisoinnin kokoa, Power BI kutsuu `update`-metodia uudella `option`-objektilla. Asetukset sisältävät sisäkkäisen `viewport`-objektin visualisoinnin uudella leveydellä ja korkeudella.

* Käyttäjä käyttää raportti-, sivu- tai visualisointitason suodatinta.

    Power BI suodattaa tiedot suodatusehtojen mukaan ja kutsuu visualisoinnin `update`-menetelmää, joka antaa uudet tiedot visualisointiin.

    Visualisointi saa uuden `options`-päivityksen uusilla tiedoilla jossakin sisäkkäisessä objektissa. Se määräytyy visualisoinnin tietonäkymän yhdistämismäärityksen mukaan.

    Lisätietoja on artikkelissa [Tietonäkymän yhdistämismääritykset](dataview-mappings.md).

* Käyttäjä valitsee arvopisteen raportin toisesta visualisoinnista.

    Power BI suodattaa tai korostaa valittuja arvopisteitä ja kutsuu `update`-menetelmää visualisoinnissa.

    Visualisointi hakee uudet suodatetut tiedot tai samat tiedot, jotka sisältävät valikoiman korostuksia.

    Lisätietoja saa artikkelista [Tietojen korostaminen visualisoinneissa](highlight.md).

* Käyttäjä valitsee kirjanmerkin raportin kirjanmerkkipaneelista.

    Tällöin voi tapahtua kaksi toimintoa:

    1. Power BI kutsuu funktiota, joka on rekisteröity menetelmällä `registerOnSelectionCallback`, ja takaisinkutsutoiminto hakee vastaavan kirjanmerkin valintamatriisit.

    2. Power BI kutsuu `update`-menetelmää, joka sisältää vastaavan suodatusobjektin `options`-objektissa.

    Kummassakin tapauksessa visualisoinnin on muutettava visualisointitilaa vastaanotettujen valintojen tai suodatusobjektin mukaan.

    Jos haluat lisätietoja kirjanmerkeistä, [lue, miten kirjanmerkkejä käsitellään](filter-api.md).

    Jos haluat lisätietoja suodattimista, [lue, miten Power BI -visualisoinnit voivat suodattaa tietoja muissa visualisoinneissa](filter-api.md).

### <a name="user-interacts-with-visual-directly"></a>Käyttäjä on vuorovaikutuksessa visualisoinnin kanssa suoraan

* Käyttäjä siirtää osoittimen tietoelementin päälle

    Visualisointi voi näyttää lisätietoja arvopisteestä Power BI:n työkaluvihjeiden ohjelmointirajapinnan kautta.
    Käyttäjä pitää hiiren osoitinta visualisoinnin päällä. Visualisointi voi käsitellä tapahtumaa ja näyttää tietoja työkaluvihje-elementissä.

    Visualisointi voi näyttää vakiotyökaluvihjeen tai raporttisivun työkaluvihjeen.

    Lue lisätietoja ohjeartikkelista [työkaluvihjeiden lisäämiseen](add-tooltips.md).

* Käyttäjä muuttaa visuaalisia ominaisuuksia (esimerkki: käyttäjä laajentaa puuta ja visualisointi tallentaa tilan ominaisuuksissa)

    Visualisointi voi tallentaa ominaisuuksien arvot Power BI -ohjelmointirajapinnan kautta. esimerkiksi kun käyttäjä on vuorovaikutuksessa visualisoinnin kanssa. Visualisoinnin on myös tallennettava tai päivitettävä ominaisuusarvot. Visualisointi voi kutsua `presistProperties`-menetelmää.

* Käyttäjä napsauttaa URL-linkkiä.

    Visualisointi ei oletusarvoisesti voi avata URL-osoitetta. Jos haluat, että URL-osoite avataan uudessa välilehdessä, visualisoinnin tulee kutsua `launchURL`-menetelmää ja välittää URL-osoite parametrina.

    Lisätietoja on kohdassa [URL-ohjelmointirajapinnan käynnistäminen](launch-url.md).

* Käyttäjä käyttää suodatinta visualisoinnissa

    Visualisointi kutsuu `applyJSONFilter`-menetelmää ja lähettää suodatusehdot, joiden avulla suodatetaan tietojen suodattaminen toisessa visualisoinnissa.

    Visualisointi voi käyttää useita suodatintyyppejä, esimerkiksi perus- ja lisäsuodatusta sekä monikkosuodatinta.

    Jos haluat lisätietoja suodattimista, [lue, miten Power BI -visualisoinnit voivat suodattaa tietoja muissa visualisoinneissa](filter-api.md).

* Käyttäjä napsauttaa tai valitsee visualisoinnin elementtejä.

    Jos haluat lisätietoja valinnasta, [lue visualisoinnin vuorovaikutuksesta](selection-api.md).

### <a name="the-visual-interacts-with-power-bi"></a>Visualisointi on vuorovaikutuksessa Power BI:n kanssa

* Visualisointi pyytää enemmän tietoja Power BI:stä.

    Visualisointi voi käsitellä tietoja osakohtaisesti. FetchMoreData-ohjelmointirajapintamenetelmä pyytää tietojoukon seuraavaa osaa.

    Jos haluat lisätietoja `fetchMoreData`-menetelmästä, [lue, miten voit noutaa lisätietoja Power BI:stä](fetch-more-data.md)

* Tapahtumapalvelu

    Power BI voi viedä raportteja PDF-muotoon tai lähettää ne sähköpostitse (vain sertifioituja visualisointeja tuetaan). Jos haluat, että visualisointi ilmoittaa Power BI:lle, kun hahmontaminen on valmis ja se on valmis tallentamaan PDF-tiedoston tai lähettämään sähköpostiviestin, sen tulee kutsua tapahtumien hahmontamisen ohjelmointirajapintaa.

    Jos haluat lisätietoja, [lue raporttien viemisestä Power BI:stä PDF-muotoon](../../consumer/end-user-pdf.md)

    Lue lisätietoja [Tapahtumapalvelusta](event-service.md)

## <a name="next-steps"></a>Seuraavat vaiheet

Oletko Web-kehittäjä ja kiinnostunut omien visualisointien luomisesta ja niiden lisäämisestä AppSourceen? Katso artikkeli [Power BI:n visualisoinnin kehittäminen](./custom-visual-develop-tutorial.md) ja lue lisää [Power BI -visualisointien julkaisemisesta AppSourcessa](../office-store.md).
