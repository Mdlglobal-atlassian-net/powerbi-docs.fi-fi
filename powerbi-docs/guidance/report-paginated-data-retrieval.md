---
title: Sivutettujen raporttien tietojen nouto-ohjeet
description: Ohjeet Power BI:n sivutettujen raporttien tietolähteiden ja tietojoukkojen luomiseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
ms.openlocfilehash: 511dc42a3090f838654cda84f596d34f02bb3439
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83275083"
---
# <a name="data-retrieval-guidance-for-paginated-reports"></a>Sivutettujen raporttien tietojen nouto-ohjeet

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee Power BI:n [sivutettuja raportteja](../paginated-reports/paginated-reports-report-builder-power-bi.md). Se sisältää suosituksia, joiden avulla voit suunnitella tehokkaan ja toimivan tietojen noudon.

## <a name="data-source-types"></a>Tietolähdetyypit

Sivutetut raportit tukevat suoraan sekä relaatio- että analyysitietolähteitä. Nämä lähteet luokitellaan edelleen joko pilvipohjaisiksi tai paikallisiksi. Paikalliset tietolähteet – joko paikallisesti tai näennäiskoneessa isännöidyt – edellyttävät tietoyhdyskäytävää, jotta Power BI voi muodostaa yhteyden. Pilvipohjainen tarkoittaa sitä, että Power BI voi muodostaa yhteyden suoraan Internet-yhteyden avulla.

Jos voit valita tietolähdetyypin (kuten mahdollisesti uudessa projektissa), suosittelemme käyttämään pilvipohjaisia tietolähteitä. Sivutetut raportit voivat muodostaa yhteyden pienemmällä verkkoviiveellä etenkin silloin, kun tietolähteet sijaitsevat samalla alueella kuin Power BI -vuokraaja. Voit myös muodostaa yhteyden näihin lähteisiin käyttämällä kertakirjautumista (SSO). Se tarkoittaa, että raportin käyttäjän tiedot voidaan lähettää tietolähteeseen, jolloin käyttäjäkohtaiset rivitason käyttöoikeudet voidaan pakottaa. Tällä hetkellä kertakirjautumista ei tueta paikallisissa tietolähteissä (eli SQL Server Analysis Services ei voi pakottaa käyttäjäkohtaisia rivitason käyttöoikeuksia).

> [!NOTE]
> Vaikka tällä hetkellä ei ole mahdollista muodostaa yhteyttä paikallisiin tietokantoihin kertakirjautumisella, voit silti pakottaa rivitason käyttöoikeudet. Se tehdään välittämällä sisäinen **Käyttäjätunnus**-kenttä tietojoukon kyselyparametriin. Tietolähteen on tallennettava täydellisen käyttäjätunnuksen arvot siten, että se voi suodattaa kyselyn tulokset oikein.
>
> Kukin myyjä voidaan esimerkiksi tallentaa rivinä **Myyjä**-taulukkoon.  Taulukossa on sarakkeet täydelliselle käyttäjätunnukselle ja myös myyjän myyntialueelle. Kyselyn aikana taulukko suodatetaan raportin käyttäjän täydellisen käyttäjätunnuksen mukaan, ja se liittyy myös myyntitietoihin sisäliitoksen avulla. Tällä tavalla kysely suodattaa myyntitietorivit tehokkaasti raportin käyttäjän myyntialueen mukaan.

### <a name="relational-data-sources"></a>Relaatiotietolähteet

Yleensä relaatiotietolähteet soveltuvat hyvin toiminnallistyylisiin raportteihin, kuten myyntilaskuihin. Ne soveltuvat myös raportteihin, joiden on noudettava erittäin suuria tietojoukkoja (yli 10 000 riviä). Relaatiotietolähteet voivat myös määrittää tallennettuja toimintosarjoja, jotka voidaan suorittaa raportin tietojoukkojen mukaan. Tallennetut toimintosarjat tarjoavat useita etuja:

- Parametrisointi
- Ohjelmointilogiikan kapselointi, joka mahdollistaa monimutkaisempien tietojen valmistelun (esimerkiksi tilapäiset taulukot, kohdistimet tai skalaariset käyttäjän määrittämät funktiot)
- Parannettu ylläpidettävyys, joka mahdollistaa tallennetun toimintosarjan logiikan päivittämisen helposti. Joissakin tapauksissa se voidaan tehdä ilman, että sivutettuja raportteja tarvitsee muokata ja julkaista uudelleen (sarakkeiden nimien ja tietotyyppien antaminen pysyy muuttumattomana).
- Parempi suorituskyky, sillä suoritussuunnitelmat on tallennettu välimuistiin uudelleenkäyttöä varten
- Tallennettujen toimintosarjojen uudelleenkäyttö useissa raporteissa

Power BI Report Builderissa voit luoda kyselylausekkeen graafisesti relaatiokyselyjen suunnittelutyökalulla, mutta vain Microsoftin tietolähteille.

### <a name="analytic-data-sources"></a>Analyysitietolähteet

Analyysitietolähteet soveltuvat hyvin sekä toiminta- että analyysiraportteihin, ja ne voivat tuottaa nopeasti yhteenvedon kyselyn tuloksista jopa erittäin suurista tietomääristä. Mallin mittarit ja suorituskykyilmaisimet voivat kapseloida monitasoisia liiketoimintasääntöjä tietojen yhteenvedon tekemistä varten. Nämä tietolähteet eivät kuitenkaan sovellu raportteihin, joiden on noudettava erittäin suuria tietojoukkoja (yli 10 000 riviä).

Power BI Report Builderissa voit valita kahdesta kyselyjen suunnittelutyökalusta: Analysis Servicesin DAX-kyselyjen suunnittelutyökalu ja Analysis Servicesin MDX-kyselyjen suunnittelutyökalu. Näitä suunnittelutyökaluja voidaan käyttää Power BI -tietojoukon tietolähteille tai SQL Server Analysis Servicesin tai Azure Analysis Servicesin malleille – taulukkomuotoisille tai monidimensioisille.

Suosittelemme, että käytät DAX-kyselyjen suunnittelutyökalua, jos se vastaa täysin kyselytarpeitasi. Jos mallissa ei määritetä tarvitsemiasi mittareita, sinun on siirryttävä kyselytilaan. Tässä tilassa voit mukauttaa kyselylauseketta lisäämällä lausekkeita (yhteenvedon saamiseksi).

MDX-kyselyjen suunnittelutyökalu edellyttää, että mallisi sisältää mittarit. Suunnittelutyökalussa on kaksi toimintoa, joita DAX-kyselyjen suunnittelutyökalu ei tue. Sen avulla voit tehdä seuraavaa:

- Määritä kyselytason lasketut jäsenet (MDX:ssä).
- Määritä tietoalueet pyytämään [palvelimen koosteita](/sql/reporting-services/report-design/report-builder-functions-aggregate-function) muissa kuin yksityiskohtaisissa ryhmissä. Jos raportissasi on oltava puolittain lisäävien tai lisäämättömien mittareiden yhteenvetoja (kuten aikatietolaskelmia tai erillisiä määriä), on todennäköisesti tehokkaampaa käyttää palvelimen koosteita kuin noutaa alhaisen tason tietorivejä ja antaa raportin laskea yhteenvetoja.

## <a name="query-result-size"></a>Kyselyn tuloksen koko

Yleensä on parasta noutaa vain raportin edellyttämät tiedot. Älä siis nouda sarakkeita tai rivejä, joita raportti ei edellytä.

Jos haluat rajoittaa rivimäärää, sinun tulee aina käyttää rajoittavimpia suodattimia ja määrittää koostekyselyitä. Koostekyselyt ryhmittelevät lähdetiedot ja tekevät niistä yhteenvedon tarkempien tulosten noutamiseksi. Oletetaan esimerkiksi, että raportissasi on oltava yhteenveto myyjän myynnistä. Luo kaikkien myyntitilausrivien noutamisen sijaan tietojoukkokysely, joka ryhmittelee tiedot myyjän mukaan ja tekee yhteenvedon kunkin ryhmän myynnistä.

## <a name="expression-based-fields"></a>Lausekkeeseen perustuvat kentät

Raportin tietojoukkoon voi lisätä kenttiä lausekkeiden perusteella. Esimerkiksi jos tietojoukko sisältää asiakkaan etunimen ja sukunimen, saatat haluta kentän, joka yhdistää kaksi kenttää tuottaen asiakkaan koko nimen. Sinulla on kaksi vaihtoehtoa tämän toimituksen suorittamiseen. Vaihtoehdot ovat:

- Luo _laskettu kenttä_, joka on lausekkeeseen perustuva tietojoukkokenttä.
- Lisää lauseke suoraan tietojoukkokyselyyn (käyttäen tietolähteen alkuperäistä kieltä), joka tuottaa säännönmukaisen tietojoukkokentän.

Suosittelemme jälkimmäistä vaihtoehtoa aina, kun se on mahdollista. On olemassa kaksi hyvää syytä siihen, miksi lausekkeiden lisääminen suoraan tietojoukkokyselyyn on parempi vaihtoehto:

- On mahdollista, että tietolähteesi on optimoitu arvioimaan lauseke tehokkaammin kuin Power BI (etenkin relaatiotietokantojen tapauksessa).
- Raportin suorituskyky paranee, koska Power BI:n ei tarvitse muodostaa laskettuja kenttiä ennen raportin hahmontamista. Lasketut kentät voivat pidentää raportin hahmontamisaikaa huomattavasti, kun tietojoukot noutavat suuren määrän rivejä.

## <a name="field-names"></a>Kenttien nimet

Kun luot tietojoukon, sen kentät nimetään automaattisesti kyselysarakkeiden mukaan. On mahdollista, että nämä nimet eivät ole kutsumanimiä tai intuitiivisia. On myös mahdollista, että lähdekyselyn sarakkeiden nimissä on merkkejä, jotka on kielletty RDL-objektien tunnisteissa (kuten välilyönnit ja symbolit). Tässä tapauksessa kielletyt merkit korvataan alaviivalla (_).

Suosittelemme, että tarkistat ensin, että kaikki kenttien nimet ovat kutsumanimiä, ytimekkäitä mutta silti merkityksellisiä. Jos ei, suosittelemme, että nimeät ne uudelleen _ennen_ raportin asettelun aloittamista. Tämä johtuu siitä, että uudelleen nimetyt kentät eivät välitä muutoksia raportin asettelussa käytettyihin lausekkeisiin. Jos päätät nimetä kentät uudelleen sen jälkeen, kun olet aloittanut raportin asettelun, sinun on etsittävä ja päivitettävä kaikki katkenneet lausekkeet.

## <a name="filter-vs-parameter"></a>Suodattimen ja parametrin vertailu

Sivutettujen raporttien malleissa on todennäköisesti raporttiparametreja. Raporttiparametreja käytetään yleensä kehottamaan raportin käyttäjää suodattamaan raportti. Sivutetun raportin tekijänä sinulla on kaksi tapaa toteuttaa raportin suodatus. Voit liittää raporttiparametrin jompaankumpaan seuraavista:

- Tietojoukon _suodatin_, jolloin raporttiparametrin arvoja käytetään tietojoukon jo noutamien tietojen suodattamiseen.
- Tietojoukon _parametri_, jolloin raporttiparametrin arvot lisätään tietolähteeseen lähetettyyn alkuperäiseen kyselyyn.

> [!NOTE]
> Kaikki raportin tietojoukot tallennetaan välimuistiin _istuntokohtaisesti_ enintään 10 minuuttia _viimeisen käytön jälkeen_. Tietojoukkoa voidaan käyttää uudelleen, kun lähetetään uusia parametriarvoja (suodatus), hahmonnetaan raportti eri muodossa tai käsitellään raportin rakennetta jollakin tavalla, kuten vaihdetaan näkyvyyttä tai lajitellaan.

Käytetään esimerkkinä myyntiraporttia, jossa on yksi raporttiparametri raportin suodattamiseksi yhden vuoden mukaan. Tietojoukko noutaa _kaikkien vuosien_ myynnin. Tämä johtuu siitä, että raporttiparametri liittyy tietojoukon suodattimiin. Raportti näyttää pyydetyn vuoden tiedot, joka on tietojoukon tietojen alijoukko. Kun raportin käyttäjä muuttaa raporttiparametrin eri vuoteen ja tarkastelee sitten raporttia, Power BI:n ei tarvitse noutaa lähdetietoja. Sen sijaan se käyttää eri suodatinta jo välimuistissa olevaan tietojoukkoon. Kun tietojoukko on välimuistissa, suodattaminen voi olla erittäin nopeaa.

Käsitellään nyt erilaista raportin rakennetta. Tällä kertaa raportin rakenne liittää myyntivuoden raporttiparametrin tietojoukkoparametriin. Näin Power BI lisää vuosiarvon alkuperäiseen kyselyyn, ja tietojoukko noutaa vain kyseisen vuoden tiedot. Aina, kun raportin käyttäjä muuttaa vuosiraportin parametrin arvoa ja tarkastelee sitten raporttia, tietojoukko noutaa uuden kyselyn tuloksen vain kyseiselle vuodelle.

Kummallakin menetelmällä voidaan suodattaa raporttitietoja, ja kumpikin voi toimia hyvin raporttirakenteissasi. Optimoitu rakenne riippuu kuitenkin ennakoiduista tietomääristä, tietojen vaihtelusta ja raportin käyttäjien ennakoidusta toiminnasta.

Suosittelemme _tietojoukon suodatusta_, kun arvelet, että tietojoukon rivien eri alijoukkoja käytetään uudelleen monta kertaa (mikä säästää hahmontamisaikaa, koska uusia tietoja ei tarvitse noutaa). Tässä skenaariossa tiedostat, että suuremman tietojoukon noutamisen kustannuksien vastineeksi tietojoukkoa voidaan käyttää uudelleen. Siitä on siis hyötyä kyselyissä, joiden luominen vie aikaa. Ole kuitenkin varovainen, sillä suurien tietojoukkojen tallentaminen välimuistiin käyttäjäkohtaisesti voi vaikuttaa haitallisesti suorituskykyyn ja siirtokapasiteettiin.

Suosittelemme _tietojoukon parametrointia_, kun on oletettavasti epätodennäköistä, että pyydetään tietojoukon rivien eri alijoukkoa, tai kun suodatettavien tietojoukon rivien määrä on todennäköisesti hyvin suuri (ja välimuistiin tallentaminen tehotonta). Tämä menetelmä toimii hyvin myös silloin, kun tietosäilö on muuttuva. Tässä tapauksessa kunkin raporttiparametrin arvon muutos johtaa ajan tasalla olevien tietojen noutamiseen.

## <a name="non-native-data-sources"></a>Muut kuin alkuperäiset tietolähteet

Jos sinun on luotava sivutettuja raportteja sellaisten tietolähteiden perusteella, joita [sivutetut raportit eivät suoraan tue](../paginated-reports/paginated-reports-data-sources.md), voit kehittää ensin Power BI Desktop -tietomallin. Näin voit muodostaa yhteyden yli 100 [Power BI -tietolähteeseen](../connect-data/power-bi-data-sources.md). Kun olet julkaissut Power BI -palvelussa, voit luoda sivutetun raportin, joka muodostaa yhteyden Power BI -tietojoukkoon.

## <a name="data-integration"></a>Tietojen integrointi

Jos sinun on yhdistettävä tietoja useista tietolähteistä, sinulla on kaksi vaihtoehtoa:

- **Yhdistä raportin tietojoukot**: Jos [sivutetut raportit tukevat tietolähteitä suoraan](../paginated-reports/paginated-reports-data-sources.md), voit halutessasi luoda laskettuja kenttiä, jotka käyttävät Report Builderin [Lookup](/sql/reporting-services/report-design/report-builder-functions-lookup-function)- tai [LookupSet](/sql/reporting-services/report-design/report-builder-functions-lookupset-function)-funktioita.
- **Luo Power BI Desktop -malli**: On kuitenkin tehokkaampaa, että luot tietomallin Power BI Desktopissa. Power Queryn avulla voit yhdistää kyselyitä minkä tahansa [tuetun tietolähteen](../connect-data/power-bi-data-sources.md) perusteella. Kun olet julkaissut Power BI -palvelussa, voit luoda sivutetun raportin, joka muodostaa yhteyden Power BI -tietojoukkoon.

## <a name="sql-server-complex-data-types"></a>SQL Serverin monimutkaiset tietotyypit

Koska SQL Server on paikallinen tietolähde, Power BI:n on muodostettava yhteys yhdyskäytävän kautta. Yhdyskäytävä ei kuitenkaan tue monimutkaisten tietotyyppien tietojen noutamista. Monimutkaisia tietotyyppejä ovat sisäiset tyypit, kuten [spatiaaliset tietotyypit](/sql/relational-databases/spatial/spatial-data-sql-server) GEOMETRIATIETO ja PAIKKATIETO sekä [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference). Ne voivat myös sisältää käyttäjän määrittämiä tyyppejä, jotka on otettu käyttöön kokoonpanoluokan kautta Microsoft.NET Framework -suorituspalvelussa (CLR).

Spatiaalisten tietojen ja analytiikan piirtäminen kartan visualisointiin edellyttää SQL Serverin spatiaalisia tietoja. Näin ollen kartan visualisointia ei voi käyttää, kun SQL Server on tietolähteesi. Se siis toimii, jos tietolähde on Azuren SQL-tietokanta, koska Power BI ei muodosta yhteyttä yhdyskäytävän kautta.

## <a name="data-related-images"></a>Tietoihin liittyvät kuvat

Kuvia voidaan käyttää logojen tai valokuvien lisäämiseksi raportin asetteluun. Kun kuvat liittyvät raportin tietojoukon noutamiin riveihin, sinulla on kaksi vaihtoehtoa:

- On mahdollista, että kuvatiedot voidaan noutaa myös tietolähteestä (jos ne on jo tallennettu taulukkoon).
- Kun kuvat on tallennettu WWW-palvelimelle, voit luoda kuvan URL-polun dynaamisen lausekkeen avulla.

Lisätietoja ja ehdotuksia on kohdassa [Sivutettujen raporttien kuvaohjeet](report-paginated-image.md).

## <a name="redundant-data-retrieval"></a>Tarpeettomien tietojen noutaminen

On mahdollista, että raporttisi noutaa tarpeettomia tietoja. Näin voi käydä, kun poistat tietojoukon kyselykenttiä tai raportissa on käyttämättömiä tietojoukkoja. Vältä näitä tilanteita, sillä ne aiheuttavat tarpeettoman taakan tietolähteillesi, verkolle ja Power BI:n kapasiteettiresursseille.

### <a name="deleted-query-fields"></a>Poistetut kyselykentät

**Tietojoukon ominaisuudet** -ikkunan **Kentät**-sivulla on mahdollista poistaa tietojoukon _kyselykenttiä_ (kyselykentät liittyvät tietojoukkokyselyn noutamiin sarakkeisiin). Report Builder ei kuitenkaan poista vastaavia sarakkeita tietojoukon kyselystä.

Jos sinun on poistettava kyselykenttiä tietojoukosta, suosittelemme, että poistat vastaavat sarakkeet tietojoukon kyselystä. Report Builder poistaa automaattisesti tarpeettomat kyselykentät. Jos poistat kyselykenttiä, muista myös muokata tietojoukon kyselylauseketta sarakkeiden poistamiseksi.

### <a name="unused-datasets"></a>Käyttämättömät tietojoukot

Kun raportti suoritetaan, kaikki tietojoukot arvioidaan, vaikka niitä ei ole sidottu raporttiobjekteihin. Muista tämän vuoksi poistaa kaikki testi- tai kehitystietojoukot ennen raportin julkaisemista.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

- [Power BI:n sivutetuissa raporteissa tuetut tietolähteet](../paginated-reports/paginated-reports-data-sources.md)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
