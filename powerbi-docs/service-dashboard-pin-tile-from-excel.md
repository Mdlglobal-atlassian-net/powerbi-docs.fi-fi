---
title: Ruudun kiinnittäminen Power BI -raporttinäkymään Excelistä
description: Kiinnitä ruutu Power BI -raporttinäkymään Excelistä OneDrive for Businessissa. Alueiden, kaavioiden ja taulukoiden kiinnittäminen
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: l8JoB7w0zJA
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: d0f258af383327fb25c8f0e896677bbd19eca6c4
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "73877419"
---
# <a name="pin-a-tile-to-a-power-bi-dashboard-from-excel"></a>Ruudun kiinnittäminen Power BI -raporttinäkymään Excelistä
Ennen kuin voit kiinnittää ruudun Excel-työkirjasta, yhdistät kyseisen työkirjan Power BI -palveluun (app.powerbi.com). Työkirjan yhdistäminen tuo lähinnä tämän työkirjan linkitetyn vain luku -version Power BI -palveluun, ja voit näin kiinnittää alueita raporttinäkymiin. Voit kiinnittää jopa kokonaisen laskentataulukon raporttinäkymään.  
Jos työkirja on jaettu kanssasi, voit tarkastella omistajan kiinnittämiä ruutuja, mutta et voi luoda raporttinäkymän ruutuja itse. 

Lue lisää siitä, miten Excel ja Power BI toimivat yhdessä, artikkelista [Tietojen noutaminen Excel-työkirjatiedostoista](https://go.microsoft.com/fwlink/?LinkID=521962).

Seuraavassa videossa esitetään useita tapoja tuoda tietoja Excel-työkirjoista ja yhdistää tietoja niihin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/l8JoB7w0zJA" frameborder="0" allowfullscreen></iframe>

## <a name="connect-your-excel-workbook-from-onedrive-for-business-to-power-bi"></a>Excel-työkirjan yhdistäminen OneDrive for Businessista Power BI:hin
Kun valitset **Yhdistä**, työkirjasi näkyy Power BI:ssä aivan samalla tavalla kuin se näkyisi Excel Onlinessa. Mutta toisin kuin Excel Onlinessa, käytettävissäsi on käteviä ominaisuuksia, joilla voit kiinnittää laskentataulukoiden elementtejä suoraan raporttinäkymiin.

Työkirjaa ei voi muokata Power BI:ssä. Jos muutoksia on tehtävä, voit valita kynäkuvakkeen työtilasi **Työkirjat**-välilehdestä ja valita sitten työkirjan muokkaamisen joko Excel Onlinessa tai tietokoneesi Excelissä. Tekemäsi muutokset tallennetaan työkirjaan OneDrivessa.

1. Lataa työkirja OneDrive for Businessiin.

2. [Yhdistä työkirjaan](service-excel-workbook-files.md) Power BI:ssä valitsemalla **Nouda tiedot > Tiedostot > OneDrive – Business** ja siirtymällä Excel-tiedoston tallennuspaikkaan. Valitse tiedosto ja sitten **Yhdistä > Yhdistä**.

    ![OneDrive for Business -valintaikkuna](media/service-dashboard-pin-tile-from-excel/power-bi-connect.png)

3. Power BI:ssä työkirja lisätään työtilasi **Työkirjat**-välilehteen.  ![Työkirjakuvake](media/service-dashboard-pin-tile-from-excel/pbi_workbookicon.png) ilmaisee, että kyseessä on Excel-työkirja ja keltainen tähti osoittaa, että se on uusi.
    
    ![Työkirjat-välilehti](media/service-dashboard-pin-tile-from-excel/power-bi-workbooks.png)
4. Avaa työkirja Power BI:ssä valitsemalla työkirjan nimi.

    Työkirjaan Power BI:ssä tekemiäsi muutoksia ei tallenneta, eivätkä ne vaikuta alkuperäiseen työkirjaan OneDrive for Businessissa. Jos lajittelet, suodatat tai muutat arvoja Power BI:ssä, kyseisiä muutoksia ei voi tallentaa tai kiinnittää. Jos sinun on tehtävä muutoksia, jotka tallennetaan, avaa työkirja Excel Onlinessa tai Excelissä muokkaamista varten valitsemalla **Muokkaa** oikeasta yläkulmasta. Näin tehtyjen muutosten päivittyminen raporttinäkymän ruutuihin voi kestää muutamia minuutteja.
   
    ![Excel Online Power BI:ssä](media/service-dashboard-pin-tile-from-excel/power-bi-opened.png)

## <a name="pin-a-range-of-cells-to-a-dashboard"></a>Solualueen kiinnittäminen raporttinäkymään
Uusi [raporttinäkymän ruutu](consumer/end-user-tiles.md) voidaan lisätä Excel-työkirjasta Power BI:ssä. Alueita voidaan kiinnittää Excel-työkirjoista, jotka on tallennettu OneDrive for Businessiin tai toiseen ryhmän jakamaan tiedostokirjastoon. Alueet voivat sisältää tietoja, kaavioita, taulukoita, pivot-taulukoita, pivot-kaavioita ja muita Excel-osia.

1. Korosta solut, jotka haluat kiinnittää raporttinäkymään.
   
    ![Solujen valitseminen Excel-työkirjassa](media/service-dashboard-pin-tile-from-excel/pbi_selectrange.png)
2. Valitse Kiinnitä ![kiinnitä-kuvake](media/service-dashboard-pin-tile-from-excel/pbi_pintile_small.png) kuvake. 
3. Kiinnitä ruutu aiemmin luotuun raporttinäkymään tai uuteen raporttinäkymään. 
   
   * Aiemmin luotu koontinäyttö: valitse avattavasta luetteloruudusta koontinäytön nimi.
   * Uusi raporttinäkymä: anna nimi uudelle raporttinäkymälle.
   
     ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-pin-tile-from-excel/pbi_dashdialog1.png)
4. Valitse **Kiinnitä**. Onnistumissanoma (lähellä oikeaa yläkulmaa) ilmaisee, että alue lisättiin ruutuna raporttinäkymään. 
   
    ![Kiinnitetty koontinäyttöön -valintaikkuna](media/service-dashboard-pin-tile-from-excel/power-bi-go-to-dashboard.png)
5. Valitse **Siirry raporttinäkymään**. Täällä kiinnitetty visualisointi voidaan [nimetä uudelleen, linkittää ja siirtää ja sen kokoa voidaan muuttaa](service-dashboard-edit-tile.md). Oletuksena kiinnitetyn ruudun valitseminen avaa työkirjan Power BI:ssä.

## <a name="pin-an-entire-table-or-pivottable-to-a-dashboard"></a>Koko taulukon tai Pivot-taulukon kiinnittäminen raporttinäkymään
Noudata edellä olevia ohjeita, mutta valitse solualueen sijaan koko taulukko tai Pivot-taulukko.

Jos halua kiinnittää taulukon, valitse koko taulukon alue ja varmista, että otsikot sisältyvät alueeseen.  Jos haluat kiinnittää Pivot-taulukon, sisällytä kaikki Pivot-taulukon näkyvät osat mahdollisesti käytetyt suodattimet mukaan lukien.

 ![solujen valitseminen](media/service-dashboard-pin-tile-from-excel/pbi_selecttable.png)

Taulukosta tai Pivot-taulukosta luotu ruutu näyttää koko taulukon.  Jos lisäät, poistat tai suodatat alkuperäisen työkirjan rivejä tai sarakkeita, myös ne lisätään, poistetaan tai suodatetaan ruudussa.

## <a name="view-the-workbook-linked-to-the-tile"></a>Ruutuun linkitetyn työkirjan tarkasteleminen
Työkirjan ruudun valitseminen avaa linkitetyn työkirjan Power BI:ssä. Koska työkirjatiedosto sijaitsee omistajan OneDrive for Businessissa, työkirjan tarkasteleminen edellyttää, että sinulla on työkirjan lukuoikeudet. Jos sinulla ei ole oikeuksia, saat virheilmoituksen.  

 ![video](media/service-dashboard-pin-tile-from-excel/pin-from-excel.gif)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
Ominaisuudet, joita ei tueta: Power BI käyttää Excel Servicesiä työkirjan ruutujen noutamiseen. Näin ollen koska joitakin Excelin ominaisuuksia ei tueta Excel Servicesin REST-ohjelmointirajapinnassa, ne eivät näy Power BI:n ruuduissa. Esimerkkejä: sparkline-kaaviot, kuvakejoukon ehdollinen muotoilu ja aikaosittajat. Täydellinen luettelo ominaisuuksista, joita ei tueta, on artikkelissa [Excel Servicesin REST-ohjelmointirajapinnan ominaisuudet, joita ei tueta](https://msdn.microsoft.com/library/office/ff394477.aspx)

## <a name="next-steps"></a>Seuraavat vaiheet
[Excel-työkirjaan linkittävän raporttinäkymän jakaminen](service-share-dashboard-that-links-to-excel-onedrive.md)

[Tietojen noutaminen Excel-työkirjoista](service-excel-workbook-files.md)

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)

