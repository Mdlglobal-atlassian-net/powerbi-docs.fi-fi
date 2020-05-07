---
title: Koosteiden (kuten summa ja keskiarvo) käsitteleminen Power BI -palvelussa
description: Opi muuttamaan kaavion koostetta (kuten summa ja keskiarvo) Power BI -palvelussa.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/03/2019
ms.author: maggies
ms.custom: seodec18
LocalizationGroup: Reports
ms.openlocfilehash: bc172f3f5c25a0f0c3773befe5bd846f95a9a2e0
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "74698344"
---
# <a name="work-with-aggregates-sum-average-and-so-on-in-the-power-bi-service"></a>Koosteiden (kuten summa ja keskiarvo) käsitteleminen Power BI -palvelussa

## <a name="what-is-an-aggregate"></a>Mikä on kooste?

Joskus on tarpeen yhdistellä tiedoissa olevia arvoja matemaattisesti. Laskutoimituksena voi olla esimerkiksi summa, keskiarvo, suurin arvo tai lukumäärä. Kun yhdistät tietojen arvoja, sitä kutsutaan *koostamiseksi*. Tämän laskutoimituksen tulos on *kooste*.

Kun Power BI -palvelulla ja Power BI Desktopilla luodaan visualisointeja, niissä saatetaan koostaa tietoja. Kooste on yleensä juuri se, mitä halusitkin, mutta toisinaan on tarpeen koostaa arvoja eri tavalla.  Esimerkiksi summa verrattuna keskiarvoon. Koosteen käyttämistä Power BI:n visualisoinnissa voi hallita ja muuttaa useilla eri tavoilla.

Tutustutaan ensin *tietotyyppeihin*, koska tietojen tyyppi määrittää, miten Power BI voi koostaa niitä ja voiko se koostaa niitä.

## <a name="types-of-data"></a>Tietojen tyypit

Useimmat tietojoukot sisältävät useita tietotyyppejä. Aivan perustasollaan tieto on joko numeerinen tai ei-numeerinen. Power BI voi koostaa numeerisia tietoja käyttämällä esimerkiksi summaa, keskiarvoa, määrää, pienintä arvoa ja varianssia. Palvelu voi koostaa jopa tekstimuotoista tietoa, jota kutsutaan *luokittaiseksi* tiedoksi. Jos yrität koostaa luokkakentän sijoittamalla sen vain numeerisia tietoja hyväksyvään säilöön, kuten **Arvot** tai **Työkaluvihjeet**, Power BI laskee jokaisen luokan esiintymiskerrat tai jokaisen luokan erilliset esiintymiskerrat. Tietynlaisilla tiedoilla, kuten päivämäärillä, on eräitä omia koostevaihtoehtojaan: aikaisin, viimeisin, ensimmäinen ja viimeinen.

Alla olevassa esimerkissä:

- **Yksikköjä myyty** ja **Valmistuksen hinta** ovat numeerisia tietoja sisältäviä sarakkeita.

- **Segmentti**, **Maa**, **Tuote**, **Kuukausi** ja **Kuukauden nimi** sisältävät luokittaista tietoa.

   ![Näyttökuva mallitietojoukosta.](media/service-aggregates/power-bi-aggregate-chart.png)

Kun luot visualisointia Power BI:ssä, palvelu koostaa numeeriset kentät (oletusarvo on *summa*) suhteessa johonkin luokittaiseen kenttään.  Koosteita voivat olla esimerkiksi yksikköjä myyty ***tuotteen mukaan***, yksikköjä myyty ***kuukauden mukaan*** tai valmistuksen hinta ***segmentin mukaan***. Power BI viitaa joihinkin numeerisiin kenttiin **mittareina**. Power BI -raporttieditorissa mittarit on helppo tunnistaa. Niiden vieressä **Kentät**-luettelossa näkyy ∑-symboli. Lisätietoja on artikkelissa [Raporttieditorin esittely](service-the-report-editor-take-a-tour.md).

![Näyttökuva Power BI:stä, jossa näkyy Kentät-luettelo.](media/service-aggregates/power-bi-aggregate-fields.png)

## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>Miksi koosteet eivät toimi haluamallani tavalla?

Koosteiden käsitteleminen Power BI -palvelussa voi vaikuttaa sekavalta. Sinulla voi olla numeerinen kenttä, eikä Power BI anna sinun muuttaa koostetta. Tai ehkäpä sinulla on kenttä, kuten vuosi, jota et halua koostaa vaan vain laskea sen esiintymien määrän.

Yleensä taustalla oleva ongelma on tietojoukon kentän kuvaus. Tietojoukon omistaja on ehkä määrittänyt kentän tekstiksi, mikä selittää, miksi Power BI ei voi laskea sen summaa tai keskiarvoa. Valitettavasti [vain tietojoukon omistaja voi muuttaa kenttien luokittelun tapaa](desktop-measures.md). Jos sinulla on tietojoukkoon omistajan käyttöoikeudet joko Power BI Desktopissa tai ohjelmassa, jolla tietojoukko luotiin (kuten Excel), voit siksi korjata ongelman. Muussa tapauksessa tarvitset muuttamiseen tietojoukon omistajan apua.  

Tämän artikkelin lopussa on erikoisosa nimeltä [**Huomioon otettavat seikat ja vianmääritys**](#considerations-and-troubleshooting). Siinä on vihjeitä ja ohjeita. Jos et löydä vastausta osiosta, julkaise kysymys [Power BI -yhteisön keskustelupalstalla](https://community.powerbi.com). Saat vastauksen pikaisesti suoraan Power BI -tiimiltä.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Numeerisen kentän koostetavan muuttaminen

Oletetaan, että sinulla on kaavio, joka laskee yhteen eri tuotteiden myydyt yksiköt, mutta haluaisit mieluummin nähdä keskiarvon.

1. Luo **yhdistelmäpylväskaavio**, joka käyttää mittaria ja luokkaa. Tässä esimerkissä käytetään myytyjä yksiköitä tuotteen mukaan.  Oletusarvoisesti Power BI luo kaavion, joka laskee yhteen myydyt yksiköt (vedä mittari **Arvot**-säilöön) jokaiselle tuotteelle (vedä luokka **Akseli**-säilöön).

   ![Näyttökuva kaaviosta, Visualisoinnit-ruudusta ja Kentät-luettelosta, jossa näkyy Summa.](media/service-aggregates/power-bi-aggregate-sum.png)

1. Napsauta **Visualisoinnit**-ruudussa mittaria hiiren kakkospainikkeella ja valitse haluamasi koosteen tyyppi. Tässä tapauksessa valitsemme vaihtoehdon **Keskiarvo**. Jos et näe tarvitsemaasi koostetta, tutustu osaan [**Huomioon otettavat seikat ja vianmääritys**](#considerations-and-troubleshooting).

   ![Näyttökuva koosteluettelosta, jossa Keskiarvo on valittuna ja näkyvissä.](media/service-aggregates/power-bi-aggregate-average.png)

   > [!NOTE]
   > Avattavan valikon vaihtoehdot vaihtelevat 1) valitun kentän ja 2) tietojoukon omistajan määrittämän kentän luokittelutavan mukaan.

1. Visualisointi käyttää nyt koostetta keskiarvon mukaan.

   ![Näyttökuva kaaviosta, jossa näkyy nyt myytyjen yksiköiden keskiarvo tuotteittain.](media/service-aggregates/power-bi-aggregate-average-2.png)

## <a name="ways-to-aggregate-your-data"></a>Tietojen koostamisen tavat

Tässä on eräitä asetuksia, jotka voivat olla käytettävissä kentän koostamiseen:

- **Älä tee yhteenvetoa**. Kun tämä asetus on valittu, Power BI käsittelee jokaista kyseisen kentän arvoa käsitellään erikseen, eikä laske niitä yhteen. Käytä tätä asetusta, jos sinulla on numeerinen tunnistesarake, jota palvelun ei tule laskea yhteen.

- **Summa**. Tämä laskee yhteen kaikki kyseisen kentän arvot.

- **Keskiarvo**. Laskee arvoista aritmeettisen keskiarvon.

- **Pienin arvo**. Näyttää pienimmän arvon.

- **Suurin arvo**. Näyttää suurimman arvon.

- **Määrä (ei tyhjä).** Tämä laskee kentän niiden arvojen määrän, jotka eivät ole tyhjiä.

- **Määrä (erillinen).** Tämä laskee tämän kentän eri arvojen määrän.

- **Keskihajonta.**

- **Varianssi**.

- **Mediaani**.  Näyttää mediaaniarvon eli joukon keskimmäisen arvon. Tämä on arvo, jonka ylä- ja alapuolella on sama määrä kohteita.  Jos mediaaneja on kaksi, Power BI laskee niiden keskiarvon.

Käytetään esimerkkinä näitä tietoja:

| Maa | Määrä |
|:--- |:--- |
| Yhdysvallat |100 |
| Iso-Britannia |150 |
| Kanada |100 |
| Saksa |125 |
| Ranska | |
| Japani |125 |
| Australia |150 |

Saamme tiedoista seuraavia tuloksia:

- **Älä tee yhteenvetoa**: kukin arvo näkyy erikseen

- **Summa**: 750

- **Keskiarvo**: 125

- **Suurin arvo**:  150

- **Pienin arvo**: 100

- **Määrä (ei tyhjä):** 6

- **Määrä (erillinen):** 4

- **Keskihajonta:** 20.4124145...

- **Varianssi:** 416.666...

- **Mediaani:** 125

## <a name="create-an-aggregate-using-a-category-text-field"></a>Koosteen luominen luokittaisesta kentästä (tekstikentästä)

Voit koostaa myös ei-numeerisen kentän. Esimerkiksi jos sinulla on kenttä tuotteen nimelle, voit lisätä sen arvona ja määrittää sen arvoksi **Määrä**, **Erillisten määrä**, **Ensimmäinen** tai **Viimeinen**.

1. Vedä **Tuote**-kenttä **Arvot**-säilöön. **Arvot**-säilöä käytetään yleensä numeerisissa kentissä. Power BI tunnistaa, että tämä kenttä on tekstikenttä, asettaa koosteeksi **Älä tee yhteenvetoa** ja esittää sinulle yksisarakkeisen taulukon.

   ![Näyttökuva Arvot-säilön Tuote-kentästä.](media/service-aggregates/power-bi-aggregate-value.png)

1. Jos muutat koostamisen **Älä tee yhteenvetoa** -oletusasetuksen asetukseksi **Määrä (erillinen)** , Power BI laskee eri tuotteiden määrän. Tässä tapauksessa niitä on neljä.
  
   ![Näyttökuva erillisten tuotteiden määrästä.](media/service-aggregates/power-bi-aggregate-count.png)

1. Jos muutat koosteasetukseksi **Määrä**, Power BI laskee kokonaismäärän. Tässä tapauksessa **Tuote**-kirjauksia on seitsemän.

   ![Näyttökuva tuotteiden määrästä.](media/service-aggregates/power-bi-aggregate-count-2.png)

1. Jos sama kenttä (tässä tapauksessa **Tuote**) vedetään **Arvot**-säilöön ja koosteasetukseksi jätetään **Älä tee yhteenvetoa** -oletusasetus, Power BI erittelee määrän tuotteen mukaan.

   ![Näyttökuva tuotteesta ja tuotteiden määrästä.](media/service-aggregates/power-bi-aggregate-final.png)

## <a name="considerations-and-troubleshooting"></a>Huomioon otettavat seikat ja vianmääritys

Kysymys:  Miksi en näe **Älä tee yhteenvetoa** -vaihtoehtoa?

Vastaus:  Valitsemasi kenttä on todennäköisesti laskettu mittari tai Excelissä tai [Power BI Desktopissa](desktop-measures.md) luotu kehittynyt mittari. Jokaisella lasketulla mittarilla on oma pysyväiskoodattu kaavansa. Et voi muuttaa koostetta, jota Power BI käyttää. Jos kyseessä on esimerkiksi summa, se voi olla vain summa. *Lasketut mittarit* näkyvät **Kentät**-luettelossa laskinsymbolilla merkittyinä.

Kysymys:  Kenttäni **on** numeerinen, joten miksi vaihtoehtoja ovat vain **Määrä** ja **Erillisten määrä**?

Vastaus 1:  Todennäköinen selitys on, että tietojoukon omistaja *ei* ole luokitellut kenttää numeroksi. Jos tietojoukossa on esimerkiksi **vuosi**kenttä, tietojoukon omistaja voi luokitella arvon tekstiksi. On todennäköistä, että Power BI laskee**vuosi**kentän (esimerkiksi vuonna 1974 syntyneiden ihmisten määrän). On epätodennäköisempää, että Power BI laskisi summan tai keskiarvon. Jos olet tietojoukon omistaja, voit avata sen Power BI Desktopissa ja muuttaa sen tyypin **Mallinnus**-välilehdessä.

Vastaus 2: Jos kentässä on laskinkuvake, se tarkoittaa, että kenttä on *laskettu mittari*. Jokaisella lasketulla mittarilla on oma pysyväiskoodattu kaavansa, jota vain tietojoukon omistaja voi muuttaa. Power BI:n käyttämä laskutoimitus voi olla yksinkertainen kooste, kuten keskiarvo tai summa. Se voi myös olla jotain monimutkaisempaa, kuten ”osallistumisen prosenttiosuus pääluokkaan” tai ”juokseva summa vuoden alusta”. Power BI ei laske tulosten summaa eikä keskiarvoa. Sen sijaan se vain laskee uudelleen (käyttäen pysyväiskoodattua kaavaa) jokaisen arvopisteen.

Vastaus 3:  Toinen mahdollisuus on, että olet vetänyt kentän *säilöön*, joka sallii vain luokittaiset arvot.  Tässä tapauksessa asetuksia ovat vain on Määrä ja Erillinen määrä.

Vastaus 4:  Lopulta neljäntenä mahdollisuutena on, että käytät kenttää akselina. Esimerkiksi palkkikaavion akselilla Power BI näyttää yhden palkin jokaiselle erilliselle arvolle eikä koosta kenttien arvoja lainkaan.

>[!NOTE]
>Poikkeus sääntöön ovat pistekaaviot, jotka *edellyttävät* koostettuja arvoja X- ja Y-akseleille.

Kysymys:  Miksi SQL Server Analysis Services (SSAS) -tietolähteille ei voi koostaa tekstikenttiä?

Vastaus:  Jos muodostat yhteyksiä reaaliajassa SSAS-monidimensiomalleihin, et voi käyttää asiakaspuolen koosteita (kuten ensimmäinen, viimeinen, keskiarvo, pienin arvo, suurin arvo ja summa).

Kysymys:  Minulla on pistekaavio, mutta haluan, että kenttääni *ei* koosteta.  Miten?

Vastaus:  Lisää kenttä **Tiedot**-säilöön X- tai Y-akselien säilöjen sijaan.

Kysymys:  Kun lisään numeerisen kentän visualisointiin, useimpien oletusasetuksena on summa, mutta joissakin se on keskiarvo, määrä tai jokin muu kooste.  Miksi koosteen oletusarvo ei ole aina sama?

Vastaus:  Tietojoukon omistajat voivat määrittää oletusyhteenvedon jokaiselle kentälle. Jos olet tietojoukon omistaja, voit muuttaa oletusyhteenvetoa Power BI Desktopin **Mallinnus**-välilehdessä.

Kysymys:  Olen tietojoukon omistaja ja haluat varmistaa, ettei tiettyä kenttää koosteta ollenkaan.

Vastaus:  Määritä Power BI Desktopin **Mallinnus**-välilehdellä **Tietotyyppi**-asetukseksi **Teksti**.

Kysymys:  En näe **Älä tee yhteenvetoa** -vaihtoehtoa avattavassa luettelossa.

Vastaus:  Yritä poistaa kenttä ja lisätä se sitten takaisin.

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](https://community.powerbi.com/)