---
title: Liittimen laajennettavuus Power BI:ssä
description: Liittimen laajennettavuusmahdollisuudet, ominaisuudet, tietoturva-asetukset ja sertifioidut liittimet
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2020
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: b604ade56335e65b25501eb9fe3d3c2fd185a6f0
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83293509"
---
# <a name="connector-extensibility-in-power-bi"></a>Liittimen laajennettavuus Power BI:ssä

Power BI voi muodostaa yhteyden tietoihin olemassa olevilla liittimillä ja yleisillä tietolähteillä (esimerkiksi ODBC, OData, OLE DB, verkko, CSV, XML, ja JSON). Kehittäjät voivat myös ottaa käyttöön uusia tietolähteitä mukautetuilla tietolaajennuksilla joita kutsutaan *mukautetuiksi liittimiksi*. Microsoft on sertifioinut jotkin mukautetut liittimet, joita se jakelee *sertifioituina liittiminä*.

Jos käytät itse kehittämiäsi tai jonkin ulkoisen tahon kehittämiä sertifioimattomia mukautettuja liittimiä, sinun täytyy muokata Power BI Desktopin suojausasetuksia sallimaan laajennusten lataaminen ilman vahvistusta tai varoitusta. Koska tämä koodi voi käsitellä tunnistetietoja (esimerkiksi lähettää niitä HTTP-yhteydellä) ja ohittaa tietosuojatasot, käytä tätä suojausasetusta vain, jos luotat ehdottomasti mukautettuihin liittimiisi.

Toinen vaihtoehto on se, että tietyn liittimen kehittäjä allekirjoittaa sen varmenteella ja antaa sinulle tiedot, joita tarvitset sen käyttöön muokkaamatta suojausasetuksiasi. Saat lisätietoja ohjeartikkelista [Tietoja luotetuista ulkopuolisista liittimistä](desktop-trusted-third-party-connectors.md).

## <a name="custom-connectors"></a>Mukautetut liittimet

Sertifioimattomat mukautetut liittimet voivat olla esimerkiksi liiketoiminnallesi tärkeitä pieniä ohjelmointirajapintoja tai laajoja toimialakohtaisia palveluita, joille Microsoft ei julkaissut liitintä. Monet liittimet ovat toimittajien jakelemia. Jos tarvitset tietyn tietoliittimen, ota yhteyttä toimittajaan. 

Jos haluat käyttää sertifioimatonta mukautettua liitintä, siirrä liittimen *.pq*-, *.pqx-* , *.m*- tai *.mez*-tiedosto kansioon *\[Tiedostot]\\Power BI Desktop\\Custom Connectors*. Jos tätä kansiota ei ole olemassa, luo se.

Muokkaa tietolaajennuksen suojausasetuksia seuraavasti:

Valitse Power BI Desktopissa **Tiedosto** > **Asetukset ja vaihtoehdot** > **Asetukset** > **Suojaus**.

Valitse **Tietolaajennukset**-kohdata **(Ei suositeltu) Salli minkä tahansa laajennuksen lataaminen ilman vahvistusta tai varoitusta**. Valitse **OK** ja käynnistä siten Power BI Desktop uudelleen. 

![Sertifioimattomien mukautettujen liittimien salliminen tietolaajennuksen tietoturva-asetuksissa](media/desktop-connector-extensibility/data-extension-security-1.png)

Power BI Desktopin tietolaajennusten suojausasetuksen oletusarvo on **(Suositus) Salli vain Microsoftin sertifioimien ja muiden luotettujen kolmannen osapuolen laajennusten lataaminen**. Jos tämä asetus on käytössä ja järjestelmässäsi on sertifioimattomia mukautettuja liittimiä, Power BI Desktopin käynnistyessä näytetään **sertifioimattomien liittimien** valintaikkuna. Siinä luetellaan liittimet, joita ei voida ladata turvallisesti.

![Sertifioimattomien liittimien valintaikkuna](media/desktop-connector-extensibility/data-extension-security-2.png)

Jos haluat korjata virheen, muokkaa **tietolaajennusten** suojausasetusta tai poista allekirjoittamattomat liittimet *mukautettujen liittimien* kansiosta.

## <a name="certified-connectors"></a>Sertifioidut liittimet

Rajoitettua tietolaajennusten joukkoa pidetään *sertifioituna*. Vaikka Microsoft toimii liittimien jakelijana, se ei vastaa niiden suorituskyvystä tai jatkuvasta toimivuudesta. Liittimen luonut ulkopuolinen kehittäjä on kuitenkin vastuussa liittimen ylläpidosta ja tuesta. 

Sertifioidut ulkopuoliset liittimet näytetään Power BI Desktopissa **Nouda tiedot** -valintaikkunan luettelossa yleisten liittimien kanssa. Sinun ei tarvitse säätää tietoturva-asetuksia käyttääksesi sertifioituja liittimiä.

Jos haluat hankkia mukautetulle liittimelle sertifioinnin, pyydä toimittajaasi ottamaan yhteyttä seuraavaan: dataconnectors@microsoft.com.
