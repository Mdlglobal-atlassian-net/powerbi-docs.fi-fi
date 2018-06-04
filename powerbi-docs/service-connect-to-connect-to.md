---
title: comScore Digital Analytixiin yhdistäminen Power BI:n avulla
description: comScore Digital Analytix Power BI:lle
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: c7e476cb9e5a210ce2d37691c44ed05dd9f3c256
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815249"
---
# <a name="connect-to-comscore-digital-analytix-with-power-bi"></a>comScore Digital Analytixiin yhdistäminen Power BI:n avulla
Visualisoi ja tutki comScore Digital Analytixiin -tietoja Power BI:ssä Power BI -sisältöpaketin avulla. Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys [Power BI:n comScore-sisältöpakettiin.](https://app.powerbi.com/getdata/services/comscore)

>[!NOTE]
>Jotta voit muodostaa yhteyden sisältöpakettiin, tarvitset comScore DAx -käyttäjätilin ja comScore-ohjelmointirajapinnan käyttöoikeuden. Alla on [lisätietoja](#Requirements).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa Nouda tiedot.
   
   ![](media/service-connect-to-connect-to/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-connect-to/services.png)
3. Valitse **comScore Digital Analytix** \> **Nouda**.
   
   ![](media/service-connect-to-connect-to/comscore.png)
4. Anna tietokeskus, comScore-asiakastunnus ja sivusto, johon haluat muodostaa yhteyden. Lisätietoja siitä, miten löydät nämä arvot, on osiossa [comScore-parametrien löytäminen](#FindingParams) alla.
   
   ![](media/service-connect-to-connect-to/parameters.png)
5. Muodosta yhteys antamalla comScore käyttäjänimesi ja -salasanasi. Lisätietoja arvon löytämisestä on alla.
   
   ![](media/service-connect-to-connect-to/creds.png)
6. Tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta raporttinäkymän ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajoitettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Järjestelmävaatimukset
Yhteyden muodostamiseen tarvitaan comScore DAx -käyttäjätili ja comScore DAx -ohjelmointirajapinnan käyttöoikeus. Ota yhteyttä comScore DAx -järjestelmänvalvojaan tilisi vahvistamiseksi.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Löydät kunkin comScore-parametrin alla olevien ohjeiden mukaisesti.

**Tietokeskus**

URL-osoite, johon siirryt comScoressa, määrittää tietokeskuksen, johon muodostat yhteyden.

Jos käytät osoitetta https://dax.comscore.com, kirjoita ”US”, ja jos käytät osoitetta https://dax.comscore.eu, kirjoita ”EU”.

![](media/service-connect-to-connect-to/comscore_url.png) 

**Asiakas**

Asiakas on sama, jota käytät kirjautuessasi comScore DAxiin.

![](media/service-connect-to-connect-to/comscore_signin.png) 

**Sivusto**

comScore-sivusto määrittää, mistä sivustosta haluat nähdä tiedot. Voit etsiä sivustoluettelon comScore-tililtäsi.

![](media/service-connect-to-connect-to/comscore_sites.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)
