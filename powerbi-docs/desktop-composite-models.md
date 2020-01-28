---
title: Yhdistelmämallien käyttäminen Power BI Desktopissa
description: Tietomallien luominen useilla tietoyhteyksillä ja monta moneen -yhteyksillä Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 45f7ecee11cd57a73ed0e998dad26935b560c8ad
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/17/2020
ms.locfileid: "76161203"
---
# <a name="use-composite-models-in-power-bi-desktop"></a>Yhdistelmämallien käyttäminen Power BI Desktopissa

Kun aiemmin Power BI Desktopissa käytit DirectQuerya raportissa, muita tietoyhteyksiä, DirectQuerya tai tuontia, ei sallittu tälle raportille. Yhdistelmämalleissa tämä rajoitus on poistettu. Raporttiin voi saumattomasti sisällyttää tietoyhteyksiä useasta DirectQuerysta tai tietojen tuontiyhteydestä valittuna yhdistelmänä.

Power BI Desktopin yhdistelmämallit koostuvat kolmesta toisiinsa liittyvästä ominaisuudesta:

* **Yhdistelmämallit**: antavat mahdollisuuden sisällyttää raporttiin useita tietoyhteyksiä, kuten DirectQuery-yhteydet tai tuonnin, millaisina tahansa yhdistelminä. Tässä artikkelissa kuvataan tarkemmin yhdistelmämallit.

* **Monta-moneen-yhteys**: Yhdistelmämallien avulla voit määrittää taulukoiden välille *monta-moneen-yhteyksiä*. Tämä lähestymistapa poistaa vaatimuksen siitä, että taulukoiden arvojen pitäisi olla yksilöllisiä. Se myös poistaa edelliset ratkaisut, kuten uusien taulukoiden lisäämisen vain yhteyksien muodostamiseksi. Jos haluat lisätietoja, katso [Monta-moneen-yhteyksien käyttö Power BI Desktopissa](desktop-many-to-many-relationships.md).

* **Tallennustilan tila**: Voit nyt määrittää, mitkä visualisoinnit tekevät kyselyjä taustatietolähteisiin. Visualisoinnit, jotka eivät edellytä kyselyä, tuodaan, vaikka ne perustuisivat DirectQueryyn. Tämä ominaisuus parantaa suorituskykyä ja vähentää taustakuormitusta. Aiemmin jopa osittajien kaltaiset yksinkertaiset visualisoinnit käynnistivät taustalähteisiin suunnattuja kyselyjä. Lisätietoja on kohdassa [Tallennustilan hallinta Power BI Desktopissa](desktop-storage-mode.md).

## <a name="use-composite-models"></a>Yhdistelmämallien käyttäminen

Yhdistelmämalleilla voit muodostaa yhteyden monenlaisiin tietolähteisiin, kun käytät Power BI Desktopia tai Power BI -palvelua. Voit tehdä nämä tietoyhteydet muutamalla eri tavalla:

* Tuomalla tiedot Power BI:hin, mikä on yleisin tapa hakea tietoja.
* Muodostamalla yhteyden suoraan tietoihin niiden alkuperäisessä lähdesäilössä käyttämällä DirectQueryä. Katso lisätietoja DirectQuerystä kohdasta [ DirectQuery Power BI:ssä](desktop-directquery-about.md).

DirectQuerya käytettäessä yhdistelmämalleilla on mahdollista luoda Power BI -malli, kuten Power BI Desktopin yksittäinen *.pbix*-tiedosto, joka toimii jommallakummalla tai kummallakin seuraavista toiminnoista:

* yhdistää tietoja yhdestä tai useammasta DirectQuery-lähteestä
* yhdistää tietoja DirectQuery-lähteistä ja tuotuja tietoja.

Yhdistelmämalleilla voit esimerkiksi luoda mallin, joka yhdistää seuraavat tietotyypit:

* Yrityksen tietovaraston myyntitiedot.
* Osaston SQL Server -tietokannan myyntikohdetiedot.
* Tiedot, jotka on tuotu laskentataulukosta.

Sellaista mallia, johon yhdistetään useamman kuin yhden DirectQuery-lähteen tietoja ja tuotuja tietoja, kutsutaan yhdistelmämalliksi.

Voit entiseen tapaan luoda suhteita taulukoiden välille, vaikka nämä taulukot olisivat peräisin eri lähteistä. Kaikki eri lähteitä käyttävät suhteet luodaan käyttäen kardinaliteettia monta moneen riippumatta niiden todellisesta kardinaliteetista. Voit vaihtaa kardinaliteetiksi yksi moneen, monta yhteen tai yksi yhteen. Minkä kardinaliteetin sitten määritätkin, ristiinlähdesuhteilla on eri käytös. Et voi käyttää Data Analysis Expressions (DAX) -toimintoja `one`-puolen arvojen noutamiseen `many`-puolelta. Saatat myös huomata suorituskykyeroavaisuuksia verrattuna saman lähteen sisäisiin monta moneen -suhteisiin.

> [!NOTE]
> Yhdistelmämallien kontekstissa kaikki tuodut taulukot ovat käytännössä yksittäinen tietolähde riippumatta taustalla olevasta tietolähteesta.

## <a name="example-of-a-composite-model"></a>Yhdistelmämallin esimerkki

Yhdistelmämallin esimerkkinä voidaan ajatella raporttia, joka on yhteydessä yrityksen tietovarastoon SQL Serverissä DirectQueryn avulla. Tässä tapauksessa tietovarasto sisältää **myynnin maan mukaan**, **vuosineljänneksen** ja **polkupyörän (tuote)** tietoja, seuraavassa kuvassa esitetyllä tavalla:

![Yhdistelmämallien suhdenäkymä](media/desktop-composite-models/composite-models_04.png)

Tässä vaiheessa voit luoda yksinkertaisia visualisointeja, joissa käytetään tästä lähteestä peräisin olevia kenttiä. Seuraava kuva näyttää myynnin kokonaismäärän *Tuotenimi*-tiedon mukaan valitulla vuosineljänneksellä.

![Tietoihin perustuva visualisointi](media/desktop-composite-models/composite-models_05.png)

Mutta entä jos sinulla on Office Excel -laskentataulukossa tietoja kullekin tuotteelle määritetystä tuotepäälliköstä sekä markkinointiprioriteetista? Jos haluat tarkastella **myynnin määrää** **tuotepäällikön mukaan**, näitä paikallisia tietoja ei ehkä voi lisätä yrityksen tietovarastoon. Tai ainakin siinä kestäisi todella kauan.

Myyntitiedot voidaan ehkä tuoda tietovarastosta DirectQueryn käyttämisen sijasta. Myyntitiedot voidaan sitten yhdistää tietoihin, jotka toit laskentataulukosta. Tämä lähestymistapa on kuitenkin kohtuuton johtuen syistä, joiden vuoksi DirectQueryä alun perin käytettiin. Syitä voivat olla seuraavat:

* Pohjana olevan tietolähteen suojaussääntöjen yhdistelmä.
* Tarve tarkastella uusimpia tietoja.
* Tietojen suuri määrä.

Yhdistelmämallit ratkaisevat tämän ongelman. Yhdistelmämallit antavat mahdollisuuden muodostaa yhteys tietovarastoon käyttämällä DirectQueryä ja noutaa sitten tietoa muista lähteistä **Get data**lla. Tässä esimerkissä muodostetaan ensin DirectQuery-yhteys yrityksen tietovarastoon. Käytämme **Get data**a, valitsemme **Excel**in ja siirrymme sitten paikalliset tiedot sisältävään laskentataulukkoon. Lopuksi tuomme laskentataulukon, joka sisältää *tuotenimet*, määritetyt **myyntipäälliköt** ja **prioriteetin**.  

![Siirtymistoimintoikkuna](media/desktop-composite-models/composite-models_06.png)

**Kentät**-luettelossa on kaksi taulukkoa: alkuperäinen **Polkupyörä**-taulukko SQL Serveristä ja uusi **Tuotepäälliköt**-taulukko. Uusi taulukko sisältää tietoja, jotka on tuotu Excelistä.

![Taulukoiden kenttänäkymä](media/desktop-composite-models/composite-models_07.png)

Power BI Desktopin **suhdenäkymässä** voimme vastaavasti nähdä lisätaulukon nimeltä**Tuotepäälliköt**.

![Taulukoiden suhdenäkymä](media/desktop-composite-models/composite-models_08.png)

Meidän on nyt liitettävä nämä taulukot mallin muihin taulukoihin. Kuten aina, luomme suhteen SQL Serverin **Polkupyörä**-taulukon ja tuodun **Tuotepäälliköt**-taulukon välille. Suhde on välillä **Polkupyörä [Tuotenimi]** ja **Tuotepäälliköt [Tuotenimi]** . Aiemmin kuvatulla tavalla kaikissa lähteiden välisissä suhteissa on oletusarvona monta moneen -kardinaliteetti.

![Luo suhde -ikkuna](media/desktop-composite-models/composite-models_09.png)

Kun tämä suhde on luotu, se näkyy Power BI Desktopin **suhdenäkymässä**.

![Uusi suhdenäkymä](media/desktop-composite-models/composite-models_10.png)

Voimme nyt luoda visualisointeja käyttämällä **Kentät**-luettelon kenttiä. Tämä lähestymistapa yhdistää saumattomasti tietoja useista lähteistä. Esimerkiksi *myyntimäärän* summa kullekin *tuotepäällikölle* näkyy seuraavassa kuvassa:

![Kentät-ruutu](media/desktop-composite-models/composite-models_11.png)

Seuraavassa esimerkissä esitetään yleinen tapaus, jossa on *dimensiotaulukko*, kuten **Tuote** tai **Asiakas**, joka laajennetaan joillakin muualta tuoduilla lisätiedoilla. On myös mahdollista käyttää DirectQueryä yhteyden muodostamiseksi eri lähteisiin. Oletetaan esimerkkitaulukon jatkamiseksi, että **maa**- ja **kausikohtaiset** **myyntitavoitteet** tallennetaan erilliseen osastokohtaiseen tietokantaan. Voit muodostaa yhteyden näihin tietoihin **Get data**a käyttämällä tavalliseen tapaan seuraavassa kuvassa esitetyllä tavalla.

![Siirtymistoimintoikkuna](media/desktop-composite-models/composite-models_12.png)

Voimme aiemmin näytetyllä tavalla luoda suhteet uuden taulukon ja mallin muiden taulukoiden välille sekä luoda visualisointeja, jotka yhdistävät nämä taulukon tiedot. **Suhdenäkymässä** näemme uudet muodostetut yhteydet:

![Suhdenäkymä, jossa on useita taulukoita](media/desktop-composite-models/composite-models_13.png)

Seuraava kuva perustuu uusiin tietoihin ja suhteisiin, jotka loimme. Vasemmassa alakulmassa oleva visualisointi näyttää yhteensä *myynnin kokonaismäärän* verrattuna *tavoitteeseen*, ja varianssin laskelma näyttää eron. **Myynnin määrän** ja **tavoitteen** tiedot ovat peräisin kahdesta eri SQL Server -tietokannasta.

![Kuva, jossa näkyy enemmän tietoja](media/desktop-composite-models/composite-models_14.png)

## <a name="set-the-storage-mode"></a>Tallennustilan tilan määrittäminen

Jokaisella yhdistelmämallin taulukolla on tallennustilan tila, joka ilmaisee, onko taulukko DirectQuery- vai tuontipohjainen. Tallennustilan tilaa voi tarkastella ja muokata **Ominaisuus**-ruudussa. Tuo tallennustilan tila näkyviin napsauttamalla taulukkoa hiiren kakkospainikkeella **Kentät**-luettelossa ja valitse sitten **Ominaisuudet**. Seuraavassa kuvassa näytetään **Myyntitavoitteet**-taulukon tallennustilan tila.

Tallennustilan tilan voi nähdä myös kunkin taulukon työkaluvihjeessä.

![Työkaluvihje, joka näyttää tallennustilan tilan](media/desktop-composite-models/composite-models_16.png)

Kaikille Power BI Desktop -tiedostoille ( *.pbix*-tiedostoille), jotka sisältävät joitakin DirectQuery-taulukoita ja joitakin tuontitaulukoita, tilarivin ilmaisema tallennustilan tila on **Yhdistelmä**. Voit napsauttaa kyseistä termiä tilarivillä ja vaihtaa kaikki taulukot tuontitaulukoiksi.

Lisätietoja tallennustilasta löytyy artikkelista [Tallennustilan hallinta Power BI Desktopissa](desktop-storage-mode.md).  

> [!NOTE]
> Voit käyttää *yhdistelmätallennustilan* tilaa Power BI Desktopissa ja Power BI -palvelussa.

## <a name="calculated-tables"></a>Lasketut taulukot

Voit lisätä laskettuja taulukoita malliin, joka käyttää DirectQueryä. Data Analysis Expressions (DAX), joka määrittää lasketun taulukon, voi viitata joko tuonti- tai DirectQuery-taulukoihin tai niiden yhdistelmiin.

Lasketut taulukot ovat aina tuotuja, ja näiden taulukoiden tiedot päivitetään, kun taulukot päivitetään. Jos laskettu taulukko viittaa DirectQuery-taulukkoon, DirectQuery-taulukkoon viittaavat visualisoinnit näyttävät aina uusimmat arvot taustalla olevassa tietolähteessä. Sen sijaan visualisoinnit, jotka viittaavat laskettuun taulukkoon, näyttävät arvot siltä ajalta, kun laskettu taulukko on viimeksi päivitetty.

## <a name="security-implications"></a>Vaikutukset tietoturvaan

Yhdistelmämalleilla on tiettyjä vaikutuksia tietoturvaan. Yhteen tietolähteeseen lähetetty kysely voi sisältää arvoja, jotka on noudettu toisesta lähteestä. Aiemmassa esimerkissä visualisointi, joka näyttää **myynnin määrän** **tuotepäällikön** mukaan, lähettää SQL-kyselyn Myynti-relaatiotietokantaan. SQL-kysely saattaa sisältää tuotepäälliköiden nimet ja niihin liittyvät tuotteet.

![Komentosarja, joka näyttää vaikutukset tietoturvaan](media/desktop-composite-models/composite-models_17.png)

Laskentataulukkoon tallennettuja tietoja sisältyy nyt kyselyyn, joka lähetetään relaatiotietokantaan. Jos nämä tiedot ovat luottamuksellisia, sinun on pohdittava asiaa tietoturvan kannalta. Ota erityisesti huomioon seuraavat asiat:

* Kaikki tietokannan järjestelmänvalvojat, jotka voivat tarkastella jäljityksiä tai valvontalokeja, voivat nähdä nämä tiedot, vaikka heillä ei olisi alkuperäisen tietolähteen käyttöoikeuksia. Tässä esimerkissä järjestelmänvalvoja tarvitsee Excel-tiedoston käyttöoikeudet.

* Kunkin lähteen salausasetukset tulee huomioida. Haluat välttää tietojen noutamista yhdestä lähteestä salatulla yhteydellä ja niiden sisällyttämistä tahattomasti kyselyyn, joka lähetetään toiseen lähteeseen salaamattomalla yhteydellä.

Kun luot yhdistelmämallin, Power BI Desktop näyttää varoituksen, joka kehottaa sinua ottamaan huomioon kaikki mahdolliset tietoturvavaikutukset.  

Vastaavista syistä varovaisuuteen on aihetta, kun avataan epäluotettavasta lähteestä lähetettyjä Power BI Desktop -tiedostoja. Jos tiedostossa on yhdistelmämalleja, yhdestä lähteestä haetut tiedot, jotka haetaan tiedoston avaavan käyttäjän tunnistetiedoilla, lähetetään toiseen tietolähteeseen kyselyn osana. Tietoja voi tällöin tarkastella haitallisen Power BI Desktop -tiedoston tekijä. Power BI Desktop näyttää varoituksen, kun avaat Power BI Desktop -tiedoston, joka sisältää useita lähteitä. Tämä varoitus on samanlainen kuin se, jonka näet avatessasi alkuperäisiä SQL-kyselyitä sisältävän tiedoston.  

## <a name="performance-implications"></a>Vaikutukset suorituskykyyn  

DirectQueryä käytettäessä suorituskyky on aina otettava huomioon ensisijassa sen varmistamiseksi, että taustalähteellä on riittävästi resursseja hyvän käyttökokemuksen tarjoamiseen. Hyvä käyttökokemus tarkoittaa, että visualisoinnit päivittyvät enintään viidessä sekunnissa. Lisätietoja suorituskyvystä on kohdassa [DirectQueryn käyttö Power BI:ssä](desktop-directquery-about.md).

Yhdistelmämallien käyttäminen tuo mukanaan myös muita suorituskykyyn liittyviä huomionarvoisia seikkoja. Yksittäinen visualisointi voi saada aikaan kyselyiden lähettämisen useisiin lähteisiin, mikä usein välittää tulokset yhdestä kyselystä toiseen lähteeseen. Tällainen tilanne voi tuottaa seuraavanlaisia suorituksia:

* **SQL-kysely, joka sisältää suuren määrän literaaliarvoja**: Esimerkiksi visualisoinnille, joka pyytää **kokonaissummaa** joukolle valittuja **tuotepäälliköitä**, on ensin löydettävä, mitkä **tuotteet** näille tuotepäälliköille on määritetty. Tämän on tapahduttava ennen kuin visualisointi lähettää SQL-kyselyn, joka sisältää kaikki tuotetunnukset `WHERE`-lausekkeessa.

* **SQL-kysely, joka tekee kyselyn alemmalla rakeisuustasolla ja jossa tiedot koostetaan myöhemmin paikallisesti**: Kun **tuotteiden** määrä, joka täyttää **tuotepäällikön** suodatusehdot, muodostuu suureksi, kaikkia tuotteita ei ehkä kannata sisällyttää `WHERE`-lausekkeeseen. Sen sijaan voit tehdä kyselyn relaatiolähteeseen **tuotteiden** alemmalla tasolla ja koostaa sitten tulokset paikallisesti. Jos **Tuotteet**-taulukon kardinaliteetti ylittää miljoonan rajan, kysely epäonnistuu.

* **Useita SQL-kyselyjä, yksi per ryhmä arvon mukaan**: Kun koostaminen käyttää **DistinctCount**-arvoa toisen lähteen jonkin sarakkeen ryhmittelemänä, ja jollei ulkoinen lähde tue ryhmittelyn määrittävien useiden literaaliarvojen tehokasta välittämistä, on lähetettävä yksi SQL-kysely per ryhmä arvon mukaan.

   Visualisointi pyytää erillistä **Asiakastilinumero**-määrää SQL Server -taulukosta **tuotepäällikköjen** mukaan laskentataulukosta tuotuna. Silloin visualisoinnin on välitettävä **Tuotepäälliköt**-taulukon tiedot SQL Serveriin lähetettävässä kyselyssä. Esimerkiksi Redshiftin kaltaisissa muissa lähteissä tämä ei olisi mahdollista. Sen sijaan lähetettäisiin yksi SQL-kysely per **myyntipäällikkö** johonkin käytännölliseen rajaan asti, jonka ylittämisen jälkeen kysely epäonnistuu.

Jokaisella näistä tapauksista on suorituskykyyn omat vaikutuksensa, joiden yksityiskohdat vaihtelevat tietolähteittäin. Jos kahden lähteen yhdistämiseen käyttävien sarakkeiden kardinaliteetti säilyy alhaisena, muutamassa tuhannessa, suorituskyvyn ei pitäisi heiketä. Tämän kardinaliteetin kasvaessa sinun tulee kiinnittää enemmän huomiota suorituskykyyn.

Lisäksi monta moneen -yhteyksien käyttäminen tarkoittaa, että jokaista summan tai välisumman tasoa varten on lähetettävä erilliset kyselyt pohjana olevaan tietolähteeseen – sen sijaan, että yksityiskohtaiset arvot koostettaisiin paikallisesti. Sellaisenaan kokonaisarvoja sisältävä yksinkertainen taulukkovisualisointi lähettäisi yhden sijaan kaksi SQL-kyselyä.

## <a name="limitations-and-considerations"></a>Rajoitukset ja huomioitavat asiat

Yhdistelmämalleissa on muutamia rajoituksia:

Tällä hetkellä yhdistelmämallien [asteittaista päivittämistä](service-premium-incremental-refresh.md) tuetaan vain SQL-, Oracle- ja Teradata-tietolähteiden yhteyksissä.

Seuraavia Live Connectin monidimensiolähteitä ei voi käyttää yhdistelmämallien kanssa:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI -tietojoukot
* Azure Analysis Services

Kun muodostat yhteyttä näihin monidimensioisiin lähteisiin DirectQueryllä, et voi muodostaa yhteyttä myös toiseen DirectQuery-lähteeseen tai yhdistää sitä tuotuihin tietoihin.

DirectQueryn olemassa olevat käyttörajoitukset koskevat edelleen yhdistelmämallien käyttämistä. Monet näistä rajoituksista ovat nyt taulukkokohtaisia ja riippuvat taulukon tallennustilan tilasta. Esimerkiksi tuodun taulukon laskettu sarake voi viitata muihin taulukoihin, mutta DirectQuery-taulukon laskettu sarake voi viitata vain saman taulukon sarakkeisiin. Muut rajoitukset koskevat vain mallia kokonaisuutena, jos jokin mallin taulukoista on DirectQuery-taulukko. Esimerkiksi Nopeat merkitykselliset tiedot- ja Q & A -ominaisuudet eivät ole käytettävissä mallissa, jos jollakin sen taulukoista tallennustilan tilana on DirectQuery.

## <a name="next-steps"></a>Seuraavat vaiheet

Seuraavissa artikkeleissa on lisätietoja yhdistelmämalleista ja DirectQuerysta:

* [Moni-moneen-yhteydet Power BI Desktopissa](desktop-many-to-many-relationships.md)
* [Tallennustilan tila Power BI Desktopissa](desktop-storage-mode.md)
* [DirectQueryn käyttö Power BI:ssä](desktop-directquery-about.md)
* [DirectQueryn tukemat tietolähteet Power BI:ssä](desktop-directquery-data-sources.md)

