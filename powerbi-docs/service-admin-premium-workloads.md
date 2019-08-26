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
ms.date: 04/15/2019
LocalizationGroup: Premium
ms.openlocfilehash: 49a1f02e5aa327c2704b6c2d789934a43b760ad0
ms.sourcegitcommit: 0e50ebfa8762e19286566432870ef16d242ac78f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/13/2019
ms.locfileid: "68962025"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium-kapasiteettien kuormitusten määrittäminen

Tässä artikkelissa kuvaillaan, miten voit ottaa käyttöön ja määrittää Power BI Premium -kapasiteettien kuormituksia. Oletusarvoisesti kapasiteetit tukevat ainoastaan Power BI -kyselyjen suorittamiseen liittyviä kuormituksia. Voit myös ottaa käyttöön ja määrittää muita kuormituksia **[tekoälylle (kognitiiviset palvelut)](service-cognitive-services.md)**, **[tietovoille](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** ja **[sivutetuille raporteille](paginated-reports-save-to-power-bi-service.md)**.

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

Tekoälykuormituksessa on **Muistin enimmäismäärä** -asetuksen lisäksi myös toinen asetus, **Salli käyttö Power BI Desktopista**. Oletusarvo on **Ei käytössä**. Tämä asetus on varattu tulevaa käyttöä varten, eikä sitä välttämättä näytetä kaikissa vuokraajissa.

### <a name="datasets-preview"></a>Tietojoukot (esikatselu)

Tietojoukkojen kuormitus on oletuksena käytössä, eikä sitä voi poistaa käytöstä. Tämä kuormitus sisältää lisäasetuksen _XMLA-päätepistettä_ varten ja joukon suorituskykyyn liittyviä asetuksia. Tämä **XMLA-päätepiste**-asetus määrittää, että asiakassovelluksista tulevissa yhteyksissä noudatetaan työtilan ja sovelluksen tasoilla määritettyä suojausryhmän jäsenyyttä. Lisätietoja on artikkelissa [Tietojoukkoihin yhdistäminen asiakassovelluksilla ja -työkaluilla](service-premium-connect-tools.md).

Suorituskykyyn liittyvät asetukset kuvataan seuraavassa taulukossa.

| Asetuksen nimi | Kuvaus | Käyttö |
|---------------------------------|----------------------------------------|----------------------------------------|
| **Välirivien enimmäismäärä** | DirectQueryn palauttamien välirivien enimmäismäärä. Oletusarvo on 1000000 ja sallittu alue on 100000–2147483647 | Hallitse resurssi-intensiivisten tai huonosti suunniteltujen raporttien vaikutusta. |
| **Offline-tietojoukon enimmäiskoko (Gt)** | Muistissa olevan offline-tietojoukon enimmäiskoko. Tämä on pakattu koko levyllä. Oletusarvon asettaa SKU ja sallittu alue on 0,1–10 Gt | Estä raportin tekijöiltä kapasiteettiin kielteisesti vaikuttavan suuren tietojoukon julkaiseminen. |
| **Tulosrivien enimmäismäärä** | Määrittää DAX-kyselyssä palautettavien rivien enimmäismäärän. Oletusarvo on 1 (ei rajoitusta) ja sallittu alue on 100000–2147483647 | Hallitse resurssi-intensiivisten tai huonosti suunniteltujen raporttien vaikutusta. |
| **Kysely muistiraja (%)** | Koskee vain DAX-mittareita ja -kyselyitä. Määritetty prosenttiarvona (%) ja rajoittaa sitä, kuinka paljon tilapäiset tulokset voivat käyttää muistia kyselyn aikana. | Hallitse resurssi-intensiivisten tai huonosti suunniteltujen raporttien vaikutusta. |
| **Kyselyn aikakatkaisu (sekuntia)** | Kokonaisluku, joka määrittää kyselyiden aikakatkaisun sekunteina. Oletusarvo on 3600 sekuntia (eli 60 minuuttia). Nolla (0) määrittää, että kyselyillä ei ole aikakatkaisua. | Hallitse paremmin pitkäkestoisia kyselyitä. |
|  |  |  |

### <a name="dataflows"></a>Tietovuot

Tekoälykuormituksessa on **Muistin enimmäismäärä** -asetuksen lisäksi myös lisäasetus, **Säilön koko**. Tämän asetuksen avulla voit optimoida tietovuon kuormituksen suorituskyvyn, kun käsitellään monimutkaisia, käsittelyltään raskaita tietovoita.

Tietovuon päivityksen yhteydessä tietovuon kuormitus muodostaa säilön kullekin tietovuon entiteetille. Kukin säilö voi varata muistia enintään Säilön koko -asetuksessa määritettyyn kokoon saakka. Oletusarvo kaikille SKU-yksiköille on **700 Mt**. Tätä asetusta kannattaa ehkä muuttaa, jos:

- Tietovoiden päivittyminen kestää liian kauan tai tietovuon päivitys epäonnistuu aikakatkaisun takia.
- Tietovuon entiteetit sisältävät laskentavaiheita, kuten liittämisen.  

On suositeltavaa käyttää [Power BI Premium -kapasiteettimittarisovellusta](service-admin-premium-monitor-capacity.md) tietovuon kuormituksen suorituskyvyn analysointiin. 

Joissakin tapauksissa säiliön koon kasvattaminen ei välttämättä paranna suorituskykyä. Jos esimerkiksi tietovuo saa tietoa vain lähteestä ilman merkittävien laskutoimitusten tekemistä, säilön koon muuttaminen ei todennäköisesti auta. Säiliön koon kasvattaminen voi auttaa, jos sen avulla tietovuon kuormitus voi varata lisää muistia entiteetin päivitystoiminnoille. Kun muistia varataan enemmän, paljon laskentaa sisältävien entiteettien päivitysaika voi lyhentyä.

Säilön koko -arvo ei voi ylittää tietovoiden kuormitukselle määritettyä enimmäismuistia. Esimerkiksi P1-kapasiteetissa muistia on 25 gigatavua. Jos tietovuon kuormituksen enimmäismuistin (%) arvoksi on asetettu 20 %, säilön koko (Mt) ei voi olla yli 5000. Kaikissa tapauksissa säiliön koko ei voi ylittää enimmäismuistin arvoa, vaikka asettaisit suuremman arvon.

### <a name="paginated-reports-preview"></a>Sivutetut raportit (esikatselu)

Sivutetut raportit mahdollistavat mukautetun koodin suorittamisen, kun raporttia hahmonnetaan. Voit esimerkiksi muuttaa tekstin väriä dynaamisesti sisällön perusteella, mikä käyttää enemmän muistia. Power BI Premium suorittaa sivutetut raportit rajoitetussa tilassa kapasiteetin sisällä. Määritetty enimmäismuisti käytetään *riippumatta* siitä, onko kuormitus aktiivinen. Jos muutat muistin enimmäisasetusta oletusarvosta, varmista, että asetat sen niin pieneksi, että se ei vaikuta haitallisesti muihin kuormituksiin.

Joissakin tapauksissa Sivutetut raportit -kuormitus saattaa lakata toimimasta. Näissä tapauksissa kuormitus näyttää virhetilan hallintaportaalissa ja raportin hahmontaminen aikakatkaistaan käyttäjiltä. Voit ratkaista ongelman poistamalla kuormituksen käytöstä ja ottamalla sen uudelleen käyttöön.

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