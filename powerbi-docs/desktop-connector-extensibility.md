---
title: Liittimen laajennettavuus Power BI:ssä
description: Liittimen laajennettavuusmahdollisuudet, ominaisuudet, tietoturva-asetukset ja sertifioidut liittimet
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/25/2018
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: c63357df043ff6a646562d398a07d8042dd5a0ee
ms.sourcegitcommit: 7fb0b68203877ff01f29724f0d1761d023075445
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/26/2018
ms.locfileid: "39256547"
---
# <a name="connector-extensibility-in-power-bi"></a>Liittimen laajennettavuus Power BI:ssä

Asiakkaat ja kehittäjät voivat Power BI:ssä laajentaa monella tapaa niitä tietolähteitä, joihin he voivat muodostaa yhteyden, kuten olemassa olevilla yhdistimillä ja yleisillä tietolähteillä (kuten ODBC OData Oledb, WWW, CSV, XML, JSON). Kyseisten tietolähteiden lisäksi kehittäjät voivat luoda tietolaajennuksia, joita kutsutaan **mukautetuiksi liittimiksi** ja sertifioida liittimen **sertifioiduksi liittimeksi**.

Power BI:n aiemmissa versioissa **mukautettujen liittimien** käyttö mahdollistettiin ominaisuusvalitsimen avulla. Nyt siitä löytyy valikko, jonka avulla voit turvallisesti hallita haluamaasi mukautetun koodin tason, jonka haluat sallia järjestelmän suorittamiseen: voit sallia kaikki mukautetut liittimet tai vain Microsoftin sertifioimat ja levittämät liittimiä**Nouda tiedot** -valintaikkunasta.

## <a name="custom-connectors"></a>Mukautetut liittimet

**Mukautetut liittimet** sisältävät laajan valikoiman liiketoiminnallesi tärkeistä pienistä ohjelmointirajapinnoista, laajoihin, muun kuin Microsoftin tarjoamiin, toimialakohtaisiin palveluihin. Useimmat tällaiset liittimet jaetaan itse toimittajan puolesta joten jos sinulla on tarve tietylle liittimelle, ota yhteyttä toimittajaan.

Käyttääksesi **mukautettuja liittimiä** laita ne  *\[asiakirjojen]\\Power BI Desktopin\\mukautetut liittimet* -kansioon ja muuta sen suojausasetuksia seuraavassa osassa kuvatulla tavalla.

Sinun ei tarvitse säätää tietoturva-asetuksia käyttääksesi **sertifioituja liittimiä**.

## <a name="data-extension-security"></a>Tietolaajennuksen tietoturva

Muuttaaksesi tietolaajennuksen tietoturva-asetuksia **Power BI Desktopissa** valitse **Tiedosto > Asetukset ja vaihtoehdot > Asetukset > Tietoturva**.

![Voi valita haluatko pystyä lataamaan mukautettuja yhdistimiä tietolaajennuksen tietoturva-asetuksista](media/desktop-connector-extensibility/data-extension-security-1.png)

**Tietolaajennukset**-valikosta voit valita kahdesta suojaustasosta:

* (Suositeltu) Salli vain sertifioitujen laajennusten lataaminen
* (Ei suositeltu) Salli minkä tahansa laajennuksen lataaminen ilman varoitusta

Jos aiot käyttää **mukautettuja liittimiä** tai itse tai kolmannen osapuolen kehittämiä ja jakamia liittimiä, sinun täytyy valita **(ei suositeltu) Salli minkä tahansa laajennuksen lataaminen ilman varoitusta** -vaihtoehto. Microsoft ei suosittele tätä tietoturva-asetusta, ellei aiot käyttää **mukautettuja liittimiä**.

**(Suositeltu)**-tietoturva-asetus näyttää virheen, jossa kuvataan liittimet, joita ei voitu ladata tietoturva vuoksi, jos järjestelmässä havaitaan mukautettuja liittimiä.

![Valintaikkunassa on kuvattu mukautetut liittimet, joita ei voi ladata tietoturva-asetuksien, tässä tapauksessa TripPinin, vuoksi](media/desktop-connector-extensibility/data-extension-security-2.png)

Ratkaistaksesi tämän ongelman ja käyttääksesi näitä liittimet sinun on muutettava tietoturva-asetukseksi **(ei suositelluksi)** aiemmin kuvattujen ohjeiden mukaisesti ja käynnistettävä **Power BI Desktop** uudelleen.

## <a name="certified-connectors"></a>Sertifioidut liittimet

Rajoitettua alijoukkoa tietolaajennuksia pidetään **sertifioituina** ja kyseiset sertifioidut liittimet ovat saatavilla **Nouda tiedot** -valintaikkunasta, mutta niiden ylläpidosta ja tuesta vastaa silti liittimen kehittänyt kolmas osapuoli. Vaikka Microsoft toimii näiden levittäjänä, se ei vastaa niiden suorituskyvystä tai jatkuvasta toimivuudesta.

Jos haluat hyväksyttää mukautetun liittimen, pyydä toimittajaasi ottamaan yhteyttä Microsoftiin.
