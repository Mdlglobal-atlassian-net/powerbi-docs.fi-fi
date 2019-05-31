---
title: Vihjeitä mallisovellusten luomiseen Power BI:ssä (esikatselu)
description: Vihjeitä, jotka liittyvät kyselyiden, tietomallien, raporttien ja koontinäyttöjen luomiseen hyviä mallisovelluksia varten
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/19/2019
ms.author: maggies
ms.openlocfilehash: 83049a16ecd42b41375da57a5a99a374596a9846
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514857"
---
# <a name="tips-for-authoring-template-apps-in-power-bi-preview"></a>Vihjeitä mallisovellusten luomiseen Power BI:ssä (esikatselu)

Kun [kehität mallisovellustasi](service-template-apps-create.md) Power BI:ssä, sinun tulee hallita myös työtilan luonnin, testauksen ja tuotannon logistiikka. Lisäksi sinun tulee luonnollisesti luoda raportti ja koontinäyttö. Luontiprosessin voi jakaa neljään pääosioon. Näiden osioiden avulla voit luoda parhaan mahdollisen mallisovelluksen:

* **Kyselyjen** avulla voit [yhdistää](desktop-connect-to-data.md) ja [muuntaa](desktop-query-overview.md) tietoja sekä määrittää [parametreja](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/). 
* **Tietomallin** avulla voit luoda [suhteita](desktop-create-and-manage-relationships.md), [mittareita](desktop-measures.md) ja Q&A-parannuksia.  
* **[Raportin sivut](desktop-report-view.md)** sisältävät visualisointeja ja suodattimia, jotka antavat merkityksellisiä tietoja.  
* **[Koontinäytöt](consumer/end-user-dashboards.md)** ja [ruudut](service-dashboard-create.md) antavat yleiskatsauksen mallisovellukseen sisältyvistä merkityksellisistä tiedoista.
* Mallitietojen avulla sovelluksesi löydettävä heti asennuksen jälkeen.

Nämä voivat olla tuttuja nykyisten Power BI -ominaisuuksien kautta. Kun luot mallisovellusta, kuhunkin osioon liittyy muitakin huomioon otettavia seikkoja. Lisätietoja on seuraavissa osissa.

<a name="queries"></a>

## <a name="queries"></a>Kyselyt
Power BI Desktopissa luotuja kyselyitä käytetään mallisovelluksissa tietolähteen yhdistämiseen ja tietojen tuomiseen. Näitä kyselyjä tarvitaan yhtenäisen rakenteen palauttamiseen, ja niitä tuetaan tietojen ajoitetussa päivityksessä (DirectQuery-kyselyitä ei tueta).

### <a name="connect-to-your-api"></a>Ohjelmointirajapintaan yhdistäminen
Aloita kyselyiden rakentaminen muodostamalla yhteys Power BI Desktopista ohjelmointirajapintaasi.

Voit käyttää ohjelmointirajapinnan yhdistämiseen tietoyhdistimiä, jotka ovat valmiina Power BI Desktop -versiossa. Voit käyttää verkkotietojen yhdistintä (Hae tiedot -> Verkko) Rest-ohjelmointirajapinnan yhdistämiseen tai OData-yhdistintä (Hae tiedot -> OData-syöte) OData-syötteen yhdistämiseen. Nämä yhdistimet toimivat suoraan vain, jos ohjelmointirajapintasi tukee perustodennusta.

> [!NOTE]
> Jos ohjelmointirajapintasi käyttää mitä tahansa muuta todennustyyppiä, kuten OAuth 2.0 -todennusta tai verkkopalvelujen ohjelmointirajapinnan avainta, sinun on kehitettävä oma tietoyhdistin, jotta Power BI Desktop voi muodostaa yhteyden ohjelmointirajapintaasi ja todentaa sen. Mukautetun liittimen on lisättävä PBI-palveluun, jotta se voi käyttää mallia sovelluksen asennusohjelma. <br> Lisätietoja oman tietoyhdistimen kehittämisestä mallisovellustasi varten saat [tietoyhdistimien ohjeista](https://aka.ms/DataConnectors). 
>
>

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
Mallin sovelluksia sovelluksen luomisen vaiheessa osana rivittyy välimuistitiedot osana sovelluksen työtilassa:

* Avulla voit ymmärtää toimintoja ja sovelluksen tarkoitus ennen kuin muodostat tiedot.
* Luo käyttökokemus, joka määrittää asennusohjelma voit tutustua tarkemmin sovelluksen ominaisuuksia, mikä johtaa yhdistämistä sovelluksen tietojoukon.

On suositeltavaa ottaa laatu mallitietoja, ennen kuin luot sovelluksen. Varmista, että sovelluksen raportin ja koontinäyttöjä täytetään tiedoilla.

## <a name="publishing-on-appsource"></a>Julkaiseminen appsourcessa
Mallin sovellukset voidaan julkaista appsourcessa, seuraavien ohjeiden mukaisesti ennen sovelluksesi appsourceen lähettämistä:

* Varmista, että luot mallin sovelluksen käyttävät mallitietoja, jotka auttavat ymmärtämään sovelluksen tehdä asennusohjelma (tyhjä raportin ja koontinäytön eivät ole hyväksytyt).
Mallin sovellukset tukevat tiedot vain Mallisovelluksia, varmista, että staattinen app-valintaruutu. [Lue lisää](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Ole vahvistus-tiimin seurata, joka sisältää tunnistetiedot ja parametreja, jotka tarvitaan yhteyden muodostamiseen tietojen Ohje.
* Sovelluksen on oltava sovelluksen kuvake Power BI-ja CPP tarjous. [Lue lisää](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Määritetty aloitussivu. [Lue lisää](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Varmista, että dokumentaatiosta seuraamalla [Power BI-sovellus tarjouksen](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).
* Koontinäyttö on osa sovellukseesi, varmista, että se ei ole tyhjä.
* Asenna sovellus app-linkin avulla ennen sen lähettämistä, varmista, että voit muodostaa tietojoukon ja sovelluksen käyttökokemus on suunniteltu voit.
* Ennen lataamista bpix mallin sovelluksen työtilaan, varmista, että lataamisen tarpeettomat yhteyksiä.
* Noudata Power BI [parhaat suunnittelukäytännöt raporttien ja visualisointien](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-best-practices) saavuttamiseksi suurin vaikutus käyttäjät ja hyväksytään jaettavaksi.

## <a name="known-limitations"></a>Tunnetut rajoitukset

| Ominaisuus | Tunnettu rajoitus |
|---------|---------|
|Sisältö:  Tietojoukot   | Tarkalleen yhden tietojoukon tulee olla käytössä. Vain Power BI Desktopissa luodut tietojoukot (.pbix-tiedostot) sallitaan. <br>Ei tueta: Tietojoukkoja, jotka ovat peräisin muista mallisovelluksista, työtilojen välisiä tietojoukkoja, sivuttuja raportteja (.rdl-tiedostot), Excel-työkirjoja |
|Sisältö: koontinäytöt | Reaaliaikaisia ruutuja ei sallita (toisin sanoen ei tue push- tai suoratoistettaviin tietojoukkoihin) |
|Sisältö: Tietovuot | Ei tueta: Tietovuot |
|Tiedostojen sisällöt | Vain PBIX-tiedostot sallitaan. <br>Ei tueta: .rdl-tiedostot (sivutetut raportit), Excel-työkirjat   |
| Tietolähteet | Pilvipohjaista ajoitettua tietojen päivittämistä tukevat tietolähteet sallitaan. <br>Ei tueta: <li> DirectQuery</li><li>Reaaliaikaiset yhteydet (Azure AS ei käy)</li> <li>Paikalliset tietolähteet (henkilökohtaisen yhdyskäytävän ja yritysyhdyskäytävän ei tueta)</li> <li>Reaaliaikainen (push-tietojoukko ei tue)</li> <li>Yhdistelmämallit</li></ul> |
| Tietojoukko: työtilojen välinen | Työtilojen välisiä tietojoukkoja ei sallita  |
| Kyselyparametrit | Ei tueta: Tyyppiä ”Any” tai ”Binary” olevat parametrit estävät tietojoukon päivitystoiminnon |
| Mukautetut visualisoinnit | Vain julkisesti käytettävissä olevia mukautettuja visualisointeja tuetaan. [Organisaation mukautettuja visualisointeja](power-bi-custom-visuals-organization.md) ei tueta. |

## <a name="next-steps"></a>Seuraavat vaiheet

[Mitä Power BI -mallisovellukset ovat? (esikatselu)](service-template-apps-overview.md)
