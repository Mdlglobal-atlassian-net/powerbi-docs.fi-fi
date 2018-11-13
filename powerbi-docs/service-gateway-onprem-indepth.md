---
title: Paikallinen tietoyhdyskäytävä tarkemmin
description: Tässä artikkelissa tarkastellaan paikallista yhdyskäytävää tarkemmin. Artikkelissa kerrotaan, miten palvelu toimii Azure Active Directoryn ja paikallisen Active Directoryn kanssa Analysis Servicesiä käytettäessä.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 30ac2c0620607d680874e423c841c381fc273904
ms.sourcegitcommit: 5eb0f37f59b5fec15c0caecbbd1f8d688c7f0013
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/09/2018
ms.locfileid: "50101504"
---
# <a name="on-premises-data-gateway-in-depth"></a>Paikallinen tietoyhdyskäytävä tarkemmin
Organisaatiosi käyttäjät voivat käyttää paikallisia tietoja (joihin heillä on jo käyttöoikeus), mutta ennen kuin kyseiset käyttäjät voivat muodostaa yhteyden paikalliseen tietolähteeseen, paikallinen tietoyhdyskäytävä on asennettava ja määritettävä. Yhdyskäytävä helpottaa nopeaa ja turvallista taustaviestintää pilvipalvelussa olevalta käyttäjältä paikalliselle tietolähteelle ja takaisin pilvipalveluun.

Yhdyskäytävän asentaa ja määrittää yleensä järjestelmänvalvoja. Toimenpide voi vaatia erityistä tietämystä paikallisista palvelimista, ja joissakin tapauksissa tarvitaan myös palvelimen järjestelmänvalvojan oikeudet.

Tämä artikkeli ei sisällä vaiheittaisia ohjeita siitä, miten yhdyskäytävä asennetaan ja määritetään. Kyseiset tiedot ovat artikkelissa [Paikallinen tietoyhdyskäytävä](service-gateway-onprem.md). Tämän artikkelin tarkoitus on tarjota tarkempi kuva yhdyskäytävän toiminnasta. Artikkelissa käsitellään jonkin verran myös käyttäjänimiä, Azure Active Directoryn ja Analysis Servicesin suojausta sekä sitä, miten pilvipalvelu käyttää sisäänkirjautumisessa käytettyä sähköpostiosoitetta, yhdyskäytävää ja Active Directorya turvalliseen yhteyden muodostamiseen ja paikallisten tietojen kyselyyn.

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="sign-in-account"></a>Kirjautumistili
Käyttäjät kirjautuvat sisään joko työpaikan tai oppilaitoksen tilillä. Se on käyttäjän organisaatiotili. Jos olet tilannut Office 365 -tarjooman etkä ole antanut todellista työsähköpostiasi, tilisi voi näyttää tältä: nancy@contoso.onmicrosoft.com. Pilvipalvelun sisällä oleva tilisi on tallennettu-vuokraajaan Azure Active Directoryssa (AAD). Useimmissa tapauksissa Azure Active Directory -tilin täydellinen käyttäjätunnus vastaa sähköpostiosoitetta.

## <a name="authentication-to-on-premises-data-sources"></a>Todentaminen – paikalliset tietolähteet
Tallennettua tunnistetietoa käytetään yhteyden muodostamiseen yhdyskäytävästä paikallisiin tietolähteisiin, pois lukien Analysis Services. Yksittäisestä käyttäjästä riippumatta yhdyskäytävä käyttää tallennettua tunnistetietoa yhteyden muodostamiseen.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Todentaminen – reaaliaikainen Analysis Services -tietolähde
Aina, kun käyttäjä on vuorovaikutuksessa Analysis Servicesin kanssa, käytössä oleva käyttäjänimi välitetään yhdyskäytävään ja paikalliseen Analysis Services -palvelimeen. Analysis Servicesiin välitetään käyttäjätietona täydellinen käyttäjätunnus (UPN) eli yleensä pilvipalveluun kirjautumisessa käytetty sähköpostiosoite. Täydellinen käyttäjätunnus välitetään EffectiveUserName-yhteysominaisuudessa. Tämän sähköpostiosoitteen on vastattava paikallisen Active Directory -toimialueen määritettyä täydellistä käyttäjätunnusta. Täydellinen käyttäjätunnus on Active Directory -tilin ominaisuus. Windows-tilin on oltava käytössä Analysis Services -roolissa, jotta palvelinta voi käyttää. Kirjautuminen ei onnistu, jos Active Directorysta ei löydy vastaavuutta.

Analysis Services-voi myös tehdä suodatuksia tämän tilin perusteella. Suodatus voidaan tehdä joko roolipohjaisessa suojauksessa tai rivitason suojauksessa.

## <a name="role-based-security"></a>Roolipohjainen suojaus
Malleissa käytetään käyttäjärooleihin perustuvaa suojausta. Roolit määritetään tietyn malliprojektin luomisvaiheessa SQL Server Data Tools -liiketoimintatietotyökaluissa (SSDT-BI) tai mallin käyttöönoton jälkeen SQL Server Management Studion (SSMS) avulla. Rooleihin kuuluu jäseniä Windows käyttäjänimen tai Windows-ryhmän mukaan. Roolit määrittävät käyttäjän oikeudet suorittaa kyselyitä tai toimintoja mallissa. Useimmilla käyttäjillä on rooli, joka antaa lukuoikeudet. Muut roolit on tarkoitettu järjestelmänvalvojille, ja ne antavat oikeuden käsitellä kohteita sekä hallita tietokantafunktioita ja muita rooleja.

## <a name="row-level-security"></a>Rivitason suojaus
Rivitason suojaus tarkoittaa nimenomaan Analysis Services -palvelun rivitason suojausta. Mallit voivat tarjota dynaamista rivitason suojausta. Taulukkomalleihin ei vaadita dynaamista suojausta – toisin kuin rooleja, joita käyttäjille on määritettävä vähintään yksi. Ylätasolla dynaaminen suojaus määrittää käyttäjän tietojenlukuoikeuden suoraan tietyn taulukon tietylle riville. Kuten roolitkin, dynaaminen rivitason suojaus perustuu käyttäjän Windows-käyttäjänimeen.

Käyttäjän mahdollisuus suorittaa kyselyjä ja tarkastella mallitietoja määräytyy ensiksi heidän Windows-käyttäjätiliinsä määritettyjen roolien perusteella ja toiseksi mahdollisen dynaamisen rivitason suojauksen perusteella.

Tässä artikkelissa ei käsitellä roolipohjaisen ja dynaamisen rivitason suojauksen ottamista käyttöön malleissa.  Lisätietoja on MSDN:n artikkeleissa, jotka käsittelevät [rooleja (SSAS – taulukkomuoto)](https://msdn.microsoft.com/library/hh213165.aspx) ja [käyttöoikeusrooleja (Analysis Services – monidimensionaaliset tiedot)](https://msdn.microsoft.com/library/ms174840.aspx). Jos haluat ymmärtää taulukkomallin suojausta mahdollisimman perusteellisesti, lataa ja lue [Taulukkomuotoisten liiketoimintatietojen semanttisen mallin suojaamista käsittelevä tekninen raportti](https://msdn.microsoft.com/library/jj127437.aspx).

## <a name="what-about-azure-active-directory"></a>Entä Azure Active Directory?
Microsoft-pilvipalveluissa käyttäjät todennetaan [Azure Active Directoryn](/azure/active-directory/fundamentals/active-directory-whatis) avulla. Azure Active Directory on vuokraaja, joka sisältää käyttäjänimet ja käyttöoikeusryhmät. Yleensä kirjautumisessa käytetty sähköpostiosoite on sama kuin tilin täydellinen käyttäjätunnus.

Mikä on käyttäjän oman paikallisen Active Directoryn rooli?

Jotta Analysis Services voi selvittää, onko siihen yhteyden muodostavalla käyttäjällä roolinsa perusteella oikeus lukea tietoja, palvelimen on muunnettava käytössä oleva käyttäjänimi, joka välitetään AAD:stä yhdyskäytävään ja Analysis Services -palvelimeen. Analysis Services -palvelin välittää käytössä olevan käyttäjänimen Windows Active Directoryn toimialueen ohjauskoneeseen (DC). Active Directoryn toimialueen ohjauskone vahvistaa, että käytössä oleva käyttäjänimi on kelvollinen täydellinen käyttäjätunnus paikallisella tilillä, ja palauttaa kyseisen käyttäjän Windows-käyttäjänimen takaisin Analysis Services -palvelimeen.

EffectiveUserName-ominaisuutta ei voi käyttää sellaisessa Analysis Services -palvelimessa, jota ei ole liitetty toimialueelle. Analysis Services -palvelimen on oltava liitetty toimialueelle kirjautumisvirheiden välttämiseksi.

## <a name="how-do-i-tell-what-my-upn-is"></a>Mistä tiedän, mikä täydellinen käyttäjätunnukseni on?
Et välttämättä tiedä täydellistä käyttäjätunnustasi etkä ehkä ole toimialueen järjestelmänvalvoja. Voit selvittää tilisi täydellisen käyttäjätunnuksen työasemaltasi seuraavan komennon avulla.

    whoami /upn

Tulos näyttää samalta kuin sähköpostiosoite, mutta kyseessä on paikallisen toimialuetilisi täydellinen käyttäjätunnus. Jos käytät Analysis Services -tietolähdettä reaaliaikaisiin yhteyksiin, tämän on vastattava yhdyskäytävästä EffectiveUserNamelle lähetettyä versiota.

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Käyttäjänimien yhdistäminen Analysis Services -tietolähteitä varten
Power BI mahdollistaa käyttäjänimien yhdistämisen Analysis Services -tietolähteitä varten. Voit määrittää sääntöjä, joiden avulla Power BI:n kautta kirjautunut käyttäjänimi yhdistetään Analysis Services -yhteydellä EffectiveUserNamelle välitettyyn nimeen. Käyttäjänimien yhdistämistoiminto on kätevä tapa kiertää ongelma, jos Azure Active Directory -käyttäjänimesi ei vastaa paikallisen Active Directoryn täydellistä käyttäjätunnusta. Jos sähköpostiosoite on esimerkiksi nancy@contoso.onmicrsoft.com, sen voi yhdistää käyttäjänimeen nancy@contoso.com, ja tämä arvo välitetään yhdyskäytävään. Lue lisätietoja [käyttäjänimien yhdistämisestä](service-gateway-enterprise-manage-ssas.md#map-user-names).

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Paikallisen Active Directoryn synkronoiminen Azure Active Directoryn kanssa
Paikallisten Active Directory -tilien on hyvä vastata Azure Active Directorya, jos aiot käyttää reaaliaikaisia Analysis Services -yhteyksiä. Eri tilien täydellisten käyttäjätunnusten on nimittäin vastattava toisiaan.

Pilvipalvelut tuntevat vain Azure Active Directoryn tilit. Vaikka olisit lisännyt tilin paikalliseen Active Directoryyn, sitä ei voi käyttää, jos sitä ei ole Azure Active Directoryssa. Voit yhdistää paikallisen Active Directoryn tilit Azure Active Directoryyn eri tavoin.

1. Voit lisätä tilejä Azure Active Directoryyn manuaalisesti.
   
   Voit luoda tilin Azure-portaalissa tai Office 365 -hallintaportaalissa, ja tilin nimi vastaa paikallisen Active Directoryn tilin täydellistä käyttäjätunnusta.
2. Voit synkronoida paikalliset tilit Azure Active Directory -vuokraajan kanssa [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-sync-whatis) -työkalun avulla.
   
   Azure AD Connect -työkalulla voidaan synkronoida hakemistot ja määrittää todentaminen, mukaan lukien salasanan hajautuksen synkronointi, läpivientitodentaminen ja liittoutuminen. Jos et ole vuokraajan järjestelmänvalvoja tai paikallisen toimialueen järjestelmänvalvoja, sinun on pyydettävä IT-järjestelmänvalvojaasi tekemään määritykset.

Azure AD Connectin käyttäminen varmistaa, että AAD:n ja paikallisen Active Directoryn täydelliset käyttäjätunnukset vastaavat toisiaan.

> [!NOTE]
> Tilien synkronointi Azure AD Connect -työkalun avulla luo uusia tilejä AAD-vuokraajaan.
> 
> 

## <a name="now-this-is-where-the-gateway-comes-in"></a>Tässä vaiheessa yhdyskäytävä tulee mukaan kuvaan.
Yhdyskäytävä toimii siltana pilvipalvelun ja paikallisen palvelimen välillä. Pilvipalvelun ja yhdyskäytävän välinen tiedonsiirto suojataan [Azuren palveluväylän](/azure/service-bus-messaging/service-bus-messaging-overview) avulla. Palveluväylä luo suojatun kanavan pilven ja paikallisen palvelimen välille yhdyskäytävän lähtevän yhteyden kautta.  Saapuvia yhteyksiä, jotka olisi avattava paikallisessa palomuurissa, ei ole.

Jos sinulla on Analysis Services -tietolähde, sinun on asennettava yhdyskäytävä sellaisessa tietokoneessa, joka on liitetty samaan toimialuepuuryhmään tai toimialueeseen kuin Analysis Services -palvelin.

Mitä lähempänä yhdyskäytävä on palvelinta, sitä nopeampi yhteys on. Yhdyskäytävän ja tietolähteen sijoittaminen samalle palvelimelle on paras tapa välttää verkkoviive yhdyskäytävän ja palvelimen välillä.

## <a name="what-to-do-next"></a>Mitä seuraavaksi?
Kun yhdyskäytävä on asennettu, sinun on luotava sille tietolähteet. Voit lisätä tietolähteitä **Yhdyskäytävien hallinta** -näytössä. Saat lisätietoja tietolähteiden hallintaa käsittelevistä artikkeleista.

[Tietolähteen hallinta – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Tietolähteen hallinta – SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Tietolähteen hallinta – SQL Server](service-gateway-enterprise-manage-sql.md)  
[Tietolähteen hallinta – Oracle](service-gateway-onprem-manage-oracle.md)  
[Tietolähteen hallinta – tuonti ja ajoitettu päivitys](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>Mahdolliset ongelmakohdat
Joskus yhdyskäytävän asentaminen epäonnistuu. Voi myös vaikuttaa siltä, että yhdyskäytävän asennus onnistui, mutta sen käyttäminen palvelussa ei silti onnistu. Monissa tapauksissa kyse on yksinkertaisesta asiasta, kuten niiden tunnistetietojen salasanasta, joiden avulla yhdyskäytävä kirjautuu tietolähteeseen.

Ongelmat voivat myös johtua kirjautumisessa käytettyjen sähköpostiosoitteiden tyypistä tai siitä, että Analysis Services ei voi selvittää käytössä olevaa käyttäjänimeä. Joskus ongelmia voi aiheuttaa se, että käytössä on useita toimialueita, joiden välillä on luottamus, ja yhdyskäytävä ja Analysis Services sijaitsevat eri toimialueilla.

Sen sijaan, että käsittelisimme yhdyskäytävän ongelmien vianmääritystä tässä, olemme koonneet vianmääritysohjeita artikkeliin nimeltä [Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md). Toivottavasti kaikki sujuu ongelmitta. Jos ongelmia kuitenkin ilmenee, toimintaperiaatteiden ymmärtämisen ja vianmääritysartikkelin pitäisi auttaa.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

## <a name="next-steps"></a>Seuraavat vaiheet

[Paikallisen tietoyhdyskäytävän vianmääritys](service-gateway-onprem-tshoot.md)  
[Azuren palveluväylä](/azure/service-bus-messaging/service-bus-messaging-overview/)  
[Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-sync-whatis/)  

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)

