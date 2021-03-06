---
title: Vihjeitä mallisovellusten kehittämiseen Power BI:ssä
description: Vihjeitä, jotka liittyvät kyselyiden, tietomallien, raporttien ja koontinäyttöjen luomiseen hyviä mallisovelluksia varten
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
ms.openlocfilehash: cbc833dea60785f6c3a6eb0298f907221ba38be5
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83332793"
---
# <a name="tips-for-authoring-template-apps-in-power-bi"></a>Vihjeitä mallisovellusten kehittämiseen Power BI:ssä

Kun [kehität mallisovellustasi](service-template-apps-create.md) Power BI:ssä, sinun tulee hallita myös työtilan luonnin, testauksen ja tuotannon logistiikka. Lisäksi sinun tulee luonnollisesti luoda raportti ja koontinäyttö. Luontiprosessin voi jakaa neljään pääosioon. Näiden osioiden avulla voit luoda parhaan mahdollisen mallisovelluksen:

* **Kyselyjen** avulla voit [yhdistää](desktop-connect-to-data.md) ja [muuntaa](../transform-model/desktop-query-overview.md) tietoja sekä määrittää [parametreja](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/). 
* **Tietomallin** avulla voit luoda [suhteita](../transform-model/desktop-create-and-manage-relationships.md), [mittareita](../transform-model/desktop-measures.md) ja Q&A-parannuksia.  
* **[Raportin sivut](../create-reports/desktop-report-view.md)** sisältävät visualisointeja ja suodattimia, jotka antavat merkityksellisiä tietoja.  
* **[Koontinäytöt](../consumer/end-user-dashboards.md)** ja [ruudut](../create-reports/service-dashboard-create.md) antavat yleiskatsauksen mallisovellukseen sisältyvistä merkityksellisistä tiedoista.
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

### <a name="qa"></a>Q&A
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
Mallisovellukset tukevat mallitietoja vain sovelluksissa, joten varmista, että tarkistat staattisen sovelluksen valintaruudun. [Lisätietoja](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Ohjeista validointitiimiä ja kerro, mitä tunnistetietoja ja parametreja vaaditaan tietoihin yhdistämiseen.
* Sovelluksen on sisällettävä sovelluskuvake Power BI:ssä ja CPP-tarjouksessa. [Lisätietoja](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Määritetty aloitussivu. [Lisätietoja](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Muista noudattaa ohjeita kohdassa [Kumppanikeskus -> Power BI:n sovelluksen tarjous](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-power-bi-app-offer).
* Jos koontinäyttö on osa sovellustasi, varmista, että se ei ole tyhjä.
* Asenna sovellus sovelluslinkin avulla ennen sen lähettämistä, ja varmista, että voit yhdistää tietojoukon ja sovelluskokemuksen suunnitelmien mukaan.
* Varmista ennen pbix-tiedoston lataamista mallityötilaan, ettet lataa mitään tarpeettomia yhteyksiä.
* Noudata Power BI:n [parhaita suunnittelukäytäntöjä raporteille ja visualisoinneille](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-best-practices), jotta vaikutat optimaalisesti käyttäjiisi ja saat hyväksynnän jakelulle.
<!--- * In general, only application with valuable functionality can be approved for general use on AppSource. Application with sample data content only must have either a guidance or statistical value.) -->

## <a name="create-a-download-link-for-the-app"></a>Sovelluksen latauslinkin luominen

Kun olet julkaissut mallisovelluksen AppSourcessa, luo latauslinkki sivustoltasi jompaankumpaan seuraavista:
* AppSourcen lataussivu – sivu on julkisesti tarkasteltavissa, hae linkki AppSource-sivultasi.
* Power BI – Power BI -käyttäjät voivat tarkastella tätä.

Katso seuraavasta koodiesimerkistä lisätietoja käyttäjän ohjaamisesta sovelluksen latauslinkkiin Power BI:ssä: [GitHub-säilö](https://github.com/microsoft/Template-apps-examples/tree/master/src).

[![Sovelluksen latauslinkki](media/service-template-apps-tips/service-template-apps-tips-download.png)](https://app.powerbi.com/groups/me/getapps/services/pbi-contentpacks.pbiapps-github)

## <a name="next-steps"></a>Seuraavat vaiheet

[Mitä Power BI -mallisovellukset ovat?](service-template-apps-overview.md)
