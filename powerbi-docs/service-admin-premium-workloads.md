---
title: Kuormitusten määrittäminen Power BI Premiumissa
description: Opi määrittämään Power BI Premium -kapasiteettien kuormituksia.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/01/2019
LocalizationGroup: Premium
ms.openlocfilehash: fbff4b744cf4a35f2fe1d0ae46f4676cd5f1db77
ms.sourcegitcommit: 8525b6365f3e224176730f4b8e5dae83f540a4ff
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/01/2019
ms.locfileid: "58795241"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium-kapasiteettien kuormitusten määrittäminen

Tässä artikkelissa kuvaillaan, miten voit ottaa käyttöön ja määrittää Power BI Premium -kapasiteettien kuormituksia. Oletusarvoisesti kapasiteetit tukevat ainoastaan Power BI -kyselyjen suorittamiseen liittyviä kuormituksia. Voit myös ottaa käyttöön ja määrittää muita kuormituksia **[tekoälylle (kognitiiviset palvelut)](service-cognitive-services.md)**, **[tietovoille](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** ja **[sivutetuille raporteille](paginated-reports-save-to-power-bi-service.md)**.

## <a name="default-memory-settings"></a>Oletusmuistiasetukset

Kyselyn kuormitukset on optimoitu Premium-kapasiteetin SKU:lle, jonka resurssit määrittävät kuormitusten rajat. Premium-kapasiteetit tukevat myös muita kuormituksia, jotka voivat käyttää oman kapasiteettisi resursseja. Näiden kuormitusten oletusmuistiarvot perustuvat SKU:n käytettävissä oleviin kapasiteetin solmuihin. Enimmäismuistiasetukset eivät ole kumulatiivisia. Enintään enimmäisarvoa vastaava muistimäärä varataan AI:lle ja tietovuolle dynaamisesti, mutta sivutetuille raporteille staattisesti. 

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office -varastointiyksiköt Software as a Service (SaaS) -skenaarioille

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| Tekoäly (kognitiiviset palvelut) | Oletus 20 %, vähimmäisarvo TBD| Oletus 20 %, vähimmäisarvo TBD | Oletus 20 %, vähimmäisarvo TBD | Oletus 20 %, vähimmäisarvo TBD | Oletus 20 %, vähimmäisarvo TBD |
| Tietovuot | – |Oletus 20 %, vähintään 12  | Oletus 20 %, vähintään 5 %  | Oletus 20 %, vähintään 3 % | Oletus 20 %, vähintään 2 %  |
| Sivutetut raportit | – |– | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure -varastointiyksiköt Platform as a Service (PaaS) -skenaarioille

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Tekoäly (kognitiiviset palvelut) | –                      | Oletus 20 %, vähimmäisarvo TBD                      | Oletus 20 %, vähimmäisarvo TBD                     | Oletus 20 %, vähimmäisarvo TBD | Oletus 20 %, vähimmäisarvo TBD | Oletus 20 %, vähimmäisarvo TBD |
| Tietovuot         | Oletus 40 %, vähintään 40 % | Oletus 24 %, vähintään 24 % | Oletus 20 %, vähintään 12 % | Oletus 20 %, vähintään 5 %  | Oletus 20 %, vähintään 3 % | Oletus 20 %, vähintään 2 %   |
| Sivutetut raportit | –                      | –                      | –                     | Oletus 20 %, vähintään 10 % | Oletus 20 %, vähintään 5 % | Oletus 20 %, vähintään 2,5 % |
| | | | | | |

## <a name="configure-workloads"></a>Kuormitusten määrittäminen

Suurenna kapasiteetin käytettävissä olevien resurssien määrää ottamalla käyttöön kuormituksia vain, jos niitä käytetään. Muuta muistiasetuksia vain, jos olet todennut, että oletusasetukset eivät vastaa kapasiteettisi resurssivaatimuksia.  

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Kuormitusten määrittäminen Power BI -hallintaportaalin kautta

1. Valitse kapasiteetti kohdasta **Kapasiteettiasetukset** > **PREMIUM-KAPASITEETIT**.

1. Laajenna **Kuormitukset** **LISÄÄ VAIHTOEHTOJA** -kohdasta.

1. Ota käyttöön yksi tai useampi kuormitus ja anna **Muistin enimmäismäärälle** arvo.   

    
    ![Kuormitusten käyttöönotto](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. Valitse **Käytä**.

> [!NOTE]
> Jos otat käyttöön sivutettujen raporttien kuormituksen, muista, että sivutettujen raporttien avulla voit suorittaa omaa koodia raporttia hahmontaessasi. Näin voit esimerkiksi sallia tekstin värin dynaamisen muuttamisen sisällön perusteella. Power BI Premium suorittaa sivutetut raportit rajoitetussa tilassa kapasiteetin sisällä. Tälle tilalle osoitetaan kaikki määrittämäsi muisti riippumatta siitä, onko kuormitus aktiivinen. Jos käytät Power BI -raportteja tai tietovoita samassa kapasiteetissa, varmista, että olet määrittänyt sivutetuille raporteille riittävän vähän muistia, jotta muiden kuormitusten nopeus ei kärsi. Sivutetut raportit -kuormitus saattaa lakata toimimasta joissain harvinaisissa tapauksissa. Näissä tapauksissa kuormitus näyttää virhetilan hallintaportaalissa ja raportin hahmontaminen aikakatkaistaan käyttäjiltä. Voit ratkaista ongelman poistamalla kuormituksen käytöstä ja ottamalla sen uudelleen käyttöön.

### <a name="rest-api"></a>REST-ohjelmointirajapinta

Kuormituksia voidaan ottaa käyttöön ja määrittää kapasiteetille käyttämällä [Kapasiteetit](https://docs.microsoft.com/rest/api/power-bi/capacities)-REST-ohjelmointirajapintoja.

## <a name="monitoring-workloads"></a>Kuormitusten valvonta

[Power BI Premium Capacity Metrics -sovellus](service-admin-premium-monitor-capacity.md) tarjoaa tietojoukkojen, tietovoiden ja sivutettujen raporttien mittareita, joiden avulla voit valvoa kapasiteeteissasi käyttöön otettuja kuormituksia. 

## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI Premium -kapasiteetin resurssien hallinta ja optimointi](service-premium-understand-how-it-works.md)   
[Omatoiminen tietovoita sisältävien tietojen valmisteleminen Power BI:ssä](service-dataflows-overview.md)   
[Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)   

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)