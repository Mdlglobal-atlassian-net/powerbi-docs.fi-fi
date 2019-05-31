---
title: Raportin luominen tietojoukosta
description: Power BI-raportin luominen tietojoukosta.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 6b69c2b1fa811d395a26403de852c44af33491c7
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770219"
---
# <a name="create-a-report-in-the-power-bi-service-by-importing-a-dataset"></a>Raportin luominen Power BI-palvelussa tuomalla tietojoukko
Olet lukenut [Power BI -raportit](consumer/end-user-reports.md) ja haluat nyt luoda omasi. Voit luoda raportin monella eri tavalla. Aloitamme tämän artikkelin luomalla perustasoisen raportin Excel-tietojoukosta Power BI-palvelussa. Kun ymmärrät raportin luomisen perusteet, tutustu [seuraavat vaiheet](#next-steps) Lisää loppuun advanced raportin aiheet.  

## <a name="prerequisites"></a>Edellytykset
- [Rekisteröidy Power BI-palveluun](service-self-service-signup-for-power-bi.md). Katso Power BI Desktop-raporttien luominen [työpöydän raporttinäkymä](desktop-report-view.md). 
- [Lataa jälleenmyyjän analyysin Excel-tietojoukkoesimerkki](http://go.microsoft.com/fwlink/?LinkId=529778) ja tallenna se OneDrive for Businessiin tai paikallisesti.

## <a name="import-the-dataset"></a>Tuo tietojoukko
Tämä raporttien luontimenetelmä alkaa tietojoukosta ja tyhjästä raporttipohjasta. Voit seurata Jälleenmyyntianalyysimallin näytteen Excel-tietojoukon.

1. Olemme raportin luominen Power BI-palvelun työtilassa niin aiemmin luotu työtila tai luo yksi.
   
   ![Luettelo sovellustyötiloista](media/service-report-create-new/power-bi-workspaces2.png)
2. Valitse vasemman siirtymisruudun alaosassa **Nouda tiedot**.
   
   ![Nouda tiedot](media/service-report-create-new/power-bi-get-data3.png)
3. Valitse **Tiedostot** ja siirry sijaintiin, johon tallensit jälleenmyyntianalyysimallin.
   
    ![valitse Tiedostot](media/service-report-create-new/power-bi-select-files.png)
4. Valitse tässä harjoituksessa **Tuonti**.
   
   ![Valitse Tuo](media/service-report-create-new/power-bi-import.png)
5. Kun tietojoukko on tuotu, valitse **Näytä tietojoukko**.
   
   ![Valitse Näytä tietojoukko](media/service-report-create-new/power-bi-view-dataset.png)
6. Tietojoukon tarkastelu itse asiassa avaa raporttieditorin.  Näkyviin tulee tyhjä kangas ja raporttien muokkaustyökalut.
   
   ![raporttieditori](media/service-report-create-new/power-bi-blank-report.png)

> [!TIP]
> Jos tunne raporttien tai haluat kerrata, [raporttieditorin esittely](service-the-report-editor-take-a-tour.md) ennen jatkamista. > 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Viisarimittarin lisääminen raporttiin
Nyt kun tietojoukkomme on tuotu, aloitetaan vastaamaan kysymyksiin.  Markkinointipäällikkö (CMO) haluaa tietää, miten lähellä tämän vuoden myyntitavoitteitamme olemme. Mittari on [hyvä valinta visualisoimaan](visuals/power-bi-report-visualizations.md) tämän tyyppisten tietojen näyttämistä.

1. Valitse Kentät-ruudussa **Myynti**  >  **Tämän vuoden myynti** > **Arvo**.
   
    ![pylväskaavio raporttieditorissa](media/service-report-create-new/power-bi-report-step1.png)
2. Voit muuntaa visualisoinnin mittariksi valitsemalla mittarin mallin ![mittarin kuvakkeesta](media/service-report-create-new/powerbi-gauge-icon.png) **Visualisoinnit**-ruudussa.
   
    ![Mittarin visualisointi raporttieditorissa](media/service-report-create-new/power-bi-report-step2.png)
3. Vedä **Myynti** > **Tämän vuoden myynti** > **Tavoite** kohtaan **Tavoitearvo**. Näyttää siltä, että olemme hyvin lähellä tavoitteitamme.
   
    ![Mittarin visualisointi tavoite tavoitearvona](media/service-report-create-new/power-bi-report-step3.png)
4. Nyt olisi hyvä aika Tallenna raportti.
   
   ![Tiedosto-valikko](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Aluekaavion ja osittajan lisääminen raporttiin
CMO haluaa esittää meille joitakin lisäkysymyksiä vastattavaksi. Hän haluaa tietää, miten tämän vuoden myynti vertautuu viime vuoteen. Ja hän haluaa nähdä havainnot alueittain.

1. Tehdään ensin tilaa pohjalle. Valitse mittari ja siirrä se oikeaan yläkulmaan. Tartu ja vedä jotain kulmaa ja pienennä sitä.
2. Poista mittarin valinta. Valitse Kentät-ruudussa **Myynti** > **Tämän vuoden myynti** > **Arvo** ja valitse **Myynti**  >  **Viime vuoden myynti**.
   
    ![raporttieditori ja mittari sekä palkkikaavio](media/service-report-create-new/power-bi-report-step4.png)
3. Voit muuntaa visualisoinnin aluekaavioksi valitsemalla Aluekaavion malli ![mittarin kuvakkeesta](media/service-report-create-new/power-bi-areachart-icon.png) **Visualisoinnit**-ruudussa.
4. Valitse **Aika**  >  **Jakso** ja lisää se **Akseli**-kohtaan.
   
    ![raporttieditori ja aluekaavio aktiivisena](media/service-report-create-new/power-bi-report-step5.png)
5. Voit lajitella visualisoinnin ajanjakson mukaan valitsemalla kolme pistettä ja valitsemalla **Lajitteluperuste**.
6. Nyt lisätään osittaja. Valitse pohjalta tyhjä alue ja valitse osittaja ![Osittajakuvake-](media/service-report-create-new/power-bi-slicer-icon.png) malli. Tarjoamme nyt pohjalle tyhjän osittajan.
   
    ![raportin pohja](media/service-report-create-new/power-bi-report-step6.png)    
7. Valitse Kentät-ruudussa **Alue** > **Alue**. Siirrä ja muuta osittajan kokoa.
   
    ![Lisää raporttieditorissa alue](media/service-report-create-new/power-bi-report-step7.png)  
8. Osittajan avulla voit etsiä kuviot ja merkitykselliset tiedot alueen mukaan.
   
   ![videon osittajan käyttämisestä](media/service-report-create-new/power-bi-slicer-video2.gif)  

Jatka tietojen tarkastelemista ja visualisointien lisäämistä. Kun olet löytänyt erityisen merkityksellisiä tietoja, [kiinnitä ne raporttinäkymään](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* Lue, miten [kiinnittää visualisointeja raporttinäkymään](service-dashboard-pin-tile-from-report.md)   
* Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

