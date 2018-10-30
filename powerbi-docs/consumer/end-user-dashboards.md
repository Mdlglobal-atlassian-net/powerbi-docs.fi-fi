---
title: Mikä on koontinäyttö Power BI -palvelun kuluttajille?
description: Koontinäyttö on yksi Power BI -palvelun tärkeistä ominaisuuksista.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 840f302b1df31736d7fcd1c0766c34963a2f6738
ms.sourcegitcommit: 2c4a075fe16ccac8e25f7ca0b40d404eacb49f6d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/20/2018
ms.locfileid: "49473921"
---
# <a name="dashboards-for-power-bi-service-consumers"></a>Koontinäytöt Power BI -palvelun kuluttajille

Power BI ***-koontinäyttö*** on yksi sivu, jota kutsutaan usein pohjaksi, jossa käytetään visualisointeja tarinan kertomiseksi. Koska se on rajoitettu vain yhteen sivuun, hyvin suunniteltu koontinäyttö sisältää vain tarinan tärkeimmät elementit.

![koontinäyttö](media/end-user-dashboards/power-bi-dashboard2.png)

Koontinäytössä näkyviä visualisointeja kutsutaan *ruuduiksi* ja ne *kiinnitetään* koontinäyttöön raporteista. Jos olet uusi Power BI:n käyttäjä, saat hyvän pohjan sen käyttöön lukemalla [Power BI:n peruskäsitteet](end-user-basic-concepts.md).

> [!NOTE]
> Koontinäytöt ovat Power BI -palvelun ominaisuus eivätkä ne ole käytettävissä Power BI Desktopissa. Koontinäyttöjä ei voi luoda mobiililaitteissa, mutta niitä voidaan [tarkastella ja jakaa](/mobile/mobile-apps-view-dashboard.md).
> 
> 

Koontinäytön visualisoinnit ovat peräisin raporteista ja kukin raportti perustuu yhteen tietojoukkoon. Itse asiassa koontinäyttöä voidaan ajatella eteisenä, josta pääsee pohjana oleviin raportteihin ja tietojoukkoihin. Valitsemalla visualisoinnin valitseminen pääset raporttiin (ja tietojoukkoon), jota käytettiin sen luomiseen.

![kaavio, jossa näkyy koontinäyttöjen, raporttien ja tietojoukkojen välinen suhde](media/end-user-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>Koontinäyttöjen edut
Koontinäytöt tarjoavat erinomaisen tavan liiketoiminnan tarkkailuun, vastausten etsimiseen ja tärkeimpien tietojesi näkemiseen yhdellä silmäyksellä. Koontinäytöillä olevat visualisoinnit saattavat olla peräisin yhdestä tai useammasta tietojoukosta sekä yhdestä tai useammasta pohjana olevasta raportista. Koontinäyttö yhdistää paikalliset ja pilvipalvelussa olevat tiedot, tarjoten yhdistetyn näkymän riippumatta siitä, missä tiedot todella sijaitsevat.

Koontinäyttö ei ole vain nätti kuva, vaan se on erittäin vuorovaikutuskykyinen ja laajalti mukautettava, ja sen ruudut päivittyvät sitä mukaa, kun sen pohjana olevat tiedot muuttuvat.

## <a name="dashboards-versus-reports"></a>Koontinäytöt vs. raportit
Raportit sekoitetaan usein koontinäyttöihin, koska nekin ovat pohjia, jotka ovat täynnä visualisointeja. Niiden välillä on kuitenkin merkittäviä eroja.

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

## <a name="dashboard-creators-and-dashboard-consumers"></a>Koontinäytön luojat ja koontinäytön kuluttajat
Roolistasi riippuen saatat olla henkilö, joka luo koontinäyttöjä omaan käyttöönsä tai jakaa niitä työtovereidensa kanssa. Haluat oppia, miten koontinäyttöjä luodaan ja jaetaan. Tai voit olla henkilö, joka saa koontinäyttöjä muilta. Haluat oppia ymmärtämään ja käyttämään koontinäyttöä.

Tässä on joitakin aiheita esiteltyinä roolin mukaan, joiden avulla pääset alkuun.

Koontinäytön jakamiseen ja jaetun koontinäytön tarkasteluun vaaditaan Power BI Pro.

### <a name="if-you-will-be-receiving-and-consuming-dashboards"></a>Jos aiot vastaanottaa ja katsella koontinäyttöjä
* Tutustu koontinäyttöihin paremmin tutustumalla johonkin [mallikoontinäytöistämme](../sample-tutorial-connect-to-the-samples.md).
* Lue lisätietoja [koontinäytön ruuduista](end-user-tiles.md) ja siitä, mitä tapahtuu, kun valitset sellaisen.
* Haluatko seurata yksittäistä koontinäytön ruutua ja saada sähköpostiviestin, kun se saavuttaa tietyn raja-arvon? [Luo hälytyksiä ruuduista](end-user-alerts.md).
* Pidä hauskaa ja esitä kysymyksiä koontinäytöistä. Opettele käyttämään [Power BI:n kysymyksiä ja vastauksia](end-user-q-and-a.md) -toimintoa kysymyksen esittämiseksi tietojasi koskien, jolloin saat vastauksen visualisoinnin muodossa.

> [!TIP]
> Jos et löytänyt etsimääsi täältä, käytä vasemmalla olevaa sisällysluetteloa.
> 

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](../power-bi-overview.md)  
[Power BI:n peruskäsitteet](end-user-basic-concepts.md)  