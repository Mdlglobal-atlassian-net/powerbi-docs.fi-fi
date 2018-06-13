---
title: Yhteyden muodostaminen Webtrendsiin Power BI:n avulla
description: Webtrends for Power BI
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
ms.openlocfilehash: 9c8772430143b974fb389eac2f2ad3e74748fd3f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815399"
---
# <a name="connect-to-webtrends-with-power-bi"></a>Yhteyden muodostaminen Webtrendsiin Power BI:n avulla
Power BI:lle suunniteltu Webtrends-sisältöpaketti sisältää lukuisia heti käyttövalmiita mittareita, kuten sivunäkymien yhteismäärän ja vierailut liikenteen lähteen mukaan. Aloita Webtrends-tietojen visualisointi Power BI:ssä muodostamalla yhteys Webtrends-tiliisi. Voit käyttää annettua raporttinäkymää ja raportteja tai mukauttaa niitä, jotta niissä korostuvat itseäsi eniten kiinnostavat tiedot.  Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys [Webtrends-sisältöpakettiin](https://app.powerbi.com/getdata/services/webtrends) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-webtrends/getdata3.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-webtrends/services.png)
3. Valitse **Webtrends** \> **Hanki**.
   
   ![](media/service-connect-to-webtrends/webtrends.png)
4. Sisältöpaketti yhdistää tiettyyn Webtrends-profiilin tunnukseen. Lisätietoja [tämän parametrin etsimisestä](#FindingParams) on alla.
   
   ![](media/service-connect-to-webtrends/parameters.png)
5. Muodosta yhteys antamalla Webtrends-tunnistetietosi. Huomaa, että käyttäjänimi-kenttään on kirjoitettava sekä tilisi että käyttäjänimesi. Katso [tiedot](#FindingParams) alla.
   
   ![](media/service-connect-to-webtrends/creds.png)
6. Hyväksymisen jälkeen tuontiprosessi alkaa automaattisesti. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
   ![](media/service-connect-to-webtrends/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md)
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä välittömästi **Päivitä nyt** -toiminnolla

## <a name="whats-included"></a>Paketin sisältö
<a name="Included"></a>

Webtrends-sisältöpaketti hakee tietoja seuraavista raporteista:  

| Raportin nimi | Raporttitunnus |
| --- | --- |
| Avainmittarit | |
| Sivustojen sisäiset haut |34awBVEP0P6 |
| Sivuilta poistumiset |7FshY8eP0P6 |
| Seuraavat sivut |CTd5rpeP0P6 |
| Edelliset sivut |aSdOeaUgnP6 |
| Sivuston sivut |oOEWQj3sUo6 |
| Sivustojen mainosten napsautukset |41df19b6d9f |
| Kaupungit |aUuHskcP0P6 |
| Maat |JHWXJNcP0P6 |
| Vierailijat |xPcmTDDP0P6 |
| Vierailun kesto |U5KAyqdP0P6 |
| Hakulausekkeet |IKYEDxIP0P6 |
| Liikenteen lähteet |JmttAoIP0P6 |
| Hakukoneet |yGz3gAGP0P6 |
| Sivuille saapumiset |i6LrkNVRUo6 |

>[!NOTE]
>SharePoint-profiilien mittajärjestelmään perustuvat järjestelmän nimet voivat poiketa hieman Webtrends-käyttöliittymässä näytetyistä. Seuraavien liitosten avulla SharePoint- ja Web-profiilien yhtenäisyys säilytetään:   

    - Istunnot = Vierailut  
    - Uudet käyttäjät = Uudet vierailijat  
    - Katselukertoja istuntoa kohden = Sivun katselukertoja vierailua kohden  
    - Päivittäinen käyttäjän kesto keskimäärin = Keskimääräinen sivustolla vietetty aika vierailijaa kohden  

## <a name="system-requirements"></a>Järjestelmävaatimukset
Sisältöpaketti edellyttää pääsyä Webtrends-profiiliin, jossa on käytössä [oikea raporttien joukko](#Included).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien löytäminen
Webtrends-profiilitunnuksesi löytyy URL-osoitteesta, kun olet valinnut profiilin:

![](media/service-connect-to-webtrends/webtrendsparameters.png)

Tunnistetiedot ovat samat kuin Webtrendsiin kirjautuessasi, mutta tilisi ja käyttäjänimesi on oltava samalla rivillä kenoviivalla erotettuna:

![](media/service-connect-to-webtrends/webtrendscreds.png)

## <a name="troubleshooting"></a>Vianmääritys
Sisältöpakettia ladattaessa saattaa tapahtua virhe tunnistetietojen antamisen jälkeen. Jos näet ”Hups”-viestin ladattaessa, katso alla olevat vianmääritysehdotukset. Jos ongelmat jatkuvat, lähetä tukipyyntö osoitteessa https://support.powerbi.com

1. Jos oikea profiilitunnus on käytössä, katso lisätiedot [Parametrien etsiminen](#FindingParams) -ohjeartikkelista.
2. Käyttäjällä on käyttöoikeudet [Sisältö](#Included)-osion raportteihin

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)
