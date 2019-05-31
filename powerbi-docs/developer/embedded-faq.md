---
title: Usein kysyttyjä kysymyksiä – Power BI Embedded
description: Selaa Power BI Embeddediä koskevien usein kysyttyjen kysymysten ja vastausten luetteloa.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 1bdc31d550573b926d45776307b8fcade95f0dc0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222165"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Usein kysyttyjä kysymyksiä – Power BI Embedded

* Jos sinulla on muita kysymyksiä, [voit esittää niitä Power BI -yhteisössä](http://community.powerbi.com/).
* Eikö ongelma ratkennut? Vieraile [Power BI -tukisivulla](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Yleiset

### <a name="what-is-power-bi-embedded"></a>Mikä Power BI Embedded on?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md) avulla sovelluskehittäjät voivat upottaa näyttäviä, täysin interaktiivisia raportteja heidän ei tarvitse luoda omia tietojen visualisointien ja ohjausobjektien alusta alkaen.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Mikä on Power BI Embeddedin kohderyhmä?

Sovelluskehittäjien ja, eli ohjelmistotoimittajat (ISV) koodaamisen sovelluksia.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Miten Power BI Embedded poikkeaa Power BI -palvelusta?

Power BI on ohjelmisto palveluna -tyyppinen analytiikkaratkaisu, joka mahdollistaa organisaatioille kriittisimpien liiketoimintatietojen tarkastelun yhdessä näkymässä.

Microsoft kehittänyt Power BI Embedded riippumattomille ohjelmistokehittäjille, jota haluat upottaa visualisointien sovelluksensa helpottavia niiden analyyttisten. Tämä spares Ohjelmistotoimittajille tarvitse luoda omia analyysitoimintojen ratkaisun itse. [Upotetun analytiikan](embedding.md) avulla käyttäjät voivat käyttää yritystietoja ja suorittaa kyselyitä sen luoda sovelluksessa merkityksellisiä tietoja.


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Mikä on Power BI Premiumin ja Power BI Embeddedin välinen ero?

Power BI Premium on optimoitu yrityksille, jotka haluavat täydellisen BI-ratkaisun, joka tarjoaa yhdessä näkymässä organisaation, kumppanien, asiakkaiden ja toimittajien tietojen tarkastelun. Power BI Premium auttaa organisaatiotasi tekemään päätöksiä. Power BI Premium on SaaS-tuote, jonka avulla käyttäjät voivat käyttää sisältöä mobiilisovelluksissa sisäisesti kehitettyjen sovellusten kautta tai Power BI-portaalissa.

Power BI Embedded on ISV-kumppaneille, jotka haluavat upottaa visualisointien sovellukset. Power BI Embedded auttaa asiakkaitasi tekemään päätöksiä, sillä se on suunnattu sovelluskehittäjille, joiden sovelluksia käyttävät asiakkaat voivat käyttää Power BI Embedded -kapasiteettiin tallennettua sisältöä organisaation sisällä tai ulkopuolella. Et voi jakaa Power BI Embedded-kapasiteetin sisältöä yhden napsautuksen verkkoon tai yhden napsautuksen julkaisulla SharePointiin.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Mikä on Microsoftin suositus sen suhteen, milloin asiakkaan kannattaa ostaa Power BI Premium ja milloin Power BI Embedded?

Microsoft suosittelee, että yritykset ostaisivat Power BI Premium, yritystason, Omatoiminen BI-pilviratkaisu. Suosittelemme ISV-ohjelmistotoimittajat Power BI Embedded sen pilvipohjaisia upotettuja analyysitoimintoja varten. Asiakas ei kuitenkaan ole ostettava tuote-rajoituksen.

Saatat joissakin tapauksissa, joissa (tavallisesti suuri) ISV, lisäksi sovelluksen upottamista haluaa käyttää P-Varastointiyksikköä saadakseen organisaatiolleen esimääritetyn Power BI-palvelun organisaatiossaan. Jotkin yritykset voivat päättää käyttää A-varastointiyksikköjä Azuressa, jos niitä kiinnostaa vain yrityssovellusten kehittäminen ja analyysitoimintojen upottaminen näihin sovelluksiin esimääritetyn Power BI -palvelun käytön sijaan.

### <a name="how-many-embed-tokens-can-i-create"></a>Kuinka monta upotettavaa tunnusta voit luoda?

Upota PRO-käyttöoikeudella upotettavat tunnukset on tarkoitettu vain kehitystestaukseen, joten Power BI-päätili tai [palveluobjektia](embed-service-principal.md) voivat ainoastaan luoda tunnuksia rajoitetun määrän. Jos haluat upottaa hyötykäyttöympäristössä, [osta kapasiteettia](#technical). Ei ole rajoitettu upotettavien tunnuksien kun ostat kapasiteettia. Siirry [Käytettävissä olevat ominaisuudet](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) -kohtaan tarkistaaksesi käyttöarvon, joka ilmaisee nykyisen upotetun käytön prosenttilukuna.

## <a name="technical"></a>Tekniset

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Mikä on Azuren A-varastointiyksiköiden ja Office 365:n EM-varastointiyksiköiden välinen ero?

PowerBI.com on yritys ohjelmisto-palveluun (SaaS)-ratkaisuna useita toimintoja, kuten sosiaalisen yhteistyön ja sähköpostitilauksen muita ominaisuuksia. PowerBI.com avulla hallita niiden upotettujen analyysitoimintojen ratkaisun sisällön ja vuokraaja-asetusten Ohjelmistotoimittajille.

Power BI Embedded on ympäristössä kuin palvelusta (PaaS) joukko API-kehittäjät avulla voit luoda upotetun analytiikkaratkaisun.

Tässä on osittainen luettelo eroja.

| Ominaisuus | Power BI Embedded | Power BI Premium -kapasiteetti | Power BI Premium -kapasiteetti |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A-varastointiyksiköt) | (EM-varastointiyksiköt) | (P-varastointiyksiköt) |
| Upotusartefaktit Power BI -sovelluksen työtilasta | Azure-kapasiteetti | Office 365 -kapasiteetti | Office 365 -kapasiteetti |
| Power BI -raporttien käyttäminen Embedded-sovelluksessa | Kyllä | Kyllä | Kyllä |
| Power BI -raporttien käyttäminen SharePointissa | Ei | Kyllä | Kyllä |
| Power BI -raporttien käyttäminen Dynamicsissa | Ei | Kyllä | Kyllä |
| Power BI -raporttien käyttäminen Teamsissa (ei sisällä mobiilisovellusta) | Ei | Kyllä | Kyllä |
| Sisällön käyttäminen ilmaisella Power BI -käyttöoikeudella Powerbi.comissa ja Power BI -mobiilisovelluksessa | Ei | Ei | Kyllä |
| Sisällön käyttäminen ilmaisella Power BI -käyttöoikeudella upotettuna MS Office -sovelluksiin | Ei | Kyllä | Kyllä |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI tarjoaa nyt kolme varastointiyksikköä upottamiseen: A-varastointiyksiköt, EM-varastointiyksiköt ja P-varastointiyksiköt. Mikä niistä minun tulisi ostaa omaa skenaariotani varten?

|  |A-varastointiyksikkö (Power BI Embedded)  |EM-varastointiyksikkö (Power BI Premium)  |P-varastointiyksikkö (Power BI Premium)  |
|---------|---------|---------|---------|
|Ostaminen  |Azure-portaali |Office |Office |
|Käyttötapaukset | Sisällön upottaminen omaan sovellukseen | <li> Sisällön upottaminen omaan sovellukseen <br><br><br> <li> Sisällön upottaminen MS Office -sovelluksiin: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (ei sisällä mobiilisovellusta)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> Sisällön upottaminen omaan sovellukseen <br><br><br> <li> Sisällön upottaminen MS Office -sovelluksiin: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (ei sisällä mobiilisovellusta)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br><br> <li> Sisällön jakaminen Power BI -käyttäjien kanssa [Power BI -palvelun](https://powerbi.microsoft.com/) kautta  |
|Laskutus |Tunneittain |Kuukausittain |Kuukausittain |
|Sitoutuminen  |Ei sitoutumista |Vuosittain  |Kuukausittain/vuosittain |
|Erot |Täysi joustavuus – skaalaus ylös/alas, resurssien keskeytys/jatkaminen Azure-portaalissa tai ohjelmointirajapinnan kautta  |Voit käyttää sisällön upottamiseen SharePoint Onlinessa ja Microsoft Teamsissa (jättää pois mobiilisovelluksen) |Yhdistää sovelluksiin upottamisen ja Power BI -palvelun käytön samassa kapasiteetissa |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Mitkä ovat ennakkoedellytykset PBIE-kapasiteetin luomiseksi Azuressa?

* Kirjaudu sisään organisaation hakemistoon (Microsoft-tilejä ei tueta).
* Sinun on oltava Power BI-vuokraaja, eli vähintään yhden käyttäjän hakemistossasi on täytynyt rekisteröityä Power BI. 
* Sinulla täytyy olla Azure-tilaus organisaatiosi hakemistossa.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Miten voin valvoa Power BI Embedded -kapasiteetin käyttöä?

* Käyttämällä [Power BI -hallintaportaalia](../service-admin-portal.md#power-bi-embedded).

* Lataamalla [mittausarvosovelluksen](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) Power BI:ssä.

* Käyttämällä [Azuren diagnostiikan kirjausta](azure-pbie-diag-logs.md).

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>Skaalautuuko skaalata automaattisesti sopeutua app-kulutus?

Ei ole automaattinen skaalattavissa, kaikki Ohjelmointirajapinnat ovat milloin tahansa.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>Miksi kapasiteetin luominen/skaalaaminen/jatkaminen aiheuttaa sen, että kapasiteetti siirtyy keskeytettyyn tilaan?

Kapasiteetin valmistelu (asteikon tai Jatka/luoda) voi epäonnistua. Nouda tiedot-Ohjelmointirajapinnan avulla voit tarkistaa kapasiteetin ProvisioningState: [Kapasiteetit – Nouda tiedot](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>Voinko luoda Power BI Embedded -kapasiteetteja vain tietyllä alueella?

[Multi-Geo (esikatselu)](embedded-multi-geo.md) -toiminnon avulla voit ostaa [Power BI Embedded -kapasiteetteja](azure-pbie-create-capacity.md) myös muualla kuin Power BI -kotivuokraajan sijainnissa

### <a name="how-can-i-find-my-pbi-tenant-region"></a>Miten voin selvittää Omat PBI alueellasi?

Voit käyttää PBI-portaalin PBI-vuokraajan alueen löytämiseksi.

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > Tietoja Power BI:stä

![Tietoja Power BI:stä](media/embedded-faq/about-01.png)
![Vuokraajan alue](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>Mitä (Pilvipalveluntarjoaja-tyyppi)-kanavaa tukee?

* Voit luoda PBIE:n vuokraajalle CSP-tilaustyypillä
* Kumppanitili voi kirjautua sisään asiakkaan vuokraajaan ja hankkia PBIE:n asiakkaan vuokraajalle. Tällöin asiakkaan vuokraajan käyttäjälle on määritettävä Power BI -kapasiteetin järjestelmänvalvojan oikeudet.

### <a name="why-do-i-get-an-unsupported-account-message"></a>Miksi saan tukematonta tiliä koskevan viestin?

Power BI edellyttää kirjautumista sisään organisaation tilillä. Yrität rekisteröityä Power BI-käyttäen Microsoft-tiliä ei tueta.

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>API-liittymät avulla voit luoda ja hallita Azure-kapasiteetit

Kyllä, on PowerShellin cmdlet-komennot ja Azure Resource Manager-REST-ohjelmointirajapinnan avulla voit luoda ja hallita PBIE resursseja.

* [REST-Ohjelmointirajapinnat](https://docs.microsoft.com/rest/api/power-bi-embedded/)
* [PowerShellin cmdlet-komennot](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>Mikä on PBI Embeddedin varatun kapasiteetin rooli PBI Embedded -ratkaisussa?

Jos haluat [Vie ratkaisusi tuotantoon](embed-sample-for-customers.md#move-to-production), sinun on määritettävä sovelluksesi käyttää Power BI-sisällön (sovelluksen työtila) Power BI Embedded (A SKU) kapasiteettiin.

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>Mitä Azure-alueet on PBI Embedded käytettävissä?

[PAM](https://ecosystemmanager.azurewebsites.net/home) (EcoManager) – kysy asiaa tuotteen saatavuudesta vastaavalta esimieheltä

Saatavilla olevat alueet (16 – samat alueet kuin Power BI)

* Yhdysvallat (6) – Itä-Yhdysvallat, Itä-Yhdysvallat 2, Yhdysvaltojen pohjoinen keskiosa, Yhdysvaltojen eteläinen keskiosa, Länsi-Yhdysvallat, Länsi-Yhdysvallat 2
* Eurooppa (2) – Pohjois-Eurooppa, Länsi-Eurooppa
* Tyynenmeren Aasia (2) – Kaakkois-Aasia, Itä-Aasia
* Brasilia (1) – Brasilia, etelä
* Japani (1) – Japani, itä
* Australia (1) – Kaakkois-Australia
* Intia (1) – Länsi-Intia
* Kanada (1) – Kanada, keskinen
* Yhdistynyt kuningaskunta (1) – Yhdistyneen kuningaskunta, eteläinen

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>Mikä on Power BI Embedded käyttäjän todentaminen mallin?

Power BI Embedded edelleen käyttää Azure AD: N pääkäyttäjän (nimetty Power BI Pro-käyttöoikeus käyttäjä) todennukseen tai kanssa [palveluobjektia](embed-service-principal.md) todentamisessa sisällä Power BI-sovellus.  

 ISV voidaan ottaa käyttöön omia todennus- ja heidän.

Voit käyttää olemassa olevaa hakemistoa, jos sinulla jo on Azure AD-vuokraaja. Voit myös luoda uuden Azure AD-vuokraajan upotetun sovelluksen sisällön suojaamista varten.

Voit hankkia AAD-tunnuksen jollain [Azure Active Directory -todennuskirjastolla](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries). Asiakaskirjastot ovat saatavilla useille alustoille.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>Oma sovellus käyttää jo AAD:tä käyttäjien todentamiseen. Miten voimme käyttää tätä identiteettiä, kun todennamme Power BI: hin ”Käyttäjä omistaa tiedot” -skenaariossa?

Se on vakio OAuth--puolestasi--työnkulun (<https://docs.microsoft.com/azure/active-directory/develop/web-api>). Sinun on määritettävä sovellus edellyttää Power BI-palvelun (pakollinen alueet) käyttöoikeudet. Kun sinulla on käyttäjän tunnus sovelluksen, voit yksinkertaisesti-kutsu käyttäen käyttäjän ADAL API-AcquireTokenAsync tunnuksen ja määrittää Power BI-resurssin URL-Osoitteen Resurssitunnus:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>Mitä objektin tunnus on Objektitunnus?

*Objektitunnus* on rekisteröity sovelluksen pääikkunassa sovelluksen Objektitunnus.

Objektin tunnus löytyvät *hallitun sovelluksen paikallisen hakemiston > ominaisuudet* osa on sinun on käytettävä Palvelutunnus objekti. Tämän Objektitunnus on viittaamaan palveluobjektia toimintoja tai tehdä muutoksia palvelun päänimen objektin tunnus. Kuten otetaan palveluobjektin järjestelmänvalvojana työtilaan.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Miten Power BI Embedded poikkeaa muista Azure-palveluista?

Power BI-tilin on oltava ennen ostit Power BI Embedded-azuressa. Power BI Embedded käyttöön alueen määrittää Power BI-tilisi. Hallitse Power BI Embedded -resurssia Azuressa seuraavien toimintojen suorittamiseksi:

* Skaalaus ylös/alas
* Kapasiteetin järjestelmänvalvojien lisääminen
* Palvelun keskeytys/jatkaminen

PowerBI.comissa voit määrittää työtiloja Power BI Embedded -kapasiteettiin tai poistaa niiden määrityksen.

### <a name="what-are-the-supported-deploy-regions"></a>Mitä ovat tuetussa käyttöönottoalueita?

Kaakkois-Australia; Brasilia, etelä; Kanada, keskinen; Itä-Yhdysvallat 2; Intia, länsiosa; Japani, itä; Yhdysvaltojen pohjoinen keskiosa; Pohjois-Eurooppa; Yhdysvaltojen eteläinen keskiosa; Kaakkois-Aasia; Yhdistynyt kuningaskunta, eteläinen; Länsi-Eurooppa; Länsi-Yhdysvallat ja Länsi-Yhdysvallat 2.

### <a name="what-content-pack-data-types-can-you-embed"></a>Sisältöpaketin mitä tietotyyppejä voit upottaa?

Voit *ei* upottaa **koontinäyttöjä** ja **ruutuja** rakennettu Sisältöpaketin tietojoukoista. Kuitenkin voit *voit* upottaa **raporttien** Sisältöpaketin tietojoukosta luotuja.

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>Mitä eroa on vs rivitason suojaus (RLS) avulla. JavaScript-suodattimien käyttämisessä?

Kun käyttää rivitason Suojausta ja JavaScript-suodattimet, koska yksi menetelmä on Lisätietoja hallinnasta mitä tietyn käyttäjän voi nähdä on usein sekaannusta ympärille ja toinen on optimoiminen käyttäjän näkymä.

Rivitason suojauksella ISV-kehittäjä hallitsee tietojen suodatusta osana mallin ja upotustunnuksen luomista. Käyttäjä näkee vain sen, mitä ISV sallii käyttäjän näkevän. Tässä tapauksessa käyttäjä voi halutessaan nähdä vähemmän kuin mitä suodatetaan, mutta hän ei voi ohittaa rivitason suojauksen määritystä ja nähdä enempää kuin mitä sallitaan.

Asiakaspuolen suodatusta (JavaScript) joka voi päättää käyttäjä näkee, että, mutta hän voi hallita muutoksia käyttäjä voi itse näkymää. Käyttäjän Javascript-Asiakaskoodin voi käynnistää tietojen suodattamista taustassa, koska se ei voi käsitellä suojatun.

Lisätietoja on artikkelissa [Rivitason suojaus JavaScript-suodattimiin verrattuna](embedded-row-level-security.md#using-rls-vs-javascript-filters).

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>Miten voin hallita palvelun päänimien käyttöoikeuksia Power BI:llä?

Kun otat [palveluobjektia](embed-service-principal.md) käytettäväksi Power BI-sovelluksen AD-käyttöoikeudet tulevat voimaan enää. Sovelluksen käyttöoikeuksia hallitaan tässä tapauksessa Power BI -hallintaportaalissa.

Palvelun päänimet perivät käyttöoikeudet kaikkiin Power BI -vuokraaja-asetuksiin käyttöoikeusryhmästään. Rajoittaa käyttöoikeuksia, Luo palvelun pääkohteet erityinen käyttöoikeusryhmä ja lisää se **lukuun ottamatta tiettyjä käyttöoikeusryhmiä** asianmukaiset, käytössä Power BI-asetusten luettelo.

Tällä on merkitystä, kun lisäät palvelun päänimen **järjestelmänvalvojaksi** uuteen työtilaan. Voit hallita tätä [ohjelmointirajapinnoilla](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser) tai Power BI -palvelussa.

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>Milloin kannattaa käyttää sovellustunnusta ja milloin palvelun päänimen objektitunnusta?

**[Sovellustunnuksella](embed-sample-for-customers.md#application-id)** luodaan käyttöoikeustietue, kun sovellustunnus välitetään todennettavaksi.

Jos haluat viitata palvelun päänimeen toiminnoissa tai tehdä muutoksia, käytä **[palvelun päänimen objektitunnusta](embed-service-principal.md#how-to-get-the-service-principal-object-id)** (ottaa esimerkiksi palvelun päänimen käyttöön työtilan järjestelmänvalvojana).

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>Voinko hallita paikallista tietoyhdyskäytävää palvelun päänimellä?

Et voi hallita paikallista tietoyhdyskäytävä (tietoyhdyskäytävä) [palvelun päänimellä](embed-service-principal.md) samalla tavalla kuin päätilillä.

Päätilillä voit asentaa tietoyhdyskäytävän, lisätä käyttäjiä yhdyskäytävään, yhdistää tietolähteisiin ja suorittaa muita hallintatehtäviä.

Palvelun päänimellä voit määrittää [rivitason suojauksen (RLS)](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal-preview) SQL Server Analysis Servicesin (SSAS) paikallisella reaaliaikaisella tietolähdeyhteydellä. Tällä tavalla voit hallita käyttäjiä ja heidän käyttöoikeuksiaan tietoihin SSAS:ssä, kun integroit **Power BI Embeddedin** palvelun päänimellä.

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>Voinko kirjautua Power BI -palveluun palvelun päänimellä?

Et voi kirjautua Power BI -palveluun palvelun päänimellä.

Et myöskään voi käyttää sisältöä käyttäjänä ulkoisissa sovelluksissa (SaaS-upotus) (vain kun luot upotustunnuksen).

### <a name="what-are-the-best-practices-to-improve-performance"></a>Mitkä ovat parhaita käytäntöjä suorituskyvyn parantamiseksi?

[Power BI Embeddedin suorituskyky](embedded-performance-best-practices.md)

## <a name="licensing"></a>Käyttöoikeudet

### <a name="how-do-i-purchase-power-bi-embedded"></a>Miten voin ostaa Power BI Embeddedin?

Power BI Embedded on saatavissa Azuren kautta.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>Mitä tapahtuu, jos olen jo ostanut Power BI Premium ja haluan nyt joitakin Power BI Embedded-Azure-etusi?

Asiakkaat jatkavat aiempien Power BI Premium-ostosten maksaa kuluvan sopimusjakson loppuun saakka ja, tässä vaiheessa voivat sitten vaihtaa niiden Power BI Premium-ostoksiaan tarpeen mukaan.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Pitääkö minun yhä ostaa Power BI Premium, jotta voin käyttää Power BI Embeddediä?

Ei. Power BI Embedded sisältää Azure-pohjaisen kapasiteetin. Sinun täytyy ottaa se käyttöön ja jakaa ratkaisusi asiakkaille.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Mihin asiakkaan on sitouduttava, kun hän ostaa Power BI Embeddedin?

Asiakkaat voivat muuttaa käyttötapaansa tuntipohjaisesti. Ei vaadi kuukausittaista tai vuosittaista sitoutumista Power BI Embedded-palvelun.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Miten Power BI Embeddedin käyttö näkyy laskussani?

Power BI Embeddedin laskutus perustuu ennustettavissa olevaan tuntihintaan, joka pohjautuu käyttöön otetun solmun (tai käyttöön otettujen solmujen) tyyppiin. Laskutetaan niin kauan kuin resurssi on aktiivinen, vaikka et käyttäisi sitä. Tarvitset keskeyttää resurssi pysäyttää laskutuksen.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Kuka tarvitsee Power BI Pro -käyttöoikeuden Power BI Embeddediä varten ja miksi?

Tarvitset Power BI Pro-käyttöoikeus tai [palveluobjektia](embed-service-principal.md) REST-ohjelmointirajapintoja. Lisää raportteja Power BI-työtilaan, analyytikko on Power BI Pro-käyttöoikeus tai palvelun päänimen. Voit hallita Power BI-vuokraajaa ja kapasiteettia, järjestelmänvalvoja vaaditaan Power BI Pro ‑käyttöoikeudet.

Power BI Embedded sallii Power BI-portaalin hallintaan ja vahvistetaan upotettua sisältöä, Power BI Pro-käyttöoikeus vaaditaan sovelluksen powerbi.comissa, jotta voit käyttää raportteja oikeissa säilöissä olevia todentamiseen.

Käyttäjä ei kuitenkaan tarvitse Pro-käyttöoikeutta [upotettujen raporttien luomiseen tai muokkaamiseen](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) sovelluksessasi, koska hänen ei tarvitse olla Power BI -käyttäjä.

### <a name="can-i-get-started-for-free"></a>Voinko aloittaa käytön maksutta?

Kyllä, voit käyttää [Azure-saldoasi](https://azure.microsoft.com/free/) Power BI Embeddediä varten.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Onko Power BI Embedded -kokeiluversiota mahdollista käyttää Azuressa?

Koska Power BI Embedded on osa Azurea, on mahdollista käyttää palvelu, jonka [yhteydessä saadulla 200 $: n saldolla](https://azure.microsoft.com/free/).

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>Onko Power BI Embedded saatavilla kansallisissa pilvipalveluissa (Yhdysvaltain julkishallinto, Saksa, Kiina)?

Power BI Embedded on käytettävissä myös [kansallisissa pilvipalveluissa](embed-sample-for-customers-national-clouds.md).

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Onko Power BI Embedded käytettävissä järjestö- ja opetustarkoituksiin?

Ei mitään erityisiä Azure hinnoittelu voittoa tavoittelemattomat järjestöt ja opetustarkoituksiin.

## <a name="power-bi-workspace-collection"></a>Power BI ‑työtilakokoelma

### <a name="what-is-power-bi-workspace-collection"></a>Mikä on Power BI ‑työtilakokoelma?

**Power BI-Työtilakokoelman** (**Power BI Embedded** versio 1) on ratkaisu perusteella **Power BI-Työtilakokoelman** Azure resource. Tämän ratkaisun avulla voit luoda asiakkaillesi **Power BI Embedded** -sovelluksia **Power BI -työtilakokoelma** -ratkaisun Power BI -sisältöä käyttämällä, erillisiä ohjelmointirajapintoja ja työtilakokoelma-avaimia antaaksesi sovellukselle käyttöoikeuden Power BI:hin.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Voinko siirtyä Power BI -työtilakokoelmasta Power BI Embeddediin?

1. Voit käyttää siirtotyökalua kloonataksesi **Power BI -työtilakokoelma** -sisällön Power BI:hin - https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration.

2. Aloita **Power BI Embedded** -sovelluksen soveltuvuusselitys, joka käyttää Power BI -sisältöä.

3. Kun olet valmis tuotantoon, osta **Power BI Embeddedille** varattua kapasiteettia ja määritä Power BI sisältö (työtila) kyseiselle kapasiteetille.

    > [!Note]
    > Voit jatkaa **Power BI t-työtilakokoelman** käyttöä sillä aikaa kun rinnakkaista työtilaa luodaan **Power BI Embedded** -ratkaisulla. Kun olet valmis, voit siirtää asiakkaasi uuteen **Power BI Embedded** -ratkaisuun ja poistaa **Power BI -työtilakokoelmaratkaisun** käytöstä.

Katso lisätietoja artikkelista [Miten Power BI -työtilakokoelman sisältö siirretään Power Embeddediin](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>Ollaanko Power BI-Työtilakokoelman sähköpostipalvelun poistamisesta?

Kyllä, mutta asiakkaat, jotka käyttävät **Power BI-Työtilakokoelman** voivat jatkaa sen käyttöä kunnes sähköpostipalvelun poistamisesta. Asiakkaat voivat myös luoda uusia työtilakokoelmia ja mitä tahansa **Power BI Embedded** -sovelluksia, jotka yhä käyttävät **Power BI -työtilakokoelmaa**.

Tämä tarkoittaa kuitenkin, että uudet ominaisuudet eivät ole lisätä **Power BI-Työtilakokoelman** ratkaisuja. Pyydämme asiakkaita siirtymään uuteen **Power BI Embedded** ratkaisu.

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Koska Power BI -työtilakokoelman tuki lakkautetaan?

Asiakkaat, jotka käyttävät **Power BI -työtilakokoelmaa** voivat jatkaa sen käyttöä 2018 kesäkuun loppuun asti tai tukisopimuksensa loppuun asti.

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>Mitkä alueet PBI-Työtilakokoelmia voi luoda?

Saatavilla alueilla: Kaakkois-Australia; Brasilia, etelä; Kanada, keskinen; Itä-Yhdysvallat 2; Japani, itä; Yhdysvaltojen pohjoinen keskiosa; Pohjois-Eurooppa; Yhdysvaltojen eteläinen keskiosa; Kaakkois-Aasia; Yhdistynyt kuningaskunta, eteläinen; Länsi-Eurooppa; Intia, läntinen ja Länsi-Yhdysvallat.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Miksi minun pitäisi siirtyä PBI -työtilakokoelmasta Power BI Embeddediin?

On joitakin uusia **Power BI Embedded** ratkaisun ominaisuuksia ja toimintoja, joita ei voi tehdä **Power BI-Työtilakokoelman**.

Seuraavassa joitakin ominaisuuksista:
* Kaikki PBI-tietolähteet tuetaan. Vain kaksi **Power BI-Työtilakokoelman** tietolähteitä. 
* Uusia ominaisuuksia, kuten usein kysyttyjä kysymyksiä, päivityksiä, kirjanmerkkejä, koontinäyttöjen ja ruutujen upottamista ja mukautettuja valikoimia tuetaan vain **Power BI Embedded** -ratkaisussa.
* Kapasiteettilaskutusmalli.

## <a name="embedding-setup-tool"></a>Upottamisen määritystyökalu

### <a name="what-is-the-embedding-setup-tool"></a>Mikä on upottamisen määritystyökalu?

[Upottamisen määritystyökalun](https://aka.ms/embedsetup) avulla voit nopeasti päästä alkuun ja ladata mallisovelluksen, joilla voit aloittaa upottamisen Power BI:ssä.

### <a name="which-solution-should-i-choose"></a>Kumpi ohjelma kannattaa valita?

* [Asiakkaille tarkoitettu upotus](embedding.md#embedding-for-your-customers) mahdollistaa raporttinäkymien ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Suorita [asiakkaille tarkoitettu upotus](https://aka.ms/embedsetup/AppOwnsData).
* [Organisaatiolle tarkoitettu upotus](embedding.md#embedding-for-your-organization) mahdollistaa Power BI -palvelun laajentamisen. Suorita [organisaatiolle tarkoitettu upotus](https://aka.ms/embedsetup/UserOwnsData).

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>Olen ladannut mallisovelluksen, kumpaa ohjelmaa minun tulee käyttää?

Jos käytät **asiakkaille tarkoitettua upotusta**, tallenna ja pura *PowerBI-Developer-Samples.zip* -tiedosto. Avaa sitten *PowerBI-Developer-Samples-master\App Owns Data*-kansio ja suorita *PowerBIEmbedded_AppOwnsData.sln*-tiedosto.

Jos käytät **organisaatiolle tarkoitettua upotusta**, tallenna ja pura *PowerBI-Developer-Samples.zip* -tiedosto. Avaa sitten *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* -kansio ja suorita *pbi-saas-embed-report.sln* -tiedosto.

### <a name="how-can-i-edit-my-registered-application"></a>Miten voi muokata rekisteröityä sovellusta?

Jos haluat oppia muokkaamaan Azure AD -rekisteröityjä sovelluksia, katso [Pikaopas: Sovelluksen päivittäminen Azure Active Directoryssa](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-update-azure-ad-app).

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Miten voit muokata Power BI käyttäjäprofiilia tai tietoja?

Voit oppia muokkaamaan Power BI -tietoja [täällä](https://docs.microsoft.com/power-bi/service-basic-concepts).

Jos haluat lisätietoja, katso [upotetun sovelluksen vianmääritys](embedded-troubleshoot.md).

Onko sinulla kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
