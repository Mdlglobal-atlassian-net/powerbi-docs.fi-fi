---
title: 'Opetusohjelma: verkkosivun tietojen tuominen ja analysointi Power BI Desktopissa'
description: 'Opetusohjelma: verkkosivun tietojen tuominen ja analysointi Power BI Desktopissa'
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 9650f0be6ca795fdea3395721c0eb02e80464821
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
---
# <a name="analyzing-web-page-data-using-power-bi-desktop-tutorial"></a>Verkkosivun tietojen analysointi Power BI Desktopissa (opetusohjelma)
Tässä opetusohjelmassa saat tietää, miten tuot tietoja verkkosivulla olevasta taulukosta ja luot raportin tietojen visualisointiin. Osana tätä prosessia siirryt verkkosivulla olevien taulukoiden välillä ja suoritat tiedonmuunnosvaiheita taulukon muodon muuntamista varten.

 Tässä artikkelissa:

* **Tehtävä 1:** yhteyden muodostaminen verkkotietolähteeseen
* **Tehtävä 2:** tietojen muotoilu kyselynäkymässä
  * Vaihe 1: muiden sarakkeiden poistaminen ja vain tarvittavien sarakkeiden näyttäminen
  * Vaihe 2: arvojen korjaaminen ja valitussa sarakkeessa olevien arvojen puhdistaminen
  * Vaihe 3: sarakkeiden arvojen suodattaminen
  * Vaihe 4: sarakkeen nimeäminen uudelleen
  * Vaihe 5: sarakkeiden nolla-arvojen suodattaminen
  * Vaihe 6: kyselyn nimeäminen uudelleen
  * Kyselyvaiheet luotu
* **Tehtävä 3:** visualisointien luominen raporttinäkymän avulla
  * Vaihe 1: kyselyn lataaminen raporttiin
  * Vaihe 2: karttavisualisoinnin luominen

## <a name="task-1-connect-to-a-web-data-source"></a>Tehtävä 1: yhteyden muodostaminen verkkotietolähteeseen
 Tehtävässä 1 turnauksen yhteenvetotaulukko tuodaan UEFA:n jalkapallon Euroopan-mestaruuskilpailuiden Wikipedia-sivulta, jonka osoite on: http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

### <a name="add-a-wikipedia-page-data-source"></a>Wikipedia-sivun tietolähteen lisääminen
1. **Aloittaminen-valintaikkunassa** tai **Aloitus**-valintanauhassa valitse **Nouda tiedot**.
2. Tämä tuo näkyviin **Nouda tiedot** -valintaikkunan, jonka kautta voit tuoda tietoja useista tietolähteistä Power BI Desktopiin. Valitsemme **Verkko**, joka on käytettävissä **Kaikki**- tai **Muut**-ryhmän alla.
3. **Verkkosisältö**-valintaikkunassa liimaa **URL-osoite**-tekstikenttään Wikipedian URL-osoite (http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship).
4. Valitse **OK**.

Kun olet luonut yhteyden verkkosivuun, näet **Siirtymistoiminto**-valintaikkunassa luettelon käytettävissä olevia taulukoista kyseisellä Wikipedia-sivulla. Voit esikatsella kunkin taulukon tietoja napsauttamalla niitä kerran.

Vasemmalla olevassa **Siirtymistoiminto**-ruudussa valitse **Tulokset[muokkaa]**-taulukko turnauksen yhteenvetotulosten näkemiseksi tai valitse **Tulokset[Muokkaa]**-taulukko ja valitse **Muokkaa**. Tämä sallii kyseisen taulukon uudelleenmuotoilun ennen sen lataamista raporttiin, sillä tiedot eivät ole analyysin edellyttämässä muodossa.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)

Tämä tuo esikatseluversion taulukosta kyselynäkymään, jossa voidaan suorittaa erinäisiä muunnosvaiheita tietojen puhdistamiseksi.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)

## <a name="task-2-shape-data-in-the-subject-table"></a>Tehtävä 2: tietojen muotoilu aihetaulukossa
Nyt, kun aihetaulukko on valittuna tietokyselyyn, kerromme, miten voit suorittaa erilaisia tietojen muotoilu- ja puhdistusvaiheita.

**Vaihe 1:** muiden sarakkeiden poistaminen vain tarvittavien sarakkeiden näyttämiseksi

Tässä vaiheessa poistat kaikki sarakkeet lukuun ottamatta sarakkeita **Vuosi** ja **Finaalin voittajat**.

1. **Kyselyn esikatselu** -ruudukossa valitse **Vuosi**- ja **Finaalin voittajat** -sarakkeet (**CTRL** + **napsautus**).
2. Napsauta sarakeotsikkoa hiiren kakkospainikkeella **Kyselyn esikatselu** -ruudukossa ja valitse **Poista muut sarakkeet** valitsemattomien sarakkeiden poistamiseksi. Huomaa, että tämä toiminto on käytettävissä myös **Aloitus**-valintanauhan **Sarakkeiden hallinta** -ryhmässä.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

**Vaihe 2:** arvojen korjaaminen ja valitussa sarakkeessa olevien arvojen puhdistaminen

Tässä vaiheessa korvaat Tiedot-liitteen **Vuosi**-sarakkeessa. Huomaa, että tämä liite on uudella rivillä, joten se ei näy taulukon esikatselussa. Mutta, jos valitset jonkin solun, jolla on numeerinen arvo Vuosi-sarakkeessa, näet koko arvon yksityiskohtaisessa näkymässä.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage5.png)

1. Valitse **Vuosi**-sarake.
2. **Kyselynäkymä**-valintanauhassa valitse **Korvaa arvot** **Aloitus**-välilehdellä tai napsauta hiiren kakkospainikkeella **Vuosi**-saraketta ja valitse **Korvaa arvot** tietojen korvaamiseksi tyhjällä tekstillä.
3. **Korvaa arvot** -valintaikkunassa syötä Tiedot **Etsittävä arvo** -tekstiruutuun ja jätä **Korvaa kohteella** -tekstiruutu tyhjäksi.
4. Valitse **OK**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

 **Vaihe 3:** sarakkeiden arvojen suodattaminen

Tässä vaiheessa suodatat **Vuosi**-sarakkeen näyttääksesi rivit, jotka eivät sisällä ”Vuotta”.

1. Napsauta suodatuksen avausnuolta **Vuosi**-sarakkeessa.
2. Avattavassa **Suodatus**-valikossa poista **Vuosi**-vaihtoehto.
3. Valitse **OK**.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

**Vaihe 4:** sarakkeen nimeäminen uudelleen

Nyt kun **Vuosi**-sarakkeen tiedot on puhdistettu, siirrymme **Finaalin voittaja** -sarakkeeseen.

Koska käsittelemme ainoastaan voittajaluetteloa, voimme antaa tämän sarakkeen uudeksi nimeksi **Maa**.

1. Valitse **Finaalin voittaja** -sarake kyselyn esikatselussa.
2. **Kyselynäkymä**-valintanauhassa, **Muunna**-välilehdellä ja **Mikä tahansa sarake** -ryhmässä on kohta **Nimeä uudelleen**.
3. Se sallii sarakkeen nimen muokkaamisen. Annamme tämän sarakkeen nimeksi **Maa**.

**Vaihe 5:** sarakkeiden nolla-arvojen suodattaminen pois

Meidän on suodatettava myös nolla-arvot pois **Maa**-sarakkeesta. Voimme käyttää siihen suodatusvalikkoa kuten vaiheessa 3. Vaihtoehtoisesti voimme toimia seuraavasti:

1. Napsauta hiiren kakkospainikkeella jotakin nolla-arvon sisältävää solua **Maa**-sarakkeessa.
2. Valitse pikavalikossa **Tekstisuodattimet -\> ei ole yhtä suuri kuin**.
3. Tämä luo uuden suodatinvaiheen, joka poistaa nolla-arvorivit **Maa**-sarakkeesta.

**Vaihe 6:** kyselyn nimeäminen

Tässä vaiheessa annat lopullisen kyselyn nimeksi **Euroopan-mestaruuskisojen voittajat**.

1. **Kyselyasetukset**-ruudun **Nimi**-tekstikenttään syötä **Euroopan-mestaruuskisojen voittajat**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

## <a name="task-3-create-visualizations-using-the-report-view"></a>Tehtävä 3: visualisointien luominen raporttinäkymän avulla
Nyt kun olemme muuntaneet tiedot analyysin edellyttämään muotoon, voimme ladata tulostaulukon raporttiin ja luoda muutamia visualisointeja.

**Vaihe 1:** kyselyn lataaminen raporttiin

Kyselyn tulosten lataamiseksi Power BI Desktopiin ja raportin luomiseksi valitsemme **Sulje ja lataa** **Aloitus**-valintanauhassa.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)

Tämä käynnistää kyselyn arvioinnin ja taulukon tulosten lataamisen raporttiin. Power BI Desktopissa valitse **Raportti**-kuvake. Näet Power BI Desktopin raporttinäkymässä.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage10.png)

Näet taulukon tuloskentät **Kentät-ruudussa** **Raporttinäkymän** oikeassa reunassa.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)

**Vaihe 2:** karttavisualisoinnin luominen

Visualisoinnin luomiseksi voimme vetää kenttiä **Kenttä-luettelosta** ja pudottaa ne **raporttipohjaan**.

1. Vedä **Maa**-kenttää ja pudota se **raporttipohjaan**. Tämä luo uuden visualisoinnin **raporttipohjassa**. Tässä tapauksessa, koska meillä on luettelo maista, se luo **karttavisualisoinnin**.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage12.png)
2. Voimme helposti muuttaa visualisoinnin tyyppiä napsauttamalla eri kuvaketta **Visualisointi**-ruudussa.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage13.png)
3. Pysymme **Kartta**-visualisointityypissä. Voimme myös muokata visualisoinnin kokoa vetämällä sitä yhdestä kulmasta, kunnes se on halutun kokoinen.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
4. Huomaa, että tällä hetkellä kartan kaikki pisteet ovat saman kokoisia. Haluamme muuttaa tätä, niin että maat, jotka ovat voittaneet Euroopan-mestaruuskisat useamman kerran, näkyvät kartalla suurempina pisteinä. Jotta voimme tehdä näin, voimme vetää **Vuosi**-kentän **Kenttä-luettelossa** **Arvot**-valintaikkunaan **Kentät-ruudun** alareunassa.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)

Kuten näet, on helppoa mukauttaa raporttien visualisointeja ja esittää tiedot halutulla tavalla. Power BI Desktop tarjoaa saumattoman kokemuksen alusta loppuun. Sen avulla voit hakea tietoja laajasta tietolähteiden joukosta ja muotoilla ne analyysitarpeidesi mukaan ja visualisoida tiedot monipuolisilla ja vuorovaikutteisilla tavoilla. Kun raportti on valmis, voit [ladata sen Power BI:hin](desktop-upload-desktop-files.md) ja luoda siihen perustuvia koontinäyttöjä, joita voit jakaa muiden Power BI -käyttäjien kanssa.

Tähän päättyy **Tietojen tuominen verkosta** -opetusohjelma. Voit ladata tämän valmiin Power BI Desktop -tiedoston [täältä](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Data_From_The_Web.pbix).

## <a name="where-else-can-i-get-more-information"></a>Mistä muualta saan lisätietoja?
* [Lue muita Power BI Desktop -opetusohjelmia](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Katso Power BI Desktop -videoita](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Käy Power BI -keskustelupalstalla](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Lue Power BI -blogia](http://go.microsoft.com/fwlink/?LinkID=519327)

