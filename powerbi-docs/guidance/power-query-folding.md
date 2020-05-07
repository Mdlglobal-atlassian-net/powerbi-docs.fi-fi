---
title: Ohjeet kyselyn delegointiin lähteeseen Power BI Desktopissa
description: Ohjeet Power Query -kyselyn delegointiin lähteeseen Power BI Desktopissa.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/09/2019
ms.author: v-pemyer
ms.openlocfilehash: e8123bba9f68305e1944dbfb280b5255e4fb9b48
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "75622150"
---
# <a name="query-folding-guidance-in-power-bi-desktop"></a>Ohjeet kyselyn delegointiin lähteeseen Power BI Desktopissa

Tämä artikkeli on suunnattu tietomallintajille, jotka kehittävät malleja Power BI Desktopissa. Se tarjoaa ohjeet parhaisiin käytäntöihin, jotka koskevat sitä, milloin ja miten Power Query -kysely voidaan delegoida lähteeseen.

_Kyselyn delegointi lähteeseen_ on Power Query -kyselyn kyky luoda yksittäinen kyselylauseke lähdetietojen noutamista ja muuntamista varten. Katso lisätietoja kohdasta [Power Query -kyselyn delegointi lähteeseen](/power-query/power-query-folding).

## <a name="guidance"></a>Opas

Ohjeet kyselyn delegointiin lähteeseen riippuvat mallitilasta.

Power Query -kyselyn on onnistuttava kyselyn delegoinnissa lähteeseen **DirectQueryn** tai **kaksois**tallennustilan taulukossa.

**Tuonti**taulukossa voi olla mahdollista delegoida kysely lähteeseen. Kun kyseessä on relaatiolähteeseen perustuva kysely ja jos yksittäinen SELECT-lause voidaan muodostaa, saavutat _parhaan tietojen päivityksen suorituskyvyn_ varmistamalla, että kyselyn delegointi lähteeseen onnistuu. Jos muunnosten käsittelyyn tarvitaan yhä Power Queryn koostemoduuli, sinun on pyrittävä minimoimaan sen tekemä työ erityisesti suurten tietojoukkojen kohdalla.

Seuraavassa luettelossa annetaan tarkat ohjeet.

- **Delegoi mahdollisimman suuri osa käsittelystä tietolähteeseen**: Kun Power Query -kyselyn kaikkia vaiheita ei voida delegoida lähteeseen, selvitä vaihe, joka estää kyselyn delegoimisen lähteeseen. Jos se on mahdollista, siirrä tätä seuraavat vaiheet aiempaan kohtaan järjestyksessä, jotta ne voidaan ottaa mukaan kyselyn lähteeseen delegointiin. Ota huomioon, että Power Queryn koostemoduuli voi olla niin älykäs, että se järjestää kyselyvaiheet uudelleen, kun se luo lähdekyselyn.

    Jos kyseessä on relaatiotietolähde, jonka kyselyiden delegoinnin lähteeseen estävä vaihe voidaan suorittaa yksittäisellä SELECT-lauseella tai tallennetun toimintosarjan menettelylogiikan puitteissa, harkitse alkuperäisen SQL-kyselyn käyttämistä seuraavassa kuvatulla tavalla.

- **Käytä alkuperäistä SQL-kyselyä**: Kun Power Query -kysely noutaa tietoja relaatiolähteestä, joissakin lähteissä on mahdollista käyttää alkuperäistä SQL-kyselyä. Kysely voi itse asiassa olla mikä tahansa kelvollinen lauseke, mukaan lukien tallennetun toimintosarjan suorittaminen. Jos lauseke tuottaa useita tulosjoukkoja, vain ensimmäinen palautetaan. Parametrit voidaan esitellä lausekkeessa, ja suosittelemme käyttämään [Value.NativeQuery](/powerquery-m/value-nativequery) -M-funktiota. Tämä funktio on suunniteltu parametriarvojen turvalliseen ja kätevään hyväksymiseen. On tärkeää ymmärtää, että Power Queryn koostemoduuli ei voi delegoida seuraavia kyselyvaiheita lähteeseen, joten sinun on sisällytettävä kaikki – tai yhtä paljon – muunnoslogiikkaa alkuperäiseen kyselylausekkeeseen.

    Kun käytät alkuperäisiä SQL-kyselyjä, kannattaa muistaa kaksi tärkeää seikkaa:

    - DirectQuery-mallitaulukossa kyselyn on oltava SELECT-lauseke, eikä se voi käyttää yleisiä taulukkolausekkeita (CTE) tai tallennettua toimintosarjaa.
    - Lisäävä päivitys ei voi käyttää alkuperäistä SQL-kyselyä. Se pakottaisi Power Queryn koostemoduulin noutamaan kaikki lähderivit ja käyttämään sen jälkeen suodattimia lisäävien muutosten määritykseen.

    > [!IMPORTANT]
    > Alkuperäinen SQL-kysely voi mahdollisesti tehdä muutakin kuin hakea tietoja. Mikä tahansa kelvollinen lauseke voidaan suorittaa (ja mahdollisesti useita kertoja), mukaan lukien lauseke, joka muokkaa tai poistaa tietoja. On tärkeää ottaa käyttöön vähimpien oikeuksien periaate, jolla varmistetaan, että tilillä, jota käytetään tietokannan käyttämiseen, on ainoastaan vaadittujen tietojen lukuoikeus.

- **Valmistele ja muunna lähteen tietoja**: Kun huomaat, että joitakin Power Query -kyselyn vaiheita ei voida delegoida lähteeseen, saatat pystyä käyttämään tietolähteessä muunnoksia. Muunnokset voidaan toteuttaa kirjoittamalla tietokantanäkymä, joka muuntaa lähdetiedot loogisesti. Vaihtoehtoisesti tiedot voidaan valmistella ja muodostaa fyysisesti, ennen kuin Power BI kyselee niitä. Relaatiotietovarasto on erinomainen esimerkki valmistelluista tiedoista, jotka koostuvat tavallisesti ennalta integroiduista organisaatiotietojen lähteistä.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- Power Query [-kyselyn delegointi lähteeseen](/power-query/power-query-folding) -artikkeli
- [Lisäävää päivitys Power BI Premiumissa](../service-premium-incremental-refresh.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
