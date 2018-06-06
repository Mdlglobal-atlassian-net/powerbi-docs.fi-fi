---
title: DAX-perusteet Power BI Desktopissa
description: DAX-perusteet Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 49f6e073d40ef00413ba38dd709780758cf1e448
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34291024"
---
# <a name="dax-basics-in-power-bi-desktop"></a>DAX-perusteet Power BI Desktopissa
Tämä artikkeli on tarkoitettu uusille Power BI Desktopin käyttäjille. Sen on tarkoitus antaa sinulle helppo ja nopea esittely siitä, miten voit käyttää Data Analysis Expression (DAX) -kaavaa ja ratkaista sillä useita peruslaskutoimituksia ja tietojen analysointiongelmia. Artikkeli sisältää käsitteellisiä tietoja, joukon harjoitustehtäviä ja muutamia tietovisoja, joilla voit testata, mitä olet oppinut. Kun olet käynyt tämän artikkelin läpi, sinulla pitäisi olla hyvä käsitys DAX:n tärkeimmistä peruskäsitteistä.

## <a name="what-is-dax"></a>Mikä DAX on?
DAX on kokoelma funktioita, operaattoreita ja vakioita, joita voidaan käyttää kaavoissa tai lausekkeissa yhden tai useamman arvon laskemiseen ja palauttamiseen. Yksinkertaisemmin ilmaistuna, DAX auttaa sinua luomaan uusia tietoja mallisi jo sisältämistä tiedoista.

## <a name="why-is-dax-so-important"></a>Miksi DAX on tärkeä?
Uuden Power BI Desktop -tiedoston luominen ja tietojen tuominen siihen on melko helppoa. Voit myös luoda raportteja, jotka näyttävät arvokasta tietoa käyttämättä ollenkaan DAX-kaavoja. Mutta entä jos sinun tarvitsee analysoida kaikkien tuoteluokkien kasvuprosenttia ja eri päivämääräväleiltä? Tai haluat laskea vuoden vuosittaisen kasvun verrattuna markkinoiden kehitykseen? DAX-kaavat mahdollistavat nämä ja tarjoavat lisäksi monia muita tärkeitä ominaisuuksia. Kun opettelet tehokkaiden DAX-kaavojen luonnin, se auttaa sinua hyödyntämään tietojasi mahdollisimman tehokkaasti. Kun saat tarvitsemasi tiedot, voit aloittaa todellisten liiketoimintaongelmien ratkaisemisen, jotka vaikuttavat yrityksen tulokseen. Tämä on Power BI:n voima, ja DAX auttaa sinua saavuttamaan sen.

## <a name="prerequisites"></a>Edellytykset
Kaavojen luominen Microsoft Excelissä saattaa olla sinulle jo tuttua. Tästä tietämyksestä on apua DAX:n ymmärtämisessä, mutta vaikka sinulla ei olisi kokemusta Excel-kaavoista, tässä kuvattujen käsitteiden avulla pääset heti alkuun DAX-kaavojen luomisessa ja oikeiden liiketoimintatiedon hallintaongelmien ratkaisemissa.

Painopisteenä on saada antaa käsitys DAX-kaavoista, joita käytetään laskutoimituksissa, ja erityisesti mittayksiköissä ja lasketuissa sarakkeissa. Power BI Desktopin, tietojen tuonnin ja kenttien lisäämisen raporttiin tulisi olla sinulle jo tuttuja, minkä lisäksi sinun tulisi tuntea peruskäsitteet [mittayksikkö](desktop-measures.md) ja [laskettu sarake](desktop-calculated-columns.md).

**Esimerkkityökirja**

Paras tapa oppia DAX on luoda joitakin peruskaavoja, käyttää sitä todellisten tietojen kanssa ja nähdä tulokset itse. Tässä esitetyissä esimerkeissä ja tehtävissä käytetään Contoso Sales Sample for Power BI Desktop Preview -tiedostoa. Tämä on sama mallitiedosto kuin se, jota käytetään [Opetusohjelma: Omien mittayksiköiden luominen Power BI Desktopissa](desktop-tutorial-create-measures.md) -artikkelissa. Voit ladata [mallitiedoston](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20for%20Power%20BI%20Designer.zip) täältä.

## <a name="lets-begin"></a>Aloitetaan!
Muodostamme ymmärryksemme DAX:ista kolmen peruskäsitteen ympärille: *syntaksi*, *funktiot* ja *konteksti*. DAX sisältää tietysti muitakin tärkeitä käsitteitä, mutta näiden kolmen käsitteen ymmärtäminen tarjoaa parhaan perustan DAX-taidoillesi.

### <a name="syntax"></a>Syntaksi
Ennen kuin luot omia kaavoja, tutustutaan DAX-kaavan syntaksiin. Syntaksi sisältää eri elementtejä, jotka muodostavat kaavan, tai yksinkertaisemmin ilmaistuna se kertoo, kuinka kaava on kirjoitettu. Otetaan esimerkiksi yksinkertainen mittayksikön DAX-kaava.

![](media/desktop-quickstart-learn-dax-basics/qsdax_1_syntax.png)

Tämä kaava sisältää seuraavat syntaksielementit:

**A.** Mittayksikön nimi **Total Sales**.

**B.** Yhtäläisyysmerkkioperaattori (**=**) ilmaisee kaavan alun. Kun laskutoimitus on tehty, se palauttaa tuloksen.

**C.** DAX-funktio **SUM** laskee yhteen kaikki **Sales[SalesAmount]**-sarakkeen luvut. Funktioista on lisätietoja jäljempänä.

**D.** Kaarisulkeet **()** ympäröivät lauseketta, joka sisältää yhden tai useampia argumentteja. Kaikki funktiot vaativat vähintään yhden argumentin. Argumentti välittää arvon funktiolle.

**E.** Viitattu taulukko **Sales**-taulukko.

**F.** Viitattu sarake **[SalesAmount]** Sales-taulukossa. Tämän argumentin avulla SUM-funktio tietää, mihin sarakkeeseen SUM eli summa koostetaan.

Kun yrität ymmärtää DAX-kaavaa, on usein hyödyllistä eritellä kukin elementti kielellä, jolla ajattelet ja jota puhut päivittäin. Voit esimerkiksi lukea tämän kaavan seuraavasti:

> *Mittayksikölle nimeltä Total Sales, laske (=) Sales-taulukon [SalesAmount ] -sarakkeen arvojen summa (SUM).*
> 
> 

Kun tämä mittayksikkö lisätään raporttiin, se laskee ja palauttaa arvot laskemalla yhteen myyntimäärät kaikkien muiden kenttien osalta, jotka otamme mukaan, esimerkiksi matkapuhelimet Suomessa.

Saatat ajatella: ”Eikö tämä mittayksikkö tee saman kuin jos vain lisäisin SalesAmount-kentän omaan raporttiini?” Kyllä vain. Mutta on olemassa hyvä syy, miksi kannattaa luoda oma mittayksikkö, joka laskee yhteen SalesAmount-kentän arvoja: voimme käyttää sitä argumenttina muissa kaavoissa. Tämä saattaa nyt vaikuttaa hieman sekavalta, mutta kun DAX-kaavataitosi kasvavat, tämän tietäminen tekee kaavoistasi ja mallistasi tehokkaampia. Tulet itse asiassa näkemään Total Sales -mittayksikön argumenttina muissa kaavoissa myöhemmin.

Käydäänpä seuraavaksi läpi muutamia muita tätä kaavaa koskevia seikkoja. Toimme esiin erityisesti funktion [SUM](https://msdn.microsoft.com/library/ee634387.aspx). Funktiot ovat ennalta laadittuja kaavoja, jotka helpottavat monimutkaisia laskutoimituksia ja käsittelytoimintoja mm. numeroiden, päivämäärien, ajan ja tekstin kanssa. Funktioista on lisätietoja jäljempänä.

Näet myös, että kaavassa sarakkeen [SalesAmount] edellä oli Sales-taulukko, johon sarake kuuluu. Tätä kutsutaan sarakkeen täydelliseksi nimeksi, koska se sisältää sarakkeen nimen, jonka edessä on taulukon nimi. Samassa taulukossa viitatut sarakkeet eivät vaadi taulukon nimen sisällyttämistä kaavaan. Tämä voi tehdä pitkistä kaavoista, jotka viittaavat moniin sarakkeisiin, lyhyempiä ja helppolukuisempia. On kuitenkin hyvä sisällyttää taulukon nimi mittayksikkökaavoihin, myös silloin kun ne ovat samassa taulukossa.

> [!NOTE]
> Jos taulukon nimessä on välilyöntejä, varattuja avainsanoja tai ei-sallittuja merkkejä, sinun on kirjoitettava taulukon nimi puolilainausmerkkien sisään. Taulukoiden nimet on kirjoitettava lainausmerkkien sisään myös, jos nimi sisältää aakkosnumeeriseen ANSI-merkkialueeseen kuulumattomia merkkejä, huolimatta siitä, tukevatko aluekohtaiset asetukset merkistöä vai ei.
> 
> 

On tärkeää, että kaavojen syntaksi on oikea. Jos syntaksi ei ole oikea, useimmissa tapauksissa ohjelma palauttaa syntaksivirheen. Muissa tapauksissa syntaksi voi olla oikea, mutta palautetut arvot eivät välttämättä ole sellaisia, joita odotit. Power BI Desktopin DAX-editorissa on ehdotustoiminto, jota käytetään syntaktisesti oikeiden kaavojen luomiseen auttamalla sinua valitsemaan oikeat elementit.

Luodaanpa yksinkertainen kaava. Tämä tehtävä auttaa sinua ymmärtämään paremmin kaavan syntaksia ja sitä, miten kaavarivin ehdotustoiminto voi auttaa sinua.

### <a name="task-create-a-measure-formula"></a>Tehtävä: mittayksikön kaavan luominen
Tämän tehtävän tekemistä varten sinun on avattava Contoso Sales Sample Power BI Desktop -tiedosto.
    
1.  Napsauta raporttinäkymän kenttäluettelossa hiiren kakkospainikkeella **Sales**-taulukkoa ja valitse sitten **Uusi mittayksikkö**.
    
2.  Korvaa kaavarivillä näkyvä **Measure** (Mittayksikkö) -sana kirjoittamalla uusi mittayksikön nimi **Previous Quarter Sales** (Edellisen neljänneksen myynti).
    
3.  Kirjoita yhtäläisyysmerkin jälkeen **SUM** ja sen perään vasen sulkumerkki.
    
    Sen sijaan, että kirjoittaisimme sarakkeen nimen suorittaaksemme yhteenlaskun välittömästi, kirjoitammekin toisen funktion, jolla *suodatamme* tiedot, jotka haluamme laskea yhteen.
    
4.  Kirjoita sulkeisiin funktio **CALCULATE** ja sen perään vasen sulkumerkki.
    
    CALCULATE-funktion avulla suodatat määrät, jotka haluamme laskea yhteen argumentilla, jonka välitämme CALCULATE-funktioon. Näitä kutsutaan sisäkkäisiksi funktioiksi. CALCULATE-funktiolla on vähintään kaksi argumenttia. Ensimmäinen on laskettava lauseke, ja toinen on suodatin.
   
5.  Kirjoita **CALCULATE**-funktion sulkeiden **()** väliin **Sales[SalesAmount]**. Tämä on CALCULATE-funktiomme ensimmäinen lausekeargumentti.
    
6.  Kirjoita pilkku (**,**), mikä määrittää ensimmäisen suodattimen, ja kirjoita sen jälkeen **PREVIOUSQUARTER** ja sen perään vasen sulkumerkki.
    
    Käytät PREVIOUSQUARTER-aikatietofunktiota suodattaaksesi SUM-tuloksemme edellisellä neljänneksellä.
    
7.  Kirjoita PREVIOUSQUARTER-funktion sulkeiden **()** väliin **Calendar[DateKey]**.
    
    PREVIOUSQUARTER-funktiolla on yksi argumentti, peräkkäisistä päivämääristä muodostuvan alueen sisältä sarake.
    
8.  Varmista, että PREVIOUSQUARTER-funktioon ja CALCULATE-funktioon välitettyjen argumenttien perässä on kaksi oikeaa sulkumerkkiä **))**.
    
   Kaavan pitäisi nyt näyttää tältä:
    
    **Previous Quarter Sales = CALCULATE(SUM(Sales[SalesAmount]), PREVIOUSQUARTER(Calendar[DateKey]))**
    
9. Vahvista kaava ja lisää se malliin napsauttamalla kaavarivin valintamerkkiä ![](media/desktop-quickstart-learn-dax-basics/qsdax_syntax_taskcheckmark.png) tai painamalla Enter-näppäintä.

Teit sen! Olet juuri luonut mittayksikön käyttämällä DAX-kaavaa, eikä mitään helppoa sitä paitsi. Tämä kaava laskee edellisen vuosineljänneksen kokonaismyynnin raportissa käytettyjen suodattimien mukaan. Jos esimerkiksi sijoitamme SalesAmount-mittayksikön ja uuden Previous Quarter Sales -mittayksikkömme kaavioon ja lisäämme sen jälkeen Year- ja QuarterOfYear-kentät osittajiksi, saisimme tulokseksi jotakin tämänkaltaista:

![](media/desktop-quickstart-learn-dax-basics/qsdax_3_chart.png)

Olet juuri tutustunut muutamiin tärkeisiin DAX-kaavoihin liittyviin näkökohtiin. Ensinnäkin tämä kaava sisälsi kaksi funktiota. Huomaa, että aikatietofunktio [PREVIOUSQUARTER](https://msdn.microsoft.com/library/ee634385.aspx) asetettiin sisäkkäin argumenttina, joka välitettiin suodatusfunktioon [CALCULATE](https://msdn.microsoft.com/library/ee634825.aspx). DAX-kaavat voivat sisältää jopa 64 sisäkkäistä funktiota. On epätodennäköistä, että mikään kaava koskaan sisältäisi näin paljon sisäkkäisiä funktioita. Itse asiassa tällaisen kaavan luominen ja sen virheenkorjaus olisi erittäin vaikeaa, eikä se todennäköisesti olisi myöskään kovin nopea.

Tässä kaavassa käytit myös suodattimia. Suodattimet rajaavat sen, mitä lasketaan. Tässä tapauksessa valitsit yhden suodattimen argumentiksi, joka on itse asiassa toisen funktion tulos. Suodattimista on lisätietoja jäljempänä.

Lopuksi käytit CALCULATE-funktiota. Tämä on yksi DAX-kaavan tehokkaimmista funktioista. Laatiessasi malleja ja luodessasi monimutkaisempia kaavoja tulet todennäköisesti käyttämään tätä funktiota monta kertaa. CALCULATE-funktio on tämän artikkelin aihealueen ulkopuolella, mutta DAX-osaamisesi kasvaessa kiinnitä tähän funktioon erityistä huomiota.

### <a name="syntax-quickquiz"></a>Testaa tietosi syntaksista
1. Mitä tämä kaavarivin painike tekee?
   
   > ![](media/desktop-quickstart-learn-dax-basics/qsdax_2_syntaxquiz.png)
   > 
   > 
2. Mitä DAX-kaavassa on aina sarakkeen nimen ympärillä?

Vastaukset ovat tämän artikkelin lopussa.

### <a name="functions"></a>Funktiot
Funktiot ovat ennalta määritettyjä kaavoja, jotka suorittavat laskutoimituksia käyttämällä erityisiä arvoja eli argumentteja tietyssä järjestyksessä tai tietyssä rakenteessa. Argumentit voivat olla muita funktioita, muita kaavoja, lausekkeita, sarakeviittauksia, numeroita, tekstiä, loogisia arvoja, kuten TOSI tai EPÄTOSI, tai vakioita.

DAX sisältää seuraavat funktioluokat: [päivämäärä- ja aikafunktiot](https://msdn.microsoft.com/library/ee634786.aspx), [aikatietofunktiot](https://msdn.microsoft.com/library/ee634763.aspx), [tietofunktiot](https://msdn.microsoft.com/library/ee634552.aspx), [loogiset](https://msdn.microsoft.com/library/ee634365.aspx), [matemaattiset](https://msdn.microsoft.com/library/ee634241.aspx) ja [tilastolliset funktiot](https://msdn.microsoft.com/library/ee634822.aspx), [tekstifunktiot](https://msdn.microsoft.com/library/ee634938.aspx), [pääkohde-/alikohdefunktiot](https://msdn.microsoft.com/library/mt150102.aspx) ja [muut](https://msdn.microsoft.com/library/mt150101.aspx) funktiot. Jos funktiot ovat sinulle tuttuja Excel-kaavoista, monet DAX-kielen funktiot vaikuttavat vastaavanlaisilta. DAX-funktiot ovat kuitenkin ainutlaatuisia seuraavin tavoin:

* DAX-funktio viittaa aina kokonaiseen sarakkeeseen tai taulukkoon. Jos haluat käyttää vain tiettyjä arvoja taulukosta tai sarakkeesta, voit lisätä kaavaan suodattimia.
* Jos laskutoimituksia on mukautettava rivikohtaisesti, voit tiettyjen DAX-funktioiden avulla suorittaa kontekstin mukaan vaihtelevia laskutoimituksia käyttämällä nykyistä rivin arvoa tai liittyvää arvoa eräänlaisena argumenttina. Kontekstista on lisätietoja jäljempänä.
* DAX sisältää monia funktioita, jotka palauttavat arvon sijasta taulukon. Taulukkoa ei näytetä, mutta sitä käytetään luomaan syötteitä muille funktioille. Voit esimerkiksi noutaa taulukon ja laskea sitten sen eri arvot tai laskea dynaamisia summia suodatetuissa taulukoissa tai sarakkeissa.
* DAX sisältää erilaisia aikatietojen funktioita. Näiden funktioiden avulla voit määrittää tai valita päivämäärävälejä ja suorittaa näihin perustuvia dynaamisia laskutoimituksia. Voit esimerkiksi verrata rinnakkaisten vuosineljännesten summia.
* Excelissä on erittäin suosittu funktio, PHAKU. DAX-funktiot eivät käsitä solua tai solualuetta viitteeksi, kuten PHAKU tekee Excelissä. DAX-funktiot ottavat viitteeksi sarakkeen tai taulukon. Pidä mielessä, että Power BI Desktopissa työskentelet relaatiotietomallin kanssa. Arvojen hakeminen toisesta taulukosta on todellisuudessa melko helppoa, ja useimmissa tapauksissa sinun ei tarvitse luoda kaavaa lainkaan.
  
  Kuten huomaat, DAX-funktioiden avulla voit luoda hyvin tehokkaita kaavoja. Ja olemme käsitelleet vasta funktioiden perusteita. DAX-taitojesi kasvaessa opit luomaan kaavoja, joissa käytät useita eri funktioita. Yksi parhaimmista kaikkia DAX-funktioita koskevia tarkempia tietoja sisältävistä resursseista on [DAX Function Reference](https://msdn.microsoft.com/library/ee634396.aspx) -artikkeli.

### <a name="functions-quickquiz"></a>Testaa tietosi funktioista
1. Mihin funktio aina viittaa?
2. Voiko kaava sisältää useamman kuin yhden funktion?
3. Mitä funktioluokkaa käyttäisit kahden tekstimerkkijonon liittämiseen yhdeksi merkkijonoksi?

Vastaukset ovat tämän artikkelin lopussa.

### <a name="context"></a>Konteksti
Konteksti on yksi niistä DAX-käsitteistä, joiden ymmärtäminen on hyvin tärkeää. DAX-kielessä on kahdentyyppisiä konteksteja: rivikonteksti ja suodatinkonteksti. Tarkastelemme ensin rivikontekstia.

**Rivikonteksti**

Rivikonteksti ymmärretään tavallisesti nykyiseksi riviksi. Sitä käytetään aina, kun kaavassa on funktio, joka käyttää suodattimia taulukon yksittäisen rivin tunnistamiseen. Funktio käyttää luontaisesti rivikontekstia jokaiseen sen taulukon riviin, jota se suodattaa. Tämäntyyppistä rivikontekstia sovelletaan useimmiten mittayksiköihin.

**Suodatinkonteksti**

Suodatinkonteksti on hieman vaikeampi ymmärtää kuin rivikonteksti. Suodatinkontekstin voi helpoiten ymmärtää seuraavasti: yksi tai useampi suodatin, jota käytetään tuloksen tai arvon määrittävässä laskutoimituksessa.

Suodatinkontekstia ei käytetä rivikontekstin sijasta, vaan sitä käytetään rivikontekstin lisäksi. Jos esimerkiksi haluat rajata laskutoimitukseen sisällytettäviä arvoja tarkemmin, voit käyttää suodatinkontekstia, joka määrittää paitsi rivikontekstin myös vain tietyn arvon (suodattimen) kyseisessä rivikontekstissa.

Suodatinkontekstia näkee helpoimmin raporteissa. Kun esimerkiksi lisäät visualisointiin TotalCost-arvon ja lisäät sen jälkeen vuoden ja alueen, määrität suodatinkontekstin, joka valitsee tietojen alijoukon antamasi tietyn vuoden ja alueen perusteella.

Miksi suodatinkonteksti on niin tärkeä DAX-kielelle? Suodatinkontekstia on helpointa käyttää lisäämällä visualisointiin kenttiä, mutta suodatinkontekstia voidaan myös käyttää DAX-kaavassa määrittämällä suodatin, joka käyttää funktioita kuten ALL, RELATED, FILTER ja CALCULATE, käyttämällä suhteita ja käyttämällä muita mittayksiköitä ja sarakkeita. Tarkastellaanpa esimerkiksi seuraavaa kaavaa StoreSales-nimisessä mittayksikössä:

![](media/desktop-quickstart-learn-dax-basics/qsdax_4_context.png)

Tämä kaava on helpompi ymmärtää, kun se eritellään samalla tavalla kuin muut kaavat edellä.

Tämä kaava sisältää seuraavat syntaksielementit:

**A.** Mittayksikön nimi **Store Sales**.

**B.** Yhtäläisyysmerkkioperaattori (**=**) ilmaisee kaavan alun.

**C.** **CALCULATE**-laskee argumenttina lausekkeen kontekstissa, jota on muutettu määritetyillä suodattimilla.

**D.** Kaarisulkeet **()** ympäröivät lauseketta, joka sisältää yhden tai useampia argumentteja.

**E.** Mittayksikkö **[Total Sales]** samassa taulukossa lausekkeena. Total Sales -mittayksikön kaava on: =SUM(Sales[SalesAmount]).

**F.** Pilkku (**,**) erottaa ensimmäisen lausekeargumentin suodatinargumentista.

**G.** Täydellinen viitattu sarake **Channel [ChannelName]**. Tämä on rivikontekstimme. Jokainen rivi tässä sarakkeessa määrittää kanavan: Store, Online, jne.

**H.** Tietty arvo, **Store**, suodattimena. Tämä on suodatinkontekstimme.

Tämä kaava varmistaa, että vain Total Sales -mittayksikön suodattimena määrittämät myyntiarvot lasketaan vain Channel[ChannelName]-sarakkeen sellaisille riveille, joissa on suodattimena ”Store”-arvo.

Kuten voit kuvitella, mahdollisuus määrittää suodatinkonteksteja kaavassa tarjoaa valtaisaa ja tehokasta käyttöpotentiaalia. Mahdollisuus viitata vain tiettyyn arvoon liittyvässä taulukossa on vain yksi esimerkki siitä. Älä huolestu, vaikka et heti ymmärtäisikään kontekstia täysin. Kun luot omia kaavojasi, opit paremmin ymmärtämään kontekstia ja sen tärkeyttä DAX-kielessä.

### <a name="context-quickquiz"></a>Testaa tietosi kontekstista
1. Mitkä ovat kaksi kontekstityyppiä?
2. Mikä on suodatinkonteksti?
3. Mikä on rivikonteksti?

Vastaukset ovat tämän artikkelin lopussa.

## <a name="summary"></a>Yhteenveto
Nyt kun sinulla on perustietämys DAX-kielen tärkeimmistä käsitteistä, voit aloittaa DAX-kaavojen luomisen mittayksiköille. DAX:n opetteleminen voi olla hieman hankalaa, mutta saatavilla on monia resursseja. Kun olet lukenut tämän artikkelin ja kokeillut muutamia omia kaavoja, voit perehtyä muihin DAX-käsitteisiin ja kaavoihin, jotka voivat auttaa omien liiketoimintaongelmiesi ratkaisemisessa. Saatavilla on useita DAX-resursseja, joista tärkein on [Data Analysis Expressions (DAX) Reference](https://msdn.microsoft.com/library/gg413422.aspx).

DAX on ollut käytössä useita vuosia muissa Microsoftin BI-työkaluissa, kuten Power Pivotin ja Analysis Servicesin taulukkomuotoisissa malleissa, joten saatavilla on paljon erinomaisia tietolähteitä. Voit etsiä lisätietoja kirjoista, teknisistä raporteista ja blogeista, joita Microsoft ja BI-huippuasiantuntijat ovat kirjoittaneet. [TechNetin DAX Resource Center Wiki ](http://social.technet.microsoft.com/wiki/contents/articles/dax-resource-center.aspx) on myös hyvä paikka aloittaa.

### <a name="quickquiz-answers"></a>Testin vastaukset
Syntaksi:

1. Vahvistaa ja syöttää mittayksikön malliin.
2. Hakasulkeet [].

Funktiot:

1. Taulukko ja sarake.
2. Kyllä. Kaava voi sisältää jopa 64 sisäkkäistä funktiota.
3. [Tekstifunktiot](https://msdn.microsoft.com/library/ee634938.aspx).

Konteksti:

1. Rivikonteksti ja suodatinkonteksti.
2. Yksi tai useampi suodatin laskutoimituksessa, joka määrittää yksittäisen arvon.
3. Nykyinen rivi.

