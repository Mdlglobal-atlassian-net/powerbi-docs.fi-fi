---
title: Power BI:n suuren käytettävyyden, vikasietoisuuden ja järjestelmäpalautuksen usein kysytyt kysymykset
description: Lue lisätietoja siitä, miten Power BI -palvelu varmistaa suuren käytettävyyden ja liiketoiminnan jatkuvuuden sekä järjestelmäpalautuksen käyttäjilleen.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/20/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 3dd50d4f57b3146135cde5e91062ed3b2a0eecc1
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "77527334"
---
# <a name="power-bi-high-availability-failover-and-disaster-recovery-faq"></a>Power BI:n suuren käytettävyyden, vikasietoisuuden ja järjestelmäpalautuksen usein kysytyt kysymykset

Tässä artikkelissa kerrotaan, miten Power BI -palvelu varmistaa suuren käytettävyyden ja liiketoiminnan jatkuvuuden sekä järjestelmäpalautuksen käyttäjilleen. Luettuasi tämän artikkelin ymmärrät, miten suuri käytettävyys saavutetaan, missä olosuhteissa Power BI hyödyntää vikasietoisuutta ja mitä voit odottaa palvelulta vikasietotilanteissa.

## <a name="what-does-high-availability-mean-for-power-bi"></a>Mitä suuri käytettävyys tarkoittaa Power BI:ssä?

Power BI on täysin hallittu palveluna tarjottava ohjelmisto eli SaaS-ohjelmisto.  Microsoft on suunnitellut sen siten ja ylläpitää sitä siten, että se on vikasietoinen infrastruktuurivioille, minkä ansiosta käyttäjien raportit ovat aina heidän käytettävissään.  Palvelulle annetaan palvelutasosopimuksessa [99,9 prosentin käytettävyysaikatakuu](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37).

## <a name="what-is-a-power-bi-failover"></a>Mitä Power BI:n vikasietoisuus tarkoittaa?

Power BI:n kustakin komponentista ylläpidetään useita esiintymiä Azuren eri palvelinkeskuksissa (eri alueilla) liiketoiminnan jatkuvuuden takaamiseksi. Jos ilmenee vika tai ongelma, jonka vuoksi Power BI ei ole käytettävissä tietyllä alueella tai tietyssä palvelinkeskuksessa, Power BI siirtää vikasietoisesti kaikki komponentit alueelle ja palvelinkeskukseen, jossa on vastaava varmuuskopioesiintymä. Vikasietoisuus palauttaa Power BI -palvelun toimintakuntoon uudella alueella (yleensä tämä on maantieteellisesti samalla alueella, kuten [Microsoft Trust Centerissä](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location) kerrotaan).

Vikasietoinen Power BI -palvelun esiintymä tukee vain _lukutoimintoja_. Tämä tarkoittaa sitä, että seuraavia toimintoja ei tueta vikasietoisuuden aikana: päivitykset, raporttien julkaisutoiminnot, koontinäyttöjen ja raporttien muokkaukset sekä muut toiminnot, jotka edellyttävät muutoksia Power BI -metatietoihin (esimerkiksi kommentin lisääminen raporttiin).  Lukutoiminnot, esimerkiksi koontinäyttöjen ja raporttien näyttäminen (jotka eivät perustu paikallisten tietolähteiden DirectQuery- ja Live Connect -yhteyksiin), toimivat normaalisti.

## <a name="how-are-backup-instances-kept-in-sync-with-my-data"></a>Miten varmuuskopioesiintymät pidetään synkronoituina tietojeni kanssa?

Kaikki Power BI -palvelun komponentit synkronoidaan varmuuskopioesiintymiensä kanssa säännöllisesti. Pyrimme 15 minuutin synkronointiväliin mille tahansa Power BI:hin ladatulle sisällölle tai siinä muokatulle sisällölle. Vikasietoisuustilanteessa Power BI käyttää [Azure-tallennuksen maantieteellisesti vikasietoista replikointia](/azure/storage/common/storage-redundancy-grs) ja [Azure SQL:n maantieteellisesti vikasietoista replikointia](/azure/sql-database/sql-database-active-geo-replication), joiden avulla se takaa sen, että varmuuskopioesiintymät ovat olemassa muilla alueilla. Tämän ansiosta niitä voidaan käyttää vikasietoisuustilanteissa.

## <a name="where-are-the-failover-clusters-located"></a>Missä vikasietoklusterit sijaitsevat?

Varmuuskopioesiintymät sijaitsevat samalla maantieteellisellä alueella, jonka organisaatiosi valitsi rekisteröityessään Power BI:hin, ellei muuta [Microsoft Trust Centerissä](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location) määritetä. Maantieteellinen alue voi koostua useista ala-alueista. Lisäksi Microsoft voi replikoida tietoja mille tahansa maantieteellisen alueen ala-alueelle tietojen vikasietoisuuden takaamiseksi. Microsoft ei replikoi tai siirrä asiakkaiden tietoja heidän valitsemiensa maantieteellisten alueiden ulkopuolelle. [Microsoft Trust Centerissä](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location) voit tutustua Power BI:n maantieteelliseen alueisiin ja niiden ala-alueisiin.

## <a name="how-does-microsoft-decide-to-failover"></a>Miten Microsoft päättää vikasietoisuudesta?

Käytämme kahta eri järjestelmää, jotka osoittavat, milloin vikasietoisuus voi olla tarpeen:

- Ulkoiset ja sisäiset valvontaratkaisumme saattavat ilmoittaa, että käytettävyys ei ole riittävä tai että toiminta ei onnistu oikeaoppisesti. Tällaiset ilmoitukset saattavat johtua havaituista vioista Power BI:n komponenteissa yhdessä palvelussa tai useissa palveluissa, joita Power BI tarvitsee tietyllä alueella.
- Microsoft Azuren keskitetty toimintatiimi saattaa ilmoittaa merkittävästä toimintahäiriöstä alueella.

Kummassakin tapauksessa Power BI:n johtoryhmä tekee päätöksen vikasietoisuudesta: päätöstä ei siis tehdä automaattisesti. Kun päätös on tehty, itse vikasietoisuusprosessi toteutetaan automaattisesti.

## <a name="how-do-i-know-power-bi-is-now-in-failover-mode"></a>Mistä tiedän, jos Power BI on vikasietotilassa?

Power BI -tukisivulla ([https://powerbi.microsoft.com/support/](https://powerbi.microsoft.com/support/)) julkaistaan ilmoitus. Ilmoituksessa kerrotaan tärkeimmät toiminnot, jotka eivät ole käytettävissä vikasietoisuuden aikana (esimerkiksi julkaisu, päivitys, koontinäytön luominen ja monistaminen sekä käyttöoikeuksien muutokset).

## <a name="how-long-does-it-take-power-bi-to-fail-over"></a>Kuinka kauan Power BI:n vikasietoisuuden toteutus kestää?

Kestää noin 15 minuuttia, että Power BI toimii jälleen sen jälkeen, kun on todettu, että vikasieto vaaditaan. Aika, joka tarvitaan vikasietotarpeen tunnistamiseen, vaihtelee toimimattoman skenaarion mukaan. 

Kun vikasieto suoritetaan, Power BI käyttää Azure-tallennuksen maantieteellistä replikointia vikasiedon suorittamiseksi. Tällaisten replikointien palautuspiste on yleensä 15 minuuttia, mutta [Azure-tallennus ei takaa tätä aikaa](https://docs.microsoft.com/azure/storage/common/storage-redundancy) palvelutasosopimuksen yhteydessä, joten Power BI ei myöskään pysty takaamaan ajanjaksoa. 


## <a name="when-does-my-power-bi-instance-return-to-the-original-region"></a>Milloin Power BI -esiintymäni palaa alkuperäiselle alueelle?

Power BI -palvelun esiintymät palaavat alkuperäisille alueilleen, kun vikasietoisuuden aiheuttanut vika on saatu korjattua. Tarkista tarkemmat tiedot Power BI -tukisivulta: Kun ongelma on ratkaistu, Power BI -tiimi poistaa ilmoituksen vikasietoisuudesta. Tässä vaiheessa toiminnan pitäisi jatkua normaalisti.

## <a name="am-i-responsible-for-the-availability-of-my-power-bi-solution"></a>Olenko itse vastuussa Power BI -ratkaisuni käytettävyydestä?

Jos organisaatiosi käyttämään Power BI -ratkaisuun liittyy jokin seuraavista elementeistä, sinun täytyy ryhtyä tiettyihin toimiin ratkaisun suuren käytettävyyden takaamiseksi:

- Jos organisaatiosi käyttää Power BI Premiumia, sinun täytyy taata, että Premium-kapasiteetti on tarpeeksi suuri käyttöönottosi kuormitukselle.  [Power BI Premiumin suunnittelun ja käyttöönoton raportista](https://aka.ms/Premium-Capacity-Planning-Deployment) sekä [Power BI Premium Capacity Metrics -sovelluksesta](service-admin-premium-monitor-capacity.md) voi olla apua tämän vaatimuksen suunnittelussa ja täyttämisessä. Lisäämme Metrics-sovellukseen ja Power BI -hallintaportaaliin säännöllisesti uusia toimintoja, joista on apua.
- Jos organisaatiosi käyttää paikallisia tietolähteitä paikallisen tietoyhdyskäytävän avulla, sinun täytyy määrittää yhdyskäytävä [tämän artikkelin ohjeiden](/data-integration/gateway/service-gateway-high-availability-clusters) mukaisesti tukemaan suurta käytettävyyttä. Noudata näitä ohjeita riippumatta siitä, oletko päivittämässä raportteja tuontitilassa tai käyttämässä tietoja tai tietomalleja DirectQueryn tai Live Connectin avulla.

## <a name="will-gateways-function-when-in-failover-mode"></a>Toimivatko yhdyskäytävät vikasietotilassa?

Ei. Paikallisten tietolähteiden tiedot (Direct Queryyn ja Live Connectiin perustuvat raportit ja koontinäytöt) eivät toimi vikasietoisuuden aikana. Yhdyskäytävämääritys ei kuitenkaan muutu: kun Power BI -esiintymä palaa alkuperäiseen tilaansa, yhdyskäytävien normaali toiminta jatkuu.
