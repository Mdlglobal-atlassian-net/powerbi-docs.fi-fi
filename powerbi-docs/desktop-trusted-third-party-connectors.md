---
title: Luotetut kolmansien osapuolten liittimet Power BI:ssä
description: Luottaminen allekirjoitettuihin kolmansien osapuolten liittimiin Power BI:ssä
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: ac3f795d6a80d5f143daf68436f41f5771b3c2bb
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "73876174"
---
# <a name="trusting-third-party-connectors"></a>Kolmansien osapuolten liittimiin luottaminen

## <a name="why-do-you-need-trusted-third-party-connectors"></a>Miksi luotettuja kolmansien osapuolten liittimiä tarvitaan?

Suosittelemme, että tietolaajennuksen suojaustaso pidetään Power BI:ssä yleensä korkeana. Siten estetään estää sellaisen koodin lataaminen, jota Microsoft ei ole sertifioinut. Voi kuitenkin olla useita tapauksia, joissa haluat ladata tietyt liittimet, jotka olet itse kirjoittanut tai saanut Microsoftin sertifiointipolun ulkopuoliselta konsultilta tai toimittajalta.

Tietyn liittimen kehittäjä voi allekirjoittaa sen varmenteella ja antaa sinulle tiedot, joita tarvitset sen turvalliseen lataamiseen heikentämättä suojausasetuksiasi.

Jos haluat lisätietoja suojausasetuksista, voit lukea niistä [täällä](https://docs.microsoft.com/power-bi/desktop-connector-extensibility).

## <a name="using-the-registry-to-trust-third-party-connectors"></a>Rekisterin käyttäminen kolmannen osapuolen liittimien luotettuudessa

Kolmansien osapuolten liittimien luotettuus määritetään Power BI:ssä mainitsemalla määritetyssä rekisteriarvossa sen varmenteen allekirjoitus, johon haluat luottaa. Jos tämä allekirjoitus vastaa varmenteen allekirjoitusta siinä liittimessä, jonka haluat ladata, voit ladata sen Power BI:n Suositeltu-suojaustasossa. 

Rekisteripolku on HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop. Varmista, että polku on olemassa, tai luo se. Valitsimme tämän sijainnin, koska sitä hallitaan ensisijaisesti IT-käytännön avulla ja koska sen muokkaaminen edellyttää paikallisen tietokoneen järjestelmänvalvojan oikeuksia. 

![Power BI Desktopin rekisteri, kun luotettujen kolmansien osapuolten avaimia ei ole määritetty](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

Lisää uusi arvo edellä määritettyyn polkuun. Tyypin on oltava moniosainen arvo (REG_MULTI_SZ), ja sen nimen tule olla TrustedCertificateThumbprints 

![Power BI Desktop rekisteri, joka sisältää merkinnän luotettavia kolmansien osapuolten liittimiä varten, mutta ei avaimia](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

Lisää niiden varmenteiden allekirjoitus, joihin haluat luottaa. Voit lisätä useita varmenteita käyttämällä erotinmerkkiä \0 tai napsauttamalla rekisterieditorissa hiirenkakkospainikkeella -> muokkaamalla jokaista allekirjoitusta ja sijoittamalla jokaisen niistä uudelle riville. Esimerkkiallekirjoitus on peräisin itse allekirjoitetusta varmenteesta. 

 ![Power BI Desktopin rekisteri, kun luotetun kolmannen osapuolen avain on määritetty](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

Jos olet noudattanut ohjeita oikein ja olet saanut kehittäjältä asianmukaisen allekirjoituksen, sinun pitäisi nyt pystyä luottamaan turvallisesti liittimiin, jotka on allekirjoitettu liittyvällä varmenteella.

## <a name="how-to-sign-connectors"></a>Liittimien allekirjoittaminen

Jos sinulla on liitin, joka sinun tai kehittäjän on allekirjoitettava, voit lukea siitä Power Query -asiakirjoista [täällä](https://docs.microsoft.com/power-query/handlingconnectorsigning).
