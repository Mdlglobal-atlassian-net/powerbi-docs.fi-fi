---
title: Power BI -koontinäytön luominen raportista
description: Power BI -koontinäytön luominen raportista
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/17/2019
ms.author: maggies
ms.openlocfilehash: b50d247f54cfe2af4cefbd14b9528b1dfa263acf
ms.sourcegitcommit: bc688fab9288ab68eaa9f54b9b59cacfdf47aa2e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/30/2019
ms.locfileid: "68624311"
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Power BI -koontinäytön luominen raportista
Olet lukenut [Johdatus raporttinäkymiin Power BI:ssä](service-dashboards.md) ja haluat nyt luoda omasi. Koontinäyttö voidaan luoda monin eri tavoin. Voit esimerkiksi luoda uuden alusta alkaen, raportista, tietojoukosta tai kopioimalla aiemmin luotu koontinäyttö.  

Tämä kaikki voi tuntua vaikealta, kun olet vasta pääsemässä alkuun, joten aloitetaan luomalla nopea ja helppo koontinäyttö, joka kiinnittää visualisointeja raportista, joka on jo muodostettu. 

Kun olet päässyt tämän pikaoppaan loppuun, sinulla on hyvä käsitys seuraavista asioista:
- Koontinäyttöjen ja raporttien välinen suhde
- Muokkausnäkymän avaaminen raporttieditorissa
- Ruudun kiinnittäminen 
- Koontinäytön ja raportin välillä siirtyminen 

## <a name="who-can-create-a-dashboard"></a>Kuka voi luoda koontinäytön?
Koontinäytön luominen on *luoja*-toiminto ja edellyttää raportin muokkausoikeuksia. Muokkausoikeudet ovat raportin luojien käytettävissä ja niiden työtovereiden käytössä, joille luoja myöntää käyttöoikeudet. Esimerkiksi jos David luo raportin työtilaABC:ssä ja lisää sitten sinut työtilan jäseneksi, niin sinulla ja Davidilla on muokkausoikeudet. Jos taas raportti on jaettu kanssasi suoraan tai osana [Power BI -sovellusta](service-create-distribute-apps.md) (olet raportin *kuluttaja*), et voi kiinnittää ruutuja koontinäyttöön.
 
![Koontinäyttö](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

> [!NOTE] 
> Koontinäytöt ovat Power BI -palvelun ominaisuus, eivät Power BI Desktopin. Koontinäyttöjä ei voi luoda Power BI -mobiilisovelluksessa, mutta niitä voidaan [tarkastella ja jakaa](consumer/mobile/mobile-apps-view-dashboard.md) siellä.
>
> 

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Video: Koontinäytön luominen kiinnittämällä visualisointeja ja kuvia raportista
Katso, kun Amanda luo uuden koontinäytön kiinnittämällä visualisointeja raportista. Kokeile sitten samaa itse [Tietojoukon ja raportin tuominen](#import-a-dataset-with-a-report) -kohdassa noudattamalla videon alapuolella olevia ohjeita.
    

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Tietojoukon ja raportin tuominen
Tuomme yhden Power BI -mallitietojoukon ja käytämme sitä uuden koontinäytön luomiseen. Käyttämämme malli on Excel-työkirja, jossa on kaksi PowerView-taulukkoa. Kun Power BI tuo työkirjan, se lisää tietojoukon sekä raportin työtilaasi. Raportti luodaan automaattisesti PowerView-taulukoista.

1. Lataa hankinta-analyysimallin [Excel-tiedosto](http://go.microsoft.com/fwlink/?LinkId=529784). On suositeltavaa tallentaa se OneDrive for Businessiin.
2. Avaa Power BI -palvelu (app.powerbi.com) selaimessasi.
3. Valitse vasemmasta siirtymisruudusta **Oma työtila** ja valitse sitten **Nouda tiedot**.

    ![Vasen siirtymisruutu](media/service-dashboard-create/power-bi-get-data3.png)
5. Valitse **Tiedostot**.

   ![Hae tiedostot](media/service-dashboard-create/power-bi-select-files.png)
6. Siirry paikkaan, jonne olet tallentanut Hankinta-analyysimallin Excel-tiedoston. Valitse se ja valitse **Yhdistä**.

   ![Yhdistä tiedostoihin](media/service-dashboard-create/power-bi-connectnew.png)
7. Valitse tässä harjoituksessa **Tuonti**.

    ![OneDrive for Business -ikkuna](media/service-dashboard-create/power-bi-import.png)
8. Kun näkyviin tulee onnistumisilmoitus, sulje se valitsemalla **x**.

   ![Onnistumisilmoitus](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-tiles-to-your-dashboard"></a>Avaa raportti ja kiinnitä koontinäyttöön ruutuja
1. Valitse samassa työtilassa **Raportit**-välilehti ja avaa sitten raportti valitsemalla **Hankinta-analyysimalli**.

    ![Raportit-välilehti](media/service-dashboard-create/power-bi-reports.png) Raportti avautuu lukunäkymässä. Huomaa, että sen alareunassa on kaksi välilehteä: **Alennusanalyysi** ja **Kulujen yleiskatsaus**. Kukin välilehti edustaa yhtä raportin sivua.

2. Avaa raportti Muokkausnäkymässä valitsemalla **Muokkaa raporttia**.

    ![Raportti Lukunäkymässä](media/service-dashboard-create/power-bi-reading-view.png)
3. Tuo käytettävissä olevat vaihtoehdot esiin pitämällä hiiren osoitinta visualisoinnin päällä. Voit lisätä visualisoinnin koontinäyttöön valitsemalla nastakuvakkeen ![Kiinnitä-kuvake](media/service-dashboard-create/power-bi-pin-icon.png).

    ![Hiiren osoitin ruudun kohdalla](media/service-dashboard-create/power-bi-hover.png)
4. Koska olemme luomassa uutta koontinäyttöä, valitse vaihtoehto **Uusi koontinäyttö** ja anna sille nimi.

    ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-create/power-bi-pin-tile.png)
5. Kun valitset **Kiinnitä**-kuvakkeen, Power BI luo uuden koontinäytön nykyisessä työtilassa. Kun näkyviin tulee **Kiinnitetty koontinäyttöön** -ilmoitus, valitse **Siirry koontinäyttöön**. Jos sinua kehotetaan tallentamaan raportti, valitse **Tallenna**.

    ![Onnistumisilmoitus](media/service-dashboard-create/power-bi-pin-success.png)

    Power BI avaa uuden koontinäytön. Siinä on yksi ruutu: juuri kiinnittämäsi visualisointi.

   ![koontinäyttö, jossa on yksi ruutu](media/service-dashboard-create/power-bi-pinned.png)
7. Jos haluat palata raporttiin, valitse ruutu. Kiinnitä uuteen koontinäyttöön muutamia lisäruutuja. Kun **Kiinnitä koontinäyttöön** -ikkuna ilmestyy näkyviin, valitse **Aiemmin luotu koontinäyttö**.  

   ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-create/power-bi-existing-dashboard.png)

## <a name="pin-an-entire-report-page-to-the-dashboard"></a>Koko raporttisivun kiinnittäminen koontinäyttöön
Yhden visualisoinnin kerrallaan kiinnittämisen sijaan voit [kiinnittää koko raporttisivun *tapahtumaruutuna*](service-dashboard-pin-live-tile-from-report.md). Näin se tapahtuu.

1. Valitse raporttieditorissa **Kulujen yleiskatsaus** -välilehti raportin toisen sivun avaamiseksi.

   ![Raportti-välilehti](media/service-dashboard-create/power-bi-page-tab.png)

2. Haluamme, että raportin kaikki visualisoinnit näkyvät koontinäytössä. Valitse valikkorivin oikeassa yläkulmassa **Kiinnitä reaaliaikainen sivu**. Koontinäytössä reaaliaikaiset sivujen ruudut päivittyvät aina, kun sivu päivitetään.

   ![Raporttieditorin oikea yläkulma](media/service-dashboard-create/power-bi-pin-live.png)

3. Kun **Kiinnitä koontinäyttöön** -ikkuna ilmestyy näkyviin, valitse **Aiemmin luotu koontinäyttö**.

   ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-create/power-bi-pin-live2.png)

4. Kun näkyviin tulee onnistumisilmoitus, valitse **Siirry koontinäyttöön**. Siellä näkyvät raportista kiinnitetyt ruudut. Alla olevassa esimerkissä olemme kiinnittäneet kaksi ruutua raportin sivulta 1 ja yhden tapahtumaruudun, joka on raportin sivu 2.

   ![Koontinäyttö](media/service-dashboard-create/power-bi-dashboard.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Onnittelut ensimmäisen koontinäytön luomisen johdosta! Nyt kun sinulla on koontinäyttö, voit tehdä sen parissa paljon muutakin. Seuraa jotakin alla olevista ehdotetuista artikkeleista tai aloita omatoiminen tutustuminen: 

* [Ruutujen koon muuttaminen ja siirtäminen](service-dashboard-edit-tile.md)
* [Kaikki koontinäyttöruuduista](service-dashboard-tiles.md)
* [Koontinäytön jakaminen luomalla sovellus](service-create-workspaces.md)
* [Power BI:n peruskäsitteet](service-basic-concepts.md)
* [Vinkkejä laadukkaiden koontinäyttöjen suunnitteluun](service-dashboards-design-tips.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/).
