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
ms.date: 03/11/2019
LocalizationGroup: Premium
ms.openlocfilehash: 0baab138ee98d2ec96bc9f47e6e727525a57ed3e
ms.sourcegitcommit: f176ba9d52d50d93f264eca21bb3fd987dbf934b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/12/2019
ms.locfileid: "57757242"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium-kapasiteettien kuormitusten määrittäminen

Tässä artikkelissa kuvaillaan, miten voit ottaa käyttöön ja määrittää Power BI Premium -kapasiteettien kuormituksia. Oletusarvoisesti kapasiteetit tukevat ainoastaan Power BI -kyselyjen suorittamiseen liittyviä kuormituksia. Kyselyn kuormitukset on optimoitu Premium-kapasiteetin SKU:lle, jonka resurssit määrittävät kuormitusten rajat. Premium-kapasiteetit tukevat myös muita kuormituksia, jotka voivat käyttää kapasiteetin resursseja.

## <a name="configure-workloads"></a>Kuormitusten määrittäminen

Voit ottaa käyttöön ja määrittää muita kuormituksia AI:lle, [tietovoille](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium) ja [sivutetuille raporteille](paginated-reports-save-to-power-bi-service.md). Näiden kuormitusten oletusmuistiarvot perustuvat SKU:n käytettävissä oleviin kapasiteetin solmuihin. Enimmäismuistiasetukset eivät ole kumulatiivisia. Enintään enimmäisarvoa vastaava muistimäärä varataan AI:lle ja tietovuolle dynaamisesti, mutta sivutetuille raporteille staattisesti. 

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


## <a name="next-steps"></a>Seuraavat vaiheet

[Power BI Premium -kapasiteetin resurssien hallinta ja optimointi](service-premium-understand-how-it-works.md)   
[Omatoiminen tietovoita sisältävien tietojen valmisteleminen Power BI:ssä](service-dataflows-overview.md)   
[Mitä ovat sivutetut raportit Power BI Premiumissa?](paginated-reports-report-builder-power-bi.md)   

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)