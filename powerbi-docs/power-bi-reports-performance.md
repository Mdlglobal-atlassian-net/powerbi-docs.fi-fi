---
title: Power BI:n suorituskykyä parantavat parhaat käytännöt
description: Tässä artikkelissa annetaan ohjeita nopeiden ja luotettavien raporttien luomiseen Power BI:ssä
author: Bhavik-MSFT
ms.author: bhmerc
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/30/2018
LocalizationGroup: Reports
ms.openlocfilehash: 52beebb839907a6b4141cec089184fcb693fe817
ms.sourcegitcommit: 0d7ad791a2d2bef45d5d60e38e0af4c9fc22187b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2019
ms.locfileid: "74010696"
---
# <a name="power-bi-performance-best-practices"></a>Power BI:n suorituskykyä parantavat parhaat käytännöt

Tässä artikkelissa annetaan ohjeita nopeiden ja luotettavien raporttien luomiseen Power BI:ssä.  

## <a name="choose-an-appropriate-storage-mode-import-directquery"></a>Valitse sopiva tallennustilan tila: Tuo, DirectQuery

Useimmissa tapauksissa Tuo-tila on paras vaihtoehto, sillä se tarjoaa suurimman nopeuden hyödyntämällä paikallisessa välimuistissa olevia muistinsisäisiä tietoja, jotka on pakattu sarakemuotoon. Tuo-tila tukee myös täydellisiä DAX-toimintoja. Harkitse DirectQueryn (ja yhdistelmämallien) käyttöä, kun lähdetietojen määrä on liian suuri Power BI ‑kapasiteetille. DirectQuerysta on hyötyä myös silloin, kun sinun on noudettava uusimmat tiedot lähteestä aina raportin lataamisen yhteydessä. Jos sinulla ei ole tällaista tarvetta ja jos käyttäjien tarvitsevat tietoja, joita päivitetään muutaman kerran päivässä tai harvemmin (esim. yrityksen tietovarastosta), Tuo-tilan käyttö on erittäin suositeltavaa. DirectQuery-tilassa käyttäjät saattavat yrittää päivittää raportin tietämättään, että he noutavat lähteestä täsmälleen samat tiedot.      

## <a name="use-filters-to-limit-report-visuals-to-display-only-whats-needed"></a>Vähennä raportin visualisointeja suodattimilla niin, että siinä näkyvät vain tarpeelliset 

Mitä enemmän tietoja visualisoinnissa on oltava näkyvissä, sitä hitaampaa on kyseisen visualisoinnin lataaminen. Vaikka tämä periaate tuntuu itsestäänselvältä, se voi kuitenkin helposti unohtua. Otetaan esimerkiksi tilanne, jossa sinulla on suuri tietojoukko. Laadit tietojoukon päälle raportin, jossa on taulukko taulukosta. Loppukäyttäjät siirtyvät haluamilleen riveille käyttämällä sivulla olevia osittajia – yleensä he ovat kiinnostuneita vain muutamista kymmenistä riveistä.

Yleinen virhe on, että taulukon oletusnäkymää ei ole suodatettu – eli siinä näkyvät kaikki yli 100 miljoonaa riviä. Näiden rivien tiedot ladataan muistiin ja puretaan jokaisen päivityksen yhteydessä. Tämä käsittely aiheuttaa huomattavaa muistikuormitusta. Ratkaisu tilanteeseen on vähentää taulukon näyttämää tietoyksiköiden enimmäismäärää käyttämällä ”Ylimmät N” -suodatinta. Tietoyksiköiden enimmäismäärä voi olla suurempi kuin mitä käyttäjät tarvitsisivat, esimerkiksi 10 000. Loppukäyttäjän käyttökokemus ei muutu, mutta muistin käyttö pienenee huomattavasti. Lisäksi suorituskyky paranee.

Samaa edellä esitettyä menetelmää on suositeltavaa käyttää kaikkiin raporttien visualisointeihin. Kysy itseltäsi, ovatko kaikki tiedot tässä visualisoinnissa tarpeellisia? Onko olemassa keinoja, joilla visualisoinnissa näytettyjen tietojen määrää voisi suodattaa niin, että vaikutus loppukäyttäjän kokemukseen olisi mahdollisimman pieni? Erityisesti taulukot voivat olla kalliita.

## <a name="limit-visuals-on-report-pages"></a>Vähennä raporttisivujen visualisointeja

Edellä oleva periaate koskee myös yksittäisen raportin sisältämien visualisointien määrää. On erittäin suositeltavaa, että vähennät yksittäisessä raportissa olevien visualisointien määrää vain siihen, mikä on tarpeellista. Alirakennesivut ovat erinomainen keino antaa lisätietoja ilman tarvetta ahtaa lisää visualisointeja raporttiin.  

## <a name="optimize-your-model"></a>Optimoi mallisi

Parhaita käytäntöjä:

- Poista käyttämättömät taulukot tai sarakkeet mahdollisuuksien mukaan. 
- Vältä erillisiä määriä kentissä, joiden kardinaliteetti on suuri – eli miljoonia erillisiä arvoja.  
- Pyri välttämään kenttiä, jotka ovat tarpeettoman tarkkoja ja kardinaliteetiltaan tarpeettoman suuria. Voit esimerkiksi jakaa erittäin yksilölliset päivämäärä- ja aika-arvot omiin sarakkeisiinsa, kuten kuukausi, vuosi, päivämäärä ja niin edelleen. Tai mikäli mahdollista, käytä pyöristystä suuren tarkkuuden kentissä pienentääksesi kardinaliteettia. Esimerkki: 13,29889 -> 13,3.
- Käytä mahdollisuuksien mukaan merkkijonojen sijaan kokonaislukuja.
- Noudata huolellisuutta DAX-funktioissa, kuten RANKX-funktiossa, jotka on testattava taulukon jokaisella rivillä. Pahimmassa tapauksessa nämä funktiot voivat eksponentiaalisesti suurentaa suoritusaika- ja muistivaatimuksia ottaen huomioon lineaariset kasvut taulukon koossa.
- Yhdistäessäsi tietolähteisiin Directqueryn kautta harkitse sellaisten sarakkeiden indeksointia, jotka suodatetaan tai ositetaan uudelleen usein. Indeksointi parantaa merkittävästi raportin vasteaikaa.  

Lisäohjeita tietolähteiden optimointiin DirectQueryä varten on [SQL Server 2016 Analysis Services DirectQuery](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/) -raportissa.

## <a name="directquery-and-live-connection-understand-underlying-data-source-performance"></a>DirectQuery ja Live-yhteys: ymmärrä taustalla olevaa tietolähteen suorituskykyä

Kun käytössä on DirectQuery tai Live-yhteys ja käyttäjät käyvät Power BI -raportissa, Power BI lähettää reaaliaikaisesti kyselyjä taustalla olevaan tietolähteeseen. Kun tietolähde palauttaa kyselytiedot, raportti hahmonnetaan. Tämän seurauksena raportin suorituskyky määräytyy pitkälti taustalla olevan tietolähteen suorituskyvyn mukaan.

Näissä tapauksissa on tärkeää, että tiedät, millainen taustalla olevan tietolähteen suorituskyky on. Eri tietolähteillä on erilaisia työkaluja kyselyn suorituskyvyn selvittämiseen. Esimerkiksi SQL Server ja Azure SQL tarjoavat kyselysäilön, joka taltioi kyselyiden historian ja niiden suoritusaikatilastot.

Ottaessasi käyttöön DirectQueryyn ja Live-yhteyteen pohjautuvia Power BI -raportteja kokeile toimintoja, joita loppukäyttäjäsi tulevat tekemään Power BI Desktopissa. Jos raportin lataaminen Power BI Desktopissa on hidasta, sen lataaminen on todennäköisesti hidasta myös loppukäyttäjien palvelussa. 

## <a name="directquery-best-practices"></a>DirectQueryn parhaat käytännöt

Seuraavassa osiossa kuvataan yleisiä parhaita käytäntöjä yhdistämiseen DirectQueryn kautta.

### <a name="db-design-guidance"></a>Ohjeita tietokannan suunnitteluun

- Työnnä laskettuja sarakkeita ja mittareita lähteeseen, mikäli mahdollista. Mitä lähempänä ne ovat lähdettä, sitä suurempi todennäköisyys suorituskyvyn parantumiseen.
- Optimoi! Ymmärrä kyselyiden suoritussuunnitelmia, lisää indeksejä usein suodatettaviin sarakkeisiin jne.

### <a name="modeling-guidance"></a>Mallinnusohjeet

- Aloita Power BI Desktopissa.
- Vältä monimutkaisia kyselyitä kyselyeditorissa.
- Älä käytä suhteellista päivämäärien suodattamista kyselyeditorissa.  
- Pidä mittarit aluksi yksinkertaisina ja lisää monimutkaisuutta asteittain.
- Vältä yhteyksiä lasketuissa sarakkeissa ja yksilöllisten tunnisteiden sarakkeissa.
- Kokeile käyttää suhteisiin Oleta viite-eheys -asetusta – monissa tapauksissa tämä asetus voi parantaa merkittävästi kyselyn toimintaa.  

### <a name="general"></a>Yleiset

- Käytä suodattimia ensin.
- Harkitse visualisointien välisen vuorovaikutuksen poistamista käytöstä, sillä tämä vähentää kyselyn kuormitusta, kun käyttäjät korostavat ristiin.
- Rajoita visualisointien määrää ja visualisointikohtaisia tietoja edellä kuvatulla tavalla.
- Rivitason suojauksen ottaminen käyttöön voi tuoda suuria muutoksia suorituskykyyn. Muista testata eri rivitason suojausrooleja, joita käyttäjillä tulee olemaan.
- Palvelu pakottaa kyselytason aikakatkaisuja, jotta pitkäkestoiset kyselyt eivät veisi suurinta osaa järjestelmäresursseista. Yli 225 sekuntia kestävät kyselyt aikakatkaistaan, ja seurauksena on visualisointitason virhe.

## <a name="understand-dashboards-and-query-caches"></a>Koontinäyttöjen ja kyselyn välimuistien ymmärtäminen

Koontinäytön lataamisen yhteydessä kyselyn välimuisti tarjoaa koontinäyttöihin kiinnitetyt visualisoinnit. Sitä vastoin raporteissa käyntien aikana kyselyt tietolähteeseen tehdään saman tien – joko Power BI -palveluun (tuonnin yhteydessä) tai määrittämääsi tietolähteeseen (kun käytössä on DirectQuery tai Live-yhteys).  

> [!NOTE]
> Kun kiinnität reaaliajassa raporttitapahtumaruutuja koontinäyttöön, niitä ei tarjota välimuistista. Sen sijaan ne toimivat raporttien tapaan ja tekevät saman tien kyselyitä taustaytimiin.

Nimensä mukaisesti tietojen noutaminen kyselyn välimuistista tarjoaa paremman ja yhdenmukaisemman suorituskyvyn kuin tietolähteen varassa oleminen. Yksi tapa hyödyntää tätä toimintoa on ottaa koontinäytöt käyttäjien ensimmäiseksi aloitussivuksi. Kiinnitä usein käytetyt ja usein pyydetyt visualisoinnit koontinäyttöihin. Näin koontinäytöistä tulee arvokas ”ensisijainen puolustautumiskeino”, joka tarjoaa tasaista suorituskykyä pienemmällä kapasiteetin kuormituksella. Käyttäjät voivat edelleen siirtyä raportin läpi napsauttamalla ja perehtyä yksityiskohtiin.  
 

DirectQueryn ja Live-yhteyden kohdalla kyselyn välimuistia päivitetään säännöllisin väliajoin tekemällä kyselyitä tietolähteelle. Oletusarvoisesti tämä tapahtuu tunnin välein, mutta aikaväli voidaan määrittää tietojoukon asetuksista. Jokainen kyselyn välimuistipäivitys lähettää kyselyjä taustalla olevaan tietolähteeseen välimuistin päivittämistä varten. Tehtyjen kyselyiden määrä riippuu koontinäyttöön kiinnitettyjen ja kyseisestä tietolähteestä riippuvien visualisointien määrästä. Huomaa, että jos rivitason suojaus on käytössä, kyselyt luodaan kullekin eri suojauskontekstille. Jos sinulla on esimerkiksi kaksi eri roolia, joihin käyttäjät jakautuvat, ja heillä on kaksi eri tietonäkymää, tällöin kyselyn välimuistin päivityksen yhteydessä Power BI luo kaksi kyselyjoukkoa. 

## <a name="understand-custom-visual-performance"></a>Tutustu mukautetun visualisoinnin suorituskykyyn 

Muista testata jokainen mukautettu visualisointi, jotta niiden hyvä suorituskyky voidaan varmistaa. Huonosti optimoidut mukautetut visualisoinnit voivat vaikuttaa kielteisesti koko raportin suorituskykyyn. 

## <a name="deep-dive-into-query-performance-with-sql-profiler-and-power-bi-desktop"></a>Tutustu tarkemmin kyselyiden suorituskykyyn SQL Profiler -työkalun ja Power BI Desktopin avulla

Saat tarkemman käsityksen siitä, mitkä visualisoinnit vievät eniten aikaa ja resursseja, yhdistämällä SQL Profiler -työkalun Power BI Desktopiin. Näin saat kokonaiskuvan kyselyn suorituskyvystä.

> [!NOTE]
> Power BI Desktop tukee diagnostiikkaporttiin yhdistämistä. Diagnostiikkaportti sallii yhteydenmuodostuksen muilla työkaluilla ja sen avulla voidaan suorittaa jäljityksiä vianmääritystä varten. *Muutosten tekemistä malliin ei tueta! Malliin tehdyt muutokset saattavat johtaa vioittumiseen ja tietojen menettämiseen.*

Ohjeet ovat seuraavat:
  
1. **Asenna SQL Server Profiler ja suorita Power BI Desktop**

   SQL Server Profiler on saatavilla osana SQL Server Management Studiota.

2. **Määritä Power BI Desktopin käyttämä portti**

   Suorita komentokehote tai PowerShell Suorita järjestelmänvalvojan oikeuksin. Etsi sitten netstat-toiminnon avulla portti, jota Power BI Desktop käyttää analyysia varten:

   `> netstat -b -n`

   Tuloksena tulisi olla luettelo sovelluksista ja niiden avoimista porteista, esimerkiksi:  

   `TCP    [::1]:55786            [::1]:55830            ESTABLISHED`

   [msmdsrv.exe]

   Etsi msmdsrv.exen käyttämä portti ja kirjoita se myöhempää käyttöä varten. Tässä tapauksessa käytät porttia 55786.
3. **Yhdistä SQL Server Profiler -työkalu Power BI Desktopiin**

   - Käynnistä SQL Server Profiler **Käynnistä**-valikon kautta
   - **Tiedosto** > **Uusi jäljitys**
   - Palvelimen tyyppi: Analysis Services
   - Palvelimen nimi: localhost: [portin numero yllä]
   - Valitse seuraavassa näytössä **Suorita**
   - SQL Profiler on nyt toiminnassa ja profiloi aktiivisesti kyselyitä, joita Power BI Desktop lähettää. 
   - Kun kyselyt on suoritettu, näet niiden kestot ja suoritinajat. Näiden tietojen avulla voit määrittää, mitkä kyselyt ovat pullonkauloja.  

SQL Profiler -työkalun avulla voit tunnistaa kyselyt, jotka vievät pisimmän suoritinajan. Nämä kyselyt ovat todennäköisesti suorituskyvyn pullonkauloja. Näitä kyselyitä suorittavien visualisointien tulee näin olla jatkuvan optimoinnin keskipisteessä.

## <a name="gateway-best-practices"></a>Yhdyskäytävää koskevat parhaat käytännöt

Paikallinen tietoyhdyskäytävä on erinomainen työkalu, jonka avulla voit yhdistää Power BI -palvelun paikallisiin tietoihin. Jos se suunnitellaan huonosti, se voi kuitenkin muodostua myös raportin suorituskyvyn pullonkaulaksi. Tämä pätee erityisesti DirectQuery-/Live-yhteystietojoukkoihin, joissa kaikki kyselyt ja kyselyvastaukset kulkevat yhdyskäytävän kautta. Seuraavassa on muutamia parhaita käytäntöjä, joilla voidaan varmistaa erittäin suorituskykyiset yhdyskäytävät: 

- **Käytä yritystilaa**, ei henkilökohtaista tilaa.
- **Yhdyskäytävän suositellut laitteisto-ominaisuudet** – kahdeksan suoritinydintä, 16 Gt:n RAM-muisti.
- **Määritä seuranta** – määritä yhdyskäytäväkoneen suorituskyvyn valvonta tunnistamaan, onko yhdyskäytävä tulossa ylikuormitetuksi ja muodostumassa pullonkaulaksi. Lisätietoja on [Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md) -asiakirjassa.
- **Skaalaa ylös tai skaalaa ulos** – jos yhdyskäytävä on tosiasiassa muodostumassa pullonkaulaksi, harkitse skaalausta ylös (eli siirrä yhdyskäytävä tehokkaampaan koneeseen, jossa on suurempi suoritin ja RAM-muistia) tai skaalaamalla ulos (esimerkiksi jakamalla ulos tietojoukkoja eri yhdyskäytäviin). 
- **Erillinen tuonti vs. DirectQuery** – jos skaalaat ulos, harkitse yhdyskäytävien jakamista niihin, jotka vastaavat tuonnista ja niihin, jotka vastaavat DirectQuerystä.

## <a name="network-latency"></a>Verkon viive

Verkon viive voi vaikuttaa raportin suorituskykyyn kasvattamalla aikaa, jonka pyynnöt tarvitsevat saavuttaakseen Power BI -palvelun, ja vastausten toimitusaikaa. Vuokraajille nimetään Power BI:ssä tietty alue. Voit tarkastella vuokraajan ”kotialuetta” siirtymällä powerbi.com-palveluun, valitsemalla oikeasta yläkulmasta **?** ja lopuksi **Tietoja Power BI:stä**. Kun vuokraajan käyttäjät käyttävät Power BI -palvelua, heidän pyyntönsä reititetään aina tälle alueelle. Kun pyynnöt saavuttavat Power BI -palvelun, palvelu voi tämän jälkeen lähettää lisäpyyntöjä esimerkiksi taustalla olevaan tietolähteeseen tai yhdyskäytävään, joita verkkoviive koskee myös.

Työkalut, kuten [Azure Speed Test](https://azurespeedtest.azurewebsites.net/), voivat osoittaa verkkoviiveen asiakkaan ja Azure-alueen välillä. Yleensä voit minimoida verkkoviiveen vaikutuksen pyrkimällä pitämään tietolähteet, yhdyskäytävät ja Power BI -klusterin mahdollisimman lähellä. Jos verkkoviive on ongelma, voit kokeilla yhdyskäytävien ja tietolähteiden sijoittamista lähemmäs Power BI -klusteria sijoittamalla ne näennäiskoneisiin.

## <a name="next-steps"></a>Seuraavat vaiheet

- Tekninen raportti [Planning a Power BI Enterprise Deployment](https://aka.ms/pbienterprisedeploy), joka sisältää kattavat ohjeet Power BI:n suuren mittakaavan käyttöönotoille
- [DirectQuery in SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/) -raportti
- [[YouTube] Building Fast and Reliable Reports in Power BI](https://www.youtube.com/watch?v=GhiJABR7XX0)
- [[YouTube] Power BI Enterprise Deployments](https://www.youtube.com/watch?v=K-zEWICvICM)
