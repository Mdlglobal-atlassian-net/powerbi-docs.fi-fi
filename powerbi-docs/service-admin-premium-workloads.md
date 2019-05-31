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
ms.openlocfilehash: c84bebef5589ec391e3640ff3be674b1fb5a0ebd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "65564872"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium-kapasiteettien kuormitusten määrittäminen

Tässä artikkelissa kuvaillaan, miten voit ottaa käyttöön ja määrittää Power BI Premium -kapasiteettien kuormituksia. Oletusarvoisesti kapasiteetit tukevat ainoastaan Power BI -kyselyjen suorittamiseen liittyviä kuormituksia. Voit myös ottaa käyttöön ja määrittää muita kuormituksia **[tekoälylle (kognitiiviset palvelut)](service-cognitive-services.md)** , **[tietovoille](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** ja **[sivutetuille raporteille](paginated-reports-save-to-power-bi-service.md)** .

## <a name="default-memory-settings"></a>Oletusmuistiasetukset

Kyselyn kuormitukset on optimoitu Premium-kapasiteetin SKU:lle, jonka resurssit määrittävät kuormitusten rajat. Premium-kapasiteetit tukevat myös muita kuormituksia, jotka voivat käyttää oman kapasiteettisi resursseja. Näiden kuormitusten oletusmuistiarvot perustuvat SKU:n käytettävissä oleviin kapasiteetin solmuihin. Enimmäismuistiasetukset eivät ole kumulatiivisia. Enintään enimmäisarvoa vastaava muistimäärä varataan AI:lle ja tietovuolle dynaamisesti, mutta sivutetuille raporteille staattisesti. 

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office -varastointiyksiköt Software as a Service (SaaS) -skenaarioille

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| AI | – | – | 20 prosenttia oletus; Pienin 20 prosenttia | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % |
| Tietovuot | – |Oletus 20 %, vähintään 12  | Oletus 20 %, vähintään 5 %  | Oletus 20 %, vähintään 3 % | Oletus 20 %, vähintään 2 %  |
| Sivutetut raportit | – |– | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure -varastointiyksiköt Platform as a Service (PaaS) -skenaarioille

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| AI | –                      | 20 prosenttia oletus; 100 % pienin                     | 20 prosenttia oletus; vähintään 50 prosenttia                     | 20 prosenttia oletus; Pienin 20 prosenttia | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % |
| Tietovuot         | Oletus 40 %, vähintään 40 % | Oletus 24 %, vähintään 24 % | Oletus 20 %, vähintään 12 % | Oletus 20 %, vähintään 5 %  | Oletus 20 %, vähintään 3 % | Oletus 20 %, vähintään 2 %   |
| Sivutetut raportit | –                      | –                      | –                     | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| | | | | | |

## <a name="workload-settings"></a>Kuormituksen asetukset

### <a name="ai-preview"></a>AI (esikatselu)

Lisäksi **Max muistin** asetuksen, Tekoäly järjestelmän kuormitus on muita asetuksia, **Salli käyttö Power BI Desktop**. Oletusarvo on **käytöstä**. Tämä asetus on varattu tulevaa käyttöä varten, ja se ei ehkä näy kaikille vuokraajille.

### <a name="datasets-preview"></a>Tietojoukot (esikatselu)

Oletusarvon mukaan tietojoukkoja järjestelmän kuormitus on käytössä ja ei voi poistaa käytöstä. Tämä kuormituksen sisältää muita asetuksia, **XMLA-päätepisteelle**. Oletusarvo on **1**, merkitys käytössä. Tämä asetus määrittää yhteydet asiakassovellusten noudattavan suojausryhmän jäsenyyden Määritä työtila ja sovelluksen tasolla. Lisätietoja on artikkelissa [tietojoukkoja, joilla asiakassovellusten ja työkaluja, joilla yhdistäminen](service-premium-connect-tools.md).

### <a name="dataflows"></a>Tietovuot

Lisäksi **Max muistin** asetuksen, Dataflows järjestelmän kuormitus on muita asetuksia, **säilön koon**. Tämän asetuksen avulla voit optimoida tietovirrassa kuormituksen suorituskykyyn monimutkaisempia ja käsittely raskas dataflows käsittelyn.

Tietovirrassa päivittäessäsi tietovirrassa kuormituksen etäasemassa säilön tietovirrassa kullekin entiteetille. Kunkin säilön voi kestää määritetty säilön koon asetuksen muistin merkkiin. Ovat kaikki Varastointiyksiköt oletusarvo on **700 Mt**. Haluat ehkä muuttaa tätä asetusta, jos:

- Dataflows kestää liian kauan, päivittää tai aikakatkaisu tietovirrassa päivitys epäonnistuu.
- Laskeminen vaiheet, esimerkiksi liitoksen tietovirrassa entiteeteissä.  

Sen käyttäjän käytät Microsoft suosittelee [Power BI Premium-kapasiteetin Mittaustietoihin](service-admin-premium-monitor-capacity.md) sovelluksen analysoida tietovirrassa kuormituksen suorituskykyyn. 

Joissakin tapauksissa säilön koon voi ei parantaa suorituskykyä. Esimerkiksi jos tietovirrassa on tietoja vain lähteestä suorittamatta merkittäviä laskutoimituksia, säilön koon muuttamisen todennäköisesti ei auta. Säilön koon voi auttaa, jos se mahdollistaa tietovirrassa kuormituksen muistin varaaminen entiteetin päivitystoiminnot. Voit pienentää mukaan on varattu enemmän muistia, Päivitä vahvasti laskettuja entiteettejä kuluvaa aikaa. 

Säilön koko-arvo ei voi olla Dataflows kuormituksen muistin enimmäismäärän. P1-kapasiteetti on 25 gt muistia. Jos tietovirrassa työmääräryhmän muisti Max (%) määritetään 20 prosenttia säilön koko (Mt) ei voi ylittää 5000. Kaikissa tapauksissa säilön koko voi olla enintään Max-muistiin, vaikka voit määrittää suurempi arvo. 

### <a name="paginated-reports-preview"></a>Sivutetut raportit (esikatselu)

Sivutetut raportit Salli mukautetun koodin suorittaminen, kun raportin hahmontaminen. Esimerkiksi muuttaa dynaamisesti tekstin väriä, sisällön perusteella, joka voi kestää lisämuistia. Power BI Premium suorittaa sivutetut raportit rajoitetussa tilassa kapasiteetin sisällä. Suurin muistin määritetty käytetään *onko* kuormitus on aktiivinen. Jos Max muistia, asetuksen muuttamista oletusarvosta, varmista, että määrität – alhainen niin, että se ei vaikuta muiden kuormitusten negatiivisesti.

Joissakin tapauksissa Sivutettujen raporttien kuormituksen voit ei ole enää käytettävissä. Tässä tapauksessa kuormituksen näyttää virhetilan hallintaportaalissa, ja käyttäjät näkevät raportin hahmontaminen aikakatkaisut. Ratkaise tämä ongelma, kuormituksen käytöstä ja ota se käyttöön uudelleen.

## <a name="configure-workloads"></a>Kuormitusten määrittäminen

Suurenna kapasiteetin käytettävissä olevien resurssien määrää ottamalla käyttöön kuormituksia vain, jos niitä käytetään. Muuta muistiasetuksia vain, jos olet todennut, että oletusasetukset eivät vastaa kapasiteettisi resurssivaatimuksia.  

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Kuormitusten määrittäminen Power BI -hallintaportaalin kautta

1. Valitse kapasiteetti kohdasta **Kapasiteettiasetukset** > **PREMIUM-KAPASITEETIT**.

1. Laajenna **Kuormitukset** **LISÄÄ VAIHTOEHTOJA** -kohdasta.

1. Ota käyttöön yksi tai useampi kuormitus ja anna **Muistin enimmäismäärälle** arvo.   

    
    ![Kuormitusten käyttöönotto](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. Valitse **Käytä**.

### <a name="rest-api"></a>REST-ohjelmointirajapinta

Kuormituksia voidaan ottaa käyttöön ja määrittää kapasiteetille käyttämällä [Kapasiteetit](https://docs.microsoft.com/rest/api/power-bi/capacities)-REST-ohjelmointirajapintoja.

## <a name="monitoring-workloads"></a>Kuormitusten valvonta

[Power BI Premium Capacity Metrics -sovellus](service-admin-premium-monitor-capacity.md) tarjoaa tietojoukkojen, tietovoiden ja sivutettujen raporttien mittareita, joiden avulla voit valvoa kapasiteeteissasi käyttöön otettuja kuormituksia. 

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI Premium-kapasiteetteja optimointi](service-premium-capacity-optimize.md)     
[Omatoiminen tietovoita sisältävien tietojen valmisteleminen Power BI:ssä](service-dataflows-overview.md)   
[Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)   

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)