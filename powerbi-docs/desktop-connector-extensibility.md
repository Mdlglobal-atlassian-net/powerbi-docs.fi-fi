---
title: Liittimen laajennettavuus Power BI:ssä
description: Liittimen laajennettavuusmahdollisuudet, ominaisuudet, tietoturva-asetukset ja sertifioidut liittimet
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 16b96d91a9dd37fa8a502bbcca772438c703cb63
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412987"
---
# <a name="connector-extensibility-in-power-bi"></a>Liittimen laajennettavuus Power BI:ssä

Power BI-asiakkaille ja kehittäjille laajentaa tietolähteet, joihin ne yhteyden monella tavalla. Hän käyttää olemassa oleviin yhdistimiin ja yleisiä tietoja lähteistä (kuten ODBC OData Oledb, WWW, CSV, XML, JSON). Kehittäjien luoda tietolaajennukset, jota kutsutaan **mukautetut liittimet**, ja ne **sertifioidut liittimet**.

Tällä hetkellä otat **mukautettujen liittimien** valikon, jonka avulla voit turvallisesti käyttöoikeustason haluat antaa suorittaa järjestelmän mukautettua koodia. Voit valita kaikki mukautetut liittimet tai vain sertifioitu ja Microsoftin liittimiä **Nouda tiedot** vuoropuhelua.

## <a name="custom-connectors"></a>Mukautetut liittimet

**Mukautettujen liittimien** voi sisältää useita erilaisia mahdollisuuksia, väliltä pieni ohjelmointirajapintoja tärkeitä liiketoiminnan suuri alakohtaisten palveluihin, joita Microsoft ei ole julkaistu liitin. Monia liittimiä jakelee toimittajan. Jos sinulla on tietyn liittimen tarpeen, ota yhteyttä toimittaja.

Käyttää **mukautetun yhdistimen**, lisätä  *\[asiakirjojen]\\Power BI Desktop\\mukautetut liittimet* -kansioon, ja muuttaa sen suojausasetuksia kuvatulla tavalla Seuraavassa osassa.

Sinun ei tarvitse säätää tietoturva-asetuksia käyttääksesi **sertifioituja liittimiä**.

## <a name="data-extension-security"></a>Tietolaajennuksen tietoturva

Muutettava tunniste suojausasetukset, **Power BI Desktop** Valitse **tiedosto > Asetukset ja vaihtoehdot > Asetukset > Suojaus**.

![Ohjausobjekti, Haluatko ladata mukautetuille yhdistimille käyttämällä laajennuksen tietosuoja-asetukset](media/desktop-connector-extensibility/data-extension-security-1.png)

**Tietolaajennukset**-valikosta voit valita kahdesta suojaustasosta:

* (Suositeltu) Salli vain sertifioitujen laajennusten lataaminen
* (Ei suositeltu) Salli minkä tahansa laajennuksen lataaminen ilman varoitusta

Jos aiot käyttää **mukautetut liittimet** tai liittimet, jotka ovat kehittäneet tai kolmannen osapuolen, sinun täytyy valita **”(Not Recommended) Salli minkä tahansa laajennuksen lataaminen ilman varoitusta”** . Microsoft ei suosittele asetusta, jos et luota täysin mukautettujen liittimien. Koska käsittelemään tunnistetietoja, kuten lähettää ne HTTP-protokollaa ja Ohita yksityisyystasot sinne koodia.

Tällä **”(suositus)”** suojauksen asetusta, jos järjestelmään on mukautetut liittimet, näyttöön tulee virhesanoma, joka kuvaa liittimet, jotka ei voi ladata suojauksen vuoksi.

![Valintaikkuna kuvataan mukautetut liittimet, joka ei voi ladata tietoturva-asetukset tämän tapauksen TripPin vuoksi](media/desktop-connector-extensibility/data-extension-security-2.png)

Ratkaista tämän ongelman ja käyttää näitä liittimet, muuta-asetukset **”(Not Recommended) Salli minkä tahansa laajennuksen lataaminen ilman varoitusta”** asetuksen aiempien ohjeiden mukaisesti. Käynnistä, **Power BI Desktop**.

## <a name="certified-connectors"></a>Sertifioidut liittimet

Tietolaajennukset rajoitettu alijoukon pidetään **sertifioitujen**. Käyttää-sertifioidut liittimet **Nouda tiedot** vuoropuhelua. Mutta kolmannen osapuolen kehittäjä, joka luodaan kytkentä on vastuussa tuki ja ylläpidosta. Kun Microsoft jakelee yhdistimet, ei ole vastuussa niiden suorituskykyä tai jatkuvan funktio.

Jos haluat hankkia mukautetulle liittimelle sertifioinnin, pyydä toimittajaasi ottamaan yhteyttä osoitteeseen dataconnectors@microsoft.com.
