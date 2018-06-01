---
title: Usein kysyttyjä kysymyksiä – Power BI Embedded
description: Selaa Power BI Embeddediä koskevien usein kysyttyjen kysymysten ja vastausten luetteloa.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/07/2018
ms.author: maghan
ms.openlocfilehash: 52ff1095c063be867354a23e0e8e4908a4b4e1d7
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/08/2018
ms.locfileid: "30974907"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Usein kysyttyjä kysymyksiä – Power BI Embedded

* Jos sinulla on muita kysymyksiä, [voit esittää niitä Power BI -yhteisössä](http://community.powerbi.com/).
* Eikö ongelma ratkennut? Käy [Power BI -tukisivulla](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Yleiset

### <a name="what-is-power-bi-embedded"></a>Mikä Power BI Embedded on?

Microsoft Power BI Embeddedin avulla sovelluskehittäjät voivat upottaa näyttäviä, täysin interaktiivisia raportteja, koontinäyttöjä ja ruutuja sovelluksiin ilman, että aikaa ja kustannuksia kuluu omien tietojen visualisointien ja ohjausobjektien luomiseen alusta alkaen.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Mikä on Power BI Embeddedin kohderyhmä?

Omia sovelluksiaan luovat sovelluskehittäjät ja ohjelmistoyritykset, joita kutsutaan riippumattomiksi ohjelmistotoimittajiksi (ISV).

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Miten Power BI Embedded poikkeaa Power BI -palvelusta?

Power BI Embedded on tarkoitettu riippumattomille ohjelmistotoimittajille tai kehittäjille, jotka kehittävät sovelluksia ja haluavat upottaa niihin asiakkaidensa päätöksentekoa helpottavia visualisointeja ilman analytiikkaratkaisun luomista alusta alkaen. Upotetut analyysitoiminnot mahdollistavat yrityskäyttäjille pääsyn liiketoimintatietoihin ja kyselyt, joiden avulla niistä voidaan luoda sovelluksessa merkityksellisiä tietoja.

Power BI on puolestaan ohjelmisto palveluna -tyyppinen analytiikkaratkaisu, joka mahdollistaa organisaatioille kriittisimpien liiketoimintatietojen tarkastelun yhdessä näkymässä.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Mikä on Power BI Premiumin ja Power BI Embeddedin välinen ero?

Power BI Premium on optimoitu yrityksille, jotka haluavat täydellisen BI-ratkaisun, joka mahdollistaa organisaation, kumppanien, asiakkaiden ja toimittajien tietojen tarkastelun yhdessä näkymässä. Power BI Premium auttaa organisaatiotasi tekemään päätöksiä. Power BI Premium on SaaS-tuote, jonka käyttäjät voivat käyttää sisältöä Power BI-portaalin, mobiilisovelluksen ja sisäisesti kehitettyjen sovellusten välityksellä.

Power BI Embedded on tarkoitettu ISV-ohjelmistotoimittajille tai kehittäjille, jotka kehittävät sovelluksia ja haluavat upottaa niihin visualisointeja. Power BI Embedded auttaa asiakkaitasi tekemään päätöksiä, sillä se on suunnattu sovelluskehittäjille, joiden sovelluksia käyttävät asiakkaat voivat käyttää Power BI Embedded -kapasiteettiin tallennettua sisältöä organisaation sisällä tai ulkopuolella. Power BI Embedded -kapasiteetin sisältöä ei voida jakaa yhden napsautuksen julkaisulla verkkoon tai yhden napsautuksen julkaisulla SharePointiin, eikä se tue SSRS-raportteja.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Mikä on Microsoftin suositus sen suhteen, milloin asiakkaan kannattaa ostaa Power BI Premium ja milloin Power BI Embedded?

Microsoft suosittelee, että yritykset ostaisivat Power BI Premiumin, joka on yritystason omatoiminen BI-pilviratkaisu, ja ISV-ohjelmistotoimittajat Power BI Embeddedin, joka tarjoaa pilvipohjaisia upotettuja analyysitoimintoja. Ei kuitenkaan ole mitään rajoituksia sen suhteen, minkä tuotteen asiakas voi ostaa.

Joissain tapauksissa (tavallisesti suuri) ISV haluaa käyttää P-varastointiyksikköä saadakseen organisaatiolleen esimääritetyn Power BI -palvelun hyödyt sekä upotusmahdollisuuden sovelluksiin. Jotkin yritykset voivat tietysti myös päättää käyttää A-varastointiyksikköjä Azuressa, jos niitä kiinnostaa vain yrityssovellusten kehittäminen ja analyysitoimintojen upottaminen näihin sovelluksiin esimääritetyn Power BI -palvelun käytön sijasta.

### <a name="how-many-embed-tokens-can-i-create"></a>Kuinka monta upotettavaa tunnusta voit luoda?

PRO-käyttöoikeudella upotettavat tunnukset on tarkoitettu vain kehitykseen ja kehitystestaukseen, joten Power BI -päätili voi luoda vain rajallisen määrän upotettavia tunnuksia. Tuotantoympäristössä upottamista varten täytyy [ostaa kapasiteettia](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical). Kun olet ostanut kapasiteettia, voit luoda upotettavia tunnuksia rajattomasti.

### <a name="when-will-power-bi-embedded-be-available-in-azure"></a>Milloin Power BI Embedded on käytettävissä Azuressa?

Power BI Embedded on käytettävissä nyt.

## <a name="technical"></a>Tekniset

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Mikä on Azuren A-varastointiyksiköiden ja Office 365:n EM-varastointiyksiköiden välinen ero?

PowerBI.com on yritysratkaisu, joka sisältää useita sosiaalisen yhteistyön ja sähköpostitilauksen kaltaisia toimintoja palveluna ohjelmistossa

Power BI Embedded on ohjelmointirajapintojen joukko, joiden avulla kehittäjät voivat luoda upotetun analytiikkaratkaisun palveluksi tietyssä ympäristössä. Upotettujen analyysitoimintojen yhteydessä PowerBI.comia tulee käyttää ISV-toimittajien ja kehittäjien auttamiseen upotetun analytiikkaratkaisun sisällön ja vuokraajatason asetusten hallinnassa.

Alla on osittainen luettelo eroista näiden ratkaisujen yhteydessä käytettävien ominaisuuksien välillä.

|Ominaisuus  |Power BI Embedded<br>(A-varastointiyksiköt) |Power BI Premium -kapasiteetti<br>(EM-varastointiyksiköt)  |
|---------|---------|---------|
|Upotusartefaktit Power BI -sovelluksen työtiloista     |Azure-kapasiteetti |Office 365 -kapasiteetti |
|Raporttien käyttämiseen vaadittu Power BI -käyttöoikeus |Ei  |Kyllä |
|Power BI -raporttien käyttäminen Embedded-sovelluksessa |Kyllä  |Kyllä |
|Power BI -raporttien käyttäminen SharePointissa |Ei |Kyllä |
|Power BI -raporttien käyttäminen Teamsissa |Ei |Kyllä |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI tarjoaa nyt upottamiseen kolme varastointiyksikköä: A-, EM- ja P-varastointiyksiköt. Mikä niistä minun tulisi ostaa omaa skenaariotani varten?

|  |A-varastointiyksikkö (Power BI Embedded)  |EM-varastointiyksikkö (Power BI Premium)  |P-varastointiyksikkö (Power BI Premium)  |
|---------|---------|---------|---------|
|Ostaminen     |Azure-portaali |Office |Office |
|Käyttötapaukset |* Sisällön upottaminen omaan sovellukseen |* Sisällön upottaminen omaan sovellukseen<br>* Sisällön jakaminen Power BI:n MAKSUTTOMAN version käyttäjien kanssa PowerBI.comin ulkopuolella ja upottaminen muihin SaaS-sovelluksiin (SharePoint, Teams) |* Sisällön upottaminen omaan sovellukseen<br>* Sisällön jakaminen Power BI:n MAKSUTTOMAN version käyttäjien kanssa PowerBI.comin ulkopuolella ja upottaminen muihin SaaS-sovelluksiin (SharePoint, Teams)<br>* Sisällön jakaminen Power BI:n MAKSUTTOMAN version käyttäjien kanssa PowerBI.comin kautta  |
|Laskutus |Tunneittain |Kuukausittain |Kuukausittain |
|Sitoutuminen  |Ei sitoutumista |Vuosittain  |Kuukausittain/vuosittain |
|Erot |Täysi joustavuus – skaalaus ylös/alas, resurssien keskeytys/jatkaminen Azure-portaalissa tai ohjelmointirajapinnan kautta  |Voidaan käyttää sisällön upottamiseen SharePoint Onlinessa ja Microsoft Teamsissa |Yhdistää sovelluksiin upottamisen ja Power BI -palvelun käytön samassa kapasiteetissa |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Mitkä ovat ennakkoedellytykset PBIE-kapasiteetin luomiseksi Azuressa?

- Sinun on kirjauduttava organisaation hakemistoon (MSA-tilejä ei tueta).
- Sinulla on oltava Power BI -vuokraaja, eli vähintään yhden käyttäjän hakemistossasi on täytynyt rekisteröityä Power BI:n käyttäjäksi. 
- Sinulla täytyy olla Azure-tilaus organisaatiosi hakemistossa.

### <a name="how-can-i-monitor-capacity-consumption"></a>Miten voin valvoa kapasiteetin käyttöä?

Valvonta Azuren kautta sisältyy lähitulevaisuuden suunnitelmiimme. Azure-resurssi Power BI Embedded sisältää tulevaisuudessa valvonnan KPI-mittareita, jotka osoittavat kunnon ja käyttötavan.

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Skaalautuuko kapasiteettini automaattisesti sovellukseni kulutuksen mukaiseksi?

Automaattista skaalausta ei tällä hetkellä ole, mutta kaikki ohjelmointirajapinnat ovat skaalattavissa milloin tahansa.

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Mikä on Power BI Embeddedin todennusmalli?

Power BI Embedded käyttää edelleen Azure AD:tä pääkäyttäjän (nimetty käyttäjä, jolla on Power BI Pro -käyttöoikeus) todennukseen ja todentaa sovelluksen Power BI:n sisällä.

Sovelluksen käyttäjien todentamisen ja käyttöoikeuksien myöntämisen toteuttaa ISV, joka voi toteuttaa oman todennuksensa sovelluksilleen.

Jos sinulla on jo Azure AD -vuokraaja, voit käyttää olemassa olevaa hakemistoa tai voit luoda uuden Azure AD-vuokraajan upotetun sovelluksen sisällön suojaamista varten.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Miten Power BI Embedded poikkeaa muista Azure-palveluista?

ISV:llä/kehittäjällä on oltava Power BI -tili, jotta Power BI Embedded on mahdollista ostaa Azuressa. Oma Power BI Embedded -käyttöönottoalueesi määräytyy Power BI -tilisi mukaan. Hallitse Power BI Embedded -resurssia Azuressa seuraavien toimintojen suorittamiseksi:

* Skaalaus ylös/alas
* Kapasiteetin järjestelmänvalvojien lisääminen
* Palvelun keskeytys/jatkaminen

PowerBI.comissa voit määrittää työtiloja Power BI Embedded -kapasiteettiin tai poistaa niiden määrityksen.

### <a name="what-deploy-regions-are-supported"></a>Mitä käyttöönottoalueita tuetaan?

Kaakkois-Australia; Brasilia, etelä; Kanada, keskinen; Itä-Yhdysvallat 2; Intia, länsiosa; Japani, itä; Yhdysvaltojen pohjoinen keskiosa; Pohjois-Eurooppa; Yhdysvaltojen eteläinen keskiosa; Kaakkois-Aasia; Yhdistynyt kuningaskunta, eteläinen; Länsi-Eurooppa; Länsi-Yhdysvallat ja Länsi-Yhdysvallat 2.

### <a name="what-type-of-content-pack-data-can-be-embedded"></a>Minkä tyyppisiä sisältöpaketin tietoja voidaan upottaa?

**Koontinäyttöjä** ja **ruutuja**, jotka on rakennettu sisältöpaketin tietojoukoista, *ei voida* upottaa, mutta sisältöpaketin tietojoukosta luotuja **raportteja** *voidaan* upottaa.

## <a name="licensing"></a>Käyttöoikeudet

### <a name="how-do-i-purchase-power-bi-embedded"></a>Miten voin ostaa Power BI Embeddedin?

Power BI Embedded on saatavissa Azuren kautta.

### <a name="how-power-bi-embedded-be-metered"></a>Miten Power BI Embeddedin käyttö laskutetaan?

Power BI Embeddedin käyttö laskutetaan tuntiperusteisesti.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Miten Power BI Embeddedin käyttö näkyy laskussani?

Power BI Embeddedin laskutus perustuu ennustettavissa olevaan tuntihintaan, joka pohjautuu käyttöön otetun solmun (tai käyttöön otettujen solmujen) tyyppiin. Ota huomioon, että sinua laskutetaan niin kauan kuin resurssi on aktiivinen, vaikka et käyttäisi sitä. Jos haluat laskutuksen loppuvan, sinun täytyy aktiivisesti keskeyttää resurssi. Keskeytys voidaan tehdä Azuren tai ARM-ohjelmointirajapintojen kautta.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Mitä tapahtuu, jos olen jo ostanut Power BI Premiumin ja haluan nyt hyödyntää joitain Power BI Embeddedin etuja Azuressa?

Asiakkaat jatkavat aiempien Power BI Premium -ostosten maksamista kuluvan sopimusjakson loppuun saakka ja voivat sitten vaihtaa Power BI Premium -ostoksiaan tarpeen mukaan.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Pitääkö minun yhä ostaa Power BI Premium, jotta voin käyttää Power BI Embeddediä?

Ei. Power BI Embedded sisältää Azure-pohjaisen kapasiteetin. Sinun täytyy ottaa se käyttöön ja jakaa ratkaisusi asiakkaille.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Kuka tarvitsee Power BI Pro -käyttöoikeuden Power BI Embeddediä varten ja miksi?

Power BI Pro -käyttöoikeus vaaditaan analyytikolta, jonka täytyy lisätä raportteja Power BI -työtilaan, kehittäjältä, joka tarvitsee REST-ohjelmointirajapintojen käyttöä, ja jokaiselta vuokraajan järjestelmänvalvojalta, jonka on hallittava Power BI -vuokraajaa ja kapasiteettia.

Power BI Embedded sallii Power BI -portaalin käytön upotetun sisällön hallintaan ja vahvistamiseen, joten Power BI Pro -käyttöoikeus vaaditaan sovelluksen todentamiseen PowerBI.comissa, jotta voit käyttää oikeissa säilöissä olevia raportteja.

### <a name="can-i-get-started-for-free"></a>Voinko aloittaa käytön maksutta?

Kyllä, voit käyttää [Azure-saldoasi](https://azure.microsoft.com/free/) Power BI Embeddediä varten.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Onko Power BI Embedded -kokeiluversiota mahdollista käyttää Azuressa?

Power BI Embedded on osa Azurea, joten palvelua on mahdollista käyttää [rekisteröitymisen yhteydessä saadulla 170 euron saldolla](https://azure.microsoft.com/free/).

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Mihin asiakkaan on sitouduttava, kun hän ostaa Power BI Embeddedin? 

Asiakkaat voivat muuttaa käyttötapaansa tuntipohjaisesti. Power BI Embedded -palvelu ei vaadi kuukausittaista tai vuosittaista sitoutumista.

### <a name="where-is-power-bi-embedded-available-us-government-germany-china-what-is-the-timing"></a>Missä Power BI Embedded on käytettävissä? Yhdysvaltain julkishallinnossa? Saksassa? Kiinassa? Mikä on ajoitus?

Power BI Embedded on käytettävissä Azuren kaupallisissa pilvipalveluissa ja Yhdysvaltain julkishallinnon pilvipalvelussa.  Käytettävyys maakohtaisissa pilvipalveluissa Saksassa ja Kiinassa lisätään tulevaisuudessa.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Onko Power BI Embedded käytettävissä järjestö- ja opetustarkoituksiin?

Voittoa tavoittelemattomat järjestöt ja oppilaitokset voivat ostaa Azuren. Näille asiakastyypeille ei ole erikoishinnoittelua Azuressa.

Onko sinulla muuta kysyttävää? [Kokeile Power BI -yhteisöä](http://community.powerbi.com/)
