---
title: Koontinäyttöruudut Power BI -palvelussa
description: Kaikki koontinäyttöruuduista Power BI:ssä. Tämä sisältää ruudut, jotka on luotu SQL Server Reporting Servicesistä (SSRS).
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/21/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: f0ff1d9a49e0566119df2c790ad618700c9a9ca3
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565448"
---
# <a name="dashboard-tiles-in-power-bi"></a>Koontinäyttöruudut Power BI:ssä
Koontinäytöt ja koontinäyttöruudut ovat Power BI -palvelun ominaisuus eivätkä Power BI Desktopin. Vaikka koontinäyttöruutuja ei voi luoda tai kiinnittää Power BI -mobiilisovelluksessa, [niitä voidaan tarkastella ja jakaa](mobile/mobile-tiles-in-the-mobile-apps.md). Power BI -mobiilisovelluksessa voit [lisätä kuvia koontinäyttöösi iPhone-sovelluksella](mobile/mobile-iphone-app-get-started.md).

## <a name="dashboard-tiles"></a>Koontinäytön ruudut
![Power BI -koontinäyttö](./media/end-user-tiles/power-bi-dashboard.png)

Ruutu on tietojen tilannevedos, joka on kiinnitetty koontinäyttöön. Ruutu voidaan luoda raportista, tietojoukosta, koontinäytöstä, Q&A-ruudusta, Excelistä, SQL Server Reporting Servicesistä (SSRS) ja niin edelleen.  Tämä näyttökuva esittää useita eri ruutuja, jotka on kiinnitetty koontinäyttöön.

Kiinnittämisen lisäksi yksittäisiä ruutuja voidaan luoda suoraan koontinäyttöön valitsemalla [Lisää ruutu](../service-dashboard-add-widget.md). Yksittäisiä ruutuja ovat tekstiruudut, kuvat, videot, suoratoistotiedot ja verkkosisältö.

Tarvitsetko apua Power BI:n rakenneosien kanssa?  Katso [Power BI - peruskäsitteet](end-user-basic-concepts.md).

> [!NOTE]
> Jos ruudun luomiseen käytetty alkuperäinen visualisointi muuttuu, ruutu ei muutu.  Jos esimerkiksi kiinnitit raportin viivakaavion ja muutit sitten viivakaavion palkkikaavioksi, koontinäytön ruudussa näkyy edelleen viivakaavio. Tiedot päivittyvät, mutta visualisointityyppi ei.
> 
> 

## <a name="pin-a-tile-from"></a>Kiinnitä ruutu kohteesta...
Voit lisätä (kiinnittää) ruudun koontinäyttöön monella eri tavalla. Ruutuja voi kiinnittää seuraavista kohteista:

* [Power BI:n kysymyksiä ja vastauksia](../service-dashboard-pin-tile-from-q-and-a.md)
* [raportti](../service-dashboard-pin-tile-from-report.md)
* [toinen koontinäyttö](../service-pin-tile-to-another-dashboard.md)
* [OneDrive for Businessin Excel-työkirja](../service-dashboard-pin-tile-from-excel.md)
* [Power BI Publisher for Excel](../publisher-for-excel.md)
* [Nopeat merkitykselliset tiedot](end-user-insights.md)
* [SSRS](https://msdn.microsoft.com/library/mt604784.aspx)

Voit luoda erillisiä ruutuja kuville, muokkausruuduille, videoille, suoratoistotiedoille ja verkkosisällölle suoraan koontinäytössä valitsemalla [Lisää ruutu](../service-dashboard-add-widget.md).

  ![Lisää ruutu -kuvake](./media/end-user-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>Koontinäytön ruutujen käsitteleminen
### <a name="move-and-resize-a-tile"></a>Ruudun siirtäminen ja koon muuttaminen
Tartu ruutuun ja [siirrä sitä koontinäytössä](../service-dashboard-edit-tile.md). Muuta ruudun kokoa pitämällä osoitinta kahvan ![kahva](./media/end-user-tiles/resize-handle.jpg) päällä ja valitsemalla se.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Muuta ulkoasua ja toimintaa pitämällä osoitinta ruudun päällä
1. Tuo kolme pistettä näyttöön pitämällä osoitinta ruudun päällä.
   
    ![ruudun kolme pistettä](./media/end-user-tiles/ellipses_new.png)
2. Avaa ruudun toimintovalikko valitsemalla kolme pistettä.
   
    ![kolme pistettä -kuvake](./media/end-user-tiles/power-bi-tile-menu.png)
   
    Täältä voit:
   
   * [avata raportin, jolla tämä ruutu on luotu ](end-user-reports.md) ![raporttikuvake](./media/end-user-tiles/chart-icon.jpg)  
   
   * [avata laskentataulukon, jolla tämä ruutu on luotu ](end-user-reports.md) ![laskentataulukkokuvake](./media/end-user-tiles/power-bi-open-worksheet.png)  
     
    * [tarkastella kohdistustilassa ](end-user-focus.md) ![kohdistuskuvake](./media/end-user-tiles/fullscreen-icon.jpg)  
     * [viedä ruudussa käytettyjä tietoja](end-user-export-data.md) ![vie tiedot -kuvake](./media/end-user-tiles/export-icon.png)
     * [muokata otsikkoa ja alaotsikkoa, lisätä hyperlinkin](../service-dashboard-edit-tile.md) ![muokkauskuvake](./media/end-user-tiles/pencil-icon.jpg)
     * [suorittaa merkityksellisiä tietoja ](end-user-insights.md) ![merkityksellisiä tietoja -kuvake](./media/end-user-tiles/power-bi-insights.png)
     * [kiinnitä ruudun toiseen koontinäyttöön ](../service-pin-tile-to-another-dashboard.md) 
        ![Kiinnitä-kuvake](./media/end-user-tiles/pin-icon.jpg)
     * [poistaa ruudun](../service-dashboard-edit-tile.md)
     ![Poista-kuvake](./media/end-user-tiles/trash-icon.png).
3. Jos haluat sulkea toimintovalikon, valitse kankaan tyhjä alue.

### <a name="select-click-a-tile"></a>Ruudun valitseminen (napsauttaminen)
Kun valitset ruudun, seuraavaksi tapahtuva asia riippuu siitä, miten ruutu on luotu ja onko sillä [mukautettu linkki](../service-dashboard-edit-tile.md). Jos sillä on mukautettu linkki, ruudun valitseminen ohjaa sinut kyseiseen linkkiin. Muussa tapauksessa ruudun valitseminen avaa raportin, Excel Online -työkirjan, SSRS-raportin, joka on paikallinen, tai kysymysten ja vastausten kysymyksen, jolla ruutu on luotu.

> [!NOTE]
> Poikkeuksena tähän ovat videoruudut, jotka on luotu suoraan koontinäyttöön **Lisää ruutu** -toiminnolla. (Tällä tavalla luodun) videoruudun valitseminen toistaa videon suoraan koontinäytössä.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Jos raporttia, jolla visualisointi on luotu, ei tallennettu, ruudun valitseminen ei tuota mitään toimia.
* Jos ruudun luotiin Excel Onlinen työkirjasta eikä sinulla ole vähintään lukuoikeuksia kyseiseen työkirjaan, ruudun valitseminen ei avaa työkirjaa Excel Onlinessa.
* Jos suoraan koontinäyttöön **Lisää ruutu** -toiminnolla luoduissa ruuduissa on määritetty mukautettu hyperlinkki, otsikon, alaotsikon tai ruudun valitseminen avaa kyseisen URL-osoitteen.  Muussa tapauksessa jonkin näiden suoraan koontinäytössä luotujen kuvan, verkkokoodin tai muokkausruudun ruudun valitseminen ei oletusarvoisesti tuota mitään toimia.
* Jos sinulla ei ole raportin käyttöoikeutta SSRS:ssä, SSRS:ssä luodun ruudun valitseminen avaa sivun, jossa ilmoitetaan, ettei sinulla ole käyttöoikeutta (rsAccessDenied).
* Jos sinulla ei ole käyttöoikeutta SSRS-palvelimen sisältävään verkkoon, SSRS:ssä luodun ruudun valitseminen avaa sivun, joka osoittaa, ettei palvelinta ei löytynyt (HTTP 404). Laitteellasi on oltava verkkoyhteys raporttipalvelimeen raportin tarkastelemiseksi.
* Jos ruudun luomiseen käytetty alkuperäinen visualisointi muuttuu, ruutu ei muutu.  Jos esimerkiksi kiinnitit raportin viivakaavion ja muutat sitten viivakaavion palkkikaavioksi, koontinäytön ruudussa näkyy edelleen viivakaavio. Tiedot päivittyvät, mutta visualisointityyppi ei.

## <a name="next-steps"></a>Seuraavat vaiheet
[Kortin (suurinumeroiden ruudun) luominen koontinäytölle](../visuals/power-bi-visualization-card.md)

[Koontinäytöt Power BI:ssä](end-user-dashboards.md)  

[Tietojen uudelleenlataus](../refresh-data.md)

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)

[Ruudun vieminen Power Pointiin](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Reporting Services -kohteiden kiinnittäminen Power BI -koontinäyttöihin](https://msdn.microsoft.com/library/mt604784.aspx)

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
