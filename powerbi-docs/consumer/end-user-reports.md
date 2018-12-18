---
title: Raportin tarkasteleminen Power BI:ssä
description: Raportit Power BI:ssä
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 31fe32bff8749b7b8136d980da9ea0e5bec3bc4f
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/12/2018
ms.locfileid: "53281053"
---
# <a name="reports-in-power-bi"></a>Raportit Power BI:ssä
## <a name="what-is-a-power-bi-report"></a>Mikä on Power BI -raportti?
Power BI ***-raportti*** on usean perspektiivin tietojoukkonäkymä, jossa visualisointeja, jotka edustavat eri havaintoja ja merkityksellisiä tietoja tietojoukosta.  Raportilla voi olla yksittäinen visualisointi tai sivuja, jotka ovat täynnä visualisointeja. Työroolistasi riippuen voit olla joku, joka *luo* raportteja, ja/tai voit olla joku, joka *kuluttaa* eli käyttää raportteja.

![raporttisivu](./media/end-user-reports/reportview.png)

Tässä raportissa on kolme sivua (tai välilehteä), ja tarkastelemme parhaillaan Myymälöiden myynnin yleiskatsaus -sivua. Tällä sivulla on kuusi erilaista visualisointia ja sivun otsikko. Visualisoinnit voidaan *kiinnittää* koontinäyttöihin ja, kun kyseinen kiinnitetty visualisointi valitaan, se avaa raportin, josta se kiinnitettiin.

Jos olet uusi Power BI:n käyttäjä, saat hyvän pohjan sen käyttöön lukemalla [Power BI:n peruskäsitteet](end-user-basic-concepts.md).

Raportit ovat Power BI -palvelun ja Power BI Desktopin ominaisuus. Raporttien käyttö on lähes samanlaista. Mobiilissa et kuitenkaan voi luoda raportteja mutta voit [tarkastella raportteja, jakaa niitä ja lisätä niihin huomautuksia](mobile/mobile-reports-in-the-mobile-apps.md).

## <a name="advantages-of-reports"></a>Raporttien edut
Raportit perustuvat yhteen tietojoukkoon. Jokainen raportin visualisointi edustaa tiedonjyvää. Visualisoinnit eivät ole staattisia. Voit lisätä ja poistaa tietoja, muuttaa visualisointityyppejä ja lisätä suodattimia ja osittajia, kun pureudut tietoihin ja etsit merkityksellisiä tietoja ja haet vastauksia. Kuten koontinäyttö, raportti on vuorovaikutteinen ja mukautettava, ja visualisoinnit päivittyvät sitä mukaa, kun sen pohjana olevat tiedot muuttuvat.

## <a name="dashboards-versus-reports"></a>Koontinäytöt vs. raportit
[Koontinäytöt](end-user-dashboards.md) sekoitetaan usein raportteihin, koska nekin ovat pohjia, jotka ovat täynnä visualisointeja. Niiden välillä on kuitenkin merkittäviä eroja.  

| **Ominaisuus** | **Koontinäytöt** | **Raportit** |
| --- | --- | --- |
| Sivut |Yksi sivu |Yksi tai useampi sivu |
| Tietolähteet |Yksi tai useampi raportti ja yksi tai useampi tietojoukko koontinäyttöä kohden |Yksi tietojoukko raporttia kohden |
| Käytettävissä Power BI Desktopissa |Ei |Kyllä, voit luoda ja tarkastella raportteja Desktopissa |
| Kiinnittäminen |Voit kiinnittää olemassa olevia visualisointeja (ruutuja) vain nykyisestä koontinäytöstä muihin koontinäyttöihisi |Voit kiinnittää visualisointeja (ruutuina) mihin tahansa koontinäyttöösi. Voit kiinnittää kokonaisia raporttisivuja mihin tahansa koontinäyttöösi. |
| Tilaa |Koontinäyttöä ei voi tilata |Raporttisivuja voi tilata |
| Suodatus |Ei voi suodattaa tai jakaa sektoreihin |Monta eri tapaa suodattaa, korostaa ja jakaa sektoreihin |
| Hälytysten asettaminen |Voit luoda hälytyksiä lähetettäväksi sähköpostina, kun tietyt ehdot täyttyvät |Ei |
| Ominaisuus |Voit määrittää jonkin koontinäytön ”esittelyssä” olevaksi koontinäytöksi |Esittelyssä olevaa raporttia ei voida luoda |
| Kyselyt luonnollisella kielellä |Käytettävissä koontinäytöltä |Ei ole käytettävissä raporteista |
| Visualisointityyppiä voidaan muuttaa |Ei. Itse asiassa, jos raportin omistaja muuttaa raportin visualisointityyppiä, koontinäyttöön kiinnitetty visualisointi ei päivity |Kyllä |
| Pohjana olevat tietojoukkojen taulukot ja kentät ovat näkyvissä |Ei. Voit viedä tietoja, mutta etänäe taulukoita ja kenttiä itse koontinäytössä. |Kyllä. Tietojoukon taulukot ja kentät ja arvot ovat näkyvissä. |
| Uusia visualisointeja voidaan luoda |Rajoitettu pienoissovellusten lisäämiseen koontinäyttöön käyttämällä ”Lisää ruutu” -toimintoa |Voidaan luoda monia erityyppisiä visualisointeja, lisätä mukautettuja visualisointeja, muokata visualisointeja ja paljon muuta Muokkausoikeuksilla |
| Mukauttaminen |Voidaan tehdä eri asioita visualisoinneille (ruuduille), kuten siirtää ja järjestellä, muuttaa kokoa, lisätä linkkejä, nimetä uudelleen ja näyttää koko näytön kokoisena. Tiedot ja visualisoinnit itse ovat vain luku -tilassa. |Lukunäkymässä voidaan julkaista, upottaa, suodattaa, viedä, ladata .pbix-tiedostona, katsella liittyvää sisältöä, luoda QR-koodeja, analysoida Excelissä ja paljon muuta.  Muokkausnäkymässä voidaan tehdä kaikki edellä mainittu ja vielä sitäkin enemmän. |

## <a name="report-creators-and-report-consumers"></a>Raportin ***laatijat*** ja raportin ***kuluttajat***
Roolistasi riippuen saatat olla henkilö, joka luo raportteja omaan käyttöönsä tai jakaa niitä työtovereidensa kanssa. Haluat oppia, miten raportteja luodaan ja jaetaan. Tai voit olla henkilö, joka saa raportteja muilta. Haluat oppia ymmärtämään ja käyttämään raportteja.

Tässä on joitakin aiheita esiteltyinä roolin mukaan, joiden avulla pääset alkuun.

### <a name="if-you-will-be-creating-and-sharing-reports"></a>Jos aiot luoda ja jakaa raportteja
* Aloita [Power BI -palvelun esittelyllä](end-user-basic-concepts.md) niin tiedät, mistä raportit ja raporttityökalut löytyvät.
* Aloita [raporttieditorin](../service-the-report-editor-take-a-tour.md) esittely.
* Lisätietoja [raportin luomisesta tietojoukosta](../service-report-create-new.md).
* [Opi käyttämään visualisointi-, sivu- ja raporttitason suodattimia](end-user-report-filter.md)
* Tutustu eri tapoihin, joilla voit [jakaa raportin työtovereidesi kanssa](../service-share-dashboards.md).

### <a name="if-you-will-be-receiving-and-consuming-reports"></a>Jos aiot vastaanottaa ja käyttää raportteja
* Aloita [Power BI -palvelun esittelyllä](end-user-basic-concepts.md) niin tiedät, mistä raportit ja raporttityökalut löytyvät.
* Opi [avaamaan raportti](end-user-report-open.md) ja tutustu kaikkeen [lukunäkymässä](end-user-reading-view.md) käytettävissä olevaan vuorovaikutukseen.
* Tutustu raportteihin paremmin tutustumalla johonkin [malleistamme](../sample-tutorial-connect-to-the-samples.md).  
<!--* Don't need the report any more? You can [remove it](../service-delete.md).-->
* Katso, mitä tietojoukkoa raportissa käytetään ja missä koontinäytöissä on raportista kiinnitettyjä ruutuja, [tarkastelemalla asiaan liittyvää sisältöä](end-user-related.md).

> [!TIP]
> Jos et löytänyt etsimääsi täältä, selaa kaikkia *raportteihin* liittyviä aiheita vasemmalla olevan sisällysluettelon avulla.
> 
> 

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](../power-bi-overview.md) 

[Power BI:n peruskäsitteet](end-user-basic-concepts.md)

