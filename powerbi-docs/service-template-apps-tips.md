---
title: Vihjeitä mallisovellusten kehittämiseen Power BI:ssä
description: Vihjeitä, jotka liittyvät kyselyiden, tietomallien, raporttien ja koontinäyttöjen luomiseen hyviä mallisovelluksia varten
author: teddybercovitz
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/26/2019
ms.author: tebercov
ms.openlocfilehash: 5e34601c3ebacb3cfd8a4a5ddeb282756d0f700b
ms.sourcegitcommit: 1789815c87e306b1427a5838655d30d3b9ba1d29
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/11/2019
ms.locfileid: "67791817"
---
# <a name="tips-for-authoring-template-apps-in-power-bi"></a>Vihjeitä mallisovellusten kehittämiseen Power BI:ssä

Kun [kehität mallisovellustasi](service-template-apps-create.md) Power BI:ssä, sinun tulee hallita myös työtilan luonnin, testauksen ja tuotannon logistiikka. Lisäksi sinun tulee luonnollisesti luoda raportti ja koontinäyttö. Luontiprosessin voi jakaa neljään pääosioon. Näiden osioiden avulla voit luoda parhaan mahdollisen mallisovelluksen:

* **Kyselyjen** avulla voit [yhdistää](desktop-connect-to-data.md) ja [muuntaa](desktop-query-overview.md) tietoja sekä määrittää [parametreja](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/). 
* **Tietomallin** avulla voit luoda [suhteita](desktop-create-and-manage-relationships.md), [mittareita](desktop-measures.md) ja Q&A-parannuksia.  
* **[Raportin sivut](desktop-report-view.md)** sisältävät visualisointeja ja suodattimia, jotka antavat merkityksellisiä tietoja.  
* **[Koontinäytöt](consumer/end-user-dashboards.md)** ja [ruudut](service-dashboard-create.md) antavat yleiskatsauksen mallisovellukseen sisältyvistä merkityksellisistä tiedoista.
* Mallitietojen avulla löydät sovelluksen heti asennuksen jälkeen.

Nämä voivat olla tuttuja nykyisten Power BI -ominaisuuksien kautta. Kun luot mallisovellusta, kuhunkin osioon liittyy muitakin huomioon otettavia seikkoja. Lisätietoja on seuraavissa osissa.

<a name="queries"></a>

## <a name="queries"></a>Kyselyt
Power BI Desktopissa luotuja kyselyitä käytetään mallisovelluksissa tietolähteen yhdistämiseen ja tietojen tuomiseen. Näitä kyselyjä tarvitaan yhtenäisen rakenteen palauttamiseen, ja niitä tuetaan tietojen ajoitetussa päivityksessä (DirectQuery-kyselyitä ei tueta).

### <a name="connect-to-your-api"></a>Ohjelmointirajapintaan yhdistäminen
Aloita kyselyiden rakentaminen muodostamalla yhteys Power BI Desktopista ohjelmointirajapintaasi.

Voit käyttää ohjelmointirajapintaan yhdistämiseen tietoyhdistimiä, jotka ovat käytettävissä Power BI Desktopissa. Voit käyttää verkkotietojen yhdistintä (Hae tiedot -> Verkko) Rest-ohjelmointirajapinnan yhdistämiseen tai OData-yhdistintä (Hae tiedot -> OData-syöte) OData-syötteen yhdistämiseen.

> [!NOTE]
> Tällä hetkellä mallisovellukset eivät tue mukautettuja yhdistimiä, joten on suositeltavaa tutustua Odatafeed Auth 2.0:iin korjauskeinona joitakin yhteyskäyttötapauksia varten tai lähettää yhdistin sertifiointia varten. Lisätietoja yhdistimen kehittämisestä ja sertifioinnista on [tietoyhdistimien ohjeissa](https://aka.ms/DataConnectors).

### <a name="consider-the-source"></a>Huomioi lähde
Kyselyt määrittelevät tiedot, jotka sisällytetään tietomalliin. Järjestelmäsi koosta riippuen näissä kyselyissä on myös oltava suodattimia, jotta koko on asiakkaittesi kannalta hallittavissa ja sopii liiketoimintaskenaarioosi.

Power BI -mallisovellukset voivat suorittaa useita kyselyitä rinnakkain ja useille käyttäjille samanaikaisesti.  Suunnittele etukäteen rajoittamisen ja samanaikaisuuden strategia ja kysy meiltä neuvoa siihen, miten mallisovelluksesta luodaan vikasietoinen.

### <a name="schema-enforcement"></a>Rakenteen pakottaminen
Varmista, että kyselysi kestävät järjestelmäsi muutokset. Rakenteen muutokset tai päivitys voi rikkoa mallin. Jos lähde voi palauttaa joillekin kyselyille tyhjäarvon tai puuttuvan rakenteen, harkitse tyhjän taulukon tai käyttäjää auttavan mukautetun virhesanoman palauttamista.

### <a name="parameters"></a>Parametrit
Power BI Desktop -version [parametrien](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) avulla käyttäjät voivat syöttää arvoja, jotka mukauttavat käyttäjän hakemia tietoja. Mieti parametreja jo etukäteen, jotta rakentamiasi yksityiskohtaisia kyselyitä tai raportteja ei tarvitse työstää jälkikäteen.

> [!NOTE]
> Mallisovellukset tukevat kaikkia parametreja lukuun ottamatta parametreja Any ja Binary.
>

### <a name="additional-query-tips"></a>Lisää kyselyvihjeitä

* Varmista, että kaikki sarakkeet on kirjoitettu oikein.
* Sarakkeissa tulee olla informatiiviset nimet (katso [Kysymykset ja vastaukset](#qa)).  
* Jaetun logiikan kannalta kannattaa harkita funktioiden tai kyselyiden käyttöä.  
* Yksityisyystasoja ei tällä hetkellä tueta palvelussa. Jos näyttöön ilmestyy yksityisyystasoihin liittyvä kehote, kysely on ehkä kirjoitettava uudelleen, niin että se käyttää suhteellisia polkuja.  

## <a name="data-models"></a>Tietomallit

Hyvin määritelty tietomalli takaa, että asiakkaasi voivat käyttää mallisovellusta helposti ja intuitiivisesti. Luo tietomalli Power BI Desktopissa.

> [!NOTE]
> Tee suurin osa perusmallintamisesta (kirjoitus, sarakkeiden nimet) [kyselyissä](#queries).

### <a name="qa"></a>Kysymykset ja vastaukset
Mallintaminen vaikuttaa myös siihen, kuinka hyvin kysymykset ja vastaukset tarjoavat tuloksia asiakkaillesi. Muista lisätä usein käytettyihin sarakkeisiin synonyymeja ja varmista, että olet nimennyt sarakkeet oikein [kyselyissä](#queries).

### <a name="additional-data-model-tips"></a>Lisävihjeitä tietomalleista

Varmista, että olet:

* käyttänyt muotoilua kaikissa arvosarakkeissa käyttänyt tyyppejä kyselyssä  
* käyttänyt muotoilua kaikissa mittareissa
* määrittänyt oletusyhteenvedon, erityisesti ”Älä tee yhteenvetoa” -vaihtoehdon soveltuvissa tapauksissa (esimerkiksi yksilöllisille arvoille)  
* määrittänyt tietoluokan soveltuvissa tapauksissa  
* määrittänyt suhteet tarpeen mukaan.  

## <a name="reports"></a>Raportit
Raporttisivut antavat lisää merkityksellisiä tietoja mallisovellukseesi sisältyvistä tiedoista. Vastaa raporttisivuilla keskeisiin liiketoiminnallisiin kysymyksiin, joihin mallisovelluksesi pyrkii vastaamaan. Luo raportti Power BI Desktopin avulla.


### <a name="additional-report-tips"></a>Lisävihjeitä raportteihin

* Käytä sivulla useampaa kuin yhtä visualisointia ristiinsuodatusta varten.  
* Tasaa visualisoinnit huolellisesti (ei päällekkäisyyksiä).  
* Sivu on määritetty kuvasuhteeseen 4:3 tai 16:9 asettelua varten.  
* Kaikki esitetyt koosteet ovat numeerisesti järkeenkäypiä (keskiarvot, yksilölliset arvot).  
* Jaottelu tuottaa rationaalisia tuloksia.  
* Logo on näkyvissä vähintään raportin yläosassa.  
* Elementit ovat asiakkaan värimallin mukaisia siinä määrin kuin mahdollista.  

<a name="dashboard"></a>

## <a name="dashboards"></a>Koontinäytöt
Koontinäyttö on mallisovelluksesi tärkein vuorovaikutuspiste asiakkaittesi kannalta. Siinä tulisi olla yleiskatsaus paketin sisällöstä ja erityisesti liiketoimintaskenaariosi tärkeistä metriikoista.

Voit luoda mallisovelluksellesi koontinäytön lataamalla PBIX-tiedoston kohdassa Hae tiedot > Tiedostot tai julkaisemalla sen suoraan Power BI Desktopin kautta.


### <a name="additional-dashboard-tips"></a>Lisää koontinäyttövihjeitä

* Säilytä sama teema kiinnittäessäsi, jotta koontinäyttösi ruudut ovat yhtenäisiä.  
* Kiinnitä teemaan logo, jotta kuluttajat tietävät, mistä paketti on peräisin.  
* Suositeltava asettelu useimmilla näytön tarkkuuksilla on 5–6 pientä ruutua leveä.  
* Kaikissa koontinäytön ruuduissa tulee olla asianmukainen otsikko tai alaotsikko.  
* Harkitse koontinäytön sisällön ryhmittelyä eri skenaarioita varten joko pysty- tai vaakasuunnassa.  

## <a name="sample-data"></a>Mallitiedot
Mallisovellukset lisäävät sovelluksen luomisvaiheen osana välimuistitiedot työtilaan osana sovellusta:

* Niiden avulla asentaja voi ymmärtää toimintoa ja sovelluksen tarkoituksen ennen tietojen yhdistämistä.
* Ne luovat kokemuksen, jonka ansiosta asentaja tutustuu tarkemmin sovelluksen ominaisuuksiin ja sovelluksen tietojoukon yhdistämiseen.

Suosittelemme hankkimaan laadukkaita mallitietoja ennen sovelluksen luomista. Varmista, että sovelluksen raportti ja koontinäytöt täytetään tiedoilla.

## <a name="publishing-on-appsource"></a>Julkaisu AppSourceen
Mallisovellukset voidaan julkaista AppSourcessa. Noudata seuraavia ohjeita ennen sovelluksen lähettämistä AppSourceen:

* Varmista, että luot mallisovelluksen käyttämällä mielenkiintoisia mallitietoja, jotka auttavat asentajaa ymmärtämään sovelluksen toimintoja (tyhjää raporttia ja koontinäyttöä ei hyväksytä).
Mallisovellukset tukevat mallitietoja vain sovelluksissa, joten varmista, että tarkistat staattisen sovelluksen valintaruudun. [Lue lisää](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Yleensä vain sovellus, jossa on hyödyllisiä ominaisuuksia, voidaan hyväksyä yleisesti käytettäväksi AppSourcessa. Vain mallitietosisältöä sisältävällä sovelluksella on oltava joko ohjaava tai tilastoanalyyttinen arvo.
* Ohjeista validointitiimiä ja kerro, mitä tunnistetietoja ja parametreja vaaditaan tietoihin yhdistämiseen.
* Sovelluksen on sisällettävä sovelluskuvake Power BI:ssä ja CPP-tarjouksessa. [Lue lisää](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Määritetty aloitussivu. [Lue lisää](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Muista noudattaa [Power BI:n sovelluksen tarjouksen](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer) ohjeita.
* Jos koontinäyttö on osa sovellustasi, varmista, että se ei ole tyhjä.
* Asenna sovellus sovelluslinkin avulla ennen sen lähettämistä, ja varmista, että voit yhdistää tietojoukon ja sovelluskokemuksen suunnitelmien mukaan.
* Varmista ennen bpix-tiedoston lataamista mallisovelluksen työtilaan, ettet lataa mitään tarpeettomia yhteyksiä.
* Noudata Power BI:n [parhaita suunnittelukäytäntöjä raporteille ja visualisoinneille](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-best-practices), jotta vaikutat optimaalisesti käyttäjiisi ja saat hyväksynnän jakelulle.

## <a name="known-limitations"></a>Tunnetut rajoitukset

| Ominaisuus | Tunnettu rajoitus |
|---------|---------|
|Sisältö:  Tietojoukot   | Tarkalleen yhden tietojoukon tulee olla käytössä. Vain Power BI Desktopissa luodut tietojoukot (.pbix-tiedostot) sallitaan. <br>Ei tueta: Tietojoukkoja, jotka ovat peräisin muista mallisovelluksista, työtilojen välisiä tietojoukkoja, sivuttuja raportteja (.rdl-tiedostot), Excel-työkirjoja |
|Sisältö: Koontinäytöt | Reaaliaikaisia ruutuja ei sallita (toisin sanoen push-ilmoituksia tai tietojoukkojen suoratoistoa ei tueta) |
|Sisältö: Tietovuot | Ei tueta: Tietovuot |
|Tiedostojen sisällöt | Vain PBIX-tiedostot sallitaan. <br>Ei tueta: .rdl-tiedostot (sivutetut raportit), Excel-työkirjat   |
| Tietolähteet | Pilvipohjaista ajoitettua tietojen päivittämistä tukevat tietolähteet sallitaan. <br>Ei tueta: <li> DirectQuery</li><li>Reaaliaikaiset yhteydet (Azure AS ei käy)</li> <li>Paikalliset tietolähteet (henkilökohtaiset yhdyskäytävät ja yritysyhdyskäytävät eivät ole tuettuja)</li> <li>Reaaliaikainen (push-tietojoukkoa ei tueta)</li> <li>Yhdistelmämallit</li></ul> |
| Tietojoukko: työtilojen välinen | Työtilojen välisiä tietojoukkoja ei sallita  |
| Kyselyparametrit | Ei tueta: Tyyppiä ”Any” tai ”Binary” olevat parametrit estävät tietojoukon päivitystoiminnon |
| Mukautetut visualisoinnit | Vain julkisesti käytettävissä olevia mukautettuja visualisointeja tuetaan. [Organisaation mukautettuja visualisointeja](power-bi-custom-visuals-organization.md) ei tueta. |

## <a name="next-steps"></a>Seuraavat vaiheet

[Mitä Power BI -mallisovellukset ovat?](service-template-apps-overview.md)
