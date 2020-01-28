---
title: Monta-moneen-suhteen ohjeet
description: Ohjeita monta-moneen-suhteiden kehittämiseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/25/2019
ms.author: v-pemyer
ms.openlocfilehash: 6ce82516413fe43cfbc1336e2f6f51003277fb4a
ms.sourcegitcommit: 3d6b27e3936e451339d8c11e9af1a72c725a5668
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/17/2020
ms.locfileid: "76161290"
---
# <a name="many-to-many-relationship-guidance"></a>Monta-moneen-suhteen ohjeet

Tämä artikkeli on tarkoitettu tietojen mallintajille, jotka käyttävät Power BI Desktopia. Tässä kuvataan kolme erilaista monta-moneen-mallinnusskenaariota. Lisäksi tässä annetaan ohjeet niiden onnistuneeseen suunnitteluun malleissasi.

> [!NOTE]
> Tämä artikkeli ei sisällä mallien suhteiden johdantoa. Jos et ole täysin perehtynyt suhteisiin, niiden ominaisuuksiin tai niiden määrittämiseen, suosittelemme, että luet ensin [Mallien suhteet Power BI Desktopissa](../desktop-relationships-understand.md) -artikkelin.
>
> Lisäksi on tärkeää, että ymmärrät tähtirakenteen periaatteet. Lisätietoja on artikkelissa [Tutustu tähtirakenteeseen ja sen merkitykseen Power BI:ssä](star-schema.md).

Monta-moneen-skenaarioita on itse asiassa kolme. Ne ilmenevät, kun teet seuraavaa:

- [liität kaksi dimensiotyyppistä taulukkoa](#relate-many-to-many-dimensions)
- [liität kaksi faktatyyppistä taulukkoa](#relate-many-to-many-facts)
- [liität yksityiskohtaiset faktatyyppiset taulukot](#relate-higher-grain-facts), kun faktatyyppinen taulukko sisältää yksityiskohtaisempia rivejä kuin dimensiotyyppisen taulukon rivit

## <a name="relate-many-to-many-dimensions"></a>Liitä monta-moneen-dimensiot

Käsitellään ensimmäistä monta-moneen-skenaariotyyppiä esimerkin avulla. Klassinen skenaario yhdistää kaksi entiteettiä: pankin asiakkaat ja pankkitilit. Ajattele, että asiakkailla voi olla useita tilejä ja tileillä voi olla useita asiakkaita. Kun tilillä on useita asiakkaita, heitä kutsutaan _yhteistilin haltijoiksi_.

Näiden entiteettien mallintaminen on yksinkertaista. Toinen dimensiotyyppinen taulukko sisältää tilit ja toinen dimensiotyyppinen taulukko sisältää asiakkaat. Dimensiotyyppisille taulukoille ominaisesti jokaisessa taulukossa on tunnussarake. Jos haluat mallintaa kahden taulukon välisen suhteen, tarvitset kolmannen taulukon. Tätä taulukkoa kutsutaan yleensä _välitaulukoksi_. Tässä esimerkissä sen tehtävänä on tallentaa yksi rivi jokaista asiakastililiitosta kohti. Kun tämä taulukko sisältää vain tunnussarakkeita, sitä kutsutaan [_faktattomaksi faktataulukoksi_](star-schema.md#factless-fact-tables).

Tässä on yksinkertainen mallikaavio kolmesta taulukosta.

![Mallikaavio sisältää kolme taulukkoa. Rakenne kuvataan seuraavassa kappaleessa.](media/relationships-many-to-many/bank-account-customer-model-example.png)

Ensimmäisen taulukon nimi on **Account**, ja se sisältää kaksi saraketta: **AccountID** ja **Account**. Toisen taulukon nimi on **AccountCustomer**, ja se sisältää kaksi saraketta: **AccountID** ja **CustomerID**. Kolmannen taulukon nimi on **Customer**, ja se sisältää kaksi saraketta: **CustomerID** ja **Customer**. Minkään taulukoiden välillä ei ole suhteita.

Kaksi yksi-moneen-suhdetta lisätään taulukoiden liittämiseksi. Tässä on päivitetty mallikaavio liitetyistä taulukoista. **Transaction**-niminen faktatyyppinen taulukko on lisätty. Siihen tallennetaan tilitapahtumat. Välitaulukko ja kaikki tunnussarakkeet on piilotettu.

![Mallikaaviossa on nyt neljä taulukkoa. Yksi-moneen-suhteita on lisätty kaikkien taulukoiden liittämiseksi.](media/relationships-many-to-many/bank-account-customer-model-related-tables-1.png)

Mallikaaviota on muokattu näyttämään taulukon rivit, jotta pystymme paremmin kuvaamaan suhteiden suodatuksen levittämistä.

> [!NOTE]
> Taulukon rivejä ei voida näyttää Power BI Desktop -mallikaaviossa. Tässä artikkelissa niin on kuitenkin tehty, jotta voidaan antaa selkeitä esimerkkejä keskustelun tueksi.

![Mallikaaviossa näkyy nyt taulukon rivit. Rivien tiedot kerrotaan seuraavassa kappaleessa.](media/relationships-many-to-many/bank-account-customer-model-related-tables-2.png)

Neljän taulukon rivien tiedot kerrotaan seuraavassa luettelossa:

- **Account**-taulukossa on kaksi riviä:
  - **AccountID** 1 liittyy tiliin Account-01
  - **AccountID** 2 liittyy tiliin Account-02
- **Customer**-taulukossa on kaksi riviä:
  - **CustomerID** 91 liittyy asiakkaaseen Customer-91
  - **CustomerID** 92 liittyy asiakkaaseen Customer-92
- **AccountCustomer**-taulukossa on kolme riviä:
  - **AccountID** 1 liittyy tunnukseen **CustomerID** 91
  - **AccountID** 1 liittyy tunnukseen **CustomerID** 92
  - **AccountID** 3 liittyy tunnukseen **CustomerID** 92
- **Transaction**-taulukossa on kolme riviä:
  - **Date** 1. tammikuuta 2019, **AccountID** 1, **Amount** 100
  - **Date** 2. helmikuuta 2019, **AccountID** 2, **Amount** 200
  - **Date** 3. maaliskuuta 2019, **AccountID** 1, **Amount** -25

Katsotaan, mitä tapahtuu, kun malliin tehdään kysely.

Alla on kaksi visualisointia, joissa esitetään yhteenveto **Transaction**-taulukon **Amount**-sarakkeesta. Ensimmäinen visualisointi on ryhmitelty tilin mukaan, joten **Amount**-sarakkeiden summa vastaa _tilin saldoa_. Toinen visualisointi on ryhmitelty asiakkaan mukaan, joten **Amount**-sarakkeiden summa vastaa _asiakkaan saldoa_.

![Kaksi raportin visualisointia esitetään rinnakkain. Visualisoinnit kuvataan seuraavassa kappaleessa.](media/relationships-many-to-many/bank-account-customer-model-queried-1.png)

Ensimmäisen visualisoinnin nimi on **Account Balance**, ja siinä on kaksi saraketta: **Account** ja **Amount**. Se näyttää seuraavan tuloksen:

- Account-01:n saldo on 75
- Account-02:n saldo on 200
- Kokonaissumma on 275

Toisen visualisoinnin nimi on **Customer Balance**, ja siinä on kaksi saraketta: **Customer** ja **Amount**. Se näyttää seuraavan tuloksen:

- Customer-91:n saldo on 275
- Customer-92:n saldo on 275
- Kokonaissumma on 275

Nopea silmäys taulukon riveihin ja **Account Balance** -visualisointiin kertoo, että tilien ja kokonaissumman tulos on oikea. Tämä johtuu siitä, että tilien ryhmittely johtaa suodatuksen levittämiseen kyseisen tilin **Transaction**-taulukkoon.

Kaikki ei kuitenkaan ole oikein **Customer Balance** -visualisoinnissa. **Customer Balance** -visualisoinnin molemmilla asiakkailla on sama saldo kuin kokonaissaldo. Tämä tulos voi olla oikea vain, jos kaikki asiakkaat ovat kaikkien tilien yhteisiä tilinhaltijoita. Näin ei ole tässä esimerkissä. Ongelma liittyy suodatuksen levittämiseen. Se ei ole levinnyt **Transaction**-taulukkoon.

Noudata suhteiden suodatuksen suuntaa **Customer**-taulukosta **Transaction**-taulukkoon. On selvää, että **Account**- ja **AccountCustomer**-taulukoiden välinen suhde leviää väärään suuntaan. Tämän suhteen suodatuksen suunnaksi on asetettava **Molemmat**.

![Mallikaaviota on päivitetty. Account- ja AccountCustomer-taulukoiden väliseen suhteeseen on tehty yksi muutos. Suodatus toimii nyt molempiin suuntiin.](media/relationships-many-to-many/bank-account-customer-model-related-tables-3.png)

![Kaksi samaa raportin visualisointia esitetään rinnakkain. Ensimmäistä visualisointia ei ole muutettu. Toisessa visualisoinnissa näkyy eri tulos, ja se kuvataan seuraavissa kappaleissa.](media/relationships-many-to-many/bank-account-customer-model-queried-2.png)

**Account Balance** -visualisoinnissa ei ole odotetusti tapahtunut muutoksia.

**Customer Balance** -visualisoinnissa näkyy kuitenkin nyt seuraava tulos:

- Customer-91:n saldo on 75
- Customer-92:n saldo on 275
- Kokonaissumma on 275

**Customer Balance** -visualisoinnissa näkyy nyt oikea tulos. Noudata itse suodatussuuntaa ja katso, miten asiakkaiden saldot laskettiin. Huomioi myös se, että näkyvä kokonaismäärä tarkoittaa _kaikkia asiakkaita_.

Joku, joka ei tunne mallien suhteita, voisi päätellä, että tulos on virheellinen. Hän saattaisi kysyä seuraavaa: _Miksi **Customer-91:n** ja **Customer-92:n** kokonaissaldo ei ole 350 (75 + 275)?_

Vastaus hänen kysymykseensä edellyttää monta-moneen-suhteen ymmärtämistä. Asiakkaan saldo voi vastata useiden tilien saldojen lisäystä, joten asiakkaiden saldot _eivät ole lisääviä_.

### <a name="relate-many-to-many-dimensions-guidance"></a>Liitä monta-moneen-dimensiot – ohjeet

Kun dimensiotyyppisten taulukoiden välillä on monta-moneen-suhde, annamme seuraavat ohjeet:

- Lisää kukin monta-moneen-suhteeseen liittyvä entiteetti mallitaulukkona ja varmista, että siinä on yksilöllisen tunnisteen (ID) sarake.
- Lisää välitaulukko liittyvien entiteettien tallentamista varten.
- Luo yksi-moneen-suhteita kolmen taulukon välille.
- Määritä **yksi** kaksisuuntainen suhde, jotta suodatuksen levittäminen jatkuu faktatyyppisiin taulukoihin.
- Kun ei ole sopivaa, että tunnistearvoja puuttuu, määritä tunnussarakkeiden **Is Nullable** -ominaisuuden arvoksi FALSE – silloin tietojen päivitys epäonnistuu, jos puuttuvia arvoja havaitaan.
- Piilota välitaulukko (ellei se sisällä raportointiin tarvittavia lisäsarakkeita tai -mittareita).
- Piilota kaikki tunnussarakkeet, jotka eivät sovellu raportointiin (esimerkiksi, kun tunnukset ovat korvaavia avaimia).
- Jos on järkevää jättää tunnussarake näkyviin, varmista, että se on suhteen ”yksi”-puolella – piilota aina ”monta”-puolen sarake. Tällöin suodatuksen suorituskyky on paras mahdollinen.
- Sekaannusten ja väärinkäsitysten välttämiseksi kirjoita selitykset raportin käyttäjille – voit lisätä kuvauksia tekstiruutuihin tai [visualisoinnin otsikon työkaluvihjeisiin](report-page-tooltips.md).

Emme suosittele liittämään monta-moneen-dimensiotyyppisiä taulukoita suoraan. Tämä rakennemenettely edellyttää monta-moneen-kardinaliteettisuhteen määrittämistä. Se voidaan saavuttaa käsitteellisesti, mutta se viittaa siihen, että liittyvät sarakkeet sisältäisivät arvojen kaksoiskappaleita. Se on kuitenkin yleinen rakennekäytäntö, että dimensiotyyppisissä taulukoissa on tunnussarake. Dimensiotyyppisissä taulukoissa tunnussarakkeen on aina oltava suhteen ”yksi”-puolella.

## <a name="relate-many-to-many-facts"></a>Liitä monta-moneen-faktat

Toinen monta-moneen-skenaariotyyppi koskee kahden faktatyyppisen taulukon liittämistä. Kaksi faktatyyppistä taulukkoa voidaan liittää suoraan. Tästä rakennetekniikasta voi olla hyötyä nopeassa ja yksinkertaisessa tietojen tarkastelussa. Emme kuitenkaan yleensä suosittele tätä rakennemenettelyä. Kerromme syyn tälle myöhemmin tässä osiossa.

Käsitellään esimerkkiä, joka koskee kahta faktatyyppistä taulukkoa: **Order** ja **Fulfillment**. **Order**-taulukossa on yksi rivi tilausriviä kohti, ja **Fulfillment**-taulukossa voi olla nolla riviä tai useampia rivejä tilausriviä kohti. **Order**-taulukon rivit vastaavat myyntitilauksia. **Fulfillment**-taulukon rivit vastaavat toimitettuja tilauskohteita. Monta-moneen-suhde yhdistää kaksi **OrderID**-saraketta, ja suodatus leviää vain **Order**-taulukosta (**Order** suodattaa **Fulfillment**-taulukkoa).

![Mallikaavio sisältää kaksi taulukkoa: Order ja Fulfillment. Monta-moneen-suhde yhdistää kaksi OrderID-saraketta, ja suodatus tapahtuu Order-taulukosta Fulfillment-taulukkoon.](media/relationships-many-to-many/order-fulfillment-model-example.png)

Suhteen kardinaliteetiksi määritetään monta-moneen **OrderID-** arvojen kaksoiskappaleiden tallentamisen tukemiseksi molemmissa taulukoissa. **Order**-taulukossa voi olla **OrderID**-arvojen kaksoiskappaleita, sillä tilauksessa voi olla useita rivejä. **Fulfillment**-taulukossa voi olla **OrderID**-arvojen kaksoiskappaleita, sillä tilauksissa voi olla useita rivejä ja tilausriveillä voi olla useita lähetyksiä.

Tarkastellaan seuraavaksi taulukon rivejä. Huomioi, että **Fulfillment**-taulukon tilausriveillä voi olla useita lähetyksiä. (Jos tilausriviä ei ole, se tarkoittaa, että tilausta ei ole vielä toteutettu.)

![Mallikaaviossa näkyy nyt taulukon rivit. Rivien tiedot kerrotaan seuraavassa kappaleessa.](media/relationships-many-to-many/order-fulfillment-model-related-tables.png)

Kahden taulukon rivien tiedot kerrotaan seuraavassa luettelossa:

- **Order**-taulukossa on viisi riviä:
  - **OrderDate** 1. tammikuuta 2019, **OrderID** 1, **OrderLine** 1, **ProductID** Prod-A, **OrderQuantity** 5, **Sales** 50
  - **OrderDate**1. tammikuuta 2019, **OrderID** 1, **OrderLine** 2, **ProductID** Prod-B, **OrderQuantity** 10, **Sales** 80
  - **OrderDate** 2. helmikuuta 2019, **OrderID** 2, **OrderLine** 1, **ProductID** Prod-B, **OrderQuantity** 5, **Sales** 40
  - **OrderDate** 2. helmikuuta 2019, **OrderID** 2, **OrderLine** 2, **ProductID** Prod-C, **OrderQuantity** 1, **Sales** 20
  - **OrderDate** 3. maaliskuuta 2019, **OrderID** 3, **OrderLine** 1, **ProductID** Prod-C, **OrderQuantity** 5, **Sales** 100
- **Fulfillment**-taulukossa on neljä riviä:
  - **FulfillmentDate** 1. tammikuuta 2019, **FulfillmentID** 50, **OrderID** 1, **OrderLine** 1, **FulfillmentQuantity** 2
  - **FulfillmentDate** 2. helmikuuta 2019, **FulfillmentID** 51, **OrderID** 2, **OrderLine** 1, **FulfillmentQuantity** 5
  - **FulfillmentDate** 2. helmikuuta 2019, **FulfillmentID** 52, **OrderID** 1, **OrderLine** 1, **FulfillmentQuantity** 3
  - **FulfillmentDate** 1. tammikuuta 2019, **FulfillmentID** 53, **OrderID** 1, **OrderLine** 2, **FulfillmentQuantity** 10

Katsotaan, mitä tapahtuu, kun malliin tehdään kysely. Tässä on taulukon visualisointi, jossa verrataan **Order**-taulukon **OrderID**-sarakkeen tilaus- ja toteutusmääriä.

![Taulukon visualisoinnissa on kolme saraketta: OrderID, OrderQuantity ja FulfillmentQuantity. Rivejä on kolme, yksi jokaista tilausta kohti. OrderID 2 ja 3 eivät ole kokonaan toteutettuja.](media/relationships-many-to-many/order-fulfillment-model-queried.png)

Visualisoinnissa näytetään tarkka tulos. Mallin hyödyllisyys on kuitenkin rajallinen – voit suodattaa tai ryhmitellä vain **Order**-taulukon **OrderID**-sarakkeen mukaan.

### <a name="relate-many-to-many-facts-guidance"></a>Liitä monta-moneen-faktat – ohjeet

Emme yleisesti ottaen suosittele kahden faktatyyppisen taulukon liittämistä suoraan monta-moneen-kardinaliteetin avulla. Tärkein syy on se, että malli ei tarjoa joustavuutta raportin visualisointien suodatukseen tai ryhmittelyyn. Esimerkissä visualisoinnit voivat suodattaa tai ryhmitellä vain **Order**-taulukon **OrderID**-sarakkeen mukaan. Toinen syy liittyy tietojesi laatuun. Jos tietojesi eheydessä on ongelmia, joitakin rivejä voidaan jättää pois kyselyjen suorittamisen aikana _heikon suhteen_ vuoksi. Katso lisätietoja kohdasta [Suhteen arviointi](../desktop-relationships-understand.md#relationship-evaluation).

Faktatyyppisten taulukoiden suoran liittämisen sijaan suosittelemme [tähtirakenteen](star-schema.md) periaatteiden käyttöönottoa. Voit tehdä sen lisäämällä dimensiotyyppisiä taulukoita. Dimensiotyyppiset taulukot liittyvät faktatyyppisiin taulukoihin yksi-moneen-suhteiden avulla. Tämä rakennemenettely on tehokas, sillä se tarjoaa joustavia raportointivaihtoehtoja. Sen avulla voit suodattaa tai ryhmitellä käyttämällä mitä tahansa dimensiotyyppisiä sarakkeita ja tehdä yhteenvedon mistä tahansa liittyvästä faktatyyppisestä taulukosta.

Mietitäänpä parempi ratkaisu.

![Mallikaavio sisältää kuusi taulukkoa: OrderLine, OrderDate, Order, Fulfillment, Product ja FulfillmentDate. Kaikki taulukot liittyvät toisiinsa. Rakenne kuvataan seuraavassa kappaleessa.](media/relationships-many-to-many/order-fulfillment-model-improved.png)

Huomioi seuraavat rakennemuutokset:

- Mallissa on nyt neljä lisätaulukkoa: **OrderLine**, **OrderDate**, **Product** ja **FulfillmentDate**
- Kaikki neljä lisätaulukkoa ovat dimensiotyyppisiä, ja yksi-moneen-suhteet liittävät nämä taulukot faktatyyppisiin taulukoihin
- **OrderLine**-taulukko sisältää **OrderLineID**-sarakkeen, joka kuvaa **OrderID**-arvoa kerrottuna sadalla sekä **OrderLine**arvoa eli kunkin tilausrivin yksilöllistä tunnistetta
- **Order**- ja **Fulfillment**-taulukot sisältävät nyt **OrderLineID**-sarakkeen. Ne eivät enää sisällä **OrderID**- ja **OrderLine**-sarakkeita
- **Fulfillment**-taulukko sisältää nyt **OrderDate**- ja **ProductID**-sarakkeet
- **FulfillmentDate**-taulukko liittyy vain **Fulfillment**-taulukkoon
- Kaikki yksilöllisten tunnisteiden sarakkeet on piilotettu

Kun otat käyttöön tähtirakenteen periaatteet, saat seuraavat edut:

- Raportin visualisoinnit voivat _suodattaa tai ryhmitellä_ dimensiotyyppisen taulukon minkä tahansa näkyvissä olevan sarakkeen mukaan
- Raportin visualisoinnit voivat _tehdä yhteenvedon_ faktatyyppisen taulukon mistä tahansa näkyvissä olevasta sarakkeesta
- **OrderLine**-, **OrderDate**- tai **Product**-taulukoihin käytetyt suodattimet leviävät molempiin faktatyyppisiin taulukoihin
- Kaikki suhteet ovat yksi-moneen-suhteita, ja jokainen suhde on _vahva suhde_. Tietojen eheyteen liittyviä ongelmia ei peitetä. Katso lisätietoja kohdasta [Suhteen arviointi](../desktop-relationships-understand.md#relationship-evaluation).

## <a name="relate-higher-grain-facts"></a>Liitä yksityiskohtaiset faktat

Tämä monta-moneen-skenaario on hyvin erilainen kuin kaksi muuta tässä artikkelissa jo kuvattua skenaariota.

Käsitellään esimerkkiä, joka koskee neljää taulukkoa: **Date**, **Sales**, **Product** ja **Target**. **Date** ja **Product** ovat dimensiotyyppisiä taulukoita, ja ne molemmat liittyvät faktatyyppiseen **Sales**-taulukkoon yksi-moneen-suhteiden avulla. Tähän asti tämä sopii hyvin tähtirakenteen periaatteisiin. **Target**-taulukko pitää kuitenkin vielä liittää muihin taulukoihin.

![Mallikaavio sisältää neljä taulukkoa: Date, Sales, Product ja Target. Target-taulukko ei liity mihinkään muuhun taulukkoon. Rakenne kuvataan seuraavassa kappaleessa.](media/relationships-many-to-many/sales-targets-model-example.png)

**Target**-taulukko sisältää kolme saraketta: **Category**, **TargetQuantity** ja **TargetYear**. Taulukon riveillä näkyvät vuosi- ja tuoteluokat. Toisin sanoen kullekin tuoteluokalle määritetään joka vuosi tavoitteet, joilla mitataan myyntisuoritusta.

![Target-taulukossa on kolme saraketta: TargetYear, Category ja TargetQuantity. Kuudelle riville tallennetaan tavoitteet vuosille 2019 ja 2020, molemmille vuosille kolme luokkaa.](media/relationships-many-to-many/sales-targets-model-target-rows.png)

**Target**-taulukko sisältää ylemmän tason tietoja kuin dimensiotyyppiset taulukot, joten yksi-moneen-suhdetta ei voida luoda. Tämä koskee vain yhtä suhdetta. Tutkitaan, miten **Target**-taulukko voidaan liittää dimensiotyyppisiin taulukoihin.

### <a name="relate-higher-grain-time-periods"></a>Liitä yksityiskohtaiset ajanjaksot

**Date**- ja **Target**-taulukoiden välisen suhteen on oltava yksi-moneen-suhde. Tämä johtuu siitä, että **TargetYear**-sarakkeen arvot ovat päivämääriä. Tässä esimerkissä kaikki **TargetYear**-sarakkeen arvot ovat kohdevuoden ensimmäisiä päiviä.

> [!TIP]
> Kun tallennat faktoja, joiden ajan rakeisuus on suurempi kuin päivä, määritä sarakkeen tietotyypiksi **Päivämäärä** (tai **Kokonaisluku**, jos käytät päivämääränäppäimiä). Tallenna sarakkeeseen arvo, joka vastaa ajanjakson ensimmäistä päivää. Esimerkiksi vuosijaksoon tallennetaan kyseisen vuoden 1. tammikuuta, ja kuukausijaksoon tallennetaan kyseisen kuukauden ensimmäinen päivä.

On kuitenkin varmistettava, että kuukausi- tai päivämäärätason suodattimet antavat merkityksellisen tuloksen. Ilman erityistä laskentalogiikkaa raportin visualisoinnit voivat ilmoittaa, että kohdepäivät ovat kunkin vuoden ensimmäisiä päiviä. Kaikki muut päivät – ja kaikki kuukaudet lukuun ottamatta tammikuuta – näyttävät kohdemääräksi TYHJÄÄ.

Seuraavassa matriisivisualisoinnissa näytetään, mitä tapahtuu, kun raportin käyttäjä porautuu vuositasolta kuukausitasolle. Visualisointi tekee yhteenvedon **TargetQuantity**-sarakkeesta. ([Näytä kohteet, joilla ei ole tietoja](../desktop-show-items-no-data.md) -asetus on otettu käyttöön matriisin riveille.)

![Matriisivisualisointi näyttää vuoden 2020 kohdemääräksi 270. Kun sitä laajennetaan näyttämään vuoden 2020 kuukaudet, tammikuu on 270 ja kaikki muut kuukausitason kohdemäärät ovat TYHJIÄ.](media/relationships-many-to-many/sales-targets-model-matrix-blank-months-bad.png)

Jos haluat välttää tämän, suosittelemme, että hallitset faktatietojen yhteenvetoa mittareita käyttämällä. Yksi tapa hallita yhteenvetoa on palauttaa TYHJÄ, kun alemman tason ajanjaksoille tehdään kyselyjä. Toinen tapa – joka on määritetty joillekin kehittyneille DAX:ille – on jakaa arvot alemman tason ajanjaksoille.

Kokeile seuraavaa mittarimääritystä, jossa käytetään [ISFILTERED](/dax/isfiltered-function-dax) DAX-funktiota. Se palauttaa arvon vain, kun **Date**- tai **Month**-sarakkeita ei ole suodatettu.

```dax
Target Quantity =
IF(
    NOT ISFILTERED('Date'[Date])
        && NOT ISFILTERED('Date'[Month]),
    SUM(Target[TargetQuantity])
)
```

Seuraava matriisivisualisointi käyttää nyt **Target Quantity** -mittaria. Se näyttää, että kaikki kuukausittaiset kohdemäärät ovat TYHJIÄ.

![Matriisivisualisointi näyttää vuoden 2020 kohdemääräksi 270. Kun sitä laajennetaan näyttämään vuoden 2020 kuukaudet, kaikki kuukausitason kohdemäärät ovat TYHJIÄ.](media/relationships-many-to-many/sales-targets-model-matrix-blank-months-good.png)

### <a name="relate-higher-grain-non-date"></a>Liitä yksityiskohtainen (ei-päivämäärä)

Erilaista rakennemenettelyä edellytetään, kun dimensiotyyppisen taulukon ei-päivämäärä sarake liitetään faktatyyppiseen taulukkoon (ja se on yksityiskohtaisempi kuin dimensiotyyppinen taulukko).

**Category**-sarakkeet (sekä **Product**- että **Target**-taulukoissa) sisältävät arvojen kaksoiskappaleet. Yksi-moneen-suhteen ”yhtä” ei siis ole. Tässä tapauksessa sinun on luotava monta-moneen-suhde. Suhteen on levitettävä suodatus yhteen suuntaan dimensiotyyppisestä taulukosta faktatyyppiseen taulukkoon.

![Mallikaavion osa näyttää Target- ja Product-taulukot. Monta-moneen-suhde yhdistää taulukot toisiinsa. Suodatussuunta on Product-taulukosta Target-taulukkoon.](media/relationships-many-to-many/sales-targets-model-relate-non-date.png)

Tarkastellaan seuraavaksi taulukon rivejä.

![Mallikaavio sisältää kaksi taulukkoa: Target ja Product. Monta-moneen-suhde yhdistää luokkasarakkeet toisiinsa. Rivien tiedot kerrotaan seuraavassa kappaleessa.](media/relationships-many-to-many/sales-targets-model-relate-non-date-tables.png)

**Target**-taulukossa on neljä riviä: kaksi riviä kummallekin kohdevuodelle (2019 ja 2020), ja kaksi luokkaa (Clothing ja Accessories). **Product**-taulukossa on kolme tuotetta. Kaksi niistä kuuluu vaateluokkaan ja yksi kuuluu asusteluokkaan. Yhden vaatteen väri on vihreä ja kahden muun sininen.

Taulukon visualisoinnin ryhmittely **Product** -taulukon **Category**-sarakkeen mukaan tuottaa seuraavan tuloksen.

![Taulukon visualisoinnissa on kaksi saraketta: Category ja TargetQuantity. Accessories on 60, Clothing on 40 ja kokonaismäärä on 100.](media/relationships-many-to-many/sales-targets-model-visual-category-targets.png)

Tämä visualisointi tuottaa oikean tuloksen. Katsotaan nyt, mitä tapahtuu, kun kohdemäärän ryhmittelyyn käytetään **Product**-taulukon **Color**-saraketta.

![Taulukon visualisoinnissa on kaksi saraketta: Color ja TargetQuantity. Blue on 100, Green on 40 ja kokonaismäärä on 100.](media/relationships-many-to-many/sales-targets-model-visual-color-targets-bad.png)

Visualisointi tuottaa virheellisiä tietoja. Miksi näin tapahtuu?

**Product**-taulukon **Color**-sarakkeen suodatuksen tuloksena on kaksi riviä. Toinen rivi on Clothing-luokalle ja toinen Accessories-luokalle. Nämä kaksi luokka-arvoa levitetään suodattimina **Target**-taulukkoon. Toisin sanoen kahden luokan tuotteissa käytetään sinistä väriä, joten _näitä luokkia_ käytetään kohteiden suodatukseen.

Jos haluat välttää tämän, suosittelemme, että hallitset faktatietojen yhteenvetoa mittareita käyttämällä, kuten edellä kuvattiin.

Kokeile seuraavaa mittarimääritystä. Huomioi, että kaikkien luokkatason alapuolella olevien **Product**-taulukon sarakkeiden suodatus testataan.

```dax
Target Quantity =
IF(
    NOT ISFILTERED('Product'[ProductID])
        && NOT ISFILTERED('Product'[Product])
        && NOT ISFILTERED('Product'[Color]),
    SUM(Target[TargetQuantity])
)
```

Seuraava taulukon visualisointi käyttää nyt **Target Quantity** -mittaria. Se näyttää, että kaikki värien kohdemäärät ovat TYHJIÄ.

![Taulukon visualisoinnissa on kaksi saraketta: Color ja TargetQuantity. Blue on TYHJÄ, Green on TYHJÄ ja kokonaismäärä on 100.](media/relationships-many-to-many/sales-targets-model-visual-color-targets-good.png)

Lopullinen mallirakenne näyttää seuraavanlaiselta.

![Mallikaaviosta näkyy, että Date- ja Target-taulukot on liitetty toisiinsa yksi-moneen-suhteella. Product- ja Target-taulukot on liitetty toisiinsa monta-moneen suhteella, ja suodatus tapahtuu Product-taulukosta Target-taulukkoon.](media/relationships-many-to-many/sales-targets-model-example-final.png)

### <a name="relate-higher-grain-facts-guidance"></a>Liitä yksityiskohtaiset faktat – ohjeet

Kun sinun täytyy liittää dimensiotyyppinen taulukko faktatyyppiseen taulukkoon ja faktatyyppisessä taulukossa on yksityiskohtaisempia rivejä kuin dimensiotyyppisessä taulukossa, huomioi seuraavat ohjeet:

- Yksityiskohtaiset faktat, päivämäärät:
  - Tallenna faktatyyppiseen taulukkoon ajanjakson ensimmäinen päivämäärä
  - Luo yksi-moneen-suhde päivämäärätaulukon ja faktatyyppisen taulukon välille
- Muut yksityiskohtaiset faktat:
  - Luo monta-moneen-suhde dimensiotyyppisen taulukon ja faktatyyppisen taulukon välille
- Molemmat tyypit:
  - Hallitse yhteenvetoa mittarilogiikalla – palauta TYHJÄ, kun alemman tason dimensiotyyppisiä sarakkeita käytetään suodatukseen tai ryhmittelyyn
  - Piilota yhteenvedettävät faktatyyppisen taulukon sarakkeet – tällä tavalla vain mittareita voidaan käyttää faktatyyppisen taulukon yhteenvetoon

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Mallien suhteet Power BI Desktopissa](../desktop-relationships-understand.md)
- [Tutustu tähtirakenteeseen ja sen merkitykseen Power BI:ssä](star-schema.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
