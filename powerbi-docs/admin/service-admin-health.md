---
title: Power BI -palvelun kunnon seuraaminen Office 365:ssä
description: Lue, miten voit tarkastella palvelun ajantasaista ja aikaisempaa kuntoa Microsoft 365 -hallintakeskuksesta.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 9d0ed841da3f398b8e0a8dc0a35ed040ccf3cab6
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83139728"
---
# <a name="track-power-bi-service-health-in-office-365"></a>Power BI -palvelun kunnon seuraaminen Office 365:ssä

Microsoft 365 -hallintakeskuksessa on tärkeitä työkaluja Power BI -järjestelmänvalvojille. Työkalut sisältävät ajantasaisia ja historiallisia tietoja palvelun kunnosta. Jos haluat käyttää palvelun kuntotietoja, sinulla on oltava jokin seuraavista rooleista:

* Power BI -palvelun järjestelmänvalvoja

* Office 365:n yleinen järjestelmänvalvoja

Saat lisätietoja rooleista [Power BI:hin liittyvät järjestelmänvalvojaroolit](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi) -ohjeartikkelista.

1. Kirjaudu [Microsoft 365 -hallintakeskukseen](https://portal.office.com/adminportal).

1. Valitse siirtymisruudusta **Näytä kaikki** > **Kunto** > **Palvelun kunto**. Näkyviin tulee Palvelun kunto -sivu:

    ![Näyttökuva Microsoft 365 -hallintakeskuksesta, jossa Kunto- ja Palvelun kunto -vaihtoehdot ovat valittuina.](media/service-admin-health/service-health-tile.png)

1. Valitse **Kaikki palvelut** -luettelosta **Tiedotteet** tai **Tapaukset** ja tarkastele tuloksia. Alla olevasta näyttökuvasta näet yhden kolmesta aktiivisesta neuvosta.

    ![Näyttökuva Palvelun kunto -sivulta, jossa on valittuna kolme tiedotetta Power BI:lle ja Näytä tiedot -vaihtoehdolle.](media/service-admin-health/active-advisories.png)

1. Saat lisätietoja valitsemalla **Näytä tiedot** kohteen kohdalta. Alla olevasta näyttökuvasta näet lisätietoja, kuten viimeaikaiset tilapäivitykset.

    ![Näyttökuva tiedotteiden tiedoista.](media/service-admin-health/advisory-details.png)

    Vieritä alas nähdäksesi lisätietoja ja sulje ruutu, kun olet valmis.

1. Saat kaikkien palveluiden historiatiedot valitsemalla **Palvelun kunto** -sivun oikeasta yläkulmasta **Näytä historia**. Valitse **Viimeiset 7 päivää** tai **Viimeiset 30 päivää**. 

1. Voit palata palvelun senhetkisen kunnon näkymään valitsemalla **Näytä nykyinen tila**.