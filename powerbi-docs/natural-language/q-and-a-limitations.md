---
title: Power BI Q&A:n rajoitukset
description: Power BI Q&A:n nykyiset rajoitukset
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2019
ms.author: mohaali
ms.openlocfilehash: 9f1beed3408d53a58a0fb725f9d98a4a95bb1b7c
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73874895"
---
# <a name="limitations-of-power-bi-qa"></a>Power BI Q&A:n rajoitukset

Power BI Q&A:ssa on tällä hetkellä on joitakin rajoituksia.

## <a name="data-sources"></a>Tietolähteet

### <a name="supported-data-sources"></a>Tuetut tietolähteet

Power BI Q&A tukee seuraavia tietolähteiden kokoonpanoja Power BI -palvelussa:

- Tuontitila
- Reaaliaikaisen yhteyden muodostaminen Azure Analysis Servicesiin
- Reaaliaikaisen yhteyden muodostaminen SQL Server-Analysis Servicesiin (yhdyskäytävän kanssa)
- Power BI -tietojoukot Power BI Desktop raportoi Q&A:n virheestä Power BI -tietojoukkoa käytettäessä. Kuitenkin kun julkaiset raportin Power BI -palveluun, virhe poistuu.

Kaikissa näissä kokoonpanoissa tuetaan myös rivitason suojausta.

### <a name="data-sources-not-supported"></a>Tietolähteitä ei tueta

Power BI Q&A ei tällä hetkellä tue seuraavia kokoonpanoja:

- Objektitason suojaus minkä tahansa tietolähdetyypin kanssa
- DirectQuery mitä tahansa lähdettä vastaan. Vaihtoehtoinen tukimenetelmä on käyttää reaaliaikaista yhteyden muodostamista DirectQueryä käyttävän Azure Analysis Servicesin kanssa.
- Yhdistelmämallit
- Reporting Services 

## <a name="tooling-limitations"></a>Työkalujen rajoitukset

Uuden työkaluvalintaikkunan avulla käyttäjät voivat mukauttaa ja parantaa Q&A:n luonnollista kieltä. Jos haluat lisätietoja työkaluista, lue [Q&A-työkalujen esittely](q-and-a-tooling-intro.md).

## <a name="review-question-limitations"></a>Kysymysten tarkastelun rajoitukset

Kysymysten tarkastelu tallentaa vain tietomalliasi vastaan kysytyt kysymykset enintään 28 päivän ajan. Kun käytät uutta tarkastele kysymyksiä -ominaisuutta, saatat huomata, ettei joitakin kysymyksiä tallenneta. Tämä kuuluu asiaan, sillä luonnollisen kielen moduuli suorittaa sarjan tietojenpuhdistusvaiheita varmistaakseen, ettei käyttäjän jokainen näppäimen painallus tallennu tai näy.

Vuokraajan järjestelmänvalvojat voivat käyttää vuokraajan järjestelmänvalvojan asetuksia kysymysten tallennusten hallintaan. Käyttöoikeudet perustuvat käyttöoikeusryhmään. 

Käyttäjät voivat myös estää kysymystensä tallentamisen valitsemalla **Asetukset** > **Yleiset** ja poistamalla valinnan, **Salli Q&A:n kirjata hakulauseeni**. 

## <a name="teach-qa-limitations"></a>Q&A:n opettamisen rajoitukset

Opeta Q&A:ta -toiminnon avulla voit korjata kahdentyyppisiä virheitä:

- Määritä kentälle sana.
- Määritä sanalle suodatusehto.

Tällä hetkellä emme tue tunnistetun termin määrittelyä uudelleen tai muiden ehtojen tai lausekkeiden määrittämistä. Suodatusehtoja määrittäessäsi voit lisäksi käyttää vain rajoitettua kielen alijoukkoa, mukaan lukien:

- ”Maa”, joka on ”USA”
- ”Maa”, joka ei ole ”USA”
- ”Paino” > 2 000
- ”Paino = 2 000
- ”Paino” < 2 000

> [!NOTE]
> Q&A-työkalut tukevat vain tuontitilaa. Se ei vielä tue yhdistämistä paikalliseen tai Azure Analysis Servicesin tietolähteeseen. Tämä rajoitus poistetaan seuraavissa Power BI -julkaisuversioissa.

### <a name="statements-not-supported"></a>Lausekkeita ei tueta

- Mittarien käyttämistä ehdoissa ei tueta tällä hetkellä. Tämän sijaan voit muuntaa mittarit lasketuiksi sarakkeiksi.
- Useita ehtoja ei tueta. Voit kiertää ongelman luomalla DAX-lasketun sarakkeen, joka laskee useita ehtoja sisältävän lausekkeen totuusarvon, ja käyttää tätä kenttää.
- Jos et määritä suodatinehtoa, kun Q&A kysyy tietojen alijoukkoa, et voi tallentaa määritelmää, vaikka koko lausekkeessa ei olisi punaisia alleviivauksia.
