---
title: Koosteiden käyttö ja hallinta Power BI Desktopissa
description: Käytä koosteita massadatan vuorovaikutteisen analyysin tekemiseen Power BI Desktopissa.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/14/2020
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: b7ff14b4932ba77b47fdb603124d29858c622fc7
ms.sourcegitcommit: d6a48e6f6e3449820b5ca03638b11c55f4e9319c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/18/2020
ms.locfileid: "77427648"
---
# <a name="use-aggregations-in-power-bi-desktop"></a>Koosteiden käyttö Power BI Desktopissa

Power BI:n *koosteiden* avulla voit pienentää taulukon kokoa, jotta voit keskittyä tärkeisiin tietoihin ja parantaa kyselyn suorituskykyä. Koosteet mahdollistavat massadatan vuorovaikutteisen analyysin tavoilla, jotka eivät ole muutoin mahdollisia. Ne voivat myös alentaa huomattavasti suurten tietojoukkojen avauskuluja päätöksenteossa.

Koosteiden käytön etuja ovat muun muassa seuraavat:

- **Parempi kyselyjen suorituskyky massadatasta**. Jokainen Power BI -visualisointitoiminto lähettää DAX-kyselyjä tietojoukkoon. Välimuistiin tallennetut kootut tiedot käyttävät murto-osan resursseista, joita tarvitaan yksityiskohtaisia tietoja varten, joten voit avata massadatan, mikä ei muuten olisi mahdollista.
- **Optimoitu tietojen päivitys**. Pienemmät välimuistikoot vähentävät päivitysaikoja, joten tiedot saadaan nopeammin käyttäjille.
- **Tasapainotetut arkkitehtuurit**. Power BI:n muistissa oleva välimuisti voi käsitellä koostekyselyjä, rajoittaa DirectQuery-tilassa lähetettyjen kyselyjen määrää ja auttaa täyttämään samanaikaisuusrajat. Jäljellä olevat tietotason kyselyt ovat yleensä suodatettuja tapahtumatason kyselyjä, joita tietovarastot ja massadatajärjestelmät käsittelevät yleensä hyvin.

![Koosteet Microsoft Power BI Desktopissa](media/desktop-aggregations/aggregations_07.jpg)

Dimensiotietolähteet, kuten tietovarastot ja tietovaraston osajoukot, voivat käyttää [suhteeseen perustuvia koosteita](#aggregation-based-on-relationships). Hadoop-pohjaisten massadatalähteiden [koosteet perustuvat usein Ryhmittelyperuste-sarakkeisiin](#aggregation-based-on-groupby-columns). Tässä artikkelissa kuvataan kunkin tietolähdetyypin Power BI -mallintamisen eroja.

## <a name="create-an-aggregated-table"></a>Koostetaulukon luominen

Luo koostetaulukko seuraavasti:
1. Määritä uusi taulukko, joka sisältää haluamasi kentät, tietolähteesi ja mallisi mukaan. 
1. Määritä koosteet **Koosteiden hallinta** -valintaikkunan avulla.
1. Jos sovellettavissa, muuta koostetaulukon [tallennustilaa](#storage-modes). 

### <a name="manage-aggregations"></a>Koosteiden hallinta

Kun olet luonut haluamasi kentät sisältävän uuden taulukon, napsauta hiiren kakkospainikkeella minkä tahansa Power BI Desktop -näkymän **Kentät**-ruutua ja valitse **Koosteiden hallinta**.

![Valitse Koosteiden hallinta](media/desktop-aggregations/aggregations-06.png)

**Koosteiden hallinta** -valintaikkunassa näytetään rivi kullekin sarakkeelle taulukossa, jossa voit määrittää koosteen toiminnan. Seuraavassa esimerkissä **Myynti**-tietotaulukon kyselyt ohjataan sisäisesti uudelleen **Myyntikoosteet**-koostetaulukkoon. 

**Koosteiden hallinta** -valintaikkunan avattavassa **Yhteenveto**-kohdassa on seuraavat arvot:
- Määrä
- Ryhmittelyperuste
- Max
- Min
- Summa
- Laske taulukon rivit

![Koosteiden hallinta -valintaikkuna](media/desktop-aggregations/aggregations_07.jpg)

Tässä suhteeseen perustuvan koosteen esimerkissä Ryhmittelyperuste-merkinnät ovat valinnaisia. DISTINCTCOUNT-arvoa lukuun ottamatta ne eivät vaikuta koosteiden toimintaan ja parantavat pääasiassa luettavuutta. Ilman Ryhmittelyperuste-merkintöjä koosteista tuotetaan silti osumia suhteiden perusteella. Tämä eroaa tässä artikkelissa myöhemmin olevasta [massadatan esimerkistä](#aggregation-based-on-groupby-columns), jossa vaaditaan Ryhmittelyperuste-merkintöjä.

Kun olet määrittänyt haluamasi koosteet, valitse **Käytä kaikkia**. 

### <a name="validations"></a>Vahvistukset

**Koosteiden hallinta** -valintaikkunassa pakotetaan seuraavat tärkeät vahvistukset:

- **Tietosarakkeen** tietotyypin on oltava sama kuin **Koostesarakkeessa**, lukuun ottamatta Määrä- ja Laske taulukon rivit -**yhteenveto**funktioita. Määrä ja Laske taulukon rivit ovat käytettävissä vain kokonaislukukoostesarakkeissa, eivätkä ne edellytä vastaavaa tietotyyppiä.
- Kolmen tai useamman taulukon kattavia ketjutettuja koosteita ei sallita. Esimerkiksi koosteet **taulukossa A** eivät voi viitata **taulukkoon B**, jossa on koosteita, jotka viittaavat **taulukkoon C**.
- Kaksoiskappaleita koosteista, joissa kaksi merkintää käyttää samaa **yhteenveto**funktiota ja viittaa samaan **tietotaulukkoon** ja **tietosarakkeeseen**, ei sallita.
- **Tietotaulukon** on käytettävä DirectQuery-tallennustilaa, ei Tuonti-tallennustilaa.
- Ryhmittelyä passiivisen suhteen käyttämän viiteavainsarakkeen mukaan ja koosteosumien saantia USERELATIONSHIP-funktiolla ei tueta.

Useimmat vahvistukset pakotetaan poistamalla avattavan valikon arvot käytöstä ja näyttämällä ohjeteksti työkaluvihjeessä seuraavan kuvan mukaisesti.

![Työkaluvihjeessä näkyvät vahvistukset](media/desktop-aggregations/aggregations_08.jpg)

### <a name="aggregation-tables-are-hidden"></a>Koostetaulukot on piilotettu

Käyttäjät, joilla on vain luku -käyttöoikeudet tietojoukkoon, eivät voi luoda kyselyn koostetaulukoita. Näin vältetään suojausongelmat käytettäessä *rivitason suojausta (RLS)* . Kuluttajat ja kyselyt viittaavat tietotaulukkoon eivätkä koostetaulukkoon, eikä niiden tarvitse tietää koostetaulukosta.

Tästä syystä koostetaulukot piilotetaan **raportti**näkymästä. Jos taulukkoa ei ole vielä piilotettu, **Koosteiden hallinta** -valintaikkuna määrittää sen piilotetuksi, kun valitset **Käytä kaikkia**.

### <a name="storage-modes"></a>Tallennustilat
Koosteominaisuus on vuorovaikutuksessa taulukkotason tallennustilojen kanssa. Power BI -taulukot voivat käyttää *DirectQuery*-, *Tuonti*- tai *Kaksoiskäyttö*-tallennustiloja. DirectQuery suorittaa taustakyselyn suoraan samalla kun Tuonti tallentaa tiedot välimuistiin ja lähettää kyselyjä välimuistiin tallennettuihin tietoihin. Kaikki Power BI:n Tuonti-tietolähteet ja ei-moniulotteiset DirectQuery-tietolähteet toimivat koosteiden kanssa. 

Jos haluat määrittää koostetaulukon tallennustilaksi Tuonti kyselyjen nopeuttamiseksi, valitse koostetaulukko Power BI Desktopin **malli**näkymästä. Laajenna **Ominaisuudet**-ruudussa **Lisäasetukset**-kohtaa, siirry alaspäin valinnassa **Tallennustila**-kohtaan ja valitse **Tuonti**. Ota huomioon, että tämä toiminto on peruuttamaton. 

![Tallennustilan tilan määrittäminen](media/desktop-aggregations/aggregations-04.png)

Lisätietoja taulukon tallennustiloista löytyy artikkelista [Tallennustilan hallinta Power BI Desktopissa](desktop-storage-mode.md).

### <a name="rls-for-aggregations"></a>RLS koosteita varten

Jotta koosteet toimivat oikein, RLS-lausekkeiden on suodatettava sekä koostetaulukko että tietotaulukko. 

Seuraavassa esimerkissä **Paikkatieto**-taulukon RLS-lauseke toimii koosteiden kanssa, koska Paikkatieto on suhteiden suodatuspuolella sekä **Myynti**-taulukossa että **Myyntikooste**-taulukossa. RLS otetaan onnistuneesti käyttöön sekä kyselyissä, jotka tuottavat osumia koostetaulukosta että kyselyissä, jotka eivät tuota siitä osumia.

![Onnistunut RLS koosteita varten](media/desktop-aggregations/manage-roles.png)

**Tuote**-taulukossa oleva RLS-lauseke suodattaa vain **Myynti**-tietotaulukon, ei **Myyntikooste**-koostetaulukkoa. Koska koostetaulukko on tietotaulukossa olevien tietojen toinen esitystapa, kyselyihin vastaaminen koostetaulukosta ei ole turvallista, jos RLS-suodatinta ei voi käyttää. Suodatusta vain tietotaulukosta ei suositella, koska tästä roolista peräisin oleviin käyttäjäkyselyihin ei voida soveltaa koosteosumia. 

RLS-lauseketta, joka suodattaa vain **Myyntikooste**-taulukon eikä **Myynti**-tietotaulukkoa, ei sallita.

![Vain koostetaulukkoon käytettävää RLS-lauseketta ei sallita](media/desktop-aggregations/filter-agg-error.jpg)

[Ryhmittelyperuste-sarakkeisiin perustuvissa koosteissa](#aggregation-based-on-groupby-columns) tietotaulukkoon sovellettavaa RLS-lauseketta voidaan käyttää suodattamaan koostetaulukko, koska koostetaulukon kaikki Ryhmittelyperuste-sarakkeet sisältyvät tietotaulukkoon. Toisaalta koostetaulukon RLS-suodatinta ei voi soveltaa tietotaulukkoon, joten sitä ei sallita.

## <a name="aggregation-based-on-relationships"></a>Suhteisiin perustuva kooste

*Suhteisiin perustuvia koosteita* käytetään yleensä dimensiomallien kanssa. Tietovarastojen ja tietovaraston osajoukkojen Power BI -tietojoukot muistuttavat tähti- tai lumihiutalerakenteita, joissa on dimensiotaulukoiden ja faktataulukoiden välisiä suhteita.

Seuraavassa yhdestä tietolähteestä peräisin olevassa mallissa taulukot käyttävät DirectQuery-tallennustilaa. **Myynti**-faktataulukko sisältää miljardeja rivejä. **Myynti**-taulukon määrittäminen Tuonti-tallennustilaksi välimuistiin tallentamista varten kuluttaisi huomattavasti muistia ja lisäisi hallintakustannuksia.

![Mallin tietotaulukot](media/desktop-aggregations/aggregations_02.jpg)

Luo sen sijaan **Myyntikooste**-koostetaulukko. **Myyntikooste**-taulukossa rivien määrä on sama kuin  **Myyntimäärä**-taulukon summa ryhmiteltynä **Asiakasavain**-, **Päivämääräavain**- ja **Tuotteen aliluokka** -arvojen mukaan. **Myyntikooste**-taulukon rakeisuus on suurempi kuin **Myynti**-taulukon, joten miljardien sijasta se saattaa sisältää miljoonia rivejä, joita on paljon helpompi hallita.

Seuraavia dimensiotaulukoita käytetään useimmiten kyselyille, joilla on merkittävä liikearvo. Ne voivat suodattaa **Myyntikooste**-taulukon käyttämällä *yksi moneen*- tai *monta yhteen* -suhteita.

- Maantiede
- Asiakas
- Päivämäärä
- Tuotteen aliluokka
- Tuoteluokka

Malli näkyy seuraavassa kuvassa.

![Mallin koostetaulukko](media/desktop-aggregations/aggregations_03.jpg)

Seuraavassa taulukossa näytetään **Myyntikooste**-taulukon koosteet.

![Myyntikooste-taulukon koosteet](media/desktop-aggregations/aggregations-table_01.jpg)

> [!NOTE]
> **Myyntikooste**-taulukko voidaan muiden taulukoiden tavoin ladata monin tavoin. Koostaminen voidaan suorittaa lähdetietokannassa ETL/ELT-prosessin avulla tai taulukon [M-lausekkeen](/powerquery-m/power-query-m-function-reference) mukaan. Koostetaulukko voi käyttää Tuonti-tallennustilaa [Power BI Premiumin lisäävän päivityksen](service-premium-incremental-refresh.md) kanssa tai ilman sitä, tai se voi käyttää DirectQuery-tallennustilaa ja se voidaan optimoida nopeille kyselyille [sarakesäilöindeksien](/sql/relational-databases/indexes/columnstore-indexes-overview) avulla. Joustavuus mahdollistaa tasapainotetut arkkitehtuurit, jotka voivat jakaa kyselyn kuormituksen pullonkaulojen välttämiseksi.

Vaihtamalla **Myyntikooste**-koostetaulukon tallennustilaksi **Tuonti** voit avata valintaikkunan, jossa aiheeseen liittyvien dimensiotaulukoiden tallennustilaksi voidaan määrittää *Kaksoistaulukko*. 

![Tallennustilan valintaikkuna](media/desktop-aggregations/aggregations_05.jpg)

Kun aiheeseen liittyvien dimensiotaulukoiden tallennustilaksi määritetään Kaksoistaulukko, niiden tallennustilana voi olla joko Tuonti tai DirectQuery alikyselyn mukaan. Esimerkissä:

- Kyselyjä, jotka koostavat arvoja Tuonti-tilan **Myyntikooste**-taulukosta ja ryhmittelevät aiheeseen liittyvien kaksoistaulukoiden määritteiden mukaan, voidaan palauttaa muistissa olevasta välimuistista.
- Kyselyjä, jotka koostavat arvoja DirectQuery-tilan **Myynti**-taulukosta ja ryhmittelevät aiheeseen liittyvien kaksoistaulukoiden määritteiden mukaan, voidaan palauttaa DirectQuery-tilassa. Ryhmittelyperuste-toiminnon sisältävä kyselyn logiikka välitetään lähdetietokantaan.

Lisätietoja Kaksoistaulukko-tallennustilasta löytyy artikkelista [Tallennustilan hallinta Power BI Desktopissa](desktop-storage-mode.md).

### <a name="strong-vs-weak-relationships"></a>Vahvat vs. heikot suhteet

Koosteiden osumat suhteiden perusteella edellyttävät vahvoja suhteita.

Vahvat suhteet sisältävät seuraavia tallennustilayhdistelmiä, joissa molemmat taulukot ovat yhdestä lähteestä:

| *Monen* puolen taulukko | *1*-puolen taulukko |
| ------------- |----------------------| 
| Kaksoistaulukko          | Kaksoistaulukko                 | 
| Tuo        | Tuonti- tai kaksoistaulukko       | 
| DirectQuery   | DirectQuery- tai kaksoistaulukko  | 

Ainoa tapaus, jossa *ristilähde*suhdetta pidetään vahvana, on silloin, jos molemman taulukon määrityksenä on Tuonti. Monta moneen -suhteita pidetään aina heikkoina.

Lisätietoja *ristilähde*koosteiden osumista, jotka eivät ole riippuvaisia suhteista, löytyy artikkelista [Ryhmittely-sarakkeisiin perustuvat koosteet](#aggregation-based-on-groupby-columns). 

### <a name="relationship-based-aggregation-query-examples"></a>Suhteeseen perustuvan koosteen kyselyesimerkit

Seuraava kysely osuu koosteeseen, koska **Päivämäärä**-taulukon sarakkeiden rakeisuus voi tuottaa osuman koosteessa. **Myyntimäärä**-sarake käyttää **Summa**-koostetta.

![Onnistunut suhteeseen perustuvan koosteen kysely](media/desktop-aggregations/aggregations-code_02.jpg)

Seuraava kysely ei osu koosteeseen. **Myyntimäärä**-summan pyytämisestä huolimatta kysely suorittaa Ryhmittelyperuste-toiminnon **Tuote**-taulukon sarakkeessa, jonka rakeisuus ei voi tuottaa osumaa koosteessa. Kun tarkkailet suhteita mallissa, huomaat, että tuotteen aliluokka voi sisältää useita **Tuote**-rivejä. Kysely ei pysty selvittämään, mihin tuotteeseen koostetaan. Tässä tapauksessa kysely palautuu DirectQueryksi ja lähettää SQL-kyselyn tietolähteeseen.

![Kysely, joka ei voi käyttää koostetta](media/desktop-aggregations/aggregations-code_03.jpg)

Koosteita ei ole tarkoitettu vain yksinkertaisiin laskutoimituksiin, jotka suorittavat suoraviivaisen yhteenlaskun. Myös monimutkaiset laskutoimitukset voivat hyötyä niistä. Käsitteellisesti monimutkainen laskutoimitus jaetaan alikyselyiksi kullekin SUMMA-, PIENIN-, SUURIN- ja MÄÄRÄ-arvolle, ja kukin alikysely arvioidaan sen määrittämiseksi, voiko se saada osuman koosteessa. Tämä logiikka ei päde kaikissa tapauksissa kyselysuunnitelman optimoinnin vuoksi, mutta yleensä sen pitäisi toimia. Seuraava esimerkki tuottaa osuman koosteessa:

![Monimutkaisen koosteen kysely](media/desktop-aggregations/aggregations-code_04.jpg)

COUNTROWS-funktio voi hyötyä koosteista. Seuraava kysely tuottaa osuman koosteessa, koska **Myynti**-taulukolle on määritetty **Laske taulukon rivit** -kooste.

![COUNTROWS-koosteen kysely](media/desktop-aggregations/aggregations-code_05.jpg)

AVERAGE-funktio voi hyötyä koosteista. Seuraava kysely tuottaa osuman koosteessa, koska AVERAGE-funktio muutetaan sisäisesti MÄÄRÄ-arvolla jaetuksi SUMMA-arvoksi. Koska **Yksikköhinta**-sarakkeessa on sekä SUMMA- että MÄÄRÄ-arvoille määritettyjä koosteita, kooste saa osuman.

![AVERAGE-koosteen kysely](media/desktop-aggregations/aggregations-code_06.jpg)

Joissakin tapauksissa DISTINCTCOUNT-funktio voi hyöytä koosteista. Seuraava kysely tuottaa osuman koosteessa, koska **Asiakasavain**-ryhmälle on Ryhmittelyperuste-merkintä, mikä säilyttää **Asiakasavain**-ryhmän erotettavuuden koostetaulukossa. Tämä tekniikka voi silti saavuttaa suorituskykyrajan, jossa yli 2–5 miljoonaa erillistä arvoa voi vaikuttaa kyselyn suorituskykyyn. Se voi kuitenkin olla hyödyllinen tilanteissa, joissa tietotaulukossa on miljardeja rivejä, mutta sarakkeessa on 2–5 miljoonaa erillistä arvoa. Tässä tapauksessa DISTINCTCOUNT-funktio voidaan suorittaa nopeammin kuin miljardeja rivejä sisältävän taulukon tarkistaminen, vaikka se olisi tallennettu välimuistiin.

![DISTINCTCOUNT-koosteen kysely](media/desktop-aggregations/aggregations-code_07.jpg)

DAX-aikatietofunktiot havaitsevat koosteet. Seuraava kysely osuu koosteeseen, koska DATESYTD-funktio luo **CalendarDay**-arvojen taulukon ja koska koostetaulukon rakeisuustaso on sellainen,että **Date**-taulukon ryhmittelysarake kattaa sen. Tämä on esimerkki CALCULATE-funktion taulukkoarvoisesta suodattimesta, joka voi toimia koosteiden kanssa.

![SUMMARIZECOLUMNS-koostekysely](media/desktop-aggregations/aggregations-code-07b.jpg)

## <a name="aggregation-based-on-groupby-columns"></a>Ryhmittelyperuste-sarakkeisiin perustuva kooste 

Hadoop-pohjaiset massadatatietomallit eroavat ominaisuuksiltaan dimensiomalleista. Suurten taulukoiden välisten liitosten välttämiseksi massadatamalleissa ei useinkaan käytetä suhteita vaan denormalisoituja dimensiomääritteitä faktataulukoille. Voit avata tällaiset massadatatietomallit vuorovaikutteista analyysia varten *Ryhmittelyperuste-sarakkeisiin perustuvien koosteiden* avulla.

Seuraava taulukko sisältää koostettavan numeerisen **Siirto**-sarakkeen. Kaikki muut sarakkeet ovat määritteitä, joiden mukaan ryhmitellään. Taulukko sisältää IoT-tietoja ja valtavan rivimäärän. Tallennustila on DirectQuery. Kyselyt tietolähteestä, jotka koostavat koko tietojoukon, toimivat hitaasti jo pelkän koon vuoksi. 

![IoT-taulukko](media/desktop-aggregations/aggregations_09.jpg)

Jotta vuorovaikutteinen analyysi voidaan ottaa käyttöön tässä tietojoukossa, voit lisätä koostetaulukon, joka ryhmittelee useimpien määritteiden mukaan, mutta jättää pois kardinaliteetiltaan suuret määritteet, kuten pituus- ja leveysasteen. Tämä vähentää rivien määrää huomattavasti, jolloin koko pienenee riittävästi välimuistiin mahtumiseksi. 

![Kuljettajan toiminnan kooste -taulukko](media/desktop-aggregations/aggregations_10.jpg)

Voit määrittää koosteliitokset **Kuljettajan toiminnan kooste** -taulukolle **Koosteiden hallinta** -valintaikkunassa. 

![Kuljettajan toiminnan kooste -taulukon Koosteiden hallinta -valintaikkuna](media/desktop-aggregations/aggregations_11.jpg)

Ryhmittelyperuste-sarakkeisiin perustuvien koosteiden **Ryhmittelyperuste**-merkinnät eivät ole valinnaisia. Ilman niitä koosteille ei saada osumia. Tämä eroaa koosteiden käyttämisestä suhteiden perusteella, jossa Ryhmittelyperuste-merkinnät ovat valinnaisia.

Seuraavassa taulukossa näytetään **Kuljettajan toiminnan kooste** -taulukon koosteet.

![Kuljettajan toiminnan kooste -koostetaulukko](media/desktop-aggregations/aggregations-table_02.jpg)

Voit määrittää **Kuljettajan toiminnan kooste** -koostetaulukon tallennustilaksi Tuonti.

### <a name="groupby-aggregation-query-example"></a>Ryhmittelyperuste-koosteen kyselyesimerkki

Seuraava kysely tuottaa osuman koosteessa, koska koostetaulukko kattaa **Toimintapäivämäärä**-sarakkeen. COUNTROWS-funktio käyttää **Laske taulukon rivit** -koostetta.

![Onnistunut Ryhmittelyperuste-kysely](media/desktop-aggregations/aggregations-code_08.jpg)

**Laske taulukon rivit** -koosteita kannattaa käyttää erityisesti malleissa, jotka sisältävät suodatinmääritteitä faktataulukoissa. Power BI voi lähettää kyselyjä tietojoukkoon käyttämällä COUNTROWS-funktiota tapauksissa, joissa käyttäjä ei sitä nimenomaisesti pyydä. Esimerkiksi suodatin-valintaikkuna näyttää rivien määrän kunkin arvon osalta.

![Suodatinvalintaikkuna](media/desktop-aggregations/aggregations-12.png)

## <a name="combined-aggregation-techniques"></a>Yhdistetyt koostetekniikat

Voit yhdistää suhteita ja Ryhmittely-sarakkeiden tekniikoita koosteita varten. Suhteisiin perustuvat koosteet saattavat edellyttää, että denormalisoidut dimensiotaulukot jaetaan useisiin taulukoihin. Jos tämä on kallista tai hankalaa tietyille dimensiotaulukoille, voit replikoida tarvittavat määritteet koostetaulukossa näille dimensioille ja käyttää suhteita muille dimensioille.

Esimerkiksi seuraava malli replikoi **Kuukausi**-, **Vuosineljännes**-, **Puolivuosi**- ja **Vuosi**-arvot **Myyntikooste**-taulukkoon. **Myyntikooste**- ja **Päivämäärä**-taulukoiden välillä ei ole suhdetta, mutta suhteita on **Asiakas**- ja **Tuotteen aliluokka** -taulukoihin. **Myyntikooste**-taulukon tallennustila on tuonti.

![Yhdistetyt koostetekniikat](media/desktop-aggregations/aggregations_15.jpg)

Seuraavassa taulukossa näkyvät **Myyntikooste**-taulukon **Koosteiden hallinta** -valintaikkunassa määritetyt merkinnät. Ryhmittelyperuste-merkinnät, joissa **Päivämäärä** on tietotaulukko, ovat pakollisia osumien saamiseksi koosteista **Päivämäärä**-määritteiden mukaan ryhmittelevillä kyselyillä. Edellisen esimerkin tapaan **Asiakasavain**- ja **Tuotteen aliluokka -avain** -arvojen **Ryhmittelyperuste**-merkinnät eivät vaikuta koosteen osumiin suhteiden vuoksi, lukuun ottamatta DISTINCTCOUNT-funktiota.

![Myyntikooste-koostetaulukon merkinnät](media/desktop-aggregations/aggregations-table_04.jpg)

### <a name="combined-aggregation-query-examples"></a>Yhdistetyn koostekyselyn esimerkit

Seuraava kysely tuottaa osumia koosteessa, koska koostetaulukko kattaa **Kalenterikuukausi**-arvon ja **Luokan nimi** on käytettävissä yksi moneen -suhteiden kautta. **Myyntimäärä**-sarake käyttää **SUMMA**-koostetta.

![Kyselyesimerkki, joka tuottaa osumia koosteessa](media/desktop-aggregations/aggregations-code_09.jpg)

Seuraava kysely ei tuota osumaa koosteessa, koska koostetaulukko ei kata **Kalenteripäivä**-arvoa.

![Kyselyesimerkki, joka ei tuota osumia koosteessa](media/desktop-aggregations/aggregations-code_10.jpg)

Seuraava aikatietokysely ei tuota osumia koosteessa, koska DATESYTD-funktio luo **Kalenteripäivä**-arvojen taulukon, ja **Kalenteripäivä** ei kata koostetaulukkoa.

![Kyselyesimerkki, joka ei tuota osumia koosteessa](media/desktop-aggregations/aggregations-code_11.jpg)

## <a name="aggregation-precedence"></a>Koosteen käsittelyjärjestys

Koosteen käsittelyjärjestys sallii useiden koostetaulukoiden käsittelyn yhtenä alikyselynä.

Seuraava esimerkki on [yhdistelmämalli](desktop-composite-models.md), joka sisältää useita lähteitä:

- **Kuljettajan toiminta** DirectQuery -taulukko sisältää yli biljoona riviä IoT-tietoja, jotka ovat peräisin massadatajärjestelmästä. Se käyttää porautumiskyselyjä yksittäisten IoT-lukemien näyttämiseen hallituissa suodatinkonteksteissa.
- **Kuljettajan toiminnan kooste** -taulukko on välitason koostetaulukko DirectQuery-tilassa. Se sisältää yli miljardi riviä Azure SQL Data Warehousessa ja on optimoitu lähteessä sarakesäilöindeksejä käyttämällä.
- **Kuljettajan toiminnan kooste2** -tuontitaulukon rakeisuus on suurempi, koska ryhmittelyperuste-määritteitä on vähän ja niiden kardinaliteetti on pieni. Rivejä voi olla vain tuhansia, joten se mahtuu helposti välimuistiin. Näitä määritteitä käytetään tärkeässä johtajatason raporttinäkymässä, joten niihin viittaavien kyselyjen on oltava mahdollisimman nopeita.

> [!NOTE]
> DirectQuery-koostetaulukoita, jotka käyttävät tietotaulukon eri tietolähdettä, tuetaan vain, jos koostetaulukko on SQL Server-, Azure SQL- tai Azure SQL Data Warehouse -lähde.

Tässä mallissa muistin käyttö on melko vähäistä, mutta malli avaa valtavan tietojoukon. Se edustaa tasapainotettua arkkitehtuuria, koska se jakaa kyselyn kuormituksen arkkitehtuurin osien välille käyttämällä niitä niiden vahvuuksien mukaan.

![Taulukot pienen käytön mallille, joka avaa valtavan tietojoukon](media/desktop-aggregations/aggregations_13.jpg)

**Kuljettajan toiminnan kooste2** -taulukon **Koosteiden hallinta** -valintaikkunassa määritetään **Käsittelyjärjestys**-kentäksi *10*, mikä on korkeampi kuin **Kuljettajan toiminnan kooste** -taulukossa. Korkeampi käsittelyjärjestysasetus tarkoittaa, että koosteita käyttävät kyselyt kohdistuvat ensin **Kuljettajan toiminnan kooste2** -taulukkoon. Alikyselyt, joihin **Kuljettajan toiminnan kooste2** -taulukko ei voi niiden rakeisuuden vuoksi vastata, kohdistuvat sen sijaan **Kuljettajan toiminnan kooste** -taulukkoon. Tietokyselyt, joihin kumpikaan koostetaulukko ei voi vastata, ohjataan **Kuljettajan toiminta** -taulukkoon.

**Tietotaulukko**-sarakkeessa määritetty sarake on **Kuljettajan toiminta** eikä **Kuljettajan toiminnan kooste**, koska ketjutettuja koosteita ei sallita.

![Koosteiden hallinta -valintaikkuna](media/desktop-aggregations/aggregations_14.jpg)

Seuraavassa taulukossa näytetään **Kuljettajan toiminnan kooste2** -taulukon koosteet.

![Kuljettajan toiminnan kooste2 -koostetaulukko](media/desktop-aggregations/aggregations-table_03.jpg)

## <a name="detect-whether-queries-hit-or-miss-aggregations"></a>Tunnista, tuottavatko kyselyt osumia koosteista vai eivät

SQL Profiler voi tunnistaa, palautetaanko kyselyt muistissa olevan välimuistin tallennusmoduulista vai ohjaako DirectQuery ne tietolähteeseen. Voit saman prosessin avulla tunnistaa, tuotetaanko koosteista osumia. Lisätietoja löytyy artikkelista [Kyselyt, jotka tuottavat osumia tai eivät tuota osumia välimuistista](desktop-storage-mode.md#queries-that-hit-or-miss-the-cache). 

SQL Profiler tarjoaa myös `Query Processing\Aggregate Table Rewrite Query` laajennetun tapahtuman.

Seuraava JSON-katkelma on esimerkki tapahtuman tuloksesta koostetta käytettäessä.

- **matchingResult** näyttää, että alikysely käytti koostetta.
- **dataRequest** näyttää alikyselyn käyttämät Ryhmittelyperuste-sarakkeet ja koostesarakkeet.
- **mapping** näyttää koostetaulukon sarakkeet, joihin yhdistettiin.

![Tapahtuman tulos koostetta käytettäessä](media/desktop-aggregations/aggregations-code_01.jpg)

## <a name="keep-caches-in-sync"></a>Säilytä välimuistit synkronoituina

Koosteet, jotka yhdistävät DirectQuery-, Tuonti- ja/tai Kaksoistaulukot-tallennustilat, saattavat palauttaa eri tietoja, ellei muistissa olevaa välimuistia pidetä synkronoituna lähdetietojen kanssa. Esimerkiksi kyselyn suorittaminen ei yritä peittää tieto-ongelmia suodattamalla DirectQuery-tuloksia välimuistiin tallennettujen arvojen kanssa täsmäämiseksi. On olemassa vakiintuneita tekniikoita tällaisten ongelmien käsittelemiseen lähteessä tarvittaessa. Suorituskyvyn optimointeja tulee käyttää vain siten, ettei se vaaranna liiketoimintavaatimuksiin vastaamista. Vastuullasi on tuntea tietovuosi ja suunnitella ne vastaavasti. 

## <a name="next-steps"></a>Seuraavat vaiheet

Lisätietoja yhdistelmämalleista löytyy artikkeleista:

- [Yhdistelmämallien käyttäminen Power BI Desktopissa](desktop-composite-models.md)
- [Monta moneen -yhteyksien käyttäminen Power BI Desktopissa](desktop-many-to-many-relationships.md)
- [Tallennustilan hallinta Power BI Desktopissa](desktop-storage-mode.md)

Lisätietoja DirectQuerystä löytyy artikkeleista:

- [Tietoja DirectQueryn käytöstä Power BI:ssä](desktop-directquery-about.md)
- [Power BI -tietolähteet](desktop-directquery-data-sources.md)
