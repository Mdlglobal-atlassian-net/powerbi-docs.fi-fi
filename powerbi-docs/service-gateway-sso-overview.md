---
title: Kertakirjautumisen (SSO) käyttäminen paikallisiin tietolähteisiin
description: Määritä yhdyskäytävä kertakirjautumisen (SSO) käyttöön ottamiseksi Power BI:stä paikallisiin tietolähteisiin.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 10/15/2018
LocalizationGroup: Gateways
ms.openlocfilehash: b728ba6ebaab81ea475f51b9134de34c37d4149b
ms.sourcegitcommit: 3b1a1f55465e5dca88783046c6b4c073e4e22e4b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2018
ms.locfileid: "51580490"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>Yleiskatsaus kertakirjautumisen (SSO) käyttämiseen Power BI -yhdyskäytävissä

Saumaton kertakirjautuminen mahdollistaa Power BI -raporttien ja -koontinäyttöjen päivittämisen paikallisista tiedoista, ja voit ottaa sen käyttöön määrittämällä paikallisen tietoyhdyskäytävän joko rajoitetun Kerberos-delegoinnin tai Security Assertion Markup Languagen (SAML) avulla. Paikallinen tietoyhdyskäytävä helpottaa kertakirjautumista DirectQueryllä, jota se käyttää yhteyden muodostamiseen paikallisiin tietolähteisiin.

Tällä hetkellä tuemme seuraavia tietolähteitä:

* SQL Server ([Kerberos](service-gateway-sso-kerberos.md))
* SAP HANA ([Kerberos](service-gateway-sso-kerberos.md) ja [SAML](service-gateway-sso-saml.md)
* SAP BW ([Kerberos](service-gateway-sso-kerberos.md)
* Teradata ([Kerberos](service-gateway-sso-kerberos.md))
* Spark ([Kerberos](service-gateway-sso-kerberos.md))
* Impala ([Kerberos](service-gateway-sso-kerberos.md))

Kun käyttäjä on vuorovaikutuksessa DirectQuery-raportin kanssa Power BI -palvelussa, jokainen ristisuodatus-, ositus-, lajittelu- ja raportin muokkaustoiminto voi aiheuttaa kyselyjä, jotka suoritetaan reaaliajassa pohjana olevalle paikalliselle tietolähteelle.  Kun tietolähteelle määritetään kertakirjautuminen, kyselyt suoritetaan Power BI:n kanssa vuorovaikutuksessa (verkkosisällön tai Power BI -mobiilisovellusten kautta) olevan käyttäjän käyttäjätiedoilla. Näin kukin käyttäjä näkee tarkasti tiedot, joihin hänellä on oikeudet pohjana olevassa tietolähteessä. Kun kertakirjautuminen on määritetty, eri käyttäjien välimuistissa ei ole jaettuja tietoja.

## <a name="query-steps-when-running-sso"></a>Kyselyn vaiheet suoritettaessa kertakirjautumista

SSO:n avulla suoritettavassa kyselyssä on kolme vaihetta, kuten seuraava kaavio osoittaa.

![Kertakirjautumiskyselyn vaiheet](media/service-gateway-sso-overview/sso-query-steps.png)

> [!NOTE]
> Oraclen SSO ei ole vielä käytössä, mutta sitä kehitetään ja se on tulossa pian.

Seuraavassa on lisätietoja näistä vaiheista:

1. **Power BI -palvelu** lisää jokaiseen kyselyyn *täydellisen käyttäjätunnuksen*, kun määritettyyn yhdyskäytävään lähetetään kyselypyyntö.

2. Yhdyskäytävän on yhdistettävä Azure Active Directoryn täydellinen käyttäjätunnus paikallisen Active Directoryn käyttäjätietoihin.

   a.  Jos Azure AD DirSync (eli *Azure AD Connect*) on määritetty, yhdistäminen toimii automaattisesti yhdyskäytävässä.

   b.  Muussa tapauksessa yhdyskäytävä voi etsiä Azure AD:n täydellisen käyttäjätunnuksen ja yhdistää sen paikalliseen käyttäjään tekemällä haun paikalliselta Active Directory -toimialueelta.

3. Yhdyskäytävän palveluprosessi tekeytyy yhdistetyksi paikalliseksi käyttäjäksi, avaa yhteyden pohjana olevaan tietokantaan ja lähettää kyselyn. Yhdyskäytävää ei tarvitse asentaa samaan tietokoneeseen kuin tietokanta.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun tiedät kertakirjautumisen perusteet, voit lukea lisätietoja Kerberoksesta ja SAML:sta:

* [Kertakirjautuminen (SSO) - Kerberos](service-gateway-sso-kerberos.md)
* [Kertakirjautuminen (SSO) - SAML](service-gateway-sso-saml.md)
