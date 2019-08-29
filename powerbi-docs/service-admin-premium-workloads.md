---
title: Kuormitusten määrittäminen Power BI Premiumissa
description: Opi määrittämään Power BI Premium -kapasiteettien kuormituksia.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 08/21/2019
LocalizationGroup: Premium
ms.openlocfilehash: 2d2eb51c5aad44572f1b427248fd85ef19a6306f
ms.sourcegitcommit: e62889690073626d92cc73ff5ae26c71011e012e
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/23/2019
ms.locfileid: "69985701"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium-kapasiteettien kuormitusten määrittäminen

Tässä artikkelissa kuvaillaan, miten voit ottaa käyttöön ja määrittää Power BI Premium -kapasiteettien kuormituksia. Oletusarvoisesti kapasiteetit tukevat ainoastaan Power BI -kyselyjen suorittamiseen liittyviä kuormituksia. Voit myös ottaa käyttöön ja määrittää muita kuormituksia **[tekoälylle (kognitiiviset palvelut)](service-cognitive-services.md)** , **[tietovoille](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** ja **[sivutetuille raporteille](paginated-reports-save-to-power-bi-service.md)** .

## <a name="default-memory-settings"></a>Oletusmuistiasetukset

Kyselyn kuormitukset on optimoitu Premium-kapasiteetin SKU:lle, jonka resurssit määrittävät kuormitusten rajat. Premium-kapasiteetit tukevat myös muita kuormituksia, jotka voivat käyttää oman kapasiteettisi resursseja. Näiden kuormitusten oletusmuistiarvot perustuvat SKU:n käytettävissä oleviin kapasiteetin solmuihin. Enimmäismuistiasetukset eivät ole kumulatiivisia. Enintään enimmäisarvoa vastaava muistimäärä varataan AI:lle ja tietovuolle dynaamisesti, mutta sivutetuille raporteille staattisesti.

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office -varastointiyksiköt Software as a Service (SaaS) -skenaarioille

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| Tekoäly | – | – | Oletus 20 %, vähintään 20 % | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % |
| Tietovuot | – |Oletus 20 %, vähintään 12  | Oletus 20 %, vähintään 5 %  | Oletus 20 %, vähintään 3 % | Oletus 20 %, vähintään 2 %  |
| Sivutetut raportit | – |– | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure -varastointiyksiköt Platform as a Service (PaaS) -skenaarioille

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Tekoäly | –                      | Oletus 20 %, vähintään 100 %                     | Oletus 20 %, vähintään 50 %                     | Oletus 20 %, vähintään 20 % | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % |
| Tietovuot         | Oletus 40 %, vähintään 40 % | Oletus 24 %, vähintään 24 % | Oletus 20 %, vähintään 12 % | Oletus 20 %, vähintään 5 %  | Oletus 20 %, vähintään 3 % | Oletus 20 %, vähintään 2 %   |
| Sivutetut raportit | –                      | –                      | –                     | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| | | | | | |

## <a name="workload-settings"></a>Kuormitusasetukset

### <a name="ai-preview"></a>Tekoäly (esikatselu)

Tekoälykuormituksen avulla voit käyttää kognitiivisia palveluita ja automaattianalyysipalveluita Power BI:ssä. Voit hallita kuormituksen toimintaa seuraavien asetusten avulla.

| Asetuksen nimi | Kuvaus |
|---------------------------------|----------------------------------------|
| **Muistin enimmäismäärä (%)** | Tekoälyprosessien käytettävissä olevan muistin enimmäismäärä prosentteina kapasiteetissa. |
| **Salli käyttö Power BI Desktopista** | Tämä asetus on varattu tulevaa käyttöä varten, eikä sitä välttämättä näytetä kaikissa vuokraajissa. |
| **Salli koneoppimismallien luominen** | Määritä, voivatko liiketoiminta-analyytikot kouluttaa, vahvistaa ja käynnistää koneoppimismalleja suoraan Power BI:ssä. Lisätietoja on artikkelissa [Automaattianalyysipalvelut Power BI:ssä (esikatselu)](service-machine-learning-automated.md). |
| **Ota käyttöön rinnakkaisuus tekoälypyynnöissä** | Määritä, voiko tekoälypyyntöjä suorittaa rinnakkain. |
|  |  |

### <a name="datasets"></a>Tietojoukot

Tietojoukkojen kuormitus on oletuksena käytössä, eikä sitä voi poistaa käytöstä. Voit hallita kuormituksen toimintaa seuraavien asetusten avulla.

| Asetuksen nimi | Kuvaus |
|---------------------------------|----------------------------------------|
| **Muistin enimmäismäärä (%)** | Tietojoukkojen käytettävissä olevan muistin enimmäismäärä prosentteina kapasiteetissa. |
| **XMLA:n päätepiste** | Tämä määrittää, että asiakassovelluksista tulevissa yhteyksissä noudatetaan työtilan ja sovelluksen tasoilla määritettyä suojausryhmän jäsenyyttä. Lisätietoja on artikkelissa [Tietojoukkoihin yhdistäminen asiakassovelluksilla ja -työkaluilla](service-premium-connect-tools.md). |
| **Välirivien enimmäismäärä** | DirectQueryn palauttamien välirivien enimmäismäärä. Oletusarvo on 1000000 ja sallittu alue on 100000–2147483647. Tämän asetuksen avulla voi hallita resurssi-intensiivisten tai huonosti suunniteltujen raporttien vaikutusta. |
| **Offline-tietojoukon enimmäiskoko (Gt)** | Muistissa olevan offline-tietojoukon enimmäiskoko. Tämä on pakattu koko levyllä. Oletusarvon asettaa SKU ja sallittu alue on 0,1–10 Gt. Tämän asetuksen avulla voi estää raportin tekijöiltä kapasiteettiin kielteisesti vaikuttavan suuren tietojoukon julkaisemisen. |
| **Tulosrivien enimmäismäärä** | DAX-kyselyssä palautettavien rivien enimmäismäärä. Oletusarvo on -1 (ei rajaa) ja sallittu alue on 100000–2147483647. Tämän asetuksen avulla voi hallita resurssi-intensiivisten tai huonosti suunniteltujen raporttien vaikutusta. |
| **Kysely muistiraja (%)** | Kyselyn tai DAX-mittarin tilapäisiin kyselyihin käytettävissä olevan muistin enimmäismäärä prosentteina. Tämän asetuksen avulla voi hallita resurssi-intensiivisten tai huonosti suunniteltujen raporttien vaikutusta. |
| **Kyselyn aikakatkaisu (sekuntia)** | Kyselyn aikakatkaisuajan suurin mahdollinen aika. Oletusarvo on 3600 sekuntia (1 tunti). Arvo 0 määrittää, että kyselyissä ei ole aikakatkaisua. Tämän asetuksen avulla voi hallita paremmin pitkäkestoisia kyselyitä. |
|  |  |  |

### <a name="dataflows"></a>Tietovuot

Tietovoiden kuormituksen avulla voit käyttää tietovoiden omatoimista tietojen valmistelua tietojen käyttämiseen, muuntamiseen, integroimiseen ja rikastamiseen. Voit hallita kuormituksen toimintaa seuraavien asetusten avulla.

| Asetuksen nimi | Kuvaus |
|---------------------------------|----------------------------------------|
| **Muistin enimmäismäärä (%)** | Tietovoiden käytettävissä olevan muistin enimmäismäärä prosentteina kapasiteetissa. |
| **Parannettu tietovoiden käsittelymoduuli (esikatselu)** | Ota tämä asetus käyttöön, jotta laskettujen entiteettien käsittely tapahtuu jopa 20 kertaa nopeammin, kun käsittelet suuria tietomääriä. **Kapasiteetti on käynnistettävä uudelleen uuden moduulin aktivoimiseksi.** Lisätietoja on kohdassa [Parannettu tietovoiden käsittelymoduuli](#enhanced-dataflows-compute-engine). |
| **Säilön koko** | Tietovoiden kussakin tietovuon entiteetissä käyttämän säilön enimmäiskoko. Oletusarvo on 700 Mt. Lisätietoja on kohdassa [Säilön koko](#container-size). |
|  |  |

#### <a name="enhanced-dataflows-compute-engine"></a>Parannettu tietovoiden käsittelymoduuli

Jos haluat hyötyä uudesta käsittelymoduulista, jaa tietojen käsittely erillisiksi tietovoiksi ja lisää muunnoslogiikka laskettuihin entiteetteihin eri tietovoissa. Tätä menetelmää suositellaan, koska käsittelymoduuli toimii tietovoissa, joissa viitataan olemassa olevaan tietovuohon. Se ei toimi tietojen käsittelyn tietovoissa. Näiden ohjeiden avulla varmistat, että uusi käsittelymoduuli käsittelee muunnosvaiheet, kuten liitokset ja yhdistämiset, optimaalisen suorituskyvyn saavuttamiseksi.

#### <a name="container-size"></a>Säilön koko

Tietovuon päivityksen yhteydessä tietovuon kuormitus muodostaa säilön kullekin tietovuon entiteetille. Kukin säilö voi varata muistia enintään **Säilön koko -asetuksessa määritettyyn kokoon saakka. Oletusarvo kaikille SKU-yksiköille on 700 Mt. Tätä asetusta kannattaa ehkä muuttaa, jos:

- Tietovoiden päivittyminen kestää liian kauan tai tietovuon päivitys epäonnistuu aikakatkaisun takia.
- Tietovuon entiteetit sisältävät laskentavaiheita, kuten liittämisen.  

On suositeltavaa käyttää [Power BI Premium -kapasiteettimittarisovellusta](service-admin-premium-monitor-capacity.md) tietovuon kuormituksen suorituskyvyn analysointiin.

Joissakin tapauksissa säiliön koon kasvattaminen ei välttämättä paranna suorituskykyä. Jos esimerkiksi tietovuo saa tietoa vain lähteestä ilman merkittävien laskutoimitusten tekemistä, säilön koon muuttaminen ei todennäköisesti auta. Säiliön koon kasvattaminen voi auttaa, jos sen avulla tietovuon kuormitus voi varata lisää muistia entiteetin päivitystoiminnoille. Kun muistia varataan enemmän, paljon laskentaa sisältävien entiteettien päivitysaika voi lyhentyä.

Säilön koko -arvo ei voi ylittää tietovoiden kuormitukselle määritettyä enimmäismuistia. Esimerkiksi P1-kapasiteetissa muistia on 25 gigatavua. Jos tietovuon kuormituksen enimmäismuistin (%) arvoksi on asetettu 20 %, säilön koko (Mt) ei voi olla yli 5000. Kaikissa tapauksissa säiliön koko ei voi ylittää enimmäismuistin arvoa, vaikka asettaisit suuremman arvon.

### <a name="paginated-reports"></a>Sivutetut raportit

Sivutettujen raporttien kuormituksen avulla voit suorittaa SQL Server Reporting Services -vakiomuotoon perustuvia sivutettuja raportteja Power BI -palvelussa. Voit hallita kuormituksen toimintaa seuraavan asetuksen avulla.

| Asetuksen nimi | Kuvaus |
|---------------------------------|----------------------------------------|
| **Muistin enimmäismäärä (%)** | Sivutettujen raporttien käytettävissä olevan muistin enimmäismäärä prosentteina kapasiteetissa. |
|  |  |

Sivutetut raportit mahdollistavat mukautetun koodin suorittamisen, kun raporttia hahmonnetaan. Voit esimerkiksi muuttaa tekstin väriä dynaamisesti sisällön perusteella, mikä käyttää enemmän muistia. Power BI Premium suorittaa sivutetut raportit rajoitetussa tilassa kapasiteetin sisällä. Määritetty enimmäismuisti käytetään *riippumatta* siitä, onko kuormitus aktiivinen. Jos muutat muistin enimmäisasetusta oletusarvosta, varmista, että asetat sen niin pieneksi, että se ei vaikuta haitallisesti muihin kuormituksiin.

Joissakin tapauksissa sivutettujen raporttien kuormitus saattaa lakata toimimasta. Näissä tapauksissa kuormitus näyttää virhetilan hallintaportaalissa ja raportin hahmontaminen aikakatkaistaan käyttäjiltä. Voit ratkaista ongelman poistamalla kuormituksen käytöstä ja ottamalla sen uudelleen käyttöön.

## <a name="configure-workloads"></a>Kuormitusten määrittäminen

Suurenna kapasiteetin käytettävissä olevien resurssien määrää ottamalla käyttöön kuormituksia vain, jos niitä käytetään. Muuta muistiasetuksia ja muita asetuksia vain, jos olet todennut, että oletusasetukset eivät vastaa kapasiteettisi resurssivaatimuksia.

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Kuormitusten määrittäminen Power BI -hallintaportaalin kautta

1. Valitse kapasiteetti kohdasta **Kapasiteettiasetukset** > **PREMIUM-KAPASITEETIT**.

1. Laajenna **Kuormitukset** **LISÄÄ VAIHTOEHTOJA** -kohdasta.

1. Ota käyttöön yksi tai useampi kuormitus ja anna **Muistin enimmäismäärälle** ja muille asetuksille arvo.

1. Valitse **Käytä**.

### <a name="rest-api"></a>REST-ohjelmointirajapinta

Kuormituksia voidaan ottaa käyttöön ja määrittää kapasiteetille käyttämällä [Kapasiteetit](https://docs.microsoft.com/rest/api/power-bi/capacities)-REST-ohjelmointirajapintoja.

## <a name="monitoring-workloads"></a>Kuormitusten valvonta

[Power BI Premium Capacity Metrics -sovellus](service-admin-premium-monitor-capacity.md) tarjoaa tietojoukkojen, tietovoiden ja sivutettujen raporttien mittareita, joiden avulla voit valvoa kapasiteeteissasi käyttöön otettuja kuormituksia. 

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI Premium -kapasiteettien optimointi](service-premium-capacity-optimize.md)     
[Omatoiminen tietovoita sisältävien tietojen valmisteleminen Power BI:ssä](service-dataflows-overview.md)   
[Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)   

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)