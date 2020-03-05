---
title: SQL Server Reporting Services -raporttien siirtäminen Power BI:hin
description: Lue ohjeet siihen, miten voit siirtää SQL Server Reporting Services (SRSS) -raportit Power BI:hin.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/03/2020
ms.author: v-pemyer
ms.openlocfilehash: f8b7cc302cd4a26aa099f723f47865723dccb7c9
ms.sourcegitcommit: b59ec11a4a0a3d5be2e4d91548d637d31b3491f8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/05/2020
ms.locfileid: "78290632"
---
# <a name="migrate-sql-server-reporting-services-reports-to-power-bi"></a>SQL Server Reporting Services -raporttien siirtäminen Power BI:hin

Tämä artikkeli on tarkoitettu SQL Server Reporting Services (SSRS) -raportteja luoville käyttäjille ja Power BI -järjestelmänvalvojille. Se sisältää ohjeet siihen, miten voit siirtää [Report Definition Language (RDL)](/sql/reporting-services/reports/report-definition-language-ssrs) -raporttisi Power BI:hin.

> [!NOTE]
> Vain RDL-raportteja voi siirtää. Power BI:ssä RDL-raportteja kutsutaan _sivutetuiksi raporteiksi_.

Ohjeet on jaettu neljään vaiheeseen. Suosittelemme, että luet ensin koko artikkelin, ennen kuin aloitat raporttiesi siirtämisen.

1. [Ennen aloittamista](#before-you-start)
1. [Esisiirtämisvaihe](#pre-migration-stage)
1. [Siirtämisvaihe](#migration-stage)
1. [Jälkisiirtämisvaihe](#post-migration-stage)

Voit toteuttaa tämän siirtämisen ilman SSRS-palvelimien käyttökatkoja tai häiriöitä raporttiesi käyttäjille. On tärkeää ymmärtää se, että mitään tietoja tai raportteja ei tarvitse poistaa. Tämä tarkoittaa siis siitä, että voit pitää nykyisen ympäristösi paikoillaan, kunnes olet valmis poistamaan sen käytöstä.

## <a name="before-you-start"></a>Ennen aloittamista

Tarkista ennen siirtämisen aloittamista, että ympäristösi täyttää tietyt vaatimukset. Kerromme näistä vaatimuksista ja esittelemme sinulle hyödyllisen siirtotyökalun.

### <a name="preparing-for-migration"></a>Siirtämiseen valmistautuminen

Kun valmistaudut siirtämään raporttisi Power BI:hin, varmista ensin, että organisaatiollasi on [Power BI Premium](../service-premium-what-is.md) -tilaus. Tämä tilaus vaaditaan, jotta voit isännöidä ja suorittaa Power BI:n sivutettuja raportteja.

### <a name="supported-versions"></a>Tuetut versiot

Voit siirtää paikallisissa palvelimissa vai pilvipalveluntarjoajien (esimerkiksi Azure) virtuaalikoneissa isännöityjä SSRS-esiintymiä.

Seuraava luettelo sisältää SQL Server -versiot, joissa tuetaan Power BI:hin siirtymistä:

> [!div class="checklist"]
> - SQL Server 2012
> - SQL Server 2014
> - SQL Server 2016
> - SQL Server 2017
> - SQL Server 2019.

Siirtäminen on mahdollista myös Power BI -raporttipalvelimesta.

### <a name="migration-tool"></a>Siirtotyökalu

Suosittelemme, että käytät [RDL-siirtotyökalua](https://github.com/microsoft/RdlMigration): se auttaa sinua valmistelemaan ja siirtämään raporttisi. Microsoft kehitti tämän työkalun auttaakseen asiakkaitaan siirtämään RDL-raportteja SSRS-palvelimistaan Power BI:hin. Se on saatavilla GitHubista. Sille on saatavilla kattavat ohjeet siirtämisskenaariota varten.

Työkalu automatisoi seuraavat tehtävät:

- Se tarkistaa, onko sinulla [tukemattomia tietolähteitä](../paginated-reports-data-sources.md) ja [raporttitoimintoja](../paginated-reports-faq.md#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi).
- Se muuntaa kaikki _jaetut_ resurssit _upotetuiksi_ resursseiksi:
  - Jaetuista **tietolähteistä** tulee upotettuja tietolähteitä.
  - Jaetuista **tietojoukoista** tulee upotettuja tietojoukkoja.
- Se julkaisee (tarkistukset läpäisevät) raportit sivutettuina raportteina määritettyyn Power BI -työtilaan (Premium-kapasiteetissa).

Se ei muokkaa tai poista olemassa olevia raporttejasi. Kun työkalu on valmis, se tuottaa yhteenvedon kaikista suoritetuista (sekä onnistuneista että epäonnistuneista) toiminnoista.

Microsoft saattaa parantaa työkalua ajan myötä. Myös yhteisöä kannustetaan osallistumaan ja auttamaan sen parantamisessa.

## <a name="pre-migration-stage"></a>Esisiirtämisvaihe

Kun olet varmistanut organisaatiosi täyttävän edellytykset, olet valmis aloittamaan _esisiirtämisvaiheen_. Tässä vaiheessa on kolme alivaihetta:

1. Tutustu
1. Arvioi
1. Valmistele

### <a name="discover"></a>Tutustu

_Tutustu_-vaiheen tarkoituksena on tunnistaa olemassa olevat SSRS-esiintymät. Tässä prosessissa verkosta tarkistetaan ja tunnistetaan kaikki organisaatiosi SQL Server -esiintymät.

Voit käyttää [Microsoft Assessment and Planning Toolkitia](https://www.microsoft.com/download/details.aspx?id=7826). Myös MAP Toolkit -nimellä tunnettu työkalupaketti etsii ja raportoi SQL Server -esiintymäsi ja -versiosi sekä asennetut toiminnot. Se on tehokas inventaario-, arviointi- ja raportointityökalu, joka voi yksinkertaistaa siirtämisen suunnitteluprosessia.

### <a name="assess"></a>Arvioi

Kun olet löytänyt SSRS-esiintymäsi, _Arvioi_-vaiheen tarkoituksena on selvittää SSR-raportit – tai palvelinkohteet – joita ei voida siirtää.

Vain RDL-raportteja voi siirtää SSRS-palvelimista Power BI:hin. Jokaisesta siirretyistä RDL-raportista tulee Power BI:n sivutettu raportti.

Seuraavia SSRS-kohdetyyppejä ei kuitenkaan voi siirtää Power BI:hin:

- jaetut tietolähteet<sup>1</sup>
- jaetut tietojoukot<sup>1</sup>
- resurssit, esimerkiksi kuvatiedostot
- suorituskykyilmaisimet (SSRS 2016 tai uudempi – vain Enterprise Edition)
- mobiiliraportit (SSRS 2016 tai uudempi – vain Enterprise Edition)
- raporttimallit (poistettu käytöstä)
- raporttiosat (poistettu käytöstä).

<sup>1</sup> [RDL-siirtotyökalu](https://github.com/microsoft/RdlMigration) muuntaa jaetut tietolähteet ja jaetut tietojoukot automaattisesti, kunhan ne käyttävät tuettuja tietolähteitä.

Jos RDL-raporttisi käyttävät toimintoja tai ominaisuuksia, [joita ei ole tueta Power BI:n sivutetuissa raporteissa](../paginated-reports-faq.md#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi), voit kehittää ne uudelleen [Power BI -raportteina](../consumer/end-user-reports.md). Vaikka RDL-raporttisi voidaan siirtää, suosittelemme kuitenkin, että harkitset niiden nykyaikaistamista Power BI -raporteiksi, jos tämä on toteuttamiskelpoista.

Jos RDL-raporttisi on noudettava tietoja _paikallisista tietolähteistä_, ne eivät voi käyttää kertakirjautumista (SSO). Tällä hetkellä kaikki tietojen nouto näistä lähteistä tehdään käyttämällä _yhdyskäytävän tietolähteen käyttäjätilin_ suojauskontekstia. SQL Server Analysis Services (SSAS) ei voi pakottaa rivitason suojausta (RLS) käyttäjäkohtaisesti.

Yleensä Power BI:n sivutetut raportit on optimoitu **tulostamista** ja **PDF-tiedostojen luomista**  varten. Power BI -raportit on taas optimoitu **analysointia ja vuorovaikutteisuutta** varten. Saat lisätietoja ohjeartikkelista [Milloin sivutettuja raportteja kannattaa käyttää Power BI:ssä?](report-paginated-or-power-bi.md)

### <a name="prepare"></a>Valmistele

_Valmistele_-vaiheessa kaikki laitetaan valmiiksi. Se käsittää Power BI -ympäristön valmistelun, raporttien suojaamisen ja julkaisemisen suunnittelun sekä ideat niiden SSRS-kohteiden uudelleenkehittämiseksi, joita ei voida siirtää.

1. Varmista, että [sivutettujen raporttien kuormitus](../service-admin-premium-workloads.md#paginated-reports) on käytössä Power BI Premium -kapasiteetissasi ja että sillä on riittävästi muistia.
1. Varmista raportin [tietolähteiden](../paginated-reports-data-sources.md) tuki ja ota käyttöön [Power BI -yhdyskäytävä](../service-gateway-onprem.md), joka mahdollistaa yhteydet paikallisiin tietolähteisiin.
1. Tutustu Power BI:n suojaukseen ja suunnittele, [miten luot SSRS-kansiot ja -käyttöoikeudet](/sql/reporting-services/security/secure-folders) uudelleen [Power BI:n työtiloilla ja työtilarooleilla](../service-new-workspaces.md).
1. Tutustu Power BI:n jakamiseen ja suunnittele, miten jaat sisältöä julkaisemalla [Power BI -sovelluksia](../service-create-distribute-apps.md).
1. Harkitse [jaettujen Power BI -tietojoukkojen](../service-datasets-build-permissions.md) käyttöä SSRS:n jaettujen tietolähteiden asemesta.
1. Luo [Power BI Desktopilla](../desktop-what-is-desktop.md) mobiilioptimoituja raportteja. Voit käyttää esimerkiksi [Power BI:n mukautettuja suorituskykymittarivisualisointeja](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083?tab=Overview) SSRS:n mobiiliraporttien ja suorituskykymittareiden asemesta.
1. Arvioi uudelleen sisäisen **Käyttäjätunnus**-kentän käyttö raporteissasi. Jos luotat **Käyttäjätunnukseen** raporttitietojen suojaamisessa, huomaa, että sivutetuissa raporteissa (Power BI -palvelussa isännöitynä) se palauttaa täydellisen käyttäjätunnuksen. NT-tilin nimen, esimerkiksi _AW\mblythe_, palauttamisen sijaan sisäinen kenttä palauttaa jotain tämänkaltaista: _m. Blythe&commat;adventureworks.com_. Sinun on muokattava tietojoukkomäärityksiä ja mahdollisesti lähdetietoja. Muokkaamisen ja julkaisun jälkeen suosittelemme, että testaat raporttisi perusteellisesti varmistaaksesi, että tietojen käyttöoikeudet toimivat odotetulla tavalla.
1. Arvioi uudelleen sisäisen **ExecutionTime**-kentän käyttö raporteissasi. Jos kyseessä ovat sivutetut raportit (Power BI -palvelussa isännöitynä), sisäinen kenttä palauttaa päivämäärän/ajan _koordinoituna yleisaikana (UTC)_ . Se voi vaikuttaa raporttiparametrin oletusarvoihin ja raportin suorituksen aikatunnisteeseen (jotka yleensä lisätään raportin alatunnisteisiin).
1. Jos tietolähteesi on SQL Server (paikallinen), tarkista, että raportit eivät käytä kartan visualisointeja. Kartan visualisointi riippuu SQL Serverin spatiaalisista tietotyypeistä, eikä yhdyskäytävä tue niitä. Lisätietoja on kohdassa [Sivutettujen raporttien tietojen nouto-ohjeet (SQL Serverin monimutkaiset tietotyypit)](report-paginated-data-retrieval.md#sql-server-complex-data-types).
1. Varmista, että raportteja luovilla käyttäjillä on [Power BI Report Builder](../report-builder-power-bi.md) asennettuna ja että uudet versiot voidaan jakaa jatkossa helposti koko organisaatioosi.

## <a name="migration-stage"></a>Siirtämisvaihe

Kun olet valmistellut Power BI -ympäristön ja -raporttisi, olet valmis _siirtämisvaiheeseen_.

Voit siirtää joko _manuaalisesti_ tai _automaattisesti_. Manuaalinen siirtäminen sopii tilanteisiin, joissa siirrettäviä raportteja on vähän tai joissa raportteja täytyy muokata ennen siirtämistä. Automaattinen siirtäminen sopii tilanteisiin, joissa siirrettäviä raportteja on paljon.

### <a name="manual-migration"></a>Manuaalinen siirtäminen

Kuka tahansa, jolla on SSRS-esiintymän ja Power BI -työtilan käyttöoikeus, voi siirtää raportteja manuaalisesti Power BI:hin. Tämän voi tehdä seuraavasti:

1. Avaa se SSRS-portaali, joka sisältää siirrettävät raportit.
1. Lataa jokainen raporttimääritelmä ja tallenna .rdl-tiedostot paikallisesti.
1. Avaa Power BI Report Builderin _uusin versio_. Muodosta yhteys Power BI -palveluun Azure AD -tunnistetiedoillasi.
1. Avaa kukin raportti Power BI Report Builderissa ja toimi sitten seuraavasti:
   1. Varmista, että kaikki tietolähteet ja tietojoukot on upotettu raporttimääritelmään ja että ne ovat [tuettuja tietolähteitä](../paginated-reports-data-sources.md).
   1. Esikatsele raportti ja tarkista, että se näkyy oikein.
   1. Valitse _Tallenna nimellä_ ja valitse sitten _Power BI -palvelu_.
   1. Valitse työtila, joka sisältää raportin.
   1. Tarkista, että raportti tallennetaan. Jos joitain raporttisi ominaisuuksia tai toimintoja ei vielä tueta, sen tallentaminen ei onnistu. Saat ilmoituksen syistä tähän. Tässä tapauksessa sinun täytyy muokata raporttiasi ja tallentaa se sitten uudelleen.

### <a name="automated-migration"></a>Automaattinen siirtäminen

Automaattiseen siirtämiseen on kaksi vaihtoehtoa. Voit käyttää

- RDL-siirtotyökalua
- SSRS:n ja Power BI:n julkisesti saatavilla olevia ohjelmointirajapintoja.

[RDL-siirtotyökalu](#migration-tool) on jo kuvattu tässä artikkelissa.

Voit automatisoida sisältösi siirtämisen julkisesti saatavilla olevilla SSRS:n ja Power BI:n ohjelmointirajapinnoilla. Vaikka RDL-siirtotyökalu käyttääkin jo näitä ohjelmointirajapintoja, voit kehittää oman työkalun, joka vastaa vaatimuksiasi tarkasti.

Saat lisätietoja ohjelmointirajapinnoista seuraavista ohjeartikkeleista:

- [Power BI:n REST-ohjelmointirajapinnan viite](../developer/rest-api-reference.md)
- [SQL Server Reporting Servicesin REST-ohjelmointirajapinnat](/sql/reporting-services/developer/rest-api).

## <a name="post-migration-stage"></a>Jälkisiirtämisvaihe

Kun olet suorittanut siirtämisen, olet valmis _jälkisiirtämisvaiheeseen_. Tässä vaiheessa suoritat joukon jälkisiirtotehtäviä, joilla varmistat kaiken toimivan oikein ja tehokkaasti.

### <a name="configure-data-sources"></a>Tietolähteiden määrittäminen

Kun raportit on siirretty Power BI:hin, sinun täytyy varmistaa, että niiden tietolähteet on määritetty oikein. Tämä voi sisältää yhdyskäytävätietolähteiden määrittämistä ja [tietolähteiden tunnistetietojen suojattua tallentamista](../paginated-reports-data-sources.md#azure-sql-database-authentication). Näitä toimintoja ei tehdä RDL-siirtotyökalulla.

### <a name="review-report-performance"></a>Raportin tehokkuuden tarkistaminen

Suosittelemme painokkaasti, että suoritat seuraavat toimenpiteet. Niillä varmistat raporttien toimivuuden käyttäjille:

1. Testaa raportit kaikilla [Power BI:n tukemilla selaimilla](../power-bi-browsers.md) ja varmista, että raportit näkyvät oikein.
1. Suorita testejä, joilla vertailet näyttämisaikoja SSRS:ssä ja Power BI:ssä. Tarkista, että Power BI -raportit näytetään hyväksyttävässä ajassa.
1. Jos Power BI -raportin näyttäminen epäonnistuu, koska muisti ei riitä, varaa [lisää resursseja Power BI Premium -kapasiteettiin](../service-admin-premium-workloads.md#paginated-reports).
1. Jos raportin näyttäminen kestää kauan, sinun kannattaa harkita sitä, että Power BI toimittaa ne raporttiesi käyttäjille [sähköpostitilauksina, jotka sisältävät raporttiliitteet](../consumer/paginated-reports-subscriptions.md).
1. Tarkista Power BI -tietojoukkoihin perustuvista Power BI -raporteista mallitoteutukset ja varmista, että ne ovat täysin optimoituja.

### <a name="reconcile-issues"></a>Ongelmien korjaaminen

Jälkisiirtämisvaihe on elintärkeä mahdollisten ongelmien korjaamisten ja tehokkuuspuutteiden korjaamisen kannalta. Sivutettujen raporttien kuormituksen lisääminen kapasiteettiin voi hidastaa suorituskykyä sivutetuille raporteille ja _muulle kapasiteettiin tallennetulle sisällölle_.

Saat lisätietoja näistä ongelmista sekä ohjeet niiden ymmärtämiseen ja lieventämiseen tutustumalla seuraaviin ohjeartikkeleihin:

- [Premium-kapasiteettien optimointi](../service-premium-capacity-optimize.md)
- [Premium-kapasiteettien valvonta sovelluksen avulla](../service-admin-premium-monitor-capacity.md)

## <a name="next-steps"></a>Seuraavat vaiheet

Saat lisätietoja tästä artikkelista tutustumalla seuraaviin resursseihin:

- [Mitä ovat sivutetut raportit Power BI Premiumissa?](../paginated-reports-report-builder-power-bi.md)
- [Sivutettujen raporttien tietojen nouto-ohjeet](report-paginated-data-retrieval.md)
- [Milloin sivutettuja raportteja kannattaa käyttää Power BI:ssä?](report-paginated-or-power-bi.md)
- [Sivutetut raportit Power BI:ssä: usein kysytyt kysymykset](../paginated-reports-faq.md)
- [Power BI Premiumin usein kysytyt kysymykset](../service-premium-faq.md)
- [RDL-siirtotyökalu](https://github.com/microsoft/RdlMigration)
- Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
- Onko sinulla ehdotuksia? [Kerro ideasi Power BI:n parantamiseksi](https://ideas.powerbi.com/)

Tarjolla on Power BI -kumppaneita, jotka voivat auttaa organisaatiotasi toteuttamaan siirtymisen onnistuneesti. Jos haluat ryhtyä yhteistyöhön Power BI -kumppanin kanssa, siirry [Power BI -kumppaniportaaliin](https://powerbi.microsoft.com/partners/).
