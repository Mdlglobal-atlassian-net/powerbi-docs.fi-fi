---
title: Perusaluekaavio
description: Perusaluekaavio.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 09322a1ead6ae4c3a00dc42e2b4a642dcc2d6181
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34584135"
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
3. Lisää uusi raportin sivu valitsemalla raportin alareunasta keltainen plus (+) -kuvake.
4. Luo aluekaavio, joka näyttää tämän vuoden myynnin ja edellisen vuoden myynnin kuukauden mukaan.
   
   a. Valitse Kentät-ruudussa **Myynti \> Viime vuoden myynti** ja **Tämän vuoden myynti > Arvo**.

   ![](media/power-bi-visualization-basic-area-chart/power-bi-bar-chart.png)

   b.  Muunna kaavio takaisin perusaluekaavioksi valitsemalla Aluekaavio-kuvake Visualisoinnit-ruudussa.

   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Valitse **Aika\> Kuukausi** ja lisää se **Akseli**-kohtaan.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Jos haluat näyttää kaavion kuukauden mukaan, valitse kolme pistettä (visualisoinnin oikeassa yläkulmassa) ja valitse **Lajittele kuukauden mukaan**.

## <a name="highlighting-and-cross-filtering"></a>Korostaminen ja ristiinsuodatus
Lisätietoja Suodattimet-paneelin käyttämisestä saat ohjeaiheesta [Suodattimen lisääminen raporttiin](power-bi-report-add-filter.md).

Voit korostaa kaavion tietyn alueen valitsemalla alueen tai sen yläreunan.  Toisin kuin muut visualisointityypit, jos muita visualisointeja on samalla sivulla, perusaluekaavion korostaminen ei ristiinsuodata muita visualisointeja raportin sivulla. Aluekaaviot ovat kuitenkin ristiinsuodatuksen kohteena muiden raportin sivulla olevien visualisointien käynnistämänä. Lisätietoja on artikkelissa [Visualisointitoimet raporteissa](service-reports-visual-interactions.md)


## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys   
* [Tee raportista helpommin käytettävä toimintarajoitteisille ihmisille](desktop-accessibility.md)
* Perusaluekaaviot eivät toimi arvojen vertailussa kerrostettujen alueiden eston vuoksi. Power BI käyttää läpinäkyvyyttä osoittamaan alueiden päällekkäisyyttä. Se kuitenkin toimii hyvin vain kahdella tai kolmella eri alueella. Kun haluat verrata trendiä yli kolmeen mittayksikköön, kokeile viivakaavioiden käyttämistä. Kun haluat verrata määrää yli kolmeen mittayksikköön, kokeile puukartan käyttämistä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Raportit Power BI:ssä](service-reports.md)  
[Visualisoinnit Power BI -raporteissa](power-bi-report-visualizations.md)  
[Power BI:n peruskäsitteet](service-basic-concepts.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

