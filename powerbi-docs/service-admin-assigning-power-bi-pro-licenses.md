---
title: Power BI Pro -käyttöoikeuksien määrittäminen
description: Power BI Pro -käyttöoikeuksien määrittäminen
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/22/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: cc22bfa635bb9d91624e6d4a5cdfe301d6478af6
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/08/2018
---
# <a name="assigning-power-bi-pro-licenses"></a>Power BI Pro -käyttöoikeuksien määrittäminen

Järjestelmänvalvojat voivat määrittää Power BI Pro -käyttöoikeuksia käyttäjille useissa hallintaportaaleissa ja useilla PowerShellin cmdlet-komennoilla. Power BI -käyttöoikeuksien hallintaa tukee Azure Active Directory (Azure AD).

* Azure-tilauksen omistajat voivat käyttää Azure Active Directorya [Azure-portaalissa](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0). 

* Yleiset järjestelmänvalvojat ja käyttäjätilien järjestelmänvalvojat voivat käyttää [Office 365 -hallintakeskusta](https://portal.office.com/AdminPortal/Home#/homepage).

## <a name="managing-power-bi-pro-licenses-in-the-azure-portal"></a>Power BI Pro -käyttöoikeuksien hallinta Azure-portaalissa

Power BI käyttää Azure AD:ta perustapalveluna. Azure AD tallentaa käyttäjätilit ja ryhmät sekä muut asetukset, esimerkiksi tiedot ostetuista tuotteista.

### <a name="assigning-licenses-to-individual-user-accounts"></a>Käyttöoikeuksien määrittäminen yksittäisille käyttäjätileille

Jos olet Azure-tilauksen omistaja, voit määrittää Pro-käyttöoikeuksia yksittäisille käyttäjätileille seuraavien ohjeiden mukaisesti:

1. Siirry [Azure-portaaliin](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0). 

2. Valitse vasemmasta siirtymispalkista Azure Active Directory.

    ![kuva](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-01.png)

3. Valitse Azure Active Directoryn kohdasta Käyttöoikeudet.

    ![kuva](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-02.png)

4. Valitse Käyttöoikeudet-kohdassa Kaikki tuotteet > Power BI Pro. Näin näet luettelon kaikista käyttäjistä, joilla on käyttöoikeus.

    ![kuva](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-03.png)

5. Jos haluat määrittää Power BI Pro -käyttöoikeuden uudelle käyttäjätilille, valitse Määritä.

    ![kuva](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-04.png)

> [!NOTE]
> Vaikka voitkin hallita useimpia käyttöoikeusasioita Azure-portaalissa, siellä et kuitenkaan voi ostaa Power BI Pro -käyttöoikeuksia. Voit ostaa Power BI Pro -tilauksia Office 365:n hallintakeskuksessa. Saat lisätietoja ohjeartikkelista [Power BI Pron ostaminen](https://docs.microsoft.com/en-us/power-bi/service-admin-purchasing-power-bi-pro).
>

## <a name="managing-power-bi-pro-licenses-in-the-office-365-admin-center"></a>Power BI Pro -käyttöoikeuksien hallinta Office 365:n hallintakeskuksessa

Jos olet yleinen järjestelmänvalvoja, Office 365:n hallintakeskuksessa voit ostaa Power BI Pro -tilauksen ja hallita organisaation liittyviä käyttöoikeuksia.

Jos olet Office 365 -järjestelmänvalvoja, voit määrittää Pro-käyttöoikeuksia yksittäisille käyttäjätileille seuraavien ohjeiden mukaisesti:

1. Siirry Office 365:n hallintakeskukseen.

2. Laajenna vasemman siirtymisruudun Käyttäjät-kohta ja napsauta Aktiiviset käyttäjät -kohtaa.

    ![kuva](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-05.png)

3. Valitse haluamasi käyttäjät ja napsauta sitten Muokkaa tuotteiden käyttöoikeuksia.

    ![kuva](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-06.png)

4. Vaihda Power BI Pro -kohdan asetukseksi Käytössä ja valitse sitten Tallenna.

    ![kuva](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-07.png)

5. Vahvista valittujen tilien Tila-kohdasta, että Power BI Pro -käyttöoikeuden määritys onnistui.

    ![kuva](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-08.png)

> [!NOTE]
> Jos tilauksesi käyttöoikeudet ovat loppuneet, voit lisätä niitä laajentamalla vasemman siirtymisruudun Laskutus-kohdan ja valitsemalla siitä Tilaukset. Valitse Tilaukset-sivulla Power BI Pro -tilaus ja napsauta sitten Lisää tai poista käyttöoikeuksia.
>

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI Pro organisaatiossasi](service-admin-power-bi-pro-in-your-organization.md)
</br>
[Laajennetun Pro-kokeiluversion aktivointi](service-extended-pro-trial.md)
</br>
[Yksittäisten käyttäjien Power BI -palvelusopimus](https://powerbi.microsoft.com/terms-of-service/)
</br>
[Power BI Premium -ilmoitus](https://aka.ms/pbipremium-announcement)
</br>
[Kirjautuneiden Power BI -käyttäjien etsiminen](service-admin-access-usage.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)