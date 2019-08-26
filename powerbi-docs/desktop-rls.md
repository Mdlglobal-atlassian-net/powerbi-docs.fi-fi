---
title: Rivitason suojauksen (RLS) ymmärtäminen Power BI Desktopissa
description: Rivitason suojauksen määrittäminen tuoduille tietojoukoille ja DirectQuerylle Power BI Desktopissa.
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 08/14/2019
LocalizationGroup: Create reports
ms.openlocfilehash: 91f2da65764480a0cf9cf298a052436b27e18c83
ms.sourcegitcommit: f6ac9e25760561f49d4257a6335ca0f54ad2d22e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560954"
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Rivitason suojaus (RLS) Power BI Desktopissa

Power BI Desktopin rivitason suojauksen (RLS) avulla voidaan rajoittaa tietojen käyttöä tietyille käyttäjille. Suodattimet rajoittavat tietoja rivitasolla. Voit määrittää suodattimia roolien sisällä.

Voit nyt määrittää rivitason suojauksen Power BI:hin tuoduille tietomalleille Power BI Desktopin avulla. Voit myös määrittää rivitason suojauksen tietojoukoille, jotka käyttävät [DirectQueryä](desktop-use-directquery.md), kuten SQL Serveriä. Aiemmin pystyit ottamaan rivitason suojauksen käyttöön vain paikallisissa Analysis Services -malleissa Power BI:n ulkopuolella. Määrität rivitason suojauksen paikalliselle mallille Analysis Servicesin reaaliaikaisia yhteyksiä varten. Tätä suojausvaihtoehtoa ei näy reaaliaikaisen yhteyden tietojoukoille.

> [!IMPORTANT]
> Jos olet määrittänyt rooleja ja sääntöjä Power BI-palvelun sisällä, kyseiset roolit on luotava uudelleen Power BI Desktopissa, ja raportti on julkaistava palveluun.

Lue lisää vaihtoehdoista [RLS:lle Power BI-palvelun sisällä](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Seuraavat vaiheet

[Rivitason suojaus (RLS) Power BI -palvelussa](service-admin-rls.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)