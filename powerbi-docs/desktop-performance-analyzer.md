---
title: Suorituskyvyn murtautumista käyttää Power BI Desktop-raportin elementin suorituskyky
description: Ota selvää, miten visualisointeja ja raportin elementtien toimivat resurssien käyttö ja reagoinnin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1851e0a55bf01073a6591f64de43830a72eca89b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65854409"
---
# <a name="use-performance-analyzer-to-examine-report-element-performance"></a>Suorituskyvyn murtautumista käyttää raportin elementin suorituskyky

- **Power BI Desktop** löydät ulos, miten kunkin raportin elementtien, kuten visualisointeja ja DAX-Kaavat toimivat. Käyttämällä **suorituskyvyn analysoiminen**, voit nähdä ja kirjaa tietueen, joka mittaa, miten kunkin raportin elementtien suorittaa, kun käyttäjä käyttää niitä ja mitä ominaisuuksia niiden suorituskyky on suurin (tai pienin) resurssin paljon resursseja.

![Suorituskyvyn analysointi](media/desktop-performance-analyzer/performance-analyzer-01.png)

Suorituskyvyn analysointi ja näyttää niin kauan päivittämisen tai päivittää kaikki visualisoinnit aloittaa kyseisen käyttäjän-toimintoja, ja näyttää löytämänsä tiedot, jotta voit tarkastella, porautumalla tai viedä tulokset. Suorituskyvyn analysoinnin avulla voit tunnistaa visualisointeja, jotka vaikuttavat raporttiesi tehokkuuteen ja tunnistetaan vaikutus.

## <a name="displaying-the-performance-analyzer-pane"></a>Näytetään suorituskyvyn analysointi-ruudusta

- **Power BI Desktop** Valitse **näkymän** valintanauhasta. - **Näytä** alueella **Näytä** valintanauhan, valitse valintaruutu kohdan **suorituskyvyn analysoiminen** näyttämään suorituskyvyn analysointi-ruudusta.

![Valitse valintanauhan Näytä suorituskyvyn analysointi](media/desktop-performance-analyzer/performance-analyzer-02.png)

Kun valittuna, suorituskyvyn analysoiminen näkyy ruudussa oma oikealta puolelta raporttipohjaan.

## <a name="using-performance-analyzer"></a>Käyttämällä suorituskyvyn analysointi

Suorituskyvyn analyzer (mukaan lukien aika, voit luoda tai päivittää visualisoinnin) käsittelyaika tarvittavat toimenpiteet päivittää raportin elementtien käynnistää käyttäjän toimia, joka johtaa kyselyn suorittamisen tuloksena. Esimerkiksi osittajan säätäminen edellyttää, että osittajan visualisointi voi muokata, lähetetään tietomalliin, kysely ja kyseessä olevan visualisointeja, jotka on päivitettävä tuloksena uudet asetukset. 

Jos haluat aloittaa tallennuksen suorituskyvyn analysoiminen, valitsemalla **Aloita taltiointi**

![Aloita tallennus](media/desktop-performance-analyzer/performance-analyzer-03.png)

Mikä tahansa toimenpiteet raportin näytetään ja kirjautuneena suorituskyvyn analysointi-ruudusta, että visualisoinnissa ladattuna Power BI-tilauksen. Esimerkiksi ehkäpä sinulla on raportti, joka käyttäjien on sanoa kestää kauan, Päivitä. Tai raportin visualisoinnin kestää kauan, joka näytetään, kun liukusäätimen muutetaan. Suorituskyvyn analysoiminen voi kertoa, mitä visual virheen aiheuttaja on ja mitä ominaisuuksia visualisoinnin tunnistaa kestää käsittelemään pisimmän kesto. 

Kun aloitat tallennuksen, **Aloita taltiointi** painike näkyy harmaana ulos (passiivinen, koska olet jo aloittanut tallennus) ja **lopettaa** painike on aktiivinen. 

Suorituskyvyn analysoiminen kerää ja näyttää mitan Suorituskykytiedot reaaliaikaisesti. Niin, että aina, kun valitset visualisoinnin, siirrä osittajan tai muulla tavalla vuorovaikutuksessa suorituskyvyn analysointi näyttää suorituskyvyn tulokset heti sen ruudussa.

Jos ruutu on enemmän tietoja kuin voidaan näyttää, siirry lisätietoja näkyy vierityspalkki.

Kunkin vuorovaikutuksen on osan tunniste ruudussa kuvaavat toiminto, joka käynnistää ne tapahtumat. Seuraavassa kuvassa vuorovaikutuksen oli käyttäjien muuttaa osittajan.

![Osia vuorovaikutuksen tyypin perusteella](media/desktop-performance-analyzer/performance-analyzer-04.png)

Jokainen visualisointi lokitietoja sisältää seuraaviin luokkiin tehtävien suorittamiseen (kesto) käyttämä aika:

* **DAX-kyselyn** -DAX-kysely on pakollinen, onko lähetetään kysely visualisoinnin välillä ja Analysis Services-tulokset.
* **Näytön** -näytössä, mukaan lukien aika, joka noutaa web kuvat tai sijaintitietojen piirtää visualisoinnin aika. 
* **Muut** -aika valmistellaan kyselyt, odottaa muita visualisointeja suorittamiseen tai muita taustakäsittely suoritetaan visualisoinnissa.

![elementtien tiedot](media/desktop-performance-analyzer/performance-analyzer-06.png)

Kun olet säädetään haluat mitata ja suorituskyvyn analysoiminen raportin, voit valita **lopettaa** painike. Suorituskyvyn tiedot pysyvät ruudussa, kun olet valinnut **lopettaa** voit analysoida.

Poista suorituskyvyn analysointi-ruudusta tiedot, valitse **Tyhjennä**. Kaikki tiedot poistetaan ja ei tallenneta, kun valitset **Tyhjennä**. Katso seuraavassa osiossa opit tiedot tallennetaan lokit. 

## <a name="refreshing-visuals"></a>Visualisointien päivittäminen

Voit valita **visualisoinnit** raportin nykyisen sivun kaikki visualisoinnit ja on siten suorituskyvyn analysoiminen kerää tietoja tällaiset visualisoinnit suorituskyvyn analysointi-ruudusta.

Voit myös päivittää yksittäisissä visualisoinneissa. Suorituskyvyn analysoiminen tallentaessaan voit valita **päivittää tätä visualisointia** löytyvät kunkin visualisoinnin, voit päivittää tämän visualisoinnin oikeassa yläkulmassa ja siepata sen suorituskyvyn tiedot.

![Päivitä yksittäisen visualisoinnin:](media/desktop-performance-analyzer/performance-analyzer-07.png)

## <a name="saving-performance-information"></a>Tallennetaan Suorituskykytiedot

Voit tallentaa tiedot, jotka suorituskyvyn analysoiminen Luo raportti valitsemalla **Vie** painike. Valitsemalla **Vie** Luo .json-tiedoston, jossa tiedot suorituskyvyn analysointi-ruudusta. 

![Suorituskyvyn analysoiminen lokitiedoston](media/desktop-performance-analyzer/performance-analyzer-05.png)


## <a name="next-steps"></a>Seuraavat vaiheet
Saat lisätietoja **Power BI Desktopista** ja käytön aloittamisesta tutustumalla seuraaviin artikkeleihin.

* [Mikä on Power BI Desktop?](desktop-what-is-desktop.md)
* [Power BI Desktopin kyselyiden yleiskatsaus](desktop-query-overview.md)
* [Power BI Desktopin tietolähteet](desktop-data-sources.md)
* [Tietoihin yhdistäminen Power BI Desktopissa](desktop-connect-to-data.md)
* [Tietojen muotoilu ja yhdistäminen Power BI Desktopissa](desktop-shape-and-combine-data.md)
* [Yleiset kyselytehtävät Power BI Desktopissa](desktop-common-query-tasks.md)   

