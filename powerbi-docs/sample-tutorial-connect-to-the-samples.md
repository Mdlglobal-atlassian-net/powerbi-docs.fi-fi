---
title: Yhteyden muodostaminen malleihin Power BI -palvelussa
description: Opi asentamaan ja tutkimaan malleja Power BI -palvelussa.
author: maggiesMSFT
ms.reviewer: amac
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/19/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 90136f39d9f2a8e330748b56d6302bb75d2a31fe
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "73873838"
---
#  <a name="connect-to-the-samples-in-the-power-bi-service"></a>Yhteyden muodostaminen malleihin Power BI -palvelussa

Tässä opetusohjelmassa opit 
- tuomaan mallisisältöpaketin, lisäämään sen Power BI -palveluun ja avaamaan paketin sisällön. *Sisältöpaketti* on mallityyppi, jossa tietojoukko on niputettu yhteen koontinäytön ja raportin kanssa. 
- avaamaan .pbix-mallitiedoston Power BI Desktop -versiossa.

Jos haluat lisää taustatietoja, tutustu kohtaan [Mallitietojoukkoja Power BI:lle](sample-datasets.md). Artikkelin avulla opit kaiken malleista, kuten niiden hakemisesta, tallentamisesta ja käyttämisestä, ja voit tutustua joihinkin mallien kertomiin tarinoihin. 

## <a name="prerequisites"></a>Edellytykset
Mallit ovat käytettävissä Power BI -palvelun ja Power BI Desktop -version kautta. Käytämme esimerkkinä Jälleenmyyntianalyysimallia.

Tässä opetusohjelmassa käytettävän *Jälleenmyyntianalyysin* mallisisältöpaketti koostuu koontinäytöstä, raportista ja tietojoukosta.
Ennen aloittamista voit tutustua tähän kyseiseen sisältöpakettiin ja sen skenaarioon kohdassa [Jälleenmyyntianalyysimalli Power BI:lle: esittely](sample-retail-analysis.md).

## <a name="samples-in-the-power-bi-service"></a>Mallit Power BI -palvelussa

1. Avaa Power BI -palvelu (app.powerbi.com), kirjaudu sisään ja avaa työtila, johon haluat tallentaa mallin. 

    Jos sinulla ei ole Power BI Pro -käyttöoikeutta, voit tallentaa mallin omaan työtilaasi.

2. Valitse siirtymisruudun alareunasta **Nouda tiedot**. 

   ![Valitse Nouda tiedot](media/sample-datasets/power-bi-get-data.png)

   Jos et näe **Nouda tiedot** -kohtaa, laajenna siirtymisruutu valitsemalla seuraava kuvake ruudun yläosasta: ![hampurilaiskuvake](media/sample-tutorial-connect-to-the-samples/expand-nav.png).

5. Valitse avautuvalta **Nouda tiedot** -sivulta **Mallit**.
   
6. Valitse **Jälleenmyyntianalyysimalli** ja **Yhdistä**.   
   
   ![Yhdistä-painike](media/sample-tutorial-connect-to-the-samples/pbi_retailanalysissampleconnect.png)

## <a name="what-was-imported"></a>Mitä tuotiin?
Kun valitset sisältöpaketeissa **Yhdistä**, Power BI hakee kopion sisältöpaketista ja tallentaa sen sinulle pilvipalveluun. Sisältöpaketin luonut henkilö sisällytti tietojoukon, raportin ja koontinäytön, joten saat ne, kun valitset **Yhdistä**. 

1. Kun valitset **Yhdistä**, Power BI luo uuden koontinäytön ja lisää sen **Koontinäytöt**-välilehteesi. 
   
   ![Jälleenmyyntianalyysimallin syöte](media/sample-retail-analysis/retail-entry.png)
2. Avaa **Raportit**-välilehti. Tässä näet uuden raportin nimeltä *Jälleenmyyntianalyysimalli*.
   
   ![Jälleenmyyntianalyysimallin raportin merkintä](media/sample-tutorial-connect-to-the-samples/power-bi-new-report.png)
   
   Tutustu **Tietojoukot**-välilehteen, jossa on myös uusi tietojoukko.
   
   ![Jälleenmyyntianalyysimallin tietojoukon merkintä](media/sample-tutorial-connect-to-the-samples/power-bi-new-dataset.png)

## <a name="explore-your-new-content"></a>Tutustu uuteen sisältöösi
Tutustu nyt itsenäisesti koontinäyttöön, tietojoukkoon ja raporttiin. Omiin koontinäyttöihin, raportteihin ja tietojoukkoihin voi siirtyä monella tavalla. Yksi näistä tavoista on kuvattu jäljempänä.  

1. Siirry takaisin **Koontinäytöt**-välilehteen ja valitse ja avaa **Jälleenmyyntianalyysimalli**-koontinäyttö.       

   Koontinäyttö avautuu, ja siinä on useita visualisointiruutuja.   
 
1. Avaa ruudun taustalla oleva raportti valitsemalla jokin koontinäytön ruuduista. Tässä esimerkissä valitaan aluekaavio **Tämän vuoden myynti, viime vuoden myynti tilikuukauden mukaan**.  

   ![Jälleenmyyntianalyysimallin koontinäyttö, jossa visualisointi korostettuna](media/sample-tutorial-connect-to-the-samples/power-bi-dashboards2new.png)

   Raportti avautuu sivulle, joka sisältää valitsemasi aluekaavion, tässä tapauksessa raportin **Alueen kuukausimyynti** -sivu.
   
   ![Alueen kuukausimyynti -raporttisivu](media/sample-tutorial-connect-to-the-samples/power-bi-report.png)
   
   > [!NOTE]
   > Jos ruutu luotiin käyttämällä [Power BI Q&A:n](power-bi-tutorial-q-and-a.md) avulla, Q&A-sivu avautuu sen sijaan. Jos ruutu on [kiinnitetty Excelistä](service-dashboard-pin-tile-from-excel.md), Excel Online avautuu Power BI:n sisällä.
   > 
   > 
1. Jaettaessa sisältöpaketti työkaverin kanssa halutaan yleensä jakaa vain merkitykselliset tiedot eikä antaa suoraa pääsyä tietoihin. **Tietojoukot**-välilehdessä on useita vaihtoehtoja tietojoukkoon tutustumiseen. Et kuitenkaan voi tarkastella tietojesi rivejä ja sarakkeita, kuten voit tehdä Power BI Desktopissa tai Excelissä. 
   
   ![Jälleenmyyntianalyysimallin tietojoukon merkintä](media/sample-tutorial-connect-to-the-samples/power-bi-new-dataset.png)
   
1. Yksi tapa tutustua tietojoukkoon on luoda omat visualisoinnit ja raportit alusta alkaen. Valitse kaaviokuvake ![Kaaviokuvake](media/sample-tutorial-connect-to-the-samples/power-bi-chart-icon4.png) tietojoukon avaamiseksi raportin muokkaustilassa.
     
   ![Upouusi raportti](media/sample-tutorial-connect-to-the-samples/power-bi-report-editing.png)

1. Toinen tapa tutustua tietojoukkoon on suorittaa [Nopeat merkitykselliset tiedot](consumer/end-user-insights.md) -toiminto. Valitse **Enemmän vaihtoehtoja** (...) ja valitse sitten **Hae nopeat merkitykselliset tiedot**. Kun merkitykselliset tiedot ovat valmiit, valitse **Näytä merkitykselliset tiedot**.
     
    ![Merkityksellisiä tietoja -raportti](media/sample-tutorial-connect-to-the-samples/power-bi-insights.png)

## <a name="samples-in-power-bi-desktop"></a>Mallit Power BI Desktopissa 
Kun avaat .pbix-mallitiedoston Power BI Desktopissa, se avautuu Raportti-näkymään, jossa voit tutustua visualisointeja sisältäviin raporttisivuihin ja luoda tai muokata niitä. Raportti-näkymä on rakenteeltaan pääpiirteittäin sama kuin raportin muokkausnäkymä Power BI -palvelussa. Voit esimerkiksi siirtää, kopioida ja liittää sekä yhdistää visualisointeja jne. 

Power BI -palvelun raportin muokkauksesta poiketen Power BI Desktopissa voit työstää kyselyitäsi ja mallintaa tietosi, jotta ne varmasti tukevat raporttiesi parhaita merkityksellisiä tietoja. Voit sen jälkeen tallentaa Power BI Desktop -tiedoston minne tahansa, esimerkiksi paikalliselle asemalle tai pilvipalveluun.

1. Lataa [jälleenmyyntianalyysin .pbix-mallitiedosto](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) ja avaa se Power BI Desktop -versiossa. 

    ![Malli Power BI -raporttinäkymässä](media/sample-tutorial-connect-to-the-samples/power-bi-samples-desktop.png)

1. Tiedosto avautuu Raportti-näkymään. Huomaa, että raporttieditorin alaosassa on neljä välilehteä. Nämä välilehdet edustavat tämän raportin neljää sivua. Tässä esimerkissä **Uudet myymälät** -sivu on valittuna. 

    ![Uudet myymälät -välilehti korostettuna](media/sample-tutorial-connect-to-the-samples/power-bi-sample-tabs.png).

1. Tutustu raporttieditoriin tarkemmin katsomalla [raporttieditorin esittely](service-the-report-editor-take-a-tour.md).

## <a name="whats-in-your-report"></a>Mitä raportissasi on?
Kun lataat .pbix-mallitiedoston, lataat raportin lisäksi myös *pohjana olevan tietojoukon*. Kun avaat tiedoston, Power BI Desktop lataa tiedot sekä niihin liittyvät kyselyt ja suhteet. Voit tarkastella pohjana olevia tietoja ja suhteita, mutta et voi tarkastella pohjana olevia kyselyitä kyselyeditorissa.


1. Vaihda [Tiedot-näkymään](desktop-data-view.md) valitsemalla taulukkokuvake ![taulukkokuvake](media/sample-tutorial-connect-to-the-samples/power-bi-data-icon.png).
 
    ![Desktopin Tiedot-näkymä](media/sample-tutorial-connect-to-the-samples/power-bi-desktop-sample-data.png)

    Tiedot-näkymän avulla voit tarkastaa Power BI Desktop -mallin tiedot, tutustua niihin ja oppia ymmärtämään niitä. Se poikkeaa taulukoiden, sarakkeiden ja tietojen tarkastelusta kyselyeditorissa. Tietonäkymän tiedot on jo ladattu malliin.

    Kun mallinnat tietojasi, haluat ehkä nähdä, mitä taulukon riveillä tai sarakkeissa todella on ilman visualisoinnin luomista raporttipohjaan. Tämä pitää paikkansa erityisesti silloin, kun luot mittareita ja laskettuja sarakkeita tai kun sinun on tunnistettava tietotyyppi tai tietoluokka.

1. Siirry [Suhteet-näkymään](desktop-relationship-view.md) valitsemalla seuraava kuvake: ![Suhdenäkymäkuvake](media/sample-tutorial-connect-to-the-samples/power-bi-desktop-relationship-icon.png).
 
    ![Suhdenäkymä Power BI Desktopissa](media/sample-tutorial-connect-to-the-samples/power-bi-relationships.png)

    Suhteet-näkymässä näytetään mallisi kaikki taulukot, sarakkeet ja suhteet. Täällä voit tarkastella, muuttaa ja luoda suhteita.

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä ympäristössä on turvallista tehdä kokeiluja, koska voit jättää tekemäsi muutokset tallentamatta. Jos kuitenkin tallennat ne, voit aina siirtyä **Nouda tiedot** -kohtaan, jolloin saat tästä mallista uuden kopion.

Toivomme, että tämä esittely on osoittanut, miten Power BI -raporttinäkymät, tietojoukot, yhteydet ja raportit voivat tarjota uusia näkökulmia mallitietoihin. Nyt on sinun vuorosi – muodosta yhteys omiin tietoihisi. Power BI:n avulla voit yhdistää useisiin eri tietolähteisiin. Lisätietoja on kohdissa [Power BI -palvelun käytön aloittaminen](service-get-started.md) ja [Power BI Desktopin käytön aloittaminen](desktop-getting-started.md).  

Lisätietoja:  
- [Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)
- [Power BI -palvelun mallit](sample-datasets.md)
- [Power BI:n tietolähteet](service-get-data.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)
