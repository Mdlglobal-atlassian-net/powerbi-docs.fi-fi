---
title: Moni-moneen-yhteydet Power BI Desktopissa (esikatselu)
description: Monta moneen -yhteyksien käyttäminen Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/23/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 1105de002f6461589d61c6f0077cceeedaada471
ms.sourcegitcommit: 6faeb642721ee5abb41c04a8b729880c01c4d40e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/23/2018
ms.locfileid: "39210889"
---
# <a name="many-to-many-relationships-in-power-bi-desktop-preview"></a>Moni-moneen-yhteydet Power BI Desktopissa (esikatselu)

**Power BI Desktopin** **moni moneen -yhteyksien** avulla voit liittää taulukoita käyttämällä **monta moneen** -ominaisuuden kardinaliteettia. Voit myös luoda useita tietolähteitä sisältäviä tietomalleja entistä helpommin ja intuitiivisemmin. **Monta moneen -yhteysominaisuus** on osa **Power BI Desktopin** laajempia **yhdistelmämallien** ominaisuuksia.

![Monta moneen -yhteyksien Muokkaa suhdetta -valintaikkuna](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

**Power BI Desktopin** **monta moneen -yhteysominaisuus** on osa kolmen toisiinsa liittyvän ominaisuuden kokoelmaa:

* **Yhdistelmämallit** – antavat mahdollisuuden sisällyttää raporttiin useita tietoyhteyksiä, kuten DirectQuery-yhteydet tai tuonnin, minä tahansa yhdistelminä.
* **Monta moneen -yhteydet** – yhdessä **yhdistelmämallien** kanssa voit muodostaa **monta moneen -yhteyksiä** taulukoiden välille ilman tarvetta yksilöllisille arvoille taulukoissa. Tämä poistaa tarpeen aiemmille kiertotavoille, kuten uusien taulukoiden lisäämiselle vain yhteyksien muodostamisen takia. 
* **Tallennustilan tila** – voit nyt määrittää, mitkä visualisoinnit edellyttävät kyselyä taustatietolähteisiin. Ne visualisoinnit, jotka eivät sitä tarvitse, tuodaan DirectQuery-kyselyyn pohjautumisesta huolimatta. Se parantaa suorituskykyä ja vähentää taustajärjestelmien kuormitusta. Aiemmin jopa osittajien kaltaiset yksinkertaiset visualisoinnit käynnistivät kyselyjä taustalähteisiin. 

Nämä kolme toisiinsa liittyvää **yhdistelmämallien** ominaisuutta on kukin kuvattu omissa artikkeleissaan:

* **Yhdistelmämallit** on kuvattu yksityiskohtaisesti [Yhdistelmämallit Power BI Desktopissa (esikatselu)](desktop-composite-models.md) -artikkelissa.
* **Monta moneen -yhteydet** on kuvattu tässä artikkelissa.
* **Tallennustilan tila** on kuvattu omassa [Tallennustilan tila Power BI Desktopissa (esikatselu)](desktop-storage-mode.md) -artikkelissaan.

## <a name="enabling-the-many-to-many-relationships-preview-feature"></a>Monta moneen -yhteyksien ottaminen käyttöön esikatseluominaisuutena

**Monta moneen -yhteysominaisuus** on osa **yhdistelmämallien** ominaisuuksia ja esikatselutilassa. Se on otettava käyttöön **Power BI Desktopissa**. Ota **yhdistelmämallit** käyttöön valitsemalla **Tiedosto > Asetukset ja vaihtoehdot > Asetukset > Esiversio-ominaisuudet**. Valitse sitten **Yhdistelmämallit**-valintaruutu.

![Esikatselutoimintojen ottaminen käyttöön](media/desktop-composite-models/composite-models_02.png)

Ominaisuuden käyttöönotto edellyttää **Power BI Desktopin** käynnistämistä uudelleen.

![Uudelleenkäynnistys vaaditaan, jotta muutokset tulevat voimaan](media/desktop-composite-models/composite-models_03.png)


## <a name="what-many-to-many-relationships-solves"></a>Monta moneen -yhteyksien edut

Ennen kuin **monta moneen -yhteydet** tulivat saataville, kahden Power BI:ssä olevan taulukon yhteyttä määritettäessä ainakin yhdessä yhteyteen liittyvässä sarakkeessa oli oltava yksilöllisiä arvoja. Monissa tilanteissa yksikään taulukon sarake ei kuitenkaan sisältänyt yksilöllisiä arvoja. 

Kahdessa taulukossa saattoi olla esimerkiksi sarake, joka sisältää *maan*, mutta *maa*-sarakkeen arvot eivät olleet yksilöllisiä kummassakaan taulukossa. Tällaisten taulukoiden yhdistämiseksi oli tarpeen luoda kiertotapoja, kuten lisätä malliin taulukkoja, jotka sisälsivät tarvittavat yksilölliset arvot. **Monta moneen -yhteydet** tarjoavat vaihtoehtoiseen lähestymistavan sallimalla tällaisten taulukoiden yhdistämisen suoraan käyttämällä yhteyttä **monta moneen** -ominaisuuden kardinaliteetin avulla.  

## <a name="using-many-to-many-relationships"></a>Monta moneen -yhteyksien käyttäminen

Kun määrität Power BI:ssä kahden taulukon välisen suhteen, sinun täytyy määrittää suhteen kardinaliteetti. Esimerkiksi taulukoiden *Tuotemyynti* ja *Tuote* (käyttämällä sarakkeita *Tuotemyynti[Tuotekoodi]* ja *Tuote[Tuotekoodi]*) yhteys määritettäisiin **moni-yhteen**-yhteydeksi, sillä kullekin tuotteelle on useita myyntejä ja sarake *Tuote*-taulukossa *(Tuotekoodi)* on yksilöllinen. Kun määrität suhteen kardinaliteetiksi **monta yhteen**, **yksi moneen** tai **yksi yhteen**, Power BI tarkistaa, että valittu kardinaliteetti vastaa varsinaisia tietoja.

Tutustu esimerkiksi seuraavan kuvan yksinkertaiseen malliin.

![Suhdenäkymä](media/desktop-many-to-many-relationships/many-to-many-relationships_02.png)

Kuvittele sitten, että *Tuote*-taulukko sisälsi vain kaksi riviä.

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_03.png)

Kuvittele myös, että *Myynti*-taulukossa on vain neljä riviä, mukaan lukien *Myynti* tuotteelle **C**, jota ei ole *Tuote*-taulukossa (viite-eheyden virheen takia).

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_04.png)

Visualisointi, joka näyttää *Tuotenimi*- ja *Hinta*-tiedot (*Tuote*-taulukosta) sekä jokaisen tuotteen *Määrä*-tiedon (*Tuotemyynti*-taulukosta), näyttäisi seuraavan kuvan kaltaiselta: 

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_05.png)

Kuten edellinen kuva näyttää, visualisoinnissa on rivi, joka sisältää tyhjän *Tuotenimi*-tiedon liitettynä tuotteen *C* myyntiin. Tyhjä rivi perustuu seuraaviin:

* *Tuotemyynti*-taulukon kaikki sellaiset rivit, joille ei ole vastaavaa riviä *Tuote*-taulukossa. Kyseessä on viite-eheyden ongelma, kuten tämän esimerkin tuotteesta *C* näemme.

* *Tuotemyynti*-taulukon kaikki sellaiset rivit, joiden viiteavainsarake on arvoltaan null. 

Näistä syistä tyhjä rivi selittyy molemmissa tapauksissa myynnillä, jossa *Tuotenimi*- ja *Hinta*-tietoja ei tunneta.

Joskus kyse on kuitenkin siitä, että taulukot ovat yhteydessä toisiinsa kahdella sarakkeella, mutta kumpikaan sarake ei ole yksilöllinen. Otetaan esimerkiksi seuraavat kaksi taulukkoa:

* *Myynti*-taulukossa on myyntitietoja *Osavaltio*-arvon mukaan. Kukin rivi sisältää myyntisumman kyseisen osavaltion myyntityypin mukaan (mukana ovat osavaltiot Kalifornia, Washington ja Texas). 

    ![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_06.png)

* *Kaupunkidata*-taulukko sisältää tietoa kaupungeista, kuten asukasmäärä ja osavaltio (mukana ovat osavaltiot Kalifornia, Washington ja New York).

    ![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_07.png)

Kummassakin taulukossa on *Osavaltio*-sarake, ja raportti olisi mielekästä tuottaa yhteenlasketuista *Myynti*-arvoista *Osavaltio*-tiedon suhteen yhdistettynä jokaisen osavaltion asukasmäärään. Asiassa on kuitenkin ongelma: *Osavaltio*-sarake ei ole yksilöllinen kummassakaan taulukossa. 

## <a name="the-prior-workaround"></a>Aiempi kiertotapa

Ennen heinäkuussa 2018 julkaistua **Power BI Desktop** -versiota ei ollut mahdollista luoda yhteyttä suoraan näiden taulukoiden välille. Yleinen tapa kiertää tämä ongelma oli toimia seuraavasti:

* Luodaan kolmas taulukko, joka sisältää vain yksilöllisiä *Osavaltio*-tunnuksia. Tämä voi olla joko laskettu taulukko (määritetty käyttämällä DAX:ää) tai taulukko, joka on määritetty käyttämällä **Kyselyeditorin** kyselyä. Taulukko voi sisältää jommastakummasta taulukosta poimitut yksilölliset tunnukset tai koko yhdistetyn joukon.

* Alkuperäiset taulukot yhdistetään tähän uuteen taulukkoon käyttämällä yleisiä **monta yhteen* -yhteyksiä.

Kiertotapataulukon voi jättää näkyviin tai piilottaa siten, että se ei näy kenttäluettelossa. Jälkimmäisessä tapauksessa **monta yhteen** -yhteydet asetetaan yleensä suodattamaan molempiin suuntiin siten, että *Osavaltio*-kenttää voi käyttää kummasta tahansa taulukosta. Sen jälkeen tiedot välitetään toiseen taulukkoon ristiinsuodatuksella. Kiertotapa näytetään seuraavassa **suhdenäkymän** kuvassa.

![Suhdenäkymä](media/desktop-many-to-many-relationships/many-to-many-relationships_08.png)

Visualisointi näyttää *Osavaltio*-tiedot (*Kaupunkidata*-taulukosta) *Asukasmäärä*-kokonaisarvojen kanssa. Yhteenlaskettu *Myynti* näkyisi sitten seuraavasti.

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_09.png)

Huomaa, koska kiertotavassa käytetään osavaltioita *Kaupunkidata*-taulukosta, vain taulukossa olevat *osavaltiot* luetellaan. Näin ollen Teksas on jäänyt pois. Lisäksi toisin kuin **monta yhteen** -yhteyksissä, summarivi sisältää kyllä kaikki *Myynti*-tiedot (myös Teksasin), mutta tietoihin ei sisälly tyhjää riviä, joka kattaa tällaiset ristiriitaiset rivit. Vastaavasti mukana ei olisi tyhjää riviä *Myynti*-tiedoille, joiden *Osavaltio*-arvo on null.

Jos *Kaupunki*-arvo lisättäisiin myös visualisointiin, *kaupunkikohtainen* asukasmäärä olisi toki tiedossa, mutta *Myynti*-tieto *kaupungille* vain toistaisi *Myynti*-tiedon vastaavalle *osavaltiolle* seuraavan kuvan tavoin. Näin normaalisti käykin ryhmiteltäessä sellaisen sarakkeen perusteella, joka ei liity johonkin koostettuun mittayksikköön.

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_10.png)

Jos uuden taulukon *Myynti*-tiedot määritettäisiin kaikkien *osavaltioiden* yhdistelmäksi tässä kiertokeinossa ja tehtäisiin näkyväksi kenttäluettelossa, sama visualisointi, joka näyttää *Osavaltio*-tiedot (uudessa taulukossa) sekä *asukasmäärän* ja *myynnin* kokonaisarvot, olisi seuraavanlainen.

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_11.png)

Tässä tapauksessa ja visualisoinnissa näytetyllä tavalla mukana olisivat *Texas* (*Myynti*-tieto mukana mutta tuntematon asukasmäärä) ja *New York* (tunnettu asukasmäärä mutta ei *Myynti-tietoa*). 

Kuten näet, tätä kiertokeino ei ollut paras mahdollinen ja se sisälsi monia ongelmia. Nämä ongelmat ratkaistiin **monta moneen -yhteyksillä**, kuten seuraavassa osiossa kuvataan.

## <a name="using-many-to-many-relationships-instead-of-the-workaround"></a>Monta moneen -yhteyksien käyttäminen kiertotavan sijaan

**Power BI Desktopin** heinäkuun 2018 versiosta alkaen voit yhdistää edellisessä osiossa kuvattuja taulukoita suoraan tarvitsematta turvautua mainittuun kiertotapaan. Nyt on mahdollista määrittää yhteyden kardinaliteetiksi **monta moneen**, mikä ilmaisee, ettei kumpikaan taulukko sisällä yksilöllisiä arvoja. Tällaisissa yhteyksissä voit edelleen hallita, mikä taulukko suodattaa toisen taulukon. Voit myös käyttää kaksisuuntaista suodatusta, jossa kumpikin taulukko suodattaa toista.  

> [!NOTE]
> Mahdollisuus luoda **monta moneen** -yhteyksiä on vielä esikatselutilassa, joten **monta moneen** -yhteyksiä käyttäviä malleja ei voi julkaista Power BI -palveluun. 

**Power BI Desktopissa** kardinaliteetin oletusarvoksi asetetaan **monta moneen**, kun havaitaan, ettei kumpikaan taulukko sisällä yksilöllisiä arvoja yhteyden sarakkeissa. Tässä tapauksessa näyttöön tulee varoitus, joka vahvistaa, että yhteysasetus on määritetty tarkoituksella, eikä kyse ole tieto-ongelman odottamaton seuraus. 

Jos luot *Kaupunkidata*- ja *Myynti*-taulukoiden välille suoran yhteyden, jossa tiedot suodatetaan *Kaupunkidata*-taulukosta *Myynti*-taulukkoon, näet seuraavan kuvan mukaisen Suhde-valintaikkunan.

![Muokkaa suhdetta -valintaikkuna](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Seuraava **suhdenäkymä** sisältäisi näin ollen suoran **monta moneen** -yhteyden kahden taulukon välillä. Ulkoasu **Kentät**-luettelossa ja myöhempi toiminta visualisointeja luotaessa on sama kuin käytettäessä edellisessä osiossa kuvattua kiertotapaa, jossa ylimääräinen taulukko yksilöllisine *osavaltioineen* ei ollut näkyvissä. Esimerkiksi – edellisen osan kiertotavan mukaisesti – visualisointi, joka kuvaa *osavaltioita* sekä asukkaiden kokonaismäärää ja myyntiä, näyttäisi seuraavalta.

![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_12.png)

**Monta moneen** -yhteyksien ja yleisempien **monta yhteen** -yhteyksien merkittävimmät erot ovat siis seuraavat.

* Näytetyt arvot eivät sisällä toisen taulukon ristiriitaisista riveistä johtuvaa tyhjää riviä tai rivejä, joissa yhteydessä käytettävä toisen taulukon sarake sisältää null-arvoja.
* *RELATED()*-funktion käyttäminen ei ole mahdollista, koska useampi kuin yksi rivi voi olla liittyvä.
* *ALL()*-funktion käyttäminen taulukossa ei poista suodattimia, joita käytetään taulukkoon **monta moneen** -yhteydellä yhdistetyissä muissa taulukoissa. Esimerkiksi edellisessä esimerkissä seuraavalla tavalla määritetty mittayksikkö ei poistaisi suodattimia sarakkeista yhdistetyssä *Kaupunkitiedot*-taulukossa:

    ![Komentosarjaesimerkki](media/desktop-many-to-many-relationships/many-to-many-relationships_13.png)

    Näin ollen visualisointi, jossa näytetään *Osavaltio*, *Myynti* ja *Kokonaismyynti*, näyttäisi seuraavalta:

    ![Taulukkovisualisointi](media/desktop-many-to-many-relationships/many-to-many-relationships_14.png)

Tämän vuoksi on varmistettava, että *ALL(\<Table>)*-funktiolla suoritetut laskutoimitukset, kuten *prosenttiosuus kokonaissummasta*, palauttavat tarkoitetut tulokset. 


## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Tämän version **monta moneen -yhteyksissä** ja **yhdistelmämalleissa** on muutamia rajoituksia.

Seuraavia monidimensioisia lähteitä ei voi käyttää **yhdistelmämallien** kanssa:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI -tietojoukot

Kun muodostetaan yhteyttä näihin monidimensioisiin lähteisiin DirectQuerylla, et voi muodostaa yhteyttä myös toiseen DirectQuery-lähteeseen tai yhdistää tuotuihin tietoihin.

DirectQueryn olemassa olevat käyttörajoitukset koskevat edelleen **monta moneen -yhteyksien** käyttämistä. Monet näistä rajoituksista ovat nyt taulukkokohtaisia ja riippuvat taulukon **tallennustilan tilasta**. Esimerkiksi tuodun taulukon laskettu sarake voi viitata muihin taulukoihin, mutta DirectQuery-taulukon laskettu sarake on yhä rajoitettu viittaamaan vain saman taulukon sarakkeisiin. Muut rajoitukset koskevat vain mallia kokonaisuutena, jos jokin mallin taulukoista on DirectQuery-taulukko. Esimerkiksi **Nopeat merkitykselliset tiedot**- ja **Q & A** -ominaisuudet eivät ole käytettävissä mallissa, jos jollakin sen taulukoista **tallennustilan tilana** on DirectQuery. 

## <a name="next-steps"></a>Seuraavat vaiheet

Seuraavissa artikkeleissa kerrotaan lisää yhdistelmämalleista ja kuvataan myös DirectQuery yksityiskohtaisemmin.

* [Yhdistelmämallit Power BI Desktopissa (esikatselu)](desktop-composite-models.md)
* [Tallennustilan tila Power BI Desktopissa (esikatselu)](desktop-storage-mode.md)

DirectQuery-artikkeleita:

* [DirectQueryn käyttäminen Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet Power BI:ssä](desktop-directquery-data-sources.md)

