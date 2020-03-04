---
title: Power BI -raporttipalvelinten uudet ominaisuudet
description: Lue Power BI -raporttipalvelimen uusista ominaisuuksista. Tämä artikkeli käsittelee tärkeimpiä ominaisuuksia, ja sitä päivitetään uusien julkaisujen myötä.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 02/27/2020
ms.openlocfilehash: 251f89dd031d9a2bda146266308dc528f05eddb2
ms.sourcegitcommit: ec4d2d0f52d737e8e0583f6a7b16e6fd87382510
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782444"
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI -raporttipalvelinten uudet ominaisuudet

Tutustu Power BI -raporttipalvelimen ja Power BI -raporttipalvelimelle optimoidun Power BI Desktopin uusiin ominaisuuksiin. Tämä artikkeli käsittelee tärkeimpiä ominaisuuksia, ja sitä päivitetään jokaisen uuden julkaisun myötä.

Lataa [Power BI -raporttipalvelin ja Power BI -raporttipalvelimelle optimoitu Power BI Desktop](https://powerbi.microsoft.com/report-server/).

Lisätietoja Power BI:hin liittyvistä uusista ominaisuuksista:

* [Power BI -palvelun uudet ominaisuudet](../service-whats-new.md)
* [Power BI Desktopin uudet ominaisuudet](../desktop-latest-update.md)
* [Power BI -mobiilisovellusten uudet ominaisuudet](../consumer/mobile/mobile-whats-new-in-the-mobile-apps.md)

## <a name="january-2020"></a>Tammikuu 2020

Lisätietoja on Power BI -raporttipalvelimen blogikirjoituksessa tammikuulta 2020.

### <a name="power-bi-desktop-optimized-for-power-bi-report-server"></a>Power BI -raporttipalvelimelle optimoitu Power BI Desktop

Tämä julkaisuversio tuo mukanaan monia uusia ominaisuuksia, kuten ehdollisen muotoilun painikkeille, parannuksia tietojen profilointiin sekä lisää muotoiluasetuksia suorituskykyilmaisimille ja taulukkovisualisoinneille. Seuraavassa on yhteenveto päivityksistä:

**Raportointi**

- Taulukon sarakkeen tai matriisin arvon määrittäminen mukautetuksi URL-osoitteeksi
- Suorituskykyilmaisimen visualisoinnin muotoilun asetukset
- Suodatinruudun käyttökokemuspäivitykset

**Analysointi**

- Painikkeiden ehdollinen muotoilu
- Lataa lisää merkityksellisten tietojen analysointia varten
- Uusi DAX-funktio: Vuosineljännes

**Tietojen valmistelu**

- Tietoprofiloinnin parannukset

**Muu**

- Uusi tiedostomuoto:. pbids
- Mallinnustoimintojen suorituskyvyn parannukset

**Raportointi**

*Taulukon sarakkeen tai matriisin arvon määrittäminen mukautetuksi URL-osoitteeksi*

Voit määrittää taulukon sarakkeen tai matriisin arvon mukautetuksi URL-osoitteeksi. Tämä uusi vaihtoehto on käytettävissä Ehdollinen muotoilu -kortin muotoiluruudussa.

*Suorituskykyilmaisimen visualisoinnin muotoilun asetukset*

Tämän kuukauden julkaisu lisää suorituskykyilmaisimille uusia muotoiluasetuksia:

- Ilmaisimen tekstin muotoilu (fonttiperhe, väri ja tasaus)
- Trendiakselin läpinäkyvyys
- Tavoitteen ja etäisyyden tekstin muotoilu (otsikon teksti, fonttiperhe, väri ja koko)
- Etäisyyden tekstin muotoilu (otsikon teksti, positiivinen suunta, fonttiperhe, väri ja koko)
- Päivämäärän otsikon lisääminen muotoiltuna (fonttiperhe, väri ja koko)

Voit muotoilla joitakin näistä uusista muotoiluasetuksista ehdollisesti:

- Ilmaisimen fontin väri
- Tavoitteen fontin väri ja tavoitteen etäisyyden fontin väri
- Hyvän/huonon/neutraalin tilan värit
- Päivämäärän fontin väri

*Suodatinruudun käyttökokemuspäivitykset*

Olemassa olevien raporttien siirtämistä uuteen ruutuun on virtaviivaistettu sen jälkeen, kun uusi suodatinominaisuus tuli yleisesti saataville [edellisessä julkaisussa](https://powerbi.microsoft.com/blog/power-bi-report-server-september-2019-feature-summary/#filterPane). Kun avaat Power BI -raporttipalvelimen ensimmäistä kertaa, näet suodatinruudun automaattisen päivityksen valintaikkunan. Päivityksiin sisältyvät myös raporttipalvelimen bannerit silloin, kun raportteja on siirrettävä uuteen käyttökokemukseen.

**Analysointi**

*Painikkeiden ehdollinen muotoilu*

Nämä ehdollisen muotoilun päivitykset ovat kaikki painikkeisiin liittyviä. Voit nyt dynaamisesti asettaa muotoilun seuraaville ominaisuuksille:

- Painiketekstien fontin väri
- Painikkeen teksti
- Kuvakkeen viivan väri
- Ääriviivan väri
- Täyttöväri
- Painikkeen työkaluvihje (toimintokortin alla)

*Lataa lisää merkityksellisten tietojen analysointia varten*

Kun suoritat analysoinnin merkityksellisten tietojen (kuten Selitä lisäys) löytämiseksi, koneoppimismalleja käytetään vain määritettyyn ajanjaksoon, jotta voimme näyttää merkitykselliset tiedot nopeasti. Jos analysoitavaa tietoa on paljon, voit nyt jatkaa analyysin suorittamista myös alkuperäisen aikarajan jälkeen.

*Uusi DAX-funktio: Quarter*

Tässä kuussa julkaistiin uusi DAX-funktio Quarter (vuosineljännes). Quarter-funktio palauttaa määritettyä päivämäärää vastaavan vuosineljänneksen.

**Tietojen valmistelu**

*Tietoprofiloinnin parannukset*

Tässä kuussa esittelemme muutamia merkittäviä parannuksia tietoprofiloinnin ominaisuuksiin Power Query -editorissa:

- Uudet ryhmittelyasetukset sarakkeen profiiliruudun arvojakauman visualisoinnille on määritetty saraketyypin mukaan – jo aiemmin lisättyjen arvon mukaan -ehtojen lisäksi.
- Teksti: Tekstin pituuden mukaan (merkkien määrä).
- Luku: Merkin (positiivinen/negatiivinen) ja pariteetin (parillinen/pariton) mukaan.
- Päivämäärä / Päivämäärä ja aika: Vuoden, kuukauden, päivän, vuoden viikon, viikon päivän, AM/PM-ajan ja päivän tunnin mukaan.
- Muita tietotyyppejä varten esimerkiksi looginen tosi/epätosi.

*Suodatusasetukset*

Pystyit jo aiemmin hyödyntämään useita tyyppikohtaisia ryhmittelyehtoja sarakeprofiilien jakaumaruudussa. Nyt voit myös suodattaa jakaumakaavion jokaisen arvon kuvateksteistä, kun ryhmittelyehtoja otetaan käyttöön. Esimerkiksi Tietoprofiilit-ruudun Päivämäärä/aika-sarakkeesta voit suodattaa esiin tietylle kuukaudelle osuvat arvot.

**Muu**

*Uusi tiedostomuoto:. pbids*

Tässä kuussa julkaisemme uuden .pdids-tiedostomuodon, jonka avulla voit tehostaa tietojen noutamista organisaatiossasi raportteja luoville käyttäjille. Suosittelemme, että järjestelmänvalvojat luovat näitä tiedostoja usein käytetyille yhteyksille.

Kun raportin tekijä avaa .pbids-tiedoston, Power BI Desktop pyytää todentamista, jotta se voi muodostaa yhteyden tiedostossa määritettyyn tietolähteeseen. Tämän jälkeen käyttäjä valitsee malliin ladattavat taulukot. Käyttäjien on ehkä myös valittava tietokanta, jos sitä ei ole määritetty tiedostossa. Sen jälkeen raportin tekijä voi aloittaa visualisointien luomisen.

Lisätietoja ja esimerkkejä saat Power BI Desktopin tietolähteet -artikkelin osiosta [Tietojen noutaminen .pbids-tiedostoja käyttämällä](../desktop-data-sources.md#using-pbids-files-to-get-data).

*Mallinnustoimintojen suorituskyvyn parannukset*

Analysis Services -moduulin suorituskykyä on parannettu mallinnustoimintojen nopeuttamista varten. Sellaisia ovat esimerkiksi mittareiden ja laskettujen sarakkeiden lisääminen sekä suhteiden luominen. Näkemiesi parannusten määrä riippuu mallista, mutta esimerkiksi tiedoston avaaminen tai mittarin lisääminen on voinut nopeutua jopa 20-kertaisesti.

Tässä olivat Power BI -raporttipalvelimen tammikuun 2020 version päivitykset. Jatka palautteen lähettämistä ja muista [äänestää ominaisuuksista, joita haluat nähdä Power BI:ssä tulevaisuudessa](https://ideas.powerbi.com/forums/265200-power-bi).

### <a name="power-bi-report-server"></a>Power BI -raporttipalvelin

#### <a name="export-to-excel-from-power-bi-reports"></a>Vieminen Exceliin Power BI -raporteista

Vieminen Exceliin Power BI -raportista toimii Power BI -raporttipalvelimessa nyt samalla tavalla kuin vieminen Exceliin Power BI -raportista Power BI -palvelussa. Vieminen onnistuu suoraan Excelin .xlsx-muotoon, ja vietävien rivien enimmäismäärä on 150 000.

#### <a name="azure-sql-managed-instance-support"></a>Azure SQL:n hallitun esiintymän tuki

Voit nyt isännöidä Power BI -raporttipalvelimessa käytettävää tietokantaluetteloa Azure SQL:n hallitussa esiintymässä, jota isännöidään joko näennäiskoneessa tai omassa palvelinkeskuksessa. Tuki rajoittuu tietokannan tunnistetietojen käyttämiseen SQL:n hallittuun esiintymään yhdistämistä varten.

#### <a name="power-bi-premium-dataset-support"></a>Power BI Premium -tietojoukkojen tuki

Voit muodostaa yhteyden Power BI -tietojoukkoihin käyttämällä joko Microsoft Report Builderia tai SQL Server Data Toolsia (SSDT). Sen jälkeen voit julkaista nämä raportit Power BI -raporttipalvelimeen käyttämällä SQL Server Analysis Services -yhteyttä. Käyttäjien on käytettävä tallennettua Windows-käyttäjänimeä ja -salasanaa skenaarion ottamiseksi käyttöön.

#### <a name="alttext-alternative-text-support-for-report-elements"></a>AltText (vaihtoehtoinen teksti) -tuki raporttielementeille

Raportin laatimisen aikana voit työkaluvihjeitä käyttämällä määrittää tekstin sen kullekin elementille. Näytönlukijat pystyvät lukemaan näitä työkaluvihjeitä.

#### <a name="azure-active-directory-application-proxy-support"></a>Azure Active Directory -sovellusvälityspalvelimen tuki

Azure Active Directory -sovellusvälityspalvelimen ansiosta sinun ei enää tarvitse hallita omaa verkkosovellusten välityspalvelinta verkko- tai mobiilisovellusten suojatun käytön sallimiseksi. Lisätietoja on artikkelissa [Paikallisten sovellusten etäkäyttö Azure Active Directory -sovellusvälityspalvelimen kautta](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

#### <a name="custom-headers"></a>Mukautetut otsikot

Voit määrittää otsikkoarvot kaikille URL-osoitteille, jotka vastaavat määritettyjä säännönmukaisten lausekkeiden rakenteita. Käyttäjät voivat päivittää mukautettuja otsikkoarvoja kelvollisella XML:llä, jos on tarve määrittää otsikkoarvoja valituille pyynnön URL-otsikoille. Järjestelmänvalvojat voivat lisätä XML:ään minkä tahansa määrän otsikoita. Lisätietoja on Reporting Servicesin **palvelimen lisäominaisuuksia** koskevan artikkelin osiossa [CustomHeaders](/sql/reporting-services/tools/server-properties-advanced-page-reporting-services#customheaders).

#### <a name="transparent-database-encryption"></a>Läpinäkyvä tietokannan salaus

Power BI -raporttipalvelin tukee nyt läpinäkyvää tietokannan salausta Power BI -raporttipalvelimen luettelotietokannalle Enterprise- ja Standard-versioissa.

#### <a name="power-bi-visuals-api"></a>Power BI:n visualisointien ohjelmointirajapinta

Tämä versio sisältää ohjelmointirajapinnan version 2.6.

#### <a name="microsoft-report-builder-update"></a>Microsoftin Report Builderin päivitys

Report Builderin uusi versio on täysin yhteensopiva Microsoft SQL Server Reporting Servicesin versioiden 2016, 2017 ja 2019 kanssa. Se on myös yhteensopiva Power BI -raporttipalvelimen kaikkien julkaistujen ja tuettujen versioiden kanssa.

## <a name="september-2019"></a>Syyskuu 2019

[Power BI -raporttipalvelimen syyskuun 2019](https://powerbi.microsoft.com/blog/power-bi-report-server-september-2019-feature-summary/) blogikirjoituksessa on lisätietoja kaikista uusista ominaisuuksista.

Power BI -raporttipalvelimen syyskuun 2019 päivityksessä on paljon Power BI -raporttiominaisuuksia. Seuraavassa on joitakin kohokohtia:

- **Visuaalisen tason suodattimet osittajille** Voit lisätä osittajiin visuaalisen tason suodattimen. Se toimii samalla tavalla kuin minkä tahansa muun visuaalisen tason suodatin, eli suodattaa vain itse osittajan, ei muita visualisointeja. Tämä suodatin on hyödyllinen tyhjien kohteiden suodattamisessa pois tai mittaussuodattimien käytössä.
- **Taulukoiden ja matriisien kuvakejoukot** KPI-kuvakkeiden avulla voit määrittää säännöt, jotka koskevat taulukon ja matriisin eri kuvakesarjojen näyttämistä samaan tapaan kuin Excelin kuvakejoukoissa.
- **Visualisointien ryhmittely** Nyt voit ryhmitellä visualisoinnit, muodot, tekstiruudut, kuvat ja painikkeet yhteen raporttisivulla samalla tavalla kuin PowerPointissa. Kun ryhmität objekteja yhteen, voit siirtää niitä kaikkia ja muuttaa niiden kaikkien kokoa samanaikaisesti. Ryhmittely helpottaa työskentelyä sellaisessa raportissa, joissa on useita objekteja kerroksittain jokaisella sivulla.
- **Uudet oletusteemat** Raporteissa käytettävissä olevat teemat on päivitetty ja uusien raporttien oletusteema vaihdettu, jotta ne ovat yhdenmukaisia uusien teemojen JSON-asetusten kanssa. Uusi oletusteema vastaa entistä paremmin Microsoftin suunnittelukieltä ja visualisointien parhaita suunnittelukäytäntöjä. 
- **Päivitetty ruuturakenne** Käyttöliittymä on päivitetty suurelta osin. Kaikkien ruutujen, alatunnisteen ja näkymävalitsimen värit on päivitetty vaaleammiksi, välistykset on päivitetty ja uuden kuvakkeet on otettu käyttöön. Uusi rakenne on koko käyttöliittymän päivittämisen ensimmäinen vaihe.

Seuraavassa on täydellinen ominaisuusluettelo. 

### <a name="reporting"></a>Raportointi

- Päivitetty ruutujen rakenne
- Sektorien visuaalisen tason suodattimet
- Suorituskyvyn analysointiruudun järjestely
- Visuaalisen otsikon työkaluvihjeet
- Taulukkojen ja matriisien selitteiden täydellinen mukauttaminen
- Hierarkianosittajan synkronoinnin tuki
- Yhdenmukaiset kirjasinkoot visualisoinneissa
- Kuvakejoukot taulukoille ja matriiseille
- Prosenttituki ehdolliselle muotoilulle sääntöjen avulla
- Uusi suodatusruutu nyt yleisesti saatavilla
- Tietojen värien tuki käytettäessä PlayAxis-akselia pistekaavioissa
- Suorituskyvyn parannuksia käytettäessä suhteellista päivämäärää ja avattavia osittajia
- Visualisointien ryhmittely
- Teemojen väri- ja tekstiluokat
- Uudet oletusteemat

### <a name="analytics"></a>Analytiikka

- Mukautetut muotoilumerkkijonot
- Muotoiluasetusten ehdollisen muotoilun päivityksiä

    - Visualisointien tausta ja otsikkovärit
    - Korttien värit
    - Mittarin täyttö ja värit
    - Vaihtoehtoinen teksti
    - Reunan väri

- Ehdollisen muotoilun varoitukset
- Parannuksia läpiporautumisen hakutuloksiin
- Uudet DAX-lausekkeet: REMOVEFILTERS ja CONVERT
- Uusi DAX-vertailuoperaattori: ==

### <a name="data-preparation"></a>Tietojen valmistelu

- M Intellisense -integroinnin parannuksia
- Uusi muunnos: Jaa sarake osiin sijaintien mukaan
- Kopioiminen leikepöydälle tietojen profiloinnista


## <a name="may-2019"></a>Toukokuu 2019

### <a name="power-bi-desktop-for-power-bi-report-server"></a>Power BI Desktop Power BI -raporttipalvelimelle

[Power BI -raporttipalvelimen toukokuun 2019](https://powerbi.microsoft.com/blog/power-bi-report-server-update-may-2019/) blogikirjoituksessa on lisätietoja kaikista uusista ominaisuuksista.

Seuraavassa on joitakin version kohokohtia:

#### <a name="performance-analyzer"></a>Suorituskyvyn analysointi 

Jos raporttisi toimii oletettua hitaammin, kokeile Power BI Desktopin suorituskyvyn analysointia. Kun käynnistät sen, se luo loki tiedoston, joka sisältää tiedot kaikista raportissa käyttämistäsi toiminnoista. Lue lisätietoja [suorituskyvyn analysoinnista](../desktop-performance-analyzer.md).

#### <a name="new-modeling-view"></a>Uusi mallinnusnäkymä

Power BI Desktopin uuden Mallintamisnäkymän avulla voit tarkastella ja käsitellä monimuotoisia tietojoukkoja, jotka sisältävät useita taulukoita. Kohokohtia ovat useita kaavioita sisältävät asettelut ja sarakkeiden, mittarien ja taulukoiden joukkomuokkaus. Lue lisätietoja [mallinnusnäkymästä](../desktop-modeling-view.md).

#### <a name="accessible-visual-interaction"></a>Helppokäyttöinen visuaalinen vuorovaikutus

Voit nyt käyttää arvopisteitä monissa valmiissa visualisoinneissa näppäimistöllä siirtymisen avulla. Lue lisätietoja [Power BI -raporttien helppokäyttöisyydestä](../desktop-accessibility.md).

#### <a name="conditional-formatting-titles-and-web-url-actions"></a>Otsikoiden ehdollinen muotoilu ja verkko-URL-toiminnot

Power BI -raportit ovat vuorovaikutteisia. On järkevää, että raportin otsikot ovat dynaamisia, jotta ne vastaavat raportin kulloistakin tilaa. Voit määrittää painikkeiden, muotojen ja kuvien URL-osoitteet dynaamisiksi saman lausekkeeseen sidotun muotoilun avulla. Lue lisätietoja [lausekepohjaisista otsikoista](../desktop-conditional-format-visual-titles.md).

#### <a name="cross-highlight-by-axis-labels"></a>Ristiinkorostus akseleiden nimien mukaan

Jos haluat ristiinkorostaa sivun muita elementtejä, voit valita visualisoinnin akselin luokkaotsikoita samalla tavalla kuin visualisoinnin arvopisteitä. Lue lisätietoja [ristiinkorostamisesta](../power-bi-reports-filters-and-highlighting.md#ad-hoc-highlighting).

#### <a name="all-the-new-features"></a>Kaikki uudet ominaisuudet

Seuraavassa on luettelo kaikista uusista ominaisuuksista:

#### <a name="reporting"></a>Raportointi

- Ristiinkorostus yhdessä pisteessä viivakaavioissa 
- Automaattinen rivitys otsikoissa 
- Oletusarvoisen visuaalisen vuorovaikutuksen päivitys ristiinsuodatusta varten
- Visuaalisten reunusten pyöristetyt kulmat 
- Yksittäinen valinta -osittaja  
- Lämpökartta-tuki Bing-kartoille  
- Ristiinkorostus akseleiden nimien mukaan  
- Työkaluvihjeen oletusmuotoilu  
- Staattisten URL-verkko-osoitteiden tuki painikkeille, muodoille ja kuville  
- Sivun tasausasetukset   
- Valintaruudun parannuksia  
- Helppokäyttöinen visuaalinen vuorovaikutus  
- Visualisoinnin otsikon ehdollinen muotoilu  
- Painikkeiden, muotojen ja kuvien URL-osoitetoimintojen ehdollinen muotoilu
- Suorituskyvyn analysointiruutu
- Näppäimistöllä siirtyminen taulukoissa ja matriiseissa
- Rivitietojen selitteen sijainnin ohjausobjektin
- Suorituskykyilmaisimen visuaalisen ilmaisimen tekstikoon ohjausobjekti

#### <a name="analytics"></a>Analytiikka

- Näytä päivämäärät hierarkiana nyt yleisesti saatavilla  

#### <a name="modeling"></a>Mallintaminen

- Uusi mallinnusnäkymä nyt yleisesti saatavilla
- Uusia DAX-funktioita
- Päivitä ALLSELECTED DAX -funktioon
- Poista käytöstä automaattiset päivämäärätaulukot uusissa raporteissa

### <a name="power-bi-report-server"></a>Power BI -raporttipalvelin

#### <a name="support-for-trusted-visuals"></a>Luotettujen visualisointien tuki

Power BI -raporttipalvelimeen on lisätty luotettujen visualisointien tuki. Tällä hetkellä tuemme Mapboxia ja PowerOn-visualisointeja. ESRI, Visio ja PowerApps eivät ole tuettuja tässä versiossa.)

#### <a name="improved-security-features"></a>Parannetut suojausominaisuudet

**RestrictedResourceMimeTypeForUpload**, jonka avulla järjestelmänvalvojat voivat määrittää pilkuin erotellun luettelon kielletyistä mime-tyypeistä, kuten text/html.

## <a name="january-2019"></a>Tammikuu 2019

Seuraavien Power BI -raporttien ominaisuuksien tuki:

[**Rivitason suojaus**](row-level-security-report-server.md) Tietojen käyttöä voidaan Power BI -raporttipalvelimessa rajoittaa tietyille käyttäjille määrittämällä rivitason suojaus (RLS). Suodattimet rajoittavat tietojen käyttöä rivitasolla ja voit määrittää roolien sisäisiä suodattimia.

[**Matriisin riviotsikoiden laajennus ja kutistus**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#expandCollapse) Lisätty mahdollisuus laajentaa tai kutistaa yksittäisiä riviotsikoita. Tämä on yksi pyydetyimpiä visualisointiominaisuuksia.

[**Kopiointi ja liittäminen .pbix-tiedostojen välillä**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#copyPaste) Voit kopioida visualisointeja .pbix-tiedostojen välillä joko visualisoinnin pikavalikosta tai normaalilla Ctrl+C-näppäinyhdistelmällä ja liittää niitä sitten toiseen raporttiin näppäinyhdistelmällä Ctrl+V.

[**Älykkäät tasauksen apuviivat**](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#smartGuides) Näet älykkäitä tasauksen apuviivoja siirtäessäsi objekteja raporttisivulla, samaan tapaan kuin PowerPointissa. Niiden avulla saat objektit helposti tasattua sivulle. Näet apuviivat aina, kun vedät objektia sivulla tai muutat sen kokoa. Jos siirrät objektin toisen objektin lähelle, se napsahtaa paikalleen tasattuna toisen objektin mukaan.

**Helppokäyttötoiminnot** Liian monia helppokäyttötoimintoja lueteltaviksi: esimerkiksi [Kentät-luetteloruudun helppokäyttöisyyden tuki](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#fieldList). Kentät-luetteloruutu on nyt täysin helppokäyttöinen. Voit siirtyä ruudussa näppäimistön ja näytönlukuohjelman avulla ja lisätä raporttisivuun kenttiä pikavalikosta.

#### <a name="custom-visuals"></a>Mukautetut visualisoinnit

- Tämä versio sisältää ohjelmointirajapinnan version 2.3.

### <a name="administrator-settings"></a>Järjestelmänvalvojan asetukset

Järjestelmänvalvojat voivat määrittää seuraavat palvelinklusterin asetukset SSMS:n lisäasetuksista:

**AllowedResourceExtensionsForUpload** Määritä niiden resurssien tiedostopäätteet, joita raporttipalvelimeen voi ladata. Sisäänrakennettujen tiedostotyyppien tiedostopäätteitä, kuten &ast;.rdl ja &ast;.pbix, ei tarvitse lisätä. Oletusasetus on ”&ast;, &ast;.xml, &ast;.xsd, &ast;.xsl, &ast;.png, &ast;.gif, &ast;.jpg, &ast;.tif, &ast;.jpeg, &ast;.tiff, &ast;.bmp, &ast;.pdf, &ast;.svg, &ast;.rtf, &ast;.txt, &ast;.doc, &ast;.docx, &ast;.pps, &ast;.ppt, &ast;.pptx”. 

**SupportedHyperlinkSchemes** Määrittää CSV-muotoisen luettelon hyperlinkkitoiminnoissa sallituista URI-malleista, joiden hahmontaminen sallitaan. &ast; sallii kaikki hyperlinkkimallit. Esimerkiksi asetus ”http, https” sallisi hyperlinkit osoitteeseen https://www. contoso.com mutta poistaisi hyperlinkit osoitteeseen “mailto:bill@contoso.com” tai javascript:window.open(‘ www.contoso.com’, ‘_blank’). Oletusasetus on &ast;.

## <a name="august-2018"></a>Elokuu 2018

Elokuussa 2018 Power BI -raporttipalvelimelle optimoituun Power BI Desktop -versioon lisättiin paljon uusia ominaisuuksia. Alueittain eriteltynä ne ovat seuraavat:

- [Raportointi](#reporting)
- [Analysointi](#analytics)
- [Mallintaminen](#modeling)

### <a name="highlights-of-the-august-2018-release"></a>Elokuun 2018 julkaisun kohokohdat

Uusia ominaisuuksia on vino pino, mutta seuraavat ovat erityisen kiinnostavia. Lisätietoja saat [blogista](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/).

#### <a name="report-theming"></a>Raportin teema

Elokuun 2018 Power BI -raporttipalvelinversioon on lisätty Raportin teema -ominaisuus, jonka avulla koko raportin värimaailman voi nopeasti muokata vastaamaan teemaa tai yrityksen brändiä. Kun tuot teeman, kaikki kaaviot päivitetään automaattisesti teeman värien mukaisiksi. Teeman värit ovat käytettävissä myös värivalikoimassa. Voit ladata teematiedoston **Vaihda teemaa**-painikkeen alta löytyvällä **Tuo teema** -toiminnolla.

Teematiedosto on JSON-tiedosto. Se sisältää kaikki värit, joita haluat raportissa käytettävän, sekä visualisointien mahdolliset oletusmuotoilut.
Seuraavassa on yksinkertainen JSON-teemamalli, joka päivittää vain raportin oletusvärit:

```json
{
"name": "waveform",
"dataColors": [ "#31B6FD", "#4584D3", "#5BD078", "#A5D028", "#F5C040", "#05E0DB", "#3153FD", "#4C45D3", "#5BD0B0", "#54D028", "#D0F540", "#057BE0" ],
"background":"#FFFFFF",
"foreground": "#F2F2F2",
"tableAccent":"#5BD078"
}
```

#### <a name="conditional-formatting-by-a-different-field"></a>Ehdollinen muotoilu toisen kentän mukaan

Yksi ehdollista muotoilua koskeva merkittävä parannus on mahdollisuus muotoilla sarake jonkin toisen mallissa olevan kentän mukaan.

#### <a name="conditional-formatting-by-values"></a>Ehdollinen muotoilu arvojen mukaan

Toinen uusi ehdollisen muotoilun tyyppi on mahdollisuus käyttää **muotoiluperusteena kentän arvoa**. Kun muotoiluperusteena on kentän arvo, voit määrittää taustan tai fontin värin mittarilla tai sarakkeella, joka sisältää kyseisen värin heksadesimaalikoodin tai nimen.

#### <a name="report-page-tooltips"></a>Raporttisivun työkaluvihjeet

Elokuun 2018 Power BI -raporttipalvelimen päivitys sisältää raporttisivun työkaluvihjetoiminnon. Tämän ominaisuuden avulla voit suunnitella raporttisivun käytettäväksi mukautettuna työkaluvihjeenä raportin muissa visualisoinneissa.

#### <a name="log-axis-improvements"></a>Logaritmisen akselin parannuksia

Karteesisten kaavioiden logaritmista akselia on parannettu merkittävästi. Voit nyt valita logaritmiasteikon minkä tahansa karteesisen kaavion, mukaan lukien yhdistelmäkaavio, numeeriselle akselille, kun käyttämäsi tiedot ovat kokonaan positiivisia tai kokonaan negatiivisia.

#### <a name="sap-hana-sso-direct-query"></a>Suora SAP HANA SSO -kysely

Suoran SAP HANA SSO -kyselyn Kerberos-tuki on nyt käytettävissä Power BI -raporteissa.

>[!Note]
>Tätä skenaariota tuetaan vain, kun SAP HANAa käsitellään suhteellisena tietolähteenä raporteissa, jotka olet luonut Power BI Desktopissa.  Voit ottaa tämän ominaisuuden käyttöön Power BI Desktopissa valitsemalla Asetukset-kohdan DirectQuery-valikosta Käsittele SAP HANAa suhteellisena lähteenä -vaihtoehdon ja valitsemalla OK.

#### <a name="custom-visuals"></a>Mukautetut visualisoinnit

- Tämä versio sisältää ohjelmointirajapinnan version 1.13.0.

- Nyt mukautetuissa visualisoinneissa voidaan palata edelliseen palvelimen nykyisen ohjelmointirajapintaversion kanssa yhteensopivaan versioon (jos sellainen on käytettävissä).

### <a name="reporting"></a>Raportointi 

- [Raportin teema](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#theming)
- [Painikkeet toimintojen käynnistämiseen](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#buttons)
- [Yhdistelmäkaavion viivatyylit](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLines)
- [Parannettu visualisointien oletusarvoinen lajittelu](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sort)
- [Numeerinen osittaja](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#numericSlicer)
- [Kehittynyt osittajan synkronointi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerSync)
- [Logaritmiakselin parannuksia](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#logAxis)
- [Suppilokaavion arvopisteiden otsikkovaihtoehdot](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#funnelChart)
- [Viivanleveyden asettaminen nollaksi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#lineStroke)
- [Suuren kontrastin tuki raporteille](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#highContrast)
- [Renkaan säde -ohjausobjekti](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#donutRadius)
- [Ympyrä- ja rengaskaavion tieto-otsikoiden sijainnin ohjausobjekti](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#detailLabels)
- [Arvopisteiden otsikoiden muotoilu erikseen kullekin yhdistelmäkaavion mittarille](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLabels)
- [Joustavuutta ja muotoilumahdollisuuksia lisäävät uudet visualisoinnin otsikot](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#visualHeader)
- [Taustakuvan muotoilu](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#wallpaper)
- [Taulukoiden ja matriisien työkaluvihjeet](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tableTooltips)
- [Visualisointien työkaluvihjeiden poistaminen käytöstä](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tooltips)
- [Osittajan helppokäyttötoiminnot](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerAccessibility)
- [Muotoiluruudun parannuksia](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#formattingPane)
- [Viiva- ja yhdistelmäkaavioiden askelletun viivan tuki](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#steppedLine)
- [Lajittelun käyttökokemuksen parannus](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sorting)
- [Raporttien tulostaminen Vienti PDF-tiedostoon -toiminnon avulla (Power BI Desktopissa)](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#print)
- [Kirjanmerkkiryhmien luominen](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#bookmarks)
- [Osittajan oikaisu](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicer)
- [Raporttisivun työkaluvihjeet](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#reportPageTooltips)

### <a name="analytics"></a>Analytiikka

- [Uusi DAX-funktio: COMBINEVALUES()](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#combineValues)
- [Mittareihin porautuminen](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#measureDrillthrough)
- [Ehdollinen muotoilu toisen kentän mukaan](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingField)
- [Ehdollinen muotoilu arvojen mukaan](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingValue)

### <a name="modeling"></a>Mallintaminen

- [Suodattaminen ja lajitteleminen tietonäkymässä](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#filterAndSort)
- [Parannettu aluekohtainen muotoilu](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#locale)
- [Mittarien tietoluokat](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dataCategory)
- [Tilastolliset DAX-funktiot](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dax)

## <a name="may-2018"></a>Tou 2018

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>Power BI -iOS-mobiilisovellusten etämäärittäminen raporttipalvelimia varten

IT-ylläpitäjänä voit käyttää organisaatiosi ydintietojen hallintatyökalua etämäärittääksesi raporttipalvelimen käyttöoikeudet Power BI -iOS-mobiilisovellukselle. Lisätietoja saat artikkelista [iOS: Raporttipalvelimen käyttöoikeuksien etämäärittäminen Power BI -iOS-mobiilisovelluksella](configure-powerbi-mobile-apps-remote.md).

## <a name="march-2018"></a>Maaliskuu 2018

Maaliskuussa 2018 Power BI -raporttipalvelimelle optimoituun Power BI Desktop -versioon lisättiin paljon uusia ominaisuuksia. Alueittain eriteltynä ne ovat seuraavat:

- [Visualisoinnit](#visuals-updates)
- [Raportointi](#reporting)
- [Analysointi](#analytics)
- [Suorituskyky](#performance)
- [Raporttipalvelin](#report-server)
- [Muut](#other-improvements)

### <a name="highlights-of-the-march-2018-release"></a>Maaliskuun 2018 julkaisun kohokohdat

Uusia ominaisuuksia on vino pino, mutta seuraavat ovat erityisen kiinnostavia.

#### <a name="rule-based-conditional-formatting-for-table-and-matrix"></a>[Sääntöihin perustuva ehdollinen muotoilu taulukoissa ja matriiseissa](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)

Luo sääntöjä, joiden perusteella taustaväri tai sarakkeen fontin väri valitaan ehdollisesti taulukon tai matriisin liiketoimintalogiikan mukaan.

#### <a name="show-and-hide-pages"></a>[Sivujen näyttäminen ja piilottaminen](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Kuvitellaan, että haluat antaa lukijoillesi raporttisi käyttöoikeudet, mutta jotkut sivut eivät ole täysin valmiit. Nyt voit piilottaa ne, kunnes ne ovat valmiita. Voit myös piilottaa sivut normaalista siirtymisnäkymästä, jolloin lukijat voivat siirtyä sivulle kirjanmerkkien tai porautumisen avulla.

#### <a name="bookmarking"></a>[Kirjanmerkkien lisääminen](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Voit nyt luoda kirjanmerkkejä ja käyttää raporttisi tietoja kerronnan tukena.

- [Kirjanmerkkien ristiinkorostus](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): Kirjanmerkit säilyttävät ja näyttävät raportin sivun, joka korostettiin ristiin kirjanmerkin luontihetkellä.
- [Lisää joustavuutta kirjanmerkkien käyttämiseen](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): Kirjanmerkit heijastavat raportissa määrittämiäsi ominaisuuksia ja vaikuttavat vain valitsemiisi visualisointeihin.

#### <a name="multi-select-data-points-across-multiple-charts"></a>[Monivalinta-arvopisteet useiden kaavioiden välillä](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

Voit valita useita arvopisteitä useista kaavioista ja käyttää ristiinsuodatusta koko sivulla.

#### <a name="sync-slicers-across-multiple-pages-of-your-report"></a>[Osittajien synkronointi usealle raporttisivulle](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

Osittajaa voidaan käyttää yhdellä, kahdella tai useammalla raporttisivulla.

#### <a name="quick-measures"></a>[Pikamittarit](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

Luo uusia mittareita nykyisten mittareiden ja taulukon numeeristen sarakkeiden perusteella.

#### <a name="drilling-down-filters-other-visuals"></a>[Muiden visualisointien suodattaminen poraamalla](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

Kun poraudut jonkin visualisoinnin valittuun luokkaan, voit suodattaa kaikki kyseisen sivun visualisoinnit saman luokan mukaan.

### <a name="visuals-updates"></a>Visualisointien päivitykset

- [Solujen tasaus taulukoissa ja matriisissa](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [Taulukoiden ja matriisien sarakkeiden esitysyksiköt ja tarkka hallinta](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [Ylivuotoarvopisteiden otsikot palkki- ja sarakekaavioissa](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [Arvopisteiden taustavärin hallinta karteesisisten taulukoiden ja karttavisualisoinneissa](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [Palkkien/sarakkeiden täytön hallinta](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [Kaavioakseleiden otsikoiden alan suurentaminen](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [Pistevisualisointi x- ja y-akseliryhmittelyistä](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [Pituus- ja leveyspiireihin perustuva suuren tiheyden näytteenotto kartoissa](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [Reagoivat osittajat](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [Ankkuripäivämäärän lisääminen suhteellisten päivämääräosittajiin](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>Raportointi

- [Visualisoinnin otsikon poistaminen käytöstä raportin lukutilassa](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [Hitaiden tietolähteiden raporttiasetukset](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [Parannettu visualisointien oletussijainti](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [Visualisointien järjestyksen hallinta valintaruudun kautta](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [Raportin objektien lukitseminen](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [Haku muotoilu- ja analyysiruudusta](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [Kentän ominaisuudet -ruutu ja kenttien kuvaukset](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Analytiikka

- [UTCNOW() ja UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [Mukautetun päivämäärätaulukon merkitseminen](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [Poraaminen suodattaa muut visualisoinnit](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [Solutason muotoilu monirivisten korttien moniulotteisissa AS-malleissa](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)

### <a name="performance"></a>Suorituskyky

- [Suodatuksen suorituskyvyn parannuksia](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [DirectQuery-suorituskyvyn parannuksia](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [Avaamisen ja tallentamisen suorituskyvyn parannuksia](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [Parannuksia ”Näytä kohteet, joilla ei ole tietoja” -ominaisuuteen](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)

### <a name="report-server"></a>Raporttipalvelin

#### <a name="export-to-accessible-pdf"></a>Helppokäyttöisen PDF-tiedoston vieminen

Kun viet sivutetun raportin (RDL) PDF-muotoon, saat nyt helppokäyttöisen/tunnisteellisen PDF-tiedoston. Tiedoston koko on tavallista suurempi, mutta tiedosto toimii paremmin näytönlukuohjelmien ja muiden käyttöä helpottavien toimintojen kanssa. Voit ottaa helppokäyttöiset PDF-tiedostot käyttöön määrittämällä **AccessiblePDF** -laitetietojen asetukseksi **Tosi**. Tutustu [PDF-laitetietojen asetusten](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings) ja [laitetietojen asetusten muuttamiseen](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings).

### <a name="other-improvements"></a>Muut parannukset

- [Parannuksia Lisää sarake esimerkeistä -toimintoon](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [Konsultointipalvelut -pikalinkki](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [Paranneltu virheraportointi](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [Aiemmin havaittujen virheiden tarkastelu](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

## <a name="october-2017"></a>Lokakuu 2017

### <a name="power-bi-report-data-sources"></a>Power BI -raporttien tietolähteet

Power BI-raporttipalvelimen Power BI -raportit voivat muodostaa yhteyden erilaisiin tietolähteisiin. Voit tuoda tietoja ja ajoittaa tietojen päivittämisen tai tehdä sille suoran kyselyn DirectQueryn tai reaaliaikaisen SQL Server Analysis Services -palvelun avulla. ”Power BI -raporttien tietolähteet Power BI -raporttipalvelimessa” -kohta sisältää tiedon ajoitettua päivittämistä ja DirectQuerya tukevista tietolähteistä.

### <a name="scheduled-data-refresh-for-imported-data"></a>Ajoitettu tuotujen tietojen päivitys

Power BI -raporttipalvelimen avulla voit määrittää ajoitetun tietojen päivittämisen, joka pitää Power BI -raporttien tiedot ajan tasalla upotetulla mallilla reaaliaikaisen yhteyden tai DirectQueryn asemesta. Tiedot tuodaan upotettuun malliin, joten se ei ole yhteydessä alkuperäiseen tietolähteeseen. Tietojen pitäminen ajan tasalla vaatii päivittämistä, mikä tapahtuu ajoitetun päivittämisen avulla. Lue lisätietoja ”Power BI -raporttien ajoitettu päivittäminen Power BI -raporttipalvelimessa” -kohdasta.

### <a name="editing-power-bi-reports-from-the-server"></a>Palvelimella olevien Power BI -raporttien muokkaaminen

Voit avata ja muokata palvelimella olevia Power BI -raporttitiedostoja (.pbix). Saat lataamasi alkuperäisen tiedoston itsellesi. **Jos palvelin on päivittänyt tiedot, tietoja ei päivitetä, kun avaat tiedoston ensimmäistä kertaa**. Sinun on päivitettävä tiedosto manuaalisesti, jotta muutokset näkyvät.

### <a name="large-file-uploaddownload"></a>Suurten tiedostojen lataaminen palvelimelle tai palvelimelta

Voit ladata enintään 2 Gt:n kokoisia tiedostoja, mutta SQL Server Management Studiossa (SSMS) määritettävissä raporttipalvelimen asetuksissa koon oletusrajoitus on 1 Gt.  Nämä tiedostot on tallennettu tietokantaan samalla tavalla kuin SharePointiin. SQL Serverin luetteloa ei tarvitse määrittää erikseen.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Jaettujen tietojoukkojen käyttö OData-syötteinä

Voit käyttää jaettuja tietojoukkoja OData-syötteellisellä Power BI Desktopilla. Lisätietoja on kohdassa [jaettujen tietojoukkojen käyttö OData-syötteinä Power BI-raporttipalvelimessa](access-dataset-odata.md).

### <a name="scale-out"></a>Skaalattavuus

Tämä versio tukee skaalattavuutta. Kuormituksen tasauksen ja palvelimen affiniteettimäärityksen avulla takaat parhaan käyttökokemuksen. Skenaariota ei ole vielä optimoitu skaalattavuutta varten, joten mallit saatetaan replikoida useille solmuille. Skenaario toimii ilman verkon kuormituksen tasaustoimintoa ja kiinteitä istuntoja. Huomaa kuitenkin, että mallin N-kertaisen lataamisen vuoksi solmut käyttävät tavallista enemmän muistia. Lisäksi yhteyksien välinen suorituskyky heikkenee, kun virtautettu malli kohtaa uuden solmun pyyntöjen välillä.  

### <a name="administrator-settings"></a>Järjestelmänvalvojan asetukset

Järjestelmänvalvojat voivat määrittää seuraavat palvelinklusterin asetukset SSMS:n lisäasetuksista:

* EnableCustomVisuals: Tosi/epätosi
* EnablePowerBIReportEmbeddedModels: Tosi/epätosi
* EnablePowerBIReportExportData: Tosi/epätosi
* MaxFileSizeMb: Oletuksena on nyt 1000
* ModelCleanupCycleMinutes: Kuinka usein mallit tarkistetaan muistista poistamista varten
* ModelExpirationMinutes: Kuinka pitkän käyttämättömyysjakson jälkeen malli vanhenee ja poistetaan
* ScheduleRefreshTimeoutMinutes: Kuinka kauan tietojen päivitys voi kestää mallia kohden. Oletusarvo on kaksi tuntia.  Ylärajaa ei ole.

**Määritystiedosto rsreportserver.config**

```xml
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Kehittäjien ohjelmointirajapinta

SSRS 2017:lle julkaistu kehittäjien ohjelmointirajapinta (REST API) on laajennettu Power BI -raporttipalvelimelle, ja se toimii sekä Excel- että .pbix-tiedostojen kanssa. Eräs mahdollinen käyttötapa on tiedostojen ohjelmallinen lataaminen palvelimelta, niiden päivittäminen ja uudelleenjulkaisu. Tämä esimerkki on ainoa tapa päivittää PowerPivot-malleja sisältävät Excel-työkirjat.

Suurille tiedostoille on uusi ja erillinen ohjelmointirajapinta, jota päivitetään Swaggerin Power BI -raporttipalvelinversiossa. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) -palvelun ja Power BI-raporttipalvelimen muistin käyttö

Power BI-raporttipalvelin toimii nyt sisäisesti SQL Server Analysis Services (SSAS) -palvelimen isäntänä. Tämä ei koske ainoastaan ajoitettua päivittämistä. SSAS:n isännöinti voi suurentaa raporttipalvelimen muistin käyttöä huomattavasti. Palvelinsolmuille on käytettävissä AS.ini-määritystiedosto. Jos SSAS:n käyttö on sinulle tuttua, haluat ehkä päivittää asetukset, kuten muistin käyttörajoituksen, levytilan välimuistiin tallentamisen jne. Katso lisätietoja kohdasta [Palvelinasetukset Analysis Services -palveluissa](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Excel-työkirjojen tarkasteleminen ja käsitteleminen

Excel ja Power BI sisältävät toimialalla ainutlaatuisia työkaluja. Yhdessä ne antavat liiketoiminta-analyytikoille valmiuden tietojen entistä helpompaan keräämiseen, muotoiluun, analyysiin ja visuaaliseen tutkimiseen. Yrityskäyttäjät voivat paitsi tarkastella Power BI -raportteja verkkoportaalissa, myös tehdä saman Excel-työkirjoille Power BI -raporttipalvelimella. Näin he voivat julkaista ja tarkastella itse tuottamaansa Microsoft BI -sisältöä samassa paikassa.

Olemme julkaisseet [vaiheittaisen ohjeet, jotka opastavat Office Onlinen Server (OOS) -palvelimen lisäämisessä Power BI -raporttipalvelimen esikatseluympäristön](excel-oos.md). Volume Licensing -tiliä käyttävät asiakkaat voivat ladata OOS:n Volume License Servicing Centeristä ilmaiseksi. He saavat käyttöönsä vain tarkastelutoiminnot. Kun määritys on valmis, käyttäjät voivat tarkastella ja käsitellä Excel-työkirjoja, jotka:

* ovat riippumattomia ulkoisista tietolähteistä
* ovat reaaliaikaisessa yhteydessä ulkoiseen SQL Server Analysis Services -tietolähteeseen
* sisältävät PowerPivot-tietomallin

### <a name="support-for-new-table-and-matrix-visuals"></a>tukevat uusia taulukko- ja matriisivisualisointeja.

Power BI-raporttipalvelin tukee nyt uusia Power BI -taulukko- ja matriisivisualisointeja. Power BI Desktop -versio on päivitettävä lokakuun 2017 julkaisuversioon, jotta voit luoda kyseisiä visualisointeja sisältäviä raportteja. Versio ei voi olla asennettuna rinnakkain Power BI Desktop (Kesäkuu 2017) -julkaisuversion kanssa. Saat Power BI Desktopin uusimman version [Power BI -raporttipalvelimen lataussivulta](https://powerbi.microsoft.com/report-server/) valitsemalla **lataamisen lisäasetukset**.

## <a name="june-2017"></a>Kesä 2017

* Power BI -raporttipalvelimen GA-versio (generally available, yleisesti saatavana) tulee saataville.

## <a name="may-2017"></a>Toukokuu 2017

* Power BI -raporttipalvelimen esiversio tulee saataville
* Power BI -raporttien paikallinen julkaisemistoiminto
  * mukautettujen visualisointien tuki
  * Vain **reaaliaikaisten Analysis Services -yhteyksien** tuki, lisää tietolähteitä tulossa.
  * Power BI -mobiilisovelluksen päivitys mahdollistaa Power BI -raporttipalvelimella isännöityjen Power BI -raporttien näyttämisen
* Parannellut yhteistyöominaisuudet kommentteja sisältävissä raporteissa

## <a name="next-steps"></a>Seuraavat vaiheet

Katso seuraavat lähteet, joiden avulla pysyt ajan tasalla Power BI -raporttipalvelimen uusista ominaisuuksista.

* [Microsoftin Power BI ‑blogi](https://powerbi.microsoft.com/blog/)
* [Guy in a Cube ‑YouTube-kanava](https://aka.ms/guyinacube)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
