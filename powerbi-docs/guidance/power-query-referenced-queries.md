---
title: Power Query -kyselyihin viittaaminen
description: Ohjeita Power Query -kyselyihin viittaamista varten.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/30/2019
ms.author: v-pemyer
ms.openlocfilehash: 242f1e44e3314af900d9f4d4e4fb7380b28b4103
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83278671"
---
# <a name="referencing-power-query-queries"></a>Power Query -kyselyihin viittaaminen

Tämä artikkeli on tarkoitettu tietojen mallintajille, jotka käyttävät Power BI Desktopia. Se antaa sinulle ohjeita muihin kyselyihin viittaavien Power Query ‑kyselyiden määrittämiseen.

Selvennetäänpä ensin, mitä tällä tarkoitetaan: _Kun kysely viittaa toiseen kyselyyn, toisen kyselyn vaiheet tavallaan yhdistetään ensimmäisen kyselyn vaiheisiin ja myös suoritetaan ennen niitä._

Esimerkkitapaus useista kyselyistä: **Kysely 1:n** tiedot ovat peräisin verkkopalvelusta, ja sen lataus on poistettu käytöstä. **Kysely 2**, **kysely 3** ja **kysely 4** viittaavat kaikki **kyselyyn 1**, ja niiden tulokset ladataan tietomalliin.

![Kuvaaja edellisessä kappaleessa kuvattujen kyselyiden riippuvuussuhteista.](media/power-query-referenced-queries/query-dependencies-web-service.png)

Usein tietomallin päivittyessä oletetaan, että Power Query noutaa **kyselyn 1** tuloksen ja että viittaukset käyttävät sitä uudelleen. Näin asia ei ole. Todellisuudessa Power Query suorittaa **kyselyn 2**, **kyselyn 3** ja **kyselyn 4** erikseen.

Tilanteen voi ajatella niin, että **kyselyyn 2** on upotettu sisään **kyselyn 1** vaiheet. Sama koskee **kyselyä 3** ja **kyselyä 4**. Seuraavassa kuvaajassa esitetään selkeämmin kyselyiden suoritustapa.

![Muokattu versio kyselyiden riippuvuussuhteet esittävästä kuvaajasta, sisältää kyselyn 2, kyselyn 3 ja kyselyn 4. Jokaiseen näistä kolmesta kyselystä on sisällytetty kysely 1.](media/power-query-referenced-queries/query-dependencies-web-service-concept.png)

**Kysely 1** suoritetaan kolme kertaa. Kyselyn suorittaminen useita kertoja voi hidastaa tietojen päivittymistä ja vaikuttaa tietolähteeseen negatiivisesti.

**Kyselyn 1** toistuvaa tietojen noutoa ei voi estää käyttämällä [Table.Buffer](/powerquery-m/table-buffer)-funktiota. Tällä funktiolla puskuroidaan taulukko muistiin. Puskuroitua taulukkoa käytetään kuitenkin vain yksittäisen kyselyn suorituksen aikana. Jos esimerkiksi **kysely 1** puskuroidaan **kyselyn 2** suorittamisen yhteydessä, puskuroituja tietoja ei voida käyttää **kyselyn 3** ja **kyselyn 4** suorittamisen aikana. Ne puskuroivat itse tiedot vielä kaksi kertaa uudelleen. (Tämä voi jopa pahentaa negatiivista vaikutusta, koska jokainen viittaava kysely puskuroi saman taulukon.)

> [!NOTE]
> Power Queryn välimuistiarkkitehtuuri on monimutkainen, eikä tässä artikkelissa paneuduta siihen. Power Query voi tallentaa tietolähteestä noudettuja tietoja välimuistiin. Siitä huolimatta se voi kuitenkin noutaa kyselyn suorittamisen aikana tiedot tietolähteestä useammin kuin kerran.

## <a name="recommendations"></a>Suositukset

Yleensä suosittelemme kyselyihin viittaamista, jotta vältetään logiikkapäällekkäisyydet eri kyselyiden välillä. Kuitenkin tämä suunnittelutapa voi hidastaa tietojen päivittymistä ja ylikuormittaa tietolähteitä, kuten edellä on kuvattu.

Suosittelemme, että luot niiden sijasta [tietovuon](../transform-model/service-dataflows-overview.md). Tietovuon käyttö voi parantaa tietojen päivittymisaikaa ja vähentää tietolähteeseen kohdistuvia vaikutuksia.

Voit suunnitella tietovuon niin, että se sisältää lähdetiedot ja muunnokset. Koska tietovuo on pysyvä tietosäilö Power BI ‑palvelun sisällä, se noutaa tiedot nopeasti. Vaikka kyselyihin viittaaminen johtaisi useisiin tietovuopyyntöihin, tietojen päivittymisajat voivat silti parantua.

Jos aiemman esimerkin **kysely 1** suunnitellaan uudestaan tietovuoentiteetiksi, **kysely 2**, **kysely 3** ja **kysely 4** voivat käyttää sitä tietolähteenä. Tämän rakenteen ansiosta entiteetti, jota **kysely 1** käyttää lähteenään, arvioidaan vain kerran.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Omatoiminen tietojen valmisteleminen Power BI:ssä](../transform-model/service-dataflows-overview.md)
- [Tietovoiden luominen ja käyttäminen Power BI:ssä](../transform-model/service-dataflows-create-use.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
