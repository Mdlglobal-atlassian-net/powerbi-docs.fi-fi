---
title: Raportin suorituskyvyn vianmääritys Power BI:ssä
description: Vianmääritysopas raportin hitaan suorituskyvyn diagnosointiin Power BI:ssä.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2020
ms.author: v-pemyer
ms.openlocfilehash: a5230a39706ce5d6941c00386160fe10114442e1
ms.sourcegitcommit: 5ece366fceee9832724dae40eacf8755e1d85b04
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/16/2020
ms.locfileid: "81527987"
---
# <a name="troubleshoot-report-performance-in-power-bi"></a>Raportin suorituskyvyn vianmääritys Power BI:ssä

Tässä artikkelissa olevien ohjeiden avulla kehittäjät ja järjestelmänvalvojat voivat suorittaa raportin hitaan suorituskyvyn vianmäärityksen. Se koskee Power BI -raportteja sekä Power BI:n sivutettuja raportteja.

Raporttien käyttäjät saattavat havaita, että raportti latautuu tai päivittyy hitaasti, kun niitä käytetään osittajien tai muiden ominaisuuksien kanssa. Kun raportteja isännöidään Premium-kapasiteetissa, hitaat raportit voidaan myös tunnistaa seuraamalla [Power BI Premiumin mittarisovellusta](../service-admin-premium-monitor-capacity.md). Tämä sovellus auttaa seuraamaan Power BI Premium -tilauksen kuntoa ja kapasiteettia.

## <a name="follow-flowchart-steps"></a>Vuokaavion vaiheiden noudattaminen

Seuraava vuokaavio auttaa ymmärtämään paremmin hitaan suorituskyvyn syyn ja määrittämään tarvittavat toiminnot.

:::image type="content" source="media/report-performance-troubleshoot/flowchart.png" alt-text="Kuvassa näkyy vuokaavio, joka on kuvattu täysin artikkelin tekstissä." border="true":::

Vuokaaviossa on kuusi päätetoimenpidettä, joista jokainen kuvailee tarvittavia toimintoja:

|Päätetoimenpide|Toiminto|
|---------|---------|
|![Vuokaavion päätetoimenpide 1.](media/common/icon-01-red-30x30.png)|Hallitse kapasiteettia<br />Skaalaa kapasiteettia |
|![Vuokaavion päätetoimenpide 2.](media/common/icon-02-red-30x30.png)|Tutki kapasiteetin toimintaa raportin normaalin käytön aikana|
|![Vuokaavion päätetoimenpide 3.](media/common/icon-03-red-30x30.png)|Arkkitehtuurin muutos<br />Harkitse Azure Analysis Servicesiä<br />Tarkista paikallinen yhdyskäytävä|
|![Vuokaavion päätetoimenpide 4.](media/common/icon-04-red-30x30.png)|Harkitse Azure Analysis Servicesiä<br />Harkitse Power BI Premiumia|
|![Vuokaavion päätetoimenpide 5.](media/common/icon-05-red-30x30.png)|Käytä Power BI Desktopin suorituskyvyn analysointia<br />Optimoi raportti, malli tai DAX|
|![Vuokaavion päätetoimenpide 6.](media/common/icon-06-red-30x30.png)|Avaa tukipalvelupyyntö|

## <a name="take-action"></a>Tee toimintoja

Ensimmäiseksi on ymmärrettävä, isännöidäänkö hidasta raporttia Premium-kapasiteetissa.

### <a name="premium-capacity"></a>Premium-kapasiteetti

Kun raporttia isännöidään Premium-kapasiteetissa, määritä **Power BI Premiumin mittarisovelluksella**, ylittääkö raportin isännöintikapasiteetti kapasiteettiresurssit usein. Suorittimen osalta asia on niin, jos se ylittää usein 80 prosenttia. Muistin osalta asia on niin, kun [aktiivisen muistin mittausarvo](../service-premium-metrics-app.md#the-active-memory-metric) ylittää 50. Kun resursseihin kohdistuu paineita, voi olla aika [hallita tai skaalata kapasiteettia](../service-admin-premium-manage.md) (vuokaavion päätetoimenpide 1). Kun resursseja on riittävästi, tutki kapasiteetin toimintaa raportin normaalin käytön aikana (vuokaavion päätetoimenpide 2).

### <a name="shared-capacity"></a>Jaettu kapasiteetti

Kun raporttia isännöidään jaetussa kapasiteetissa, kapasiteetin kunnon valvonta ei ole mahdollista. Asiaa on tutkittava eri tavalla.

Selvitä ensin, onko suorituskyky hitaampaa tiettyinä aikoina päivästä tai kuukaudesta. Jos näin on – ja monet käyttäjät avaavat raportin kyseisenä aikana – harkitse kahta vaihtoehtoa:

- Kasvata kyselyjen siirtonopeutta siirtämällä tietojoukko [Azure Analysis Servicesiin](/azure/analysis-services/analysis-services-overview) tai Premium-kapasiteettiin (vuokaavion päätetoimenpide 4).
- Käyttämällä Power BI Desktopin [Suorituskyvyn analysointia](../desktop-performance-analyzer.md) voit selvittää, miten kaikki raporttielementit, kuten visualisoinnit ja DAX-kaavat, toimivat. On erityisen hyödyllistä määrittää, johtuvatko suorituskykyongelmat kyselystä vai visualisoinnin hahmonnuksesta (vuokaavion päätetoimenpide 5).

Jos tiettyä aikaan liittyvää kaavaa ei mielestäsi ole, mieti seuraavaksi, liittyykö hidas suorituskyky tiettyyn maantieteelliseen alueeseen. Jos näin on, tietolähde on todennäköisesti etäinen ja verkkoyhteys on hidas. Harkitse tässä tapauksessa seuraavaa:

- Muuta arkkitehtuuria käyttämällä [Azure Analysis Servicesiä](/azure/analysis-services/analysis-services-overview) (vuokaavion päätetoimenpide 3).
- Optimoi [paikallisen tietoyhdyskäytävän suorituskyky](/data-integration/gateway/service-gateway-performance) (vuokaavion päätetoimenpide 3).

Lopuksi, jos huomaat, että tiettyä aikaan liittyvää kaavaa ei ole _ja_ hidasta suorituskykyä esiintyy kaikilla alueilla, selvitä, liittyykö hidas suorituskyky tiettyihin laitteisiin, asiakkaisiin tai verkkoselaimiin. Jos näin ei ole, voit optimoida raportin tai mallin Power BI Desktopin [suorituskyvyn analysoinnilla](../desktop-performance-analyzer.md) (vuokaavion päätetoimenpide 5).

Kun olet määrittänyt, että tietyt laitteet, asiakkaat tai selaimet vaikuttavat hitaaseen suorituskykyyn, suosittelemme, että luot tukipalvelupyynnön [Power BI:n tukisivulla](https://powerbi.microsoft.com/support/) (vuokaavion päätetoimenpide 6).

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Power BI -ohjeet](index.yml)
- [Raportin suorituskyvyn valvominen](monitor-report-performance.md)
- [Suorituskyvyn analysointi](../desktop-performance-analyzer.md)
- Tekninen raportti: [Power BI:n yrityskäyttöönoton suunnitteleminen](https://go.microsoft.com/fwlink/?linkid=2057861)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)
