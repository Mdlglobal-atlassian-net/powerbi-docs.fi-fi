---
title: Power BI:n sisältöpakettien luontimallit
description: Mallisisältöpaketin luominen
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/09/2017
ms.author: maghan
ms.openlocfilehash: bfed948be385439d33b335b08da68b103cd7c1b8
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/08/2018
---
# <a name="author-template-content-packs-in-power-bi"></a>Power BI:n sisältöpakettien luontimallit
Sisältöpaketin luonnissa käytetään Power BI Desktop -versiota ja PowerBI.comia. Sisältöpaketissa on neljä osaa:

* Kyselyjen avulla voit [yhdistää](../desktop-connect-to-data.md) ja [muuntaa](../desktop-query-overview.md) tietoja sekä määrittää [parametreja](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/).  
* Tietomallin avulla voit luoda [suhteita](../desktop-create-and-manage-relationships.md), [mittareita](../desktop-measures.md) ja Q&A-parannuksia.  
* Raportin [sivut](../desktop-report-view.md) sisältävät visualisointeja ja suodattimia, jotka antavat merkityksellisiä tietoja.  
* [Koontinäyttö](../service-dashboards.md) ja [ruudut](../service-dashboard-create.md) antavat yleiskatsauksen sisältyvistä merkityksellisistä tiedoista.  

Nämä voivat olla tuttuja nykyisten Power BI -ominaisuuksien kautta. Sisältöpakettia luotaessa kunkin osa-alueen kohdalla on huomioitava myös muita asioita. Katso lisätietoja kustakin osasta jäljempänä.

<a name="queries"></a>

## <a name="queries"></a>Kyselyt
Power BI Desktop -versiossa luotuja kyselyitä käytetään mallisisältöpaketeissa tietolähteen yhdistämiseen ja tietojen tuomiseen. Näitä kyselyjä tarvitaan yhtenäisen rakenteen palauttamiseen, ja niitä tuetaan tietojen ajoitetussa päivityksessä (suoraa kyselyä ei tueta).

Mallisisältöpaketit tukevat vain yhtä tietolähdettä sisältöpakettia kohden, joten kyselyt kannattaa määrittää huolellisesti. Yksi tietolähde on lähde, joka vaatii saman todennuksen. Voit tehdä useita ohjelmointirajapinnan kutsuja eri kyselyissä, jos kaikki kutsut tehdään samaan ohjelmointirajapinnan päätepisteeseen ja niissä käytetään samaa todennusta. Power BI -sisältöpaketit eivät tue useita lähteitä, jotka vaativat eri todennuksen.

### <a name="connect-to-your-api"></a>Ohjelmointirajapintaan yhdistäminen
Aloita kyselyiden rakentaminen muodostamalla yhteys Power BI Desktop -versiosta ohjelmointirajapintaasi.

Voit käyttää ohjelmointirajapinnan yhdistämiseen tietoyhdistimiä, jotka ovat valmiina Power BI Desktop -versiossa. Voit käyttää verkkotietojen yhdistintä (Hae tiedot -> Verkko) Rest-ohjelmointirajapinnan yhdistämiseen tai OData-yhdistintä (Hae tiedot -> OData-syöte) OData-syötteen yhdistämiseen. Huomaa, että nämä yhdistimet toimivat suoraan vain, jos ohjelmointirajapintasi tukee perustodennusta.

> [!NOTE]
> Jos ohjelmointirajapintasi käyttää mitä tahansa muuta todennustyyppiä, kuten OAuth 2.0 -todennusta tai verkkopalvelujen ohjelmointirajapinnan avainta, sinun on kehitettävä oma tietoyhdistin, jotta Power BI Desktop voi muodostaa yhteyden ohjelmointirajapintaasi ja todentaa sen. Lisätietoja oman tietoyhdistimen kehittämisestä sisältöpakettiasi varten saat tietoyhdistimien ohjeista [täältä](https://aka.ms/DataConnectors). 
> 
> 

### <a name="consider-the-source"></a>Huomioi lähde
Kyselyt määrittelevät tiedot, jotka sisällytetään tietomalliin. Järjestelmäsi koosta riippuen näissä kyselyissä on myös oltava suodattimia, jotta koko on asiakkaittesi kannalta hallittavissa ja sopii liiketoimintaskenaarioosi.

Power BI -sisältöpaketit voivat suorittaa useita kyselyitä rinnakkain ja useille käyttäjille samanaikaisesti.  Suunnittele etukäteen rajoittamisen ja samanaikaisuuden strategia ja kysy meiltä neuvoa siihen, miten sisältöpaketista luodaan vikasietoinen.

### <a name="schema-enforcement"></a>Rakenteen pakottaminen
Varmista, että kyselysi kestävät järjestelmäsi muutokset. Rakenteen muutokset tai päivitys voi rikkoa mallin. Jos lähde voi palauttaa joillekin kyselyille tyhjäarvon tai puuttuvan rakenteen, harkitse tyhjän taulukon palauttamista tai mukautettua virhesanomaa, josta käyttäjälle on hyötyä.

### <a name="parameters"></a>Parametrit
Power BI Desktop -version [parametrien](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) avulla käyttäjät voivat syöttää arvoja, jotka mukauttavat käyttäjän hakemia tietoja. Mieti parametreja jo etukäteen, jotta rakentamiasi yksityiskohtaisia kyselyitä tai raportteja ei tarvitse työstää jälkikäteen.

> [!NOTE]
> Tällä hetkellä mallisisältöpaketit tukevat vain tekstiparametreja. Muita parametrityyppejä voi käyttää kehitysvaiheessa, mutta [testauksen](template-content-pack-testing.md#templates) aikana kaikki käyttäjien antamat arvot ovat kirjallisia.
> 
> 

### <a name="additional-query-tips"></a>Lisää kyselyvihjeitä
* Varmista, että kaikki sarakkeet on kirjoitettu oikein.  
* Sarakkeissa on informatiiviset nimet (katso Q&A).  
* Jaetun logiikan kannalta kannattaa harkita funktioiden tai kyselyiden käyttöä.  
* Yksityisyystasoja ei tällä hetkellä tueta palvelussa. Jos näyttöön ilmestyy kehote yksityisyystasoista, sinun on ehkä kirjoitettava kysely uudelleen, jotta voit käyttää suhteellisia polkuja.  

## <a name="data-model"></a>Tietomalli
Hyvin määritelty tietomalli takaa, että asiakkaasi voivat käyttää sisältöpakettia helposti ja intuitiivisesti. Luo tietomalli Power BI Desktop -versiossa.

> [!NOTE]
> Suuri osa perusmallintamisesta (kirjoitus, sarakkeiden nimet) pitäisi tehdä [kyselyissä](#queries).
> 
> 

### <a name="qa"></a>Q&A
Mallintaminen vaikuttaa myös siihen, kuinka hyvin Q&A tarjoaa tuloksia asiakkaillesi. Muista lisätä usein käytettyihin sarakkeisiin synonyymeja ja varmista, että sarakkeet on nimetty oikein [kyselyissä](#queries).

### <a name="additional-data-model-tips"></a>Lisävihjeitä tietomalleista
* Kaikissa arvosarakkeissa on käytetty muotoilua.
    >[!NOTE]
    >Kyselyssä pitäisi käyttää tyyppejä.  
* Kaikissa mittareissa on käytetty muotoilua.  
* Oletusyhteenveto on määritetty. Erityisesti ”Älä tee yhteenvetoa” soveltuvissa tapauksissa (esimerkiksi yksilöllisille arvoille).  
* Tietoluokka on määritetty soveltuvissa tapauksissa.  
* Suhteet on määritetty tarpeen mukaan.  

## <a name="reports"></a>Raportit
Raporttisivut antavat lisää merkityksellisiä tietoja sisältöpakettiisi sisältyvistä tiedoista. Vastaa raporttisivuilla keskeisiin liiketoiminnallisiin kysymyksiin, joihin sisältöpakettisi pyrkii vastaamaan. Luo raportti Power BI Desktop -version avulla.

> [!NOTE]
> Sisältöpakettiin voi sisällyttää ainoastaan yhden raportin. Hyödynnä eri sivuja nostamalla esille skenaariosi eri osia.
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

## <a name="dashboard"></a>Koontinäyttö
Koontinäyttö on sisältöpakettisi tärkein vuorovaikutuspiste asiakkaittesi kannalta. Siinä tulisi olla yleiskatsaus paketin sisällöstä ja erityisesti liiketoimintaskenaariosi tärkeistä metriikoista.

Voit luoda koontinäytön mallisisältöpaketillesi lataamalla PBIX-tiedostosi kohdassa Hae tiedot > Tiedostot tai julkaisemalla sen suoraan Power BI Desktop -version kautta.

> [!NOTE]
> Mallisisältöpaketeissa voi tällä hetkellä olla vain yksi raportti ja tietomalli sisältöpakettia kohden. Älä kiinnitä sisältöpaketissa käytössä olevaan koontinäyttöön sisältöä useista raporteista tai tietomalleista.
> 
> 

### <a name="additional-dashboard-tips"></a>Lisää koontinäyttövihjeitä
* Säilytä sama teema kiinnittäessäsi, jotta koontinäyttösi ruudut ovat yhtenäisiä.  
* Kiinnitä teemaan logo, jotta kuluttajat tietävät, mistä paketti on peräisin.  
* Suositeltava asettelu useimmilla näytön tarkkuuksilla on 5–6 pientä ruutua leveä.  
* Kaikissa koontinäytön ruuduissa pitäisi olla asianmukainen otsikko tai alaotsikko.  
* Harkitse koontinäytön sisällön ryhmittelyä eri skenaarioita varten joko pysty- tai vaakasuunnassa.  

<a name="restrictions"></a>

## <a name="summary-of-restrictions"></a>Yhteenveto rajoituksista
Kuten edellä olevissa osissa on lueteltu, mallisisältöpaketeissa on tällä hetkellä tiettyjä rajoituksia:  

| Tuetaan | *Ei tueta* |
| --- | --- |
| PBI Desktop -versiossa rakennetut tietojoukot |*Tietojoukot muista sisältöpaketeista tai syötteistä, kuten Excel-tiedostoista* |
| Tietolähdettä tuetaan pilvipohjaisessa ajoitetussa tietojen päivityksessä |*Suoraa kyselyä tai paikallista yhteyttä ei tueta* |
| Kyselyt, jotka palauttavat yhtenäisen rakenteen tai virheitä soveltuvissa tapauksissa |*Dynaamiset tai mukautetut rakenteet* |
| Yksi tietolähde tietojoukkoa kohden |*Useat tietolähteet, kuten koosteet tai URL-osoitteet, jotka tulkitaan useiksi tietolähteiksi* |
| Tekstityyppiä olevat parametrit |*Muut parametrityypit (kuten päivämäärä) tai ”sallittujen arvojen luettelo”* |
| Yksi koontinäyttö, raportti ja tietojoukko |*Useita koontinäyttöjä, raportteja tai tietojoukkoja* |

## <a name="next-step"></a>Seuraava vaihe
[Sisältöpaketin testaus ja lähettäminen](template-content-pack-testing.md)

