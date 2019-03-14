---
title: Missä Power BI -vuokraajani sijaitsee?
description: Saat lisätietoja Power BI -vuokraajan sijainnista ja siitä, miten se valitaan. Tämä on tärkeää ymmärtää, sillä se vaikuttaa vuorovaikutukseen, jota sinulla on palvelun kanssa.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 08536d412796b1516b689ed728af0126330edf93
ms.sourcegitcommit: 378265939126fd7c96cb9334dac587fc80291e97
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/07/2019
ms.locfileid: "57580130"
---
# <a name="where-is-my-power-bi-tenant-located"></a>Missä Power BI -vuokraajani sijaitsee?

<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Saat lisätietoja Power BI -vuokraajan sijainnista ja siitä, miten se valitaan. Sijainnin ymmärtäminen on tärkeää, koska se voi vaikuttaa toimiisi palvelussa.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>Power BI-vuokraajan sijainnin määrittäminen

Etsi alue, jolla vuokraajasi sijaitsee, toimi seuraavasti.

1. Valitse Power BI -palvelun yläreunan valikosta ohje (**?**) ja sitten **Tietoja Power BI:stä**.

1. Etsii arvo kohdan **Tietosi on tallennettu kohteeseen** vierestä. Tämä on alue, jolla vuokraajasi sijaitsee. Tämä on myös alue, johon tietosi on tallennettu, ellet käytä erikseen varattuja kapasiteetteja työtilojesi eri alueilla.

    ![Tietoalue](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>Miten tietoalue valitaan

Tietoalue perustuu maahan, jonka valitset luodessasi vuokraajan. Tämä koskee Office 365 -rekisteröitymistä Power BI:n lisäksi, sillä nämä tiedot on jaettu. Jos kyseessä on uusi vuokraaja, valitse oikea maa luettelosta, kun rekisteröidyt.

![Maan valinta](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Power BI valitsee lähimpänä tätä valintaa olevan tietoalueen, joka määrittää, minne vuokraajasi tiedot tallennetaan.

> [!IMPORTANT]
> Tätä valintaa ei voi muuttaa vuokraajan luomisen jälkeen.

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

