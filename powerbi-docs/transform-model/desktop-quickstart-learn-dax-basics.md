---
title: DAX-perusteet Power BI Desktopissa
description: DAX-perusteet Power BI Desktopissa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/21/2019
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 783a9bdce34345afd87be379aff7e073ff8c548d
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565852"
---
# <a name="apply-dax-basics-in-power-bi-desktop"></a>Käytä DAX-perusteita Power BI Desktopissa
Tämä artikkeli on tarkoitettu uusille Power BI Desktopin käyttäjille. Se antaa sinulle helpon ja nopean esittelyn siitä, miten voit käyttää Data Analysis Expression (DAX) -kaavaa ja ratkaista sillä useita peruslaskutoimituksia ja tietojen analysointiongelmia. Artikkeli sisältää käsitteellisiä tietoja, joukon harjoitustehtäviä ja lähtötasotestin, jolla voit testata, mitä olet oppinut. Kun olet käynyt tämän artikkelin läpi, sinulla pitäisi olla hyvä käsitys DAX:n tärkeimmistä peruskäsitteistä.

## <a name="what-is-dax"></a>Mikä DAX on?
DAX on kokoelma funktioita, operaattoreita ja vakioita, joita voidaan käyttää kaavoissa tai lausekkeissa yhden tai useamman arvon laskemiseen ja palauttamiseen. Yksinkertaisemmin ilmaistuna, DAX auttaa sinua luomaan uusia tietoja mallisi jo sisältämistä tiedoista.

## <a name="why-is-dax-so-important"></a>Miksi DAX on tärkeä?
Uuden Power BI Desktop -tiedoston luominen ja tietojen tuominen siihen on helppoa. Voit myös luoda raportteja, jotka näyttävät arvokasta tietoa käyttämättä ollenkaan DAX-kaavoja. Mutta entä jos sinun tarvitsee analysoida kaikkien tuoteluokkien kasvuprosenttia ja eri päivämääräväleiltä? Tai haluat laskea vuoden vuosittaisen kasvun verrattuna markkinoiden kehitykseen? DAX-kaavat mahdollistavat nämä ja tarjoavat lisäksi monia muita tärkeitä ominaisuuksia. Kun opettelet tehokkaiden DAX-kaavojen luonnin, se auttaa sinua hyödyntämään tietojasi mahdollisimman tehokkaasti. Kun saat tarvitsemasi tiedot, voit aloittaa todellisten liiketoimintaongelmien ratkaisemisen, jotka vaikuttavat yrityksen tulokseen. Tämä on Power BI:n voima, ja DAX auttaa sinua saavuttamaan sen.

## <a name="prerequisites"></a>Edellytykset
Kaavojen luominen Microsoft Excelissä saattaa olla sinulle jo tuttua. Tästä tietämyksestä on apua DAX:n ymmärtämisessä, mutta vaikka sinulla ei olisi kokemusta Excel-kaavoista, tässä kuvattujen käsitteiden avulla pääset heti alkuun DAX-kaavojen luomisessa ja oikeiden liiketoimintatiedon hallintaongelmien ratkaisemissa.

Painopisteenä on saada antaa käsitys DAX-kaavoista, joita käytetään laskutoimituksissa, ja erityisesti mittareissa ja lasketuissa sarakkeissa. Power BI Desktopin, tietojen tuonnin ja kenttien lisäämisen raporttiin tulisi olla sinulle jo tuttuja, minkä lisäksi sinun tulisi tuntea peruskäsitteet [mittari](desktop-measures.md) ja [laskettu sarake](desktop-calculated-columns.md).

### <a name="example-workbook"></a>Esimerkkityökirja

Paras tapa oppia DAX on luoda joitakin peruskaavoja, käyttää niitä todellisten tietojen kanssa ja nähdä tulokset itse. Tässä esitetyissä esimerkeissä ja tehtävissä käytetään [Contoso Sales Sample for Power BI Desktop -tiedostoa](https://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20for%20Power%20BI%20Designer.zip). Mallitiedosto on sama, jota käytetään [Opetusohjelmassa: Omien mittarien luominen Power BI Desktopissa](desktop-tutorial-create-measures.md) -artikkelissa. 

## <a name="lets-begin"></a>Aloitetaan!
Muodostamme ymmärryksemme DAX:ista kolmen peruskäsitteen ympärille: *syntaksi*, *funktiot* ja *konteksti*. DAX sisältää muitakin tärkeitä käsitteitä, mutta näiden kolmen käsitteen ymmärtäminen tarjoaa parhaan perustan DAX-taidoillesi.

### <a name="syntax"></a>Syntaksi
Ennen kuin luot omia kaavoja, tutustutaan DAX-kaavan syntaksiin. Syntaksi sisältää eri elementtejä, jotka muodostavat kaavan, tai yksinkertaisemmin ilmaistuna se kertoo, kuinka kaava on kirjoitettu. Tässä on esimerkiksi yksinkertainen mittarin DAX-kaava:

![DAX-kaavan syntaksi](media/desktop-quickstart-learn-dax-basics/qsdax_1_syntax.png)

Tämä kaava sisältää seuraavat syntaksielementit:

**A.** Mittarin nimi **Total Sales**.

**B.** Yhtäläisyysmerkkioperaattori ( **=** ), joka ilmaisee kaavan alun. Kun laskutoimitus on tehty, se palauttaa tuloksen.

**C.** DAX-funktio **SUM**, joka laskee yhteen kaikki **Sales[SalesAmount]** -sarakkeen luvut. Funktioista on lisätietoja jäljempänä.

**D.** Kaarisulkeet **()** , jotka ympäröivät lauseketta, joka sisältää yhden tai useampia argumentteja. Kaikki funktiot vaativat vähintään yhden argumentin. Argumentti välittää arvon funktiolle.

**E.** Viitattu taulukko **Sales**-taulukko.

**F.** Viitattu sarake **[SalesAmount]** Sales-taulukossa. Tämän argumentin avulla SUM-funktio tietää, mihin sarakkeeseen SUM eli summa koostetaan.

Kun yrität ymmärtää DAX-kaavaa, on usein hyödyllistä eritellä kukin elementti kielellä, jolla ajattelet ja jota puhut päivittäin. Voit esimerkiksi lukea tämän kaavan seuraavasti:

> *Mittarille nimeltä Total Sales, laske (=) Sales-taulukon [SalesAmount ] -sarakkeen arvojen summa (SUM).*
> 
> 

Kun tämä mittari lisätään raporttiin, se laskee ja palauttaa arvot laskemalla yhteen myyntimäärät kaikkien muiden kenttien osalta, jotka otamme mukaan, esimerkiksi matkapuhelimet Suomessa.

Saatat ajatella: ”Eikö tämä mittari tee saman kuin jos vain lisäisin SalesAmount-kentän omaan raporttiini?” Kyllä vain. Mutta on hyvä syy sille, miksi kannattaa luoda oma mittari, joka laskee yhteen SalesAmount-kentän arvoja: voimme käyttää sitä argumenttina muissa kaavoissa. Tämä saattaa nyt vaikuttaa hieman sekavalta, mutta kun DAX-kaavataitosi kasvavat, tämän menetelmän tietäminen tekee kaavoistasi ja mallistasi tehokkaampia. Tulet itse asiassa näkemään Total Sales -mittarin argumenttina muissa kaavoissa myöhemmin.

Käydäänpä seuraavaksi läpi muutamia muita tätä kaavaa koskevia seikkoja. Toimme esiin erityisesti funktion [SUM](/dax/sum-function-dax). Funktiot ovat ennalta laadittuja kaavoja, jotka helpottavat monimutkaisia laskutoimituksia ja käsittelytoimintoja mm. numeroiden, päivämäärien, ajan ja tekstin kanssa. Funktioista on lisätietoja jäljempänä.

Näet myös, että kaavassa sarakkeen nimen [SalesAmount] edellä oli Sales-taulukko, johon sarake kuuluu. Tätä nimeä kutsutaan sarakkeen täydelliseksi nimeksi, koska se sisältää sarakkeen nimen, jonka edessä on taulukon nimi. Viitattaessa saman taulukon sisällä oleviin sarakkeisiin kaavaan ei tarvita taulukon nimeä. Tämän avulla pitkistä kaavoista, jotka viittaavat moniin sarakkeisiin, saadaan lyhempiä ja helpommin luettavia. On kuitenkin hyvä sisällyttää taulukon nimi mittarikaavoihin, myös silloin kun ne ovat samassa taulukossa.

> [!NOTE]
> Jos taulukon nimessä on välilyöntejä, varattuja avainsanoja tai ei-sallittuja merkkejä, sinun on kirjoitettava taulukon nimi puolilainausmerkkien sisään. Taulukoiden nimet on kirjoitettava lainausmerkkien sisään myös, jos nimi sisältää aakkosnumeeriseen ANSI-merkkialueeseen kuulumattomia merkkejä, huolimatta siitä, tukevatko aluekohtaiset asetukset merkistöä vai ei.
> 
> 

On tärkeää, että kaavojen syntaksi on oikea. Jos syntaksi ei ole oikea, useimmissa tapauksissa ohjelma palauttaa syntaksivirheen. Muissa tapauksissa syntaksi voi olla oikea, mutta palautetut arvot eivät välttämättä ole sellaisia, joita odotit. Power BI Desktopin DAX-editorissa on ehdotustoiminto, jota käytetään syntaktisesti oikeiden kaavojen luomiseen auttamalla sinua valitsemaan oikeat elementit.

Luodaanpa yksinkertainen kaava. Tämä tehtävä auttaa sinua ymmärtämään paremmin kaavan syntaksia ja sitä, miten kaavarivin ehdotustoiminto voi auttaa sinua.

### <a name="task-create-a-measure-formula"></a>Tehtävä: mittarin kaavan luominen

1. [Lataa](https://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20for%20Power%20BI%20Designer.zip) ja avaa Contoso Sales Sample Power BI Desktop -tiedosto. 
    
2. Napsauta raporttinäkymän kenttäluettelossa hiiren kakkospainikkeella **Sales**-taulukkoa ja valitse sitten **Uusi mittari**.
    
3. Korvaa kaavarivillä näkyvä **Measure** (Mittari) -sana kirjoittamalla uusi mittarin nimi *Previous Quarter Sales* (Edellisen neljänneksen myynti).
    
4. Kirjoita yhtäläisyysmerkin jälkeen ensimmäiset kirjaimet *CAL* ja kaksoisnapsauta sitten haluamaasi funktiota. Tässä kaavassa halutaan käyttää **CALCULATE**-funktiota.

   CALCULATE-funktion avulla suodatat määrät, jotka haluamme laskea yhteen argumentilla, jonka välitämme CALCULATE-funktioon. Näitä kutsutaan sisäkkäisiksi funktioiksi. CALCULATE-funktiolla on vähintään kaksi argumenttia. Ensimmäinen on laskettava lauseke, ja toinen on suodatin.
   
5. Kirjoita **CALCULATE**-funktion alkusulkeen *(* jälkeen *SUM* ja sen toinen alkusulje *(* . 

   Seuraavaksi välitämme argumentin SUM-funktioon.

6. Ala kirjoittaa *Sal*, ja valitse sitten **Sales[SalesAmount]** ja lisää sen jälkeen loppusulje *)* . 

   Tämä on CALCULATE-funktiomme ensimmäinen lausekeargumentti.
    
7. Kirjoita pilkku ( *,* ) ja lisää sen perään välilyönti, mikä määrittää ensimmäisen suodattimen. Kirjoita sitten *PREVIOUSQUARTER*. 
    
   Käytät PREVIOUSQUARTER-aikatietofunktiota suodattaaksesi SUM-tulokset edellisellä neljänneksellä.
    
8. Kirjoita PREVIOUSQUARTER-funktion alkusulkeen *(* jälkeen *Calendar[DateKey]* .
    
   PREVIOUSQUARTER-funktiolla on yksi argumentti, peräkkäisistä päivämääristä muodostuvan alueen sisältä sarake. Tässä tapauksessa kyseessä on kalenteri-taulukon DateKey-sarake.
    
9. Lisää PREVIOUSQUARTER-funktioon ja CALCULATE-funktioon välitettyjen argumenttien perään kaksi loppusuljetta *))* .
    
   Kaavan pitäisi nyt näyttää tältä:
    
   **Previous Quarter Sales = CALCULATE(SUM(Sales[SalesAmount]), PREVIOUSQUARTER(Calendar[DateKey]))**
    
10. Valitse valintamerkki ![Valintamerkkikuvake](media/desktop-quickstart-learn-dax-basics/qsdax_syntax_taskcheckmark.png) kaavarivillä tai paina Enter vahvistaaksesi kaavan ja lisätäksesi se malliin.

Teit sen! Olet juuri luonut monitasoisen mittarin käyttämällä DAX-kaavaa, eikä mitään helppoa sitä paitsi. Tämä kaava laskee edellisen vuosineljänneksen kokonaismyynnin raportissa käytettyjen suodattimien mukaan. Jos esimerkiksi sijoitamme SalesAmount-mittarin ja uuden Previous Quarter Sales -mittarimme kaavioon ja lisäämme sen jälkeen Year- ja QuarterOfYear-kentät osittajiksi, saisimme tulokseksi jotakin tämänkaltaista:

![Previous Quarter Sales- ja SalesAmount-kaavio](media/desktop-quickstart-learn-dax-basics/qsdax_3_chart.png)

Olet juuri tutustunut muutamiin tärkeisiin DAX-kaavoihin liittyviin näkökohtiin: 

- Tämä kaava sisälsi kaksi funktiota. Aikatietofunktio [PREVIOUSQUARTER](/dax/previousquarter-function-dax) asetettiin sisäkkäin argumenttina, joka välitettiin suodatusfunktioon [CALCULATE](/dax/calculate-function-dax). 

   DAX-kaavat voivat sisältää jopa 64 sisäkkäistä funktiota. On epätodennäköistä, että mikään kaava koskaan sisältäisi näin paljon sisäkkäisiä funktioita. Itse asiassa tällaisen kaavan luominen ja sen virheenkorjaus olisi vaikeaa, eikä se todennäköisesti olisi myöskään kovin nopea.

- Tässä kaavassa käytit myös suodattimia. Suodattimet rajaavat sen, mitä lasketaan. Tässä tapauksessa valitsit yhden suodattimen argumentiksi, joka on itse asiassa toisen funktion tulos. Suodattimista on lisätietoja jäljempänä.

- Käytit CALCULATE-funktiota. Tämä funktio on yksi DAX-kaavan tehokkaimmista funktioista. Laatiessasi malleja ja luodessasi monimutkaisempia kaavoja tulet todennäköisesti käyttämään tätä funktiota monta kertaa. Vaikka tarkempi CALCULATE-funktion käsittely on tämän artikkelin aihealueen ulkopuolella, DAX-osaamisesi kasvaessa kiinnitä siihen erityistä huomiota.

### <a name="syntax-quickquiz"></a>Testaa tietosi syntaksista
1. Mitä tämä kaavarivin painike tekee?
   
   > ![Painikkeen valinta](media/desktop-quickstart-learn-dax-basics/qsdax_2_syntaxquiz.png)
   > 
   > 
2. Mitä DAX-kaavassa on aina sarakkeen nimen ympärillä?

Vastaukset ovat tämän artikkelin lopussa.

### <a name="functions"></a>Funktiot
Funktiot ovat ennalta määritettyjä kaavoja, jotka suorittavat laskutoimituksia käyttämällä erityisiä arvoja eli argumentteja tietyssä järjestyksessä tai tietyssä rakenteessa. Argumentit voivat olla muita funktioita, muita kaavoja, lausekkeita, sarakeviittauksia, numeroita, tekstiä, loogisia arvoja, kuten TOSI tai EPÄTOSI, tai vakioita.

DAX sisältää seuraavat funktioluokat: [päivämäärä- ja aikafunktiot](/dax/date-and-time-functions-dax), [aikatietofunktiot](/dax/time-intelligence-functions-dax), [tietofunktiot](/dax/information-functions-dax), [loogiset](/dax/logical-functions-dax), [matemaattiset](/dax/math-and-trig-functions-dax) ja [tilastolliset funktiot](/dax/statistical-functions-dax), [tekstifunktiot](/dax/text-functions-dax), [pääkohde-/alikohdefunktiot](/dax/parent-and-child-functions-dax) ja [muut](/dax/other-functions-dax) funktiot. Jos funktiot ovat sinulle tuttuja Excel-kaavoista, monet DAX-kielen funktiot vaikuttavat vastaavanlaisilta. DAX-funktiot ovat kuitenkin ainutlaatuisia seuraavin tavoin:

* DAX-funktio viittaa aina kokonaiseen sarakkeeseen tai taulukkoon. Jos haluat käyttää vain tiettyjä arvoja taulukosta tai sarakkeesta, voit lisätä kaavaan suodattimia.
* Jos laskutoimituksia on mukautettava rivikohtaisesti, voit tiettyjen DAX-funktioiden avulla suorittaa kontekstin mukaan vaihtelevia laskutoimituksia käyttämällä nykyistä rivin arvoa tai liittyvää arvoa eräänlaisena argumenttina. Kontekstista on lisätietoja jäljempänä.
* DAX sisältää monia funktioita, jotka palauttavat arvon sijasta taulukon. Taulukkoa ei näytetä, mutta sitä käytetään luomaan syötteitä muille funktioille. Voit esimerkiksi noutaa taulukon ja laskea sitten sen eri arvot tai laskea dynaamisia summia suodatetuissa taulukoissa tai sarakkeissa.
* DAX sisältää erilaisia aikatietojen funktioita. Näiden funktioiden avulla voit määrittää tai valita päivämäärävälejä ja suorittaa näihin perustuvia dynaamisia laskutoimituksia. Voit esimerkiksi verrata rinnakkaisten vuosineljännesten summia.
* Excelissä on suosittu funktio, PHAKU. DAX-funktiot eivät käsitä solua tai solualuetta viitteeksi, kuten PHAKU tekee Excelissä. DAX-funktiot ottavat viitteeksi sarakkeen tai taulukon. Pidä mielessä, että Power BI Desktopissa työskentelet relaatiotietomallin kanssa. Arvojen hakeminen toisesta taulukosta on helppoa, ja useimmissa tapauksissa sinun ei tarvitse luoda kaavoja lainkaan.
  
  Kuten huomaat, DAX-funktioiden avulla voit luoda tehokkaita kaavoja. Ja olemme käsitelleet vasta funktioiden perusteita. DAX-taitojesi kasvaessa opit luomaan kaavoja, joissa käytät useita eri funktioita. Yksi parhaimmista kaikkia DAX-funktioita koskevia tarkempia tietoja sisältävistä resursseista on [DAX Function Reference](/dax/) -artikkeli.

### <a name="functions-quickquiz"></a>Testaa tietosi funktioista
1. Mihin funktio aina viittaa?
2. Voiko kaava sisältää useamman kuin yhden funktion?
3. Mitä funktioluokkaa käyttäisit kahden tekstimerkkijonon liittämiseen yhdeksi merkkijonoksi?

Vastaukset ovat tämän artikkelin lopussa.

### <a name="context"></a>Konteksti
Konteksti on yksi niistä DAX-käsitteistä, joiden ymmärtäminen on hyvin tärkeää. DAX-kielessä on kahdentyyppisiä konteksteja: rivikonteksti ja suodatinkonteksti. Tarkastelemme ensin rivikontekstia.

**Rivikonteksti**

Rivikonteksti ymmärretään tavallisesti nykyiseksi riviksi. Sitä käytetään aina, kun kaavassa on funktio, joka käyttää suodattimia taulukon yksittäisen rivin tunnistamiseen. Funktio käyttää luontaisesti rivikontekstia jokaiseen sen taulukon riviin, jota se suodattaa. Tämäntyyppistä rivikontekstia sovelletaan useimmiten mittareihin.

**Suodatinkonteksti**

Suodatinkonteksti on hieman vaikeampi ymmärtää kuin rivikonteksti. Suodatinkontekstia voi ajatella seuraavasti: Yksi tai useampi suodatin käytössä laskutoimituksessa, joka määrittää yksittäisen tuloksen tai arvon.

Suodatinkontekstia ei käytetä rivikontekstin sijasta, vaan sitä käytetään rivikontekstin lisäksi. Jos esimerkiksi haluat rajata laskutoimitukseen sisällytettäviä arvoja tarkemmin, voit käyttää suodatinkontekstia, joka määrittää paitsi rivikontekstin myös tietyn arvon (suodattimen) kyseisessä rivikontekstissa.

Suodatinkontekstia näkee helpoimmin raporteissa. Kun esimerkiksi lisäät visualisointiin TotalCost-arvon ja lisäät sen jälkeen vuoden ja alueen, määrität suodatinkontekstin, joka valitsee tietojen alijoukon antamasi tietyn vuoden ja alueen perusteella.

Miksi suodatinkonteksti on niin tärkeä DAX-kielelle? Suodatinkontekstia on helpointa käyttää lisäämällä visualisointiin kenttiä, mutta suodatinkontekstia voidaan myös käyttää DAX-kaavassa määrittämällä suodatin, joka käyttää funktioita kuten ALL, RELATED, FILTER ja CALCULATE, käyttämällä suhteita ja käyttämällä muita mittareita ja sarakkeita. Tarkastellaanpa esimerkiksi seuraavaa kaavaa StoreSales-nimisessä mittarissa:

![Store Sales -mittari](media/desktop-quickstart-learn-dax-basics/qsdax_4_context.png)

Tämä kaava on helpompi ymmärtää, kun se eritellään samalla tavalla kuin muut kaavat edellä.

Tämä kaava sisältää seuraavat syntaksielementit:

**A.** Mittarin nimi **Store Sales**.

**B.** Yhtäläisyysmerkkioperaattori ( **=** ), joka ilmaisee kaavan alun.

**C.** **CALCULATE**-funktio, joka laskee argumenttina lausekkeen kontekstissa, jota on muutettu määritetyillä suodattimilla.

**D.** Kaarisulkeet **()** , jotka ympäröivät lauseketta, joka sisältää yhden tai useampia argumentteja.

**E.** Mittari **[Total Sales]** samassa taulukossa lausekkeena. Total Sales -mittarin kaava on: =SUM(Sales[SalesAmount]).

**F.** Pilkku ( **,** ), joka erottaa ensimmäisen lausekeargumentin suodatinargumentista.

**G.** Täydellinen viitattu sarake **Channel [ChannelName]** . Tämä on rivikontekstimme. Jokainen rivi tässä sarakkeessa määrittää kanavan, kuten Store tai Online.

**H.** Tietty arvo, **Store**, suodattimena. Tämä on suodatinkontekstimme.

Tämä kaava varmistaa, että vain Total Sales -mittarin suodattimena määrittämät myyntiarvot lasketaan vain Channel[ChannelName]-sarakkeen sellaisille riveille, joissa on suodattimena *Store*-arvo.

Kuten voit kuvitella, mahdollisuus määrittää suodatinkonteksteja kaavassa tarjoaa valtaisaa ja tehokasta käyttöpotentiaalia. Mahdollisuus viitata vain tiettyyn arvoon liittyvässä taulukossa on vain yksi esimerkki siitä. Älä huolestu, vaikka et heti ymmärtäisikään kontekstia täysin. Kun luot omia kaavojasi, opit paremmin ymmärtämään kontekstia ja sen tärkeyttä DAX-kielessä.

### <a name="context-quickquiz"></a>Testaa tietosi kontekstista
1. Mitkä ovat kaksi kontekstityyppiä?
2. Mikä on suodatinkonteksti?
3. Mikä on rivikonteksti?

Vastaukset ovat tämän artikkelin lopussa.

## <a name="summary"></a>Yhteenveto
Nyt kun sinulla on perustietämys DAX-kielen tärkeimmistä käsitteistä, voit aloittaa DAX-kaavojen luomisen mittareille. DAX:n opetteleminen voi olla hieman hankalaa, mutta saatavilla on monia resursseja. Kun olet lukenut tämän artikkelin ja kokeillut muutamia omia kaavoja, voit perehtyä muihin DAX-käsitteisiin ja kaavoihin, jotka voivat auttaa omien liiketoimintaongelmiesi ratkaisemisessa. Saatavilla on useita DAX-resursseja, joista tärkein on [Data Analysis Expressions (DAX) Reference](/dax/).

Koska DAX on ollut käytössä useita vuosia muissa Microsoftin BI-työkaluissa, kuten Power Pivotin ja Analysis Servicesin taulukkomuotoisissa malleissa, saatavilla on paljon erinomaisia tietolähteitä. Voit etsiä lisätietoja kirjoista, teknisistä raporteista ja blogeista, joita Microsoft ja BI-huippuasiantuntijat ovat kirjoittaneet. [TechNetin DAX Resource Center Wiki ](https://social.technet.microsoft.com/wiki/contents/articles/dax-resource-center.aspx) on myös hyvä paikka aloittaa.

### <a name="quickquiz-answers"></a>Testin vastaukset
Syntaksi:

1. Vahvistaa ja syöttää mittarin malliin.
2. Hakasulkeet [].

Funktiot:

1. Taulukko ja sarake.
2. Kyllä. Kaava voi sisältää jopa 64 sisäkkäistä funktiota.
3. [Tekstifunktiot](/dax/text-functions-dax).

Konteksti:

1. Rivikonteksti ja suodatinkonteksti.
2. Yksi tai useampi suodatin laskutoimituksessa, joka määrittää yksittäisen arvon.
3. Nykyinen rivi.
