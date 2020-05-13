---
title: Tietojen käytön rajoittaminen rivitason suojauksen (RLS) avulla Power BI Desktopissa
description: Rivitason suojauksen määrittäminen tuoduille tietojoukoille ja DirectQuerylle Power BI Desktopissa.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 01/31/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 89c33de2ef7319c6dcbeace0df79786128e16cd9
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83334311"
---
# <a name="restrict-data-access-with-row-level-security-rls-for-power-bi-desktop"></a>Tietojen käytön rajoittaminen rivitason suojauksen (RLS) avulla Power BI Desktopissa

Power BI Desktopin rivitason suojauksen (RLS) avulla voidaan rajoittaa tietojen käyttöä tietyille käyttäjille. Suodattimet rajoittavat tietoja rivitasolla. Voit määrittää suodattimia roolien sisällä.

Voit nyt määrittää rivitason suojauksen Power BI:hin tuoduille tietomalleille Power BI Desktopin avulla. Voit myös määrittää rivitason suojauksen tietojoukoille, jotka käyttävät [DirectQueryä](../connect-data/desktop-use-directquery.md), kuten SQL Serveriä. Aiemmin pystyit ottamaan rivitason suojauksen käyttöön vain paikallisissa Analysis Services -malleissa Power BI:n ulkopuolella. Määrität rivitason suojauksen paikalliselle mallille Analysis Servicesin reaaliaikaisia yhteyksiä varten. Tätä suojausvaihtoehtoa ei näy reaaliaikaisen yhteyden tietojoukoille.

> [!IMPORTANT]
> Jos olet määrittänyt rooleja ja sääntöjä Power BI-palvelun sisällä, kyseiset roolit on luotava uudelleen Power BI Desktopissa, ja raportti on julkaistava palveluun. Lue lisää vaihtoehdoista [RLS:lle Power BI-palvelun sisällä](../admin/service-admin-rls.md).

[!INCLUDE [include-short-name](../includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-limitations.md)]

[!INCLUDE [include-short-name](../includes/rls-faq.md)]

## <a name="next-steps"></a>Seuraavat vaiheet

[Rivitason suojaus (RLS) Power BI -palvelussa](../admin/service-admin-rls.md)  

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/).