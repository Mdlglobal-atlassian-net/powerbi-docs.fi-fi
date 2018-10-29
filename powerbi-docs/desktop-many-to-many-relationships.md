---
title: Moni-moneen-yhteydet Power BI Desktopissa (esikatselu)
description: Monta moneen -yhteyksien käyttäminen Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/17/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 379f80e1e87181ffdacdaab01d87ff435f2a9501
ms.sourcegitcommit: 2c4a075fe16ccac8e25f7ca0b40d404eacb49f6d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/20/2018
ms.locfileid: "49473770"
---
# <a name="many-to-many-relationships-in-power-bi-desktop-preview"></a>Moni-moneen-yhteydet Power BI Desktopissa (esikatselu)

Power BI Desktopin *moni-moneen-yhteysominaisuuden* avulla voit liittää taulukoita, jotka käyttävät *moni-moneen*-kardinaliteettia. Voit helposti ja intuitiivisesti luoda tietomalleja, jotka sisältävät kahden tai useamman tietolähteen. *Moni-moneen-yhteysominaisuus* on osa Power BI Desktopin laajempia *yhdistelmämallien* ominaisuuksia.

![Moni-moneen-suhde ”Muokkaa suhdetta” -ruudussa](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Power BI Desktopin *moni-moneen -yhteysominaisuus* on yksi kolmesta toisiinsa liittyvästä ominaisuudesta:

* **Yhdistelmämallit**: Antavat mahdollisuuden sisällyttää raporttiin kaksi tietoyhteyttä tai enemmän (kuten DirectQuery-yhteydet tai tuonnin) minä tahansa yhdistelminä. Jos haluat lisätietoja, katso [Yhdistelmämallien käyttäminen Power BI Desktopissa (esikatselu)](desktop-composite-models.md).

* **Moni-moneen-yhteydet**: *Yhdistelmämallien* avulla voit määrittää taulukoiden välille *moni-moneen-yhteyksiä*. Tämä lähestymistapa poistaa vaatimuksen siitä, että taulukoiden arvojen pitäisi olla yksilöllisiä. Se myös poistaa edelliset ratkaisut, kuten uusien taulukoiden lisäämisen vain yhteyksien muodostamiseksi. Ominaisuutta kuvataan tarkemmin myöhemmin tässä artikkelissa.

* **Tallennustilan tila**: Voit nyt määrittää, mitkä visualisoinnit edellyttävät kyselyä taustatietolähteisiin. Visualisoinnit, jotka eivät edellytä kyselyä, tuodaan, vaikka ne perustuisivat DirectQueryyn. Tämä ominaisuus parantaa suorituskykyä ja vähentää taustakuormitusta. Aiemmin jopa osittajien kaltaiset yksinkertaiset visualisoinnit aloittivat kyselyjä taustalähteisiin. Lisätietoja löytyy artikkelista [Tallennustilan tila Power BI Desktopissa (esikatselu)](desktop-storage-mode.md).

## <a name="enable-the-many-to-many-relationships-preview-feature"></a>*Moni-moneen-yhteyksien* ottaminen käyttöön esikatseluominaisuutena

*Moni-moneen-yhteysominaisuus* on otettava käyttöön Power BI Desktopissa. Ota yhdistelmämallit käyttöön valitsemalla **Tiedosto** >  **Asetukset ja vaihtoehdot** > **Asetukset** > **Esikatseluominaisuudet**. Valitse sitten **Yhdistelmämallit**-valintaruutu.

![Esikatseluominaisuudet-ruutu](media/desktop-composite-models/composite-models_02.png)

Jos haluat ottaa ominaisuuden käyttöön, sinun tulee käynnistää Power BI Desktop uudelleen.

![Ominaisuus edellyttää uudelleenkäynnistämistä -ikkuna](media/desktop-composite-models/composite-models_03.png)

## <a name="what-many-to-many-relationships-solves"></a>*Moni-moneen-yhteyksien* edut

Ennen kuin *moni-moneen-yhteysominaisuus* tuli saataville, käyttäjien tuli määrittää kahden taulukon välinen yhteys Power BI:ssa. Ainakin yhdessä yhteyteen liittyvässä taulukon sarakkeessa oli oltava yksilöllisiä arvoja. Usein kuitenkin kävi niin, että yksikään sarake ei sisältänyt yksilöllisiä arvoja. 

Kahdessa taulukossa saattoi olla esimerkiksi *Maa*-niminen sarake, mutta *Maa*-sarakkeen arvot eivät olleet yksilöllisiä kummassakaan taulukossa. Tällaisten taulukoiden yhdistämiseksi oli tarpeen luoda kiertotapoja. Yksi mahdollinen kiertotapa oli lisätä malliin taulukkoja, jotka sisälsivät tarvittavat yksilölliset arvot. *Moni-moneen-yhteysominaisuuden* avulla tällaisia taulukoita voidaan liittää toisiinsa suoraan käyttämällä yhteyttä, jonka kardinaliteetti on **moni-moneen**.  

## <a name="use-many-to-many-relationships"></a>*Moni-moneen-yhteyksien* käyttäminen

Kun määrität Power BI:ssä kahden taulukon välisen suhteen, sinun täytyy määrittää suhteen kardinaliteetti. Esimerkiksi taulukoiden *Tuotemyynti* ja *Tuote*&mdash;käyttämällä sarakkeita *Tuotemyynti[Tuotekoodi]* ja *Tuote[Tuotekoodi]*&mdash; yhteys määritettäisiin *monta-yhteen*-yhteydeksi. Yhteys määritetään näin, koska kullekin tuotteelle on useita myyntejä ja sarake *Tuote*-taulukossa *(Tuotekoodi)* on yksilöllinen. Kun määrität suhteen kardinaliteetiksi *monta-yhteen*, *yksi-moneen* tai *yksi-yhteen*, Power BI tarkistaa, että valittu kardinaliteetti vastaa varsinaisia tietoja.

Tutustu esimerkiksi seuraavan kuvan yksinkertaiseen malliin:

![Suhdenäkymä](media/desktop-many-to-many-relationships/many-to-many-relationships_02.png)

Kuvittele nyt, että *Tuote*-taulukosta näytettäisiin vain kaksi riviä seuraavanlaisesti:

![Tuote-taulukon visualisointi, jossa näkyy kaksi riviä](media/desktop-many-to-many-relationships/many-to-many-relationships_03.png)

Kuvittele myös, että *Myynti*-taulukossa on vain neljä riviä, mukaan lukien rivi tuotteelle C. Viite-eheyden virheen vuoksi C-tuotteen rivi ei löydy *Tuote*-taulukosta.

![Myynti-taulukon visualisointi, jossa näkyy neljä riviä](media/desktop-many-to-many-relationships/many-to-many-relationships_04.png)

*Tuotenimi*- ja *Hinta*-tiedot (*Tuote*-taulukosta) sekä jokaisen tuotteen *Määrä*-tieto (*Tuotemyynti*-taulukosta) esitettäisiin seuraavalla tavalla: 

![Visualisointi, jossa esitetään tuotteen nimi, hinta ja määrä](media/desktop-many-to-many-relationships/many-to-many-relationships_05.png)

Kuten yllä olevasta kuvasta näkyy, tuotteen C myyntitietoihin on liitetty tyhjä *Tuotenimi*-rivi. Tämä tyhjä rivi perustuu seuraaviin:

* *Tuotemyynti*-taulukon kaikki sellaiset rivit, joille ei ole vastaavaa riviä *Tuote*-taulukossa. Kyseessä on viite-eheyden ongelma, kuten näemme tuotteen *C* kohdalla tässä esimerkissä.

* *Tuotemyynti*-taulukon kaikki sellaiset rivit, joiden viiteavainsarake on arvoltaan null. 

Näistä syistä tyhjä rivi selittyy molemmissa tapauksissa myynnillä, jossa *Tuotenimi*- ja *Hinta*-tietoja ei tunneta.

Joskus kyse on kuitenkin siitä, että taulukot ovat yhteydessä toisiinsa kahdella sarakkeella, mutta kumpikaan sarake ei ole yksilöllinen. Otetaan esimerkiksi seuraavat kaksi taulukkoa:

* *Myynti*-taulukossa näkyy myyntitietoja *Osavaltio*-arvon mukaan, ja kukin rivi sisältää myyntisumman kyseisen osavaltion myyntityypin mukaan. Osavaltioihin sisältyy Kalifornian, Washingtonin ja Texasin osavaltiot. 

    ![Myynti-taulukko, jossa näytetään myynti osavaltion mukaan](media/desktop-many-to-many-relationships/many-to-many-relationships_06.png)

* *Kaupunkidata*-taulukko näyttää tietoa kaupungeista, kuten asukasmäärän ja osavaltion (sisältää Kalifornian, Washingtonin ja New Yorkin).

    ![Myynti-taulukko, joka näyttää kaupungin, osavaltion ja asukasmäärä](media/desktop-many-to-many-relationships/many-to-many-relationships_07.png)

Vaikka kummassakin taulukossa on *Osavaltio*-sarake ja raportin olisi hyvä sisältää kaikki tiedot myynnistä jokaisessa osavaltiossa sekä kunkin osavaltion asukasmäärä, tässä piilee yksi ongelma: *Osavaltio*-sarake ei ole yksilöllinen kummassakaan taulukossa. 

## <a name="the-previous-workaround"></a>Aiempi vaihtoehtoinen menetelmä

Ennen heinäkuun 2018 Power BI Desktop -versiota käyttäjät eivät voineet luoda suoraa suhdetta näiden taulukoiden välille. Yleinen tapa kiertää tämä ongelma oli toimia seuraavasti:

* Luodaan kolmas taulukko, joka sisältää vain yksilöllisiä *Osavaltio*-tunnuksia. Taulukko voi olla mikä tahansa tai kaikki seuraavista:
  * Laskettu taulukko (määritetty Data Analysis Expressionsin [DAX] avulla).
  * Kyselyeditorissa määritetty kyselyyn pohjautuva taulukko, joka voi näyttää yhdestä taulukosta haetut yksilöivät tunnukset.
  * Yhdistetty koko joukko.

* Alkuperäiset taulukot yhdistetään tähän uuteen taulukkoon käyttämällä yleisiä *monta-yhteen*-yhteyksiä.

Kiertotapataulukon voi jättää näkyviin tai piilottaa siten, että se ei näy **Kentät**-luettelossa. Jos piilotat taulukon, *monta-yhteen*-yhteydet asetetaan yleensä suodattamaan molempiin suuntiin, jolloin voit käyttää *Osavaltio*-kenttää kummasta tahansa taulukosta. Sen jälkeen tiedot välitetään toiseen taulukkoon ristiinsuodatuksella. Tämä lähestymistapa esitetään seuraavassa kuvassa:

![Suhdenäkymä](media/desktop-many-to-many-relationships/many-to-many-relationships_08.png)

Visualisointi, joka näyttää *Osavaltio*-tiedot (*Kaupunkidata*-taulukosta) *Asukasmäärä*-kokonaisarvon ja yhteenlasketun *Myynti*-arvon, näkyisi sitten seuraavasti:

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_09.png)

> [!NOTE]
> Koska kiertotavassa käytetään osavaltioita *Kaupunkidata*-taulukosta, vain taulukossa olevat osavaltiot luetellaan, jonka vuoksi Teksas on jäänyt pois. Lisäksi toisin kuin *monta-yhteen*-yhteyksissä, summarivi sisältää kyllä kaikki *Myynti*-tiedot (myös Teksasin), mutta tietoihin ei sisälly tyhjää riviä, joka kattaa tällaiset ristiriitaiset rivit. Vastaavasti mukana ei olisi tyhjää riviä *Myynti*-tiedoille, joiden *Osavaltio*-arvo on null.

Jos *Kaupunki*-arvo lisättäisiin myös visualisointiin, *kaupunkikohtainen* asukasmäärä olisi toki tiedossa, mutta *Myynti*-tieto *kaupungille* vain toistaisi *Myynti*-tiedon vastaavalle *osavaltiolle*. Näin normaalisti käykin, kun sarakkeessa oleva ryhmittely ei liity johonkin koostettuun mittayksikköön, kuten seuraavassa kuvassa esitetään:

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_10.png)

Jos uusi *Myynti*-taulukko määritetään kaikkien *osavaltioiden* yhdistelmäksi tässä kiertokeinossa ja tehdään näkyväksi **Kentät**-luettelossa, sama visualisointi, joka näyttää *Osavaltio*-tiedot (uudessa taulukossa) sekä *asukasmäärän* ja *myynnin* kokonaisarvot, olisi seuraavanlainen:

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_11.png)

Tässä tapauksessa mukana olisivat *Texas*&mdash;*Myynti*-tieto mukana mutta tuntematon *asukasmäärä*&mdash; ja *New York*&mdash;tunnettu *asukasmäärä* mutta ei *Myynti*-tietoa&mdash;. Tämä kiertokeino ei ole paras mahdollinen ja se sisältää monia ongelmia. Nämä ongelmat ratkaistiin moni-moneen-yhteyksillä, kuten seuraavassa osiossa kuvataan.

## <a name="use-many-to-many-relationships-instead-of-the-workaround"></a>*Moni-moneen-yhteyksien* käyttäminen kiertotavan sijaan

Power BI Desktopin heinäkuun 2018 versiosta alkaen voit yhdistää taulukoita suoraan ilman, että sinun tarvitsee turvautua edellisessä osiossa kuvattuihin kiertotapoihin. Nyt voit määrittää suhteen kardinaliteetiksi *monta moneen*. Tämä asetus ilmaisee, että kumpikaan taulukko ei sisällä yksilöllisiä arvoja. Tällaisissa yhteyksissä voit edelleen hallita, mikä taulukko suodattaa toisen taulukon. Voit myös käyttää kaksisuuntaista suodatusta, jossa kumpikin taulukko suodattaa toista.  

> [!NOTE]
> *Moni-moneen-yhteyksien* luominen on esikatselutilassa. Niin kauan kuin se on esikatselussa, et voi julkaista Power BI -palvelumalleihin, jotka käyttävät *moni-moneen-yhteyksiä*. 

Power BI Desktopissa kardinaliteetin oletusarvoksi asetetaan *monta moneen*, kun havaitaan, ettei kumpikaan taulukko sisällä yksilöllisiä arvoja yhteyden sarakkeissa. Tässä tapauksessa näyttöön tulee varoitus, joka vahvistaa, että yhteysasetus on määritetty tarkoituksella, eikä kyse ole tieto-ongelman odottamaton seuraus. 

Jos luot esimerkiksi *Kaupunkidata*- ja *Myynti*-taulukoiden välille suoran yhteyden&mdash;jossa tiedot suodatetaan *Kaupunkidata*-taulukosta *Myynti*-taulukkoon&mdash;Power BI Desktop näyttää seuraavan kuvan mukaisen **Muokkaa suhdetta** -ikkunan:

![”Muokkaa suhdetta” -ikkuna](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Seuraava **suhdenäkymä** näyttäisi kyseisen kahden taulukon välisen suoran moni-moneen-yhteyden. Taulukoiden ulkoasu **Kentät**-luettelossa (sekä niiden myöhempi toiminta visualisointeja luotaessa) on samanlainen kuin kiertotapaa käytettäessä. Kiertotapaa käytettäessä ylimääräinen taulukko, joka näyttää erilliset *Osavaltio*tiedot, ei ole määritetty näkyväksi. Esimerkiksi aiemman osion mukainen visualisointi, joka sisältää *Osavaltio*-, *Asukasmäärä*- ja *Myynti*-tiedot, esitettäisiin seuraavanlaisesti:

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_12.png)

*Moni-moneen*-yhteyksien ja yleisempien *monta-yhteen*-yhteyksien merkittävimmät erot ovat seuraavat:

* Näytetyt arvot eivät sisällä toisen taulukon ristiriitaisista riveistä johtuvaa tyhjää riviä. Arvot eivät myöskään sisällä rivejä, joissa yhteydessä käytettävän toisen taulukon sarake sisältää null-arvoja.
* `RELATED()`-funktion käyttäminen ei ole mahdollista, koska useampi kuin yksi rivi voi olla liittyvä.
* `ALL()`-funktion käyttäminen taulukossa ei poista suodattimia, joita käytetään taulukkoon moni-moneen-yhteydellä yhdistetyissä muissa taulukoissa. Edellisessä esimerkissä mittayksikkö, joka on määritetty seuraavan komentosarjan tavoin, ei poistaisi yhdistetyn *Kaupunkitiedot*-taulukon sarakkeissa olevia suodattimia:

    ![Komentosarjaesimerkki](media/desktop-many-to-many-relationships/many-to-many-relationships_13.png)

    Visualisointi, jossa näytetään *Osavaltio*, *Myynti* ja *Kokonaismyynti*, näyttäisi seuraavalta:

    ![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_14.png)

Näiden eroavaisuuksien vuoksi sinun tuleekin varmistaa, että `ALL(\<Table>)`-funktiolla suoritetut laskutoimitukset, kuten *prosenttiosuus kokonaissummasta*, palauttavat tarkoitetut tulokset. 


## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Tämän version *moni-moneen-yhteyksissä* ja yhdistelmämalleissa on muutamia rajoituksia.

Seuraavia Live Connectin monidimensioisia lähteitä ei voi käyttää yhdistelmämallien kanssa:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI -tietojoukot
* Azure Analysis Services

Kun muodostat yhteyttä näihin monidimensioisiin lähteisiin DirectQuerylla, et voi muodostaa yhteyttä myös toiseen DirectQuery-lähteeseen tai yhdistää sitä tuotuihin tietoihin.

DirectQueryn olemassa olevat käyttörajoitukset koskevat edelleen *moni-moneen-yhteyksien* käyttämistä. Monet näistä rajoituksista ovat nyt taulukkokohtaisia ja riippuvat taulukon tallennustilan tilasta. Esimerkiksi tuodun taulukon laskettu sarake voi viitata muihin taulukoihin, mutta DirectQuery-taulukon laskettu sarake voi viitata vain saman taulukon sarakkeisiin. Muut rajoitukset koskevat vain mallia kokonaisuutena, jos jokin mallin taulukoista on DirectQuery-taulukko. Esimerkiksi Nopeat merkitykselliset tiedot ja Q&A-ominaisuudet eivät ole käytettävissä mallissa, jos jollakin sen taulukoista tallennustilan tilana on DirectQuery. 

## <a name="next-steps"></a>Seuraavat vaiheet

Seuraavissa artikkeleissa on lisätietoja yhdistelmämalleista ja DirectQuerysta:
* [Yhdistelmämallit Power BI Desktopissa (esikatselu)](desktop-composite-models.md)
* [Tallennustilan tila Power BI Desktopissa (esikatselu)](desktop-storage-mode.md)
* [DirectQueryn käyttö Power BI Desktopissa](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet Power BI Desktopissa](desktop-directquery-data-sources.md)
