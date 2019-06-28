---
title: Power BI:n raportin muodostimella luotavien raporttien suunnitteluvinkkejä
description: Seuraavien vinkkien avulla voit suunnitella sivutettuja raportteja Power BI:n sivutetun raportin muodostimessa.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: c1490ff0-5b8a-43c1-8d22-e459395db4f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: d7e232d09eee2a4cfff17d4565443195e6f7f1aa
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840345"
---
# <a name="report-design-tips-in-power-bi-report-builder"></a>Power BI:n raportin muodostimella luotavien raporttien suunnitteluvinkkejä
  Seuraavien vinkkien avulla voit suunnitella sivutettuja raportteja Power BI:n sivutetun raportin muodostimessa.  
  
   
  
##  <a name="DesigningReports"></a> Raporttien suunnittelu  
  
-   Hyvin suunniteltu raportti välittää tietoja, jotka johtavat toimiin. Määritä kysymykset, joihin voidaan vastata raportin avulla. Pidä kysymykset mielessä raporttia suunnitellessasi.  
  
-   Jotta voit suunnitella tehokkaita tietojen visualisointeja, mieti, miten tiedot näytetään, jotta raportin käyttäjän olisi helppo ymmärtää niitä. Valitse tietoalue, joka vastaa visualisoitavia tietoja hyvin. Esimerkiksi kaavio välittää yhteenveto- ja koostetietoja paremmin kuin taulukko, jossa on yksityiskohtaisia tietoja usealla sivulla. Voit visualisoida minkä tahansa tietojoukon sisältämän tietoalueen tietoja, mukaan lukien kaavioita, karttoja, ilmaisimia, sparkline-kaavioita, tietopalkkeja ja taulukkomuotoisia tietoja erilaisissa tablixiin perustuvissa ruudukkoasetteluissa. 
  
-   Jos haluat toimittaa raportin tietyssä vientimuodossa, testaa vientimuotoa suunnittelun alkuvaiheessa. Ominaisuuksien tuki riippuu valitsemastasi hahmontamistoiminnosta.  
  
-   Kun rakennat monimutkaisia asetteluita, luo asettelu vaiheittain. Voit järjestää raporttikohteet käyttämällä suorakulmioita säilöinä. Voit luoda tietoalueita suoraan suunnittelupinnalle maksimoidaksesi työskentelytilasi. Kun kukin tietoalue on valmis, vedä ne suorakulmiosäilöön. Sisällön sijoittaminen onnistuu yhdellä kertaa, kun käytät suorakulmioita säilöinä. Suorakulmioiden käyttö auttaa hallitsemaan raporttikohteiden hahmontamista kullekin sivulle.  
  
-   Mieti, voisitko parantaa tiettyjen raporttikohteiden näkyvyyttä ja sallia käyttäjien valita, näytetäänkö kohteet. Tämä voit tehdä raportista selkeämmän. Voit määrittää näkyvyyden parametrin tai tekstiruudun vaihtopainikkeen avulla. Voit lisätä ehdollisesti piilotettuja tekstiruutuja näyttääksesi lausekkeiden välivaiheiden tulokset. Kun raportti näyttää odottamattomia tietoja, voit näyttää välivaiheen tulokset vianmäärityksen helpottamiseksi.  
  
-   Käsitellessäsi sisäkkäisiä kohteita tablix-soluissa tai -suorakulmioissa voit määrittää säilölle ja säilössä oleville kohteille erilaisia taustavärejä. Oletusarvoisesti taustaväri on **ei väriä**. Kohteet, joilla on tietty taustaväri, näkyvät sellaisten kohteiden läpi, joille on määritetty taustaväriksi **ei väriä**. Tämän menetelmän avulla voit valita valituille näyttöominaisuuksille oikean kohteen, kuten tablix-solujen reunan näkyvyyden.  
  
 Lisätietoja raportin suunnittelussa huomioitavista seikoista on kohdassa [Raportin suunnittelu raportin muodostimessa](report-builder-planning-report.md)).  
  
##  <a name="NamingConventions"></a> Raporttien, tietolähteiden ja tietojoukkojen nimeämiskäytännöt  
  
-   Käytä nimeämiskäytäntöjä tietolähteille ja tietojoukoille, jotka kuvaavat tietolähdettä.  
  
    1.  **Tietolähteet** Jos et turvallisuussyistä halua käyttää palvelinta tai tietokantaa, käytä aliasta, joka ilmaisee käyttäjälle, mikä tietolähde on.  
  
    2.  **Tietojoukot** Käytä nimeä, joka ilmaisee, mihin tietolähteeseen tietojoukko perustuu.  
  
##  <a name="Data"></a> Tietojen käsitteleminen  
  
-   Aseta aivan aluksi raporttitietoruudussa näkyviksi kaikki tiedot, joita haluat käsitellä. Tarkentaessasi kysymyksiä, joihin raportti vastaa, mieti, miten voit rajoittaa raportin tietojoukkojen tiedot oleelliseen.  
  
-   Yleisesti ottaen sinun kannattaa sisällyttää vain sellaiset tiedot, joiden haluat näkyvän raportissa. Käytä tietojoukkokyselyissä kyselymuuttujia, joiden avulla käyttäjä voi valita näytettävät raporttitiedot. Jos olet luomassa jaettuja tietojoukkoja, voit tarjota samat toiminnallisuudet lisäämällä raporttiparametreihin perustuvia suodattimia.  
  
-   Jos kyselyjen kirjoittaminen on sinulle tuttua, huomaa, että kohtuullisten tietomäärien ryhmittely raporttiin kyselyn sijaan saattaa olla järkevää. Jos kaikki ryhmittelyt ovat kyselyssä, raportista saattaa tulla kyselytulosjoukon esittely. Toisaalta voit näyttää suurista tietomääristä koostettuja arvoja kaaviossa tai matriisissa näyttämättä yksityiskohtaisia tietoja.  
  
-   Voit tarpeen mukaan näyttää raportin tietolähteiden nimet ja sijainnit, tietojoukon kyselyn komentotekstin ja parametriarvot. Monet uudet käyttävät kysyvät ensimmäisenä, mistä tieto on peräisin. Voit ehdollisesti piilottaa tämäntyyppistä tietoja sisältävät tekstiruudut ja antaa käyttäjien valita, haluavatko he nähdä ne. Tämä voi selkeyttää raportin esitystapaa. Kokeile lisätä nämä tiedot raportin viimeiselle sivulle. Määritä tekstiruudun näkyvyys käyttäjän muutettavissa olevan parametrin perusteella.  
  
##  <a name="DesignSurface"></a> Raportin suunnittelualueen käyttö  
 Raportin suunnittelualueessa ei ole WYSIWYG-toimintoa. Kun lisäät raporttikohteita suunnittelualueelle, niiden suhteellinen sijainti vaikuttaa siihen, miltä kohteet näyttävät hahmonnetun raportin sivulla. Välilyönnit säilytetään.  
  
-   Kohdistusapuviivojen ja asettelupainikkeiden avulla voit tasata ja järjestää kohteita raportin suunnittelualueella. Voit esimerkiksi tasata valittujen kohteiden yläosan tai reunat, laajentaa kohteen toisen kohteen kokoa vastaavaksi tai säätää tai kohteiden välejä.  
  
-   Nuolinäppäinten avulla voit säätää suunnittelualueella valittujen kohteiden sijaintia ja kokoa. Esimerkiksi seuraavat näppäinyhdistelmät ovat erittäin käteviä:  
  
    -   **Nuolinäppäimillä** voit siirtää valittua raporttikohdetta.  
  
    -   **CTRL+nuolinäppäimillä** voit siirtää valittua raporttikohdetta vähittäin.  
  
    -   **CTRL+VAIHTO+nuolinäppäimillä** voit suurentaa tai pienentää valitun raporttikohteen kokoa.  
  
-   Voit lisätä kohteen suorakulmioon, osoittamalla hiiren vasemmalla yläkulmalla kohteen alkuperäistä sijaintia suorakulmiosäilössä. Sijoita valitut objektit pikanäppäinten avulla. Suorakulmio laajenee automaattisesti säilössä olevien kohteiden koon mukaan.  
  
-   Jos haluat lisätä useita kohteita tablix-soluun, lisää ensin suorakulmio ja lisää sen jälkeen kohteet.  
  
     Oletuksena jokainen tablix-solu sisältää tekstiruudun. Kun lisäät suorakulmion soluun, suorakulmio korvaa tekstiruudun. Voit lisätä tablix-solun suorakulmioon esimerkiksi sisäkkäisiä ilmaisimia, joiden avulla voit hallita, miten kaavio tai ilmaisin laajenee, kun muutat solun rivin korkeutta.  
  
-   Voit säätää suunnittelualueen näkymääsi **zoomauksen** avulla. Voit käsitellä koko sivua tai sivun osia.  
  
-   Kun vedät kenttiä raportin tietoruudusta Ryhmittely-ruutuun, älä vedä kenttää muiden suunnittelualueella olevien raporttikohteiden yli, koska tällöin muut kohteet valitaan tablix-tietoalueen sijasta. Vedä kenttä alas raportin tietoruutuun ja sitten Ryhmittely-ruutuun.  
  
###  <a name="Selecting"></a> Kohteiden valinta  
 Voit valita haluamasi objektin raportin suunnittelualueelta ESC-näppäimen, hiiren kakkospainikkeen pikavalikon, Ominaisuudet-ruudun ja Ryhmittely-ruudun avulla.  
  
-   -   ESC-näppäintä painamalla voit selata raporttikohteita, jotka on pinottu samaan paikkaan suunnittelualueella.  
  
    -   Joidenkin raporttikohteiden tapauksessa voit kokeilla hiiren kakkospainikkeen pikavalikkoa haluamasi raporttikohteen tai sen osan valintaan.  
  
    -   Ominaisuudet-ruudussa näytetään senhetkisen valinnan ominaisuudet.  
  
    -   Voit käsitellä tablix-tietoalueen rivinryhmiä ja sarakeryhmiä valitsemalla haluamasi ryhmän Ryhmittely-ruudussa.  

  
##  <a name="ReportItems"></a> Tiettyjen raporttikohdetyyppien käsitteleminen  
  
###  <a name="Parameters"></a> Parametrien käsitteleminen  
  
-   Raporttiparametrien ensisijainen tarkoitus on suodattaa tietolähteen sisältö ja noutaa ainoastaan raportin kannalta oleelliset tiedot.  
  
-   Päätä raporttiparametrien osalta, mikä on asianmukainen osallistavan vuorovaikutteisuuden ja käyttäjän auttamisen suhde. Voit esimerkiksi määrittää parametrin oletusarvoiksi arvot, jotka ovat tunnetusti suosittuja.  
  
###  <a name="Text"></a> Tekstin käsitteleminen  
  
-   Kun liität monirivisiä tietoja tekstiruutuun, teksti lisätään yhtenä tekstinä. Kutakin tekstiä voidaan muotoilla vain kokonaisuutena. Voit muotoilla kunkin rivin erikseen lisäämällä tarvittaessa rivinvaihdon Enter-näppäimellä. Voit sen jälkeen käyttää muotoilua ja tyylejä tekstirivin tekstiruuduissa toisistaan riippumatta.  
  
-   Voit määrittää ominaisuudet ja toiminnot tekstiruudussa tai paikkamerkkitekstissä. Jos käytössä on vain yksi tekstirivi, on tehokkaampaa määrittää asetukset tekstiruudussa kuin tekstissä.  
  
###  <a name="Expressions"></a> Lausekkeiden käyttäminen  
  
-   Yksinkertaisten ja monimutkaisten lausekemuotojen ymmärtäminen Voit kirjoittaa yksinkertaisen muotoisia lausekkeita suoraan tekstiruutuihin, Ominaisuudet-ruudun ominaisuuksiin tai valintaikkunoihin, jotka tukevat lausekkeita.
  
-   Lausekkeen luominen helpottuu, kun luot jokaisen osan erikseen ja tarkistat sen arvon. Voit lopuksi yhdistää kaikki osat lopulliseksi lausekkeeksi. Kokeile lisätä tekstiruutu matriisin soluun, näyttää jokainen lausekkeen osa ja määrittää näkyvyys tekstiruudussa. Voit hallita reunan tyyliä ja väriä, kun tekstiruutu on piilotettu, lisää tekstiruudun ensin suorakulmioon ja asettamalla reunan tyylin ja värin matriisin suorakulmion värin mukaiseksi.  
  
###  <a name="Indicators"></a> Ilmaisimien käsitteleminen  
  
-   Ilmaisin näytetään oletuksena vähintään kolmessa tilassa. Kun lisäät raporttiin ilmaisimen raporttiin, voit määrittää sen lisäämällä tai poistamalla tiloja. Käyttäjien on helpompi erottaa väriltään ja muodoltaan erottuva ilmaisin ympäristöstään.  
  
##  <a name="Rendering"></a> Raporttisivun raporttikohteiden hahmontamisen hallinta  
  
-   Raportin suunnittelunalueella olevat raporttikohteet laajenevat niihin liittyvän tietojoukon, lausekkeen, aliraportin tai tekstin sisällön koon mukaan.  
  
    -   Kun asetat kohteen raporttisivulle, kyseisen kohteen ja sen oikealla puolella olevien kohteiden etäisyydestä tulee vähimmäisetäisyys, joka on säilytettävä raporttikohteen kasvaessa vaakasuunnassa. Vastaavasti kohteen ja sen yllä olevan kohteen etäisyydestä tulee vähimmäisetäisyys, joka on säilytettävä ylemmän raporttikohteen kasvaessa pystysuunnassa.  
  
    -   Raportin kohde kasvaa tietojensa koon mukaan ja työntää vertaiskohteet (samaan pääsäilöön sisältyvät) tieltään seuraavien sääntöjen mukaisesti:  
  
    -   Kohteet siirtyvät alaspäin niin, että niiden vähimmäisetäisyys yllä oleviin kohteisiin pysyy vakiona.  
  
    -   Kohteet siirtyvät oikealle niin, että niiden vähimmäisetäisyys vasemmalla oleviin kohteisiin pysyy vakiona. Järjestelmissä, joissa on asettelu oikealta vasemmalle, kohteet siirtyvät vasemmalle niin, että niiden vähimmäisetäisyys oikealla oleviin kohteisiin pysyy vakiona.  
  
    -   Säilöt laajenevat alikohteiden kasvaessa. Ominaisuudet-ruudussa valitun kohteen pääominaisuus ilmaisee kohteen säilön. Voit myös nähdä raporttikohteiden säilöhierarkian Tiedoston jäsennys -ruudussa.  
  
    -   **Asettelu**-työkalurivissä on useita painikkeita, joiden avulla voit tasata raporttikohteiden reunat, keskikohdat ja välistyksen. Ota **Asettelu**-työkalurivi käyttöön **Näkymän**-valikosta osoittamalla **Työkalurivit**-kohtaa ja valitsemalla sitten **Asettelu**.  
  
-   Jos haluat tallentaa raportin .pdf-tiedostona, raportin leveys on määritettävä yksiselitteiseksi arvoksi, joka antaa vientitiedostomuotoon haluamasi tulokset. Voit esimerkiksi määrittää raportin sivun leveydeksi täsmälleen 7,9375 tuumaa sekä vasemman ja oikean reunuksen leveydeksi 0,5 tuumaa.  
  
-   Käytä raportin katseluohjelman työkalurivillä olevaa **Tulostusasettelua** ja **Sivun asetuksia** hahmontaakseesi raportin tulostuksen kanssa sopivaan näkymään. Voit poistaa ei-toivotut vaakasivut seuraavasti:  
  
    1.  Poista kaikki ylimääräiset välilyönnit tietoalueiden välistä ja raportin reunoilta.  
  
    2.  Pienennä sivun reunukset **Raportin ominaisuudet** -valintaikkunassa.  
  
    3.  **Suorakulmioiden** käyttö säilöinä auttaa hallitsemaan raporttikohteiden hahmontamista kullekin sivulle.  
  
    4.  Voit käyttää pystysuuntaista tekstiä muuttamalla WritingMode-tekstiruutuominaisuutta sarakeotsikoista.  
  
 Raporttikohteiden toiminta, leveys- ja korkeusominaisuudet, raportin leipätekstin koko, sivun korkeus- ja leveysmääritys, pääraportin reunusten asetukset ja sivuttamisen hahmontamisesta riippuva tuki yhdessä määrittävät, mitkä raporttikohteet mahtuvat hahmonnetulle sivulle samanaikaisesti. 
 
## <a name="next-steps"></a>Seuraavat vaiheet

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)  
