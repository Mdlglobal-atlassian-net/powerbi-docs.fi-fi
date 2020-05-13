---
title: Power BI Premium -kapasiteettien valvominen hallintaportaalissa
description: Power BI -hallintaportaalissa voit valvoa Premium-kapasiteettejasi.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/11/2020
LocalizationGroup: Premium
ms.openlocfilehash: 941e67984405392a76a7302d297479bbeccb7842
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83137157"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Kapasiteettien valvonta hallintaportaalissa

**Kunto**-välilehti **Kapasiteettiasetusten** alueella hallintaportaalissa antaa yhteenvedon omasta kapasiteetistasi ja käytössä olevista kuormituksista.  

![Kapasiteetin kunto -välilehti portaalissa](media/service-admin-premium-monitor-portal/admin-portal-health.png)

Jos tarvitset kattavampia mittareita, käytä [Power BI Premium Capacity Metrics](service-admin-premium-monitor-capacity.md)-sovellusta. Sovellus tarjoaa porautumisen ja suodatuksen sekä yksityiskohtaisimmat mittarit kapasiteetin suorituskykyyn vaikuttavista kaikista seikoista. Lue lisää kohdasta[Premium-kapasiteettien valvonta sovelluksen avulla](service-admin-premium-monitor-capacity.md).

> [!IMPORTANT]
> Jos Power BI Premium -kapasiteetissasi on resurssien runsaan käytön aiheuttamia suorituskyky- tai luotettavuusongelmia, voit saada sähköpostiviesteinä ilmoituksia, joiden avulla voit tunnistaa ja ratkaista ongelmat. Tämä voi olla yksinkertainen tapa ratkaista kapasiteettien ylikuormitus. Lisätietoja on artikkelissa [Kapasiteetin ja luotettavuuden ilmoitukset](service-interruption-notifications.md#capacity-and-reliability-notifications).


## <a name="system-metrics"></a>Järjestelmän mittarit

**Kunto**-välilehdellä korkeimmalla tasolla suorittimen ja muistin käyttö tarjoavat nopean näkymän kapasiteetin tärkeimpiin mittareihin. Nämä mittarit ovat kumulatiivisia kaikki kapasiteetin käytössä olevissa kuormitukset huomioiden.

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| SUORITTIMEN KÄYTTÖ | Suorittimen keskimääräinen käyttöaste prosentteina käytettävissä olevista suorittimista. |
| MUISTIN KÄYTTÖ | Keskimääräinen muistin käyttö gigatavuina (Gt).|

## <a name="workload-metrics"></a>Kuormituksen mittarit

Jokaiselle kuormitukselle, joka on käytössä kapasiteettia varten. Suorittimen ja muistin käyttö tulevat näkyviin.

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| SUORITTIMEN KÄYTTÖ | Suorittimen keskimääräinen käyttöaste prosentteina käytettävissä olevista suorittimista. |
| MUISTIN KÄYTTÖ | Keskimääräinen muistin käyttö gigatavuina (Gt).|

### <a name="detailed-workload-metrics"></a>Kuormituksen mittareiden yksityiskohtaiset tiedot

Jokainen kuormitus sisältää lisämittareita. Näytettävien mittarien tyyppi riippuu kuormituksesta. Jos haluat tarkastella kuormituksen yksityiskohtaisia mittareita, napsauta Laajenna-nuolta (alas).

![Työmäärän kunnon laajentaminen](media/service-admin-premium-monitor-portal/admin-portal-health-expand.png)

#### <a name="dataflows"></a>Tietovuot

##### <a name="dataflow-operations"></a>Tietovuotoiminnot

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Kokonaismäärä | Kunkin tietovuon päivitysten kokonaismäärä. |
| Onnistumisten määrä | Kunkin tietovuon onnistuneiden päivitysten kokonaismäärä.|
| Keskimääräinen kesto (min.) | tietovuon päivityksen keskimääräinen kesto minuutteina |
| Enimmäiskesto (min.) | Tietovuon pitkäkestoisimman päivityksen kesto minuutteina. |
| Keskimääräinen odotusaika (min.) | Keskimääräinen viive ajoitetun ajankohdan ja tietovuon päivityksen alkamisen välillä minuutteina. |
| Enimmäisodotusaika (min.) | Tietovuon enimmäisodotusaika minuutteina.  |

#### <a name="datasets"></a>Tietojoukot

##### <a name="refresh"></a>Päivitä

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Kokonaismäärä | Kunkin tietojoukon päivitysten kokonaismäärä. |
| Onnistumisten määrä | Kunkin tietojoukon onnistuneiden päivitysten kokonaismäärä. |
| Virheiden määrä | Kunkin tietojoukon epäonnistuneiden päivitysten kokonaismäärä. |
| Onnistumisprosentti  | Onnistuneiden päivitysten määrä jaettuna päivitysten kokonaismäärällä luotettavuuden mittaamiseksi. |
| Keskimääräinen kesto (min.) | Tietojoukon päivityksen keskimääräinen kesto minuutteina.  |
| Enimmäiskesto (min.) | Tietojoukon pitkäkestoisimman päivityksen kesto minuutteina. |
| Keskimääräinen odotusaika (min.) | Keskimääräinen viive ajoitetun ajankohdan ja tietojoukon päivityksen alkamisen välillä minuutteina. |
| Enimmäisodotusaika (min.) | Tietojoukon enimmäisodotusaika minuutteina. |

##### <a name="query"></a>Kysely

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Kokonaismäärä | Tietojoukolle suoritettavien kyselyjen kokonaismäärä. |
| Keskimääräinen kesto (ms) |tietojoukon kyselyn keskimääräinen kesto millisekunteina|
| Enimmäiskesto (ms) |Tietojoukon pitkäkestoisimman kyselyn kesto millisekunteina. |
| Keskimääräinen odotusaika (ms) |Tietojoukon kyselyn keskimääräinen odotusaika millisekunteina. |
| Enimmäisodotusaika (ms) |Tietojoukon pisimpään odottaneen kyselyn kesto millisekunteina. |

##### <a name="eviction"></a>Häätäminen

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Mallin laskenta | Häädettävien tietojoukkojen kokonaismäärä tälle kapasiteetille. Kun kapasiteetti kohtaa muistipainetta, solmu häätää yhden tai useamman tietojoukon muistista. Passiiviset tietojoukot (joihin ei kyseisellä hetkellä kohdistu kysely- tai uudelleenlataustoimintoja) häädetään ensin. Seuraavaksi häätöjärjestyksessä sovelletaan ”viimeiseksi käytetyt ensin” -mittaria. |

#### <a name="paginated-reports"></a>Sivutetut raportit

##### <a name="report-execution"></a>Raportin suorittaminen

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Suorituslaskenta  | Kuinka monta kertaa käyttäjät ovat katselleet ja suorittaneet raportin.|

##### <a name="report-usage"></a>Raportin käyttö

| **Mittausarvo** | **Kuvaus** |
| --- | --- |
| Onnistumisten määrä | Kuinka monta kertaa käyttäjät ovat katselleet raporttia. |
| Virheiden määrä |Kuinka monta kertaa käyttäjät ovat katselleet raporttia.|
| Rivimäärä |Raportin tietorivien määrä. |
| Tietojen noutamisen kesto (ms) |raportin tietojen noutamiseen keskimääräisesti kuluva aika millisekunteina. Pitkä kesto voi olla osoitus kyselyjen hitaasta suorittamisesta tai muista tietolähteeseen liittyvistä ongelmista.  |
| Prosessin kesto (ms) |Raportin tietojen käsittelemiseen keskimääräisesti kuluva aika millisekunteina. |
| Hahmonnuksen kesto (ms) |Raportin hahmontamiseen selaimessa keskimääräisesti kuluva aika millisekunteina. |

> [!NOTE]
> **AI**-kuormituksen yksityiskohtaiset mittarit eivät ole vielä käytettävissä.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun tiedät, miten voit valvoa Power BI Premium -kapasiteetteja, lue lisätietoja kapasiteettien optimoinnista.

> [!div class="nextstepaction"]
> [Power BI Premium -kapasiteettien optimointi](service-premium-capacity-optimize.md)
