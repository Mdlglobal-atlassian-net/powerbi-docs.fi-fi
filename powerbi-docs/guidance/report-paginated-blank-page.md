---
title: Tyhjien sivujen välttäminen sivutettuja raportteja tulostettaessa
description: Ohjeet sivutettujen raporttien suunnittelemiseen tyhjien sivujen välttämiseksi tulostettaessa.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: v-pemyer
ms.openlocfilehash: 349459b95a815a52665e50687554f81f90a9c81b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "78920814"
---
# <a name="avoid-blank-pages-when-printing-paginated-reports"></a>Tyhjien sivujen välttäminen sivutettuja raportteja tulostettaessa

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee Power BI:n [sivutettuja raportteja](../paginated-reports/paginated-reports-report-builder-power-bi.md). Se antaa suosituksia, joiden avulla voit välttää tyhjiä sivuja, kun raporttisi viedään paperimuotoon, kuten PDF tai Microsoft Word, tai se tulostetaan.

## <a name="page-setup"></a>Sivun asetukset

Raportin sivukoko-ominaisuudet määrittävät sivun suunnan, mitat ja reunukset. Voit käyttää näitä raportin ominaisuuksia seuraavasti:

- Käyttämällä raportin **ominaisuussivua**: Napsauta hiiren kakkospainikkeella raporttipohjan ulkopuolella olevaa tummanharmaata aluetta ja valitse sitten _Raportin ominaisuudet_.
- Käyttämällä [**Ominaisuus**-ruutua](../paginated-reports/paginated-reports-report-design-view.md#4-properties-pane): Napsauta raporttipohjan ulkopuolella olevaa tummanharmaata aluetta raporttiobjektin valitsemiseksi. Varmista, että **Ominaisuudet**-ruutu on auki.

Raportin **ominaisuussivun** **Sivun asetukset** -sivu sisältää helpon käyttöliittymän sivun asetusominaisuuksien tarkastelua ja päivitystä varten.

![Kuvassa näytetään Raportin ominaisuudet -ikkuna, jossa korostetaan Sivun asetukset -sivua.](media/report-paginated-blank-page/report-page-setup-properties.png)

Varmista, että kaikki sivun koko-ominaisuudet on määritetty oikein:

|Ominaisuus|Suositus|
|---------|---------|
|Sivun yksiköt|Valitse tarvittavat yksiköt – tuumat tai senttimetrit.|
|Suunta|Valitse oikea vaihtoehto – pysty tai vaaka.|
|Paperikoko|Valitse paperikoko tai määritä mukautetut leveys- ja korkeusarvot.|
|Reunukset|Määritä sopivat arvot vasemmalle, oikealle, ylös ja alas.|
|||

## <a name="report-body-width"></a>Raportin leipätekstin leveys

Sivun koko-ominaisuudet määrittävät raporttiobjekteille käytettävissä olevan tilan. Raporttiobjektit voivat olla tietoalueita, tietojen visualisointeja tai muita raporttikohteita.

Yleinen syy tyhjien sivujen tulostamiseen on se, että raportin leipätekstin leveys _ylittää käytettävissä olevan sivutilan_.

Voit vain tarkastella raportin leipätekstin leveyttä ja määrittää sen **Ominaisuudet**-ruudun avulla. Napsauta ensin missä tahansa raportin leipätekstin tyhjällä alueella.

![Kuvassa näytetään Ominaisuudet-ruutu, jossa korostetaan raportin leipätekstin leveysominaisuutta.](media/report-paginated-blank-page/report-body-properties-width.png)

Varmista, että leveyden arvo ei ylitä käytettävissä olevaa sivun leveyttä. Käytä seuraavaa kaavaa:

```Report body width <= Report page width - (Left margin + Right margin)```

> [!NOTE]
> Raportin leipätekstin leveyttä ei voi pienentää, kun raporttiobjektit ovat jo tilassa, jonka haluat poistaa. Sinun täytyy ensin sijoittaa ne uudelleen tai muuttaa niiden kokoa ennen leveyden pienentämistä.
>
> Raportin leipätekstin leveys voi myös kasvaa automaattisesti, kun lisäät uusia objekteja tai muutat olemassa olevien objektien kokoa tai sijoitat ne uudelleen. Raportin suunnittelutoiminto laajentaa aina leipätekstiä niin, että se mahtuu sen sisältämien objektien sijaintiin ja kokoon.

## <a name="report-body-height"></a>Raportin leipätekstin korkeus

Toinen syy tyhjän sivun tulostamiseen on se, että raportin leipätekstissä on ylimääräinen välilyönti viimeisen objektin jälkeen.

Suosittelemme aina pienentämään leipätekstin korkeutta lopussa olevan mahdollisen välilyönnin poistamiseksi.

![Kuvassa näytetään raportin rakenne. Tablix-elementin tietoalueen alla oleva tila on korostettu ja merkitty tarpeettomaksi.](media/report-paginated-blank-page/report-body-remove-trailing-space.png)

## <a name="page-break-options"></a>Sivunvaihdon asetukset

Kullakin tietoalueella ja tietojen visualisoinnilla on sivun vaihtoasetukset. Voit käyttää näitä asetuksia sen ominaisuussivulla tai **Ominaisuudet**-ruudussa.

Varmista, että **Lisää sivunvaihto jälkeen** -ominaisuus ei ole tarpeettomasti käytössä.

![Kuvassa näytetään Tablix-elementin Ominaisuudet-ikkuna. ”Lisää sivunvaihto jälkeen” -ominaisuus on käytössä.](media/report-paginated-blank-page/data-region-page-break-option-after.png)

## <a name="consume-container-whitespace"></a>Säilön välilyöntien käyttäminen

Jos tyhjän sivun ongelma jatkuu, voit myös yrittää poistaa käytöstä raportin **ConsumeContainerWhitespace**-ominaisuuden. Se voidaan määrittää vain **Ominaisuudet**-ruudussa.

![Kuvassa näytetään Ominaisuudet-ruutu, jossa korostetaan ConsumeContainerWhitespace-ominaisuutta.](media/report-paginated-blank-page/report-properties-consumecontainerwhitespace.png)

Oletusarvon mukaan se on käytössä. Se määrää sen, pitäisikö säilöissä, kuten raportin leipätekstissä tai suorakulmiossa, käyttää vähimmäisvälilyöntejä. Tämä koskee vain välilyöntejä, jotka ovat sisältöjen oikealla puolella ja alapuolella.

## <a name="printer-paper-size"></a>Tulostimen paperikoko

Lopuksi jos tulostat raportin paperille, varmista, että tulostimeen on lisättyä oikeanlaista paperia. Fyysisen paperikoon on vastattava [raportin paperikokoa](#page-setup).

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](../paginated-reports/paginated-reports-report-builder-power-bi.md)
- [Sivutus Power BI:n sivutetuissa raporteissa](../paginated-reports/paginated-reports-pagination.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com)
