---
title: R:n käyttö Power-kyselyeditorissa
description: Käytä R:ää Power BI Desktopin kyselyeditorissa kehittyneeseen analyysiin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/06/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b64b4b736291ce1c3bde02010b7e583a0c3dc406
ms.sourcegitcommit: 226b47f64e6749061cd54bf8d4436f7deaed7691
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/09/2019
ms.locfileid: "70841518"
---
# <a name="use-r-in-query-editor"></a>R:n käyttö kyselyeditorissa

[**R**](https://mran.microsoft.com/documents/what-is-r) on tehokas ohjelmointikieli, jota monet tilastotieteilijät, datatieteilijät ja tietoanalyytikot käyttävät. Voit käyttää **R:ää** Power BI Desktopin **kyselyeditorissa** seuraaviin tarkoituksiin:

* Tietomallien valmistelu

* Raporttien luominen

* Tietojen puhdistaminen, edistynyt tietojen muotoilu ja tietojoukkoanalytiikka, jotka sisältävät puuttuvat tiedot, ennusteet, klusteroinnin ja paljon muuta.  

## <a name="install-r"></a>Asenna R

Voit ladata **R:n** maksutta [Revolution Open -lataussivulta](https://mran.revolutionanalytics.com/download/) ja [CRAN-säilöstä](https://cran.r-project.org/bin/windows/base/).

### <a name="install-mice"></a>Asenna mice

R-ympäristössä on oltava asennettuna [**mice**-kirjasto](https://www.rdocumentation.org/packages/mice/versions/3.5.0/topics/mice). Ilman **mice**-kirjastoa mallikomentosarjan koodi ei toimi oikein. **Mice**-paketin myötä otetaan käyttöön menetelmä, jonka avulla puuttuvat tiedot käsitellään.

**Mice**-kirjaston asentaminen:

1. Käynnistä R.exe-ohjelma (esimerkiksi C:\Program Files\Microsoft\R Open\R-3.5.3\bin\R.exe)  

2. Suorita asennuskomento:

   ``` 
   >  install.packages('mice') 
   ```

## <a name="use-r-in-query-editor"></a>R:n käyttö kyselyeditorissa

Havainnollistamme **R:n** käyttöä **kyselyeditorissa** käyttämällä esimerkkinä osakemarkkinoiden tietojoukkoa, joka on .csv-tiedostossa. Työstämme sitä seuraavien vaiheiden kautta:

1. [Lataa **EuStockMarkets_NA.csv**-tiedosto](http://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/EuStockMarkets_NA.csv). Muista, mihin tallensit sen.

1. Lataa tiedosto **Power BI Desktopiin**: valitse **Aloitus**-valintanauhasta **Nouda tiedot > Teksti/CSV**.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_1.png)

1. Valitse tiedosto ja valitse sitten **Avaa**. CSV-tiedot näytetään **teksti/CSV-tiedosto** -valintaikkunassa.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_2.png)

1. Kun tiedot on ladattu, näet ne **Kentät**-ruudussa.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_3.png)

1. Jos haluat avata **kyselyeditorin**, valitse **Aloitus**-valintanauhasta **Muokkaa kyselyitä**.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_4.png)

1. Valitse **Muunna**-valintanauhasta **Suorita R-komentosarja**. Näyttöön tulee **Suorita R-komentosarja** -editori.  

   Riveiltä 15 ja 20 puuttuu tietoja, kuten muiltakin rivejä, joita et näe kuvassa. Seuraavissa vaiheissa näytetään, miten R täyttää kyseiset rivit puolestasi.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_5d.png)

1. Anna tässä esimerkissä seuraava komentosarjakoodi. Muista korvata &lt;Oma tiedostopolku&gt; polulla, joka osoittaa **EuStockMarkets_NA.csv**-tiedostoon paikallisessa tiedostojärjestelmässäsi, esimerkiksi C:/Users/John Doe/Documents/Microsoft/EuStockMarkets_NA.csv

    ```r
       dataset <- read.csv(file="<Your File Path>/EuStockMarkets_NA.csv", header=TRUE, sep=",")
       library(mice)
       tempData <- mice(dataset,m=1,maxit=50,meth='pmm',seed=100)
       completedData <- complete(tempData,1)
       output <- dataset
       output$completedValues <- completedData$"SMI missing values"
    ```

    > [!NOTE]
    > Saat joutua korvaamaan muuttujan nimeltä *tuloste*, jotta voit luoda oikein uuden tietojoukon, johon suodattimia käytetään.

7. Kun olet valinnut **OK**, **kyselyeditori** näyttää tietoturvaa koskevan varoituksen.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_6.png)
8. Jotta R-komentosarjat toimivat oikein Power BI -palvelussa, kaikki tietolähteet on asetettava **julkisiksi**. Saat lisätietoja tietosuoja-asetuksista ja niiden vaikutuksista katsomalla [yksityisyystasot](desktop-privacy-levels.md).

   ![](media/desktop-r-in-query-editor/r-in-query-editor_7.png)

   Kun olet valinnut **Tallenna**, komentosarja suoritetaan. Huomaa **Kentät**-ruudun uusi sarake **completedValues**. Huomaa, että muutamia tietoelementtejä puuttuu, kuten rivillä 15 ja 18. Katso seuraavassa kohdassa, miten R käsittelee sen.

   Käyttämällä vain viittä R-komentosarjan riviä **kyselyeditori** täyttää puuttuvat arvot ennakoivan mallin avulla.

## <a name="create-visuals-from-r-script-data"></a>Visualisointien luominen R-komentosarjatiedoista

Voimme nyt visualisoida, miten **mice**-kirjastoa käyttävä R-komentosarjakoodi täytti puuttuvat arvot, mikä on esitetty seuraavassa kuvassa:

![](media/desktop-r-in-query-editor/r-in-query-editor_8a.png)

Voit tallentaa kaikki valmiit visualisoinnit yhteen **Power BI Desktopin** .pbix-tiedostoon ja käyttää tietomallia ja sen R-komentosarjoja Power BI -palvelussa.

> [!NOTE]
> Voit [ladata .pbix-tiedoston](http://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/Complete%20Values%20with%20R%20in%20PQ.pbix), jossa kaikki nämä vaiheet on suoritettu.

Kun olet ladannut .pbix-tiedoston Power BI -palveluun, sinun on lisätoimien avulla otettava käyttöön tietojen päivitys ja päivitetyt visualisoinnit:  

* **Ota tietojoukon ajoitettu päivitys käyttöön** – Jos haluat ottaa tietojoukon ja R-komentosarjan sisältävän työkirjan päivittämisen käyttöön, katso kohta [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md), jossa on myös tietoja **henkilökohtaisesta yhdyskäytävästä**.

* **Asenna henkilökohtainen yhdyskäytävä** – **henkilökohtainen yhdyskäytävä** on oltava asennettuna koneessa, jossa tiedosto ja **R** sijaitsevat. Power BI -palvelu käyttää työkirjaa ja hahmontaa päivitetyt visualisoinnit uudelleen. Lue lisätietoja [henkilökohtaisen yhdyskäytävän asentamisesta ja määrittämisestä](service-gateway-personal-mode.md).

## <a name="limitations"></a>Rajoitukset

Kyselyissä, jotka sisältävät **Kyselyeditorissa** luotuja R-komentosarjoja, on joitakin rajoituksia:

* Kaikki R-tietolähteet on määritettävä **julkisiksi**. Myös kaikkien muiden **kyselyeditorin** kyselyn vaiheiden on oltava julkisia. Siirry tietolähdeasetuksiin **Power BI Desktopissa** valitsemalla **Tiedosto > Asetukset > Tietolähdeasetukset**.

  ![](media/desktop-r-in-query-editor/r-in-query-editor_9.png)

  Valitse **Tietolähdeasetukset**-valintaikkunassa tietolähteet ja sitten **Muokkaa käyttöoikeuksia...** .  Aseta **yksityisyystasoksi** **Julkinen**.

  ![](media/desktop-r-in-query-editor/r-in-query-editor_10.png)    
* Jos haluat ottaa R-visualisointien tai tietojoukon ajoitetun päivityksen käyttöön, sinun on otettava **Ajoitettu päivitys** käyttöön ja asennettava **Henkilökohtainen yhdyskäytävä** tietokoneeseen, jossa työkirja ja **R** ovat. Saat lisätietoja kummastakin tämän artikkelin edellisestä osasta, jonka linkeissä on lisätietoja kummastakin.

Voit tehdä kaikenlaisia asioita R:llä ja mukautetuilla kyselyillä, joten tutki ja muotoile tietoja sellaisiksi, miten haluat niiden näkyvän.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Johdanto R:ään](https://mran.microsoft.com/documents/what-is-r) 

* [Suorita R-komentosarat Power BI Desktopissa](desktop-r-scripts.md) 

* [Ulkoisen R IDE:n käyttö Power BI:n kanssa](desktop-r-ide.md) 

* [R-paketit Power BI-palvelussa](service-r-packages-support.md)
