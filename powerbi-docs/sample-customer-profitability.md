---
title: 'Asiakkaan tuottavuuden malli Power BI:lle: aloita esittely'
description: 'Asiakkaan tuottavuuden malli Power BI:lle: aloita esittely'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/23/2018
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 3dd4f5f0404737685757400202d3a92767e44189
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280833"
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Asiakkaan tuottavuuden malli Power BI:lle: aloita esittely

## <a name="overview-of-the-customer-profitability-sample"></a>Asiakkaan tuottavuuden mallin yleiskatsaus
Asiakkaan tuottavuuden malli -sisältöpaketti sisältää koontinäytön, raportin ja tietojoukon yritykselle, joka valmistaa markkinointimateriaalia. Talousjohtaja loi tämän koontinäytön nähdäkseen tärkeitä arvoja viidestä liiketoimintayksikön johtajasta, tuotteista, asiakkaista ja myyntikatteista. Hän näkee yhdellä vilkaisulla, mitkä tekijät vaikuttavat kannattavuuteen.

![power bi -koontinäyttö](media/sample-customer-profitability/power-bi-dash.png)

Tämä malli kuuluu sarjaan, jossa esitellään, miten Power BI:tä voidaan käyttää liiketoimintaan suuntautuneiden tietojen, raporttien ja koontinäyttöjen kanssa. Nämä ovat obviEnceltä ([www.obvience.com](http://www.obvience.com/)) saatuja oikeita tietoja, jotka on tehty nimettömiksi. Tiedot ovat käytettävissä useissa muodoissa: sisältöpaketti/sovellus, Excel-työkirja tai Power BI Desktopin .pbix-tiedosto. Katso [Mallitietojoukot](sample-datasets.md).

## <a name="prerequisites"></a>Edellytykset
Haluatko seurata mukana? Tässä opetusohjelmassa käytetään Power BI -palvelua ja Asiakkaan tuottavuuden malli -sisältöpakettia.  Koska raportin käyttökokemukset ovat niin samankaltaisia, voit myös seurata käyttäen Power BI Desktopia ja mallin PBIX-tiedostoa. Ohjeet sisältöpaketin ja PBIX-tiedoston yhdistämiseen ovat alla.

### <a name="get-the-content-pack-for-this-sample"></a>Mallin sisältöpaketin noutaminen

1. Avaa Power BI -palvelu (app.powerbi.com) ja kirjaudu sisään.
2. Valitse vasemmasta alakulmasta **Nouda tiedot**.

    ![hae tiedot](media/sample-datasets/power-bi-get-data.png)
3. Valitse ilmestyvältä Nouda tiedot -sivulta **Mallit**-kuvake.

   ![mallit-kuvake](media/sample-datasets/power-bi-samples-icon.png)
4. Valitse **Asiakkaan tuottavuuden malli** ja valitse sitten **Yhdistä**.  

   ![Nouda tiedot](media/sample-customer-profitability/get-supplier-sample.png)
5. Power BI tuo sisältöpaketin ja lisää uuden koontinäytön, raportin ja tietojoukon senhetkiseen työtilaasi. Uusi sisältö merkitään keltaisella tähdellä. Kokeile Power BI:n käyttöä mallien avulla.  

   ![Tähti](media/sample-customer-profitability/supplier-sample-asterisk.png)

### <a name="get-the-pbix-file-for-this-sample"></a>Hae tämän mallin .pbix-tiedosto

Vaihtoehtoisesti voit ladata näytteen .pbix-tiedostona, joka on suunniteltu käytettäväksi Power BI Desktopilla.
[Asiakkaan tuottavuuden malli](http://download.microsoft.com/download/6/A/9/6A93FD6E-CBA5-40BD-B42E-4DCAE8CDD059/Customer%20Profitability%20Sample%20PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Hae tämän näytteen Excel-työkirja

Jos haluat perehtyä tämän mallin tietolähteeseen, se on saatavana myös [Excel-työkirjana](http://go.microsoft.com/fwlink/?LinkId=529781). Työkirja sisältää Power View -taulukoita, joita voit tarkastella ja muokata. Raakatiedot saa näkyviin valitsemalla **Power Pivot > Hallinta**.


## <a name="what-is-our-dashboard-telling-us"></a>Mitä koontinäyttö kertoo?

Etsi **Oma työtila** -kohdasta asiakkaan tuottavuuden mallin koontinäyttö:

![Asiakkaan tuottavuuden mallin koontinäyttö](media/sample-customer-profitability/power-bi-dash.png)

### <a name="company-wide-dashboard-tiles"></a>Koko yrityksen laajuiset koontinäytön ruudut
1. Avaa koontinäyttö Power BI -palvelussa. Koontinäytön ruutujen avulla talousjohtaja saa kuvan korkean tason yritysarvoista, jotka ovat tärkeitä hänelle.  Kun hän näkee jotakin mielenkiintoista, hän voi valita ruudun ja perehtyä tietoihin tarkemmin.

2. Tarkista koontinäytön vasemmalla puolella olevat ruudut.

    ![ruudut esimiehille](media/sample-customer-profitability/power-bi-manager.png)

- Yrityksen myyntikate on 42,5.
- Asiakkaita on 80.
- Myynnissä on 5 eri tuotetta.
- Budjetointiin verrattuna tuoton varianssiprosentti oli pienin helmikuussa ja suurin maaliskuussa.
- Valtaosa tuotosta tulee itäisiltä ja pohjoisilta alueilta. Myyntikate ei ole koskaan ylittänyt budjettia. ER-0 ja MA-0 vaativat lisätutkimuksia.
- Vuoden kokonaistuotto on lähellä budjetoitua.


### <a name="manager-specific-dashboard-tiles"></a>Esimieskohtaiset koontinäytön ruudut
Koontinäytön oikeassa reunassa olevat ruudut sisältävät tiimin tuloskortin. Talousjohtajan on seurattava esimiehiä ja näiden ruutujen kautta hän näkee tuotosta korkean tason yleiskatsauksen käyttämällä myyntikatetta. Jos myyntikatetrendi on odottamaton kenelle tahansa esimiehelle, hän voi tutkia asiaa tarkemmin.

![myyntikate esimiehille](media/sample-customer-profitability/power-bi-manager2.png)

- Kaikki johtajat Carlosta lukuun ottamatta ovat jo ylittäneet myyntitavoitteensa. Mutta Carloksen toteutunut myynti on suurin.
- Annelien myyntikate on pienin, mutta kasvu oli tasaista maaliskuun jälkeen.
- Toisaalta Valeryn myyntikate on pudonnut huomattavasti.
- Andrew’n vuosi sisälsi heilahtelua.

## <a name="explore-the-dashboards-underlying-data"></a>Koontinäytön pohjana oleviin tietoihin perehtyminen
Tämä koontinäyttö sisältää ruutuja, jotka on yhdistetty raporttiin ja Excel-työkirjaan.

### <a name="open-the-excel-online-data-source"></a>Excel Online -tietolähteen avaaminen
Kaksi tämän koontinäytön ruutua, ”Tavoite vs. toteutunut” ja ”Tulojen kasvu vuosittain”, on kiinnitetty Excel-työkirjasta. Kun valitset jommankumman näistä ruuduista, Power BI avaa tietolähteen eli tässä tapauksessa Excel Onlinen.

![Excel online](media/sample-customer-profitability/power-bi-excel-online.png)

1. Valitse kumpi tahansa Excelistä kiinnitetyistä ruuduista. Excel Online avautuu Power BI -palvelussa.
2. Huomaa, että työkirjassa on 3 välilehteä täynnä tietoa. Avaa Tuotto.
3. Selvitetäänpä, miksi Carlos ei ole vielä saavuttanut tavoitettaan.  
    a. Valitse Johtaja-liukusäätimestä **Carlos Grilo**.   
    b. Ensimmäisen Pivot-taulukon mukaan Carloksen parhaan tuotteen Primuksen tuotto on pudonnut 152 % edellisestä vuodesta. Vuosittaisessa kaaviossa näkyy, että hän jää budjetoidun alle useimpina kuukausina.  

    ![Pivot-taulukko](media/sample-customer-profitability/power-bi-pivotchart.png)

    ![Carlosin tulokset](media/sample-customer-profitability/power-bi-carlos.png)

4. Jatka tutkimista. Jos löydät jotakin mielenkiintoista, valitse **Kiinnitä** ![kiinnitä-kuvake](media/sample-customer-profitability/power-bi-excel-pin.png) oikeassa yläkulmassa ja [kiinnitä se koontinäyttöön](service-dashboard-pin-tile-from-excel.md).

5. Palaa koontinäyttöön selaimen taaksepäin osoittavalla nuolella.

### <a name="open-the-underlying-power-bi-report"></a>Pohjana olevan Power BI -raportin avaaminen
Valtaosa Asiakkaan tuottavuuden mallin koontinäytön ruuduista on kiinnitetty pohjana olevasta Asiakkaan tuottavuuden mallin raportista.

1. Avaa raportti lukutilassa valitsemalla jokin näistä ruuduista.

2. Raportissa on 3 sivua. Raportin alareunan jokainen välilehti edustaa yhtä sivua.

    ![3 välilehteä alareunassa](media/sample-customer-profitability/power-bi-report-tabs.png)

    * Tiimin tuloskortissa keskitytään 5 johtajan suoritukseen ja asiakaskokoonpanoon.
    * Alakateanalyysin avulla on helppo analysoida kannattavuutta verrattuna koko alan kannattavuuteen.
    * Johtajan tuloskortti tarjoaa näkymän kustakin johtajasta muotoiltuna tarkastelua varten Cortanassa.

### <a name="team-scorecard-page"></a>Tiimin tuloskortti -sivu
![Tiimin tuloskortti -raporttisivu](media/sample-customer-profitability/customer2.png)

Seuraavaksi tarkastellaan kahta tiimin jäsentä yksityiskohtaisesti, jotta näemme, mitä merkityksellistä tietoa voidaan saada. Valitse vasemmalla olevasta osittajasta Andrew’n nimi, jotta raporttisivu suodatetaan näyttämään vain Andrew'n tiedot.

* Näet suorituskykyilmaisimen avulla nopeasti Andrew'n **tulotilan** – hän on vihreällä. Hän toimii hyvin.
* Tulovarianssiprosentti budjettiin kuukausittain -aluekaavio näyttää, että helmikuun pudotusta lukuun ottamatta Andrew tekee työnsä kaiken kaikkiaan melko hyvin. Hänen vahvin alueensa on itä ja hän käsittelee 49 asiakasta ja 5 (yhteensä 7) tuotetta. Hänen myyntikatteensa on keskitasoa.
* Koko vuoden tulot ja tulovarianssiprosentti budjettiin kuukausittain -raportti näyttää tasaisen tulokehityksen. Kun suodatat tiedot **Keski**-alueen mukaan alueen puukartassa, huomaat, että Andrew’lla on tuloa vain maaliskuussa ja vain Indianasta. Onko tämä tarkoituksellista vai pitääkö tähän perehtyä tarkemmin?

Siirrytään Valeryyn. Valitse osittajasta Valeryn nimi, jotta raporttisivu suodatetaan näyttämään vain Valeryn tiedot.  
![sektori johtajalle Valery Ushalov](media/sample-customer-profitability/customer3.png)

* Huomaa punainen suorituskykyilmaisin **Koko vuoden tulojen tilassa**. Tätä on ehdottomasti tutkittava tarkemmin.
* Hänen tulovarianssinsa muodostaa myös huolestuttavan kuvan – hän ei saavuta myyntikatettaan.
* Valerylla on vain 9 asiakasta, hän käsittelee vain 2 tuotetta ja hän työskentelee lähes yksinomaan pohjoisessa olevien asiakkaiden parissa. Tämä erikoistuminen saattaa selittää laajemman vaihtelun hänen arvoissaan.
* Kun puukartassa valitaan **Pohjoinen**-neliö, huomataan, että Valeryn myyntikate pohjoisessa on yhdenmukainen hänen yleistä katteensa kanssa.
* Kun valitaan toinen **Alue**-neliö, tilanne muuttuu mielenkiintoiseksi: hänen myyntikatteensa vaihtelee 23 prosentista 79 prosenttiin ja tuloluvut muilla alueilla pohjoista lukuun ottamatta vaihtelevat rajusti kausittain.

Jatketaan tietojen tutkimista, jotta saamme selville, miksi Valeryn alue ei toimi hyvin. Tarkastellaan alueita, muita liiketoimintayksiköitä ja raportin seuraavaa sivua eli Alakateanalyysia.

### <a name="industry-margin-analysis"></a>Alakateanalyysi
Tällä raporttisivulla tiedot ovat eri sektorista. Sivulla tarkastellaan koko alan myyntikatetta eriteltynä segmenteittäin. Talousjohtaja käyttää tätä sivua yrityksen ja liiketoimintayksikön arvojen vertaamiseen koko alan arvoihin. Tietojen avulla voidaan tutkia trendejä ja kannattavuutta. Saatat ihmetellä, miksi ”Myyntikate kuukauden ja johtajan nimen mukaan” -aluekaavio on tällä sivulla, koska se on tiimikohtainen. Kun se on täällä, voimme suodattaa sivun liiketoimintayksikön johtajan mukaan.  
![Alakateanalyysi-raporttisivu](media/sample-customer-profitability/customer6.png)

Miten kannattavuus vaihtelee aloittain? Miten tuotteet ja asiakkaat voidaan eritellä alan mukaan? Valitse vasemmasta yläkulmasta ainakin yksi toimiala. (Aloita kuluttajatuotteista.) Voit tyhjentää suodattimen valitsemalla Pyyhin-kuvakkeen.

Kuplakaaviossa talousjohtaja etsii suurimpia kuplia, koska niillä on suurin vaikutus tuloihin. Kun sivu suodatetaan johtajan mukaan napsauttamalla johtajan nimeä aluekaaviossa, on helppo nähdä kunkin johtajan vaikutus toimialan segmentin mukaan.

* Andrew'n vaikutusala kattaa useita eri toimialasegmenttejä erittäin vaihtelevilla myyntikatteilla (useimmat positiivisen puolella) ja varianssiprosenteilla.
* Annelien kaavio on samankaltainen sillä poikkeuksella, että hän keskittyy vain muutamiin toimialasegmentteihin (Valtio-segmentti ja Gladius-tuote).
* Carlos on selvästi keskittynyt Palvelut-segmenttiin ja tuotto on hyvällä tasolla. Hän on parantanut huomattavasti varianssiprosenttiaan korkean teknologian segmentissä ja hänelle uusi segmentti, Teollisuus, on toiminut poikkeuksellisen hyvin verrattuna budjetoituun.
* Tina tekee työtä useilla segmenteillä ja hänellä on korkein myyntikate, mutta hänen kupliensa pääosin pieni koko osoittaa, että hänen vaikutuksensa yrityksen tulokseen on vähäinen.
* Valery, jonka vastuulla on vain yksi tuote, toimii vain 5 toimialasegmentillä. Hänen toimialavaikutuksensa on kausittaista, mutta tuloksena on aina suuri kupla, mikä osoittaa, että vaikutus yrityksen tulokseen on merkittävä. Selittääkö ala hänen negatiivista suorituskykyään?

### <a name="executive-scorecard"></a>Johtajan tuloskortti
Tämä sivu on muotoiltu vastauskortiksi Cortanalle. Lisätietoja on artikkelissa [Vastauskorttien luominen Cortanalle](service-cortana-answer-cards.md).

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Tietoihin perehtyminen esittämällä kysymyksiä Q&A:ssa
Analyysia varten olisi hyödyllistä määrittää, mikä toimiala tuottaa eniten tuloja Valerylle. Käytetään Q&A-toimintoa.

1. Avaa raportti muokkausnäkymässä valitsemalla **Muokkaa raporttia**. Muokkausnäkymä on käytettävissä vain, jos omistat raportin. Tätä kutsutaan joskus **luontitilaksi**. Jos tämä raportti on sen sijaan jaettu kanssasi, et voi avata sitä muokkausnäkymässä.

2.  Valitse yläreunan valikkoriviltä **Esitä kysymys**, jotta Q&A-kysymysruutu avautuu.

    ![Esitä tietojasi koskeva kysymys](media/sample-customer-profitability/power-bi-ask-question.png)

3. Kirjoita **kokonaistulot alan mukaan: Valery**. Huomaa, miten visualisointi päivittyy, kun kirjoitat kysymyksen.

    ![kirjoita kysymys kysymysruutuun](media/sample-customer-profitability/power-bi-qna.png)

   Jakelu on Valeryn suurin tuottoalue.

### <a name="dig-deeper-by-adding-filters"></a>Pureudutaan syvemmälle lisäämällä suodattimia.
Tutustutaan *Jakelu*-alaan.  

1. Avaa Alakateanalyysi-raporttisivu.
2. Laajenna oikeassa reunassa oleva suodatinruutu (jos sitä ei ole vielä laajennettu) valitsematta mitään raporttisivun visualisointia. Suodattimet-ruudussa pitäisi näkyä vain sivutason suodattimet.  

   ![Sivutason suodattimet](media/sample-customer-profitability/power-bi-filters.png)
3. Etsi **Toimiala**-suodatin ja laajenna luettelo valitsemalla nuoli. Lisätään Jakelu-alaan sivutason suodatin. Poista ensin kaikki valinnat tyhjentämällä **Valitse kaikki** -valintaruutu. Valitse sitten vain **Jakelu.**  

   ![suodatin Jakelulle](media/sample-customer-profitability/customer7.png)
4. Myyntikate kuukauden ja johtajan nimen mukaan -aluekaavio näyttää, että vain Valerylla ja Tinalla on asiakkaita tällä toimialalla. Vain Valery on työskennellyt tämän toimialan parissa kesäkuusta marraskuuhun.   
5. Valitse **Tina** ja valitse sitten **Valery** Myyntikate kuukauden ja johtajan nimen mukaan -aluekaavion selitteessä. Huomaa, että Tinan osuus Kokonaistuotto tuotteittain -arvosta on erittäin pieni verrattuna Valeryyn.
6. Näet todelliset tulot esittämällä Q&A:ssa kysymyksen **kokonaistulot johtajan mukaan: jakauma skenaariokohtaisesti**.  

     ![tuo palkkikaavio näkyviin kirjoittamalla kysymys kysymysruutuun](media/sample-customer-profitability/power-bi-qna2.png)

    Voimme tutkia vastaavasti muita aloja ja jopa lisätä asiakkaita visualisointeihin, jotta ymmärrämme Valeryn suorituskyvyn syyt.

Tämä on turvallinen ympäristö kaikenlaisille kokeiluille. Voit aina jättää tekemäsi muutokset tallentamatta. Jos kuitenkin tallennat ne, voit aina siirtyä **Nouda tiedot** -kohtaan, jolloin saat mallista uuden kopion.

Voit myös [ladata vain tietojoukon (Excel-työkirjan) tälle mallille](http://go.microsoft.com/fwlink/?LinkId=529781).

## <a name="next-steps-connect-to-your-data"></a>Seuraavat vaiheet: Yhdistä tietoihisi
Toivomme, että tämä esittely on osoittanut, miten Power BI -koontinäytöt, kysymysosio ja raportit voivat tarjota uusia näkökulmia asiakastietoihin. Nyt sinun vuorosi – muodosta yhteys omiin tietoihisi. Power BI:n avulla voit yhdistää useita eri tietolähteitä. Lisätietoja [Power BI:n käytön aloittamisesta](service-get-started.md).

[Takaisin malleihin Power BI:ssä](sample-datasets.md)  
