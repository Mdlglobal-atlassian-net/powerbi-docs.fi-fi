---
title: Raporttien esikatselu Power BI:n raportin muodostimessa
description: Kun luot raportin sivutetun raportin muodostimessa, suosittelemme esikatselemaan raportin usein. Näin voit varmistaa, että raportissa näkyvät haluamasi tiedot.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: ba6b5bdd-d8c6-4aa8-ba32-3a10b11969d4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: afbc31e3ece8bc72ad52bb2fe7c3d871b2f68e1b
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840230"
---
# <a name="previewing-reports-in-power-bi-report-builder"></a>Raporttien esikatselu Power BI:n raportin muodostimessa
  Kun luot raportin sivutetun raportin muodostimessa, suosittelemme esikatselemaan raportin usein. Näin voit varmistaa, että raportissa näkyvät haluamasi tiedot. Esikatsele raportti valitsemalla **Suorita**. Raportti hahmonnetaan esikatselutilassa.  
  
 Raportin muodostimen parantaa esikatselukokemusta käyttämällä muokkausistuntoja, kun yhteys raporttipalvelimeen on muodostettu. Muokkausistunto luo tietovälimuistin ja mahdollistaa välimuistissa olevien tietojoukkojen toistuvan esikatselun raportissa. Muokkausistuntoa ei voi käsitellä suoraan, mutta voit parantaa suorituskykyä, kun ymmärrät, milloin välimuistissa oleva tietojoukko päivitetään ja miksi raportti hahmontaa nopeasti tai hitaasti.  

  
> [!NOTE]  
> Raportin muodostimen ja selaimen esikatseluominaisuuksissa on eroja. Esimerkiksi kalenteriohjausobjekti, joka lisätään raporttiin määrittäessäsi päivämäärä/aika-tyyppisen parametrin, poikkeaa raportin muodostimessa ja selaimessa. 
  
## <a name="improving-preview-performance"></a>Esikatselun suorituskyvyn parantaminen  
 Raporttien luomis- ja päivittämismenetelmät vaikuttavat siihen, kuinka nopeasti raportti hahmonnetaan esikatselussa. Kun esikatselet palvelinviittaukseen pohjautuvaa raporttia ensimmäisen kerran, muokkausistunnon luodaan puolestasi ja raporttia suoritettaessa käytetyt tiedot lisätään tallennettavalle tietovälimuistille. Kun teet raporttiin muutoksia, jotka eivät vaikuta tietoihin, välimuistiin tallennettua kopiota käytetään raportissa. Tämä tarkoittaa sitä, että et näe tietojen muuttuvan aina, kun esikatselet raporttia. Jos haluat uusia tietoja, paina valintanauhan **Päivitä**-painiketta.  
  
 Seuraavat toiminnot aiheuttavat välimuistin päivittämisen ja hidastavat raportin hahmontamista, kun esikatselet raporttia seuraavan kerran:  
  
-   Tietojoukon lisääminen, muuttaminen tai poistaminen. Välimuistissa oleva tietojoukko sisältää kaikki raportin käyttämät tietojoukot. Minkä tahansa tietojoukon muuttaminen tekee välimuistissa olevasta tietojoukosta kelvottoman. Tällaisia muutoksia ovat uudelleennimeäminen, kysely tai tietojoukon kenttien muuttaminen.  
  
    > [!NOTE]  
    >  Jos tietojoukossa on paljon kenttiä, joita et käytä, mieti, voisitko päivittää tietojoukon niin, että kyseiset kentät jätetään huomiotta. Tämä luo uuden muokkausistunnon, ja raportin ensimmäisen esikatselu on hidas, mutta välimuistiin tallennettavan tietojoukon pienempi koko nopeuttaa raporttipalvelimen toimintaa kokonaisuudessaan.  
  
-   Tietolähteen lisääminen, muuttaminen tai poistaminen. Tämä sisältää tietolähteen nimen, ominaisuuksien, tietolaajennuksen tai yhteyden muuttamisen.  
  
-   Raportin käyttämän tietolähteen vaihtaminen.  
  
-   Raportin kielen muuttaminen.  
  
-   Raportin käyttämien kokoonpanojen tai mukautetun koodin muuttaminen.  
  
-   Raportin tai parametrien arvojen sisältämien kyselyparametrien lisääminen, muuttaminen tai poistaminen.  
  
 Raportin asettelun ja tietojen muotoilun muutokset eivät vaikuta välimuistissa olevaan tietojoukkoon. Voit tehdä seuraavat toimet päivittämättä välimuistissa olevaa tietojoukkoa:  
  
-   Taulukkojen, matriisien, kaavioiden tai muiden tietoalueiden lisääminen ja poistaminen.  
  
-   Raportin sarakkeiden lisääminen ja poistaminen. Tietojoukon kentät ovat käytettävissä raportissa. Kenttien lisääminen raporttiin tai poistaminen siitä ei vaikuta tietojoukkoon.  
  
-   Taulukoissa ja matriiseissa olevien kenttien järjestyksen muuttaminen.  
  
-   Rivi- ja sarakeryhmien lisääminen, muuttaminen ja poistaminen.  
  
-   Kenttien tietoarvojen muotoilun lisääminen, muuttaminen ja poistaminen.  
  
-   Kuvien, viivojen tai tekstiruutujen lisääminen, muuttaminen ja poistaminen.  
  
-   Sivunvaihtojen muuttaminen.  
  
Muokkausistunto luodaan, kun esikatselet raporttia ensimmäistä kertaa. Muokkausistunto kestää oletuksena 7 200 sekuntia (2 tuntia). Kahden tunnin ajastus nollataan aina, kun raportti suoritetaan. Muokkausistunnon vanhentuessa välimuisti tyhjennetään. Jos muokkausistunto vanhentuu, uusi istunto luodaan automaattisesti, kun esikatselet raporttia seuraavan kerran.
  
Oletusarvoisesti välimuisti voi sisältää enintään viisi tietojoukkoa kerrallaan. Raportissa saattaa olla tätä enemmän tietoa, jos käytät useita eri parametriarvojen yhdistelmiä. Tämä edellyttää välimuistin päivittämistä ja sitä, että raportti hahmonnetaan hitaammin seuraavan esikatselun aikana. 
  
## <a name="concurrency-of-report-updates"></a>Raporttipäivitysten samanaikaisuus  
Raportteja esikatsellaan usein osana päivittämistä ja raportin tallentamista Power BI -palveluun. Kun päivität raporttia, on mahdollista, että joku muu päivittää ja tallentaa raporttia samanaikaisesti. Tallennettava raportti on raportin viimeisin versio, joka on saatavana tulevaa tarkastelua ja päivittämistä varten. Tämä tarkoittaa sitä, että esikatselemasi raportin versio ei välttämättä sama versio, jonka avaa seuraavan kerran. Voit halutessasi tallentaa raportin uudella nimellä raportin muodostimen **Tallenna nimellä** -valikkovaihtoehdolla.  
  
## <a name="external-report-items"></a>Ulkoiset raporttikohteet  
 Raportti voi sisältää ulkoisia kohteita, esimerkiksi kuvia, jotka on tallennettu raportista erikseen. Koska kohteet on tallennettu erikseen, ne saatetaan poistaa tai siirtää eri paikkaan. Jos näin käy, raportin esikatselu voi epäonnistua. Voit joko päivittää kohteen päivitetyn sijainnin raporttiin tai, jos kohde poistettiin, korvata sen toisella kohteella. Voit myös poistaa raportista viittauksen kohteeseen.  
  
## <a name="next-steps"></a>Seuraavat vaiheet

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)
  
