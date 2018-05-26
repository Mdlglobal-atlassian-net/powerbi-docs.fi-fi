---
title: Raporttien ja visualisointien parhaat suunnittelukäytännöt (tekninen raportti)
description: 'Tekninen raportti: parhaat käytännöt raporttien suunnitteluun Power BI:ssä'
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: ''
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/21/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 868d05891d1b2cb24dfae60b7f3bee405ff7d08f
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/08/2018
---
# <a name="best-design-practices-for-reports-and-visuals"></a>Raporttien ja visualisointien parhaat suunnittelukäytännöt
<!-- Shared newnav Include -->
[!INCLUDE [newnavbydefault](./includes/newnavbydefault.md)]

## <a name="introduction"></a>Johdanto
Tästä raportista voit lukea parhaita käytäntöjä raporttien suunnitteluun Power BI:ssä. Raportin alussa käsitellään suunnittelua ja suunnitteluperiaatteita, joita voit noudattaa omissa raporteissasi sekä raporttiin sisältyvissä sivuissa ja yksittäisissä visualisoinneissa.  Monet näistä parhaista käytännöistä soveltuvat myös koontinäyttöjen suunnitteluun.

Toivomme, että tämä tekninen raportti antaa sinulle alkusysäyksen ja että sovellat oppimaasi omiin raportteihin ja visualisointeihin sekä jatkat keskustelua community.powerbi.comissa. BI-raportin suunnittelun ja visualisoinnin käyttö on nykyisin kuuma puheenaihe. Monet mielipidevaikuttajat, blogikirjoittajat ja verkkosivustot ovat käsitelleet tätä aihetta syvällisesti (lopussa on lueteltu niistä joitakin).   

> [!NOTE]
> Tämän teknisen raportin suositukset on tarkoitettu ohjenuoraksi tilanteissa, joissa niistä voi olla hyötyä. Alla kuvatun jokaisen periaatteen osalta on yleensä päteviä syitä ”rikkoa sääntöä”.
> 
> 

*Tietoja tulvii joka nurkasta. Kyse ei ole niiden liian suuresta määrästä vaan siitä, ettemme tiedä, miten taltuttaa niitä.*
-- Stephen Few

## <a name="a-look-at-the-landscape-and-terminology"></a>Katsaus käyttöympäristöön ja terminologiaan
Power BI:n raportissa voi olla yksi tai useampi raporttisivu. Kaikkiin sivuihin viitataan yhteisesti raporttina. Raportin peruselementtejä ovat visualisoinnit, erilliset kuvat ja tekstiruudut. Siihen liittyy lukemattomia muotoiluvaihtoehtoja yksittäisistä arvopisteistä raportin elementteihin ja itse raporttisivuun.

Aloitamme raportin suunnitteluvaiheesta, jatkamme raportin suunnittelun perusperiaatteisiin, käsittelemme visuaalisen suunnittelun periaatteita ja pureudumme lopuksi yksittäisten visualisointityyppien parhaisiin käytäntöihin.

Löydät syvällisiä neuvoja ja ohjeita Power BI:n raporttien luomisesta ja käyttämisestä **powerbi.comista > Opiskele**.

## <a name="before-you-build-your-first-visualizationfocus-on-requirements"></a>Keskity ennen ensimmäisen visualisoinnin luomista vaatimuksiin
Raportin luominen alkaa jo ennen ensimmäisen visualisoinnin luomista, koska hyvän raportin perustana on suunnittelu.  Tutustu käsiteltäviin tietoihin ja kirjoita ylös raportin vaatimukset. Kysy itseltäsi ”Mitkä ovat liiketoimintatarpeet, miten näitä tietoja käytetään ja kuka niitä käyttää?” Avainkysymys on ”Mitä päätöksiä lukija pystyy tekemään tämän raportin perusteella?”

Suunnittelu perustuu näistä kysymyksistä saatuun vastaukseen. Jokainen raportti kertoo tarinan. Varmista, että tarina vastaa liiketoimintatarvetta. Voi olla houkuttelevaa lisätä visualisointeja, jotka näyttävät dramaattisia merkityksellisiä tietoja. Jos nämä tiedot eivät kuitenkaan vastaa liiketoimintatarpeita, raportista ei ole hyötyä – ja itse asiassa nämä visualisoinnit saattavat häiritä lukijoiden keskittymistä. Saatat myös huomata, ettei raportti anna tarvittavia tietoja päätöksen tekemiseen. Voidaanko tätä raporttia käyttää tarvittavien asioiden mittaamiseen?

Raportteja voidaan käyttää muun muassa valvontaan, selvittämiseen, seurantaan, ennustamiseen, mittaamiseen, hallintaan ja testaukseen. Jos liiketoimintatarpeena on suorituskykyä mittaava myyntiraportti, suunnitellussa raportissa saatetaan tarkastella nykyistä myyntiä vertaamalla sitä aiempaan myyntiin ja kilpailijoihin. Se voi myös sisältää suorituskykyilmaisimia, jotka käynnistävät hälytyksiä.  Lukijat voivat myyntilukujen perusteella havaita myymälöiden sulkemisia tai toimitusketjuongelmia, jotka voivat vaikuttaa myyntiin.  He voivat myös ehkä tarkastella myyntiä esimerkiksi myymälän, alueen, tuotteen ja vuodenajan mukaan.

Sinun on tiedettävä raportin asiakkaat ja suunniteltava se siten, että käytät tuttua terminologiaa sekä annat tietoja asiakkaiden tietotasoa vastaavalla yksityiskohtaisuuden ja monimutkaisuuden tasolla. Onko asiakastyyppejä useampia? Yksi koko ei aina sovi kaikille; suunnittele erillisiä raporttisivuja asiantuntemuksen mukaan ja muista merkitä kaikki sivut selvästi, jotta asiakkaat löytävät tarvitsemansa. Voit myös käyttää osittajia, jotta asiakkaat voivat räätälöidä sivut haluamakseen. Ota asiakas mukaan suunnitteluvaiheeseen ja vältä luomasta jotakin, jota uskot heidän tarvitsevan.  Ole valmis aloittamaan uudestaan ja kertaamaan asioita.

Kun olet määrittänyt liiketoimintatarpeen, asiakkaat ja sisällytettävän metriikan, valitse oikeat visualisoinnit tarinan kertomiseksi esittämällä ne mahdollisimman tehokkaasti. Koska alue on laaja, käsittelemme aluksi joitakin raportin suunnittelun perusperiaatteita.

## <a name="principles-of-report-design"></a>Raportin suunnittelun periaatteet
Raporttisivun tila on rajallinen. Yksi vaikeimmista asioista onkin mahduttaa kaikkia halutut elementit tähän tilaan siten, että tiedot ymmärretään helposti. Älä myöskään aliarvioi ”kauneuden” merkitystä. Avaimena on löytää kauneuden ja hyödyllisyyden välinen tasapaino.

Katsotaanpa asettelua, selkeyttä ja estetiikkaa.

### <a name="layout---the-report-canvas"></a>Asettelu – raportin piirtoalusta
Raportin piirtoalustalla on rajallisesti tilaa.  Jos kaikki elementit eivät mahdu yhdelle raporttisivulle, voit jakaa raportin eri sivuille.  Raporttisivu voidaan räätälöidä tiettyä yleisöä (henkilöstöhallinto, tietotekniikka, myynti, ylin johtoryhmä) tai tiettyä liiketoimintakysymystä (miten viat vaikuttavat seisonta-aikaan, miten markkinointikampanja vaikuttaa tunteisiin) varten. Raporttisivu voidaan myös esittää vaiheittaisena tarinana (ensimmäinen sivu on yleiskatsaus tai mielenkiinnon herättävä ”koukku”, tarinaa jatketaan toisella sivulla, kolmannella sivulla sukelletaan tarinaan syvemmin jne.).  Jos koko raportti mahtuu yhdelle sivulle, niin homma on sillä selvä. Jos näin ei ole, luo erillisiä raporttisivuja, jotka pätkivät sisällön loogisesti.  Äläkä unohda antaa sivuille merkityksellisiä ja hyödyllisiä nimiä.

Ajattele, että täytät taidegalleriaa. Et varmaankaan laittaisi 50 taideteosta pieneen huoneeseen, jonka täyttäisit tuoleilla maalaten kunkin seinän eri värillä. Kuraattorina valitsisit vain taideteokset, joilla on yhteinen teema, ja asettaisit ne ympäri huonetta siten, että vierailijoilla on paljon tilaa liikkua ja ajatella, sekä laittaisit taideteosten viereen niitä kuvaavat tietokortit. Sen vuoksi useimmissa moderneissa gallerioissa onkin runsaasti seiniä!
Tätä artikkelia varten aloitamme raportin esimerkillä, joka vaatii  paljon työtä.  Soveltamalla suunnittelun parhaita käytäntöjä ja periaatteita voimme parantaa raporttiamme.

![](media/power-bi-visualization-best-practices/power-bi-example1newa.png)

**Kuva 1:    Tämä huonosti suunniteltu raporttisivu vaatii paljon työtä**

Yllä olevassa esimerkissä on monta tilaan liittyvää (asettelu) suunnitteluongelmaa, joita käsittelemme seuraavassa:

* tasaus, järjestys ja läheisyys
* huono tilankäyttö ja lajittelu
* tarpeettomat osat

### <a name="alignment-order-and-proximity"></a>Tasaus, järjestys ja läheisyys
Raportin elementtien asettelu vaikuttaa ymmärtämiseen ja ohjaa lukijaa raporttisivun läpi. Elementtien sijoittelutapa kertoo tarinan.  Tarina voi olla ”aloita tästä ja katso sitten tätä” tai ”nämä kolme elementtiä liittyvät toisiinsa”.

* Useimmissa kulttuureissa luetaan vasemmalta oikealle ja ylhäältä alas. Sijoita kaikkein tärkein elementti raportin vasempaan yläkulmaan. Järjestä sitten muut visualisoinnit siten, että tietoja selataan ja ymmärretään loogisesti.
* Sijoita elementit, jotka edellyttävät lukijaa tekemään valinnan, niiden visualisointien vasemmalle puolelle, joihin valinta vaikuttaa (esimerkiksi osittajat).
* Aseta sijaintiriippuvaiset elementit lähelle toisiaan; läheisyys tarkoittaa, että elementit liittyvät toisiinsa.
* Toinen tapa välittää suhteita on lisätä reunus tai väritausta liittyvien elementtien ympärille. Vastaavasti voit erottaa raportin eri osiot lisäämällä erotinviivan.
* Voit pätkiä raporttisivun osiot visuaalisesti tyhjän tilan avulla.
* Täytä raporttisivu. Jos siinä on mielestäsi paljon ylimääräistä tyhjää tilaa, voit suurentaa visualisointeja tai pienentää piirtoalustaa.
* Määritä raportin elementtien koot harkitusti. Älä anna tilan saatavuuden määrätä visualisoinnin kokoa.
* Tee tärkeistä elementeistä suurempia kuin muista tai lisää nuolen kaltainen visuaalinen elementti huomion kiinnittämiseksi.
* Tasaa raporttisivun elementit joko symmetrisesti tai tarkoituksella epäsymmetrisesti.

Katsotaanpa tasausta tarkemmin.

#### <a name="alignment"></a>Tasaus
Tasaus ei tarkoita sitä, että eri osien on oltava saman kokoisia tai että raportin jokaisella rivillä on oltava sama määrä osia. Se tarkoittaa vain sitä, että sivun rakenne helpottaa sen selausta ja luettavuutta.

Näemme alla olevasta päivitetystä raportistamme, että raportin osat on nyt tasattu vasempaan ja oikeaan reunaan ja että jokainen raportin rivi on tasattu myös vaaka- ja pystysuorassa. Osittajat ovat niiden visualisointien vasemmalla puolella, joihin ne vaikuttavat.

![](media/power-bi-visualization-best-practices/power-bi-example2new.png)

**Kuva 2:    Huonon raportin esimerkkimme parantui asettelun muokkauksilla**

Power BI sisältää työkaluja, joiden avulla voit tasata visualisointeja. Kun olet valinnut Power BI Desktopissa useita visualisointeja, voit täsmätä visualisointien sijainnin **Visualisoinnit**-valintanauhan **Tasaa ja jaa** -vaihtoehtojen avulla.

![](media/power-bi-visualization-best-practices/power-bi-visualization.png)

**Kuva 3:    Tasaa visualisoinnit Power BI Desktopissa**

Voit Power BI:n verkkoversiossa ja Power BI Desktopissa myös hallita tarkasti kaikkien visualisointien kokoa ja sijaintia muotoiluruudun **Yleiset**-välilehdessä:

![](media/power-bi-visualization-best-practices/power-bi-align-vizs.png)

**Kuva 4:    Määritä visualisoinnin tarkka sijainti**

Esimerkkiraporttisivullamme (kuva 2) kaksi korttia ja leveä reunus on tasattu **X-sijainnissa** arvoon 200.

#### <a name="fit-to-the-space"></a>Sovita tilaan
Hyödynnä optimaalisesti käytettävissä olevaa tilaa.  Jos tiedät, miten raporttia tarkastellaan tai miten se näytetään, ota se huomioon suunnittelussa. Vähennä tyhjää tilaa piirtoalustan täyttämiseksi.  Pyri kaikin tavoin välttämään vierityspalkkeja yksittäisissä visualisoinneissa.  Täytä tila puristamatta visualisointeja liian pieneen tilaan.

##### <a name="adjust-the-page-size"></a>Säädä sivun kokoa
Pienentämällä sivun kokoa yksittäiset elementit näyttävät suuremmilta verrattuna koko sivuun. Voit tehdä näin poistamalla valinnan sivun mistä tahansa visualisoinnista ja käyttämällä muotoiluruudun **Sivukoko**-välilehteä.  

Tässä on raporttisivu, jossa käytetään sivukokoa 4:3 ja sitten sivukokoa 16:9. Huomaa, miten asettelu sopii paljon paremmin sivukokoon 16:9. Tilaa jää jopa riittävästi vierityspalkin poistamiseen toisesta visualisoinnista.

![](media/power-bi-visualization-best-practices/power-bi-page-view-before.png)

**Kuva 5a:    Raportti sivukoossa 4:3**

![](media/power-bi-visualization-best-practices/power-bi-page-view-after.png)

**Kuva 5b:    Raportti sivukoossa 16:9**

Katsotaanko raporttiasi sivukoossa 4:3, 16:9 vai jossain muussa sivukoossa? Pieneltä vai suurelta näytöltä? Vai katsotaanko raporttia kaikissa mahdollisissa näyttösuhteissa ja -koissa?  Pidä tämä mielessä suunnittelun aikana.

Näyttää siltä, että esimerkkiraporttisivumme on hieman ahdas. Kun mitään visualisointia ei ole valittu, avaa muotoiluruutu valitsemalla maalaustelan kuvake. Laajenna **sivukokoa** ja muuta **korkeudeksi** 900.

![](media/power-bi-visualization-best-practices/power-bi-page-size.png)

**Kuva 6:    Lisää sivun korkeutta**

#### <a name="reduce-clutter"></a>Poista tarpeettomat kohdat
Tarpeettomia kohtia sisältävää raporttisivua on vaikea ymmärtää yhdellä silmäyksellä. Se voi olla jopa niin hankalaa, että lukijat eivät edes tohdi yrittää.  Hankkiudu eroon kaikista raportin elementeistä, jotka eivät ole tarpeellisia. Älä lisää sanahälinää, joka ei helpota ymmärtämistä tai selaamista. Raporttisivun on välitettävä tiedot mahdollisimman selkeästi, nopeasti ja johdonmukaisesti.

Edward Tufte kutsuu sitä kirjassaan *The Visual Display of Quantitative Information* ”tiedosta käsinkirjoitukseen -suhteeksi”.  Poista periaatteessa kaikki, joka ei ole olennaista.

Poistamalla tarpeettomat kohdat raporttisivulle tulee lisää tyhjää tilaa ja voit soveltaa paremmin parhaita käytäntöjä, jotka opit yllä olevassa ”Tasaus, järjestys ja läheisyys” -osiossa.

Esimerkkimme näyttää nyt jo paremmalta. Olemme poistaneet paljon tarpeettomia kohtia ja lisänneet muotoja elementtien ryhmittelemiseksi yhteen.  Taustakuva on poistettu, tarpeeton nuolimuoto ja tekstiruutu on poistettu, yksi visualisointi on siirretty raportin toiselle sivulle jne. Olemme myös pidentäneet sivun kokoa tyhjän (keltaisen) tilan lisäämiseksi.

![](media/power-bi-visualization-best-practices/power-bi-example3newer.png)

**Kuva 7:    Huonon raportin esimerkistä on poistettu tarpeettomat kohdat**

### <a name="tell-a-story-at-a-glance"></a>Kerro tarina yhdellä silmäyksellä
Yleisenä testinä pitäisi olla se, että joku, joka ei ole nähnyt raporttia aiemmin, pystyy nopeasti ymmärtämään sen ilman selityksiä. Lukijoiden pitäisi nopealla silmäyksellä nähdä, mitä sivu käsittelee, ja mitä kukin kaava/taulukko käsittelee.   

Kun lukijat tarkastelevat raporttia, katseen pitäisi ohjautua elementtiin, jota haluat heidän katsovat ensin, ja jatkua sitten vasemmalta oikealle ja ylhäältä alas.  Voit muuttaa tätä käytöstä lisäämällä visuaalisia vihjeitä, kuten tekstiruudun selitteitä, muotoja, reunuksia, kokoja ja värejä.  

#### <a name="text-boxes"></a>Tekstiruudut
Joskus visualisointien otsikot eivät riitä kertomaan tarinaa.  Lisäämällä tekstiruutuja voit viestiä raportteja tarkastelevien henkilöiden kanssa.  Tekstiruudut voivat kuvata raporttisivua, visualisointien ryhmää tai yksittäistä visualisointia. Ne voivat selittää tuloksia tai määritellä tarkemmin visualisointia tai sen osia tai visualisointien välisiä suhteita. Tekstiruutujen avulla voidaan kiinnittää huomio tekstiruudussa korostettujen eri kriteerien mukaan.

Valitse Power BI -palvelun yläreunan valikkopalkista **Tekstiruutu**. (Valitse Power BI Desktopissa **Tekstiruutu** valintanauhan **Lisää**-alueelta.)

![](media/power-bi-visualization-best-practices/power-bi-text-boxes.png)

**Kuva 8:    Lisää tekstiruutu**

Kirjoita tyhjään ruutuun ja määritä sitten fontti, koko, tasaus jne. alareunan ohjausobjektien avulla. Voit muuttaa ruudun kokoa kahvojen avulla.

![](media/power-bi-visualization-best-practices/power-bi-text-box-edit.png)

**Kuva 9:    Muotoile tekstiruutua**

Älä lisää liikaa tekstiä! Jos raportissa on liikaa tekstiä, se vie huomion pois visualisoinneista. Jos raporttisivulle on mielestäsi lisättävä paljon tekstiä, jota se olisi ymmärrettävä, aloita raportti uudelleen.  Voitko valita eri visualisoinnin, joka kertoo paremman tarinan yksistään? Voitko muokata visualisoinnin alkuperäisiä otsikkoja siten, että niitä on helpompi ymmärtää?   

#### <a name="text"></a>Teksti
Luo tekstityyliopas ja sovella sitä raportin kaikkiin sivuihin. Valitse vain pari fonttia, tekstikokoa ja väriä.  Sovella tätä tyyliopasta tekstielementtien lisäksi myös visualisointeihin valintaan (katso alla olevia otsikkoja ja selitteitä, jotka ovat visualisointien osa). Määritä sääntöjä sille, milloin käytät esimerkiksi lihavointia, kursivointia, suurempaa fonttikokoa ja tiettyjä värejä.  Yritä välttää koko sanan kirjoittamista isolla tai alleviivausta.

#### <a name="shapes"></a>Muodot
Muodot voivat myös helpottaa selausta ja ymmärtämistä. Voit muotojen avulla ryhmitellä liittyviä tietoja yhteen, korostaa tärkeitä tietoja ja käyttää nuolia katseen suuntaamiseen. Muodot auttavat lukijoita ymmärtämään, mistä aloittaa ja miten tulkita raporttia. Suunnittelussa tästä käytetään usein termiä *kontrasti*.

![](media/power-bi-visualization-best-practices/shapes.png)

**Kuva 10a:    Muodot Power BI -palvelussa**

![](media/power-bi-visualization-best-practices/power-bi-desktop-shapes2new.png)

**Kuva 10b:    Muodot Power BI Desktopissa**

Miltä esimerkkisivumme näyttää nyt?  Kuvassa 11 näkyy siistimpi sivu, jossa on vähemmän tarpeettomia osia ja jossa on käytetty johdonmukaisesti tekstiä, fontteja ja värejä.  Vasemmassa yläkulmassa oleva sivun otsikko kertoo, mitä sivulla käsitellään.

![](media/power-bi-visualization-best-practices/power-bi-example4new.png)

**Kuva 11:    Raporttiesimerkkimme, johon on sovellettu tekstin ohjeviivoja ja johon on lisätty otsikko**

Esimerkissämme raporttisivun otsikko lisättiin vasempaan yläkulmaan eli ensimmäiseen paikkaan, jota lukijat katsovat. Fonttikoko on 28 ja fontti on Segoe Bold, jotta otsikko erottuu sivun muista osista.  Tekstityylioppaassa kehotetaan välttämään taustoja, mustia otsikoita, kuvatekstejä ja selitteitä. Ohjetta on sovellettu mahdollisuuksien mukaan sivun kaikissa visualisoinneissa (yhdistelmäkaavion akseleita ja otsikoita ei voi muokata).  Lisäksi:

* Kortit: **Luokan selite** on poistettu käytöstä, **Otsikko** on käytössä ja pistekoko on 12, musta ja keskitetty.
* Visualisoinnin otsikot: jos käytössä, pistekoko on 12 ja tasattu vasemmalle.
* Osittajat: **Ylätunniste** on poistettu käytöstä, **Otsikko** on käytössä. Jätä **Kohteet** > **Teksti** harmaaksi, pistekoko 10.
* Piste- ja pylväskaaviot: musta fontti X- ja Y-akseleille sekä X- ja Y-akseleiden otsikoille, jos käytössä.

#### <a name="color"></a>Väri
Käytä väriä johdonmukaisesti.  Käsittelemme väriä tarkemmin visuaalisen suunnittelun periaatteissa jäljempänä. Tässä yhteydessä haluamme kuitenkin painottaa värin valinnan merkitystä, jotta se ei häiritse lukijoiden kykyä ymmärtää nopeasti raporttia.  Liian monet kirkkaat värit rasittavat aisteja. Tässä osiossa kerrotaan lisää siitä, mitä värin kanssa ei pitäisi tehdä.

#### <a name="backgrounds"></a>Taustat
Kun määrität raporttisivujen taustoja, valitse värit, jotka eivät jätä raporttia varjoon, kalskahda yhteen sivun muiden värien kanssa tai yleensäkään osu häiritsevästi silmään. Muista, että joillakin väreillä on luontainen merkityksensä.  Esimerkiksi Yhdysvalloissa punainen väri mielletään yleensä ”kielteiseksi”.

![](media/power-bi-visualization-best-practices/power-bi-page-background.png)

**Kuva 12: Määritä raportin tausta**

Et ole luomassa taideteosta vaan toiminnallista raporttia. Valitse väri, joka parantaa luettavuutta ja tuo esiin raportin elementit.  

Värin ja visualisointien käyttöä verkkosivuilla koskevan selvityksen mukaan värien välinen suurempi kontrasti nopeuttaa ymmärtämistä (The effect of text and background colour on visual search of Web pages and **Determining Users’ Perception of Web Page Visual Complexity and Aesthetic Characteristics**).

Olemme soveltaneet joitakin värien parhaita käytäntöjä alla olevaan esimerkkiraporttiimme (kuvat 20 ja 21). Tärkein muutos oli taustavärin muuttaminen mustaksi.  Keltainen oli liian räikeä ja rasitti silmiä.  Lisäksi ”Count of athlete name by year and class” -kaaviossa palkkien keltainen osa katosi keltaiseen taustaan.  Mustan (tai valkoisen) taustan käyttäminen takaa mahdollisimman hyvän kontrastin ja huomioi kiinnittyy visualisointeihin.

Paransimme esimerkkiraporttia myös seuraavasti:

**Sivun otsikko**

Kun muutimme taustan mustaksi, otsikko katosi, koska tekstiruutukentässä voi käyttää vain mustaa fonttia.   Voit korjata tämän lisäämällä sen sijaan tekstiruudun otsikon.  Valitse tekstiruutu, poista teksti ja valitse sitten Visualisoinnit-välilehdessä **Otsikko** ja ota se käyttöön. Valitse nuoli **Otsikko**-vaihtoehtojen laajentamiseksi, kirjoita **Summer Olympic Games** **Otsikon teksti** -kenttään ja valitse valkoinen **fonttiväri**.

![](media/power-bi-visualization-best-practices/power-bi-text-box-title.png)

**Kuva 13: Lisää sivun otsikko**

**Kortit**

Korttivisualisointien tapauksessa avaa muotoiluruutu (maalaustelan kuvake) ja ota **tausta** käyttöön. Valitse valkoinen, jonka läpinäkyvyys on 0 %. Ota sitten **otsikko** käyttöön, valitse valkoinen **fonttiväri** ja musta **taustaväri**.

**Osittajat**

Tässä vaiheessa kahdella osittajalla oli erilainen muotoilu, mikä ei ole suunnittelun kannalta järkevää. Muuta kummankin osittajan taustaväri turkoosiksi.  Turkoosi on hyvä valinta, koska se on osa sivun värivalikoimaa – näet sen täytetyssä kartassa, puukartassa ja pylväskaaviossa.

![](media/power-bi-visualization-best-practices/power-bi-slicer-background.png)

**Kuva 14: Muuta osittajan taustaväriä**

Lisää ohut valkoinen reunus.

![](media/power-bi-visualization-best-practices/power-bi-slicer-outline.png)

**Kuva 15: Lisää reunus osittajaan**

Harmaata fonttia on vaikea erottaa turkoosia vasten, joten muuta **kohteiden** väri valkoiseksi.

![](media/power-bi-visualization-best-practices/power-bi-slicer-items.png)

**Kuva 16: Muuta osittajan fonttiväriä**

Muuta lopuksi **Otsikko**-kohdassa **fonttiväriksi** valkoinen ja lisää musta **taustaväri**.

![](media/power-bi-visualization-best-practices/power-bi-card-formatting.png)

**Kuva 17: Muotoile osittajan otsikkoa**

**Suorakulmio-muoto**

Suorakulmio on myös kadonnut mustaan taustaan.  Korjaa ongelma valitsemalla muoto ja ottamalla **Muotoile muotoa** -ruudussa käyttöön **tausta**.

![](media/power-bi-visualization-best-practices/power-bi-shape-format.png)

**Kuva 18: Muotoile muotoa**

**Pylväskaaviot, kuplakaavio, täytetty kartta ja puukartta**

Lisää valkoinen tausta raporttisivun jäljellä oleviin visualisointeihin. Laajenna muotoiluruudusta **Viiva**-vaihtoehtoa ja määritä **viivan väriksi** valkoinen ja **painoksi** 3.

![](media/power-bi-visualization-best-practices/power-bi-background.png)

**Kuva 19: Lisää valkoinen tausta jäljellä oleviin visualisointeihin**

![](media/power-bi-visualization-best-practices/power-bi-example5a.png)

**Kuva 20: Raporttiesimerkki, jossa on sovellettu värien parhaita käytäntöjä (musta tausta)**

![](media/power-bi-visualization-best-practices/power-bi-example5b.png)

**Kuva 21:    Raporttiesimerkki, jossa on sovellettu värien parhaita käytäntöjä (valkoinen tausta)**
 

### <a name="aesthetics"></a>Estetiikka
Olemme käsitelleet edellä jo useita estetiikkaan liittyviä näkökohtia, kuten tasausta, väriä, fonttivalintoja ja tarpeettomia osia.  Raportin suunnitteluun liittyy kuitenkin pari muuta parasta käytäntöä, joita kannattaa käsitellä ja jotka koskevat raportin yleistä ulkoasua.  

Muista, että raportin funktiona on täyttää liiketoimintatarve, eikä olla kaunis.  Raportin ulkoasun on kuitenkin jossain määrin oltava kaunis etenkin ensivaikutelman luomiseksi. Nashvillen konsultti Tony Bodoh selittää ”Tunteet pulpahtavat pintaan puoli sekuntia ennen kuin logiikka saa jalansijaa.”  Lukijat reagoivat raporttisivuun ensin tunnetasolla ennen kuin tutustuvat siihen syvemmin. Jos sivusi näyttää epäjärjestelmälliseltä, sekavalta tai ammattitaidottomalta, lukijasi ei ehkä koskaan tutustu sen välittämään upeaan tarinaan.

TDI-blogikirjoittaja ja TechTarget-toimialan analyytikko Wayne Eckerson esittää tätä koskevan mainion analogian.  Raportin suunnittelu on aivan kuin sisustaisit huonetta.  Ajan kuluessa ostat maljakon, sohvan, päätypöydän ja maalauksen.  Pidät erikseen näistä kaikista elementeistä. Vaikka jokainen yksilöllinen valinta on merkityksellinen, yhdessä nämä esineet saattavat kalskahtaa toisiinsa tai kilpailla huomiosta.

Keskity seuraaviin seikkoihin:

* Luo raportille yhteinen teema tai ulkoasu, jota sovellat raportin kaikille sivuille.
* Käytä erillisiä kuvia ja muuta grafiikkaa tukena poikkeamatta todellisesta tarinasta.
* Sovella myös kaikkia parhaita käytäntöjä, joita käsittelimme tässä artikkelin kohdassa.

## <a name="principles-of-visual-design"></a>Visuaalisen suunnittelun periaatteet
Olemme jo tarkastelleet raportin suunnittelun periaatteita eli miten voimme järjestää raportin elementit siten, että lukijat ymmärtävät raportin sisällön nopeasti.  Tutustumme nyt itse visualisointien suunnittelun periaatteisiin.  Seuraavassa osiossa pureudumme yksittäisiin visualisointeihin ja käsittelemme joitakin yleisemmin käytettyjen tyyppien parhaita käytäntöjä.

Jätämme tässä osiossa esimerkkiraporttisivumme rauhaan hetkeksi ja tarkastelemme muita esimerkkejä.  Kun olemme käyneet läpi visuaalisen suunnittelun periaatteet, palaamme esimerkkiraporttisivullemme ja sovellamme oppimaamme (vaiheittaisten ohjeiden avulla).  

### <a name="planning--choose-the-right-visual"></a>Suunnittelu – valitse oikea visualisointi
Samalla tavoin kuin on tärkeää suunnitella raportti ennen sen luomista, jokainen visualisointi vaatii myös suunnittelua.  Kysy itseltäsi ”Minkä tarinan yritän kertoa tämän visualisoinnin avulla?” Selvitä sitten, millainen visualisointityyppi kertoo tarinan parhaiten. Voit näyttää edistymisen myyntisyklissä palkkikaaviossa, mutta eikö vesiputous- tai suppilokaavio kertoisi sitä paremmin? Jos tarvitset tässä apua, lue tämän teknisen raportin viimeinen osio ”Visualisointityypit ja parhaat käytännöt”, jossa kuvataan joidenkin yleisempien tyyppien parhaita käytäntöjä.  Älä hämmästy, jos ensimmäinen valitsemasi visualisointityyppi ei loppujen lopuksi olekaan paras vaihtoehto.  Kokeile useampaa kuin yhtä visualisointityyppiä, jotta löydät parhaimmalta näyttävän vaihtoehdon.

Tutustu siihen, miten luokittaiset ja kvantitatiiviset tiedot eroavat toisistaan ja mitkä visualisointityypit toimivat parhaiten tietyntyyppisten tietojen kanssa. Kvantitatiivisiin tietoihin viitataan usein mittoina ja ne ovat yleensä numeerisia. Luokittaisiin tietoihin viitataan usein dimensioina ja niitä voidaan luokitella. Käsittelemme tätä tarkemmin jäljempänä osiossa ”Oikean mitan valinta”.

Vältä houkutusta käyttää muodikkaita tai monimutkaisempia visualisointityyppejä vain siksi, että raportti tekisi suuremman vaikutuksen. Tavoitteena on soveltaa kaikkein yksinkertaisinta vaihtoehtoa tarinasi välittämiseen. Tiedot voidaan välittää nopeasti vaakasuuntaisten palkkikaavioiden ja yksinkertaisten viivakaavioiden avulla.  Ne ovat tuttuja ja helppokäyttöisiä, ja useimmat lukijat pystyvät tulkitsemaan ne vaivattomasti.  Lisäksi etuna on myös se, että useimmat lukevat vasemmalta oikealla ja ylhäältä alas. Nämä kaksi kaaviotyyppiä voidaan siten käydä läpi ja ymmärtää nopeasti.

Onko visualisointia vieritettävä tarinan kertomiseksi? Jos mahdollista, vältä vieritystä.  Kokeile käyttää suodattimia ja hierarkioita/porausta. Jos ne eivät poista vierityspalkkia, harkitse erilaista visualisointityyppiä. Jos et pysty poistamaan vieritystä, vaakasuora vieritys on parempi vaihtoehto kuin pystysuora vieritys.

Vaikka valitsisit ehdottomasti parhaimman visualisoinnin tarinalle, saatat kuitenkin tarvita apua tarinan kertomiseen.  Tässä vaiheessa voit käyttää selitteitä, otsikkoja, valikkoja, värejä ja kokoja. Käsittelemme näitä rakenne-elementtejä myöhemmin osiossa ”Rakenne-elementit”.

### <a name="choose-the-right-measure"></a>Valitse oikea mitta
Onko visualisoinnin avulla kerrottu tarina kiinnostava? Onko sillä merkitystä?  Älä luo visualisointeja turhaan. Ajattelit ehkä, että tiedot kertovat kiinnostavan tarina, mutta näin ei olekaan. Älä pelkää aloittaa alusta ja etsiä kiinnostavampaa tarinaa. Tai ehkä tarina on olemassa, mutta sitä on mitattava eri tavalla.

Oletetaan esimerkiksi, että haluat mitata myyntiesimiestesi onnistumista. Mitä mittaa käyttäisit tähän tehtävään?  Pitäisitkö mittapuuna parasta kokonaismyyntiä tai kokonaistuottoa, kasvua viime vuoteen verrattuna tai suorituskykyä verrattuna kohdetavoitteeseen? Myyjänä toimiva Sirkka on saavuttanut suurimman tuoton, ja jos näytät kokonaistuoton myyjän mukaan palkkikaaviossa, hän saattaa näyttää rokkitähdeltä verrattuna muihin myyjiin.  Mutta jos Sirkan myyntikustannukset (kuten matka-, toimitus- ja valmistuskulut) ovat korkeat, pelkkä myynnin tarkasteleminen ei kerro parasta tarinaa.

#### <a name="reflect-realitydont-distort-reality"></a>Heijasta todellisuutta / älä vääristele totuutta
On mahdollista luoda visualisointi, joka vääristelee totuutta. Eräällä verkkosivustolla tietojen tehokäyttäjät jakavat näitä ”huonoja” visualisointeja. Kommenteissa tulee yleisesti esiin pettymys yritykseen, joka loi ja jakoi tämän visualisoinnin.  Se välittää viestin siitä, ettei tähän yritykseen voi luottaa.

Luo siis visualisointeja, jotka eivät tarkoituksella vääristele todellisuutta ja joita ei ole manipuloitu. Voit näin kertoa tarinan, jonka haluat niiden avulla välittää.  Tässä on esimerkki:

![](media/power-bi-visualization-best-practices/corp-success-distorted.png)

**Kuva 22:    Vääristellyn todellisuuden kaavio**

Tässä esimerkissä näyttäisi siltä, että neljän yrityksen välillä on suuri ero ja että CorpB pärjää selvästi paremmin kuin kolme muuta yritystä.  Huomaa kuitenkin, että X-akseli ei ala nollasta ja että yritysten välisiin eroihin liittyy todennäköisesti virhemarginaali.  Tässä ovat samat tiedot, kun X-akseli alkaa nollasta.

![](media/power-bi-visualization-best-practices/corp-success.png)

**Kuva 23:    Realistinen kaavio**

Lukijat odottavat ja usein olettavat, että X-akseli alkaa nollasta. Jos et halua aloittaa nollasta, tee se siten, etteivät tulokset vääristy. Harkitse myös visuaalisen vihjeen tai tekstiruudun lisäämistä, jotta osoitat poikkeavasi normista.  

### <a name="design-elements"></a>Rakenne-elementit
Kun olet valinnut tyypin sekä mitannut ja luonut visualisoinnin, on aika hienosäätää ulkoasua mahdollisimman hyväksi.  Tässä osiossa käsitellään seuraavia seikkoja:

* Asettelu, tila ja koko
* Teksti-elementit: selitteet, huomautukset, valikot, otsikot
* Lajittelu
* Visuaalinen vuorovaikutus
* Väri

#### <a name="tweaking-visuals-for-best-use-of-space"></a>Visualisointien sovittaminen parasta tilankäyttöä varten
Jos yritä mahduttaa useita kaavioita raporttiin, tietojen käsinkirjoitussuhteen maksimointi auttaa tuomaan esiin tietojen välittämän tarinan. Kuten aiemmin mainittiin, Edward Tufte huomautti tiedoista käsinkirjoitukseen -suhteesta: tavoitteena on poistaa kaaviosta mahdollisimman monta merkintää heikentämättä lukijan kykyä tulkita tietoja.

Alla olevassa ensimmäisessä kaavioryhmässä on toistuvia akselin selitteitä (Jan 2014, Apr 2014 jne.) ja otsikkoja (”by Date”). Kunkin kaavion otsikot vaativat myös erillisen vaakasuuntaisen tilan jokaisessa kaaviossa. Kun poistamme kaavion otsikot ja otamme käyttöön yksittäiset akselin selitteet, voimme poistaa hieman tekstiä ja käyttää yleistä tilaa paremmin. Teksti supistuu entisestään ja tiedoille saadaan lisää tilaa, kun poistamme akselin selitteet yläreunan kahdesta kaaviosta.

Jos haluat korostaa tiettyjä ajanjaksoja, voit piirtää viivoja tai suorakulmioita kaikkien kaavioiden taakse. Tällä tavoin katse ohjautuu ylös ja alas vertailun helpottamiseksi.

![](media/power-bi-visualization-best-practices/power-bi-multiples-before.png)

**Kuva 24:    Ennen**

![](media/power-bi-visualization-best-practices/power-bi-multiples-after.png)

**Kuva 25:    Jälkeen**

**Ota akselin otsikot käyttöön tai poista ne käytöstä**

Valitse visualisointi, jotta se on aktiivinen, ja avaa muotoiluruutu. Laajenna **X-akselin** tai **Y-akselin** vaihtoehtoja ja vedä **otsikon** liukusäädin päälle tai pois.

![](media/power-bi-visualization-best-practices/power-bi-axis-titles.png)

**Kuva 26:    Ota akselin otsikot käyttöön tai poista ne käytöstä**

**Ota akselin selitteet käyttöön tai poista ne käytöstä**

Valitse visualisointi, jotta se on aktiivinen, ja avaa muotoiluruutu. **X-akselin** ja **Y-akselin** vieressä on liukusäätimet.  Vedä liukusäädintä, jotta voit ottaa akselin selitteet käyttöön tai poistaa ne käytöstä.

![](media/power-bi-visualization-best-practices/power-bi-axis-labels.png)

**Kuva 27: Ota akselin selitteet käyttöön tai poista ne käytöstä**

> [!TIP]
> Saatat ehkä poistaa Y-akselin selitteet käytöstä tilanteessa, jossa **tietoselitteet** on otettu käyttöön.
> 
> 

**Poista visualisoinnit otsikot**

Valitse visualisointi, jotta se on aktiivinen, ja avaa muotoiluruutu. Poista **otsikon** liukusäädin käytöstä.

![](media/power-bi-visualization-best-practices/power-bi-title-off.png)

**Kuva 28:    Poista otsikot visualisoinneista**

Mieti, miten lukijat tarkastelevat raporttia, ja varmista, että visualisoinnit ja tekstit ovat riittävän leveitä ja tummia luettaviksi. Jos sinulla on suhteellisesti suurempi visualisointi sivulla, lukijat voivat olettaa, että kyse on tärkeimmästä asiasta. Lisää riittävästi tilaa visualisointien välille, jotta raporttisi ei näytä sekavalta ja epäselvältä.  Tasaa visualisoinnit, jotta ohjaat lukijoiden katseen oikeaan paikkaan.

**Visualisoinnin koon muuttaminen**

Valitse visualisointi, jotta se on aktiivinen. Voit muuttaa kokoa tarttumalla yhdestä kahvasta ja vetämällä sitä.

![](media/power-bi-visualization-best-practices/power-bi-drag-handles.png)

**Kuva 29: Muuta visualisoinnin kokoa**

**Visualisoinnin siirtäminen**

Valitse visualisointi, jotta se on aktiivinen. Valitse visualisoinnin yläreunan keskellä oleva tartuntapalkki, pidä se alhaalla ja vedä visualisointi uuteen sijaintiinsa.

![](media/power-bi-visualization-best-practices/power-bi-move.png)

**Kuva 30: Siirrä visualisointia**

#### <a name="titles-and-labels-that-are-part-of-the-visualizations"></a>Otsikot ja selitteet, jotka ovat osa visualisointeja
Varmista, että otsikot ja selitteet ovat luettavia ja selkeitä. Otsikoissa ja selitteissä olevan tekstin koon on oltava optimaalinen ja värien on erotuttava selvästi (esimerkiksi musta harmaan sijasta). Muista lukea tyylioppaamme (katso edellä oleva ”Teksti”-osio). Rajoita värien ja kokojen määrää -- jos kokoja ja värejä on liikaa, sivu näyttää ahtaalta ja sekavalta.  Harkitse saman fonttivärin ja -koon käyttöä raportin kaikkien visualisointien otsikoissa ja valitse sama tasaus raporttisivun kaikille otsikoille.  

**Muotoiluruutu**

Valitse kullekin jäljempänä luetelluille muotoilusäädöille maalaustelan kuvake, jotta voit avata Muotoilu-ruudun.

![](media/power-bi-visualization-best-practices/power-bi-paintbrush.png)

**Kuva 31: Avaa Muotoilu-ruutu**

Valitse sitten säädettävä visuaalinen elementti ja varmista, että se on käytössä. Esimerkkejä visuaalisista elementeistä ovat seuraavat: **X-akseli**, **Y-akseli**, **otsikko**, **arvopisteen otsikot** ja **selite**. Alla olevassa esimerkissä näytetään **Otsikko**-elementti.

![](media/power-bi-visualization-best-practices/power-bi-title-formatting.png)

**Kuva 32: Muotoile visuaalista otsikkoa**

**Määritä tekstin koko**

Tekstin kokoa voidaan säätää otsikoille ja arvopisteen otsikoille, mutta ei X- tai Y-akseleille tai kuvateksteille.  Kun on kyse nimenomaan arvopisteen otsikoista, kokeile **näyttöyksiköitä** ja erilaisia **desimaaleja**, kunnes löydät optimaalisen tietotason raportin näyttämiseksi.   

**Määritä tekstin tasaus**

Otsikko voidaan tasata vasemmalle, oikealle ja keskelle.  Valitse niistä yksi ja sovella tätä samaa asetusta sivun kaikkiin visualisointeihin.  

**Määritä tekstin sijainti**

Tekstin sijaintia voidaan säätää joillekin Y-akseleille ja kuvatekstille.   Valitsitpa näistä minkä tahansa, toimi samalla tavoin muiden Y-akseleiden ja sivun kaikkien muiden kuvatekstien kanssa.

**Määritä otsikon ja selitteen pituus**

Säädä otsikoiden, akselin otsikoiden, arvopisteen otsikoiden ja kuvatekstien pituutta. Jos haluat näyttää jonkin näistä elementeistä, voit pituutta (ja tekstin kokoa) säätämällä varmistaa, ettei mitään tekstiä katkaista. Käytä **otsikolle** ja **kuvatekstille** asetusta **Otsikon teksti**. Kirjoita tähän todellinen otsikko, joka näkyy visualisoinnissa. Käytä **X-akselille** ja **Y-akselille** asetusta **Tyyli**, ja valitse se avattavasta valikosta. Käytä **arvopisteen otsikoille** asetusta **Näyttö** ja **Desimaali**. Valitse avattavan **Näyttö**-valikon avulla mittayksiköt: miljoonat, tuhannet, ei mitään, automaattinen jne. Kerro Power BI:lle **Desimaali**-kentän avulla näytettävien desimaalien määrä.

**Määritä tekstin väri**

Tekstin väriä voidaan mukauttaa otsikoille, akseleille ja arvopisteen otsikoille.  

#### <a name="titles-and-labels-that-are-not-part-of-the-visualizations"></a>Otsikot ja selitteet, jotka eivät ole osa visualisointeja
Käsittelimme tässä raportissa aiemmin tekstiruutujen lisäämistä raporttisivuille. Joskus visualisointien otsikot eivät riitä kertomaan tarinaa.  Voit lisätä tekstiruutuja, jos haluat välittää raportin lukijoille lisätietoja.  
Jotta raporttisivu ei näyttäisi liian sekavalta tai ahtaalta, käytä johdonmukaisesti tekstiruudun fontteja, kokoja, värejä ja tasausta. Jotta voit mukauttaa tekstiruudussa olevaa tekstiä, voit tuoda muotoiluvalikon näkyviin valitsemalla tekstiruudun.

![](media/power-bi-visualization-best-practices/power-bi-text-box-edit.png)

**Kuva 33: Muotoile tekstiruudussa käytettävää fonttia**

#### <a name="sorting"></a>Lajittelu
Voit tuoda merkitykselliset tiedot nopeammin esiin määrittämällä visualisointien lajittelun. Kun lajittelet esimerkiksi palkkikaaviot laskevassa tai nousevassa järjestyksessä palkeissa olevan arvon mukaan, voit nopeasti näyttää tärkeät lisätiedot tilaa käyttämättä.

Jos haluat lajitella kaavion, valitse kolme pistettä (...) kaavion oikeasta yläkulmasta, valitse **Lajittele** ja valitse kenttä, jonka mukaan haluat lajitella, ja suunta. Lisätietoja on artikkelissa [Visualisoinnin lajittelutavan muuttaminen](power-bi-report-change-sort.md).

#### <a name="chart-interaction-and-interplay"></a>Kaavioiden välinen vuorovaikutus
Yksi Power BI:n kiinnostavimmista ominaisuuksista on kyky muokata tapaa, jolla kaaviot toimivat keskenään vuorovaikutuksessa.  Kaavioiden rajat on oletusarvoisesti korostettu: kun valitset tietopisteen, muiden kaavioiden liitännäiset tiedot korostetaan ja liittymättömät tiedot himmennetään. Voit ohittaa tämän toiminnon käyttämällä mitä tahansa kaaviota todellisena suodattimena, mikä säästää sivulla olevaa tilaa. Valitse tätä varten **Visuaaliset vuorovaikutukset** valikkopalkista.

![](media/power-bi-visualization-best-practices/power-bi-visual-interactions.png)

**Kuva 34: Visuaaliset vuorovaikutukset**

Päätä sitten sivulla olevan kunkin visualisoinnin osalta, haluatko valita visualisoinnin suodatusta tai korostamista varten, tai olla tekemättä mitään. Kaikkia visualisointeja ei voida korostaa, eikä niihin voida käyttää korostuksen ohjausta. Lisätietoja on artikkelissa [Visuaaliset vuorovaikutukset Power BI:ssä](service-reports-visual-interactions.md).

> [!TIP]
> Power BI:n uusille käyttäjille tämä kyky napsauttaa ja käsitellä raportteja, ei ole ehkä heti selkeää. Kun lisäät tekstiruutuja, heidän on helpompi ymmärtää, mitä he voivat napsauttaa merkityksellisten lisätietojen saamiseksi.
> 
> 

#### <a name="the-use-of-color-in-visuals"></a>Värien käyttäminen visualisoinneissa
Käsittelimme tässä asiakirjassa aiemmin, miten tärkeää on laatia suunnitelma värien käytöstä raportissa. Tässä osiossa toistetaan hieman samaa asiaa, mutta keskitytään pääasiassa siihen, miten värejä käytetään yksittäisissä visualisoinneissa. Tässä yhteydessä sovelletaan samoja periaatteita: voit värin avulla sitoa raportin yhteen, painottaa tärkeitä tietoja ja parantaa lukijan ymmärrystä visualisoinnista. Liian monet värit ovat häiritseviä ja lukijan on vaikea ymmärtää, mitä osiota hänen pitäisi tarkastella. Älä tingi ymmärryksestä kauneuden vuoksi. Lisää väriä vain, jos se parantaa ymmärtämistä.

> [!TIP]
> Tunne yleisösi ja kaikki siihen liittyvät värisäännöt.  Esimerkiksi Yhdysvalloissa vihreä tarkoittaa yleensä ”hyvää” asiaa ja punainen ”huonoa” asiaa.
> 
> 

Tämä ohjeaihe on jaettu seuraaviin osiin:

1. Tietojen väri
2. Arvopisteen otsikon väri
3. Luokittaisten arvojen väri
4. Numeeristen arvojen väri

**Mielenkiintoisten tietojen korostaminen värien avulla**

Helpoin tapa käyttää väriä on muuttaa yhden tai useamman tietopisteen väriä, jotta huomio kiinnittyy tähän tietopisteeseen. Tässä esimerkissä väri muuttuu, kun olympialaiset siirretään neljän vuoden jaksosta kahden vuoden jaksoksi kesä- ja talvikisojen vaihtelun vuoksi.

![](media/power-bi-visualization-best-practices/power-bi-data-color.png)

**Kuva 35:    Käytä väriä tarinan kertomiseen**

Voit muuttaa tietopisteen värejä muotoiluruudun **Tietojen värit** -välilehdessä. Jos haluat mukauttaa kutakin tietopistettä erikseen, varmista, että **Näytä kaikki** -asetus on käytössä.

![](media/power-bi-visualization-best-practices/power-bi-colors.png)

**Kuva 36: Määritä tietopisteen värit**

> [!NOTE]
> Power BI soveltaa oletusarvoista teemaa raportin visualisointeihin.  Teemavärit valitaan monipuolisuuden ja kontrastin lisäämiseksi. Jos haluat poiketa oletusarvoisesta teemavalikoimasta, valitse **Mukautettu väri**.
> 
> 

![](media/power-bi-visualization-best-practices/power-bi-custom-color.png)

**Kuva 37: Valitse mukautettu väri**

Voit Power BI Desktopissa jopa korostaa poikkeavia arvoja tai rivin osiota toisen sarjan avulla:

![](media/power-bi-visualization-best-practices/power-bi-outliers.png)

**Kuva 38:    Desktopin käyttäminen poikkeavien arvojen korostamiseksi**

Tässä ”Poikkeavat arvot” -sarja on olemassa vain, kun elokuun keskilämpötila laskee alle 60. Tämä tehtiin luomalla laskettu DAX-sarake seuraavalla kaavalla:

Poikkeavat arvot = if(Editions[Temp]<60, Editions[Temp], BLANK())

Tässä esimerkissä on kolme poikkeavaa arvoa: 1952, 1956 ja 2000.

**Selitteiden ja otsikoiden värit**

Kun tarkastelet kaikkia käytettävissä olevia muotoiluvaihtoehtoja, löydät useita eri paikkoja lisätä värejä otsikoihin ja kuvateksteihin. Voit esimerkiksi muuttaa arvopisteen otsikoiden ja akselin otsikoiden väriä. Toimi varovasti.  Visualisoinnin otsikoille käytetään yleensä yhtä väriä.  Kuten tämän asiakirjan kaikkien ohjeiden kanssa, joissakin tilanteissa on syytä ”rikkoa sääntöä”. Jos aiot toimia tällä tavoin, varmista, että siihen on hyvä syy.

**Luokittaisten arvojen väri**

Sarjan kaavioiden kuvatekstissä on yleensä luokittainen arvo. Esimerkiksi alla olevan kuvatekstin kukin väri edustaa eri maan/alueen luokkaa.

![](media/power-bi-visualization-best-practices/power-bi-bubble-color.png)

**Kuva 39: Sovelletut oletusvärit**

Power BI:n käyttämät oletusvärit on valittu siten, että luokittaisten arvojen välillä on hyvä värinerotus ja ne on helppo erottaa toisistaan. Näitä värejä muutetaan toisinaan vastaamaan tiettyä yrityksen mallia, mutta se voi aiheuttaa ongelmia.

![](media/power-bi-visualization-best-practices/power-bi-bubble-color2.png)

**Kuva 40: Väri, jota sovelletaan yhden värin sävyinä**

Tähän visualisointiin on valittu yksi sävy ja värin intensiteetti on vaihteleva. Sen vuoksi se antaa väärän käsityksen luokkien välisestä järjestyksestä. Sen mukaan tummat kuplat ovat mittakaavassa korkeammalla tai matalammalla kuin vaaleammat sävyt. Aakkosjärjestystä lukuun ottamatta tämän kaltaisessa luokittaisessa arvossa ei ole yleensä mitään luontaista järjestystä.
Voit vaihtaa oletusvärejä avaamalla muotoiluruudun ja valitsemalla **Tietojen värit**.

**Numeeristen arvojen värit**

Jos kentillä on luontainen järjestys ja numeerinen arvo, voit myös värittää arvopisteet arvon mukaan. Tästä voi olla hyötyä sen näyttämiseksi, miten arvot on jaettu tiedoissa. Sen avulla myös kaksi muuttujaa voidaan näyttää yhdessä kaaviossa. Tässä esimerkissä tehdään esimerkiksi selväksi, että vaikka Kiina on voittanut eniten mitaleja, Japani ja Thaimaa ovat osallistuneet useampiin olympialaisiin.

![](media/power-bi-visualization-best-practices/power-bi-saturation.png)

**Kuva 41: Väritä arvopisteet arvon mukaan**

Voit luoda tämän kaavion lisäämällä arvon Värin kylläisyys -kenttään ja säätämällä sitten näitä värejä muotoiluruudussa.

![](media/power-bi-visualization-best-practices/power-bi-saturation2.png)

**Kuva 42: Lisää Värin kylläisyys -kenttä**

![](media/power-bi-visualization-best-practices/power-bi-color-controls.png)

**Kuva 43: Säädä kylläisyydessä käytettyjä värejä**

Värin avulla voidaan myös korostaa keskitettyä arvoa ympäröivää varianssia. Esimerkiksi positiiviset arvot voidaan värittää vihreiksi ja negatiiviset arvot punaisiksi. Ota huomioon kulttuuriset erot, kun määrität värejä positiivisille tai negatiivisille arvoille; kaikissa kulttuureissa punainen väri ei välttämättä tarkoita huonoa ja vihreä hyvää!

![](media/power-bi-visualization-best-practices/power-bi-color.png)

**Kuva 44:    Keskitettyä arvoa ympäröivän varianssin korostaminen värin avulla**
 

### <a name="principles-of-visual-design--applied-to-example-report-page"></a>Visuaalisen suunnittelun periaatteet – sovellettuna esimerkkiraporttisivuun
Tartutaanpa nyt edellä käsiteltyihin visuaalisiin periaatteisiin ja sovelletaan niitä esimerkkiraporttiimme.

Ennen

![](media/power-bi-visualization-best-practices/power-bi-example5a.png)

**Kuva 45:    Esimerkkiraporttimme (ennen)**

Jälkeen

![](media/power-bi-visualization-best-practices/power-bi-example6anew.png)

**Kuva 46: Esimerkkiraporttimme (jälkeen)**

#### <a name="what-did-we-do"></a>Mitä teimme?
1. Osittaja: tyhjät kohdat poistettiin osittajista lisäämällä sivutason suodatin ja valitsemalla vain kulta, hopea ja pronssi. **Ohjausobjektin valinta** -tilaksi muutettiin pois käytöstä kohteille **Valitse yksi** ja **Valitse kaikki**.
2. Kupla: kuvatekstissä on niin monta kohdetta, että ne vierivät ulos näytöltä.  Kuvateksti poistettiin ja otettiin käyttöön sen sijaan **Luokan selitteet**. Tiedot tulevat näkyviin, kun asiakkaat liikuttavat hiirtä kuplien päällä. Otsikkoa lyhennettiin ja poistettiin ”maan/alueen mukaan”, koska se on itsestäänselvää. Akselin otsikot otettiin käyttöön kummallekin, jotta kaaviota on helpompi ymmärtää.
3. Täytetty kartta: **tietojen värejä** muutettiin, jotta ne erottuvat paremmin. Otettiin käyttöön **Eriytyvä** ja **Minimi**-asetukseksi määritettiin vaaleanpunainen ja **Maksimi**-asetukseksi punainen.
4. Puukartta: poistettiin suodatin, joka oli määritetty vain Yhdysvalloille. **Arvopisteen otsikot** määritettiin yhteen desimaaliin. Visualisoinnissa käytettiin Luokka-kenttää, mikä ei ole kovin hyödyllistä, koska se on lähes aina 33 % (kulta/hopea/pronssi).  Valittiin erilainen kiinnostavampi kenttä, sukupuoli. Vesilajit muutettiin sinisiksi ja yleisurheilulajit harmaiksi.
5. Yläosan palkkikaavio: otsikkoa lyhennettiin, poistettiin arvopisteen otsikot, selitteen otsikko poistettiin käytöstä. Otsikon sanajärjestystä muutettiin sopimaan alla olevaan kaavioon.
6. Alaosan palkkikaavio: lajiteltiin nousevan vuoden mukaan vastaamaan yllä olevaa kaaviota. Muutettiin värejä vastaamaan luokkaa. Muutettiin otsikkoa. Poistettiin kuvateksti käytöstä, jotta tiedoille jää enemmän tilaa. Otettiin käyttöön tietopisteen otsikot, jotka eivät näy raportissa (koska visualisointi on liian pieni, jotta selitteitä voidaan lukea), mutta jotka tulevat näkyviin, kun visualisointi avataan Kohdistus-tilassa. [Lisätietoja Kohdistus-tilasta](service-focus-mode.md). **Työkaluvihjeisiin** lisättiin tapahtumien lukumäärä (erillinen), joten kun hiirtä liikutetaan pinotun pylvään yläpuolella, työkaluvihjeet kertovat nyt myös, kuinka monta kilpailua järjestettiin tänä vuonna.
7. Visuaaliset vuorovaikutukset: vuorovaikutukset poistettiin käytöstä kummallekin kortille, koska haluan niiden näyttävän aina pelien ja urheilulajien kokonaismäärän.

## <a name="visual-types-and-best-practices"></a>Visualisointityypit ja parhaat käytännöt
Power BI:ssä on luontaisesti useita visualisointityyppejä.  Niiden lisäksi Microsoft ja Power BI -yhteisö tarjoavat mukautettuja visualisointeja, joten visualisointien kokonaismäärä on liian suuri tässä lueteltavaksi. Tarkastellaanpa kuitenkin joitakin useimmin käytettyjä alkuperäisiä visualisointityyppejä.  

### <a name="line-charts"></a>Viivakaaviot
![](media/power-bi-visualization-best-practices/power-bi-line-chartb.png)

Viivakaaviot ovat tehokas tapa tarkastella tietoja ajan kuluessa.  Kun tarkastelet tietoja taulukoissa, havaitset nopeasti huiput, notkot, syklit ja toimintatapamallit.  
Alla olevassa esimerkissä näytetään trendit, jotka koskevat annettujen mitalien lukumäärää ja nämä mitalit voittaneiden urheilijoiden lukumäärää.  

![](media/power-bi-visualization-best-practices/power-bi-line-chart.png)

**Kuva 47:    Viivakaaviot**

#### <a name="best-practices"></a>Parhaat käytännöt
* Kun tarkastelemme viivakaavioita, silmiin pistää ensiksi käyrän muoto.  Tämä tarkoittaa, että tarvitsemme X-akselia. Se tekee käyrästä mielekkään tällaisissa aika- tai jakeluluokissa.  Jos sijoitat X-akselille luokittaisia kenttiä, kuten tuotteen tai maantieteen, viivakaavio ei ole kiinnostava, koska käyrän muoto ei anna mitään merkityksellistä tietoa.
* Jos päätät sijoittaa useita kaavioita toinen toisensa ylä- ja alapuolella tällä tavoin, se helpottaa sarjojen vertailua tasaten X-akselin. Suodattimien avulla voit varmistaa, että näkyvissä on sama arvoalue.  Varmista esimerkiksi, että päivämääräalueet ovat samat,  kuten 1896–2012 kummassakin kaaviossa.
* Käytä koko tila.  Jos se on tietojen kannalta järkevää, määritä Y-akselin aloitus- ja lopetuspisteet, jotta voit poistaa tyhjän tilan kaavion ylä- ja alaosasta ja keskittyä todellisiin arvopisteisiin. Valitse tätä varten maalaustelan kuvake, jotta voit avata muotoiluruudun. Laajenna **Y-akselin** aluetta sekä määritä **aloitus**- ja **lopetus**pisteet.
  
  ![](media/power-bi-visualization-best-practices/power-bi-start-end.png)
  
  **Kuva 48: Määritä aloitus- ja lopetuspisteet**
* Aloitus- ja lopetuspisteet on nimenomaisesti määritettävä myös silloin, kun vertailet kahta tai useampaa kaaviota samalla sivulla käyttämällä samaa Y-akselin kenttää.  Jos esimerkiksi tarkastelet kumulatiivista tapahtumien lukumäärää ja Ison-Britannian lukumäärät ovat välillä 1–70 ja Australian 1–12, kaksi viivakaaviota näyttää hyvin erilaiset Y-akselit (kuva x). Tämä vaikeuttaa vertailua yhdellä silmäyksellä. Määritä kaaviot käyttämään sen sijaan samaa Y-akselin aluetta (kuva x).
  
  ![](media/power-bi-visualization-best-practices/power-bi-line-chart2.png)
  
  **Kuva 49: Viivakaaviot, joissa on erilaiset Y-akselit**
  
  ![](media/power-bi-visualization-best-practices/power-bi-line-chart3.png)
  
  **Kuva 50: Viivakaaviot, joissa on samat Y-akselit**

Lisätietoja:

* [X- ja Y-akselien mukauttaminen](power-bi-visualization-customize-x-axis-and-y-axis.md)
* [Viivakaaviot ja epäsäännölliset välit](http://www.perceptualedge.com/articles/visual_business_intelligence/line_graphs_and_irregular_intervals.pdf)
* [Viivakaaviot 101](http://www.columnfivemedia.com/data-visualization-101-line-charts)

### <a name="barcolumn-charts"></a>Palkki-/pylväskaaviot
![](media/power-bi-visualization-best-practices/power-bi-bar-chart.png)

Jos viivakaavioita käytetään yleensä tietojen tarkastelemiseen ajan kuluessa, palkkikaavioita käytetään tietyn arvon tarkastelemiseen eri luokissa.  Jos palkit lajitellaan luvun perusteella, näet välittömästi tärkeimmät arvot ja jakelun.  Vaakasuuntaiset palkkikaaviot toimivat hyvin pidemmissä selitteissä.  

![](media/power-bi-visualization-best-practices/power-bi-horizontal-scroll.png)

**Kuva 51: Vaakasuuntainen palkkikaavio**

#### <a name="best-practices"></a>Parhaat käytännöt
* Näytä arvopisteen selitteet arvoille.  Tämä helpottaa erityisten arvojen määrittämistä. Avaa tätä varten muotoiluruutu ja ota **arvopisteen selitteet** käyttöön.
  
  ![](media/power-bi-visualization-best-practices/power-bi-data-labels.png)
  
  **Kuva 52: Arvopisteen selitteiden ottaminen käyttöön**
* Edellä oleva palkkikaavio on todella kätevä verrattaessa yhtä mittaa monen **yksittäisen pisteessä kanssa ajalla mitattuna**.  Samalla kun edellä oleva viivakaavio näytti trendin ajan kuluessa, palkkikaavio näyttää trendin yhdelle luokalle tiettynä ajankohtana.  Voimme yhdellä silmäyksellä havaita, että palkkiokaavion mukaan Espanjan työttömyysaste on yksi maailman huonoimmista eli 25 %.
* Kun koko palkki-/pylväskaavio ei mahdu varattuun tilaan, Power BI lisää vierityspalkkeja. Kun se on mahdollista ja järkevää, jäsennä visualisointi ja raportti näyttämään koko kaavio, jotta lukija saa yleiskäsityksen koko jakautumisesta.  Valitettavasti tämä ei ole mahdollista esimerkissämme ympäri maailmaa sijaitsevien maiden suuren lukumäärän vuoksi.
  
  Yksi keino rajoittaa sisällytettäviä arvoja on käyttää suodatinta. Voit esimerkiksi lisätä visuaalisen tason suodattimen, joka näyttää maan vain, jos työttömyysaste on yli 20 prosenttia.
* Palkki- ja pylväskaavioita voidaan porata alaspäin (ja jälleen takaisin ylöspäin).  Tämä on kätevä tapa pakata lisätietoja visualisointiin ilman, että se vie tilaa.  Alla olevassa esimerkissä on hierarkia Alueet > Maat.  Kun kaksoisnapsautat aluepalkkia, poraat alaspäin maihin, jotka muodostavat tämän alueen.  Lisätietoja porauksesta on artikkelissa [Porautuminen alaspäin visualisoinnissa](power-bi-visualization-drill-down.md).
  
  ![](media/power-bi-visualization-best-practices/power-bi-drill.png)
  
  **Kuvassa 53: Porautuminen alaspäin**

Lisätietoja palkki- ja pylväskaavioista:

* [Palkkikaaviot 101](http://blog.newscred.com/article/data-visualization-101-bar-charts/3c53044d4add7c31e79a3f80128771f4?page=thankyou)
* [Tietojen visualisoinnin luettelo: palkkikaavio](http://www.datavizcatalogue.com/methods/bar_chart.html#.VYV-hY3bLJw)
* [Tietojen visualisoinnin luettelo: monijoukkokaavio](http://www.datavizcatalogue.com/methods/multiset_barchart.html#.VYV_gI3bLJw)

### <a name="stacked-barcolumn-charts"></a>Pinotut palkki-/pylväskaaviot
![](media/power-bi-visualization-best-practices/power-bi-stacked.png)

Lisää toinen dimensio palkki-/pylväskaavioihin pinoamalla eri luokkia palkissa tai pylväässä.  Kaavio näyttää nyt tietoja yleisestä trendistä (korkeuden/pituuden mukaan), mutta myös luokkien vaikutuksen tähän trendiin. Alla oleva kaavio näyttää huippujalkapallojoukkueen tulojen yleisen kasvun yli 6 miljardin vuonna 2014.

![](media/power-bi-visualization-best-practices/power-bi-deloite.png)

**Kuva 54: pinottu pylväskaavio**

Tämä pinottu pylväskaavio näyttää, että kokonaistulot ovat kasvaneet ajan kuluessa. Kaupalliset tulot - ja Lähetystulot-luokat ovat myös kasvaneet tasaisesti ajan kuluessa, mikä on lisännyt kokonaistuloja.  Tämän kaavion avulla ei ole kuitenkaan helppo vertailla sitä, mikä vaikutus kullakin kolmella luokalla on toinen toisiinsa. Miten Kaupalliset tulot -luokka on esimerkiksi kasvanut verrattuna Lähetystulot- tai Pelipäivän tulot -luokkaan?  Nämä tiedot olisi parempi esittää viivakaaviossa, joka auttaa visualisoimaan niitä.  

![](media/power-bi-visualization-best-practices/power-bi-deloite2.png)

**Kuva 55: Muuntaminen viivakaavioksi**

Tämän viivakaavion avulla on helpompi nähdä, että eniten ovat kasvaneet kaupalliset tulot, joita seuraavat lähetystulot ja pelipäivän tulot.

#### <a name="best-practices"></a>Parhaat käytännöt
* Samoin kuin sarakkeiden tai palkkien tapauksessa, voit valita vaaka- tai pystysuuntaisen näytön välillä.   Jos selitteet ovat pitkiä, kannattaa valita vaakasuuntainen näyttö, ja aikasarjatietojen tapauksessa pystysuuntainen näyttö.  
* Vältä pinottuja palkki-/pylväskaavioita, jos haluat näyttää trendien ja muiden mallien muuttumisen ajan kuluessa.  Tähän sopivat paljon paremmin muut kaaviot, kuten viivakaaviot.
* Jakautuminen voi myös perustua kokonaismäärään tai sen prosenttiosuuteen.  
* Kuten Few mainitsi *, pinotun palkin segmenttejä on vaikea vertailla. Jos segmentit on järjestetty vierekkäin ja kaikki kasvavat ylöspäin samasta perusviivasta, niiden korkeuksia on helppo vertailla. Tehtävä vaikeutuu, kun ne pinotaan toinen toisensa päälle. Sen lisäksi vaikka onkin varsin helppo nähdä, miten (tulot) muuttuvat kuukaudesta toiseen, on varsin vaikea nähdä, miten (tulot) muissa (luokissa) ovat muuttuneet*.  
* 100-prosentin pinotun kaaviot ovat hyvä valinta, kun prosenttiosuuksien yhteismäärä nousee 100:aan.  Seuraavassa esimerkissä näytetään luokan jakautuminen joukkueen mukaan.  Prosenttiosuudet ovat suhteellisia ja näyttävät yhdellä silmäyksellä mallit. Esimerkiksi Evertonin tulot ovat peräisin pääasiassa lähetyksistä (yli 70 %) kun taas PSG saa vain 20 % tuloistaan lähetyksistä.  Kun valitset vaakasuuntaisen näytön, joukkueen selitteet mahtuvat siihen paremmin ja näet helpommin tuottotyypin vaikutuksen.
  
  ![](media/power-bi-visualization-best-practices/power-bi-deloite3.png)
  
  **Kuva 56: Vaakasuuntainen pinottu kaavio**

Lisätietoja pinotuista kaavioista:

* [Tietojen visualisoinnin luettelo: pinotut pylväskaaviot](http://www.datavizcatalogue.com/methods/stacked_bar_graph.html#top)
* [Milloin kannattaa käyttää 100-prosentin pinottuja palkkikaavioita?](http://www.perceptualedge.com/blog/?p=2239)

### <a name="combo-barcolumn-charts"></a>Yhdistelmäpalkki-/pylväskaaviot
![](media/power-bi-visualization-best-practices/power-bi-combo.png)

Power BI:ssä pylväs- ja viivakaaviot voidaan yhdistää yhdistelmäkaavioksi. Vaihtoehtoja ovat seuraavat: viivakaavio ja pinottu pylväskaavio sekä viivakaavio ja lohkopylväskaavio. Voit säästää arvokasta piirtoalustatilaa yhdistämällä kaksi erillistä visualisointia yhdeksi kokonaisuudeksi.

Alla on kaksi tilannevedosta ennen ja jälkeen.  Ensimmäisellä sivulla on kaksi erillistä visualisointia: pylväskaavio, joka näyttää väestönkasvun ajan kuluessa ja viivakaavio, joka näyttää BKT:n ajan kuluessa. Nämä kaaviot sopivat hyvin yhdistelmäkaavioksi, koska niillä on sama X-akseli (vuosi) ja arvot (2002–2012).  Miksi et yhdistäisi niitä, jotta voit vertailla näitä kahta trendiä yhdessä visualisoinnissa?  Näiden kahden kaavion yhdistäminen nopeuttaa tietojen vertailua.

Uudella raporttisivulla on yksi visualisointi: viiva ja pinottu pylväskaavio. Olisimme yhtä helposti luoda viivan ja pinotun pylväskaavion.  Voimme nyt helpommin tarkastella kahden trendin välistä suhdetta.   Voimme nähdä, että väestö ja BKT noudattivat vuoteen 2008 asti samantapaista trendiä. Mutta vuodesta 2009 alkaen väestön kasvun tasaannuttua BKT on vaihdellut enemmän.  

![](media/power-bi-visualization-best-practices/power-bi-spain-line.png)

 **Kuva 57: Kahtena erillisenä kaaviona**

![](media/power-bi-visualization-best-practices/power-bi-spain-combo.png)

 **Kuva 58: Yhtenä yhdistelmäkaaviona**

#### <a name="best-practices"></a>Parhaat käytännöt
Yhdistelmäkaaviot toimivat parhaiten, kun molemmalla visualisoinnilla on vähintään yksi sama akseli.

Tarkkaile akseleitasi! Onko yhdistelmäkaaviota helppo lukea ja tulkita?  Vai käytetäänkö siinä erilaisia alueita ja arvoja? Jos pylväskaavion Y-akselin mittakaava on esimerkiksi paljon pienempi kuin viivakaavion Y-akselin mittakaava, yhdistelmäkaavio ei anna merkityksellisiä tietoja.  Huomaa esimerkiksi kolmas viiva (turkoosin värinen), joka kulkee alas pohjaan asti.

   ![](media/power-bi-visualization-best-practices/power-bi-dual-line.png)

   **Kuva 59: Epäonnistunut viivakaavio**

Yhdistelmäkaaviosta ei ole myöskään hyötyä, jos pylväskaavio ja viivakaavio käyttävät kahta erilaista mittaa, etkä luo kaksinkertaisia akseleita.  Esimerkiksi dollarit verrattuna prosentteihin. Muista sisällyttää kummatkin akselit, jotta lukija ymmärtää paremmin kaaviota. Voit myös harkita akselin otsikkojen lisäämistä.

Avaa tätä varten muotoiluruutu, laajenna **Y-akselia** ja ota  **Näytä toissijainen** käyttöön (jos se ei ole jo käytössä). Tätä asetusta on joskus vaikea löytää; laajenna **Y-akselia (sarake)** ja vieritä alaspäin, kunnes näet **Näytä toissijainen**. Ota myös Y-akselin (sarake) **Otsikko** ja Y-akselin (viiva) **Otsikko** käyttöön.

![](media/power-bi-visualization-best-practices/power-bi-show-secondary-new.png)

**Kuva 60: Toissijaisen akselin näyttäminen**

![](media/power-bi-visualization-best-practices/power-bi-combo-chart.png)

**Kuva 61: Yhdistelmäkaavion luominen sen sijaan**

* Hyödynnä kaksinkertaisia akseleita. Se on kätevä tapa vertailla useita mittoja, joilla on erilaisia arvoalueita. Se on myös kätevä tapa havainnollistaa kahden mitan välistä korrelaatiota yhdessä visualisoinnissa.

Lisätietoja:

* [Opetusohjelma: Yhdistelmäkaavio Power BI:ssä](power-bi-visualization-combo-chart.md)
* [Kaksoisskaalattujen akseleiden vaara visualisoinneissa](http://www.perceptualedge.com/articles/visual_business_intelligence/dual-scaled_axes.pdf)

### <a name="scatter-chart"></a>Pistekaavio
![](media/power-bi-visualization-best-practices/power-bi-scatter.png)

Toisinaan meillä voi olla useita muuttujia, jotka haluamme nähdä yhdessä. Pistekaavio voi tällöin olla hyvin kätevä keino yleiskuvan saamiseen.  Pistekaaviot näyttävät kahden (pistekaavio) tai kolmen (kuplakaavio) määrällisen mitan väliset suhteet.  Pistekaaviossa on aina kaksi arvoakselia, jotka näyttävät yhden numeerisen tietosarjan vaakasuuntaisella akselilla ja toisen numeerisen arvosarjan pystysuuntaisella akselilla. Kaaviossa näytetään arvopisteet numeerisen arvon X ja Y leikkauskohdassa yhdistämällä nämä kaksi arvoa yhdeksi arvopisteeksi. Nämä arvopisteet voidaan jakaa tasaisesti tai epätasaisesti vaakasuuntaiselle akselille tietojen mukaan.

Kuplakaaviossa arvopisteet korvataan kuplilla ja kuplan koko edustaa tietojen muuta dimensiota.

Alla olevassa Etelä-Amerikkaa koskevassa kuplakaaviossa verrataan toisiinsa asukaskohtaista BKT:tä (Y-akseli), BKT:n määrää (X-akseli) ja väestöä Etelä-Amerikan maan mukaan.  Kuplan koko edustaa tämän maan kokonaisasukaslukua. Brasilian asukasluku on suurin (kuplan koko) ja sillä on suurin osuus Etelä-Amerikan BKT:stä (se on selvästi pisimmällä X-akselilla).  Huomaa kuitenkin, että Uruguayn, Chilen ja Argentiinan asukaskohtainen BKT on korkeampi kuin Brasilian (selvästi ylempänä Y-akselilla).

![](media/power-bi-visualization-best-practices/power-bi-bubble.png)

**Kuva 62: Etelä-Amerikan BKT ja asukasluku kuplakaaviona**

Jos lisäät toistoakselin, voit pitää itseäsi Hans Roslingina ja kertoa tarinan ajan kuluessa (https://www.youtube.com/watch?v=PbaDBJWCeD4). Jos haluat lisätä toistoakselin, vedä päivä/aikakenttä **toistoakselille**.

#### <a name="best-practices"></a>Parhaat käytännöt
* Piste- ja kuplakaaviot ovat mainioita tarinankertojia. Ne eivät ole kuitenkaan yhtä hyödyllisiä tietojen tarkastelussa.  Stephen Few huomauttaa tästä alla olevassa kappaleessa *. Tämän lähestymistavan vahvuus näkyy silloin, kun sitä käytetään tarinan kertomiseen. Kun Rosling kertoo, mitä kaaviossa tapahtuu kun kuplat liikkuvat ympäriinsä ja niiden arvo muuttuu sen mukaan, mitä hän haluaa meille näyttää, tiedot heräävät henkiin. Animoidut kuplakaaviot sopivat kuitenkin selvästi huonommin omatoimiseen tietojen tarkasteluun ja tulkintaan. Rosling ei epäilemättä käytä tätä menetelmää uusiin tarinoihin vaan kertoo vain tunnettuja tarinoita. Emme voi nähdä useampaa kuin yhden kuplan kerralla, koska ne liikkuvat ympäriinsä, joten meidän on pakko toistaa animaatio useamman kerran käsityksen saamiseksi tilanteesta. Voimme lisätä merkintöjä kuplien valitsemiseksi ja nähdä sitten näiden kuplien täydelliset polut. Jos merkintöjä käytetään useampaan kuin pariin kuplaan, kaaviosta tulee nopeasti sekava. Haluan lähinnä osoittaa, ettei tämä ole paras keino näyttää näitä tietoja tarkastelua ja analyysiä varten.*
* X- ja Y-akseleiden otsikkojen lisääminen auttaa kertomaan tarinan.  Etenkin kuplakaavioissa on useita osia ja otsikot auttavat lukijoita ymmärtämään visualisoinnin.
* Visualisointia on helpompi tulkita, jos lisäät arvopisteen otsikoita.  Erityisesti jos kuplakaavion selitteessä on useita kohteita, samoja värejä voi olla hankala erottaa.  Yllä olevassa visualisoinnissa Surinamen, Kolumbian ja Ecuadorin kuvatekstin värit ovat hyvin samanlaiset.
* Loitko pistekaavion ja näitkö vain yhden arvopisteen, joka yhdistää kaikki arvot X- ja Y-akseleille? Vai yhdistääkö kaavio kaikki arvot yhdelle vaaka- tai pystysuuntaiselle viivalle?  Voit korjata tämän lisäämällä kentän **Tiedot**-alueelle ja kertoa näin Power BI:lle, miten arvot ryhmitetään. Kentän on oltava yksilöllinen jokaiselle arvopisteelle, jonka haluat piirtää. Löydät ohjeita artikkelista [Power BI:n pistekaavion ja kuplakaavion opetusohjelma](power-bi-visualization-scatter.md).

### <a name="tree-map-charts"></a>Puukarttakaaviot
![](media/power-bi-visualization-best-practices/power-bi-treemap.png)

Puukartoista voi olla paljon hyötyä yleiskäsityksen saamiseksi kokonaisuuden eri osien koosta etenkin, kun ne voidaan ryhmitellä luokittain.  Kun yritän ymmärtää uutta liiketoimintaa, tärkeimpien osien puukartasta voi olla paljon hyötyä yleisen jakautumisen hahmottamiseksi.

Alla olevassa ensimmäisessä kaaviossa näet heti, että Brasilian osuus on noin puolet Etelä-Amerikan BKT:stä ja että Venezuela ja Argentiina ovat karkeasti ottaen saman kokoisia.

Jos haluat saada laajemman kontekstin ja sinulla on käsitys tärkeimpien osallistuvien maiden vaikutuksesta, voit luoda visuaalisia hierarkioita siten, että luokan jäsenet (maat) on sijoitettu alueiden sisäpuolelle. Toinen puukartta antaa meille käsityksen ensinnäkin alueiden suhteellisesta koosta. Näemme sitten jokaisella alueella, mitkä yksittäiset maat osallistuvat eniten. Näemme, että täällä on kolme valtavaa aluetta (Eurooppa, Aasia ja Pohjois-Amerikka). Voimme myös nähdä niiden sisäpuolella helposti tärkeimmät maat/alueet.

Puukartan pääasiallinen rajoitus on sen rajallinen kyky vertailla erilaisia suorakulmioita tärkeimpien suorakulmioiden lisäksi.  Tämä kaavio soveltuu hyvin yleiskäsityksen antamiseen, mutta pylväs- ja palkkikaaviot ovat luultavasti parempi valinta, jos haluat tarkemman käsityksen eri osien suhteellisesta koosta.
  Ensimmäinen puukartta antaa esimerkiksi laajemman käsityksen BKT-koon järjestyksestä, mutta siinä on vaikea tunnistaa erityisiä eroja maiden väillä etenkin pienemmissä ruuduissa, joita ei ole otsikoitu. Näiden tietojen tapauksessa, kun vertaillaan yksittäistä ryhmittelyä, olisi ehkä parempi valita palkki- tai pylväskaavio.

![](media/power-bi-visualization-best-practices/power-bi-treemap3.png)

**Kuva 63: Etelä-Amerikan BKT:n vertailu puukarttana**

Olemme nyt lisänneet toisen tietotason eli alueen. Voimme täällä nähdä BKT:n yleisen jakautumisen alueittain sekä suhteellisen vaikutuksen alueiden sisällä. Muista, että jos toimit näin muun kuin yhteenlaskettavan mitan (kuten keskiarvojen) kanssa, tietojen summa ei ehkä edusta yhdistetyn tason todellista arvoa.

![](media/power-bi-visualization-best-practices/power-bi-treemap2.png)

**Kuva 64: BKT alueittain ja maittain puukarttana**

Löydät lisätietoja puukartoista napsauttamalla alla olevia linkkejä.

* [Puukarttojen yleiskatsaus](http://www.perceptualedge.com/articles/b-eye/treemaps.pdf)
* [Tietojen visualisoinnin luettelo: puukartat](http://www.datavizcatalogue.com/methods/treemap.html#.VYhylI3bL7Y)

### <a name="other-charts"></a>Muut kaaviot
#### <a name="pie-or-donut-charts"></a>Ympyrä- tai rengaskaaviot
![](media/power-bi-visualization-best-practices/power-bi-donut.png)

Palkki-, pylväs- tai viivakaaviot sopivat yleensä useimpiin tilanteisiin. Ympyrä- ja rengaskaavioita on usein vaikea tulkita oikein, ja ne voivat itse asiassa usein vääristää tietoja. Vältä niitä aina kun mahdollista. Stephen Few on kirjoittanut erinomaisen artikkelin niiden taustasta ja vaaroista [Save the Pies for Dessert]([www.percetualedge.com/articles/08-21-07.pdf](http://www.perceptualedge.com/articles/08-21-07.pdf)

Ympyräkaavioista voi olla hänen mukaansa hyötyä yhdessä tilanteessa eli verrattaessa osien ja kokonaisuuden suhteita toisiinsa. Tosin tässäkin tapauksessa olisi parempi käyttää 100-prosentin pinottua palkkikaaviota.

Toinen hauska ympyräkaaviota koskeva artikkeli (ja animaatio) löytyy [Darkhorse Analytics -sivustolta](http://www.darkhorseanalytics.com/blog/salvaging-the-pie).

Voit myös lukea vastakkaisen näkökulman artikkelista [Why Tufte is flat-out wrong about pie charts](http://speakingppt.com/2013/03/18/why-tufte-is-flat-out-wrong-about-pie-charts/)

#### <a name="radial-gauges--kpis"></a>Sädemittarit ja suorituskykyilmaisimet
![](media/power-bi-visualization-best-practices/power-bi-gauge.png)

Sädemittarit saattavat tuntua hyvältä visualisoinnilta osoittamaan suorituskykyä suhteessa tavoitteeseen, ja ne ovat hyvin suosittuja johdon koontinäytöissä. Niihin liittyy kuitenkin kaksi pääasiallista ongelmaa. Samoin kuin ympyräkaavioita, varjostetun alueen kulmaa on vaikea tulkita verrattuna täyden 180 asteen kaareen tai tavoiteviivaan. Se käyttää myös paljon tilaa näyttämään yhden metriikan.

Hyvä vaihtoehto tälle on yksinkertainen KPI-visualisointi.

![](media/power-bi-visualization-best-practices/power-bi-kpi.png)

Suorituskykyilmaisimet näyttävät arvon, tilan, varianssin tavoitteesta ja trendin samassa tilassa. Vihreä muuttuu punaiseksi, jos tavoitetta ei saavuteta, ja se voi olla keltainen, jos saavutetaan jokin välitavoite. Sitä on paljon helpompi lukea ja tulkita kuin sädemittaria.

Lisätietoja:

* [Opetusohjelma: Sädemittarikaaviot Power BI:ssä](power-bi-visualization-radial-gauge-charts.md)
* [Opetusohjelma: Suorituskykyilmaisimet Power BI:ssä](power-bi-visualization-kpi.md)

## <a name="conclusion"></a>Päätelmät
Nyt on aika testata näitä parhaita käytäntöjä.  Voit kertoa meille myös omista parhaista käytännöistäsi. Etkä ole samaa mieltä suosituksistamme tai löysitkö hyvän syyn ”poiketa säännöistä”?  Haluamme myös kuulla mielellämme niitä koskevia kommentteja.  

### <a name="book-recommendations"></a>Kirjasuositukset
Markkinoilla on nykyisin monta hyvää kirjaa, jotka auttavat tiimejä soveltamaan visuaalisia suunnittelutekniikoita. Lue ehdottomasti Stephen Few’n kirja *Information Dashboard Design*. Hän käsittelee teemoja vieläkin tarkemmin kahdessa muussa kirjassa *Show me the Numbers* ja *Now You See It*. Few ja muut ovat saaneet inspiraationsa Edward R. Tuftelta, jonka kirjaa *The Visual Display of Quantitative Information* pidetään alan klassikkona. Tufte on myös kirjoittanut teokset *Visual Explanations*, *Envisioning Information* ja *Beautiful Evidence*. Toinen hyvä vaihtoehto on Andy Kirkin uusin kirja *Data Visualization: A Handbook for Data Driven Design*. Muita suositeltavia kirjailijoita ovat: Lachlan James, William McKnight ja Boris Evelson (Forrester), Darkhorse Analytics.

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

