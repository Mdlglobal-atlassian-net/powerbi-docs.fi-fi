---
title: Liittimen laajennettavuus Power BI:ssä
description: Liittimen laajennettavuusmahdollisuudet, ominaisuudet, tietoturva-asetukset ja sertifioidut liittimet
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: e493e4a41e7b357a23677c1c50f654dbee51e0ca
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878414"
---
# <a name="connector-extensibility-in-power-bi"></a>Liittimen laajennettavuus Power BI:ssä

Power BI:ssä asiakkaat ja kehittäjät voivat laajentaa yhdistettävien tietolähteiden määrää monin eri tavoin. He käyttävät olemassa olevia liittimiä ja yleisiä tietolähteitä (kuten ODBC, OData, Oledb, Web, CSV, XML, JSON). Kehittäjät voivat myös luoda tietolaajennuksia, joita kutsutaan **mukautetuiksi liittimiksi**, ja tehdä niistä **sertifioituja liittimiä**.

Tällä hetkellä **mukautetut liittimet** otetaan käyttöön valikossa, jonka avulla voit suojatusti hallita järjestelmässä suoritettavan mukautetun koodin tasoa. Voit valita kaikki mukautetut liittimet tai vain Microsoftin sertifioimat ja jakelemat liittimet **Nouda tiedot** -valintaikkunassa.

## <a name="custom-connectors"></a>Mukautetut liittimet

**Mukautetut liittimet** voivat sisältää runsaasti mahdollisuuksia – liiketoiminnallesi tärkeistä pienistä ohjelmointirajapinnoista laajoihin toimialakohtaisiin palveluihin, joiden tarjoaja on jokin muu taho kuin Microsoft. Toimittaja jakelee useita liittimiä. Jos tarvitset tietyn tietoliittimen, ota yhteyttä toimittajaan.

Käyttääksesi **mukautettua liitintä** laita se  *\[asiakirjojen]\\Power BI Desktopin\\mukautetut liittimet* -kansioon ja muuta sen suojausasetuksia seuraavassa osassa kuvatulla tavalla.

Sinun ei tarvitse säätää tietoturva-asetuksia käyttääksesi **sertifioituja liittimiä**.

## <a name="data-extension-security"></a>Tietolaajennuksen tietoturva

Muuttaaksesi tietolaajennuksen tietoturva-asetuksia **Power BI Desktopissa** valitse **Tiedosto > Asetukset ja vaihtoehdot > Asetukset > Tietoturva**.

![Voi valita haluatko ladata mukautettuja yhdistimiä tietolaajennuksen tietoturva-asetuksista](media/desktop-connector-extensibility/data-extension-security-1.png)

**Tietolaajennukset**-valikosta voit valita kahdesta suojaustasosta:

* (Suositeltu) Salli vain sertifioitujen laajennusten lataaminen
* (Ei suositeltu) Salli minkä tahansa laajennuksen lataaminen ilman varoitusta

Jos aiot käyttää **mukautettuja liittimiä** tai itse kehittämiäsi tai kolmannen osapuolen kehittämiä liittimiä, sinun on valittava **(Ei suositeltu) Salli minkä tahansa laajennuksen lataaminen ilman varoitusta** -vaihtoehto. Microsoft ei suosittele tätä tietoturva-asetusta, ellet luota mukautettuihin liittimiisi täysin. Tämä on siksi, koska koodin avulla voidaan käsitellä tunnistetietoja, kuten lähettää niitä HTTP-yhteyden välityksellä, ja ohittaa yksityisyystasot.

Jos käytössä on **(Suositeltu)** -tietoturva-asetus ja järjestelmässäsi on mukautettuja liittimiä, näyttöön tulee virhe ”Seuraavaa liitintä ei ole sertifioitu, emmekä pystyneet varmistamaan, että sen käyttäminen on turvallista” ja sitten luettelo liittimistä, joita ei voi ladata turvallisesti.

![Valintaikkunassa on kuvattu mukautetut liittimet, joita ei voi ladata tietoturva-asetuksien, tässä tapauksessa TripPinin, vuoksi](media/desktop-connector-extensibility/data-extension-security-2.png)

Jos haluat korjata virheen muuttamatta suojausta, poista allekirjoittamattomat liittimet mukautettujen liittimien kansiosta.

Jos haluat korjata virheen ja käyttää kyseisiä liittimiä, sinun on muutettava tietoturva-asetukseksi **(Ei suositeltu) Salli minkä tahansa laajennuksen lataaminen ilman varoitusta** edellä kuvatulla tavalla. Käynnistä siten **Power BI Desktop** uudelleen.

## <a name="certified-connectors"></a>Sertifioidut liittimet

Rajoitettua tietolaajennusten joukkoa pidetään **sertifioituna**. Käytä sertifioituja liittimiä **Nouda tiedot** -valintaikkunassa. Liittimen luonut kolmannen osapuolen kehittäjä on kuitenkin vastuussa liittimen ylläpidosta ja tuesta. Vaikka Microsoft toimii liittimien jakelijana, se ei vastaa niiden suorituskyvystä tai jatkuvasta toimivuudesta.

Jos haluat hankkia mukautetulle liittimelle sertifioinnin, pyydä toimittajaasi ottamaan yhteyttä osoitteeseen dataconnectors@microsoft.com.
