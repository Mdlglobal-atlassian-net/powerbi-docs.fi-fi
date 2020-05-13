---
title: COVID-19-seurantamalli Yhdysvaltain viranomaisille
description: Lataa muokattavaksi malliraportti, joka sisältää Yhdysvaltain osavaltiotason ja paikallistason tietoja COVID-19-pandemiasta.
author: LukaszPawlowski-MS
ms.reviewer: maggies
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/28/2020
ms.author: lukaszp
LocalizationGroup: Samples
ms.openlocfilehash: aca7fc70bc70de553eee070ce5e1522b96c94880
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83277889"
---
# <a name="covid-19-tracking-sample-for-us-state-and-local-governments"></a>COVID-19-seurantamalli Yhdysvaltain viranomaisille

Power BI -tiimi on luonut COVID-19-seurantamallin, jonka avulla Yhdysvaltain viranomaiset voivat julkaista ja räätälöidä vuorovaikutteisia raportteja COVID-19-tilanteesta. Power BI Desktopilla viranomaiset voivat analysoida ja visualisoida COVID-19-tietoja ja pitää yhteisönsä ajan tasalla kaupunki-, piirikunta-, osavaltio- ja maatasolla. Power BI:n Julkaise verkkoon -toiminnolla he voivat jakaa raportin suoraan kansalaisten tiedoksi. Tässä artikkelissa esitellään eri tapoja käyttää Power BI:n vuorovaikutteisia visualisointeja julkisessa tarinassa, blogissa tai verkkosivustossa.

:::image type="content" source="media/sample-covid-19-us/covid-19-us-tracking-sample.png" alt-text="COVID-19-malli ja tietoja Yhdysvalloista":::

Tässä artikkelissa opit

- kopioimaan upotuskoodin ja sijoittamaan sen omaan sivustoosi 
- tekemään muokkauksia, esimerkiksi muotoilemaan näkyviin tietyn osavaltion tiedot
- julkaisemaan Power BI -palveluun
- julkaisemaan verkkoon 
- yhdistämään näitä tietoja toisesta lähteestä peräisin oleviin tietoihin. 

## <a name="prerequisites"></a>Edellytykset

Sinun täytyy täyttää seuraavat edellytykset, ennen kuin voit aloittaa tarinasi kertomisen Power BI:llä:

- Lataa maksuton [Power BI Desktop](https://powerbi.microsoft.com/desktop/) -sovellus.
- Rekisteröidy [Power BI -palveluun](https://powerbi.microsoft.com/get-started/).

## <a name="option-1-pre-built-embed-code"></a>Vaihtoehto 1: valmis upotuskoodi

Microsoft on julkaissut malliraportin ja verkkoon julkaisemisen upotuskoodin. Upotuskoodilla voit upottaa koko mallin, koko maan näkymä mukaan lukien, sekä porautua osavaltio- ja piirikuntatasolle omassa verkkosivustossasi. Suosittelemme, että tutustut tämän artikkelin [vastuuvapauslausekkeisiin](#disclaimers) ennen näiden tietojen julkaisemista.

Jos haluat sisällyttää vuorovaikutteisen grafiikan sivustoosi, kopioi ja liitä seuraava upotuskoodi siihen kohtaan, jossa haluat näyttää grafiikan verkkosivullasi.  

```
<iframe width="1600" height="900" src="https://app.powerbi.com/view?r=eyJrIjoiMmI2ZjExMzItZTcwNy00YmUwLWFlMTAtYTUxYzVjODZmYjA5IiwidCI6ImMxMzZlZWMwLWZlOTItNDVlMC1iZWFlLTQ2OTg0OTczZTIzMiIsImMiOjF9" frameborder="0" allowFullScreen="true"></iframe>
```

Upotuskoodi on HTML iFrame -elementti, jonka voit lisätä mille tahansa HTML-sivulle. Säädä iFramen leveys ja korkeus sivustoosi sopivaksi. Malliraportti on tehty 16:9-kuvasuhteelle, joten valitse koko, joka säilyttää tämän kuvasuhteen. Oikein toteutettuna grafiikka näkyy ilman ylimääräisiä harmaita reunoja. Tutustu [iFramen koon muokkaamiseen vinkkeihin](../collaborate-share/service-publish-to-web.md#tips-for-iframe-height-and-width), kun teet näitä muutoksia.

## <a name="option-2-customize-the-sample-power-bi-file"></a>Vaihtoehto 2: muokkaa Power BI -mallitiedostoa

Power BI -tiedosto sisältää tiedot ja vuorovaikutteisen grafiikan .pbix-tiedostomuodossa, jota voit muokata Power BI Desktopissa.  

Voit esimerkiksi suodattaa raportin tiettyyn osavaltioon ja luoda sitten tällä tavalla muokatulle raportille oman verkkoon julkaisemisen upotuskoodin.

USAFacts-tiedot tarjotaan Creative Commons -käyttöoikeuden nojalla, joten tietojen lähde täytyy mainita käyttöoikeusehtojen mukaisesti. Tutustu [vastuuvapauslausekkeisiin](#disclaimers) ennen näiden tietojen julkaisemista.

Aloita [lataamalla .pbix-tiedosto (täältä)](https://go.microsoft.com/fwlink/?linkid=2125058).

### <a name="update-your-report"></a>Päivitä raporttisi 

1. Lataa maksuttoman [Power BI Desktop](https://powerbi.microsoft.com/desktop/) -sovelluksen uusin versio, jos sinulla ei vielä ole sitä. 

2. Lataa [.pbix-tiedosto](https://go.microsoft.com/fwlink/?linkid=2125058), jos sinulla ei vielä ole sitä, ja avaa se Power BI Desktopissa.

3. Suodata raportti tiettyyn osavaltioon laajentamalla Suodattimet-ruutu valitsemalla nuoli.

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-filters-pane.png" alt-text="Laajenna Suodattimet-ruutu":::

4. Valitse haluamasi osavaltio. 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-filter-selection.png" alt-text="Valitse osavaltio":::

5. Tallenna tiedosto valitsemalla **Tiedosto** > **Tallenna**. 

### <a name="refresh-your-report"></a>Päivitä raportti 

1. Valitse **Päivitä**-painike.

    :::image type="content" source="media/sample-covid-19-us/power-bi-desktop-refresh-button.png" alt-text="Päivitä-painike":::

2. Valitse **Anonyymi** > **Yhdistä**. 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-azure-blob.png" alt-text="Valitse Anonyymi":::

 
3. Valitse **Ohita yksityisyystasot** (tarvittaessa) > **Tallenna**. 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-privacy-levels.png" alt-text="Valitse yksityisyystasot":::

### <a name="publish-your-report-to-the-power-bi-service"></a>Julkaise raportti Power BI -palveluun

Kun olet muokannut raportin haluamallasi tavalla, [julkaise se Power BI -palveluun täällä annettujen ohjeiden mukaisesti](../create-reports/desktop-upload-desktop-files.md).

### <a name="configure-scheduled-refresh"></a>Ajoitetun päivityksen määrittäminen

Jos haluat pitää raportin tiedot ajan tasalla, voit määrittää [päivitysaikataulun](../connect-data/refresh-scheduled-refresh.md) raportin julkaisemisen jälkeen.

Kun toimit ohjeiden mukaisesti, valitse seuraavat asetukset:

1. Tietolähteen tunnistetietojen todennusmenetelmä: Anonyymi
2. Tämän tietolähteen tietosuojataso: Julkinen

Testaa päivitysasetus valitsemalla [Päivitä nyt](../connect-data/refresh-data.md#data-refresh) -toiminto tietojoukkokohteessa.

Päivitetyt tiedot ladataan aina, kun päivitys suoritetaan aikataulun mukaisesti. Taustatiedot tarjoaa USAFacts, ja ne eivät välttämättä päivity yhtä usein kuin päivitysaikataulussasi on määritetty. Tarkista [USAFactsin verkkosivustosta](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/) taustatietojen edellisen päivityksen ajankohta. 

Jos aiot julkaista muokatun raportin verkkosivustossasi, sinun kannattaa määrittää päivitysaikataulu USAFacts-tietojen päivittämisen mukaisesti. Koska USAFacts saattaa päivittää tietoja eri aikaan joka päivä, sinun kannattaa ehkä määrittää useita päivityskertoja kullekin päivälle. 

### <a name="create-a-publish-to-web-embed-code"></a>Luo verkkoon julkaisemisen upotuskoodi 

Jos haluat upottaa muokatun raportin omaan verkkosivustoosi, [luo oma verkkoon julkaisemisen upotuskoodi ohjeiden mukaisesti](../collaborate-share/service-publish-to-web.md#create-embed-codes-with-publish-to-web).

Kun julkaiset upotuskoodin, upotat tiedot sivustoosi vahvistusvalintaikkunan iFramen avulla.

Jos teet raporttiin muutoksia Power BI Desktopissa, voit julkaista ja korvata olemassa olevan raportin Power BI -palvelussa. Upotuskoodi ei muutu. Raportin muutokset tai päivitetyt tiedot näkyvät verkkosivustossasi noin tunnin kuluttua. 

## <a name="option-3-mash-up-data-from-another-source"></a>Tapa 3: toisesta lähteestä peräisin olevien tietojen yhdistäminen 

Voit yhdistää tämän raportin tietoja myös toisesta lähteestä peräisin oleviin tietoihin. Seuraavassa esimerkissä tiedot ovat peräisin [Johns Hopkins Universitysta](https://github.com/CSSEGISandData/COVID-19). Suosittelemme, että tutustut tämän artikkelin [vastuuvapauslausekkeisiin](#disclaimers) ennen näiden tietojen julkaisemista.

1. Valitse **Nouda tiedot** > **Verkko**.

    :::image type="content" source="media/sample-covid-19-us/power-bi-desktop-get-data.png" alt-text="Nouda tiedot -painike":::

2. Anna seuraava URL-osoite:

    ```
    https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv
    ```

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-from-web.png" alt-text="Valitse tiedot verkosta":::

3. Valitse **OK**. 

    > [!NOTE]
    > Johns Hopkins Universityn julkaisema linkki voi muuttua. Tarkista uusimmat tiedot [Johns Hopkins GitHub -sivulta](https://github.com/CSSEGISandData/COVID-19).

4. Lataa maailmanlaajuisten vahvistettujen tautitapausten tiedot valitsemalla **Lataa**.  

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-load-data.png" alt-text="Lataa tiedot verkosta":::

    [Verkkosivuille yhdistäminen Power BI Desktopista](../connect-data/desktop-connect-to-web.md) -ohjeartikkelista saat lisätietoja tietojen lataamisesta verkosta.
    
Tämän jälkeen voit visualisoida tietoja Power BI Desktopilla. Toimi lopuksi **tavan 2** [(Julkaise raportti Power BI -palveluun)](#publish-your-report-to-the-power-bi-service) ohjeiden mukaisesti ja julkaise raportti sekä luo muokattu upotuskoodi. 

## <a name="option-4-use-the-covid-19-us-tracking-template-app"></a>Vaihtoehto 4: käytä COVID-19 US Tracking -mallisovellusta

Power BI -työryhmä on luonut lisävaihtoehdoksi COVID-19 US Tracking *-mallisovelluksen*, jonka avulla pääset alkuun heti. Mallisovellukset ovat tiettyyn tietolähteeseen liittyviä raportti-, koontinäyttö- ja tietojoukkopaketteja. Voit ladata ne AppSourcesta, käyttää niitä tai muokata tarpeidesi mukaan ja jaella niitä työtovereillesi. 

Tämä COVID-19 US Tracking -mallisovellus sisältää valmiin COVID-19-mittausraportin, jota voi käyttää sellaisenaan, jota voi mukauttaa suoraan Power BI -palvelussa tai jonka voi ladata tarvittaessa muiden tietolähteiden lisäykseksi. Lue tiedot [COVID-19 US Tracking -mallisovelluksen asentamisesta](../connect-data/service-connect-to-covid-19-tracking.md) ja käytön aloittamisesta heti.

## <a name="about-the-data-source-for-this-report"></a>Tietoja tämän raportin tietolähteestä
Tämä vuorovaikutteinen raportti koostaa yhteen tietoja CDC:ltä (Centers for Disease Control and Prevention) sekä osavaltio- ja paikallistason terveydenhuoltoviranomaisilta. Piirikuntatason tiedot on vahvistettu viittaamalla suoraan osavaltio- ja paikallistason viranomaisiin (linkki).

Tiedot tarjoaa USAFacts. Koska tietoja päivitetään niin usein, ne eivät ehkä vastaa täysin viranomaisorganisaatioiden tai uutismedioiden ilmoittamia lukuja. Saat lisätietoja ja voit ladata tiedot [USAFactsin verkkosivustosta](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/). 

## <a name="disclaimers"></a>Vastuuvapauslausekkeet

Tämä raportti ja tiedot tarjotaan sellaisenaan, kaikkine vikoineen ja ilmaan minkäänlaisia takuita. Microsoft ei anna mitään suoria takuita ja kiistää nimenomaisesti kaikki epäsuorat takuut, mukaan lukien takuut soveltuvuudesta kaupankäynnin kohteeksi, tiettyyn käyttötarkoitukseen tai oikeuksien rikkomattomuudesta.

USAFacts-tiedot tarjotaan Creative Commons -käyttöoikeuden nojalla. Jos haluat käyttää niitä, mainitse tietojen lähteeksi USAFacts ja linkitä USAFactsin palveluun. Voit tarkistaa tarkat lähdeviittausohjeet kohdasta **#MadewithUSAFacts** USAFacts-sivulta [Coronavirus in the United States: Mapping the COVID-19 outbreak in the states and counties](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/).

Johns Hopkins Universityn tietojen tekijänoikeudet: copyright 2020 Johns Hopkins University, kaikki oikeudet pidätetään. Tiedot tarjotaan julkisesti vain opetus- ja tutkimuskäyttöön. Tässä ovat koostetietoesimerkin tietojen täydet [käyttöehdot](https://github.com/CSSEGISandData/COVID-19/blob/master/README.md). Lisätietoja on saatavilla [Johns Hopkins Universityn verkkosivustosta](https://coronavirus.jhu.edu/map-faq.html).

## <a name="next-steps"></a>Seuraavat vaiheet

[Hanki Power BI:n malleja](../create-reports/sample-datasets.md)




