---
title: Power BI Yhdysvaltain valtionhallinnon asiakkaille – katsaus
description: Yhdysvaltain valtionhallinnon asiakkaat voivat lisätä Power BI Pro -tilauksen Microsoft 365 Government -palvelupakettiinsa. Lue tästä palvelun kuvauksesta, miten voit rekisteröityä ja tarkastella ominaisuuksien saatavuutta.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/07/2020
ms.author: kfollis
LocalizationGroup: Get started
ms.openlocfilehash: aeaaf0e1e8baa70b5159d908ce1e27bb937de372
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83344706"
---
# <a name="power-bi-for-us-government-customers"></a>Power BI Yhdysvaltain valtionhallinnon asiakkaille
Tämä artikkeli on tarkoitettu Yhdysvaltain valtionhallinnon asiakkaille, jotka ottavat Power BI:n käyttöön osana Office 365 Government -palvelupakettia. Government-palvelupaketit on suunniteltu sellaisten organisaatioiden ainutlaatuisiin tarpeisiin, joiden pitää olla yhteensopivia Yhdysvaltain valtionhallinnon vaatimusten ja suojausstandardien kanssa. Yhdysvaltain valtionhallinnon asiakkaille suunniteltu Power BI-palvelu eroaa Power BI -palvelun kaupallisesta versiosta. Nämä ominaisuuksien erot ja ominaisuudet kuvataan seuraavissa osissa.

## <a name="add-power-bi-to-your-office-365-government-plan"></a>Power BI:n lisääminen Office 365 Government -palvelupakettiin

Ennen kuin voit saada Yhdysvaltain valtionhallinnolle tarkoitetun Power BI -paketin ja määrittää käyttäjille käyttöoikeuksia, sinun on rekisteröidyttävä Office 365 Government -palvelupakettiin. Jos organisaatiollasi on jo Office 365 Government -palvelupaketti, siirry eteenpäin kohtaan [Osta Power BI Pro valtionhallinnon asiakkaille -tilaus](#buy-a-power-bi-pro-subscription-for-government-customers).

### <a name="enroll-in-an-office-365-government-plan"></a>Rekisteröityminen Office 365 Government -palvelupakettiin

Jos olet uusi asiakas, sinun on ennen Office 365 Government -palvelupakettiin rekisteröitymistä vahvistettava, että organisaatiosi täyttää kelpoisuusvaatimukset.  Aloita täyttämällä [Office 365 for Government -kelpoisuuden vahvistuslomake](https://www.microsoft.com/microsoft-365/government/eligibility-validation). Varmista, että valitset oikean palvelupaketin organisaatiollesi, perehtymällä [Office 365:n Yhdysvaltain valtionhallinnon palvelukuvauksiin](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government).

> [!NOTE]
> Jos olet jo ottanut käyttöön Power BI:n kaupallisessa ympäristössä ja haluat siirtää sen Yhdysvaltain valtionhallinnon pilveen, sinun on lisättävä uusi Power BI Pro -tilaus Office 365 Government -palvelupakettiisi. Replikoi sitten kaupalliset tiedot Yhdysvaltain valtionhallinnon Power BI -palveluun, poista kaupalliset käyttöoikeusmääritykset käyttäjätileiltä ja määritä sitten käyttäjätileille Power BI Pro Government -käyttöoikeudet.
>
>
## <a name="government-cloud-instances"></a>Valtionhallinnon pilviesiintymät
Office 365 järjestää eri ympäristöjä valtion virastoille vaihtelevien yhteensopivuusvaatimusten täyttämiseksi. Lisätietoja kustakin ympäristöstä on kohdassa:

* [Office 365 Government Community Cloud (GCC)](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc) on tarkoitettu liittovaltion, osavaltion ja paikallistason hallinnolle.

* [Office 365 Government Community Cloud High (GCC High)](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod) on tarkoitettu liittovaltion virastoille, puolustusteollisuudelle, ilmailuteollisuudelle ja muille organisaatioille, joilla on hallussaan valvottua luokittelematonta tietoa. Tämä ympäristö soveltuu kansallisen turvallisuuden organisaatioille ja yrityksille, joilla on hallussaan kansainvälisiin asekauppamääräyksiin (ITAR) liittyvää tietoa tai liittovaltion puolustuksen hankintamääräysliitteen (DFARS) edellytyksiä.

* [Office 365 DoD -ympäristö](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod) on suunniteltu yksinomaan Yhdysvaltain puolustusministeriön tarpeisiin. 

## <a name="connect-to-power-bi-for-us-government"></a>Yhteyden muodostaminen Yhdysvaltain valtionhallinnon Power BI:hin

Power BI:hin yhdistämisen URL-osoite on eri valtionhallinnon käyttäjille ja kaupallisille käyttäjille. Kirjaudu sisään Power BI:hin käyttämällä seuraavia URL-osoitteita:

| Kaupallinen versio  | GCC  | GCC High | DoD |
| --- | --- | --- | --- |
| [https://app.powerbi.com/](https://app.powerbi.com) |[https://app.powerbigov.us](https://app.powerbigov.us) | [https://app.high.powerbigov.us](https://app.high.powerbigov.us) | [https://app.mil.powerbigov.us](https://app.mil.powerbigov.us) |

Tilisi voidaan määrittää useampaan kuin yhteen pilvipalveluun. Jos tilisi on määritetty sillä tavalla, voit Power BI:hin kirjautuessasi valita, mihin pilveen luot yhteyden.

## <a name="buy-a-power-bi-pro-subscription-for-government-customers"></a>Osta Power BI Pro -tilaus valtionhallinnon asiakkaille

Kun olet ottanut käyttöön Office 365:n, voit lisätä Power BI Pro -tilauksen. Osta Power BI Pro Government -palvelu suorittamalla vaiheittaiset ohjeet kohdassa [Rekisteröi Yhdysvaltain julkishallinnon organisaatio](service-govus-signup.md). Osta riittävästi käyttöoikeuksia kaikille käyttäjille, joiden tarvitsee päästä käyttämään Power BI:tä, ja määritä sitten käyttöoikeudet yksittäisille käyttäjätileille.

> [!IMPORTANT]
> Power BI US Government ei ole saatavissa *ilmaisena* käyttöoikeutena. Kaikille käyttäjille on määritettävä *Pro*-käyttöoikeudet, jotta he saavat käyttää valtionhallinnon yhteisöpilveä. Jos käyttäjän tilille on määritetty ilmainen käyttöoikeus, hän saa käyttää ainoastaan kaupallisia pilvipalveluja ja hänelle tulee todennus- ja käyttöoikeusongelmia. Jos olet ostanut Power BI Premiumin, sinun ei tarvitse määrittää Pro-käyttöoikeuksia käytön mahdollistamiseksi.  Kuka tahansa organisaation käyttäjä voi käyttää hänen kanssaan jaettuja raportteja, kunhan raportit julkaistaan Premium-kapasiteettiin. Jos haluat tarkastella eri käyttöoikeustyyppien välisiä eroja, katso kohta [Power BI -palvelun ominaisuudet käyttöoikeustyypin mukaan](../fundamentals/service-features-license-type.md).
>

## <a name="connect-government-and-global-azure-cloud-services"></a>Valtionhallinnon ja yleisten Azure-pilvipalveluiden yhdistäminen

Azure jaetaan useiden pilvien kautta. Oletuksena voit ottaa käyttöön palomuurisäännöt avatessasi yhteyden pilvipalvelukohtaiseen esiintymään, mutta pilvien välinen verkostoituminen on erilaista.  Jotta voit kommunikoida julkisen pilven palveluiden ja valtionhallinnon yhteisön pilvipalvelujen välillä, sinun on määritettävä erityiset palomuurisäännöt. Jos esimerkiksi haluat SQL-tietokannan julkisen pilven esiintymiä valtionhallinnon pilvessä käyttöön otetusta Power BI:stä käsin, tarvitset palomuurisäännön SQL-tietokannassa. Määritä tietyt palomuurisäännöt SQL-tietokantaan, jotta Azure Government -pilveen voidaan muodostaa yhteys seuraavista palvelinkeskuksista:

* USGov Iowa
* USGov Virginia
* USGov Texas
* USGov Arizona

Julkisessa pilvipalvelussa IP-alueet ovat käytettävissä. Jos haluat käyttöösi Yhdysvaltain valtionhallinnon pilvipalvelujen IP-alueet, lataa [Azure-IP-alueet ja palvelutunnisteet – Yhdysvaltain valtionhallinnon pilvipalvelut](https://www.microsoft.com/download/details.aspx?id=57063) -tiedosto. 

Lisätietoja SQL-tietokantojen palomuurien määrittämisestä on kohdassa [IP-palomuurisääntöjen luominen ja hallitseminen](https://docs.microsoft.com/azure/sql-database/sql-database-firewall-configure#create-and-manage-ip-firewall-rules).

## <a name="power-bi-feature-availability"></a>Power BI -ominaisuuksien saatavuus

Jotta valtionhallinnon pilvipalveluasiakkaiden tarpeet saadaan täytettyä, valtionhallinnon palvelupakettien ja kaupallisten palvelupakettien välillä on eräitä eroja. Katso seuraavasta taulukosta, mitkä ominaisuudet ovat saatavana missäkin ympäristössä:

|Ominaisuus |   |GCC |GCC High |DoD|
|------|------|------|------|------|
|Hallinta|Ilmaiset käyttöoikeudet|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Rajoitusten määrittäminen tietojen tallennukselle|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Active Directory -ryhmien käyttäminen jakamiseen ja käytön hallintaan|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Valvonta Office 365:n suojauksen ja yhteensopivuuden hallintakeskuksen avulla|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Jakaminen ulkoisille käyttäjille|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Raporttien ja koontinäyttöjen käyttömittarit|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Azure B2B GCC:n ja kaupallisten pilvipalvelujen välillä|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|Raportin luominen|Koontinäyttöjen ja raporttien luominen ja tarkasteleminen|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Ajoitettu tietojen päivittäminen|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Päivitettävät työryhmän koontinäytöt|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Sivutetut raportit|Käytettävissä|Toteutussuunnitelmassa|Toteutussuunnitelmassa|
|  |Mallisovellukset|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|Tietoihin yhdistäminen|Tietojen ja raporttien tuominen Excelistä|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Tietojen tuominen CSV-tiedostoista|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Tietojen tuominen Power BI Desktop -tiedostoista|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Yhteydet CDS:ään|Käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Azure Data Lake Storage Gen2 -liitin|Käytettävissä|Ei käytettävissä|Ei käytettävissä|
|Tiedonhallinta|Tiedonhallinnan yhdyskäytävä|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Tietojen salaus Azure SQL -tietokannassa|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Tietojen salaus Power BI:n blob-objektisäilössä|Käytettävissä|Käytettävissä|Käytettävissä|
|Tuotteiden välinen integrointi|Upottaminen SharePoint Onlinessa Power BI -verkko-osan avulla|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Upottaminen SharePoint Onlinessa Embed-verkko-osan avulla|Käytettävissä|Käytettävissä|Käytettävissä|
|  |Tietovuot ja tekoälytoiminnot|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Power Automate -liitettävyys tietopohjaisille hälytyksille|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Power BI -välilehti Teamsissa|Käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Automaattinen koneoppiminen|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Azuren kognitiiviset palvelut|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|
|  |Azure-koneoppiminen|Ei käytettävissä|Ei käytettävissä|Ei käytettävissä|

## <a name="next-steps"></a>Seuraavat vaiheet

* [Rekisteröidy Yhdysvaltain valtionhallinnon Power BI:hin](service-govus-signup.md)
* [Microsoft Power Apps Yhdysvaltain valtionhallinnolle](https://docs.microsoft.com/power-platform/admin/powerapps-us-government)
* [Power Automate Yhdysvaltain valtionhallinnolle](https://docs.microsoft.com/power-automate/us-govt)
* <a href="https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government">Yhdysvaltain valtionhallinnon Power BI:n esittelyohjelma</a>
