---
title: Kirjautuneena olevien Power BI -käyttäjien etsiminen
description: Jos olet vuokraajan järjestelmänvalvoja ja haluat nähdä, kuka on kirjautuneena sisään Power BI, voit käyttää Azure Active Directory ‑käyttöoikeudella raportit käyttöraporteista.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: e513607dd89aee15f10145cf62bd461621cc12c0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906721"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Kirjautuneena olevien Power BI -käyttäjien etsiminen

Jos olet vuokraajan järjestelmänvalvoja ja haluat nähdä, kuka on kirjautuneena sisään Power BI käyttää [Azure Active Directory ‑käyttöoikeudella raporttien](/azure/active-directory/reports-monitoring/concept-sign-ins) käyttöraporteista.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> **Sisäänkirjautumiset** raportti sisältää hyödyllisiä tietoja, mutta se ei tunnista käyttöoikeus kullakin käyttäjällä on tyyppiä. Katso käyttöoikeudet Microsoft 365 -hallintakeskuksessa.

## <a name="requirements"></a>Vaatimukset

Kaikki käyttäjät (myös muut kuin järjestelmänvalvojat) voivat nähdä raportin omista kirjautumisistaan, mutta sinun on täytettävä seuraavat vaatimukset, jotta voit nähdä raportin kaikista käyttäjistä.

* Vuokraajan on oltava liitetty Azure Active Directory Premium-käyttöoikeus.

* Sinulla on oltava jokin seuraavista rooleista: Yleinen järjestelmänvalvoja, Suojauksen järjestelmänvalvoja tai rooli, jolla on suojaustietojen lukuoikeudet.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Kirjautumisten tarkastelu Azure-portaalin kautta

Jos haluat tarkastella kirjautumistoimintaa, toimi seuraavien ohjeiden mukaisesti.

1. Valitse **Azure-portaalissa** **Azure Active Directory**.

1. Valitse **Valvonta**-kohdassa **Kirjautumiset**.
   
    ![Näyttökuva Azure-Käyttöliittymän korostettuna Azure Active Directory- ja sisäänkirjautumiset asetuksiin.](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Valitse Sovellus-kenttään suodattimeksi joko **Microsoft Power BI** tai **Power BI Gateway** ja valitse **Käytä**.

    **Microsoft Power BI** suodattimet kirjautumistoimintaa liittyvät palveluun, olisi **Power BI Gateway** kirjautumistoimintaa paikallisen tietoyhdyskäytävän tiettyjä suodattimia.
   
    ![Näyttökuva sisäänkirjautumiset suodattimen korostettuna sovellukset-kentän.](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Tietojen vieminen

Voit myös [sisäänkirjautumisen raportin lataaminen](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) jommassakummassa seuraavista muodoista: CSV-tiedostosta tai JSON-tiedosto.

![Näyttökuva Lataa-painiketta.](media/service-admin-access-usage/download-sign-in-data-csv.png)

Yläosassa **sisäänkirjautumiset** raportin, valitse **Lataa** ja valitse jokin seuraavista vaihtoehdoista:

* **CSV** lataamaan mukaiset tiedot CSV-tiedostona.

* **JSON** ladata mukaiset tiedot JSON-tiedoston.

## <a name="data-retention"></a>Tietojen säilytys

Kirjautumiseen liittyvät tiedot ovat käytettävissä enintään 30 päivän ajan. Katso lisätietoja, [Azure Active Directory-raporttien säilytyskäytännöt](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Seuraavat vaiheet

[Valvonnan käyttö organisaatiossa](service-admin-auditing.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)