---
title: Azuren automaattianalyysipalveluiden integroiminen Power BI:hin (esikatselu)
description: Opi käyttämään automaattianalyysipalveluita Power BI:ssä
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/12/2019
ms.author: davidi
LocalizationGroup: conceptual
ms.openlocfilehash: 9a7afafaa14ed890e10e77507aafb637755cd87f
ms.sourcegitcommit: 06ae54ed221979939699c67d63aeccba8b9dfcda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/14/2019
ms.locfileid: "57965490"
---
# <a name="azure-machine-learning-integration-in-power-bi-preview"></a>Azuren automaattianalyysipalveluiden integroiminen Power BI:hin (esikatselu)

Useat organisaatiot käyttävät **automaattianalyysin** malleja saadakseen parempia merkityksellisiä tietoja ja ennusteita liiketoiminnastaan. Voit visualisoida ja käynnistää merkityksellisiä tietoja näistä malleista raporteissa, koontinäytöissä ja muita analyyseissa, mikä helpottaa merkityksellisten tietojen välittämistä niille yrityskäyttäjille, jotka tarvitsevat niitä eniten.  Power BI:n avulla voi nyt helposti sisällyttää Azuren automaattianalyysipalvelussa isännöityjen mallien merkityksellisiä tietoja käyttämällä yksinkertaisia osoita ja napsauta -liikkeitä.

Jotta tätä ominaisuutta voisi käyttää, datatieteilijän tulee vain myöntää Azuren automaattianalyysipalveluiden mallille käyttöoikeus BI-analyytikkoon Azure-portaalin kautta.  Kunkin istunnon aluksi Power Query sitten löytää kaikki Azuren automaattianalyysipalveluiden mallit, joihin käyttäjällä on käyttöoikeus, ja paljastaa ne dynaamisina Power Query -funktioina.  Käyttäjä voi käynnistää kyseiset funktiot käyttämällä niitä Power Query -editorin valintanauhasta tai käynnistämällä suoraan M-funktion. Lisäksi Power BI käsittelee käyttöoikeuspyynnöt automaattisesti erissä suorituskyvyn parantamiseksi, kun se käynnistää Azuren automaattianalyysipalveluiden mallin rivijoukolle.

Tätä toimintoa tuetaan tällä hetkellä vain Power BI -tietovoille sekä Power Querylle verkossa Power BI -palvelussa.

Lisätietoja tietovoista on artikkelissa [Omatoiminen tietojen valmistelu Power BI:ssä](service-dataflows-overview.md).

Lisätietoja Azuren automaattianalyysipalveluista on seuraavissa:

- Yleiskatsaus:  [Mitä ovat Azuren automaattianalyysipalvelut?](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml)
- Pikaoppaita ja opetusohjelmia Azuren automaattianalyysipalveluihin:  [Azuren automaattianalyysipalveluiden dokumentaatio](https://docs.microsoft.com/azure/machine-learning/)

## <a name="granting-access-to-the-azure-ml-model-to-a-power-bi-user"></a>Azuren automaattianalyysipalvelumallin käyttöoikeuksien myöntäminen Power BI -käyttäjälle

Jotta käyttäjä voisi käsitellä Azuren automaattianalyysipalveluiden mallia Power BI:stä, hänellä on oltava Azure-tilauksen **luku**-oikeudet.  Lisäksi:

- Automaattianalyysistudion malleille **luku**-oikeus automaattianalyysistudion verkkopalveluun
- Automaattianalyysipalvelun malleille **luku**-oikeus automaattianalyysipalvelun työtilaan

Tässä artikkelissa kuvataan, kuinka Power BI -käyttäjälle myönnetään käyttöoikeus Azuren automaattianalyysipalveluissa isännöityyn malliin, niin että käyttäjä voi käsitellä mallia Power Query -funktiona.  Lisätietoja on artikkelissa [Käyttöoikeuksien hallinta RBAC:n ja Azure-portaalin avulla](https://docs.microsoft.com/azure/role-based-access-control/role-assignments-portal).

1. Kirjaudu sisään [Azure-portaaliin](https://portal.azure.com).

2. Siirry **Tilaukset**-sivulle. Pääset **Tilaukset**-sivulle valitsemalla Azure-portaalin vasemmanpuoleisen siirtymisvalikon luettelosta **Kaikki palvelut** -vaihtoehdon.

    ![Azuren Tilaukset-sivu](media/service-machine-learning-integration/machine-learning-integration_01.png)

3. Valitse tilauksesi.

    ![Valitse tilauksesi](media/service-machine-learning-integration/machine-learning-integration_02.png)

4. Valitse **Käyttöoikeuksien valvonta (IAM)** ja valitse sitten **Lisää**-painike.

    ![Käyttöoikeuksien valvonta (AIM)](media/service-machine-learning-integration/machine-learning-integration_03.png)

5. Valitse rooliksi **Lukija**. Valitse Power BI -käyttäjä, jolle haluat myöntää Azuren automaattianalyysipalveluiden käyttöoikeuden.

    ![Valitse rooliksi Lukija](media/service-machine-learning-integration/machine-learning-integration_04.png)

6. Valitse **Tallenna**.

7. Toista vaiheet kolmesta kuuteen ja myönnä käyttäjälle **Lukija**-käyttöoikeus tiettyyn Automaattianalyysistudion verkkopalveluun *tai* Automaattianalyysipalvelun työtilaan, joka isännöi mallia.


## <a name="schema-discovery-for-machine-learning-service-models"></a>Rakenteen etsiminen Automaattianalyysipalveluiden malleille

Datatieteilijät käyttävät ensisijaisesti Pythonia, kun he kehittävät (ja jopa ottavat käyttöön) koneoppimismalleja Automaattianalyysipalveluihin.  Toisin kuin automaattianalyysistudion yhteydessä, joka auttaa automatisoimaan skeematiedoston luonnin mallia varten, automaattianalyysipalvelun tapauksessa datatieteilijän tulee erikseen luoda rakennetiedosto Pythonia käyttämällä.

Tämä rakennetiedosto tulee sisällyttää kohteeseen

## <a name="invoking-the-azure-ml-model-in-power-bi"></a>Azuren automaattianalyysipalveluiden mallin käynnistäminen Power BI:ssä

Voit käynnistää minkä tahansa Azuren automaattianalyysipalveluiden mallin, johon olet saanut käyttöoikeuden, suoraan tietovuosi Power Query -editorista. Jos haluat käyttää Azuren automaattianalyysipalveluiden malleja, valitse sen entiteetin **Muokkaa**-painike, jota haluat rikastuttaa Azuren automaattianalyysipalveluiden mallin merkityksellisillä tiedoilla, kuten seuraavassa kuvassa esitetään.

![Power BI -palvelu – entiteetin muokkaaminen](media/service-machine-learning-integration/machine-learning-integration_05.png)

**Muokkaa**-painikkeen valitseminen avaa Power Query -editorin tietovuossa oleville entiteeteille.

![Power Query -editori](media/service-machine-learning-integration/machine-learning-integration_06.png)

Valitse valintanauhan **Tekoälyn merkitykselliset tiedot** -painike ja valitse sitten vasemmasta siirtymisvalikosta _Azuren koneoppimismallit_ -kansio. Kaikki Azuren automaattianalyysipalveluiden mallit, joihin sinulla on käyttöoikeus, näkyvät tässä Power Query -funktioina. Lisäksi Azuren automaattianalyysipalveluiden mallin syöteparametrit yhdistetään automaattisesti vastaavan Power Query -funktion parametreina.

Jos haluat käynnistää Azuren automaattianalyysipalveluiden mallin, voit määrittää avattavassa luettelossa minkä tahansa valitun entiteetin sarakkeista syötteeksi. Voit myös määrittää syötteenä käytettävän vakioarvon käyttämällä syötevalintaikkunan vasemmalla puolella olevaa sarakekuvaketta.

![Valitse sarake](media/service-machine-learning-integration/machine-learning-integration_07.png)

Valitse **Käynnistä**, niin voit tarkastella Azuren automaattianalyysipalveluiden mallin tulostetta entiteettitaulukon uutena sarakkeena. Näet myös mallin kutsun kyselyyn käytettynä vaiheena.

![Valitse Käynnistä](media/service-machine-learning-integration/machine-learning-integration_08.png)

Jos malli palauttaa useita tulosteparametreja, ne ryhmitellään yhteen tulossarakkeen tietueena. Voit laajentaa sarakkeen, niin että saat yksittäiset tulosteparametrit erillisiin sarakkeisiin.

![Laajenna sarake](media/service-machine-learning-integration/machine-learning-integration_09.png)

Kun tallennat tietovuon, malli käynnistetään automaattisesti, kun tietovuohon päivitetään entiteettitaulukon uusia tai päivitettyjä rivejä.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä artikkelissa annettiin yleiskuva siitä, miten automaattianalyysit integroidaan Power BI -palveluun. Myös seuraavat artikkelit voivat olla kiinnostavia ja hyödyllisiä. 

* [Opetusohjelma: Automaattianalyysistudion mallin käynnistys Power BI:ssä (esikatselu)](service-tutorial-invoke-machine-learning-model.md)
* [Opetusohjelma: Kognitiivisten palvelujen käyttö Power BI:ssä](service-tutorial-use-cognitive-services.md)
* [Kognitiiviset palvelut Power BI:ssä (esikatselu)](service-cognitive-services.md)

Lisätietoja tietovoista on seuraavissa artikkeleissa:
* [Tietovoiden luominen ja käyttäminen Power BI:ssä](service-dataflows-create-use.md)
* [Laskettujen entiteettien käyttäminen Power BI Premiumissa (esikatselu)](service-dataflows-computed-entities-premium.md)
* [Tietovoiden käyttäminen paikallisten tietolähteiden kanssa (esikatselu)](service-dataflows-on-premises-gateways.md)
* [Kehittäjien resurssit Power BI -tietovoille (esikatselu)](service-dataflows-developer-resources.md)
* [Tietovuot ja Azure Data Lake -integrointi (esikatselu)](service-dataflows-azure-data-lake-integration.md)


