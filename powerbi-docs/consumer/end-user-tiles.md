---
title: Koontinäyttöruudut Power BI -palvelussa kuluttajille
description: Kaikki koontinäyttöruuduista Power BI:ssä kuluttajille. Tämä sisältää ruudut, jotka on luotu SQL Server Reporting Servicesistä (SSRS).
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 1e86403dbdb2972cc83b379efff8bbc17173a4e1
ms.sourcegitcommit: 35d763dfc75c229204d36fd8b35c1e860786b707
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/27/2018
ms.locfileid: "52331892"
---
# <a name="dashboard-tiles-in-power-bi"></a>Koontinäyttöruudut Power BI:ssä
Koontinäytöt ja koontinäyttöruudut ovat Power BI -palvelun ominaisuus eivätkä Power BI Desktopin. Vaikka koontinäyttöruutuja ei voi luoda tai kiinnittää Power BI -mobiilisovelluksessa, [niitä voidaan tarkastella ja jakaa](mobile/mobile-tiles-in-the-mobile-apps.md). 

## <a name="dashboard-tiles"></a>Koontinäytön ruudut
![Power BI -koontinäyttö](./media/end-user-tiles/power-bi-dashboard.png)

Ruutu on tietojen tilannevedos, jonka *suunnittelija* on kiinnittänyt koontinäyttöön. Ruutu voidaan luoda raportista, tietojoukosta, koontinäytöstä, Q&A-kyselyruudusta, Excelistä, SQL Server Reporting Servicesistä (SSRS) ja niin edelleen.  Tämä näyttökuva esittää useita eri ruutuja, jotka on kiinnitetty koontinäyttöön.

Raporteista kiinnitettyjen ruutujen lisäksi *suunnittelijat* voivat lisätä yksittäisiä ruutuja suoraan koontinäyttöön käyttämällä **Lisää ruutu** -komentoa. Yksittäisiä ruutuja ovat tekstiruudut, kuvat, videot, suoratoistotiedot ja verkkosisältö.

Tarvitsetko apua Power BI:n rakenneosien kanssa?  Katso [Power BI - peruskäsitteet](end-user-basic-concepts.md).


## <a name="interacting-with-tiles-on-a-dashboard"></a>Koontinäytön ruutujen käsitteleminen

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Muuta ulkoasua ja toimintaa pitämällä osoitinta ruudun päällä
1. Tuo kolme pistettä näyttöön pitämällä osoitinta ruudun päällä.
   
    ![ruudun kolme pistettä](./media/end-user-tiles/ellipses_new.png)
2. Avaa ruudun toimintovalikko valitsemalla kolme pistettä. Käytettävissä olevat vaihtoehdot vaihtelevat visualisointityypin ja ruudun luontimenetelmän mukaan. Tässä on muutama esimerkki siitä, mitä saatat nähdä.

    - Q&A:n avulla luotu ruutu
   
        ![kolme pistettä -kuvake](./media/end-user-tiles/power-bi-menu1.png)

    - työkirjasta luotu ruutu
   
        ![kolme pistettä -kuvake](./media/end-user-tiles/power-bi-menu2.png)

    - raportista luotu ruutu
   
        ![kolme pistettä -kuvake](./media/end-user-tiles/power-bi-menu3.png)
   
    Täältä voit:
   
   * [avata raportin, jolla tämä ruutu on luotu ](end-user-reports.md) ![raporttikuvake](./media/end-user-tiles/chart-icon.jpg)  
   
   * [avata Q&A-kysymyksen, jolla tämä ruutu on luotu](end-user-reports.md) ![Q&A-kuvake](./media/end-user-tiles/qna-icon.png)  
   

   * [avata työkirjan, jolla tämä ruutu on luotu ](end-user-reports.md) ![laskentataulukkokuvake](./media/end-user-tiles/power-bi-open-worksheet.png)  
    * [tarkastella ruutua kohdistustilassa ](end-user-focus.md) ![kohdistuskuvake](./media/end-user-tiles/fullscreen-icon.jpg)  
     * [suorittaa merkityksellisiä tietoja ](end-user-insights.md) ![merkityksellisiä tietoja -kuvake](./media/end-user-tiles/power-bi-insights.png)
    * [lisätä kommentin ja aloittaa keskustelun](end-user-comment.md)  ![kommenttikuvake](./media/end-user-tiles/comment-icons.png)

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
* Jos ruudun luomiseen käytetty alkuperäinen visualisointi muuttuu, ruutu ei muutu.  Jos esimerkiksi *suunnittelija* kiinnitti raportin viivakaavion ja muutti sitten viivakaavion palkkikaavioksi, koontinäytön ruudussa näkyy edelleen viivakaavio. Tiedot päivittyvät, mutta visualisointityyppi ei.

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojen uudelleenlataus](../refresh-data.md)

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)
