---
title: Yleiskatsaus kertakirjautumisen (SSO) käyttämiseen Power BI -yhdyskäytävissä
description: Määritä yhdyskäytävä kertakirjautumisen (SSO) käyttöön ottamiseksi Power BI:stä paikallisiin tietolähteisiin.
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: b5ef7e99edbf862891811047ea5f1f961aaea348
ms.sourcegitcommit: b22a9a43f61ed7fc0ced1924eec71b2534ac63f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/21/2020
ms.locfileid: "77527587"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>Yleiskatsaus kertakirjautumisen (SSO) käyttämiseen Power BI -yhdyskäytävissä

Voit saada saumattoman kertakirjautumisen, jolloin Power BI -raportit ja -koontinäytöt päivitetään reaaliaikaisesti paikallisista tiedoista, määrittämällä paikallisen tietoyhdyskäytävän. Voit valita, määritätkö yhdyskäytävän rajoitetun [Kerberos](service-gateway-sso-kerberos.md)-delegoinnin vai Security Assertion Markup Languagen ([SAML](service-gateway-sso-saml.md)) avulla. Paikallinen tietoyhdyskäytävä tukee kertakirjautumista käyttämällä [DirectQueryä](desktop-directquery-about.md) tai päivitystä, joka muodostaa yhteyden paikallisiin tietolähteisiin. 

Power BI tukee seuraavia tietolähteitä:

* SQL Server (Kerberos)
* SAP HANA (Kerberos ja SAML)
* SAP BW -sovelluspalvelin (Kerberos)
* SAP BW -viestipalvelin (Kerberos) – julkinen esikatselu
* Oracle (Kerberos) – julkinen esikatselu
* Teradata (Kerberos)
* Spark (Kerberos)
* Impala (Kerberos)

Emme tällä hetkellä tue SSO:ta [M-laajennuksissa](https://github.com/microsoft/DataConnectors/blob/master/docs/m-extensions.md).

Kun käyttäjä on vuorovaikutuksessa DirectQuery-raportin kanssa Power BI -palvelussa, jokainen ristisuodatus-, ositus-, lajittelu- ja raportin muokkaustoiminto voi aiheuttaa kyselyjä, jotka suoritetaan reaaliajassa pohjana olevalle paikalliselle tietolähteelle. Kun määrität kertakirjautumisen tietolähteelle, kyselyt suoritetaan Power BI:n kanssa vuorovaikutuksessa (verkkosisällön tai Power BI -mobiilisovellusten kautta) olevan käyttäjän käyttäjätiedoilla. Näin ollen jokainen käyttäjä näkee juuri ne tiedot, joihin hänellä on käyttöoikeudet pohjana olevassa tietolähteessä. 

Voit myös määrittää Power BI -palvelussa päivitettäväksi määritetyn raportin käyttämään kertakirjautumista. Kun määrität kertakirjautumisen tälle tietolähteelle, kyselyt suoritetaan tietojoukon omistajan Power BI:n käyttäjätiedoilla. Tämän vuoksi päivitys tapahtuu tietojoukon omistajan oikeuksien perusteella pohjana olevassa tietolähteessä. Päivittäminen SSO:n avulla on tällä hetkellä käytössä vain tietolähteille, jotka käyttävät [rajoitettua Kerberos-delegointia](service-gateway-sso-kerberos.md) 

## <a name="query-steps-when-running-sso"></a>Kyselyn vaiheet suoritettaessa kertakirjautumista

SSO:n avulla suoritettavassa kyselyssä on kolme vaihetta, kuten seuraava kaavio osoittaa.

![Kertakirjautumiskyselyn vaiheet](media/service-gateway-sso-overview/sso-query-steps.png)

Seuraavassa on lisätietoja kustakin vaiheesta:

1. Jokaisessa kyselyssä Power BI -palvelu sisältää *käyttäjän täydellisen käyttäjätunnuksen (UPN)* eli Power BI -palveluun kirjautuneena olevan käyttäjän täydellisen käyttäjänimen, kun kyselypyyntö lähetetään määritettyyn yhdyskäytävään.

2. Yhdyskäytävän on yhdistettävä Azure Active Directoryn täydellinen käyttäjätunnus paikallisen Active Directoryn käyttäjätietoihin:

   a. Jos Azure AD DirSync (eli *Azure AD Connect*) on määritetty, yhdistäminen toimii automaattisesti yhdyskäytävässä.

   b.  Muussa tapauksessa yhdyskäytävä voi etsiä Azure AD:n täydellisen käyttäjätunnuksen ja yhdistää sen paikalliseen AD-käyttäjään tekemällä haun paikalliselta Active Directory -toimialueelta.

3. Yhdyskäytävän palveluprosessi tekeytyy yhdistetyksi paikalliseksi käyttäjäksi, avaa yhteyden pohjana olevaan tietokantaan ja lähettää sitten kyselyn. Sinun ei tarvitse asentaa yhdyskäytävää samaan tietokoneeseen tietokannan kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun olet saanut perustiedot siitä, miten kertakirjautuminen otetaan käyttöön yhdyskäytävän kautta, voit lukea lisätietoja Kerberoksesta ja SAML:sta:

* [Kertakirjautuminen (SSO) - Kerberos](service-gateway-sso-kerberos.md)
* [Kertakirjautuminen (SSO) - SAML](service-gateway-sso-saml.md)
