---
title: sisällytä tiedosto
description: sisällytä tiedosto
services: powerbi
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 04/28/2020
ms.author: davidi
ms.openlocfilehash: d56988986cfd994bb21c9bc25d024903719472cf
ms.sourcegitcommit: c772c544ce2e1e2a147b9b62e5579ac3cb59d54c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/29/2020
ms.locfileid: "82255831"
---
## <a name="single-sign-on"></a>Kertakirjautuminen

Kun julkaiset Azure SQL DirectQuery -tietojoukon palveluun, voit ottaa kertakirjautumisen (SSO) käyttöön käyttäjillesi Azure Active Directory (Azure AD) OAuth2:n kautta.

Voit ottaa kertakirjautumisen käyttöön siirtymällä tietojoukon asetuksiin, avaamalla **Tietolähteet**-välilehden ja valitsemalla Kertakirjautuminen-valintaruudun.

![Määritä Azure SQL DQ -valintaikkuna](media/direct-query-sso/sso-dialog.png)

Kun SSO-asetus on käytössä ja käyttäjät käyttävät raportteja, jotka on luotu tietolähteeseen, Power BI lähettää todennetut Azure AD -tunnistetiedot kyselyissä Azure SQL -tietokantaan tai tietovarastoon. Tämän asetuksen avulla Power BI voi noudattaa tietoturva-asetuksia, jotka on määritetty tietolähteen tasolla.

Kertakirjautumisen asetus tulee voimaan kaikissa tietojoukoissa, jotka käyttävät tätä tietolähdettä. Se ei vaikuta tuontitilanteissa käytettyihin todentamismenetelmiin.

