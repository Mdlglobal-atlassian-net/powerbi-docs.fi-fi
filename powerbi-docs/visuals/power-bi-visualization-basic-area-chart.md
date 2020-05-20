---
title: Perusaluekaavio
description: Perusaluekaavio.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/05/2020
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: e03a453b95a797b281f789e8aed40b3879b54e02
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563845"
---
# <a name="create-and-use-basic-area-charts"></a>Perusaluekaavioiden luominen ja käyttäminen

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Perusaluekaavio (eli kerrostettu aluekaavio) perustuu viivakaavioon. Akselin ja rivin välissä oleva alue täytetään väreillä osoittamaan määrää. 

Aluekaaviot korostavat muutoksen suuruutta ajan kuluessa, ja niiden avulla voidaan kiinnittää huomio trendin kokonaisarvoon. Esimerkiksi tiedot, jotka edustavat tuottoa ajan kuluessa, voidaan kuvata aluekaaviossa kokonaistuoton korostamiseksi.

![](media/power-bi-visualization-basic-area-chart/power-bi-chart-example.png)

> [!NOTE]
> Raportin jakaminen työtoverin kanssa Power BI:ssä edellyttää, että teillä kummallakin on oma Power BI Pro -käyttöoikeus tai että raportti on tallennettu Premium-kapasiteettiin.

## <a name="when-to-use-a-basic-area-chart"></a>Milloin kannattaa käyttää perusaluekaaviota
Perusaluekaavio on hyvä valinta:

* jos haluat tarkastella ja vertailla määrän trendiä aikasarjassa 
* yksittäisille sarjoille, jotka edustavat fyysisesti laskettavissa olevaa joukkoa

### <a name="prerequisites"></a>Edellytykset
Tässä opetusohjelmassa käytetään [Jälleenmyyntianalyysimallin PBIX-tiedostoa](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. Valitse valikkorivin vasemmasta yläosasta **Tiedosto** > **Avaa**
   
2. **Jälleenmyyntianalyysimallin PBIX-tiedoston löytäminen**

1. Avaa **Jälleenmyyntianalyysimallin PBIX-tiedosto** raporttinäkymässä ![Näyttökuva raporttinäkymän kuvakkeesta.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Valitse ![Näyttökuva keltaisesta välilehdestä.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) uuden sivun lisäämiseksi.


## <a name="create-a-basic-area-chart"></a>Perusaluekaavion luominen
 

1. Näillä ohjeilla voit luoda aluekaavio, joka näyttää tämän vuoden myynnin ja edellisen vuoden myynnin kuukauden mukaan.
   
   a. Valitse Kentät-ruudusta **Myynti \> Viime vuoden myynti** ja **Tämän vuoden myynti > Arvo**.

   ![aluekaavion tietoarvot](media/power-bi-visualization-basic-area-chart/power-bi-bar-chart.png)

   b.  Muunna kaavio takaisin perusaluekaavioksi valitsemalla Aluekaavio-kuvake Visualisoinnit-ruudussa.

   ![aluekaaviokuvake](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  Valitse **Aika \> FiscalMonth** ja lisää se **Akseli**-kohtaan.   
   ![aluekaavion akseliarvot](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Jos haluat näyttää kaavion kuukauden mukaan, valitse kolme pistettä (visualisoinnin oikeassa yläkulmassa) ja valitse **Lajittele kuukauden mukaan**. Jos haluat muuttaa lajittelujärjestyksen, valitse kolme pistettä uudelleen ja valitse joko **Lajittele nousevaan järjestykseen** tai **Lajittele laskevaan järjestykseen**.

## <a name="highlighting-and-cross-filtering"></a>Korostaminen ja ristiinsuodatus
Lisätietoja Suodattimet-paneelin käyttämisestä saat ohjeaiheesta [Suodattimen lisääminen raporttiin](../create-reports/power-bi-report-add-filter.md).

Voit korostaa kaavion tietyn alueen valitsemalla alueen tai sen yläreunan.  Toisin kuin muut visualisointityypit, jos muita visualisointeja on samalla sivulla, perusaluekaavion korostaminen ei ristiinsuodata muita visualisointeja raportin sivulla. Aluekaaviot ovat kuitenkin ristiinsuodatuksen kohteena muiden raportin sivulla olevien visualisointien käynnistämänä. 

1. Kokeile sitä valitsemalla aluekaavio ja kopioimalla se **Uusien myymälöiden analyysi** -raportin sivulle (CTRL-C ja CTRL-V).
2. Valitse yksi aluekaavion sävytetyistä alueista ja sen jälkeen toinen. Huomaa, että tällä ei ole vaikutusta muihin sivulla oleviin visualisointeihin.
1. Valitse nyt elementti. Näet, että tämä ristiinsuodattaa aluekaavion.

    ![Suodatinesimerkkejä](media/power-bi-visualization-basic-area-chart/power-bi-area-chart-filters.gif) 

Lisätietoja on artikkelissa [Visualisointitoimet raporteissa](../create-reports/service-reports-visual-interactions.md)


## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys   
* [Tee raportista helpommin käytettävä toimintarajoitteisille ihmisille](../create-reports/desktop-accessibility-overview.md)
* Perusaluekaaviot eivät toimi arvojen vertailussa kerrostettujen alueiden eston vuoksi. Power BI käyttää läpinäkyvyyttä osoittamaan alueiden päällekkäisyyttä. Se kuitenkin toimii hyvin vain kahdella tai kolmella eri alueella. Kun haluat verrata trendiä yli kolmeen mittariin, kokeile viivakaavioiden käyttämistä. Kun haluat verrata määrää yli kolmeen mittariin, kokeile puukartan käyttämistä.

## <a name="next-step"></a>Seuraava vaihe
[Raportit Power BI:ssä](power-bi-visualization-card.md)  
