---
title: Ohjeet ruudun kiinnittämiseksi koontinäyttöön Q&A:sta
description: Ohjeet ruudun kiinnittämiseksi Power BI:n koontinäyttöön Q&A-kysymysruudusta
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 33598798104d88f3044a6689effa54e9b4256274
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285181"
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Ruudun kiinnittäminen koontinäyttöön Q&A:sta
## <a name="how-to-pin-a-tile-from-qa"></a>Ohjeet ruudun kiinnittämiseen Q&A:sta
Q&A on Power BI:n ad-hoc-raportointityökalu. Haluatko löytää tietyn merkityksellisen tiedon? Esitä tietojasi koskeva kysymys, jotta saat vastauksen visualisoinnin muodossa.

Näissä ohjeissa käytetään Power BI -palvelua (app.powerbi.com) koontinäytön avaamiseen, kysymyksen esittämiseen luonnollisella kielellä visualisoinnin luomista varten ja kyseisen visualisoinnin kiinnittämiseen koontinäyttöön. Koontinäytöt eivät ole käytettävissä Power BI Desktopissa. Lisätietoja Q&A:n käyttämisestä muiden Power BI:n työkalujen ja sisältöjen kanssa on artikkelissa [Yleiskatsaus Power BI Q&A:sta](consumer/end-user-q-and-a.md). 

Avaa seuraamista varten [Jälleenmyyntianalyysimalli](sample-retail-analysis.md).


1. Avaa [koontinäyttö](consumer/end-user-dashboards.md), johon on kiinnitetty vähintään yksi ruutu raportista. Kun esität kysymyksen, Power BI etsii vastausta kaikista tietojoukoista, joissa on kiinnitettynä ruutu kyseiseen koontinäyttöön.  Lisätietoja on artikkelissa [Tietojen noutaminen](service-get-data.md).
2. Ala kirjoittaa tiedoista etsittävää asiaa koontinäyttösi ylälaidassa olevaan kysymysruutuun.  
   ![Q&A-kysymysruutu](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Kun kirjoitat esimerkiksi ”viime vuoden myynti kuukauden ja alueen mukaan”...  
   ![kirjoita kysymys](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)

   kysymysruutu antaa ehdotuksia.
4. Jos haluat lisätä kaavion koontinäyttöösi ruutuna, valitse Kiinnitä ![](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) pohjan oikeassa yläkulmassa. Jos koontinäyttö on jaettu kanssasi, et voi kiinnittää visualisointeja.

5. Kiinnitä ruutu aiemmin luotuun koontinäyttöön tai uuteen koontinäyttöön.

   ![Kiinnitä koontinäyttöön -valintaikkuna](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin-to-dashboard.png)

   * Aiemmin luotu koontinäyttö: valitse avattavasta luetteloruudusta koontinäytön nimi. Vaihtoehtosi rajoittuvat vain nykyisessä työtilassasi oleviin koontinäyttöihin.
   * Uusi koontinäyttö: anna uudelle koontinäytölle nimi ja se lisätään nykyiseen työtilaasi.

6. Valitse **Kiinnitä**.

   Onnistumissanoma (oikean yläkulman lähellä) ilmaisee, että visualisointi lisättiin ruutuna koontinäyttöön.  

   ![Kiinnitetty koontinäyttöön](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin.png)
7. Valitse **Siirry koontinäyttöön**, jotta näet uuden ruudun. Siellä voit esimerkiksi [nimetä uudelleen, muuttaa kokoa, lisätä hyperlinkin ja sijoittaa ruudun uudelleen](service-dashboard-edit-tile.md) koontinäytössä.

   ![koontinäyttö ja ruudut](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys
* Kun alat kirjoittaa kysymystä, Q&A alkaa heti hakea parasta vastausta kaikista tietojoukoista, jotka liittyvät nykyiseen koontinäyttöön.  Nykyinen koontinäyttö on yläreunan siirtymispalkissa lueteltu koontinäyttö. Esimerkiksi tämä kysymys esitetään Jälleenmyyntianalyysimalli**Retail Analysis Sample**-koontinäytössä, joka on osa **mihart**-sovellustyötilaa.

  ![navigointipolut](media/service-dashboard-pin-tile-from-q-and-a/power-bi-navbar.png)
* **Mistä Q&A tietää, mitä tietojoukkoja pitää käyttää**?  Q&A pääsee käyttämään kaikkia tietojoukkoja, joista on vähintään yksi visualisointi kiinnitettynä kyseiseen koontinäyttöön.

* **Eikö kysymysruutu näy**? Ota yhteyttä Power BI -järjestelmänvalvojaasi. Järjestelmänvalvoja voi poistaa Q&A:n käytöstä.


## <a name="next-steps"></a>Seuraavat vaiheet
[Nimeäminen uudelleen, koon muuttaminen, hyperlinkin lisääminen ja ruudun sijoittaminen uudelleen](service-dashboard-edit-tile.md)    
[Koontinäytön ruudun näyttäminen kohdistustilassa](consumer/end-user-focus.md)     
[Takaisin Q&A:han Power BI:ssä](consumer/end-user-q-and-a.md)  
Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
