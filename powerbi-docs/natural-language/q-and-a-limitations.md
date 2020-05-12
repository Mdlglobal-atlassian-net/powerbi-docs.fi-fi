---
title: Power BI Q&A:n rajoitukset
description: Power BI Q&A:n nykyiset rajoitukset
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/21/2020
ms.author: maggies
ms.openlocfilehash: b71fd2986fb79adf88493416ac8234f2656aefa9
ms.sourcegitcommit: a199dda2ab50184ce25f7c9a01e7ada382a88d2c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/06/2020
ms.locfileid: "82866767"
---
# <a name="limitations-of-power-bi-qa"></a>Power BI Q&A:n rajoitukset

Power BI Q&A:ssa on tällä hetkellä on joitakin rajoituksia.

## <a name="data-sources"></a>Tietolähteet

### <a name="supported-data-sources"></a>Tuetut tietolähteet

Power BI Q&A tukee seuraavia tietolähteiden kokoonpanoja Power BI -palvelussa:

- Tuontitila
- Reaaliaikaisen yhteyden muodostaminen Azure Analysis Servicesiin
- Reaaliaikaisen yhteyden muodostaminen SQL Server-Analysis Servicesiin (yhdyskäytävän kanssa)
- Power BI -tietojoukot

Kaikissa näissä kokoonpanoissa tuetaan myös rivitason suojausta.

### <a name="data-sources-not-supported"></a>Tietolähteitä ei tueta

Power BI Q&A ei tällä hetkellä tue seuraavia kokoonpanoja:

- Objektitason suojaus minkä tahansa tietolähdetyypin kanssa
- DirectQuery mitä tahansa lähdettä vastaan. Vaihtoehtoinen menetelmä on käyttää reaaliaikaista yhteyden muodostamista DirectQueryä käyttävän Azure Analysis Servicesin kanssa.
- Yhdistelmämallit
- Reporting Services 

## <a name="tooling-limitations"></a>Työkalujen rajoitukset

Uuden työkaluvalintaikkunan avulla käyttäjät voivat mukauttaa ja parantaa Q&A:n luonnollista kieltä. Jos haluat lisätietoja työkaluista, lue [Q&A-työkalujen esittely](q-and-a-tooling-intro.md).

## <a name="review-question-limitations"></a>Kysymysten tarkastelun rajoitukset

Kysymysten tarkastelu tallentaa vain tietomalliasi vastaan kysytyt kysymykset enintään 28 päivän ajan. Kun käytät uutta tarkastele kysymyksiä -ominaisuutta, saatat huomata, ettei joitakin kysymyksiä tallenneta. Tämä kuuluu asiaan, sillä luonnollisen kielen moduuli suorittaa sarjan tietojenpuhdistusvaiheita varmistaakseen, ettei käyttäjän jokaista näppäimen painallusta tallenneta tai näytetä.

Vuokraajan järjestelmänvalvojat voivat käyttää vuokraajan järjestelmänvalvojan asetuksia kysymysten tallennusten hallintaan. Käyttöoikeudet perustuvat käyttöoikeusryhmään. 

Käyttäjät voivat myös estää kysymystensä tallentamisen valitsemalla **Asetukset** > **Yleiset** ja poistamalla valinnan, **Salli Q&A:n kirjata hakulauseeni**. 

## <a name="teach-qa-limitations"></a>Q&A:n opettamisen rajoitukset

Opeta Q&A:ta -toiminnon avulla voit korjata kahdentyyppisiä virheitä:

- Määritä kentälle sana.
- Määritä sanalle suodatusehto.

Tällä hetkellä emme tue tunnistetun termin määrittelyä uudelleen tai muiden ehtojen tai lausekkeiden määrittämistä. Suodatusehtoja määrittäessäsi voit lisäksi käyttää vain rajoitettua kielen alijoukkoa, mukaan lukien:

- Maa, joka on USA
- Maa, joka ei ole USA
- Tuotteet > 100
- Tuotteet on suurempi kuin 100
- Tuotteet = 100
- Tuotteet on 100
- Tuotteet < 100
- Tuotteet on pienempi kuin 100

> [!NOTE]
> Q&A-työkalut tukevat vain tuontitilaa. Se ei vielä tue yhdistämistä paikalliseen tai Azure Analysis Servicesin tietolähteeseen. Tämä rajoitus poistetaan seuraavissa Power BI -julkaisuversioissa.

### <a name="statements-not-supported"></a>Lausekkeita ei tueta

- Mittarien käyttämistä ehdoissa ei tueta tällä hetkellä. Tämän sijaan voit muuntaa mittarit lasketuiksi sarakkeiksi.
- Useita ehtoja ei tueta. Voit kiertää ongelman luomalla DAX-lasketun sarakkeen, joka laskee useita ehtoja sisältävän lausekkeen totuusarvon, ja käyttää tätä kenttää.
- Jos et määritä suodatinehtoa, kun Q&A kysyy tietojen alijoukkoa, et voi tallentaa määritelmää, vaikka koko lausekkeessa ei olisi punaisia alleviivauksia.

## <a name="next-steps"></a>Seuraavat vaiheet

Luonnollisen kielen moduulin parantamiseen on olemassa joitain parhaita käytäntöjä. Lisätietoja: [Q&A:n parhaat käytännöt](q-and-a-best-practices.md).