---
title: Power BI Desktopin yhdistelmämallin ohjeet
description: Ohjeita yhdistelmämallien kehittämiseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/24/2019
ms.author: v-pemyer
ms.openlocfilehash: fa9ecd66d30839e169252065f7f736189b71b6ce
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "76889476"
---
# <a name="composite-model-guidance-in-power-bi-desktop"></a>{0}Power BI Desktopin yhdistelmämallin ohjeet{0}

Tämä artikkeli on suunnattu tietomallintajille, jotka kehittävät Power BI -yhdistelmämalleja. Artikkelissa kuvaillaan yhdistelmämallin käyttötapauksia ja annetaan suunnitteluohjeita. Erityisesti autamme selvittämään, sopiiko yhdistelmämalli omalle ratkaisullesi. Jos näin on, artikkelin avulla voit myös suunnitella optimaalisen mallin.

> [!NOTE]
> Tämä artikkeli ei sisällä johdantoa yhdistelmämalleihin. Jos et ole perehtynyt yhdistelmämalleihin, suosittelemme, että luet ensin [Yhdistelmämallien käyttäminen Power BI Desktopissa](../desktop-composite-models.md) -artikkelin.
>
> Koska yhdistelmämallit koostuvat vähintään yhdestä DirectQuery-lähteestä, on syytä perehtyä myös [mallien suhteisiin](../desktop-relationships-understand.md), [DirectQuery-malleihin](../desktop-directquery-about.md) ja [DirectQuery-mallin suunnitteluohjeisiin](directquery-model-guidance.md).

## <a name="composite-model-use-cases"></a>Yhdistelmämallin käyttötapaukset

Malli kannattaa mahdollisuuksien mukaan aina kehittää tuontitilassa. Tämä tila tarjoaa parhaan suunnittelullisen joustavuuden ja parhaan suorituskyvyn.

Tuontimallit eivät kuitenkaan pysty ratkaisemaan haasteita, jotka liittyvät suuriin tietomääriin tai lähes reaaliaikaisten tietojen raportointiin. Kummassakin tapauksessa voit harkita DirectQuery-mallia sillä oletuksella, että tiedot on tallennettu [DirectQuery-tilan tukemaan](../power-bi-data-sources.md) yksittäiseen tietolähteeseen.

Voit harkita yhdistelmämallin kehittämistä myös seuraavissa tilanteissa.

- Mallisi voi olla DirectQuery-malli, mutta haluat parantaa suorituskykyä. Yhdistelmämallissa suorituskykyä voidaan parantaa määrittämällä kullekin taulukolle asianmukainen tallennustila. Voit myös lisätä [koosteita](../desktop-aggregations.md). Kummastakin optimoinnista kerrotaan myöhemmin tässä artikkelissa.
- Haluat yhdistää DirectQuery-malliin lisätietoja, jotka on tuotava malliin. Tuodut tiedot voidaan ladata eri tietolähteestä tai lasketuista taulukoista.
- Haluat yhdistää vähintään kaksi DirectQuery-tietolähdettä yhdeksi malliksi.

> [!NOTE]
> Yhdistelmämalleihin ei voi yhdistää reaaliaikaisten yhteyksien lähteitä tai analyyttisia DirectQuery-tietokantalähteitä. Reaaliaikaisten yhteyksien lähteitä ovat esimerkiksi [ulkoiset isännöidyt mallit](../service-datasets-understand.md#external-hosted-models) ja Power BI -tietojoukot. Analyyttisia DirectQuery-tietokantalähteitä ovat esimerkiksi SAP Business Warehouse ja SAP HANA.

## <a name="optimize-model-design"></a>Mallin rakenteen optimoiminen

Yhdistelmämalli voidaan optimoida määrittämällä taulukon [tallennustilat](../desktop-storage-mode.md) ja lisäämällä [koosteita](../desktop-aggregations.md).

### <a name="table-storage-mode"></a>Taulukkotallennustilan tila

Yhdistelmämallissa voit määrittää tallennustilan kullekin taulukolle (lukuun ottamatta laskettuja taulukoita):

- **DirectQuery**: Suosittelemme, että asetat tämän tilan taulukoille, jotka edustavat suuria tietomääriä tai joiden on tuotettava lähes reaaliaikaisia tuloksia. Tietoja ei tuoda näihin taulukoihin. Yleensä nämä taulukot ovat faktatyyppisiä taulukoita, joita käytetään yhteenvetoihin.
- **Tuonti**: Suosittelemme, että asetat tämän tilan dimensiotyyppisille taulukoille, joita käytetään suodattamisessa ja ryhmittelyssä. Se on lisäksi ainoa vaihtoehto sellaisiin lähteisiin perustuville taulukoille, joita DirectQuery-tila ei tue. Lasketut taulukot ovat aina tuontitaulukoita.
- **Kaksoistaulukot**: Suosittelemme, että asetat tämän tilan dimensiotyyppisille taulukoille, jos on olemassa mahdollisuus, että niihin tehdään kyselyitä yhdessä samassa lähteessä olevien faktatyyppisten DirectQuery-taulukoiden kanssa.

Power BI voi tehdä kyselyitä yhdistelmämalleihin useissa eri tilanteissa:

- **Kyselyt vain tuonti- tai kaksoistaulukoihin**: Kaikki tiedot noudetaan mallin välimuistista. Se tuottaa parhaan mahdollisen suorituskyvyn. Tämä tilanne on yleinen dimensiotyyppisille taulukoille, joihin suodattimet tai osittajavisualisoinnit tekevät kyselyjä.
- **Kyselyt saman lähteen kaksoistaulukoihin tai DirectQuery-taulukoihin**: Kaikki tiedot noudetaan lähettämällä vähintään yksi alkuperäinen kysely DirectQuery-lähteeseen. Se tuottaa parhaan mahdollisen suorituskyvyn erityisesti silloin, kun lähdetaulukoissa on asianmukaiset indeksit. Tämä tilanne on yleinen kyselyissä, jotka liittyvät dimensiotyyppisiin kaksoistaulukoihin ja faktatyyppisiin DirectQuery-taulukoihin. Nämä kyselyt ovat _saarensisäisiä_, joten kaikki yksi yhteen- ja yksi moneen -yhteydet arvioidaan [vahvoiksi suhteiksi](../desktop-relationships-understand.md#strong-relationships).
- **Kaikki muut kyselyt**: Näihin kyselyihin liittyy saartenvälisiä suhteita. Tämä johtuu joko siitä, että tuontitaulukko liittyy DirectQuery-taulukkoon, tai siitä, että kaksoistaulukko liittyy eri lähteessä olevaan DirectQuery-taulukkoon, jolloin se käyttäytyy tuontitaulukkona. Kaikki yhteydet arvioidaan [heikoiksi yhteyksiksi](../desktop-relationships-understand.md#weak-relationships). Tämä tarkoittaa myös, että muihin kuin DirectQuery-taulukoihin käytetyt ryhmittelyt on lähetettävä DirectQuery-lähteeseen virtuaalisena taulukkona. Tässä tapauksessa alkuperäinen kysely voi olla tehoton etenkin suurissa ryhmittelyjoukoissa. Lisäksi se saattaa tuoda julki luottamuksellisia tietoja alkuperäisessä kyselyssä.

Yhteenvetona suosittelemme seuraavaa:

- Harkitse tarkkaan, onko yhdistelmämalli todella oikea ratkaisu. Se toki mahdollistaa eri tietolähteiden mallitason integroimisen, mutta samalla se tuo mukanaan suunnittelullisia monimutkaisuuksia, joilla on mahdolliset seurauksensa.
- Aseta tallennustilaksi **DirectQuery**, kun taulukko on suuria tietomääriä sisältävä faktatyyppinen taulukko tai sen on tuotettava lähes reaaliaikaisia tuloksia.
- Aseta tallennustilaksi **kaksoistaulukko**, kun kyseessä on dimensiotyyppinen taulukko, johon tehdään kyselyjä yhdessä samaan lähteeseen perustuvien faktatyyppisten **DirectQuery-** -taulukoiden kanssa.
- Määritä asianmukaiset päivitystiheydet, jotta kaksoistaulukoiden (ja mahdollisten riippuvaisten laskettujen taulukoiden) mallin välimuisti säilyy synkronoituna lähdetietokantojen kanssa.
- Pyri varmistamaan tietojen eheys tietolähteiden välillä (mukaan lukien mallin välimuisti) – heikot suhteet poistavat rivejä, jos liittyvät sarakearvot eivät täsmää.
- Optimoi DirectQuery-tietolähteet asianmukaisten indeksien avulla tehokkaiden liitosten, suodatusten ja ryhmittelyjen varmistamiseksi.
- Älä lataa luottamuksellisia tietoja tuonti- tai kaksoistaulukoihin, jos alkuperäisellä kyselyllä on vaara tulla kaapatuksi. Lisätietoja aiheesta on artikkelissa [Yhdistelmämallien käyttäminen Power BI Desktopissa (Vaikutukset tietoturvaan)](../desktop-composite-models.md#security-implications).

### <a name="aggregations"></a>Koostamiset

Voit lisätä koosteita DirectQuery-taulukoihin yhdistelmämallissasi. Koosteet tallennetaan mallin välimuistiin, joten ne toimivat tuontitaulukkoina, vaikka niitä ei voi käyttää mallitaulukon tavoin. Niiden tarkoituksena on parantaa yksityiskohtaisempien kyselyjen suorituskykyä. Saat lisätietoja ohjeartikkelista [Koosteet Power BI Desktopissa](../desktop-aggregations.md).

Suosittelemme, että koostetaulukko noudattaa tätä perussääntöä: Sen rivien määrän tulisi olla vähintään kymmenen kertaa pienempi kuin pohjana olevassa taulukossa. Jos pohjana olevassa taulukossa on esimerkiksi miljardi riviä, koostetaulukon rivimäärän ei tulisi ylittää sataa miljoonaa riviä. Tämä sääntö varmistaa, että koostetaulukon luomisesta ja ylläpitämisestä on vastaavaa hyötyä suorituskyvylle.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Yhdistelmämallien käyttäminen Power BI Desktopissa](../desktop-composite-models.md)
- [Mallien suhteet Power BI Desktopissa](../desktop-relationships-understand.md)
- [DirectQuery-mallit Power BI Desktopissa](../desktop-directquery-about.md)
- [DirectQueryn käyttö Power BI Desktopissa](../desktop-use-directquery.md)
- [Power BI Desktopin DirectQuery-mallin vianmääritys](../desktop-directquery-troubleshoot.md)
- [Power BI -tietolähteet](../power-bi-data-sources.md)
- [Tallennustilan tila Power BI Desktopissa](../desktop-storage-mode.md)
- [Koosteet Power BI Desktopissa](../desktop-aggregations.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com)
