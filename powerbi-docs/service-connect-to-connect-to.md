---
title: comScore Digital Analytixiin yhdistäminen Power BI:n avulla
description: comScore Digital Analytix Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: bc9a8637416bdea50e955c1aea73bbcfeed51bb6
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242997"
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
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

<a name="Requirements"></a>

## <a name="system-requirements"></a>Järjestelmävaatimukset
Yhteyden muodostamiseen tarvitaan comScore DAx -käyttäjätili ja comScore DAx -ohjelmointirajapinnan käyttöoikeus. Ota yhteyttä comScore DAx -järjestelmänvalvojaan tilisi vahvistamiseksi.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Löydät kunkin comScore-parametrin alla olevien ohjeiden mukaisesti.

**Tietokeskus**

URL-osoite, johon siirryt comScoressa, määrittää tietokeskuksen, johon muodostat yhteyden.

Jos sinulla on käytössä https://dax.comscore.com, syötä “US”, jos sinulla on käytössä https://dax.comscore.eu, syötä “EU”.

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

