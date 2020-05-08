---
title: Mallien suhteet Power BI Desktopissa
description: Johdatus mallien yhteyksien teoriaan Power BI Desktopissa
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/15/2019
ms.author: v-pemyer
ms.openlocfilehash: 991f8b47337ba563ecfd223d69d687269a44ed78
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79041604"
---
# <a name="model-relationships-in-power-bi-desktop"></a>Mallien suhteet Power BI Desktopissa

Tämä artikkeli on tarkoitettu tuotujen tietojen mallintajille, jotka käyttävät Power BI Desktopia. Se on tärkeä mallisuunnittelun aihealue, jolla on oleellinen rooli toimitettaessa intuitiivisia, tarkkoja ja optimaalisia malleja.

Kun haluat perehtyä optimaalisen mallin suunnitteluun syvällisemmin ja ottaa huomioon taulukoiden roolin ja yhteydet, katso artikkelia [Tutustu tähtirakenteeseen ja sen merkitykseen Power BI:ssä](guidance/star-schema.md).

## <a name="relationship-purpose"></a>Yhteyden tarkoitus

Yksinkertaisesti ilmaisten Power BI -yhteydet levittävät mallitaulukoiden sarakkeissa käytettyjä suodattimia toisiin mallitaulukoihin. Suodattimet leviävät niin kauan kuin niillä on yhteyspolku seurattavanaan, mikä voi merkitä, että ne leviävät moniin taulukkoihin.

Yhteyspolut ovat deterministisiä, mikä tarkoittaa, että suodattimet levitetään aina samaa tietä ja ilman satunnaisia vaihteluja. Yhteydet voidaan kuitenkin poistaa käytöstä tai niiden suodatinkontekstia voidaan muuntaa tiettyjä DAX-funktioita käyttävillä mallilaskelmilla. Katso lisätietoja tämän artikkelin myöhemmästä aiheesta [Asiaan liittyvät DAX-funktiot](#relevant-dax-functions).

> [!IMPORTANT]
> On tärkeää ymmärtää, että malliyhteyksiin ei liity tietojen eheyden pakottamista. Katso lisätietoja tämän artikkelin myöhemmästä aiheesta [Yhteyden arviointi](#relationship-evaluation). Tämä aihe selittää, miten malliyhteydet toimivat, kun tiedoissasi ilmenee eheysongelmia.

Tarkastellaan animoidun esimerkin avulla, kuinka yhteydet levittävät suodattimia.

![Animoitu esimerkki siitä, kuinka yhteys levittää suodatinta](media/desktop-relationships-understand/animation-filter-propagation.gif)

Tässä esimerkissä malliin kuuluu neljä taulukkoa: **Luokka**, **Tuote**, **Vuosi** ja **Myynti**. **Luokka**-taulukko liittyy **Tuote**-taulukkoon ja **Tuote**-taulukko liittyy **Myynti**-taulukkoon. **Vuosi**-taulukko liittyy myös **Myynti**-taulukkoon. Kaikki yhteydet ovat yksi moneen -tyyppisiä (yksityiskohdat kuvaillaan myöhemmin tässä artikkelissa).

Kysely, mahdollisesti Power BI -kortin visualisoinnin synnyttämä, pyytää myynnin kokonaismäärää myyntitilauksille, jotka koskevat yksittäistä luokkaa, **Cat-A**, ja yhtä vuotta, **CY2018**. Siksi näet, että suodattimia käytetään taulukoissa **Luokka** ja **Vuosi**. Suodatin taulukossa **Luokka** leviää taulukkoon **Tuote** ja eristää kaksi tuotetta, jotka on määritetty luokkaan **Cat-A**. Sitten taulukon **Tuote** suodattimet leviävät taulukkoon **Myynti** ja eristävät vain ne kaksi riviä, jotka koskevat näitä tuotteita. Nämä kaksi myyntiriviä edustavat luokkaan **Cat-A** määritettyjen tuotteiden myyntiä. Niiden määrä on yhteenlaskettuna 14 yksikköä. Samanaikaisesti taulukon **Vuosi** suodatin leviää suodattamaan edelleen taulukkoa **Myynti**, jolloin jäljelle jää vain se ainoa myyntirivi, joka koskee luokkaan **Cat-A** määriteltyjä, vuonna **CY2018** tilattuja tuotteita. Kyselyn palauttama määräarvo on 11 yksikköä. Huomaa, että kun taulukkoon käytetään useita eri suodattimia (kuten tässä esimerkissä taulukkoon **Myynti**),kyseessä on aina AND-operaatio, joka edellyttää kaikkien ehtojen olevan tosia.

### <a name="disconnected-tables"></a>Irralliset taulukot

On epätavallista, että mallitaulukko ei liity toiseen mallitaulukkoon. Pätevässä mallirakenteessa tällaista taulukkoa voidaan luonnehtia _irralliseksi taulukoksi_. Irrallista taulukkoa ei ole tarkoitettu levittämään suodattimia muihin mallisuodattimiin. Sen sijaan sen tarkoitus on hyväksyä “käyttäjän syöte” (mahdollisesti varustettuna osittajavisualisoinnilla), jolloin mallilaskelmat voivat hyödyntää syötearvoa merkityksellisesti. Harkitse esimerkiksi irrallista taulukkoa, joka sisältää joukon valuutanvaihtosuhteiden arvoja. Jos suodattimen on määrä suodattaa yksittäisen suhdearvon mukaan, arvoa voidaan käyttää mittauslausekkeessa myyntiarvojen muuntamiseen.

Power BI Desktopin entä jos -parametri on ominaisuus, joka luo irrallisen taulukon. Katso lisätietoja artikkelista [Entä jos -parametrien luominen ja käyttäminen muuttujien visualisointiin Power BI Desktopissa](desktop-what-if.md).

## <a name="relationship-properties"></a>Yhteyden ominaisuudet

Malliyhteys liittää yhden taulukon yhden sarakkeen toisen taulukon yhteen sarakkeeseen. (On yksi erityinen tapaus, jossa tämä vaatimus ei ole tosi, ja se koskee vain monisarakkeisia yhteyksiä DirectQuery-malleissa. Lisätietoja on artikkelissa DAX-funktiosta [COMBINEVALUES](/dax/combinevalues-function-dax).)

> [!NOTE]
> Saraketta ei ole mahdollista liittää toiseen sarakkeeseen _samassa taulukossa_. Tämä sekoitetaan usein mahdollisuuteen määrittää relaatiotietokannan viiteavainrajoite, joka on itseensä viittaava taulukon osalta. Tätä relaatiotietokantakonseptia voidaan käyttää pää-alielementtisuhteiden tallentamiseen (esimerkiksi jokainen työntekijätietue on suhteessa “raportoi henkilölle” -työntekijään). Tämäntyyppisiin yhteyksiin perustuvan mallihierarkian luominen ei ole mahdollista luomalla malliyhteyksiä. Jos haluat saavuttaa tämän, katso artikkelia [Pää-alielementtifunktiot](/dax/parent-and-child-functions-dax).

### <a name="cardinality"></a>Kardinaliteetti

Kullakin määritettävällä malliyhteydellä on oltava kardinaliteettityyppi. Kardinaliteettityyppivalintoja on neljä ja ne edustavat “kohteesta” ja “kohteeseen” liittyvien sarakkeiden tieto-ominaisuuksia. “Yksi”-puoli tarkoittaa, että sarake sisältää yksilöllisiä arvoja, “kaksi”-puoli tarkoittaa, että sarake sallii yhdelle arvolle kaksoiskappaleita.

> [!NOTE]
> Jos tietojen päivittämistoiminto yrittää ladata kaksoiskappalearvoja “yksi”-puolen sarakkeeseen, koko tietojen päivittämisyritys epäonnistuu.

Neljä vaihtoehtoa pikamerkintätapoineen on kuvattu seuraavassa luettelossa:

- Yksi moneen (1:\*)
- Monta yhteen (\*:1)
- Yksi yhteen (1:1)
- Monta moneen (\*:\*)

Kun luot yhteyden Power BI Desktopissa, suunnittelutoiminta havaitsee sen automaattisesti ja määrittää kardinaliteettityypin. Suunnittelutoiminto tekee mallista kyselyn ja selvittää, mitkä sarakkeet sisältävät yksilöllisiä arvoja. Tuontimalleissa se käyttää sisäisiä tallennustilastoja; DirectQuery-malleissa se lähettää profilointikyselyjä tietolähteelle. Joskus se voi kuitenkin erehtyä. Tämä tapahtuu siksi, että tietoja ei ole vielä ladattu taulukoihin, tai siksi, että sarakkeet, joiden odotat sisältävän kaksoiskappalearvoja, sisältävät vain ainutlaatuisia arvoja. Kummassakin tapauksessa voit päivittää kardinaliteettityypin, jos kaikki “yksi”-puolen sarakkeet sisältävät ainutlaatuisia arvoja (tai tietorivejä ei vielä ole ladattu taulukkoon).

**Yksi moneen**- ja **Monta yhteen** -kardinaliteettivalinnat ovat oleelliselta osin sama asia, ja ne ovat myös kaikkein tavallisimmat kardinaliteettityypit.

Kun määrität Yksi moneen- tai Monta yhteen -yhteyden, valitset sen, joka vastaa sarakkeiden yhdistämisjärjestystäsi. Pohdi, miten määrittäisit yhteyden **Tuote**-taulukosta **Myynti**-taulukkoon käyttämällä kustakin taulukosta löytyvää **ProductID**-saraketta. Kardinaliteettityypiksi tulee _Yksi moneen_, koska sarake **ProductID** **Tuote**-taulukossa sisältää yksilöllisiä arvoja. Jos olet yhdistänyt taulukot päinvastaiseen suuntaan, **Myynnistä** **Tuotteeseen**, kardinaliteettityypiksi tulee _Monta yhteen_.

**Yksi yhteen** -yhteys tarkoittaa, että molemmat sarakkeet sisältävät yksilöllisiä arvoja. Tämä kardinaliteettityyppi ei ole yleinen, eikä se luultavasti ole optimaalinen mallin rakenne, koska tallennetaan tarpeetonta tietoa. Lisätietoja tämän kardinaliteettityypin käyttämisestä on artikkelissa [Yksi-yhteen-suhteen ohjeet](guidance/relationships-one-to-one.md).

**Monta moneen** -yhteys tarkoittaa, että molemmat sarakkeet voivat sisältää saman arvon useampia kertoja. Tätä kardinaliteettityyppiä käytetään harvoin. Siitä on yleensä hyötyä silloin, kun suunnitellaan monimutkaisia mallivaatimuksia. Ohjeita tämän kardinaliteettityypin käyttämisestä on kohdassa [Monta-moneen-suhteen ohjeet](guidance/relationships-many-to-many.md).

> [!NOTE]
> Monta moneen -kardinaliteettityyppiä ei nykyisellään tueta malleilla, joita kehitetään Power BI -raporttipalvelinta varten.

> [!TIP]
> Power BI Desktop -mallinäkymässä voit tulkita yhteyden kardinaliteettityypin katsomalla tunnuslukuja (1 tai \*) kummallakin yhteysviivan puolella. Jos haluat selvittää, mitkä sarakkeet liittyvät toisiinsa, sinun on valittava yhteysviiva – tai vietävä kohdistin yhteysviivan kohdalle – jotta voit korostaa sarakkeet.

### <a name="cross-filter-direction"></a>Ristisuodatussuunta

Kullakin määritettävällä malliyhteydellä on oltava ristisuodatussuunta. Valintasi määrittää suodattimien leviämissuunnan tai -suunnat. Mahdolliset ristisuodatusvalinnat ovat riippuvaisia kardinaliteettityypistä.

| Kardinaliteettityyppi | Ristisuodatusvalinnat |
| --- | --- |
| Yksi moneen (tai Monta yhteen) | Yksittäinen<br>Molemmat |
| Yksi yhteen | Molemmat |
| Monta moneen | Yksittäinen (taulukosta 1 taulukkoon 2)<br>Yksittäinen (taulukosta 2 taulukkoon 1)<br>Molemmat |

_Yksittäinen_ ristisuodatussuunta tarkoittaa “yhteen suuntaan” ja _Molemmat_ tarkoittaa “molempiin suuntiin”. Molempiin suuntiin suodattavaa yhteyttä sanotaan tavallisesti _kaksisuuntaiseksi_.

Yksi moneen -yhteyksissä ristisuodatussuunta menee aina “yksi”-puolelta, ja valinnaisesti “monta”-puolelta (kaksisuuntainen). Yksi yhteen -yhteyksissä ristisuodatussuunta lähtee aina molemmista taulukoista. Lopuksi: Monta moneen -yhteyksissä ristisuodatussuunta voi lähteä jommastakummasta taulukosta, tai molemmista taulukoista. Huomaa, että kun kardinaliteettityyppi sisältää “yksi”-puolen, suodattimet leviävät aina siltä puolelta.

Kun ristisuodatussuunnaksi on määritetty **Molemmat**, käytettävissä on lisäominaisuus. Se voi käyttää kaksisuuntaista suodatusta, kun rivitason suojauksen (RLS) sääntöjä käytetään. Lisätietoja RLS:stä saat artikkelista [Rivitason suojaus (RLS) Power BI Desktopissa](desktop-rls.md).

Yhteyden ristisuodatussuunnan muokkaaminen, kuten suodatuksen leviämisen poistaminen käytöstä, voidaan tehdä myös mallilaskelman avulla. Se tehdään käyttämällä DAX-funktiota [CROSSFILTER](/dax/crossfilter-function).

Kaksisuuntaiset yhteydet voivat vaikuttaa haitallisesti suorituskykyyn. Lisäksi kaksisuuntaisen yhteyden määrittäminen voi synnyttää moniselitteisiä leviämispolkuja. Tässä tapauksessa Power BI Desktop voi epäonnistua yhteyden muuttamisessa ja antaa sinulle virheilmoituksen. Joskus Power BI Desktop voi kuitenkin sallia moniselitteisen yhteyspolun määrittämisen taulukoiden välille. Käsittelyjärjestyssääntöjä, jotka vaikuttavat moniselitteisyyden tunnistamiseen ja polun määrittämiseen, kuvataan myöhemmin tämän artikkelin aiheessa [Käsittelyjärjestyssäännöt](#precedence-rules).

Suosittelemme kaksisuuntaisen suodatuksen käyttöä vain kun se on välttämätöntä. Lisätietoja on artikkelissa [Kaksisuuntaisen suhteen ohjeet](guidance/relationships-bidirectional-filtering.md).

> [!TIP]
> Power BI Desktopin mallinäkymässä voit selvittää yhteyden ristisuodatussuunnan panemalla merkille yhteysviivan nuolenpääkuviot. Yksinkertainen nuolenpääkuvio edustaa yksisuuntaista suodatinta nuolenpään suunnassa, kaksinkertainen nuolenpääkuvio edustaa kaksisuuntaista yhteyttä.

### <a name="make-this-relationship-active"></a>Suhteen muuttaminen aktiiviseksi

Kahden mallitaulukon välillä voi olla vain yksi aktiivinen suodatuksen levityspolku. On kuitenkin mahdollista ottaa käyttöön ylimääräisiä yhteyspolkuja, vaikka nämä yhteydet on määritettävä _passiivisiksi_. Passiivisia yhteyksiä voidaan muuttaa aktiivisiksi vain mallilaskelman arvioinnin aikana. Se tehdään käyttämällä DAX-funktiota [USERELATIONSHIP](/dax/userelationship-function-dax).

Lisätietoja on artikkelissa [Aktiivisten ja passiivisten suhteiden ohjeet](guidance/relationships-active-inactive.md).

> [!TIP]
> Power BI Desktop -mallinäkymässä voit selvittää, onko yhteys aktiivinen vai passiivinen. Aktiivista yhteyttä edustaa yhtenäinen viiva; passiivinen yhteys esitetään katkoviivana.

### <a name="assume-referential-integrity"></a>Oleta viite-eheys

Ominaisuus _Oleta viite-eheys_ on käytettävissä vain yksi moneen- ja yksi yhteen -yhteyksissä kahden DirectQuery-tallennustapataulukon välillä, jotka perustuvat samaan tietolähteeseen. Kun ominaisuus on käytössä, tietolähteelle lähetettävät alkuperäiskyselyt liittävät molemmat taulukot yhteen käyttämällä SISÄLIITOSTA ULKOLIITOKSEN sijaan. Yleensä tämän ominaisuuden käyttöönotto parantaa kyselyn tehokkuutta, mutta tämä riippuu kuitenkin tietolähteen ominaisuuksista.

Ota tämä ominaisuus aina käyttöön, kun taulukoiden välillä on tietokannan viiteavaimen rajoite. Silloin, kun viiteavaimen rajoitetta ei ole, voit yhä ottaa ominaisuuden käyttöön, jos olet varma tietojen eheydestä.

> [!IMPORTANT]
> Jos tietojen eheys vaarantuu, sisäliitos poistaa yhteensopimattomat rivit taulukoiden väliltä. Pohdi esimerkiksi mallitaulukkoa **Myynti**, jonka **ProductID**-sarakkeeseen sisältyy siihen liittyvästä **Tuote**-taulukosta puuttuva arvo. Suodattimien levittäminen **Tuote**-taulukosta **Myynti**-taulukkoon poistaa tuntemattomien tuotteiden myyntirivit. Tämä johtaa siihen, että myyntitulokset näkyvät todellista pienempinä.
>
> Lisätietoja on artikkelissa [Oleta viite-eheys -asetus Power BI Desktopissa](desktop-assume-referential-integrity.md).

## <a name="relevant-dax-functions"></a>Asiaan liittyvät DAX-funktiot

On olemassa useita DAX-funktioita, jotka liittyvät malliyhteyksiin. Kutakin funktioita kuvataan lyhyesti seuraavassa luettelossa:

- [RELATED](/dax/related-function-dax): Hakee arvon “yksi”-puolelta.
- [RELATEDTABLE](/dax/relatedtable-function-dax): Hakee taulukon rivit “monta”-puolelta.
- [USERELATIONSHIP](/dax/userelationship-function-dax): Pakottaa käyttämään tiettyä passiivista malliyhteyttä.
- [CROSSFILTER](/dax/crossfilter-function): Muokkaa yhteyden ristisuodatussuuntaa (yksi tai molemmat), tai poistaa suodattimien levittämisen toiminnasta (ei mitään).
- [COMBINEVALUES](/dax/combinevalues-function-dax): Yhdistää kaksi tai useampia tekstimerkkijonoa yhdeksi tekstimerkkijonoksi. Tämän funktion tarkoituksena on tukea monisarakkeisia yhteyksiä DirectQuery-malleissa.
- [TREATAS](/dax/treatas-function): Soveltaa taulukkolausekkeen tulosta suodattimena liittymättömän taulukon sarakkeisiin.
- [Pää- ja alielementtifunktiot](/dax/parent-and-child-functions-dax): Toisiinsa liittyvien funktioiden perhe, jota voidaan käyttää laskettujen sarakkeiden luomiseen pää-alielementtihierarkian naturalisoimiseksi. Näitä sarakkeita voidaan sitten käyttää kiinteän tason hierarkian luomiseen.

## <a name="relationship-evaluation"></a>Yhteyden arviointi

Arviointiperspektiivistä käsin malliyhteydet luokitellaan joko _vahvoiksi_ tai _heikoiksi_. Se ei ole sellainen yhteyden ominaisuus, joka olisi määritettävissä. Se itse asiassa päätellään kahden yhteen kuuluvan taulukon kardinaliteettityypistä ja tietolähteestä. On tärkeää ymmärtää arviointityyppi, sillä tietojen eheyden vaarantuminen voi vaikuttaa suorituskykyyn. Tämä aihe käsittelee näitä vaikutuksia ja seurauksia tietojen eheydelle.

Ensinnäkin yhteyksien arviointien ymmärtämiseen tarvitaan jonkin verran mallintamisteoriaa.

Tuonti- tai DirectQuery-malli hakee kaiken tietonsa joko Vertipaq-välimuistista tai lähdetietokannasta. Molemmissa tapauksissa Power BI kykenee määrittämään, että yhteydellä on “yksi”-puoli.

Voidaan kuitenkin luoda yhdistelmämalli, joka koostuu erilaisia tallennustapoja käyttävistä taulukoista (tuonti, DirectQuery tai kaksoistaulukko), tai taulukoista jotka käyttävät useita DirectQuery-lähteitä. Jokaista lähdettä, myös tuontitiedon Vertipaq-välimuistia, pidetään _tietosaarena_. Malliyhteydet voidaan sitten luokitella _saarensisäisiksi_ tai _saartenvälisiksi_. Saarensisäinen yhteys yhdistää kaksi taulukkoa saman tietosaaren sisällä, kun taas saartenvälinen yhteys yhdistää eri tietosaarten taulukoita. Ota huomioon, että tuonti- ja DirectQuery-malleissa yhteydet ovat aina saarensisäisiä.

Tarkastellaan esimerkkiä yhdistelmämallista.

![Esimerkki yhdistelmämallista, joka koostuu kahdesta saaresta](media/desktop-relationships-understand/data-island-example.png)

Tässä esimerkissä yhdistelmämalli koostuu kahdesta saaresta: Vertipaq-tietosaaresta ja DirectQuery-lähdettä käyttävästä tietosaaresta. Vertipaq-tietosaari sisältää kolme taulukkoa, ja DirectQuery-lähteellinen saari sisältää kaksi taulukkoa. Olemassa on yksi saartenvälinen yhteys, joka yhdistää yhden taulukon Vertipaq-tietosaarelta DirectQuery-lähteiseen tietosaareen kuuluvaan taulukkoon.

### <a name="strong-relationships"></a>Vahvat yhteydet

Malliyhteys on _vahva_, kun kyselymoduuli voi määrittää yhteyden “yksi”-puolen. Sillä on vahvistus, että “yksi”-puolen sarake sisältää yksilöllisiä arvoja. Kaikki saarensisäiset yhdestä moneen -yhteydet ovat vahvoja yhteyksiä.

Seuraavassa esimerkissä on kaksi vahvaa yhteyttä, molemmat merkitty **S**:llä. Yhteyksiin kuuluu Vertipaq-saaren sisäinen yhdestä moneen -suhde ja DirectQuery-lähteen sisäinen yhdestä moneen -suhde.

![Esimerkki yhdistelmämallista, joka koostuu kahdesta saaresta, vahvat yhteydet merkittyinä](media/desktop-relationships-understand/data-island-example-strong.png)

Tuontimalleilla, joissa kaikki tiedot on tallennettu Vertipaq-välimuistiin, jokaiselle vahvalle yhteydelle luodaan tietorakenne aina kun tiedot päivitetään. Tietorakenteet koostuvat kaikkien sarakkeidenvälisten arvojen indeksoiduista linkityksistä, ja niiden tarkoitus on nopeuttaa taulukoiden liittämistä kyselyn aikana.

Kyselyn aikana vahvat yhteydet mahdollistavat _taulukon laajentamisen_. Taulukon laajentaminen johtaa virtuaalitaulukon luomiseen, kun säilytetään perustaulukon alkuperäiset sarakkeet ja laajennetaan ne liittyviin taulukoihin. Tuontitaulukoilla tämä tehdään kyselymoduulissa; DirectQuery-taulukoilla se tehdään lähdetietokantaan lähetetyssä alkuperäisessä kyselyssä (sillä ehdolla, että **Oleta viite-eheys**-ominaisuus ei ole käytössä). Kyselymoduuli toimii sitten laajennetun taulukon yhteydessä käyttäen suodattimia ja ryhmitellen laajennetun taulukon sarakkeiden arvojen mukaan.

> [!NOTE]
> Passiiviset yhteydet laajennetaan silloinkin, kun ei ole laskelmaa käyttämässä yhteyttä. Kaksisuuntaisilla yhteyksillä ei ole vaikutusta taulukon laajentamiseen.

Yksi moneen -yhteyksillä taululukon laajentaminen tapahtuu “moneen”-puolelta “yksi”-puolelle käyttämällä VASEMMANPUOLEISEN ULKOLIITOKSEN semantiikkaa. Kun “monta”-puolen arvolle ei löydy vastaavaa “yksi”-puolen arvoa, “yksi”-puolen taulukkoon lisätään tyhjä virtuaalirivi.

Taulukon laajentaminen tapahtuu myös saarensisäisissä yksi yhteen -yhteyksissä, mutta tällöin käytetään TÄYDEN ULKOLIITOKSEN semantiikkaa. Se varmistaa, että molemmille puolille lisätään tarpeen mukaan tyhjiä virtuaalirivejä.

Tyhjät näennäisrivit ovat käytännössä _tuntemattomia jäseniä_. Tuntemattomat jäsenet edustavat viite-eheyden rikkomuksia, joissa “monta”-puolen arvolla ei ole vastaavaa “yksi”-puolen arvoa. Ihannetapauksessa näitä tyhjiä kohtia ei pitäisi olla olemassa, ja ne voidaan poistaa puhdistamalla tai korjaamalla lähdetieto.

Tarkastellaan taulukon laajennuksen toimintaa animoidun esimerkin avulla.

![Animoitu esimerkki taulukon laajennuksesta](media/desktop-relationships-understand/animation-expanded-table.gif)

Tässä esimerkissä malliin kuuluu kolme taulukkoa: **Luokka**, **Tuote** ja **Myynti**. **Luokka**-taulukko liittyy **Tuote**-taulukkoon yksi moneen -yhteydellä, **Tuote**-taulukko liittyy **Myynti**-taulukkoon yksi moneen -yhteydellä. **Luokka**-taulukossa on kaksi riviä, **Tuote**-taulukko sisältää kolme riviä ja **Myynti**-taulukossa on viisi riviä. Ne ovat yhteensopivia arvoja kaikkien yhteyksien molemmilta puolilta, mikä tarkoittaa, että viite-eheyttä ei rikota. Esiin tulee kyselyn aikana laajennettu taulukko. Taulukon sarakkeet tulevat kaikista kolmesta taulukosta. Se on käytännössä denormalisoitu perspektiivi kolmen taulukon sisältämään tietoon. Uusi rivi lisätään **Myynti**-taulukkoon, ja sillä on tuotantotunnusarvo (9), jolla ei ole vastaavaa arvoa taulukossa **Tuote**. Se on viite-eheysrikkomus. Laajennetussa taulukossa uudella rivillä on arvo (Tyhjä) taulukoiden **Luokka** ja **Tuote** sarakkeissa.

### <a name="weak-relationships"></a>Heikot yhteydet

Malliyhteys on _heikko_, kun taattua “yksi”-puolta ei ole. Tähän voi olla kaksi syytä:

- Yhteys käyttää monta moneen -kardinaliteettityyppiä (vaikka yksi tai molemmat sarakkeet sisältävät yksilöllisiä arvoja)
- Yhteys on saartenvälinen (mikä on mahdollista vain yhdistelmämalleissa)

Seuraavassa esimerkissä on kaksi heikkoa yhteyttä, molemmat merkitty **W**:llä. Yhteyksiin kuuluu monta moneen -yhteys, joka on Vertipaq-saaren sisäinen, ja yksi moneen -yhteys, joka on saartenvälinen.

![Esimerkki yhdistelmämallista, joka koostuu kahdesta saaresta, heikot yhteydet merkittyinä](media/desktop-relationships-understand/data-island-example-weak.png)

Tuontimalleissa tietorakenteita ei koskaan luoda heikoille yhteyksille. Tämä tarkoittaa, että taulukkoliitokset on ratkaistava kyselyn aikana.

Taulukon laajentamista ei koskaan tapahdu heikoilla yhteyksillä. Taulukot liitetään käyttämällä INNER JOIN -semantiikkaa, ja tästä syystä tyhjiä virtuaalirivejä ei lisätä viite-eheysrikkomusten kompensoimista varten.

Heikkoihin yhteyksiin liittyy muitakin rajoituksia:

- LIITTYVÄÄ DAX-funktiota ei voida käyttää “yksi”-puolen sarakkeen arvojen hakemiseen
- Topologia rajoittaa RLS:n pakottamista

> [!NOTE]
> Power BI Desktop -mallinäkymässä ei ole aina mahdollista määrittää, onko malliyhteys vahva vai heikko. Monta moneen -yhteys on aina heikko, samoin kuin yksi moneen -yhteys, jos se on saartenvälinen. Yhteyden saartenvälisyyden selvittämiseksi on tarkastettava taulukon tallennustavat ja tietolähteet, jotta päästään oikeaan johtopäätökseen.

### <a name="precedence-rules"></a>Käsittelyjärjestyssäännöt

Kaksisuuntaiset yhteydet voivat tuoda käyttöön useita – ja siksi moniselitteisiä – suodattimien levityspolkuja mallitaulukoiden välillä. Seuraavassa luettelossa esitetään käsittelyjärjestyssäännöt, joita Power BI käyttää moniselitteisyyden tunnistamiseen ja polun selvittämiseen:

1. Monta yhteen- ja yksi yhteen -yhteydet, myös heikot yhteydet
2. Monta moneen -yhteydet
3. Kaksisuuntaiset yhteydet päinvastaisessa suunnassa (eli ”monta”-puolelta)

### <a name="performance-preference"></a>Suorituskykyjärjestys

Seuraavassa luettelossa yhteyksien suodattimenlevityskyky on järjestyksessä nopeimmasta hitaimpaan:

1. Saarensisäiset yksi moneen -yhteydet
2. Monta moneen -kardinaliteettiyhteydet
3. Monta moneen -malliyhteydet, jotka on saavutettu välittäjätaulukon avulla, mikä edellyttää ainakin yhtä kaksisuuntaista yhteyttä
4. Saartenväliset yhteydet

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Tutustu tähtirakenteeseen ja sen merkitykseen Power BI:ssä](guidance/star-schema.md)
- [Yksi-yhteen-suhteen ohjeet](guidance/relationships-one-to-one.md)
- [Monta-moneen-suhteen ohjeet](guidance/relationships-many-to-many.md)
- [Aktiivisten ja passiivisten suhteiden ohjeet](guidance/relationships-active-inactive.md)
- [Kaksisuuntaisen suhteen ohjeet](guidance/relationships-bidirectional-filtering.md)
- [Yhteyden vianmääritysohjeet](guidance/relationships-troubleshoot.md)
- Video: [Huomioitavat asiat Power BI:n yhteyksiin liittyen](https://www.youtube.com/watch?v=78d6mwR8GtA)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
