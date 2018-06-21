---
title: Rivitason suojauksen (RLS) ymmärtäminen Power BI Desktopissa
description: Rivitason suojauksen määrittäminen tuoduille tietojoukoille ja DirectQuerylle Power BI Desktopissa.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/03/2018
ms.author: maghan
LocalizationGroup: Create reports
ms.openlocfilehash: 022668737f6bcce987b2923ba7a4416f4a08460a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34287068"
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Rivitason suojaus (RLS) Power BI Desktopissa
Power BI Desktopin rivitason suojaus (RLS) rajoittaa tietojen käyttöä tietyille käyttäjille. Suodattimet rajoittavat tietoja rivitasolla. Voit määrittää suodattimia roolien sisällä.

Voit nyt määrittää rivitason suojauksen Power BI:hin tuoduille tietomalleille Power BI Desktopin avulla. Voit myös määrittää rivitason suojauksen tietojoukoille, jotka käyttävät DirectQueryä, kuten SQL Serveriä. Aiemmin pystyit ottamaan rivitason suojauksen käyttöön vain paikallisissa Analysis Services -malleissa Power BI:n ulkopuolella. Määrität rivitason suojauksen paikalliselle mallille Analysis Servicesin reaaliaikaisia yhteyksiä varten. Suojausvaihtoehtoa ei näy reaaliaikaisen yhteyden tietojoukoille.

> [!IMPORTANT]
> Jos olet määrittänyt rooleja ja sääntöjä Power BI-palvelun sisällä, kyseiset roolit on luotava uudelleen Power BI Desktopissa, ja raportti on julkaistava palveluun.
> 
> 

Lue lisää vaihtoehdoista [RLS:lle Power BI-palvelun sisällä](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Seuraavat vaiheet
[Rivitason suojaus (RLS) Power BI -palvelussa](service-admin-rls.md)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

