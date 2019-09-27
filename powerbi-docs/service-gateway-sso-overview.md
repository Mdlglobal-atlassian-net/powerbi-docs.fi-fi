---
title: Kertakirjautumisen (SSO) käyttäminen paikallisiin tietolähteisiin
description: Määritä yhdyskäytävä kertakirjautumisen (SSO) käyttöön ottamiseksi Power BI:stä paikallisiin tietolähteisiin.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 4991117cfa8b34d9adbbd2dc29082d1e75b6852d
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/18/2019
ms.locfileid: "71100396"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>Yleiskatsaus kertakirjautumisen (SSO) käyttämiseen Power BI -yhdyskäytävissä

Saumaton kertakirjautuminen mahdollistaa Power BI -raporttien ja -koontinäyttöjen päivittämisen reaaliaikaisesti paikallisista tiedoista, ja voit ottaa sen käyttöön määrittämällä paikallisen tietoyhdyskäytävän joko rajoitetun Kerberos-delegoinnin tai Security Assertion Markup Languagen (SAML) avulla. Paikallinen tietoyhdyskäytävä tukee kertakirjautumista DirectQueryllä, jota se käyttää yhteyden muodostamiseen paikallisiin tietolähteisiin.

Tällä hetkellä tuemme seuraavia tietolähteitä:

* SQL Server ([Kerberos](service-gateway-sso-kerberos.md))
* SAP HANA ([Kerberos](service-gateway-sso-kerberos.md) ja [SAML](service-gateway-sso-saml.md))
* SAP BW ([Kerberos](service-gateway-sso-kerberos.md))
* Teradata ([Kerberos](service-gateway-sso-kerberos.md))
* Spark ([Kerberos](service-gateway-sso-kerberos.md))
* Impala ([Kerberos](service-gateway-sso-kerberos.md))

Kun käyttäjä on vuorovaikutuksessa DirectQuery-raportin kanssa Power BI -palvelussa, jokainen ristisuodatus-, ositus-, lajittelu- ja raportin muokkaustoiminto voi aiheuttaa kyselyjä, jotka suoritetaan reaaliajassa pohjana olevalle paikalliselle tietolähteelle. Kun tietolähteelle määritetään kertakirjautuminen, kyselyt suoritetaan Power BI:n kanssa vuorovaikutuksessa (verkkosisällön tai Power BI -mobiilisovellusten kautta) olevan käyttäjän käyttäjätiedoilla. Näin kukin käyttäjä näkee tarkasti tiedot, joihin hänellä on oikeudet pohjana olevassa tietolähteessä. Kun kertakirjautuminen on määritetty, eri käyttäjien välimuistissa ei ole jaettuja tietoja.

## <a name="query-steps-when-running-sso"></a>Kyselyn vaiheet suoritettaessa kertakirjautumista

SSO:n avulla suoritettavassa kyselyssä on kolme vaihetta, kuten seuraava kaavio osoittaa.

![Kertakirjautumiskyselyn vaiheet](media/service-gateway-sso-overview/sso-query-steps.png)

Seuraavassa on lisätietoja näistä vaiheista:

1. **Power BI -palvelu** lisää jokaiseen kyselyyn *täydellisen käyttäjätunnuksen*, kun määritettyyn yhdyskäytävään lähetetään kyselypyyntö.

2. Yhdyskäytävän on yhdistettävä Azure Active Directoryn täydellinen käyttäjätunnus paikallisen Active Directoryn käyttäjätietoihin.

   a.  Jos Azure AD DirSync (eli *Azure AD Connect*) on määritetty, yhdistäminen toimii automaattisesti yhdyskäytävässä.

   b.  Muussa tapauksessa yhdyskäytävä voi etsiä Azure AD:n täydellisen käyttäjätunnuksen ja yhdistää sen paikalliseen käyttäjään tekemällä haun paikalliselta Active Directory -toimialueelta.

3. Yhdyskäytävän palveluprosessi tekeytyy yhdistetyksi paikalliseksi käyttäjäksi, avaa yhteyden pohjana olevaan tietokantaan ja lähettää kyselyn. Yhdyskäytävää ei tarvitse asentaa samaan tietokoneeseen kuin tietokanta.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun tiedät kertakirjautumisen perusteet yhdyskäytävän kautta, voit lukea lisätietoja Kerberoksesta ja SAML:sta:

* [Kertakirjautuminen (SSO) - Kerberos](service-gateway-sso-kerberos.md)
* [Kertakirjautuminen (SSO) - SAML](service-gateway-sso-saml.md)
