---
title: Power BI -koontinäytön luominen raportista
description: Power BI -koontinäytön luominen raportista
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/02/2018
ms.author: mihart
ms.openlocfilehash: 666938d8d852793b68bb278147c61f077c839ed2
ms.sourcegitcommit: 1a79e48ac820c28c5d0fd05399f49ed22fc74ed7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/19/2018
ms.locfileid: "49435360"
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Power BI -koontinäytön luominen raportista
Olet lukenut [Koontinäytöt Power BI:ssä](service-dashboards.md) ja haluat nyt luoda omasi. Koontinäyttö voidaan luoda monin eri tavoin, esimerkiksi uusi alusta alkaen, raportista, tietojoukosta tai kopioimalla aiemmin luotu koontinäyttö.  

Tämä kaikki voi tuntua vaikealta, kun olet vasta pääsemässä alkuun, joten aloitetaan luomalla nopea ja helppo koontinäyttö kiinnittämällä visualisointeja raportista, joka on jo muodostettu. Kun olet päässyt tämän pikaoppaan loppuun, sinulla on hyvä käsitys koontinäyttöjen ja raporttien välisestä suhteesta, Muokkausnäkymän avaamisesta raporttieditorissa, ruutujen kiinnittämisestä sekä koontinäytön ja raportin välillä siirtymisestä. Pääset edistyneempiin aihealueisiin käyttämällä linkkejä vasemmalla olevasta Sisältöluettelosta tai **Seuraavat vaiheet** -kohdasta artikkelin lopussa.

## <a name="who-can-create-a-dashboard"></a>Kuka voi luoda koontinäytön?
Koontinäytön luominen on **luoja**-toiminto ja edellyttää raportin muokkausoikeuksia. Muokkausoikeudet ovat raportin luojien käytettävissä ja niiden työtovereiden käytössä, joille luoja myöntää käyttöoikeudet. Esimerkiksi jos David luo raportin työtilaABC:ssä ja lisää sitten sinut työtilan jäseneksi, niin sinulla ja Davidilla on muokkausoikeudet. Jos taas raportti on jaettu kanssasi suoraan tai osana [Power BI -sovellusta](service-create-distribute-apps.md) (olet raportin **kuluttaja**), et voi kiinnittää ruutuja koontinäyttöön.

> **HUOMAUTUS**: Koontinäytöt ovat Power BI -palvelun ominaisuus, eivät Power BI Desktopin. Koontinäyttöjä ei voi luoda Power BI -mobiilisovelluksessa, mutta niitä voidaan [tarkastella ja jakaa](consumer/mobile/mobile-apps-view-dashboard.md).
>
> 

![koontinäyttö](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Video: Koontinäytön luominen kiinnittämällä visualisointeja ja kuvia raportista
Katso, kun Amanda luo uuden koontinäytön kiinnittämällä visualisointeja raportista. Kokeile sitten samaa itse Hankinta-analyysimallin avulla noudattamalla videon alapuolella olevia ohjeita.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

### <a name="prerequisites"></a>Edellytykset
Ohjeen seuraamiseksi sinun tulee ladata ”Hankinta-analyysi”-mallin Excel-työkirja ja avata se Power BI -palvelussa (app.powerbi.com).

## <a name="import-a-dataset-with-a-report"></a>Tietojoukon ja raportin tuominen
Tuomme yhden Power BI -mallitietojoukon ja käytämme sitä uuden koontinäytön luomiseen. Käyttämämme malli on Excel-työkirja, jossa on kaksi PowerView-taulukkoa. Kun Power BI tuo työkirjan, se lisää tietojoukon sekä raportin työtilaasi.  Raportti luodaan automaattisesti PowerView-taulukoista.

1. [Valitse tämä linkki](http://go.microsoft.com/fwlink/?LinkId=529784), jonka kautta voit ladata ja tallentaa Hankinta-analyysimallin Excel-tiedoston. On suositeltavaa tallentaa se OneDrive for Businessiin.
2. Avaa Power BI -palvelu (app.powerbi.com) selaimessasi.
3. Valitse **Oma työtila**.
4. Valitse vasemmassa siirtymispalkissa **Nouda tiedot**.

    ![vasen siirtymisruutu](media/service-dashboard-create/power-bi-get-data3.png)
5. Valitse **Tiedostot**.

   ![Hae tiedostot](media/service-dashboard-create/power-bi-select-files.png)
6. Siirry paikkaan, jonne olet tallentanut Hankinta-analyysimallin Excel-tiedoston. Valitse se ja valitse **Yhdistä**.

   ![yhdistä tiedostoihin](media/service-dashboard-create/power-bi-connectnew.png)
7. Valitse tässä harjoituksessa **Tuonti**.

    ![OneDrive for Business -ikkuna](media/service-dashboard-create/power-bi-import.png)
8. Kun näkyviin tulee onnistumisilmoitus, sulje se valitsemalla **x**.

   ![onnistumisilmoitus](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-some-tiles-to-a-dashboard"></a>Avaa raportti ja kiinnitä koontinäyttöön ruutuja
1. Valitse samassa työtilassa **Raportit**-välilehti. Äskettäin tuotu raportti näkyy keltaisella tähdellä merkittynä. Avaa raportti valitsemalla sen nimi.

    ![raportit-välilehti](media/service-dashboard-create/power-bi-reports.png)
2. Raportti avautuu lukunäkymässä. Huomaa, että sen alareunassa on kaksi välilehteä: Alennusanalyysi ja Kulujen yleiskatsaus. Kukin välilehti edustaa yhtä raportin sivua.
    Avaa raportti Muokkausnäkymässä valitsemalla **Muokkaa raporttia**.

    ![raportti Lukunäkymässä](media/service-dashboard-create/power-bi-reading-view.png)
3. Tuo käytettävissä olevat vaihtoehdot esiin pitämällä hiiren osoitinta visualisoinnin päällä. Voit lisätä visualisoinnin koontinäyttöön valitsemalla nastakuvakkeen ![](media/service-dashboard-create/power-bi-pin-icon.png).

    ![hiiren osoitin ruudun kohdalla](media/service-dashboard-create/power-bi-hover.png)
4. Koska olemme luomassa uutta koontinäyttöä, valitse vaihtoehto **Uusi koontinäyttö** ja anna sille nimi.

   ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-create/power-bi-pin-tile.png)
5. Kun valitset **Kiinnitä**-kuvakkeen, Power BI luo uuden koontinäytön nykyisessä työtilassa. Kun näkyviin tulee **Kiinnitetty koontinäyttöön** -ilmoitus, valitse **Siirry koontinäyttöön**. Jos sinua kehotetaan tallentamaan raportti, valitse **Tallenna**.

     ![onnistumisilmoitus](media/service-dashboard-create/power-bi-pin-success.png)
6. Power BI avaa uuden koontinäytön ja siinä on yksi ruutu eli juuri kiinnittämäsi visualisointi.

   ![koontinäyttö, jossa on yksi ruutu](media/service-dashboard-create/power-bi-pinned.png)
7. Jos haluat palata raporttiin, valitse ruutu. Kiinnitä uuteen koontinäyttöön muutamia lisäruutuja. Tällä kertaa, kun **Kiinnitä koontinäyttöön** -ikkuna ilmestyy näkyviin, valitse **Aiemmin luotu koontinäyttö**.  

   ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-create/power-bi-existing-dashboard.png)

## <a name="pin-an-entire-report-page-to-the-dashboard"></a>Koko raporttisivun kiinnittäminen koontinäyttöön
Yhden visualisoinnin kerrallaan kiinnittämisen sijaan voit [kiinnittää koko raporttisivun *tapahtumaruutuna*](service-dashboard-pin-live-tile-from-report.md). Näin se tapahtuu.

1. Valitse raporttieditorissa **Kulujen yleiskatsaus** -välilehti raportin toisen sivun avaamiseksi.

   ![raportti-välilehti](media/service-dashboard-create/power-bi-page-tab.png)

2. Haluat lisätä kaikki nämä visualisoinnit koontinäyttöön.  Valitse valikkorivin oikeassa yläkulmassa **Kiinnitä reaaliaikainen sivu**. Koontinäytössä reaaliaikaiset sivujen ruudut päivittyvät aina, kun sivu päivitetään.

   ![raporttieditorin oikea yläkulma](media/service-dashboard-create/power-bi-pin-live.png)

3. Kun **Kiinnitä koontinäyttöön** -ikkuna ilmestyy näkyviin, valitse **Aiemmin luotu koontinäyttö**.

   ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-create/power-bi-pin-live2.png)

4. Kun näkyviin tulee onnistumisilmoitus, valitse **Siirry koontinäyttöön**. Siellä näkyvät raportista kiinnitetyt ruudut. Alla olevassa esimerkissä olemme kiinnittäneet kaksi ruutua raportin sivulta 1 ja yhden tapahtumaruudun, joka on raportin sivu 2.

   ![koontinäyttö](media/service-dashboard-create/power-bi-dashboard.png)

Onnittelut ensimmäisen koontinäytön luomisen johdosta! Nyt, kun sinulla on koontinäyttö, voit tehdä sen parissa paljon muutakin.  Kokeile jotakin ehdotetuista **Seuraavista vaiheista** alla tai kokeile eri vaihtoehtoja ja tutustu sen käyttöön omaan tahtiisi.   

## <a name="next-steps"></a>Seuraavat vaiheet
* [Ruutujen koon muuttaminen ja siirtäminen](service-dashboard-edit-tile.md)
* [Kaikki koontinäyttöruuduista](service-dashboard-tiles.md)
* [Koontinäytön jakaminen luomalla sovellus](service-create-workspaces.md)
* [Power BI:n peruskäsitteet](service-basic-concepts.md)
* [Vinkkejä laadukkaiden koontinäyttöjen suunnitteluun](service-dashboards-design-tips.md)

Ilmenikö muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
