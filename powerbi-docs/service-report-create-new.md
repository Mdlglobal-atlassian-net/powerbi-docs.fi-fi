---
title: 'Opetusohjelma - Uuden raportin luominen tietojoukosta '
description: Uuden raportin luominen tietojoukosta.
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: monitoring
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7da16deb3e5919d509a5cbbb7fd845914c8c4ea4
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/09/2018
ms.locfileid: "30974752"
---
# <a name="create-a-new-power-bi-report-by-importing-a-dataset"></a>Uuden raportin luominen tuomalla tietojoukko
Olet lukenut [Power BI -raportit](service-reports.md) ja haluat nyt luoda omasi. Voit luoda raportin monella eri tavalla, ja aloitamme tämän artikkelin luomalla hyvin perustasoisen raportin Excel-tietojoukosta. Kun ymmärrät raportin luomisen perusteet, **Seuraavat vaiheet** näytön alareunassa vievät sinut monimutkaisempia raportteja koskevaan aiheisiin.  

> **VIHJE**: Voit luoda raportin kopioimalla aiemmin luodun raportin, katso [Kopioi raportti](power-bi-report-copy.md)
> 
### <a name="prerequisites"></a>Edellytykset
- Power BI -palvelu (katso raporttien luominen Power BI Desktopista kohdasta [Työpöydän raporttinäkymä](desktop-report-view.md)   
- Jälleenmyyntianalyysimallin tietojoukko

## <a name="import-the-dataset"></a>Tuo tietojoukko
Tämä raporttien luontimenetelmä alkaa tietojoukosta ja tyhjästä raporttipohjasta. Seuraavaksi [Lataa jälleenmyyjän analyysin Excel-tietojoukkoesimerkki](http://go.microsoft.com/fwlink/?LinkId=529778) ja tallenna se OneDrive for Businessiin (ensisijainen) tai paikallisesti.

1. Luomme raportin Power BI -palvelun työtilassa, joten valitse aiemmin luotu työtila tai luo uusi.
   
   ![Luettelo sovellustyötiloista](media/service-report-create-new/power-bi-workspaces2.png)
2. Valitse vasemman siirtymisruudun alaosassa, **Nouda tiedot**.
   
   ![Nouda tiedot](media/service-report-create-new/power-bi-get-data3.png)
3. Valitse **Tiedostot** ja siirry sijaintiin, johon tallensit jälleenmyyntianalyysimallin.
   
    ![valitse Tiedostot](media/service-report-create-new/power-bi-select-files.png)
4. Valitse tässä harjoituksessa **Tuonti**.
   
   ![Valitse Tuo](media/service-report-create-new/power-bi-import.png)
5. Kun tietojoukko on tuotu, valitse **Näytä tietojoukko**.
   
   ![Valitse Näytä tietojoukko](media/service-report-create-new/power-bi-view-dataset.png)
6. Tietojoukon tarkastelu itse asiassa avaa raporttieditorin.  Näkyviin tulee tyhjä kangas ja raporttien muokkaustyökalut.
   
   ![raporttieditori](media/service-report-create-new/power-bi-blank-report.png)

> **Vihje**: Jos et tunne raporttien muokkauspohjaa tai haluat päivittää tietojasi, [katso esittely raporttieditorista ](service-the-report-editor-take-a-tour.md) ennen jatkamista.
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Viisarimittarin lisääminen raporttiin
Nyt kun tietojoukkomme on tuotu, aloitetaan vastaamaan kysymyksiin.  Markkinointipäällikkö (CMO) haluaa tietää, miten lähellä tämän vuoden myyntitavoitteitamme olemme. Mittari on [hyvä valinta visualisoimaan](power-bi-report-visualizations.md) tämän tyyppisten tietojen näyttämistä.

1. Valitse Kentät-ruudussa **Myynti**  >  **Tämän vuoden myynti** > **Arvo**.
   
    ![pylväskaavio raporttieditorissa](media/service-report-create-new/power-bi-report-step1.png)
2. Visualisoinnin muuntaminen mittariksi valitsemalla ![Mittarin malli](media/service-report-create-new/powerbi-gauge-icon.png) mittarin kuvakkeesta **Visualisoinnit**-ruudussa.
   
    ![Mittarin visualisointi raporttieditorissa](media/service-report-create-new/power-bi-report-step2.png)
3. Vedä **Myynti** > **Tämän vuoden myynti** > **Tavoite** kohtaan **Tavoitearvo**. Näyttää siltä, että olemme hyvin lähellä tavoitteitamme.
   
    ![Mittarin visualisointi tavoite tavoitearvona](media/service-report-create-new/power-bi-report-step3.png)
4. Nyt olisi hyvä aika [tallentaa raporttisi](service-report-save.md).
   
   ![Tiedosto-valikko](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Aluekaavion ja osittajan lisääminen raporttiin
CMO haluaa esittää meille joitakin lisäkysymyksiä vastattavaksi. Hän haluaa tietää, miten tämän vuoden myynti vertautuu viime vuoteen. Ja hän haluaa nähdä havainnot alueittain.

1. Tehdään ensin tilaa pohjalle. Valitse mittari ja siirrä se oikeaan yläkulmaan. Tartu ja vedä jotain kulmaa ja pienennä sitä.
2. Poista mittarin valinta. Valitse Kentät-ruudussa **Myynti** > **Tämän vuoden myynti** > **Arvo** ja valitse **Myynti**  >  **Viime vuoden myynti**.
   
    ![raporttieditori ja mittari sekä palkkikaavio](media/service-report-create-new/power-bi-report-step4.png)
3. Visualisoinnin muuntaminen aluekaavioksi valitsemalla Aluekaavion malli ![mittarin kuvakkeesta](media/service-report-create-new/power-bi-areachart-icon.png) **Visualisoinnit**-ruudussa.
4. Valitse **Aika**  >  **Jakso** ja lisää se **Akseli**-kohtaan.
   
    ![raporttieditori ja aluekaavio aktiivisena](media/service-report-create-new/power-bi-report-step5.png)
5. Voit lajitella visualisoinnin ajanjakson mukaan valitsemalla kolme pistettä ja valitsemalla **Lajitteluperuste**.
6. Nyt lisätään osittaja. Valitse pohjalta tyhjä alue ja valitse osittaja ![Osittajakuvake-](media/service-report-create-new/power-bi-slicer-icon.png)    malli. Tämä lisää pohjalle tyhjän osittajan.
   
    ![raportin pohja](media/service-report-create-new/power-bi-report-step6.png)    
7. Valitse Kentät-ruudussa **Alue** > **Alue**. Siirrä ja muuta osittajan kokoa.
   
    ![Lisää raporttieditorissa alue](media/service-report-create-new/power-bi-report-step7.png)  
8. Osittajan avulla voit etsiä kuviot ja merkitykselliset tiedot alueen mukaan.
   
   ![videon osittajan käyttämisestä](media/service-report-create-new/power-bi-slicer-video2.gif)  

Jatka tietojen tarkastelemista ja visualisointien lisäämistä. Kun olet löytänyt erityisen merkityksellisiä tietoja, [kiinnitä ne raporttinäkymään](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Seuraavat vaiheet
* [Uuden sivun lisääminen raporttiin](power-bi-report-add-page.md)  
* Lue, miten [kiinnittää visualisointeja raporttinäkymään](service-dashboard-pin-tile-from-report.md)   
* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
