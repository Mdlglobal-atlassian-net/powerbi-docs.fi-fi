---
title: sisällytä tiedosto
description: sisällytä tiedosto
services: powerbi
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: mblythe
ms.openlocfilehash: 94b6959b6bcbf250e54a353e8b725b6c9e5a2e30
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448375"
---
## <a name="single-sign-on"></a>Kertakirjautuminen

Kun julkaiset Azure SQL DirectQuery -tietojoukon palveluun, voit ottaa kertakirjautumisen (SSO) käyttöön Azure Active Directory (Azure AD) OAuth2:n käyttäjillesi.

Voit ottaa kertakirjautumisen käyttöön siirtymällä tietojoukon asetuksiin, avaamalla **Tietolähteet**-välilehden ja valitsemalla Kertakirjautuminen-valintaruudun.

![Määritä Azure SQL DQ -valintaikkuna](media/direct-query-sso/sso-dialog.png)

Kun SSO-asetus on käytössä ja käyttäjät käyttävät raportteja, jotka on luotu tietolähteeseen, Power BI lähettää todennetut Azure AD -tunnistetiedot kyselyissä Azure SQL -tietokantaan tai tietovarastoon. Näin Power BI voi noudattaa tietoturva-asetuksia, jotka on määritetty tietolähteen tasolla.

Kertakirjautumisen asetus tulee voimaan kaikissa tietojoukoissa, jotka käyttävät tätä tietolähdettä. Se ei vaikuta tuontitilanteissa käytettyihin todentamismenetelmiin.

> [!Note]
> Azure Multi-Factor Authenticationia (MFA) ei tueta. Käyttäjät, jotka haluavat käyttää kertakirjautumista Azure SQL:n DirectQueryn avulla, täytyy vapauttaa MFA:n käytöstä.