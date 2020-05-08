---
title: Parannetun laskentamoduulin käyttö tietovoiden kanssa
description: Lue ohjeet Power BI Premiumin parannetun käsittelymoduulin käyttöön tietovoiden kanssa
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 1d2bd150d33d95f2ec8759f9e876b3920eede3b6
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "75840066"
---
# <a name="the-enhanced-compute-engine"></a>Parannettu laskentamoduuli

Power BI:n parannetulla laskentamoduulilla Power BI Premium -tilaajat voivat käyttää kapasiteettiaan tietovoiden käytön optimointiin. Parannetun laskentamoduulin käyttö tarjoaa seuraavat edut:

* Se pienentää merkittävästi päivitysaikaa pitkään suoritettaville ETL-vaiheille lasketuissa entiteeteissä (esimerkiksi *liitosten*, *erillisten*, *suodattimien* ja *ryhmittelyperusteiden* suorittaminen).
* Se mahdollistaa DirectQuery-kyselyiden suorittamisen entiteeteille (helmikuussa 2020).

Seuraavissa osioissa kuvataan, miten voit ottaa käyttöön parannetun laskentamoduulin, sekä vastataan yleisiin kysymyksiin.


## <a name="using-the-enhanced-compute-engine"></a>Parannetun laskentamoduulin käyttäminen

Parannettu laskentamoduuli otetaan käyttöön Power BI -palvelun **kapasiteettiasetusten** sivun **tietovoiden** osiossa. Parannettu laskentamoduuli on oletusarvoisesti **poissa käytöstä**. Jos haluat ottaa sen käyttöön, siirrä valitsin **Käytössä**-asetukseen, kuten alla olevassa kuvassa. Muista tallentaa asetuksesi. 

![Parannetun laskentamoduulin käyttöönottaminen](media/service-dataflows-enhanced-compute-engine/enhanced-compute-engine-01.png)

Kun olet ottanut parannetun laskentamoduulin käyttöön ja palaat tietovoihisi, sinun pitäisi nähdä suorituskyvyn parantuneen kaikissa lasketuissa entiteeteissä, jotka suorittavat monimutkaisia toimintoja (esimerkiksi *liitokset* tai *ryhmittelyperusteen* toiminnot tietovoille, jotka on luotu olemassa olevista linkitetyistä entiteeteistä samassa kapasiteetissa). 

Voidaksesi käyttää laskentamoduulia parhaalla mahdollisella tavalla, sinun tulisi jakaa ETL-vaihe kahteen erilliseen tietovuohon seuraavasti:

* **Tietovuo 1**: tämän tietovuon tulisi ainoastaan ottaa vastaan kaikki pakollinen tietolähteestä ja välittää se tietovuohon 2.
* **Tietovuo 2**: Suorita kaikki ETL-toiminnot tässä toisessa tietovuossa, mutta varmista, että viittaat tietovuohon 1, jonka pitäisi olla samassa kapasiteetissa. Varmista, että suoritat ensin toiminnot, jotka voivat taittaa (suodatus, ryhmittelyperuste, erillinen, liitos), ennen muita toimintoja. Näin varmistat, että laskentamoduulia hyödynnetään.

## <a name="common-questions-and-answers"></a>Yleisiä kysymyksiä ja vastauksia

**Kysymys:** olen ottanut parannetun laskentamoduulin käyttöön, mutta päivitykset ovat hitaampia. Miksi?

**Vastaus**: Jos otat parannetun laskentamoduulin käyttöön, hitaammille päivitysajoille voi olla kaksi selitystä:

 - Kun parannettu laskentamoduuli otetaan käyttöön, se edellyttää jonkin verran muistia toimiakseen oikein. Tämän johdosta päivityksen suorittamiseen on käytettävissä vähemmän muistia. Tämä kasvattaa todennäköisyyttä sille, että päivityksiä asetetaan jonoon, mikä taas pienentää sitä tietovoiden määrää, joka voidaan päivittää samanaikaisesti. Voit korjata tämän seuraavasti: kun otat käyttöön parannettua laskentamoduulia, kasvata tietovoille määritetyn muistin määrää varmistaaksesi, että samanaikaisille tietovuopäivityksille käytettävissä olevan muistin määrä pysyy samana.

 - Toinen syy hitaammille päivityksille voi olla se, että laskentamoduuli toimii ainoastaan olemassa olevien entiteettien päällä, joten jos tietovuo viittaa tietolähteeseen, joka ei ole tietovuo, suorituskyky ei parane. Suorituskyky ei parane, koska joissain massadatakäyttötilanteissa ensimmäinen lukeminen tietolähteestä olisi hitaampaa, koska tiedot täytyy välittää parannetulle laskentamoduulille.  

**Kysymys:** En näe parannetun laskentamoduulin valitsinta. Miksi?

**Vastaus**: Parannettu laskentamoduuli julkaistaan vaiheittain eri alueilla eri puolilla maailmaa. Tarkoituksemme on saada se käyttöön kaikilla alueilla vuoden 2020 loppuun mennessä.

**Kysymys:** mitä tietotyyppejä laskentamoduuli tukee?

**Vastaus**: Parannettu laskentamoduuli ja tietovuot tukevat tällä hetkellä seuraavia tietotyyppejä. Jos tietovuosi ei käytä jotain seuraavista tietotyypeistä, päivityksen yhteydessä saattaa ilmetä virheitä:

* Päivämäärä ja aika
* Desimaaliluku
* Teksti
* Kokonaisluku
* Päivämäärä/aika/vyöhyke
* Tosi/epätosi
* Päivämäärä
* Aika

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä artikkelissa annettiin tietoja parannetun laskentamoduulin käytöstä tietovoiden kanssa. Myös seuraavista artikkeleista voi olla apua:

* [Omatoiminen tietojen valmistelu tietovoiden avulla](service-dataflows-overview.md)
* [Tietovoiden luominen ja käyttäminen Power BI:ssä](service-dataflows-create-use.md)
* [Laskettujen entiteettien käyttäminen Power BI Premiumissa](service-dataflows-computed-entities-premium.md)
* [Kehittäjien resurssit Power BI -tietovoille](service-dataflows-developer-resources.md)

Lisätietoja Power Querysta ja ajoitetusta päivityksestä on seuraavissa artikkeleissa:
* [Kyselyn yleiskatsaus Power BI Desktopissa](desktop-query-overview.md)
* [Ajoitetun päivityksen määrittäminen](refresh-scheduled-refresh.md)

Lisätietoja Common Data Modelista on sen yleiskatsauksen sisältävässä artikkelissa:
* [Common Data Model – yleiskatsaus](https://docs.microsoft.com/powerapps/common-data-model/overview)

