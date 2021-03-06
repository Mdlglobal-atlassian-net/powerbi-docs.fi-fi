---
title: Kirjautuneena olevien Power BI -käyttäjien etsiminen
description: Jos olet vuokraajan järjestelmänvalvoja ja haluat nähdä, kuka on kirjautuneena sisään Power BI:hin, voit katsoa sen Azure Active Directory -käyttöoikeudella käyttöraporteista.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 32ca01d06f4fc8c3f90f73bf8137349eed0220a6
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83129785"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Kirjautuneena olevien Power BI -käyttäjien etsiminen

Jos olet vuokraajan järjestelmänvalvoja ja haluat nähdä, kuka on kirjautuneena sisään Power BI:hin, katso se [Azure Active Directory -käyttöoikeudella käyttöraporteista](/azure/active-directory/reports-monitoring/concept-sign-ins).

> [!NOTE]
> Tämä **Kirjautumiset**-raportti sisältää hyödyllisiä tietoja, mutta se ei määritä kullakin käyttäjällä olevaa käyttöoikeustyyppiä. Katso käyttöoikeudet Microsoft 365 -hallintakeskuksessa.

## <a name="requirements"></a>Vaatimukset

Kaikki käyttäjät (myös muut kuin järjestelmänvalvojat) voivat nähdä raportin omista kirjautumisistaan, mutta sinun on täytettävä seuraavat vaatimukset, jotta voit nähdä raportin kaikista käyttäjistä.

* Vuokraajalla on oltava vuokraajaan liitetty Azure Active Directory Premium -käyttöoikeus.

* Sinulla on oltava jokin seuraavista rooleista: yleinen järjestelmänvalvoja, suojauksenvalvoja tai suojauksenlukija.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Kirjautumisten tarkastelu Azure-portaalin kautta

Jos haluat tarkastella kirjautumistoimintaa, toimi seuraavien ohjeiden mukaisesti.

1. Valitse **Azure-portaalissa** **Azure Active Directory**.

1. Valitse **Valvonta**-kohdassa **Kirjautumiset**.
   
    ![Näyttökuva Azure-käyttöliittymästä, jossa on korostettuna Azure Active Directory- ja Kirjautumiset -asetukset.](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Valitse Sovellus-kenttään suodattimeksi joko **Microsoft Power BI** tai **Power BI Gateway** ja valitse **Käytä**.

    **Microsoft Power BI** suodattaa palvelun kirjautumistoiminnan, kun taas **Power BI Gateway** suodattaa paikallisen tietoyhdyskäytävän tietyt kirjautumiset.
   
    ![Näyttökuva Kirjautumiset-suodattimesta Sovellukset-kenttä korostettuna.](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Tietojen vieminen

Voit [ladata kirjautumisraportin](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) kahdessa muodossa, joko CSV-tiedostona tai JSON-tiedostona.

![Näyttökuva latauspainikkeesta.](media/service-admin-access-usage/download-sign-in-data-csv.png)

Valitse **Kirjautumiset**-raportin yläreunasta **Lataa** ja sitten toinen seuraavista vaihtoehdoista:

* **CSV** ladataksesi suodattimien mukaiset tiedot csv-tiedostona.

* **JSON** ladataksesi suodattimien mukaiset tiedot json-tiedostona.

## <a name="data-retention"></a>Tietojen säilytys

Kirjautumiseen liittyvät tiedot ovat käytettävissä enintään 30 päivän ajan. Lisätietoja on artikkelissa [Azure Active Directoryn raporttien säilytyskäytännöt](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Seuraavat vaiheet

[Valvonnan käyttö organisaatiossa](service-admin-auditing.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)