---
title: Porautumispainikkeen luominen Power BI:ssä
description: Voit lisätä Power BI -raportteihin porautumispainikkeita, joiden avulla raportit toimivat sovellusten tavoin ja jotka auttavat syventämään käyttäjien sitoutumista.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/12/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: d3cb3c8093446d4417a59c5f64ab6b85a765e3c8
ms.sourcegitcommit: 7e845812874b3347bcf87ca642c66bed298b244a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/13/2020
ms.locfileid: "79206443"
---
# <a name="create-a-drill-through-button-in-power-bi-preview"></a>Porautumispainikkeen luominen Power BI:ssä (esikatselu)

Kun luot painikkeen Power BI:ssä, voit valita **Poraudu (esikatselu)** -toiminnon. Tämä toimintotyyppi luo painikkeen, joka porautuu kohdistettuun sivuun ja hakee tiettyyn kontekstiin suodatetut tiedot.

Porautumispainike voi olla hyödyllinen, jos haluat lisätä tärkeiden porautumisskenaarioiden löydettävyyttä raporteissasi.

Kun käyttäjä tässä esimerkissä valitsee Word-palkin kaaviossa, **Näytä tiedot** -painike tulee käyttöön.

![Näytä tiedot -painike](media/desktop-drill-through-buttons/power-bi-drill-through-visual-button.png)

Kun käyttäjä valitsee **Näytä tiedot** -painikkeen, hän porautuu Ostoskorianalyysi-sivulle. Kuten näet visualisoinnista vasemmalla, porautumissivu suodatetaan nyt Wordia varten.

![Suodatettu visualisointi](media/desktop-drill-through-buttons/power-bi-drill-through-destination.png)

## <a name="set-up-a-drill-through-button"></a>Porautumispainikkeen määrittäminen

Kun haluat määrittää porautumispainikkeen, sinun on ensin [määritettävä kelvollinen porautumissivu](desktop-drillthrough.md) raportissasi. Sen jälkeen sinun on luotava painike, jonka toimintotyyppi on **Porautuminen**, ja valittava porautumissivu **Kohde**-asetukseksi.

Koska porautumispainikkeessa on kaksi tilaa (porautuminen käytössä tai poissa käytöstä), työkaluvihjevaihtoehtojakin on kaksi.

![Porautumispainikkeen määrittäminen](media/desktop-drill-through-buttons/power-bi-create-drill-through-button.png)

Jos jätät työkaluvihjeruudut tyhjiksi, Power BI luo työkaluvihjeet automaattisesti. Nämä työkaluvihjeet perustuvat kohde- ja porautumiskenttiin.

Seuraavassa on esimerkki automaattisesti luodusta työkaluvihjeestä, kun painike on poissa käytöstä:

”Jos haluat porautua ostoskorianalyysiin (kohdesivu), valitse tuotteesta yksi arvopiste (porautumiskenttä).”

![Poissa käytöstä oleva automaattisesti luotu työkaluvihje](media/desktop-drill-through-buttons/power-bi-drill-through-tooltip-disabled.png)

Seuraavassa on esimerkki automaattisesti luodusta työkaluvihjeestä, kun painike on käytössä:

”Napsauttamalla voit porautua ostoskorianalyysiin (kohdesivu).”

![Käytössä oleva automaattisesti luotu työkaluvihje](media/desktop-drill-through-buttons/power-bi-drill-through-visual-button.png)

Jos kuitenkin haluat luoda mukautettuja työkaluvihjeitä, voit aina syöttää staattisen merkkijonon. Työkaluvihjeiden ehdollinen muotoilu ei ole vielä tuettua.

Ehdollisen muotoilun avulla voit muuttaa painikkeen tekstiä kentän valitun arvon perusteella. Tätä varten sinun on luotava mittari, joka tulostaa halutun merkkijonon DAX-funktion SELECTEDVALUE-arvon perusteella.

Seuraavassa on esimerkkimittari, joka tulostaa ”Näytä tuotteen tiedot” -tekstin, jos yksittäistä tuotearvoa EI valita. Muutoin se tulostaa tekstin ”Näytä kohteen [valittu tuote] tiedot”:

```
String_for_button = If(SELECTEDVALUE('Product'[Product], 0) == 0), "See product details", "See details for " & SELECTEDVALUE('Product'[Product]))
```

Kun olet luonut tämän mittarin, valitse painikkeen tekstiä varten **Ehdollinen muotoilu** -asetus:

![Valitse Ehdollinen muotoilu](media/desktop-drill-through-buttons/power-bi-button-conditional-tooltip.png)

Valitse sitten painikkeen tekstiä varten valitsemasi mittari:

![Kenttään perustuva arvo](media/desktop-drill-through-buttons/power-bi-conditional-measure.png)

Kun yksittäinen tuote on valittuna, painikkeen tekstinä on:

”Näytä kohteen Word tiedot”

![Kun yksittäinen arvo on valittuna](media/desktop-drill-through-buttons/power-bi-conditional-button-text.png)

Kun yhtään tuotetta ei ole valittuna tai vähintään kaksi tuotetta on valittuna, painike poistetaan käytöstä ja painikkeen tekstinä on:

”Näytä tuotteen tiedot”

![Kun useita arvoja on valittuna](media/desktop-drill-through-buttons/power-bi-button-conditional-text-2.png)

## <a name="pass-filter-context"></a>Välitä suodatinkonteksti

Painike toimii tavallisen porautumisen tavoin, joten voit myös välittää suodattimia muihin kenttiin ristiinsuodattamalla visualisoinnit, jotka sisältävät porautumiskentän. Jos käytät esimerkiksi **Ctrl** +  **-napsautusta** ja ristiinsuodatusta, voit siirtää useita suodattimia säilöön porautumissivulle, koska valintasi ristiinsuodattavat tuotteen sisältävän visualisoinnin porautumiskentän:

![Suodatinkontekstin välittäminen](media/desktop-drill-through-buttons/power-bi-cross-filter-drill-through-button.png)

Kun valitset porautumispainikkeen, sekä kaupan että tuotteen suodattimet välitetään kohdesivulle:

![Tämän sivun suodattimet](media/desktop-drill-through-buttons/power-bi-button-filters-passed-through.png)

### <a name="ambiguous-filter-context"></a>Moniselitteinen suodatinkonteksti

Koska porautumispainike ei ole sidottu yksittäiseen visualisointiin ja valintasi on moniselitteinen, painike poistetaan käytöstä.

Tässä esimerkissä painike on poistettu käytöstä, koska molemmat visualisoinnit sisältävät yhden Tuote-valinnan. On epäselvää, minkä visualisoinnin mihin arvopisteeseen porautumistoiminto sidotaan:

![Moniselitteinen suodatinkonteksti](media/desktop-drill-through-buttons/power-bi-button-disabled-ambiguity.png)

## <a name="limitations"></a>Rajoitukset

- Tämä painike ei salli useiden kohteiden käyttämistä yhdellä painikkeella.
- Tämä painike tukee vain porautumista samassa raportissa. Se ei siis tue raporttien välistä porautumista.
- Painikkeen käytöstä poistetun tilan muotoilu on sidottu raporttiteeman väriluokkiin. Lue lisää [väriluokista](desktop-report-themes.md#setting-structural-colors).
- Porautumistoiminto toimii kaikkien sisäisten visualisointien ja *joidenkin* AppSourcesta tuotujen visualisointien kanssa. Se ei kuitenkaan välttämättä toimi *kaikkien* AppSourcesta tuotujen visualisointien kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet
Seuraavissa artikkeleissa on lisätietoja ominaisuuksista, jotka muistuttavat painikkeita tai toimivat niiden kanssa:

* [Painikkeiden luominen](desktop-buttons.md)
* [Porautumisen käyttäminen Power BI -raporteissa](desktop-drillthrough.md)
* [Kirjanmerkkien käyttäminen merkityksellisten tietojen jakamiseen ja tarinoiden koostamiseen Power BI:ssä](desktop-bookmarks.md)

