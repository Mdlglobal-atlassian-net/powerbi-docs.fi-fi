---
title: Vihjeitä mallisovellusten luomiseen Power BI:ssä (esikatselu)
description: Vihjeitä, jotka liittyvät kyselyiden, tietomallien, raporttien ja koontinäyttöjen luomiseen hyviä mallisovelluksia varten
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/05/2019
ms.author: maggies
ms.openlocfilehash: 282638c7c1c8a60ee93292602766d63fd0fe436e
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/14/2019
ms.locfileid: "56249678"
---
# <a name="tips-for-authoring-template-apps-in-power-bi-preview"></a>Vihjeitä mallisovellusten luomiseen Power BI:ssä (esikatselu)

Kun [kehität mallisovellustasi](service-template-apps-create.md) Power BI:ssä, sinun tulee hallita myös työtilan luonnin, testauksen ja tuotannon logistiikka. Lisäksi sinun tulee luonnollisesti luoda raportti ja koontinäyttö. Luontiprosessin voi jakaa neljään pääosioon. Näiden osioiden avulla voit luoda parhaan mahdollisen mallisovelluksen:

* **Kyselyjen** avulla voit [yhdistää](desktop-connect-to-data.md) ja [muuntaa](desktop-query-overview.md) tietoja sekä määrittää [parametreja](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/). 
* **Tietomallin** avulla voit luoda [suhteita](desktop-create-and-manage-relationships.md), [mittareita](desktop-measures.md) ja Q&A-parannuksia.  
* **[Raportin sivut](desktop-report-view.md)** sisältävät visualisointeja ja suodattimia, jotka antavat merkityksellisiä tietoja.  
* **[Koontinäytöt](consumer/end-user-dashboards.md)** ja [ruudut](service-dashboard-create.md) antavat yleiskatsauksen mallisovellukseen sisältyvistä merkityksellisistä tiedoista.  

Nämä voivat olla tuttuja nykyisten Power BI -ominaisuuksien kautta. Kun luot mallisovellusta, kuhunkin osioon liittyy muitakin huomioon otettavia seikkoja. Lisätietoja on seuraavissa osissa.

<a name="queries"></a>

## <a name="queries"></a>Kyselyt
Power BI Desktopissa luotuja kyselyitä käytetään mallisovelluksissa tietolähteen yhdistämiseen ja tietojen tuomiseen. Näitä kyselyjä tarvitaan yhtenäisen rakenteen palauttamiseen, ja niitä tuetaan tietojen ajoitetussa päivityksessä (DirectQuery-kyselyitä ei tueta).

### <a name="connect-to-your-api"></a>Ohjelmointirajapintaan yhdistäminen
Aloita kyselyiden rakentaminen muodostamalla yhteys Power BI Desktopista ohjelmointirajapintaasi.

Voit käyttää ohjelmointirajapinnan yhdistämiseen tietoyhdistimiä, jotka ovat valmiina Power BI Desktop -versiossa. Voit käyttää verkkotietojen yhdistintä (Hae tiedot -> Verkko) Rest-ohjelmointirajapinnan yhdistämiseen tai OData-yhdistintä (Hae tiedot -> OData-syöte) OData-syötteen yhdistämiseen. Nämä yhdistimet toimivat suoraan vain, jos ohjelmointirajapintasi tukee perustodennusta.

> [!NOTE]
> Jos ohjelmointirajapintasi käyttää mitä tahansa muuta todennustyyppiä, kuten OAuth 2.0 -todennusta tai verkkopalvelujen ohjelmointirajapinnan avainta, sinun on kehitettävä oma tietoyhdistin, jotta Power BI Desktop voi muodostaa yhteyden ohjelmointirajapintaasi ja todentaa sen. Lisätietoja oman tietoyhdistimen kehittämisestä mallisovellustasi varten saat [tietoyhdistimien ohjeista](https://aka.ms/DataConnectors). 
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
>


### <a name="qa"></a>Kysymykset ja vastaukset
Mallintaminen vaikuttaa myös siihen, kuinka hyvin kysymykset ja vastaukset tarjoavat tuloksia asiakkaillesi. Muista lisätä usein käytettyihin sarakkeisiin synonyymeja ja varmista, että olet nimennyt sarakkeet oikein [kyselyissä](#queries).

### <a name="additional-data-model-tips"></a>Lisävihjeitä tietomalleista

Varmista, että olet:
* käyttänyt muotoilua kaikissa arvosarakkeissa käyttänyt tyyppejä kyselyssä  
* käyttänyt muotoilua kaikissa mittayksiköissä 
* määrittänyt oletusyhteenvedon, erityisesti ”Älä tee yhteenvetoa” -vaihtoehdon soveltuvissa tapauksissa (esimerkiksi yksilöllisille arvoille)  
* määrittänyt tietoluokan soveltuvissa tapauksissa  
* määrittänyt suhteet tarpeen mukaan.  

## <a name="reports"></a>Raportit
Raporttisivut antavat lisää merkityksellisiä tietoja mallisovellukseesi sisältyvistä tiedoista. Vastaa raporttisivuilla keskeisiin liiketoiminnallisiin kysymyksiin, joihin mallisovelluksesi pyrkii vastaamaan. Luo raportti Power BI Desktopin avulla.

> [!NOTE]
> Mallisovellukseen voi sisällyttää ainoastaan yhden raportin. Hyödynnä siis eri sivuja nostamalla esille skenaariosi eri osia.
>
>

### <a name="additional-report-tips"></a>Lisävihjeitä raportteihin

* Käytä sivulla useampaa kuin yhtä visualisointia ristiinsuodatusta varten.  
* Tasaa visualisoinnit huolellisesti (ei päällekkäisyyksiä).  
* Sivu on määritetty kuvasuhteeseen 4:3 tai 16:9 asettelua varten.  
* Kaikki esitetyt koosteet ovat numeerisesti järkeenkäypiä (keskiarvot, yksilölliset arvot).  
* Jaottelu tuottaa rationaalisia tuloksia.  
* Logo on näkyvissä vähintään raportin yläosassa.  
* Elementit ovat asiakkaan värimallin mukaisia siinä määrin kuin mahdollista.  

<a name="dashboard"></a>

## <a name="dashboards"></a>koontinäytöt
Koontinäyttö on mallisovelluksesi tärkein vuorovaikutuspiste asiakkaittesi kannalta. Siinä tulisi olla yleiskatsaus paketin sisällöstä ja erityisesti liiketoimintaskenaariosi tärkeistä metriikoista.

Voit luoda mallisovelluksellesi koontinäytön lataamalla PBIX-tiedoston kohdassa Hae tiedot > Tiedostot tai julkaisemalla sen suoraan Power BI Desktopin kautta.

> [!NOTE]
> Mallisovelluksissa tulee tällä hetkellä olla yksi raportti ja tietomalli mallisovellusta kohden. Älä kiinnitä mallisovelluksessa käytettyyn koontinäyttöön sisältöä useista raporteista tai tietomalleista.
>
>

### <a name="additional-dashboard-tips"></a>Lisää koontinäyttövihjeitä

* Säilytä sama teema kiinnittäessäsi, jotta koontinäyttösi ruudut ovat yhtenäisiä.  
* Kiinnitä teemaan logo, jotta kuluttajat tietävät, mistä paketti on peräisin.  
* Suositeltava asettelu useimmilla näytön tarkkuuksilla on 5–6 pientä ruutua leveä.  
* Kaikissa koontinäytön ruuduissa tulee olla asianmukainen otsikko tai alaotsikko.  
* Harkitse koontinäytön sisällön ryhmittelyä eri skenaarioita varten joko pysty- tai vaakasuunnassa.  

## <a name="known-limitations"></a>Tunnetut rajoitukset

| Ominaisuus | Tunnettu rajoitus |
|---------|---------|
|Sisältö:  Tietojoukot   | Tarkalleen yhden tietojoukon tulee olla käytössä. Vain Power BI Desktopissa luodut tietojoukot (.pbix-tiedostot) sallitaan. <br>Ei tueta: Tietojoukkoja, jotka ovat peräisin muista mallisovelluksista, työtilojen välisiä tietojoukkoja, sivuttuja raportteja (.rdl-tiedostot), Excel-työkirjoja |
|Sisältö: Raportit     | Enintään yksi raportti    |
| Sisältö: koontinäytöt | Enintään yksi muu kuin tyhjä koontinäyttö <br>Ei tueta: Reaaliaikaisia ruutuja (toisin sanoen PushDataset ja pubnub eivät ole tuettuja) |
| Sisältö: Tietovuot | Ei tueta: Tietovuot |
| Tiedostojen sisällöt | Vain PBIX-tiedostot sallitaan. <br>Ei tueta: .rdl-tiedostot (sivutetut raportit), Excel-työkirjat   |
| Tietolähteet | Pilvipohjaista ajoitettua tietojen päivittämistä tukevat tietolähteet sallitaan. <br>Ei tueta: <br>DirectQuery <br>Reaaliaikaiset yhteydet (Azure AS ei käy) <br>Paikalliset tietolähteet (henkilökohtaiset yhdyskäytävät ja yritysyhdyskäytävät eivät ole tuettuja) <br>Reaaliaikainen (pushdataset ei ole tuettu) <br>Yhdistelmämallit |
| Tietojoukko: työtilojen välinen | Työtilojen välisiä tietojoukkoja ei sallita  |
| Sisältö: koontinäytöt | Reaaliaikaisia ruutuja ei sallita (toisin sanoen PushDataset ja pubnub eivät ole tuettuja) |
| Kyselyparametrit | Ei tueta: Tyyppiä ”Any” tai ”Binary” olevat parametrit estävät tietojoukon päivitystoiminnon |
| Mukautetut visualisoinnit | Vain julkisesti käytettävissä olevia mukautettuja visualisointeja tuetaan. [Organisaation mukautettuja visualisointeja](power-bi-custom-visuals-organization.md) ei tueta. |

## <a name="next-steps"></a>Seuraavat vaiheet

[Mitä Power BI -mallisovellukset ovat? (esikatselu)](service-template-apps-overview.md)
