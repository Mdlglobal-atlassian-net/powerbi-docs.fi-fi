---
title: 'Sivutetut raportit Power BI:ssä: usein kysytyt kysymykset (esikatselu)'
description: Tässä artikkelissa vastataan usein kysyttyihin kysymyksiin sivutetuista raporteista. Näiden raporttien pitkälle muotoiltu ja pikselintarkka sisältö on optimoitu tulostamista tai PDF:n luontia varten.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: overview
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: 0ddf95563c52af135ac7ae4fe71aeddcd2ce7313
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/07/2018
ms.locfileid: "51267276"
---
# <a name="paginated-reports-in-power-bi-faq-preview"></a>Sivutetut raportit Power BI:ssä: usein kysytyt kysymykset (esikatselu)

Tässä artikkelissa vastataan usein kysyttyihin kysymyksiin sivutetuista raporteista. Näiden raporttien pitkälle muotoiltu ja pikselintarkka sisältö on optimoitu tulostamista tai PDF:n luontia varten. Niitä kutsutaan ”sivutetuiksi”, koska ne on muotoiltu sopimaan hyvin useille sivuille. Sivutetut raportit perustuvat SQL Server Reporting Servicesin RDL-raporttitekniikkaan. 

Tässä artikkelissa vastataan useisiin yleisiin kysymyksiin, joita käyttäjillä on Power BI Premiumin sivutetuista raporteista ja raportin muodostimesta, sivutettujen raporttien erillisestä luontityökalusta. Tarvitset Power BI Pro -käyttöoikeuden raportin julkaisemiseksi palveluun. Voit julkaista ja jakaa sivutettuja raportteja omassa työtilassasi tai sovelluksen työtiloissa niin kauan kuin työtila on Power BI Premium -kapasiteetissa. 

## <a name="administration"></a>Hallinta

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Minkä kokoista Premium-kapasiteettia tarvitsen sivutettuja raportteja varten?

Sivutettujen raporttien kuormitus on käytettävissä P1– P3-varastointiyksiköissä julkista esikatselua varten.  Voit myös käyttää sitä testi-/kehitysskenaarioita varten A4–A6-varastointiyksikköjen kanssa.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Mikä on muistin enimmäisraja, jota voin soveltaa sivutettuihin raportteihin kapasiteetissa?

Voit nykyisin varata vain 50 prosenttia muistista tätä kuormitusta varten. 

### <a name="how-does-user-access-work-for-paginated-reports"></a>Miten käyttöoikeudet toimivat sivutettujen raporttien kanssa?

Sivutettujen raporttien käyttöoikeudet ovat samat kuin käyttäjän oikeudet kaikkeen muuhun sisältöön Power BI -palvelussa. 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Miten voin ottaa käyttöön / poistaa käytöstä raporttien kuormituksen?

Kapasiteetin järjestelmänvalvoja voi ottaa käyttöön tai poistaa käytöstä sivutettujen raporttien kuormituksen kapasiteetin järjestelmänvalvojan portaalin sivulla.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>Miten voin seurata sivutettujen raporttien käyttöä omassa vuokraajassani?

Office 365 -valvontalokeissa eritellään tämän raporttityypin käyttö seuraavissa tapahtumissa: 

- Power BI -raportin tarkasteleminen
- Power BI -raportin poistaminen
- Power BI -raportin luominen
- Ladattu Power BI -raportti

ReportType-kentän arvona on ”PaginatedReport”, jolla määritetään sivutetut raportit verrattuna Power BI -raportteihin.

Lisäksi valvontalokit tarjoavat seuraavat tapahtumat  sivutetuille raporteille:

- Sidottu Power BI -tietojoukko yhdyskäytävään
- Power BI -tietolähteeseen tutustuminen
- TakeOverDatasource

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>Voinko seurata tätä kuormitusta Premium-kapasiteetin valvontasovelluksen kautta?

Et vielä. Valvonta on saatavana julkisessa esikatselussa uutena välilehtenä olemassa olevassa raportissa samoilla asianmukaisilla tiedoilla, joita sinulla on Power BI -tietojoukoille.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>Tarvitsenko Pro-käyttöoikeuden sivutettujen raporttien luontia ja julkaisua varten?

Kyllä. Et voi ladata raportteja työtilaan ilman Pro-käyttöoikeutta. Voit ladata raportin muodostimen ja kokeilla sitä ilman Pro-käyttöoikeutta, mutta et julkaista luomiasi raportteja. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Entä jos minulla on sivutettu raportti työtilassa ja sivutetun raportin järjestelmän kuormitus on poistettu käytöstä?

Näyttöön tulee virheviesti, etkä voi tarkastella raporttia, ennen kuin kuormitus on otettu takaisin käyttöön. Voit silti poistaa raportin työtilasta.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>Mikä on oletusmuisti kullekin Premium-varastointiyksikölle, joita tuetaan sivutetuille raporteille?

Oletusmuisti kullekin Premium-varastointiyksikölle sivutettuja raportteja varten:

- **P1/A4**: oletus 20 %, vähintään 10 %
- **P2/A5**: oletus 10 %, vähintään 5 %
- **P3/A6**: oletus 5 %, vähintään 2,5 %

## <a name="general"></a>Yleinen

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>Milloin minun pitäisi käyttää sivutettua raporttia verrattuna Power BI -raporttiin?

Sivutetut raportit sopivat parhaiten skenaarioihin, jotka edellyttävät pitkälle muotoiltua ja pikselintarkkaa sisältöä, joka on optimoitu tulostamista tai PDF:n luontia varten.  Tuloslaskelma on hyvä esimerkki raporttityypistä, jonka haluat luultavasti luoda sivutettuna raporttina.  

Power BI -raportit on optimoitu tutkimista ja vuorovaikutteisuutta varten.  Myyntiraportti, jossa eri myyjät haluavat osittaa tietoja samassa raportissa tietyille alueilleen/toimialoilleen/asiakkailleen ja nähdä, miten luvut muuttuvat, kannattaa laatia Power BI -raporttina.

### <a name="the-documentation-says-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Dokumentaation mukaan raportin muodostin on ensisijainen luontityökalu. Voinko luoda sivutettuja raportteja Power BI:n SQL Server Data Toolsissa?

Kyllä, mutta Power BI -palvelu mahdollistaa vain yhden kohteen lataamisen kerrallaan, joten monia skenaarioita, joita tekijät käyttävät SQL Server Data Toolsin (SSDT) kanssa, ei vielä tueta. Täydellinen [tukemattomien ominaisuuksien luettelo](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) on jäljempänä näissä usein kysytyissä kysymyksissä.  

### <a name="what-versions-of-report-builder-do-you-support"></a>Mitkä ovat raportin muodostimen tuetut versiot?

Käytä SQL Server 2016:n raportin muodostimen uusinta versiota raporttien luontiin ja julkaisuun Power BI -palveluun. Asenna [raportin muodostin Microsoft Download Centeristä](https://www.microsoft.com/download/details.aspx?id=53613).

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>Miten voin siirtää Power BI:hin olemassa olevat raportit, jotka olen tallentanut SQL Reporting Servicesessä?

Sinun on ladattava raportti palvelimesta ja ladattava se sitten Power BI:hin portaalin kautta.  Tällä hetkellä ei ole saatavilla siirtotyökalua, mutta tarkoituksenamme on luoda tällainen sen jälkeen, kun olemme päättäneet julkisen esikatselun ja saavuttaneet oikean ominaisuuspariteettitason tuotteiden välillä.

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Voinko avata raportteja ja julkaista ne suoraan palveluun?

Et vielä tässä vaiheessa. Lisäämme tuen raporttien avaamiselle ja niiden julkaisemiselle suoraan raportin muodostimesta jossakin vaiheessa, samalla tavoin kuin voit tehdä Power BI Desktopissa.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>Mitä SSRS:n sivutettuja raporttiominaisuuksia ei vielä tueta Power BI:ssä?

Tällä hetkellä sivutetut raportit eivät tue seuraavia kohteita:

- Jaetut tietolähteet
- Jaetut tietojoukot
- Aliraportit
- Napsauttamalla tarkasteltavat toiminnot ja alirakennetoiminnot
- Linkitetyt raportit
- Kirjanmerkit
- Bing-karttakerrokset
- Mukautetut fontit
- Piilotetut parametrit

Vaihto ja vuorovaikutteinen lajittelu eivät vielä ole tuotannossa, mutta niitä odotetaan pian.    

Saat virheviestin, jos yrität ladata tiedoston, jolla on tukematon ominaisuus Power BI -palvelussa (muu kuin vaihto/lajittelu).

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Mitä tietolähteitä tuette nykyisin sivutetuille raporteille?

Tuemme Azure SQL -tietokantaa, SQL Serveriä ja SQL Server Analysis Services (SSAS) -taulukkomalleja, jotka käyttävät paikallista yhdyskäytävää. Emme tue nykyisin SSAS (MDX) -monidimensiomalleja.

Kun SSAS-malleja käytetään yhdyskäytävän kautta, käyttäjä, jonka tunnistetiedot on tallennettu, tarvitsee korkeammat käyttöoikeudet SSAS-malleihin voidakseen työskennellä yhdyskäytävän kautta.

### <a name="what-authentication-methods-do-you-support"></a>Mitä todennusmenetelmiä tuette?

Sinun on nykyisin tallennettava käyttäjänimi ja salasana tietolähteen kanssa portaalissa tai yhdyskäytävässä.  Esikatseluun on tulossa myöhemmin muita todennusmenetelmiä tukemaan esimerkiksi rivitason suojausta.

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Voinko käyttää Power BI -tietojoukkoa tietolähteenä omalle sivutetulle raportilleni?

Et vielä, mutta tämä tuki on suunnitteilla pian.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Voinko käyttää tallennettuja toimintosarjoja yhdyskäytävän kautta?

Voit käyttää tallennettua toimintosarjaa yhdyskäytävän kautta, ellei tallennetulla toimintosarjalla ole parametreja.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Mitkä vientimuodot ovat saatavilla raportilleni Power BI -palvelussa?

Voit viedä raportin Microsoft Exceliin, Microsoft Wordiin, Microsoft PowerPointiin, PDF:ään, .CSV:een, XML:ään ja MHTML:een.

### <a name="can-i-print-paginated-reports"></a>Voinko tulostaa sivutettuja raportteja?

Voit nykyisin viedä raportin PDF:ään ja tulostaa tiedoston. Tulostus suoraan sivutetusta raportista pitäisi pian olla käytettävissä. 

### <a name="are-e-mail-subscriptions-available-yet-for-paginated-reports"></a>Ovatko sähköpostitilaukset jo käytettävissä sivutetuille raporteille?

Eivät, sähköpostitilaukset ovat tulossa myöhemmin.

### <a name="what-features-from-ssrs-will-you-be-supporting-in-the-power-bi-service"></a>Mitä SSRS-ominaisuuksia tuette Power BI -palvelussa?

Tarkoituksenamme on tarjota mahdollisimman läheinen pariteetti näiden kahden tuotteen välille.  SSRS:n ja Power BI:n joitakin toimintoja ei ole ehkä järkevää yrittää muuttaa sopimaan olemassa oleviin SSRS-malleihin, kuten Power BI:n eri käyttöoikeusmalleja, mutta pyydämme palautetta asiakkailta ja kumppaneilta tällaisten päätösten tekemiseksi.

### <a name="can-i-run-custom-code-in-my-report"></a>Voinko suorittaa mukautetun koodin raportissani?

Kyllä, tuemme kykyä suorittaa koodin raporteissasi samalla tavoin kuin SSRS:ssä.

### <a name="does-this-mean-ssrs-is-going-away"></a>Tarkoittaako tämä sitä, että SSRS on poistumassa?

Ei lainkaan.  Tämä uusi valikoima tarjoaa asiakkaille pilvipohjaisen vaihtoehdon heidän sivutetuille raporteilleen.  

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Voinko käyttää sisäistä Power BI:tä upottamaan sivutetut raportit sovellukseen, jota isännöin?

Tarkoituksenamme on tukea tätä skenaariota olemassa olevissa Power BI -ohjelmointirajapinnoissa, mutta emme ole vielä määrittäneet aikarajaa sille, milloin tämä skenaario on käytettävissä.

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Voinko porautua Power BI -raportista sivutettuun raporttiin?

Et vielä, mutta tarkoituksenamme on ehdottomasti tukea tätä skenaariota.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Voinko jakaa oman sivutetun raportin sisältöni Power BI -sovelluksen kautta?

Voit nykyisin jakaa yksittäiset sivutetut raportit muiden käyttäjien kanssa jakotoiminnon kautta portaalissa. Emme vielä tue jakamista sovelluksessa, mutta tämä toiminto tulossa pian. Meillä on myös jakopainike työkalurivillä.

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>Toimivatko muut raporttikohtaiset ominaisuudet Power BI:ssä, kuten raporttiruutujen kiinnittäminen koontinäyttöihin ja sivutettujen raporttien käsitteleminen?

Tarkoituksenamme on ottaa käyttöön mahdollisimman laajasti raporttien tuki palvelun samoille tärkeille skenaarioille.  Vaikka raporttien luontityökalu onkin erilainen, käyttäjien kannalta parhainta olisi lisätä raportti portaalin luetteloon. Käyttäjälle tärkeintä ei ole raportin luontitapa vaan se, että hän voi suorittaa haluamansa tehtävät.  Hyvä esimerkki tästä ominaisuuspariteetista on suunniteltu kommenttien tuki. Vaikka itse ominaisuus toimiikin ehkä hieman eri tavalla kunkin raporttityypin mukaan, kummassakin voidaan käyttää kommentteja.

### <a name="are-you-planning-to-create-a-new-authoring-tool-for-paginated-reports-in-the-power-bi-service--we-cant-do-everything-we-need-to-with-report-builder-today"></a>Aiotteko luoda uuden luontityökalun sivutetuille raporteille Power BI -palvelussa?  Emme voi tehdä nykyisin kaikkea haluamaamme raportin muodostimella.

Vaikka pohdimmekin yhä parasta työkalua koskevia eri vaihtoehtoja, tuemme jatkossakin tiettyjä ominaisuuksia, kuten ALM:tä, mukautettuja laajennuksia ja muita ominaisuuksia, jotka voidaan ehkä sisällyttää vain yhteen SSRS:n luontityökaluun. 

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>Onko suunnitteilla siirtotyökalua, jotta SSRS-asiakkaat voivat siirtää olemassa olevat raporttinsa ja resurssinsa  Power BI:hin?

Kyllä, mutta ei ennen kuin Power BI -palvelun tärkeimmät tuetut ominaisuudet ovat valmiita.

### <a name="will-i-ever-be-able-to-create-both-paginated-reports-and-power-bi-reports-in-a-single-authoring-tool"></a>Voinko vastaisuudessa luoda sekä sivutettuja raportteja että Power BI -raportteja yhdessä luontityökalussa?

Emme nykyisin suunnittele yhtä luontityökalua, mutta etsimme keinoja mahdollisesti yhdistää luontityökalut yhdeksi BI-paketiksi erillisten latausten/tuotemukautusten sijasta.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Onko Power BI -palvelussa raporttien katseluohjelman hallinta sivutetuille raporteille?

Ei, nykyisin ei ole saatavilla raporttien katseluohjelman hallintaa.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Voidaanko sivutettuja raportteja hakea Power BI -palvelun uudesta Aloitus-kohdasta?

Ei, et voi tällä hetkellä hakea sivutettuja raportteja Aloitus-kohdasta.  Näet ne kuitenkin uuden Aloitus-kohdan muissa osissa.

## <a name="next-steps"></a>Seuraavat vaiheet

- [Raportin muodostimen asentaminen Microsoft Download Centeristä](https://www.microsoft.com/download/details.aspx?id=53613)
- [Opetusohjelma: Sivutetun raportin luominen](paginated-reports-quickstart-aw.md)