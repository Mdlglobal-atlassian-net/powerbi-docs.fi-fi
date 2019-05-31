---
title: Power BI Premium -kapasiteettien valvominen hallintaportaalissa
description: Power BI -hallintaportaalissa voit valvoa Premium-kapasiteettejasi.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 36b03a67e7c02702a70b6486880cc8eabf93e823
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65564906"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Kapasiteettien valvonta hallintaportaalissa

**Kunnon** välilehdessä **kapasiteettiasetukset** alueella hallintaportaalissa on mittareita, joka on yhteenveto siitä kapasiteetin ja käytössä työnkulut.  

![Kapasiteetin kunnon välilehti-portaalissa](media/service-admin-premium-monitor-portal/admin-portal-health.png)

Jos haluat kattavamman mittareita, käytä [Power BI Premium-kapasiteetin Mittaustietoihin](service-admin-premium-monitor-capacity.md) sovelluksen. Sovellus tarjoaa ylös ja alas suodatusta ja tarkempi luomiensa lähellä jokaisen osan, joka vaikuttaa kapasiteetin suorituskykyä. Lisätietoja on artikkelissa [valvonnan Premium-kapasiteetteja sovelluksessa](service-admin-premium-monitor-capacity.md).

## <a name="system-metrics"></a>Järjestelmän mittarit

Valitse **kunnon** välilehti ylimmällä tasolla suorittimen käyttö ja anna luettelon tärkeimpiä mittareita kapasiteetti muistinkäyttö. Näiden arvojen tila on koottu, mukaan lukien kaikki käytössä työmääriä kapasiteetti.

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| SUORITTIMEN KÄYTTÖ | Keskimääräinen suorittimen käyttöaste yhteensä käytettävissä suorittimen prosenttilukuna. |
| MUISTINKÄYTTÖ | Keskimääräinen muistinkäyttö gigatavuina (gt).|

## <a name="workload-metrics"></a>Kuormituksen mittarit

Kuormituksen kunkin kapasiteetin käytössä. Suorittimen käyttö ja muistinkäyttö ovat näkyvissä.

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| SUORITTIMEN KÄYTTÖ | Keskimääräinen suorittimen käyttöaste yhteensä käytettävissä suorittimen prosenttilukuna. |
| MUISTINKÄYTTÖ | Keskimääräinen muistinkäyttö gigatavuina (gt).|

### <a name="detailed-workload-metrics"></a>Yksityiskohtaiset kuormituksen mittarit

Jokainen kuormitus on lisää mittareita. Näytetään mittareiden määräytyvät kuormitus. Näet yksityiskohtaiset mittareita kuormituksen napsauttamalla Laajenna (ALANUOLI).

![Laajenna kuormituksen kunto](media/service-admin-premium-monitor-portal/admin-portal-health-expand.png)

#### <a name="dataflows"></a>Tietovuot

##### <a name="dataflow-operations"></a>Tietovirrassa toiminnot

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Kokonaismäärä | Kunkin tietovuon päivitysten kokonaismäärä. |
| Onnistumisten määrä | Yhteensä onnistui päivitykset kunkin tietovirrassa.|
| Keskimääräinen kesto (min) | tietovuon päivityksen keskimääräinen kesto minuutteina |
| Suurin kesto (min) | Tietovuon pitkäkestoisimman päivityksen kesto minuutteina. |
| Keskimääräinen odotusaika (min) | Keskimääräinen viive ajoitetun ajankohdan ja tietovuon päivityksen alkamisen välillä minuutteina. |
| Suurin odotusaika (min) | Tietovuon enimmäisodotusaika minuutteina.  |

#### <a name="datasets"></a>Tietojoukot

##### <a name="refresh"></a>Päivitä

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Kokonaismäärä | Kunkin tietojoukon päivitysten kokonaismäärä. |
| Onnistumisten määrä | Onnistuneet summa päivittyy kullekin tietojoukolle. |
| Virheiden määrä | Epäonnistuneet päivitykset yhteensä kullekin tietojoukolle. |
| Onnistumisprosentti  | Mitata yhteensä päivitykset jaettuna onnistuneiden päivitysten määrä. luotettavuutta. |
| Keskimääräinen kesto (min) | Tietojoukon päivityksen keskimääräinen kesto minuutteina.  |
| Suurin kesto (min) | Tietojoukon pitkäkestoisimman päivityksen kesto minuutteina. |
| Keskimääräinen odotusaika (min) | Keskimääräinen viive ajoitetun ajankohdan ja tietojoukon päivityksen alkamisen välillä minuutteina. |
| Suurin odotusaika (min) | Tietojoukon enimmäisodotusaika minuutteina. |

##### <a name="query"></a>Kysely

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Kokonaismäärä | Tietojoukolle suoritettavien kyselyjen kokonaismäärä. |
| Keskimääräinen kesto (ms) |tietojoukon kyselyn keskimääräinen kesto millisekunteina|
| Enimmäiskesto (ms) |Tietojoukon pitkäkestoisimman kyselyn kesto millisekunteina. |
| Keskimääräinen odotusaika (ms) |Tietojoukon kyselyn keskimääräinen odotusaika millisekunteina. |
| Suurin odotusaika (ms) |Tietojoukon pisimpään odottaneen kyselyn kesto millisekunteina. |

##### <a name="eviction"></a>Häätäminen

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Mallin määrä | Tietojoukon häätöjä tämän kapasiteetin kokonaismäärä. Kun kapasiteetti kohtaa muistipainetta, solmu häätää yhden tai useamman tietojoukon muistista. Passiiviset tietojoukot (joihin ei kyseisellä hetkellä kohdistu kysely- tai uudelleenlataustoimintoja) häädetään ensin. Seuraavaksi häätöjärjestyksessä sovelletaan ”viimeiseksi käytetyt ensin” -mittaria. |

#### <a name="paginated-reports"></a>Sivutetut raportit

##### <a name="report-execution"></a>Raportin suorittaminen

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Suorittaminen määrä  | Montako kertaa raportin suoritettiin käyttäjien.|

##### <a name="report-usage"></a>Raportin käyttö

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Onnistumisten määrä | Montako kertaa käyttäjä on tarkasteltu raportin. |
| Virheiden määrä |Montako kertaa käyttäjä on tarkasteltu raportin.|
| Rivimäärä |Raportin tietorivien määrä. |
| Tietojen noutaminen kesto (ms) |raportin tietojen noutamiseen keskimääräisesti kuluva aika millisekunteina. Pitkä kesto voi olla osoitus kyselyjen hitaasta suorittamisesta tai muista tietolähteeseen liittyvistä ongelmista.  |
| Käsittelyn kesto (ms) |Raportin tietojen käsittelemiseen keskimääräisesti kuluva aika millisekunteina. |
| Hahmontaminen kesto (ms) |Raportin hahmontamiseen selaimessa keskimääräisesti kuluva aika millisekunteina. |

> [!NOTE]
> Yksityiskohtaiset tiedot **AI** kuormituksen eivät ole vielä käytettävissä.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun tiedät, miten voit valvoa Power BI Premium -kapasiteetteja, lue lisätietoja kapasiteettien optimoinnista.

> [!div class="nextstepaction"]
> [Power BI Premium-kapasiteetteja optimointi](service-premium-capacity-optimize.md)
