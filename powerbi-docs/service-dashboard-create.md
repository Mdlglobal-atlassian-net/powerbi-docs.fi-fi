---
title: Power BI -koontinäytön luominen raportista
description: Power BI -koontinäytön luominen raportista
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/17/2019
ms.author: maggies
ms.openlocfilehash: d67e7acf4309595e8bccac86119ea38f1a97797f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2019
ms.locfileid: "73853419"
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Power BI -koontinäytön luominen raportista
Olet lukenut [Johdatus raporttinäkymiin Power BI:ssä](service-dashboards.md) ja haluat nyt luoda omasi. Koontinäyttö voidaan luoda monin eri tavoin. Voit esimerkiksi luoda uuden alusta alkaen, raportista, tietojoukosta tai kopioimalla aiemmin luotu koontinäyttö.  

Aloitetaan luomalla nopea ja helppo koontinäyttö, joka kiinnittää visualisointeja raportista, joka on jo muodostettu. 

Kun olet päässyt tämän artikkelin loppuun, sinulla on hyvä käsitys seuraavista asioista:
- Koontinäyttöjen ja raporttien välinen suhde
- Muokkausnäkymän avaaminen raporttieditorissa
- Ruudun kiinnittäminen 
- Koontinäytön ja raportin välillä siirtyminen 
 
![Koontinäyttö](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

> [!NOTE] 
> Koontinäytöt ovat Power BI -palvelun ominaisuus, eivät Power BI Desktopin. Vaikka raporttinäkymiä ei luoda Power BI -mobiilisovelluksilla, niitä voi [tarkastella ja jakaa](consumer/mobile/mobile-apps-view-dashboard.md) niillä.
>
> 

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Video: Koontinäytön luominen kiinnittämällä visualisointeja ja kuvia raportista
Katso, kun Amanda luo uuden koontinäytön kiinnittämällä visualisointeja raportista. Kokeile sitten samaa itse [Tietojoukon ja raportin tuominen](#import-a-dataset-with-a-report) -kohdassa noudattamalla seuraavan osion ohjeita.
    

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Tietojoukon ja raportin tuominen
Näissä vaiheittaisissa ohjeissa tuomme yhden Power BI -mallitietojoukon ja käytämme sitä uuden koontinäytön luomiseen. Käyttämämme malli on Excel-työkirja, jossa on kaksi PowerView-taulukkoa. Kun Power BI tuo työkirjan, se lisää tietojoukon sekä raportin työtilaasi. Raportti luodaan automaattisesti PowerView-taulukoista.

1. Lataa [hankinta-analyysimallin](https://go.microsoft.com/fwlink/?LinkId=529784) Excel-tiedosto. On suositeltavaa tallentaa se OneDrive for Businessiin.
2. Avaa Power BI -palvelu (app.powerbi.com) selaimessasi.
3. Valitse siirtymisruudusta **Oma työtila** ja valitse sitten **Nouda tiedot**.

    ![siirtymisruutu](media/service-dashboard-create/power-bi-get-data-new-look.png)
5. Valitse **Hanki** kohdassa **Tiedostot**.

   ![Hae tiedostot](media/service-dashboard-create/power-bi-select-files.png)
6. Siirry paikkaan, jonne olet tallentanut Hankinta-analyysimallin Excel-tiedoston. Valitse se ja valitse **Yhdistä**.

   ![Yhdistä tiedostoihin](media/service-dashboard-create/power-bi-connectnew.png)
7. Valitse tässä harjoituksessa **Tuonti**.

    ![OneDrive for Business -ikkuna](media/service-dashboard-create/power-bi-import.png)
8. Kun näkyviin tulee onnistumisilmoitus, sulje se valitsemalla **x**.

   ![Onnistumisilmoitus](media/service-dashboard-create/power-bi-view-datasetnew.png)

> [!TIP]
> Tiesitkö? Voit kaventaa siirtymisruutua valitsemalla yläreunassa olevan kuvakkeen, jossa on kolme riviä ![Siirtymisruudun näytä tai piilota -kuvake](media/service-dashboard-create/power-bi-new-look-hide-nav-pane.png). Näin saat enemmän tilaa itse raportille.

### <a name="open-the-report-and-pin-tiles-to-your-dashboard"></a>Avaa raportti ja kiinnitä koontinäyttöön ruutuja
1. Valitse samassa työtilassa **Raportit**-välilehti ja avaa sitten raportti valitsemalla **Hankinta-analyysimalli**.

    ![Raportit-välilehti](media/service-dashboard-create/power-bi-reports.png) Raportti avautuu lukunäkymässä. Huomaathan, että sen alareunassa on kaksi välilehteä: **Alennusanalyysi** ja **Kulujen yleiskatsaus**. Kukin välilehti edustaa yhtä raportin sivua.

2. Avaa raportti Muokkausnäkymässä valitsemalla **Lisää asetuksia (...)**  > **Muokkaa raporttia**.

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

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/).
