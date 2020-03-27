---
title: 'Sivutetut raportit Power BI:ssä: Usein kysytyt kysymykset'
description: Tässä artikkelissa vastataan usein kysyttyihin kysymyksiin sivutetuista raporteista. Näiden raporttien pitkälle muotoiltu ja pikselintarkka sisältö on optimoitu tulostamista tai PDF:n luontia varten.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 03/18/2020
ms.openlocfilehash: 885c6b98e66a6ce2fd8069cc86bf50440cb94b4b
ms.sourcegitcommit: 2c798b97fdb02b4bf4e74cf05442a4b01dc5cbab
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/21/2020
ms.locfileid: "80113602"
---
# <a name="paginated-reports-in-power-bi-faq"></a>Sivutetut raportit Power BI:ssä: Usein kysytyt kysymykset 

Tässä artikkelissa vastataan usein kysyttyihin kysymyksiin sivutetuista raporteista. Näiden raporttien pitkälle muotoiltu ja pikselintarkka sisältö on optimoitu tulostamista tai PDF:n luontia varten. Niitä kutsutaan ”sivutetuiksi”, koska ne on muotoiltu sopimaan hyvin useille sivuille. Sivutetut raportit perustuvat SQL Server Reporting Servicesin RDL-raporttitekniikkaan. 

Tässä artikkelissa vastataan useisiin yleisiin kysymyksiin, joita käyttäjillä on Power BI Premiumin sivutetuista raporteista ja raportin muodostimesta, sivutettujen raporttien erillisestä luontityökalusta. Tarvitset Power BI Pro -käyttöoikeuden raportin julkaisemiseksi palveluun. Voit julkaista ja jakaa sivutettuja raportteja omassa työtilassasi tai työtiloissa niin kauan kuin työtila on Power BI Premium -kapasiteetissa. 

## <a name="administration"></a>Hallinta

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Minkä kokoista Premium-kapasiteettia tarvitsen sivutettuja raportteja varten?

Sivutettujen raporttien kuormitus on käytettävissä P1– P3-varastointiyksiköissä.  Voit myös käyttää sitä A4–A6-varastointiyksikköjen kanssa testi-/kehitysskenaarioita varten.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Mikä on muistin enimmäisraja, jota voin soveltaa sivutettuihin raportteihin kapasiteetissa?

Voit käyttää jopa 100 % muistia tätä kuormitusta varten.

### <a name="how-does-user-access-work-for-paginated-reports"></a>Miten käyttöoikeudet toimivat sivutettujen raporttien kanssa?

Sivutettujen raporttien käyttöoikeudet ovat samat kuin käyttäjän oikeudet kaikkeen muuhun sisältöön Power BI -palvelussa. 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Miten voin ottaa käyttöön / poistaa käytöstä raporttien kuormituksen?

Kapasiteetin järjestelmänvalvoja voi ottaa käyttöön tai poistaa käytöstä sivutettujen raporttien kuormituksen kapasiteetin järjestelmänvalvojan portaalin sivulla.  Oletusarvoisesti kuormitus on käytössä kaikissa luomissasi uusissa kapasiteetissa, mutta se ei käytä muistia, ennen kuin lataat ensimmäisen sivutetun raporttisi palvelimeen.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>Miten voin seurata sivutettujen raporttien käyttöä omassa vuokraajassani?

Office 365 -valvontalokeissa eritellään tämän raporttityypin käyttö seuraavissa tapahtumissa: 

- Power BI -raportin tarkasteleminen
- Power BI -raportin poistaminen
- Power BI -raportin luominen
- Ladattu Power BI -raportti

ReportType-kentän arvona on "PaginatedReport", jolla määritetään sivutetut raportit verrattuna Power BI -raportteihin.

Lisäksi valvontalokit tarjoavat seuraavat tapahtumat  sivutetuille raporteille:

- Sidottu Power BI -tietojoukko yhdyskäytävään
- Power BI -tietolähteeseen tutustuminen
- TakeOverDatasource

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>Voinko seurata tätä kuormitusta Premium-kapasiteetin valvontasovelluksen kautta?

Kyllä. Valvonta on käytettävissä uutena välilehtenä, joka sisältää samat tiedot kuin Power BI -tietojoukoilla.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>Tarvitsenko Pro-käyttöoikeuden sivutettujen raporttien luontia ja julkaisua varten?

Voit ladata sivutettuja raportteja omaan työtilaasi ilman Pro-käyttöoikeutta, jos se on Premium-kapasiteetissa.  Muut työtilat edellyttävät Pro-käyttöoikeutta, jotta niihin voidaan luoda ja julkaista sisältöä. Rohkaisemme sinua lataamaan Power BI:n raportin muodostimen ja käyttämään sitä myös ilman Pro-käyttöoikeutta. Et voi kuitenkaan julkaista sivutettuja raportteja, jotka olet luonut ilman tätä käyttöoikeutta. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Entä jos minulla on sivutettu raportti työtilassa ja sivutetun raportin järjestelmän kuormitus on poistettu käytöstä?

Näyttöön tulee virheviesti, etkä voi tarkastella raporttia, ennen kuin kuormitus on otettu takaisin käyttöön. Voit silti poistaa raportin työtilasta.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-that-support-paginated-reports"></a>Mikä on oletusmuisti kullekin Premium-varastointiyksikölle, jotka tukevat sivutettuja raportteja?

Oletusmuisti kullekin Premium-varastointiyksikölle sivutettuja raportteja varten:

- **P1/A4**: Oletus 20 %, vähintään 10 %
- **P2/A5**: Oletus 20 %, vähintään 5 %
- **P3/A6**: Oletus 20 %, vähintään 2,5 %

Power BI ‑vuokraajien järjestelmänvalvojat voivat muokata muistin oletusarvoista enimmäisosuutta hallintaportaalista. Katso **Sivutettujen raporttien** kuormitusosio **Kapasiteettiasetukset**-välilehden **Power BI Premium** ‑kohdasta.

:::image type="content" source="media/paginated-reports-faq/paginated-reports-capacity-settings.png" alt-text="Sivutettujen raporttien Kapasiteettiasetukset-välilehti":::

## <a name="general"></a>Yleiset

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>Milloin minun pitäisi käyttää sivutettua raporttia verrattuna Power BI -raporttiin?

Sivutetut raportit sopivat parhaiten skenaarioihin, jotka edellyttävät pitkälle muotoiltua ja pikselintarkkaa sisältöä, joka on optimoitu tulostamista tai PDF:n luontia varten.  Tuloslaskelma on hyvä esimerkki raporttityypistä, jonka haluat luultavasti luoda sivutettuna raporttina.  

Power BI -raportit on optimoitu tutkimista ja vuorovaikutteisuutta varten.  Myyntiraportti, jossa eri myyjät haluavat osittaa tietoja samassa raportissa tietyille alueilleen/toimialoilleen/asiakkailleen ja nähdä, miten luvut muuttuvat, kannattaa laatia Power BI -raporttina.

### <a name="the-documentation-says-power-bi-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Dokumentaation mukaan Power BI:n raportin muodostin on ensisijainen luontityökalu. Voinko luoda sivutettuja raportteja Power BI:n SQL Server Data Toolsissa?

Kyllä, mutta Power BI -palvelu mahdollistaa vain yhden kohteen lataamisen kerrallaan, joten monia skenaarioita, joita tekijät käyttävät SQL Server Data Toolsin (SSDT) kanssa, ei vielä tueta. Täydellinen [tukemattomien ominaisuuksien luettelo](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) on jäljempänä näissä usein kysytyissä kysymyksissä.  

### <a name="what-versions-of-report-builder-do-you-support"></a>Mitkä ovat raportin muodostimen tuetut versiot?

Olemme julkaisseet Power BI Report Builderin sivutettujen raporttien ensisijaiseksi luontityökaluksi Power BI -palvelussa. Asenna [Power BI:n raportin muodostin Microsoft Download Centeristä](https://go.microsoft.com/fwlink/?linkid=2086513).

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>Miten voin siirtää Power BI:hin olemassa olevat raportit, jotka olen tallentanut SQL Reporting Servicesessä?

GitHubissa olevat projektit tukevat nyt sisällön siirtämistä SQL Server Reporting Servicesistä Power BI:hin.  Tarkastele tietoja ja lataa työkalu täältä: [https://github.com/microsoft/RdlMigration](https://github.com/microsoft/RdlMigration)

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Voinko avata raportteja ja julkaista ne suoraan palveluun?

Kyllä. Olemme lisänneet tuen raporttien avaamiselle ja niiden julkaisemiselle suoraan Power BI Report Builderissa.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>Mitä SSRS:n sivutettuja raporttiominaisuuksia ei vielä tueta Power BI:ssä?

Tällä hetkellä sivutetut raportit eivät tue seuraavia kohteita:

- Jaetut tietolähteet
- Jaetut tietojoukot
- Aliraportit
- Porautuminen ja napsauttaminen muihin raportteihin
- Linkitetyt raportit
- Bing-karttakerrokset
- Mukautetut fontit

Saat virheviestin, jos yrität ladata tiedoston, jolla on tukematon ominaisuus Power BI -palvelussa (muu kuin vaihto/lajittelu).

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Mitä tietolähteitä tuette nykyisin sivutetuille raporteille?

Artikkelissa [Power BI:n sivutetuissa raporteissa tuetut tietolähteet](paginated-reports-data-sources.md) on luettelo tietolähteistä. 

### <a name="what-authentication-methods-do-you-support"></a>Mitä todennusmenetelmiä tuette?

Tuemme SSO:ta Azure Analysis Services -palveluissa, Microsoft Azuren SQL-tietokannassa ja Power BI -tietolähteissä.  Tuemme myös OAuthia Microsoft Azuren SQL-tietokannassa ja Azure Analysis Services -palveluissa.  Muille tietolähteille on tallennettava nykyisin käyttäjänimi ja salasana tietolähteen kanssa portaaliin tai yhdyskäytävään.  

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Voinko käyttää Power BI -tietojoukkoa tietolähteenä omalle sivutetulle raportilleni?

Kyllä, tuemme Power BI -tietojoukkoja sivutettujen raporttien tietolähteinä.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Voinko käyttää tallennettuja toimintosarjoja yhdyskäytävän kautta?

Kyllä, tallennettujen toimintosarjojen käyttämistä yhdyskäytävän kautta tuetaan SQL Server -tietolähteille, mukaan lukien niille, jotka käyttävät parametreja.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Mitkä vientimuodot ovat saatavilla raportilleni Power BI -palvelussa?

Voit viedä raportin Microsoft Exceliin, Microsoft Wordiin, Microsoft PowerPointiin, PDF:ään, .CSV:een, XML:ään ja MHTML:een.

### <a name="can-i-print-paginated-reports"></a>Voinko tulostaa sivutettuja raportteja?

Kyllä, tulostus on käytettävissä sivutetuille raporteille, minkä lisäksi tulostuksen esikatselua on parannettu. 

### <a name="are-e-mail-subscriptions-available-for-paginated-reports"></a>Ovatko sähköpostitilaukset käytettävissä sivutetuille raporteille?

Kyllä, sähköpostitilauksia tuetaan täysin sivutetuille raporteille, ja ne sisältävät kuuden erilaisen tiedostomuodon ja parametriarvon tuen.

### <a name="can-i-run-custom-code-in-my-report"></a>Voinko suorittaa mukautetun koodin raportissani?

Kyllä, tuemme kykyä suorittaa koodin raporteissasi samalla tavoin kuin SSRS:ssä.

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Voinko käyttää sisäistä Power BI:tä upottamaan sivutetut raportit sovellukseen, jota isännöin?

SaaS-upotus, mukaan lukien suojatun upotuksen tuki, on jo käytettävissä. Saat lisätietoja PaaS-upotuksesta opetusohjelmasta [Power BI:n sivutetun raportin upottaminen sovellukseen asiakkaitasi varten](../developer/embed-paginated-reports-customers.md).

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Voinko porautua Power BI -raportista sivutettuun raporttiin?

Kyllä, tämä voidaan tehdä käyttämällä URL-parametreja sivutettujen raporttien kanssa.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Voinko jakaa oman sivutetun raportin sisältöni Power BI -sovelluksen kautta?

Kyllä, sivutettujen raporttien tuki on tarkoitus ottaa käyttöön sovelluksissa sekä v1- että v2-työtiloissa. 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>Toimivatko muut raporttikohtaiset ominaisuudet Power BI:ssä, kuten raporttiruutujen kiinnittäminen koontinäyttöihin ja sivutettujen raporttien käsitteleminen?

Tarkoituksenamme on ottaa käyttöön mahdollisimman laajasti raporttien tuki palvelun samoille tärkeille skenaarioille.  Vaikka raporttien luontityökalu onkin erilainen, käyttäjien kannalta parhainta olisi lisätä raportti portaalin luetteloon. Käyttäjälle tärkeintä ei ole raportin luontitapa vaan se, että hän voi suorittaa haluamansa tehtävät.  Hyvä esimerkki tästä ominaisuuspariteetista on suunniteltu kommenttien tuki. Vaikka itse ominaisuus toimiikin ehkä hieman eri tavalla kunkin raporttityypin mukaan, kummassakin voidaan käyttää kommentteja.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Onko Power BI -palvelussa raporttien katseluohjelman hallinta sivutetuille raporteille?

Ei, raporttien katseluohjelman hallintaa ei tällä hetkellä ole saatavilla.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Voidaanko sivutettuja raportteja hakea Power BI -palvelun uudesta Aloitus-kohdasta?

Kyllä, voit nyt hakea sivutettuja raportteja Aloitus-kohdasta.  Näet ne myös uuden Aloitus-kohdan muissa osissa.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Asenna Power BI:n raportin muodostin Microsoft Download Centeristä](https://go.microsoft.com/fwlink/?linkid=2086513)
- [Opetusohjelma: Luo sivutettu raportti](paginated-reports-quickstart-aw.md)
