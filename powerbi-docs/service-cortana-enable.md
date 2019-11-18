---
title: Aktivoi Cortana Power BI:lle
description: Käytä Cortanaa Power BI:n kanssa saadaksesi vastauksia tiedoistasi. Aktivoi Cortana kullekin Power BI -tietojoukolle ja ota sitten Cortana käyttöön päästäksesi käsiksi tietojoukkoihisi Windows-laitteilta.
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: a631bc37c193521b2acc367a0c6d8540419e3b79
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73872901"
---
# <a name="enable-cortana-to-access-power-bi-reports-and-their-underlying-datasets"></a>Mahdollista Cortanalle Power BI-raporttien (ja niiden taustalla olevien tietojoukkojen) käyttö
Olet lukenut sivun [Perehdytys Cortanaan ja Power BI:hin](service-cortana-intro.md) (jos et ole, kannattaa se lukea ensin ja palata sitten takaisin). Ja nyt haluat kokeilla sitä itse.  Muutamien vaatimusten on täytyttävä ennen kuin voit esittää luonnollisella ohjelmointikielellä kysymyksiä Cortanassa ja etsiä vastauksia Power BI ***raportit*** -osioon tallennetuista tiedoista. Tarkemmin sanottuna sinun pitää toimia seuraavasti.

> [!IMPORTANT]
> Cortanan integrointi on vanhentumassa Power BI:ssä. 11. kesäkuuta alkaen Cortana ei enää toimi koontinäyttöjen ja raporttien kanssa.

Power BI -palvelussa

* salli yksi tai useampi tietojoukko Cortanalle (raportit ovat tietojoukkojen päällä, joten Cortana tarvitsee pääsyn kyseisiin tietojoukkoihin)

Microsoft Windowsissa

* Tarkista, että käytössäsi on Windows 10:n versio 1511 tai sitä uudempi versio
* Varmista, että Power BI ja Windows ovat yhteydessä toisiinsa. Tämä tarkoittaa, että liität tilisi Windowsiin.

## <a name="use-power-bi-service-to-enable-cortana-to-access-report-pages-in-power-bi"></a>Käytä Power BI -palvelua mahdollistaaksesi Cortanan pääsyn Power BI:ssä oleviin raporttisivuihin
Power BI:sä olevien raporttien antaminen Cortanan käytettäväksi on yksinkertainen prosessi.  Itse asiassa sinun tarvitsee vain ottaa raportin pohjana oleva tietojoukko käyttöön valitsemalla ”salli Cortanan käyttää tätä tietojoukkoa”. Tämän jälkeen Windows 10:n käyttäjät voivat saada vastauksia Cortanassa olevasta raportista, mikäli heillä on pääsy Power BI:ssä olevaan tietojoukkoon joko tavallisen Power BI -jakamisen, sovellusten tai sisältöpaketin kautta.

Sinun tulee kirjautua sisään Power BI -palveluun (ei Power BI Desktopiin) ja toistaa nämä vaiheet jokaisen tietojoukon kohdalla, jota haluat Cortanan käyttävän.

1. Määritä, mitkä tietojoukot sallitaan käytettäväksi. Valitse sisältöluettelosta raportti, jota haluat Cortanan voivan käyttää ja valitse **näytä aiheeseen liittyvä** kuvake ![](media/service-cortana-enable/power-bi-cortana-view-related-icon.png) .
   
    ![Tarkastele aiheeseen liittyvää sisältöä](media/service-cortana-enable/power-bi-view-related.png)
2. Tähän raporttiin liittyvä tietojoukko on **Contoso Sales**.
   
    ![Contoso Sales -tietojoukko](media/service-cortana-enable/power-bi-identify-dataset.png)
3. Tietojoukon nimen oikealla puolella, valitse **Enemmän vaihtoehtoja** (...) > Asetukset**.  
   
    ![Valitse asetukset](media/service-cortana-enable/power-bi-settings-cortana.png)
4. Valitse **Q&A ja Cortana** > **salli Cortanan käyttää tätä tietojoukkoa** > **käytä**.
   
   ![Cortana käyttötietojoukko](media/service-cortana-enable/power-bi-cortana-enable-new.png)
   
   Tässä esimerkissä mahdollistamme Cortanan käytön Contoso Sales -tietojoukkojen kanssa.
   
   > [!NOTE]
   > Tulokset alkavat ilmestyä 30 minuutin sisällä, uuden tietojoukon tai Cortanan vastauskortin lisäämisestä Power BI:hin ja sen käytön sallimisesta Cortanalle. Sisään- ja uloskirjautuminen Windows 10:en tai Cortanan uudelleenkäynnistäminen Windows 10:ssä sallii heti uuden sisällön ilmestymisen.
   > 
   > Jos sallit tietojoukon käytön Cortanalle, ja kyseinen tietojoukko on osa omistamaasi sisältöpakettia tai sovellusta, täytyy sinun julkaista uudelleen, jotta myös työtoverisi voisivat käyttää kyseistä tietojoukkoa Cortanan kanssa.
   > 
   > 

## <a name="add-your-power-bi-credentials-to-windows"></a>Lisää Power BI -tunnistetietosi Windowsiin
Käytössäsi olevan Windows 10:n version on oltava 1511 tai sitä uudempi.

1. Selvitä, mikä Windows 10:n versio sinulla on käytössä. Avaa **asetukset**.
    ![Avaa Windowsin asetukset](media/service-cortana-enable/power-bi-cortana-windows.png)

    Sen jälkeen valitse **järjestelmä > tietoja**. Näytön alareunassa näet **Windowsin määritykset > versio**

   * Jos sinulla on käytössäsi Windows 10:n versio väliltä 1511 (Windows 10, marraskuu 2015 päivitys) ja 1607, lisää työ- tai koulutilisi sekä Microsoft-tilisi (suorittamalla alla olevat vaiheet 2 ja 3).
   * Jos käytössäsi oleva Windows 10:n versio on 1607 (Windows 10, heinäkuu 2016 päivitys) tai sitä uudempi, lisää työ- tai koulutilisi (suorittamalla ainoastaan alla oleva vaihe 2).
1. Lisää työ- tai koulutilisi Cortanaan.
   
   * Avaa **asetukset** > **tilit**.
     
       ![Asetukset – tilit](media/service-cortana-enable/power-bi-windows-accounts.png)
   * Vieritä alas ja valitse **lisää työ- tai koulutili**. Tai, valitse **Tilit**-sivulta **Käytä työ- tai koulutiliä > Yhdistä**.
     
     ![Työtilin lisääminen](media/service-cortana-enable/power-bi-add-work-account2.png)

Cortana käyttää tätä työ- tai koulutiliä, tarkistaakseen Power BI:stä mahdolliset vastaukset Cortanassa esittämiisi kysymyksiin.

## <a name="next-steps"></a>Seuraavat vaiheet
[Luo Cortana *Vastauskortit* Power BI:ssä](service-cortana-answer-cards.md)

[Cortanan ja Power BI:n integrointiin liittyvien ongelmien vianmääritys](service-cortana-troubleshoot.md)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

