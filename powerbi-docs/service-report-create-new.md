---
title: Raportin luominen tietojoukosta
description: Power BI -raportin luominen tietojoukosta.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: c3f30206a01dce9cf9fd3ce0600b46b401df2b1f
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/06/2020
ms.locfileid: "73871760"
---
# <a name="create-a-report-in-the-power-bi-service-by-importing-a-dataset"></a>Raportin luominen Power BI -palvelussa tuomalla tietojoukko
Olet lukenut [Power BI -raportit](consumer/end-user-reports.md) ja haluat nyt luoda omasi. Voit luoda raportin eri tavoin. Tässä artikkelissa aloitamme luomalla perusraportin Excel-tietojoukosta Power BI -palvelussa. Kun ymmärrät raportin luomisen perusteet, lopussa olevat [Seuraavat vaiheet](#next-steps) vievät sinut monimutkaisempia raportteja koskevaan aiheisiin.  

## <a name="prerequisites"></a>Edellytykset
- [Rekisteröidy Power BI -palveluun](service-self-service-signup-for-power-bi.md). Katso raporttien luominen Power BI Desktopissa kohdasta [Työpöydän raporttinäkymä](desktop-report-view.md). 
- [Lataa jälleenmyyjän analyysin Excel-tietojoukkoesimerkki](https://go.microsoft.com/fwlink/?LinkId=529778) ja tallenna se OneDrive for Businessiin tai paikallisesti.

## <a name="import-the-dataset"></a>Tuo tietojoukko
Tämä raporttien luontimenetelmä alkaa tietojoukosta ja tyhjästä raporttipohjasta. Voit seurata mukana tarkastelemalla Excelin Jälleenmyyntianalyysimalli-tietojoukkoa.

1. Luomme raportin Power BI -palvelun työtilassa, joten valitse aiemmin luotu työtila tai luo uusi.
   
   ![Luettelo työtiloista](media/service-report-create-new/power-bi-workspaces2.png)
2. Valitse siirtymisruudun alareunasta **Nouda tiedot**.
   
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
> Jos et tunne raporttien muokkauspohjaa tai haluat päivittää tietojasi, [katso esittely raporttieditorista ](service-the-report-editor-take-a-tour.md) ennen jatkamista.> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Viisarimittarin lisääminen raporttiin
Nyt kun tietojoukkomme on tuotu, aloitetaan vastaamaan kysymyksiin.  Markkinointipäällikkö (CMO) haluaa tietää, miten lähellä tämän vuoden myyntitavoitteitamme olemme. Mittari on [hyvä valinta visualisoimaan](visuals/power-bi-report-visualizations.md) tämän tyyppisten tietojen näyttämistä.

1. Valitse Kentät-ruudussa **Myynti** > **Tämän vuoden myynti** > **Arvo**.
   
    ![pylväskaavio raporttieditorissa](media/service-report-create-new/power-bi-report-step1.png)
2. Voit muuntaa visualisoinnin mittariksi valitsemalla mittarin mallin ![mittarin kuvakkeesta](media/service-report-create-new/powerbi-gauge-icon.png)**Visualisoinnit**-ruudussa.
   
    ![Mittarin visualisointi raporttieditorissa](media/service-report-create-new/power-bi-report-step2.png)
3. Vedä **Myynti** > **Tämän vuoden myynti** > **Tavoite** kohtaan **Tavoitearvo**. Näyttää siltä, että olemme hyvin lähellä tavoitteitamme.
   
    ![Mittarin visualisointi tavoite tavoitearvona](media/service-report-create-new/power-bi-report-step3.png)
4. Nyt olisi hyvä aika tallentaa raporttisi.
   
   ![Tiedosto-valikko](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Aluekaavion ja osittajan lisääminen raporttiin
CMO haluaa esittää meille joitakin lisäkysymyksiä vastattavaksi. Hän haluaa tietää, miten tämän vuoden myynti vertautuu viime vuoteen. Ja hän haluaa nähdä havainnot alueittain.

1. Tehdään ensin tilaa pohjalle. Valitse mittari ja siirrä se oikeaan yläkulmaan. Tartu ja vedä jotain kulmaa ja pienennä sitä.
2. Poista mittarin valinta. Valitse Kentät-ruudussa **Myynti** > **Tämän vuoden myynti** > **Arvo** ja valitse **Myynti** > **Viime vuoden myynti**.
   
    ![raporttieditori ja mittari sekä palkkikaavio](media/service-report-create-new/power-bi-report-step4.png)
3. Voit muuntaa visualisoinnin aluekaavioksi valitsemalla Aluekaavion malli ![mittarin kuvakkeesta](media/service-report-create-new/power-bi-areachart-icon.png)**Visualisoinnit**-ruudussa.
4. Valitse **Aika** > **Jakso** ja lisää se **Akseli**-kohtaan.
   
    ![raporttieditori ja aluekaavio aktiivisena](media/service-report-create-new/power-bi-report-step5.png)
5. Voit lajitella visualisoinnin ajanjakson mukaan valitsemalla kolme pistettä ja valitsemalla **Lajitteluperuste**.
6. Nyt lisätään osittaja. Valitse pohjalta tyhjä alue ja valitse osittaja ![Osittajakuvake-](media/service-report-create-new/power-bi-slicer-icon.png) malli. Pohjalla on nyt tyhjä osittaja.
   
    ![raportin pohja](media/service-report-create-new/power-bi-report-step6.png)    
7. Valitse Kentät-ruudussa **Alue** > **Alue**. Siirrä ja muuta osittajan kokoa.
   
    ![Lisää raporttieditorissa alue](media/service-report-create-new/power-bi-report-step7.png)  
8. Osittajan avulla voit etsiä kuviot ja merkitykselliset tiedot alueen mukaan.
   
   ![videon osittajan käyttämisestä](media/service-report-create-new/power-bi-slicer-video2.gif)  

Jatka tietojen tarkastelemista ja visualisointien lisäämistä. Kun olet löytänyt erityisen merkityksellisiä tietoja, [kiinnitä ne raporttinäkymään](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Seuraavat vaiheet

* Lue, miten [kiinnittää visualisointeja raporttinäkymään](service-dashboard-pin-tile-from-report.md)   
* Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

