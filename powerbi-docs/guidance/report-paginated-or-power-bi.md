---
title: Milloin sivutettuja raportteja kannattaa käyttää Power BI:ssä
description: Ohjeita Power BI:n sivutettujen raporttien käyttämiseen.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/04/2020
ms.author: v-pemyer
ms.openlocfilehash: 2e048c3aa2ebc6e51388be652234c2ccf2348663
ms.sourcegitcommit: 801d2baa944469a5b79cf591eb8afd18ca4e00b1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/11/2020
ms.locfileid: "75886132"
---
# <a name="when-to-use-paginated-reports-in-power-bi"></a>Milloin sivutettuja raportteja kannattaa käyttää Power BI:ssä

Tämä artikkeli koskee raportin laatijaa, joka suunnittelee raportteja Power BI:lle. Se tarjoaa ehdotuksia, joiden avulla voit valita sopivan ajankohdan [Power BI:n sivutettujen raporttien](../paginated-reports-report-builder-power-bi.md) kehittämiseen.

> [!NOTE]
> Power BI:n sivutettujen raporttien julkaiseminen edellyttää Power BI Premium -tilausta. Raportit hahmonnetaan vain silloin, kun ne ovat työtilassa varatussa kapasiteetissa, jonka [sivutettujen raporttien kuormitus on otettu käyttöön](../service-admin-premium-workloads.md#paginated-reports).

Power BI:n sivutetut raportit on optimoitu **tulostusta** tai **PDF:n luontia** varten. Ne tarjoavat myös mahdollisuuden tuottaa erittäin muotoiltuja ja pikselintarkkoja asetteluja. Sivutetut raportit ovat siis ihanteellisia toimintaraporteille, kuten myyntilaskuille.

Power BI -raportit on sen sijaan optimoitu **tutkimista ja vuorovaikutteisuutta** varten. Ne voivat myös esittää tietosi käyttämällä huippumodernia visualisointivalikoimaa. Power BI -raportit ovat siis ihanteellisia analyyttisia raportteja varten, sillä raporttisi käyttäjät voivat tutkia niitä ja huomata näin suhteita ja säännönmukaisuuksia.

Suosittelemme harkitsemaan sivutetun Power BI -raportin käyttämistä seuraavissa tapauksissa:

* Tiedät, että raportti tulee tulostaa tai siitä pitää tehdä PDF-tiedosto.
* Tietoruudukon asettelut saattavat laajentua ja vuotaa yli. Huomaa, että Power BI -raportin taulukon tai matriisin koko ei voi muuttua dynaamisesti niin, että se näyttäisi kaikki tiedot – sen sijaan käytössä on vierityspalkit. Jos taulukko tulostetaan, sitä ei kuitenkaan voi vierittää näyttämään mitään sillä näkymättömiä tietoja.
* Power BI:n sivutetut ominaisuudet auttavat tässä asiassa. Monia tällaisia raporttiskenaarioita kuvataan myöhemmin tässä artikkelissa.

## <a name="legacy-reports"></a>Aiemmat raportit

Kun sinulla on jo SQL Server Reporting Servicesin (SSRS) [Report Definition Language (RDL)](/sql/reporting-services/reports/report-definition-language-ssrs) -raportteja, voit kehittää ne uudelleen [Power BI -raporteiksi](../consumer/end-user-reports.md) tai siirtää ne Power BI:hin sivutettuina raportteina. Lisätietoja on artikkelissa [SQL Server Reporting Services -raporttien siirtäminen Power BI:hin](migrate-ssrs-reports-to-power-bi.md).

Kun sivutetut raportit on julkaistu Power BI -työtilaan, ne ovat käytettävissä rinnakkain Power BI -raporttien kanssa. Sen jälkeen ne voidaan helposti jakaa [Power BI -sovellusten](../service-create-distribute-apps.md) avulla.

Voit harkita SSRS-raporttien kehittämistä uudelleen sen sijaan, että siirtäisit ne. Tämä koskee erityisesti niiltä raportteja, jotka on tarkoitettu analyyttisten kokemusten toimittamiseen. Näissä tapauksissa Power BI -raportit tarjoavat todennäköisesti parempia raportinkäyttäjäkokemuksia.

## <a name="paginated-report-scenarios"></a>Sivutettujen raporttien skenaariot

On monia pakottavia tilanteita, joissa saatat suosia Power BI:n sivutetun raportin kehittämistä. Monet ovat ominaisuuksia, joita Power BI -raportit eivät tue.

* **Tulostusvalmis**: Sivutetut raportit on optimoitu tulostusta tai PDF:n luontia varten. Tarvittaessa tietoalueet voivat laajentua ja vuotaa yli hallitusti useille sivuille. Raportin asettelut voivat määrittää reunukset sekä sivun ylä- ja alatunnisteet.
* **Muotojen hahmontaminen**: Power BI voi hahmontaa sivutettuja raportteja eri muodoissa. Muotoihin kuuluvat Microsoft Excel, Microsoft Word, Microsoft PowerPoint, PDF, CSV, XML ja MHTML. (Power BI-palvelu käyttää MHTML-muotoa raporttien hahmontamiseen.) Raporttisi käyttäjät voivat halutessaan viedä niitä itselleen sopivassa muodossa.
* **Tarkkuusasettelu**: Voit suunnitella erittäin muotoiltuja ja pikselintarkkoja asetteluja, jotka on määritetty haluttuun kokoon ja sijaintiin tuuman tai senttimetrin murto-osan tarkkuudella.
* **Dynaaminen rakenne**: Voit luoda erittäin reagoivia asetteluja asettamalla useita raportin ominaisuuksia käyttämään VB.NET-lausekkeita. Lausekkeilla on pääsy moniin keskeisiin .NET Framework -kirjastoihin.
* **Hahmonnuskohtainen asettelu**: Lausekkeiden avulla voit muokata raportin asettelua käytetyn hahmontamismuodon perusteella. Voit esimerkiksi suunnitella raportin, joka poistaa käytöstä näkyvyyden vaihtomekanismin (alaspäin ja ylöspäin porautumisen), kun se hahmonnetaan käyttäen muuta kuin vuorovaikutteista muotoa, esimerkiksi PDF:ää.
* **Alkuperäiset kyselyt**: Sinun ei tarvitse ensin kehittää Power BI -tietojoukkoa. Voit kirjoittaa alkuperäisiä kyselyitä (tai käyttää tallennettuja toimintosarjoja) mille tahansa [tuetulle tietolähteelle](../paginated-reports-data-sources.md). Kyselyt voivat sisältää parametrisointia.
* **Graafisten kyselyjen suunnittelutyökalu**: Power BI:n Raportin muodostin sisältää graafisten kyselyjen suunnittelutyökaluja, joiden avulla voit kirjoittaa ja testata tietojoukkokyselyitä.
* **Staattiset tietojoukot**: Voit määrittää tietojoukon ja syöttää tiedot suoraan raporttimääritykseen. Tästä ominaisuudesta on hyötyä erityisesti demon tukemisessa tai soveltuvuusselvityksen (POC) toimittamisessa.
* **Tietojen integrointi**: Voit yhdistää tietoja eri tietolähteistä tai staattisilla tietojoukoilla. Se tehdään luomalla mukautettuja kenttiä VB.NET-lausekkeiden avulla.
* **Parametrisointi**: Voit suunnitella erittäin mukautettuja parametrisointikokemuksia, kuten aineistopohjaisia parametreja ja johdannaisparametreja. Voit myös määrittää parametrien oletusarvot. Nämä kokemukset voidaan suunnitella siten, että raporttisi käyttäjät voivat nopeasti ottaa käyttöön sopivia suodattimia. Parametrien ei myöskään tarvitse suodattaa raporttitietoja. Niiden avulla voidaan tukea "entä jos"-tilanteita tai dynaamista suodatusta tai muotoilua.
* **Kuvatiedot**: Raporttisi voi hahmontaa kuvia, kun ne on tallennettu binaarimuotoon tietolähteessä.
* **Mukautettu koodi**: Voit kehittää VB.NET-funktioiden koodilohkoja raportissasi ja käyttää niitä missä tahansa raporttilausekkeessa.
* **Aliraportit**: Voit upottaa raporttiin muita Power BI:n sivutettuja raportteja (samasta työtilasta).
* **Joustavat tietoruudukot**: Voit hienosäätää ruudukon asetteluja tablix-tietoalueen avulla. Se tukee myös monimutkaisia asetteluja, kuten sisäkkäisiä ja vierekkäisiä ryhmiä. Lisäksi se voidaan määrittää toistamaan otsikoita useita sivuja tulostettaessa. Se voi myös upottaa aliraportin tai muita visualisointeja, kuten tietopalkkeja, sparkline-kaavioita ja ilmaisimia.
* **Paikkatietotyypit**: Kartan tietoalue voi visualisoida [SQL Server -paikkatietotyyppejä](/sql/relational-databases/spatial/spatial-data-sql-server). Näin ollen maantieteellisiä ja geometrisiä tietotyyppejä voidaan käyttää pisteiden, viivojen tai monikulmioiden visualisoimiseen. Myös ESRI-muototiedostoissa määritettyjä monikulmioita voidaan visualisoida.
* **Nykyaikaiset mittarit**: Säteittäisiä ja lineaarisia mittareita voidaan käyttää suorituskykyilmaisimen arvojen ja tilan näyttämiseen. Ne voidaan upottaa myös ruudukon tietoalueisiin, jotka toistuvat ryhmissä.
* **HTML-hahmontaminen**: Voit näyttää monipuolisesti muotoiltua tekstiä, kun se tallennetaan HTML-muodossa.
* **Sähköpostin yhdistäminen**: Tekstiruudun paikkamerkkien avulla voit lisätä tekstiin tietoarvoja. Näin voit luoda sähköpostin yhdistämisraportin.
* **Vuorovaikutteisuusominaisuudet**: Vuorovaikutteisuusominaisuudet sisältävät näkyvyyden vaihtomekanismin (alas- ja ylöspäin porautuminen), linkit, vuorovaikutteisen lajittelun ja työkaluvihjeet. Voit myös lisätä linkkejä, jotka porautuvat Power BI -raportteihin tai muihin Power BI:n sivutettuihin raportteihin. Linkit voivat jopa viedä toiseen sijaintiin samassa raportissa.
* **Tilaukset**: Power BI voi toimittaa sivutettuja raportteja aikataulun mukaisesti sähköpostiviesteinä, jolloin raportin liitteet ovat missä tahansa tuetussa muodossa.
* **Käyttäjäkohtaiset asettelut**: Voit luoda reagoivia raporttiasetteluja raportin avaavan todennetun käyttäjän perusteella. Voit suunnitella raportin suodattamaan tiedot eri tavoin, piilottamaan tietoalueita tai visualisointeja, käyttämään eri muotoiluja tai määrittämään käyttäjäkohtaisia parametrien oletusarvoja.

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tähän artikkeliin liittyen tutustumalla seuraaviin resursseihin:

* [Mitä ovat sivutetut raportit Power BI Premiumissa?](../paginated-reports-report-builder-power-bi.md)
* Kaveri kuutiossa -video: [Esittelyssä sivutetut raportit Power BI:ssä](https://www.youtube.com/watch?v=wfqn45XNK3M)
* [SQL Server Reporting Services -raporttien siirtäminen Power BI:hin](migrate-ssrs-reports-to-power-bi.md)
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
* Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com)
