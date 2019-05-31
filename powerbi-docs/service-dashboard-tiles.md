---
title: Johdatus raporttinäkymien ruutuihin Power BI -suunnittelijoille
description: Kaikki koontinäyttöruuduista Power BI:ssä. Tämä sisältää ruudut, jotka on luotu SQL Server Reporting Services (SSRS) -raporteista.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: c8b5728c951bc1a25e71da8885997814c5485cd4
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61139003"
---
# <a name="intro-to-dashboard-tiles-for-power-bi-designers"></a>Johdatus raporttinäkymien ruutuihin Power BI -suunnittelijoille

Ruutu on tietojen tilannevedos, joka on kiinnitetty koontinäyttöön. Ruutu voidaan luoda raportista, tietojoukosta, raporttinäkymästä, Q&A-ruudusta, Excelistä, SQL Server Reporting Services (SSRS) -raporteista ja niin edelleen.  Tämä näyttökuva esittää useita eri ruutuja, jotka on kiinnitetty koontinäyttöön.

![Power BI -koontinäyttö](media/service-dashboard-tiles/power-bi-dashboard.png)

Koontinäytöt ja koontinäyttöruudut ovat Power BI -palvelun ominaisuus eivätkä Power BI Desktopin. Raporttinäkymiä ei voi luoda mobiililaitteilla, mutta niitä voi [tarkastella ja jakaa](mobile-apps-view-dashboard.md) niillä.

Kiinnittämisen lisäksi yksittäisiä ruutuja voidaan luoda suoraan raporttinäkymään valitsemalla [Lisää ruutu](service-dashboard-add-widget.md). Yksittäisiä ruutuja ovat tekstiruudut, kuvat, videot, suoratoistotiedot ja verkkosisältö.

Tarvitsetko apua Power BI:n rakenneosien kanssa?  Katso [Power BI - peruskäsitteet](service-basic-concepts.md).

> [!NOTE]
> Jos ruudun luomiseen käytetty alkuperäinen visualisointi muuttuu, ruutu ei muutu.  Jos esimerkiksi kiinnitit raportin viivakaavion ja muutit sitten viivakaavion palkkikaavioksi, koontinäytön ruudussa näkyy edelleen viivakaavio. Tiedot päivittyvät, mutta visualisointityyppi ei.
> 
> 

## <a name="pin-a-tile-from"></a>Kiinnitä ruutu kohteesta...
Voit lisätä (kiinnittää) ruudun koontinäyttöön monella eri tavalla. Ruutuja voi kiinnittää seuraavista kohteista:

* [Power BI:n kysymyksiä ja vastauksia](service-dashboard-pin-tile-from-q-and-a.md)
* [raportti](service-dashboard-pin-tile-from-report.md)
* [toinen koontinäyttö](service-pin-tile-to-another-dashboard.md)
* [OneDrive for Businessin Excel-työkirja](service-dashboard-pin-tile-from-excel.md)
* [Power BI Publisher for Excel](publisher-for-excel.md)
* [Quick Insights (Nopeat merkitykselliset tiedot)](service-insights.md)
* [Reporting Services](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards)

Voit luoda erillisiä ruutuja kuville, muokkausruuduille, videoille, suoratoistotiedoille ja verkkosisällölle suoraan koontinäytössä valitsemalla [Lisää ruutu](service-dashboard-add-widget.md).

  ![Lisää ruutu -kuvake](media/service-dashboard-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>Koontinäytön ruutujen käsitteleminen
### <a name="move-and-resize-a-tile"></a>Ruudun siirtäminen ja koon muuttaminen
Tartu ruutuun ja [siirrä sitä koontinäytössä](service-dashboard-edit-tile.md). Muuta ruudun kokoa pitämällä osoitinta kahvan ![kahva](media/service-dashboard-tiles/resize-handle.jpg) päällä ja valitsemalla se.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Muuta ulkoasua ja toimintaa pitämällä osoitinta ruudun päällä
1. Tuo kolme pistettä näyttöön pitämällä osoitinta ruudun päällä.
   
    ![ruudun kolme pistettä](media/service-dashboard-tiles/ellipses_new.png)
2. Avaa ruudun toimintovalikko valitsemalla kolme pistettä.
   
    ![kolme pistettä -kuvake](media/service-dashboard-tiles/power-bi-tile-menu.png)
   
    Täältä voit:
   
   * [avata raportin, jolla tämä ruutu on luotu ](service-reports.md) ![raporttikuvake](media/service-dashboard-tiles/chart-icon.jpg)  
   
   * [avata laskentataulukon, jolla tämä ruutu on luotu ](service-reports.md) ![laskentataulukkokuvake](media/service-dashboard-tiles/power-bi-open-worksheet.png)  
     
    * [tarkastella tarkastelutilassa ](service-focus-mode.md)![kohdistuskuvake](media/service-dashboard-tiles/fullscreen-icon.jpg)  
     * [viedä ruudussa käytettyjä tietoja](visuals/power-bi-visualization-export-data.md) ![vie tiedot -kuvake](media/service-dashboard-tiles/export-icon.png)
     * [muokata otsikkoa ja alaotsikkoa, lisätä hyperlinkin](service-dashboard-edit-tile.md) ![muokkauskuvake](media/service-dashboard-tiles/pencil-icon.jpg)
     * [suorittaa merkityksellisiä tietoja ](service-insights.md) ![merkityksellisiä tietoja -kuvake](media/service-dashboard-tiles/power-bi-insights.png)
     * [kiinnitä ruudun toiseen koontinäyttöön ](service-pin-tile-to-another-dashboard.md) 
        ![Kiinnitä-kuvake](media/service-dashboard-tiles/pin-icon.jpg)
     * [poistaa ruudun](service-dashboard-edit-tile.md)
     ![Poista-kuvake](media/service-dashboard-tiles/trash-icon.png).
3. Jos haluat sulkea toimintovalikon, valitse kankaan tyhjä alue.

### <a name="select-click-a-tile"></a>Ruudun valitseminen (napsauttaminen)
Kun valitset ruudun, seuraavaksi tapahtuva asia riippuu siitä, miten ruutu on luotu. Jos sillä on [mukautettu linkki](service-dashboard-edit-tile.md), ruudun valitseminen ohjaa sinut kyseiseen linkkiin. Muussa tapauksessa ruudun valitseminen avaa raportin, Excel Online -työkirjan, paikallisen Reporting Services -raportin tai Q&A-kysymyksen, jolla ruutu on luotu.

> [!NOTE]
> Poikkeuksena tähän ovat videoruudut, jotka on luotu suoraan koontinäyttöön **Lisää ruutu** -toiminnolla. (Tällä tavalla luodun) videoruudun valitseminen toistaa videon suoraan koontinäytössä.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

* Jos raporttia, jolla visualisointi on luotu, ei tallennettu, ruudun valitseminen ei tuota mitään toimia.
* Jos ruutu on luotu Excel Online -työkirjasta, tarvitset vähintään työkirjan lukuoikeudet. Muussa tapauksessa työkirjaa ei avata Excel Onlinessa, kun ruutu valitaan.
* Oletetaan, että luot ruudun suoraan raporttinäkymään käyttämällä **Lisää ruutu** -vaihtoehtoa ja määrität sille mukautetun hyperlinkin. Siinä tapauksessa otsikon, alaotsikon tai ruudun valitseminen avaa kyseisen URL-osoitteen. Muussa tapauksessa suoraan raporttinäkymässä luodun kuvan, verkkokoodin tai muokkausruudun ruudun valitseminen ei oletusarvoisesti tuota mitään toimia.
* Jos sinulla ei ole raportin käyttöoikeutta Reporting Servicesissä, Reporting Services -raportista luodun ruudun valitseminen avaa sivun, jossa ilmoitetaan, ettei sinulla ole käyttöoikeutta (rsAccessDenied).
* Jos sinulla ei ole käyttöoikeutta Reporting Services -palvelimen sisältävään verkkoon, Reporting Servicesistä luodun ruudun valitseminen avaa sivun, joka osoittaa, ettei palvelinta löytynyt (HTTP 404). Laitteellasi on oltava verkkoyhteys raporttipalvelimeen raportin tarkastelemista varten.
* Jos ruudun luomiseen käytetty alkuperäinen visualisointi muuttuu, ruutu ei muutu.  Jos esimerkiksi kiinnitit raportin viivakaavion ja muutat sitten viivakaavion palkkikaavioksi, raporttinäkymän ruudussa näkyy edelleen viivakaavio. Tiedot päivittyvät, mutta visualisointityyppi ei.

## <a name="next-steps"></a>Seuraavat vaiheet
[Kortin (suurinumeroiden ruudun) luominen koontinäytölle](power-bi-visualization-card.md)

[Koontinäytöt Power BI:ssä](service-dashboards.md)  

[Tietojen uudelleenlataus](refresh-data.md)

[Power BI:n peruskäsitteet](service-basic-concepts.md)

[Ruudun vieminen Power Pointiin](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Reporting Services -kohteiden kiinnittäminen Power BI -koontinäyttöihin](https://msdn.microsoft.com/library/mt604784.aspx)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

