---
title: Mikä on Power BI -koontinäyttö?
description: Koontinäyttö on yksi Power BI -palvelun tärkeistä ominaisuuksista.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: d0e1fdc79ae4bcd5946d82f2cbf7b929a47372cb
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2018
ms.locfileid: "37136797"
---
# <a name="dashboards-in-power-bi-service"></a>Koontinäytöt Power BI -palvelussa

Power BI ***-koontinäyttö*** on yksi sivu, jota kutsutaan usein pohjaksi, jossa käytetään visualisointeja tarinan kertomiseksi. Koska se on rajoitettu vain yhteen sivuun, hyvin suunniteltu koontinäyttö sisältää vain tarinan tärkeimmät elementit.

![koontinäyttö](media/service-dashboards/power-bi-dashboard2.png)

Koontinäytössä näkyviä visualisointeja kutsutaan *ruuduiksi* ja ne *kiinnitetään* koontinäyttöön raporteista. Jos olet uusi Power BI:n käyttäjä, saat hyvän pohjan sen käyttöön lukemalla [Power BI:n peruskäsitteet](service-basic-concepts.md).

> [!NOTE]
> Koontinäytöt ovat Power BI -palvelun ominaisuus eivätkä ne ole käytettävissä Power BI Desktopissa. Koontinäyttöjä ei voi luoda mobiililaitteissa, mutta niitä voidaan [tarkastella ja jakaa](mobile-apps-view-dashboard.md).
> 
> 

Koontinäytön visualisoinnit ovat peräisin raporteista ja kukin raportti perustuu yhteen tietojoukkoon. Itse asiassa koontinäyttöä voidaan ajatella eteisenä, josta pääsee pohjana oleviin raportteihin ja tietojoukkoihin. Valitsemalla visualisoinnin valitseminen pääset raporttiin (ja tietojoukkoon), jota käytettiin sen luomiseen.

![kaavio, jossa näkyy koontinäyttöjen, raporttien ja tietojoukkojen välinen suhde](media/service-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>Koontinäyttöjen edut
Koontinäytöt tarjoavat erinomaisen tavan liiketoiminnan tarkkailuun, vastausten etsimiseen ja tärkeimpien tietojesi näkemiseen yhdellä silmäyksellä. Koontinäytöillä olevat visualisoinnit saattavat olla peräisin yhdestä tai useammasta tietojoukosta sekä yhdestä tai useammasta pohjana olevasta raportista. Koontinäyttö yhdistää paikalliset ja pilvipalvelussa olevat tiedot, tarjoten yhdistetyn näkymän riippumatta siitä, missä tiedot todella sijaitsevat.

Koontinäyttö ei ole vain nätti kuva, vaan se on erittäin vuorovaikutuskykyinen ja laajalti mukautettava, ja sen ruudut päivittyvät sitä mukaa, kun sen pohjana olevat tiedot muuttuvat.

## <a name="dashboards-versus-reports"></a>Koontinäytöt vs. raportit
[Raportit](service-reports.md) sekoitetaan usein koontinäyttöihin, koska nekin ovat pohjia, jotka ovat täynnä visualisointeja. Niiden välillä on kuitenkin merkittäviä eroja.

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

### <a name="if-you-will-be-creating-and-sharing-dashboards"></a>Jos aiot luoda ja jakaa koontinäyttöjä
* Käytä jotain malleistamme [koontinäytön luomiseksi raportista](service-dashboard-create.md).
* Lue lisätietoja [koontinäytön ruuduista](service-dashboard-tiles.md) ja eri tavoista niiden kiinnittämiseksi koontinäyttöön.
* Auta koontinäytön kuluttajia luomalla koontinäyttöjä, jotka [toimivat hyvin luonnollisella kielellä tehtyjen kysymysten kanssa](service-prepare-data-for-q-and-a.md) ja joista saa [nopeasti tietoja](service-insights-optimize.md).
* Tutustu eri tapoihin, joilla voit [jakaa koontinäytön työtovereidesi kanssa](service-how-to-collaborate-distribute-dashboards-reports.md).

### <a name="if-you-will-be-receiving-and-consuming-dashboards"></a>Jos aiot vastaanottaa ja katsella koontinäyttöjä
* Tutustu koontinäyttöihin paremmin tutustumalla johonkin [mallikoontinäytöistämme](sample-tutorial-connect-to-the-samples.md).
* Lue lisätietoja [koontinäytön ruuduista](service-dashboard-tiles.md) ja siitä, mitä tapahtuu, kun valitset sellaisen.
* Etkö pidä koontinäytön ulkoasusta?  Voit [ muuttaa ruutujen kokoa, siirtää ja nimetä ne uudelleen](service-dashboard-edit-tile.md).
* Haluatko seurata yksittäistä koontinäytön ruutua ja saada sähköpostiviestin, kun se saavuttaa tietyn raja-arvon? [Luo hälytyksiä ruuduista](service-set-data-alerts.md).
* Pidä hauskaa ja esitä kysymyksiä koontinäytöistä. Opettele käyttämään [Power BI:n kysymyksiä ja vastauksia](power-bi-tutorial-q-and-a.md) -toimintoa kysymyksen esittämiseksi tietojasi koskien, jolloin saat vastauksen visualisoinnin muodossa.

> [!TIP]
> Jos et löytänyt etsimääsi täältä, käytä vasemmalla olevaa sisällysluetteloa.
> 
> 

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)  
[Power BI:n peruskäsitteet](service-basic-concepts.md)  
[Power BI Premium – mikä se on?](service-premium.md)  

Ilmenikö muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

