---
title: Microsoft Power BI Premium -kapasiteettien hallinta
description: Kuvailee Power BI Premium -kapasiteettien hallintatehtäviä.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 2e32a61891cee2fb5e2a80167d5283962dc164bb
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/02/2019
ms.locfileid: "74697470"
---
# <a name="managing-premium-capacities"></a>Premium-kapasiteettien hallinta

Power BI Premiumin hallinta edellyttää Premium-kapasiteettien luontia, hallintaa ja seurantaa. Tässä artikkelissa on yleiskatsaus kapasiteetteihin. Vaiheittaiset ohjeet ovat kohdassa [Kapasiteettien määrittäminen ja hallinta](service-admin-premium-manage.md).

## <a name="creating-and-managing-capacities"></a>Kapasiteettien luominen ja hallinta

Power BI:n hallintaportaalin **Kapasiteettiasetukset**-sivulla näytetään ostettujen näennäisytimien ja saatavana olevien Premium-kapasiteettien määrä. Tällä sivulla Office 365:n yleiset järjestelmänvalvojat tai Power BI -palvelun järjestelmänvalvojat voivat luoda Premium-kapasiteetteja käytettävissä olevista näennäisytimistä tai muokata olemassa olevia Premium-kapasiteetteja.

Premium-kapasiteetteja luodessaan järjestelmänvalvojien on määritettävä seuraavat asiat:

- kapasiteetin nimi (yksilöllinen nimi vuokraajassa)
- kapasiteetin järjestelmänvalvojat
- kapasiteetin koko
- tietojen sijainnin alue

Vähintään yksi kapasiteetin järjestelmänvalvoja täytyy määrittää. Kapasiteetin järjestelmänvalvojiksi määritetyt käyttäjät voivat

- määrittää kapasiteetille työtiloja
- hallita käyttöoikeuksia lisätäkseen kapasiteetin järjestelmänvalvojia tai käyttäjiä, joilla on määrityskäyttöoikeudet (jotta he voivat määrittää kapasiteetille työtiloja)
- hallita kuormituksia määrittääkseen suurimman muistin käytön sivutetuille raporteille ja tietovuon kuormituksille
- käynnistää kapasiteetin uudelleen nollatakseen kaikki toiminnot järjestelmän ylikuormituksen vuoksi.

Kapasiteetin järjestelmänvalvojat eivät voi käyttää työtilan sisältöä, ellei sitä ole nimenomaisesti määritetty työtilan käyttöoikeuksissa. Heillä ei myöskään ole käyttöoikeuksia kaikkiin Power BI -järjestelmänvalvojien alueisiin (ellei sitä ole nimenomaisesti määritetty), kuten käyttötilastoihin, valvontalokeihin tai vuokraajan asetuksiin. On tärkeää huomata, että kapasiteettien järjestelmänvalvojilla ei ole oikeutta uusien kapasiteettien luomiseen tai olemassa olevien kapasiteettien skaalaamiseen. Järjestelmänvalvojat määritetään kapasiteetin mukaan, jolloin he voivat vain tarkastella ja hallita kapasiteetteja, joihin he ovat määritettyjä.

Kapasiteetin koko valitaan käytettävissä olevasta varastointiyksikköasetusten luettelosta, ja sitä rajoittaa käytettävissä olevien näennäisytimien määrä varannossa. Varannosta on mahdollista luoda useita kapasiteetteja joko yhdestä tai useammasta ostetusta varastointiyksiköstä. Esimerkiksi P3-varastointiyksikköä (32 näennäisydintä) voidaan käyttää kolmen kapasiteetin luomiseen: yksi P2 (16 näennäisydintä) ja kaksi P1:tä (2 x 8 näennäisydintä). Parannettu suorituskyky ja skaalaus voidaan saavuttaa luomalla pienempiä kapasiteetteja [Premium-kapasiteettien optimointi](service-premium-capacity-optimize.md) -artikkelissa kuvatulla tavalla. Seuraavassa kuvassa on mallimääritys kuvitteelliselle Contoso-organisaatiolle. Se sisältää viisi Premium-kapasiteettia (3 x P1 ja 2 x P3), joissa jokaisessa on työtila, sekä useita työtiloja jaetussa kapasiteetissa.

![Mallimääritys kuvitteelliselle Contoso-organisaatiolle](media/service-premium-capacity-manage/contoso-organization-example.png)

Premium-kapasiteetti voidaan määrittää jollekin muulle alueelle kuin Power BI -vuokraajan kotialueelle. Tätä kutsutaan multi-geoksi. Multi-geon avulla järjestelmänvalvoja voi hallita, missä palvelinkeskuksissa Power BI -sisältösi sijaitsee määritettyjen maantieteellisten alueiden sisällä. Multi-geon käyttöönotto liittyy yleensä yrityksen tai julkishallinnon vaatimustenmukaisuusehtoihin, eivät niinkään suorituskykyyn tai skaalaukseen. Raporttien ja raporttinäkymien lataamiseen liittyy edelleen metatietopyyntöjä kotialueelle. Lue lisätietoja artikkelista [Multi-Geo-tuki Power BI Premiumille](service-admin-premium-multi-geo.md).

Power BI -palvelun järjestelmänvalvojat ja Officen 365:n yleiset järjestelmänvalvojat voivat muokata Premium-kapasiteetteja. He voivat erityisesti

- muuttaa kapasiteetin kokoa resurssien suurentamiseksi tai pienentämiseksi
- lisätä tai poistaa kapasiteetin järjestelmänvalvojia
- lisätä tai poistaa käyttäjiä, joilla on määrityskäyttöoikeudet
- lisätä tai poistaa lisäkuormituksia
- vaihtaa aluetta.

Määrityskäyttöoikeudet vaaditaan työtilan määrittämiseen tietylle Premium-kapasiteetille. Käyttöoikeudet voidaan myöntää koko organisaatiolle, tietyille käyttäjille tai ryhmille.

Oletusarvoisesti Premium-kapasiteetit tukevat Power BI -kyselyjen suorittamiseen liittyviä kuormituksia. Premium-kapasiteetit tukevat myös muita kuormituksia, joita ovat **Tekoäly (kognitiiviset palvelut)** , **Sivutetut raportit** ja **Tietovuot**. Jokainen kuormitus edellyttää enimmäismuistin (prosenttiosuutena kaikesta käytettävissä olevasta muistista) määrittämistä, jota kuormitus voi käyttää. On tärkeää ymmärtää, että muistin enimmäisvarausten lisääminen voi vaikuttaa isännöitävien aktiivisten mallien määrään ja päivitysten siirtomäärään. 

Muisti kohdistetaan tietovoille dynaamisesti mutta sivutetuille raporteille staattisesti. Syy enimmäismuistin staattiseen varaamiseen on se, että sivutetut raportit suoritetaan kapasiteetin suojatussa rajoitetussa tilassa. Sivutettujen raporttien muisti on määritettävä varoen, sillä se vähentää käytettävissä olevaa muistia mallien lataamista varten. Jos haluat lisätietoja, katso kohta [Oletusmuistiasetukset](service-admin-premium-workloads.md#default-memory-settings).

Premium-kapasiteetin poistaminen on mahdollista, eikä se aiheuta sen työtilojen ja sisällön poistamista. Sen sijaan se siirtää kaikki määritetyt työtilat jaettuun kapasiteettiin. Jos Premium-kapasiteetti luotiin eri alueella, työtila siirretään kotialueen jaettuun kapasiteettiin.

### <a name="assigning-workspaces-to-capacities"></a>Työtilojen määrittäminen kapasiteeteille

Premium-kapasiteetille voidaan määrittää työtiloja Power BI -hallintaportaalissa tai, työtilan kohdalla, **Työtila**-ruudussa.

Kapasiteetin järjestelmänvalvojat, Office 365:n yleiset järjestelmänvalvojat sekä Power BI -palvelun järjestelmänvalvojat voivat joukkomäärittää työtiloja Power BI -hallintaportaalissa. Joukkomääritys voi koskea seuraavia kohteita:

- **Työtilat käyttäjien mukaan** – Kaikki näiden käyttäjien omistamat työtilat, mukaan lukien henkilökohtaiset työtilat, on määritetty Premium-kapasiteettiin. Tähän sisältyy työtilojen uudelleenvaraaminen, kun ne on jo määritetty eri Premium-kapasiteettiin. Lisäksi käyttäjille myönnetään myös työtilan määrityskäyttöoikeudet.

- **Määritetyt työtilat**
- **Koko organisaation työtilat** – Kaikki työtilat, mukaan lukien henkilökohtaiset työtilat, on määritetty Premium-kapasiteettiin. Kaikille nykyisille ja tuleville käyttäjille myönnetään työtilan määrityskäyttöoikeudet. Tätä menetelmää ei suositella. Kohdennetumpi menetelmä on suositellumpi tapa.

Työtila voidaan lisätä Premium-kapasiteettiin käyttämällä **Työtila**-ruutua, jos käyttäjä on sekä työtilan järjestelmänvalvoja että hänellä on määrityskäyttöoikeudet.

![Työtilan määrittäminen Premium-kapasiteettiin Työtila-ruudun avulla](media/service-premium-capacity-manage/assign-workspace-capacity.png)

Työtilan järjestelmänvalvojat voivat poistaa työtilan kapasiteetista (jaettuun kapasiteettiin) ilman määrityskäyttöoikeuksia. Työtilojen poistaminen varatuista kapasiteeteista siirtää työtilan käytännössä jaettuun kapasiteettiin. Ota huomioon, että työtilan poistamisella Premium-kapasiteetista voi olla kielteisiä seurauksia: esimerkiksi jaettu sisältö ei ehkä ole enää käytettävissä ilmaisen Power BI:n lisensoiduille käyttäjille tai ajoitettu päivitys keskeytyy, kun jaettujen kapasiteettien tukemat määrät ylittyvät.

Power BI -palvelussa Premium-kapasiteettiin määritetyn työtilan tunnistaa helposti sen työtilan nimeä koristavasta vinoneliökuvakkeesta.

![Premium-kapasiteettiin määritetyn työtilan tunnistaminen](media/service-premium-capacity-manage/premium-diamond-icon.png)

## <a name="monitoring-capacities"></a>Kapasiteettien valvonta

Premium-kapasiteettien valvonta antaa järjestelmänvalvojille käsityksen siitä, miten kapasiteetit toimivat. Kapasiteetteja voidaan valvoa Power BI -hallintaportaalissa tai **Power BI Premium -kapasiteetin mittausarvot** (Power BI) -sovelluksella.

### <a name="power-bi-admin-portal"></a>Power BI -hallintaportaali

Hallintaportaalissa kullekin kapasiteetille on **Kunto**-välilehti, joka sisältää yhteenvedon kapasiteetin mittareista ja kunkin käytössä olevan kuormituksen. Mittarit näyttävät keskiarvon viimeisten seitsemän päivän ajalta.  

Kapasiteettitasolla mittarit ovat kumulatiivisia kaikissa käytössä olevissa kuormituksissa. Käytettävissä ovat seuraavat mittarit:

- **SUORITTIMEN KÄYTTÖ** – antaa keskimääräisen suorittimen käytön prosentteina käytettävissä olevasta suorittimen kokonaismäärästä kapasiteetille.  
- **MUISTIN KÄYTTÖ** – antaa keskimääräisen muistin käytön (gigatavuina) käytettävissä olevana muistin kokonaismääränä kapasiteetille. 

Kunkin käytössä olevan kuormituksen osalta annetaan suorittimen käyttö ja muistin käyttö sekä useita kuormituskohtaisia mittareita. Esimerkiksi Tietovuo-kuormituksessa **Kokonaismäärä**-kohdassa näytetään kunkin tietovuon päivitysten kokonaismäärä, ja **Keskimääräinen kesto** ilmaisee tietovuon päivityksen keskimääräisen keston.

![Kapasiteetin kunto -välilehti portaalissa](media/service-premium-capacity-manage/admin-portal-health-dataflows.png)

Lisätietoja kunkin kuormituksen kaikista käytettävissä olevista mittareista on kohdassa [Kapasiteettien valvonta hallintaportaalissa](service-admin-premium-monitor-portal.md).

Power BI -hallintaportaalin valvontatoiminnot on suunniteltu tarjoamaan nopean yhteenvedon kapasiteetin tärkeimmistä mittareista. Tarkempaa seurantaa varten on suositeltavaa käyttää **Power BI Premium -kapasiteettiarvot** -sovellusta.

### <a name="power-bi-premium-capacity-metrics-app"></a>Power BI Premium -kapasiteettiarvot -sovellus

[Power BI Premium -kapasiteettiarvot](https://appsource.microsoft.com/product/power-bi/pbi_pcmm.pbi-premiumcapacitymonitoring?tab=Overview) -sovellus on kapasiteetin järjestelmänvalvojien käytettävissä oleva Power BI -sovellus, ja se asennetaan samalla tavalla kuin muutkin Power BI -sovellukset. Se sisältää koontinäytön ja raportin.

![Power BI Premium -kapasiteettiarvot -sovellus](media/service-premium-capacity-manage/capacity-metrics-app.png)

Kun sovellus avautuu, koontinäyttö ladataan, ja siinä näkyy useita ruutuja, joissa näkyy koottu näkymä kaikista niistä kapasiteeteista, joiden kapasiteetin järjestelmänvalvoja käyttäjä on. Koontinäytön asettelu sisältää viisi pääosaa:

- **Yleiskatsaus** – sovelluksen versio, kapasiteettien ja työtilojen määrä
- **Järjestelmän yhteenveto** – muistin ja suorittimen mittarit
- **Tietojoukon yhteenveto** – tietojoukkojen määrä, DQ/LC, päivitys ja kyselyjen mittarit
- **Tietovuon yhteenveto** – tietovoiden määrä ja tietojoukon mittarit
- **Sivutetun raportin yhteenveto** – päivitysten ja näkymien mittarit

Pohjana olevaa raporttia, josta koontinäytön ruudut on kiinnitetty, voidaan käyttää napsauttamalla mitä tahansa koontinäytön ruutua. Se tarjoaa yksityiskohtaisen perspektiivin kustakin koontinäytön osasta ja tukee vuorovaikutteista suodatusta. 

Suodatus voidaan tehdä määrittämällä osittajia päivämääräalueen, kapasiteetin, työtilan ja kuormituksen mukaan (raportti, tietojoukko, tietovuo) ja valitsemalla raportin visualisoinneista elementtejä raporttisivun ristiinsuodatusta varten. Ristiinsuodatus on tehokas tekniikka, jonka avulla tiedot voidaan rajata tiettyihin ajanjaksoihin, kapasiteetteihin, työtiloihin, tietojoukkoihin jne., ja se voi olla erittäin hyödyllinen pääsyyanalyysin suorittamisessa.

Lisätietoja koontinäytön ja raportin mittareista sovelluksessa on kohdassa [Premium-kapasiteettien valvonta sovelluksen avulla](service-admin-premium-monitor-capacity.md).

### <a name="interpreting-metrics"></a>Mittareiden tulkinta

Mittareita tulee valvoa perusymmärryksen saamiseksi resurssien käytöstä ja kuormituksesta. Jos kapasiteetista tulee hidas, on tärkeää ymmärtää, mitä mittareita pitää valvoa ja mitä päätelmiä niistä voi tehdä.

Ihannetapauksessa kyselyiden pitäisi valmistua sekunnissa, jotta ne voivat tarjota reagoivia kokemuksia raportin käyttäjille ja mahdollistaa kyselyjen suuremman siirtomäärän. Taustaprosessien, kuten päivitysten, valmistumisen hidastuminen ei ole yleensä yhtä huolestuttavaa.

Yleensä hitaat raportit saattavat olla merkki ylikuumenevasta kapasiteetista. Kun raporttien lataaminen epäonnistuu, se on merkki ylikuumenneesta kapasiteetista. Kummassakin tilanteessa pääsyynä voi olla useita tekijöitä, kuten seuraavat tekijät:

- **Epäonnistuneet kyselyt** ovat varmasti merkki muistiin kohdistuvasta paineesta ja siitä, että mallia voitu ladata muistiin. Power BI -palvelu yrittää ladata mallin 30 sekunnin ajan ennen epäonnistumista.

- **Liian pitkät kyselyiden odotusajat** voivat johtua useista syistä:
  - Power BI -palvelun on ensin häädettävä malli(t) ja sitten ladattava malli, jossa kysely suoritetaan (muista, että kasvaneet tietojoukkojen häätömäärät eivät yksinään viittaa kapasiteetin stressiin, ellei siihen liity myös pitkiä kyselyiden odotusaikoja, jotka ovat merkkinä muistin tietojen poistamisesta).
  - Mallin latausajat (erityisesti odotusaika suuren mallin lataamisessa muistiin).
  - Pitkäkestoiset kyselyt.
  - Liian monta LC\DQ-yhteyttä (kapasiteettirajoitukset ylittyvät).
  - Suorittimen kylläisyys.
  - Monitasoiset raporttimallit, joissa on liian paljon visualisointeja yhdellä sivulla (muista, että jokainen visualisointi on kysely).

- **Pitkät kyselyjen kestot** voivat olla merkkinä siitä, että malleja ei ole optimoitu, erityisesti silloin, kun kapasiteetissa on aktiivisena useita tietojoukkoja ja vain yksi tietojoukko tuottaa pitkiä kyselyjen kestoja. Tämä viittaa siihen, että kapasiteetilla on riittävät resurssit ja että kyseessä oleva tietojoukko ei ole paras mahdollinen tai että se on vain hidas. Pitkäkestoiset kyselyt voivat olla ongelmallisia, koska ne voivat estää muiden prosessien tarvitsemien resurssien käyttämisen.
- **Pitkät päivityksen odotusajat** ovat merkkinä siitä, että muisti ei riitä useiden aktiivisten mallien muistin käytön vuoksi, tai että ongelmallinen päivitys estää muita päivityksiä (ylittäen rinnakkaiset päivitysrajat).

Tarkempia tietoja mittareiden käyttämisestä on [Premium-kapasiteettien optimointi](service-premium-capacity-optimize.md) -artikkelissa.

## <a name="acknowledgements"></a>Kiitokset

Tämän artikkelin on kirjoittanut Peter Myers, joka on Data Platform MVP ja itsenäinen BI-asiantuntija, yhdessä [Bitwise Solutionsin](https://www.bitwisesolutions.com.au/) kanssa.

## <a name="next-steps"></a>Seuraavat vaiheet

> [!div class="nextstepaction"]
> [Premium-kapasiteettien optimointi](service-premium-capacity-optimize.md)   
> [!div class="nextstepaction"]
> [Premium-kapasiteettien kuormitusten määrittäminen](service-admin-premium-workloads.md)   

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

