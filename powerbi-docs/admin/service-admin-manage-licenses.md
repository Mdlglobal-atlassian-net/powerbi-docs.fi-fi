---
title: Power BI -käyttöoikeuksien tarkasteleminen ja hallinta
description: Järjestelmänvalvojien ohjeet siihen, miten he voivat tarkastella ja hallita organisaationsa Power BI -käyttäjien käyttöoikeuksia.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/08/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 2d5eab5dbbf600227611cadc870fab1b3e44a4b7
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83138895"
---
# <a name="view-and-manage-power-bi-user-licenses"></a>Power BI -käyttöoikeuksien tarkasteleminen ja hallinta

Tässä artikkelissa kerrotaan, miten järjestelmänvalvojat voivat käyttää Microsoft 365 -hallintakeskusta tai Azure-portaalia käyttäjien käyttöoikeuksien tarkastelemiseen ja hallintaan.

> [!NOTE]
>
>Käyttäjälle on mahdollista määrittää sekä Power BI -käyttöoikeus (ilmainen) että Power BI Pro -käyttöoikeus. Näin voi käydä, kun käyttäjä rekisteröityy maksuttomaan käyttöoikeuteen ja hänelle määritetään myöhemmin Power BI Pro -käyttöoikeus. Korkein käyttöoikeustaso tulee tällöin voimaan.
>

## <a name="view-your-subscriptions"></a>Omien tilausten tarkasteleminen

Jos haluat tarkistaa, mitä Power BI -tilaukset organisaatiossasi on, toimi seuraavasti.

1. Kirjaudu [Microsoft 365 -hallintakeskukseen](https://admin.microsoft.com).
2. Valitse siirtymisvalikossa **Laskutus** > **Tuotteet ja palvelut**.

Aktiiviset Power BI -tilauksesi ja muut tilauksesi tulevat näkyviin. Luettelossa voi näkyä odottamaton Power BI -tilaus (ilmainen), kuten seuraavassa kuvassa.

  ![Käyttäjän aktivoima ilmainen Power BI -tilaus](media/service-admin-manage-licenses/power-bi-free-user-activated.png)

Tämän tyyppinen tilaus luodaan sinulle, kun käyttäjät hyödyntävät omatoimista rekisteröitymistä. Lisätietoja on artikkelissa [Power BI organisaatiossasi](https://docs.microsoft.com/microsoft-365/admin/misc/power-bi-in-your-organization?view=o365-worldwide).

## <a name="manage-user-licenses-in-microsoft-365"></a>Käyttöoikeuksien hallinta Microsoft 365:ssä

Jos haluat hallita käyttöoikeuksia Microsoft 365 -hallintakeskuksen avulla, lue artikkeli [Yrityksen tilausten ja laskutuksen dokumentaatio](https://docs.microsoft.com/microsoft-365/commerce/?view=o365-worldwide).

## <a name="manage-user-licenses-in-azure-portal"></a>Käyttöoikeuksien hallinta Azure-portaalissa

Voit tarkastella Power BI -käyttöoikeuksia ja määrittää niitä Azure-portaalin avulla seuraavasti.

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

2. Etsi **Azure Active Directory** ja valitse se.

3. Valitse Azure Active Directoryn resurssivalikon **Hallitse**-kohdassa **Käyttöoikeudet**.

4. Valitse **Kaikki tuotteet** resurssivalikosta ja valitse sitten Power BI -käyttöoikeustyyppi. Esiin tulee luettelo käyttäjistä, joilla on käyttöoikeus.

5. Kun haluat määrittää käyttöoikeuden valitse komentopalkista **+ Määritä**. Valitse **Määritä käyttöoikeus** -sivulla käyttäjä, valitse sitten **Määritysasetukset** ja ota Power BI -käyttöoikeus käyttöön valitulle käyttäjätilille.

6. Jos haluat poistaa käyttöoikeuden, valitse valintaruutu käyttäjän nimen vieressä ja valitse sitten **Poista käyttöoikeus**.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Power BI Pron ostaminen](service-admin-purchasing-power-bi-pro.md)
- [Käyttöoikeudet organisaatiollesi](service-admin-licensing-organization.md)
