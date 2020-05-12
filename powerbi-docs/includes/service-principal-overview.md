---
title: Palvelun päänimen yleiskatsaus
description: Palvelun päänimen yleiskatsaus
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 04/05/2020
ms.custom: include file
ms.openlocfilehash: 7fc4412a66602fe3a6548c3e1afb06de788da90d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "82616119"
---
Palvelun päänimi todentamismenetelmä, jonka avulla Azure AD -sovellus voi käyttää Power BI -palvelun sisältöä ja ohjelmointi rajapintoja.

Kun luot Azure Active Directory (Azure AD) -sovelluksen, luodaan [palvelun pääobjekti](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object). Palvelun pääobjekti, jota kutsutaan myös *palvelun päänimeksi*, antaa Azure AD:lle oikeuden sovelluksesi todentamiseen. Kun sovellus on todennettu, se voi käyttää Azure AD:n vuokraajaresursseja.

Todentamisessa palvelun päänimi käyttää Azure AD -sovelluksen *sovellustunnusta* ja jotakin seuraavista:
* Sovellussalaisuus
* Varmenne