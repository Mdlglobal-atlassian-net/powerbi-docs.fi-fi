---
title: Perusaluekaavio
description: Perusaluekaavio.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 02d81a4ebb92ec199887109c7f2d9afcb6449eda
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61393191"
---
# <a name="basic-area-chart"></a>Perusaluekaavio
Perusaluekaavio (eli kerrostettu aluekaavio) perustuu viivakaavioon. Akselin ja rivin välissä oleva alue täytetään väreillä osoittamaan määrää. 

Aluekaaviot korostavat muutoksen suuruutta ajan kuluessa, ja niiden avulla voidaan kiinnittää huomio trendin kokonaisarvoon. Esimerkiksi tiedot, jotka edustavat tuottoa ajan kuluessa, voidaan kuvata aluekaaviossa kokonaistuoton korostamiseksi.

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>Milloin kannattaa käyttää perusaluekaaviota
Perusaluekaavio on hyvä valinta:

* jos haluat tarkastella ja vertailla määrän trendiä aikasarjassa 
* yksittäisille sarjoille, jotka edustavat fyysisesti laskettavissa olevaa joukkoa

### <a name="prerequisites"></a>Edellytykset
 - Power BI -palvelu
 - Jälleenmyyntianalyysimalli

Seurataksesi kirjaudu Power BI:hin, valitse **Nouda tiedot \> Mallit \> Jälleenmyyntianalyysimalli > Yhdistä** ja valitse **Koontinäyttö**. 

## <a name="create-a-basic-area-chart"></a>Perusaluekaavion luominen
 

1. Avaa Jälleenmyyntianalyysimalli-raportti valitsemalla Jälleenmyyntianalyysimalli-koontinäytössä **Myymälöitä yhteensä** -ruutu.
2. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**.
3. Lisää uusi raporttisivu valitsemalla raportin alareunasta keltainen plus (+) -kuvake.
4. Luo aluekaavio, joka näyttää tämän vuoden myynnin ja edellisen vuoden myynnin kuukauden mukaan.
   
   a. Valitse Kentät-ruudussa **Myynti \> Viime vuoden myynti** ja **Tämän vuoden myynti > Arvo**.

   ![](media/power-bi-visualization-basic-area-chart/power-bi-bar-chart.png)

   b.  Muunna kaavio takaisin perusaluekaavioksi valitsemalla Aluekaavio-kuvake Visualisoinnit-ruudussa.

   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Valitse **Aika\> Kuukausi** ja lisää se **Akseli**-kohtaan.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Jos haluat näyttää kaavion kuukauden mukaan, valitse kolme pistettä (visualisoinnin oikeassa yläkulmassa) ja valitse **Lajittele kuukauden mukaan**. Jos haluat muuttaa lajittelujärjestyksen, valitse kolme pistettä uudelleen ja valitse joko **Lajittele nousevaan järjestykseen** tai **Lajittele laskevaan järjestykseen**.

## <a name="highlighting-and-cross-filtering"></a>Korostaminen ja ristiinsuodatus
Lisätietoja Suodattimet-paneelin käyttämisestä saat ohjeaiheesta [Suodattimen lisääminen raporttiin](../power-bi-report-add-filter.md).

Voit korostaa kaavion tietyn alueen valitsemalla alueen tai sen yläreunan.  Toisin kuin muut visualisointityypit, jos muita visualisointeja on samalla sivulla, perusaluekaavion korostaminen ei ristiinsuodata muita visualisointeja raportin sivulla. Aluekaaviot ovat kuitenkin ristiinsuodatuksen kohteena muiden raportin sivulla olevien visualisointien käynnistämänä. 

1. Kokeile sitä valitsemalla aluekaavio ja kopioimalla se toiselle raportin sivulle (CTRL-C ja CTRL-V).
2. Valitse yksi sävytetyistä alueista ja sen jälkeen toinen. Huomaa, että tällä ei ole vaikutusta muihin sivulla oleviin visualisointeihin.

    ![Tämän vuoden myynti valittuna aluekaaviosta](media/power-bi-visualization-basic-area-chart/power-bi-select-area.png)

3. Valitse nyt elementti sivun muista visualisoinneista. Se voi olla esimerkiksi sarakekaavio tai kuukausi viivakaaviossa. Huomaa, miten tämä suodattaa aluekaavion.  

    ![Ft Oglethorpe -palkki valittu](media/power-bi-visualization-basic-area-chart/power-bi-filter.png) 

Lisätietoja on artikkelissa [Visualisointitoimet raporteissa](../service-reports-visual-interactions.md)


## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys   
* [Tee raportista helpommin käytettävä toimintarajoitteisille ihmisille](../desktop-accessibility.md)
* Perusaluekaaviot eivät toimi arvojen vertailussa kerrostettujen alueiden eston vuoksi. Power BI käyttää läpinäkyvyyttä osoittamaan alueiden päällekkäisyyttä. Se kuitenkin toimii hyvin vain kahdella tai kolmella eri alueella. Kun haluat verrata trendiä yli kolmeen mittariin, kokeile viivakaavioiden käyttämistä. Kun haluat verrata määrää yli kolmeen mittariin, kokeile puukartan käyttämistä.

## <a name="next-step"></a>Seuraava vaihe
[Raportit Power BI:ssä](power-bi-visualization-card.md)  

