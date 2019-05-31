---
title: Luotettu kolmannen osapuolen liittimien Power BI
description: Miten voit luottaa allekirjoitettu kolmannen osapuolen liittimen Power BI-
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 30b7457c6149320c43f24b967a842382821b01b1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607784"
---
# <a name="trusting-third-party-connectors"></a>Luottaminen kolmannen osapuolen liittimet

## <a name="why-do-you-need-trusted-third-party-connectors"></a>Miksi tarvitset luotettua kolmannen osapuolen liittimiä?

Power BI yleensä suositeltavaa pitäminen 'tietojen laajennuksen suojauksen' tason, ylemmän tason, joka estää lataamista ei niille Microsoftin sertifioinnin koodi. Saatat kuitenkin monissa tapauksissa, johon haluat ladata erityiset liittimet – olet kirjoittanut ne tai konsultti tai Microsoft certification-polku ulkopuolella toimittajan antama ne.

Annetun liittimen developer voit kirjautua sen varmenne ja tietoja, sinun on ladattava turvallisesti ilman, että tietoturva-asetukset.

Jos haluat lisätietoja tietoturva-asetukset, voit lukea tietoja ne [tähän](https://docs.microsoft.com/power-bi/desktop-connector-extensibility).

## <a name="using-the-registry-to-trust-third-party-connectors"></a>Rekisterin avulla voit luottaa kolmannen osapuolen liittimet

Valitsit Microsoft Power BI-liittimien kolmannen osapuolen tehdään luettelo määritetyn rekisteriarvo luotat varmenteen allekirjoitus. Jos tätä allekirjoitusta vastaa varmenteen liittimeen ladattavan allekirjoitus, voi ladata sen Power BI suositeltu,' tasoa. 

The registry path is HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop. Varmista, että polku on olemassa, tai luoda sen. Valitsimme vuoksi se pääasiassa valvoo IT-käytännön sekä edellyttää paikallisen tietokoneen järjestelmänvalvojan käyttöoikeudet Muokkaa tähän sijaintiin. 

![Power BI Desktop rekisterin luotettu kolmannen osapuolen avaimia ei ole asetettu](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

Lisää uusi yllä määritettyä polkuun. Tyypin on oltava ”Moniosainen arvo” (REG_MULTI_SZ), ja se tulee kutsua ”TrustedCertificateThumbprints” 

![Power BI Desktop rekisterin merkintä luotettu kolmannen osapuolen liittimet, mutta ei ole avaimia](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

Lisää luotat varmenteiden thumbprints. Voit lisätä useita varmenteita käyttämällä ”\0” erottimena tai editorissa rekisterin juuri napsauttamalla -> Muokkaa ja sijoittaa kunkin allekirjoitus uudelle riville. Esimerkki allekirjoitus otetaan allekirjoitettua varmennetta. 

 ![Power BI Desktop rekisterin käyttämällä Luotetun kolmannen osapuolen avaimia](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

Jos olet seurannut ohjeita oikein ja on annettu oikea allekirjoitus-sovelluskehittäjä, voit nyt pitäisi turvallisesti allekirjoitettu liittyvät varmenteella trust-liittimiin.

## <a name="how-to-sign-connectors"></a>Miten sen käyttäjäksi liittimet

Jos sinulla on liitin tai on kirjauduttava kehittäjä, voit lukea tietoja siitä Power Query-kohdasta [tähän](https://docs.microsoft.com/power-query/handlingconnectorsigning).
