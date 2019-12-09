---
title: sisällytä tiedosto
description: sisällytä tiedosto
services: powerbi
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: davidi
ms.openlocfilehash: eec30d11c1bd99271416ab1a3a2dbb581687e315
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74698304"
---
## <a name="single-sign-on"></a>Kertakirjautuminen

Kun julkaiset Azure SQL DirectQuery -tietojoukon palveluun, voit ottaa kertakirjautumisen (SSO) käyttöön Azure Active Directory (Azure AD) OAuth2:n käyttäjillesi.

Voit ottaa kertakirjautumisen käyttöön siirtymällä tietojoukon asetuksiin, avaamalla **Tietolähteet**-välilehden ja valitsemalla Kertakirjautuminen-valintaruudun.

![Määritä Azure SQL DQ -valintaikkuna](media/direct-query-sso/sso-dialog.png)

Kun SSO-asetus on käytössä ja käyttäjät käyttävät raportteja, jotka on luotu tietolähteeseen, Power BI lähettää todennetut Azure AD -tunnistetiedot kyselyissä Azure SQL -tietokantaan tai tietovarastoon. Näin Power BI voi noudattaa tietoturva-asetuksia, jotka on määritetty tietolähteen tasolla.

Kertakirjautumisen asetus tulee voimaan kaikissa tietojoukoissa, jotka käyttävät tätä tietolähdettä. Se ei vaikuta tuontitilanteissa käytettyihin todentamismenetelmiin.

> [!Note]
> Azure Multi-Factor Authenticationia (MFA) ei tueta. Käyttäjät, jotka haluavat käyttää kertakirjautumista Azure SQL:n DirectQueryn avulla, täytyy vapauttaa MFA:n käytöstä.