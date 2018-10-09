---
title: Mikä on koontinäyttö Power BI -palvelun kuluttajille?
description: Koontinäyttö on yksi Power BI -palvelun tärkeistä ominaisuuksista.
author: maggieMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/02/2018
ms.author: maggie
LocalizationGroup: Dashboards
ms.openlocfilehash: 2e71f3a1efe60094b9a714e1d03b891aa9da99a6
ms.sourcegitcommit: 07beb155ec0ea1cdcc741085251ed06d7bc8581c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/09/2018
ms.locfileid: "48875007"
---
# <a name="dashboards-in-power-bi-service"></a>Koontinäytöt Power BI -palvelussa

Power BI ***-koontinäyttö*** on yksi sivu, jota kutsutaan usein pohjaksi, jossa käytetään visualisointeja tarinan kertomiseksi. Koska se on rajoitettu vain yhteen sivuun, hyvin suunniteltu koontinäyttö sisältää vain tarinan tärkeimmät elementit.

![koontinäyttö](media/service-dashboards/power-bi-dashboard2.png)

Koontinäytöt ovat Power BI -palvelun ominaisuus eivätkä ne ole käytettävissä Power BI Desktopissa. Koontinäyttöjä ei voi luoda mobiililaitteissa, mutta niitä voidaan [tarkastella ja jakaa](mobile-apps-view-dashboard.md).

## <a name="dashboard-creators-and-dashboard-consumers"></a>Koontinäytön luojat ja koontinäytön kuluttajat
Roolistasi riippuen saatat olla henkilö, joka luo koontinäyttöjä omaan käyttöönsä tai jakaa niitä työtovereidensa kanssa. Sinulle sopivia tietoja löytyy kohdasta **Koontinäytöt luojille**. Jos olet henkilö, joka saa koontinäyttöjä muilta. Haluat oppia ymmärtämään ja käyttämään koontinäyttöä. Tämä artikkeli sopii sinulle!


### <a name="if-you-will-be-receiving-and-consuming-dashboards"></a>Jos aiot vastaanottaa ja katsella koontinäyttöjä

Koontinäytössä näkyviä visualisointeja kutsutaan *ruuduiksi* ja koontinäytön *luojat* *kiinnittävät* ne koontinäyttöön raporteista. Jos olet uusi Power BI:n käyttäjä, saat hyvän pohjan sen käyttöön lukemalla [Power BI:n peruskäsitteet](service-basic-concepts.md).

> [!IMPORTANT]
> Jaetun koontinäytön tarkasteluun vaaditaan [Power BI Pro](service-free-vs-pro.md).

Koontinäytön visualisoinnit ovat peräisin raporteista ja kukin raportti perustuu yhteen tietojoukkoon. Itse asiassa koontinäyttöä voidaan ajatella eteisenä, josta pääsee pohjana oleviin raportteihin ja tietojoukkoihin. Valitsemalla visualisoinnin valitseminen pääset raporttiin (ja tietojoukkoon), jota käytettiin sen luomiseen.

![kaavio, jossa näkyy koontinäyttöjen, raporttien ja tietojoukkojen välinen suhde](media/service-dashboards/power-bi-diagram.png)



## <a name="advantages-of-dashboards"></a>Koontinäyttöjen edut
Koontinäytöt tarjoavat erinomaisen tavan liiketoiminnan tarkkailuun, vastausten etsimiseen ja tärkeimpien tietojesi näkemiseen yhdellä silmäyksellä. Koontinäytöillä olevat visualisoinnit saattavat olla peräisin yhdestä tai useammasta tietojoukosta sekä yhdestä tai useammasta pohjana olevasta raportista. Koontinäyttö yhdistää paikalliset ja pilvipalvelussa olevat tiedot, tarjoten yhdistetyn näkymän riippumatta siitä, missä tiedot todella sijaitsevat.

Koontinäyttö ei ole vain nätti kuva, vaan se on erittäin vuorovaikutuskykyinen ja sen ruudut päivittyvät sitä mukaa, kun sen pohjana olevat tiedot muuttuvat.

## <a name="dashboards-versus-reports"></a>Koontinäytöt vs. raportit
[Raportit](service-reports.md) sekoitetaan usein koontinäyttöihin, koska nekin ovat pohjia, jotka ovat täynnä visualisointeja. Niiden välillä on kuitenkin merkittäviä eroja Power BI -asiakkaille.

| **Ominaisuus** | **Koontinäytöt** | **Raportit** |
| --- | --- | --- |
| Sivut |Yksi sivu |Yksi tai useampi sivu |
| Tietolähteet |Yksi tai useampi raportti ja yksi tai useampi tietojoukko koontinäyttöä kohden |Yksi tietojoukko raporttia kohden |
| Käytettävissä Power BI Desktopissa |Ei |Kyllä, ***luojat*** voivat luoda ja tarkastella raportteja Desktopissa |
| Tilaa |Koontinäytön voi tilata |Raporttisivuja voi tilata |
| Suodatus |Ei voi suodattaa tai jakaa sektoreihin |Monta eri tapaa suodattaa, korostaa ja jakaa sektoreihin |
| Esittelyssä |Voit määrittää jonkin koontinäytön ”esittelyssä” olevaksi koontinäytöksi |Esittelyssä olevaa raporttia ei voida luoda |
| Suosikki | Koontinäyttöjä voi merkitä *suosikeiksi* | Raportteja voi merkitä *suosikeiksi*
| Hälytysten asettaminen |Käytettävissä koontinäytön ruuduilta tietyissä tilanteissa |Ei ole käytettävissä raporteista |
| Kyselyt luonnollisella kielellä |Käytettävissä koontinäytöltä |Ei ole käytettävissä raporteista |
| Pohjana olevat tietojoukkojen taulukot ja kentät ovat näkyvissä |Ei. Voit viedä tietoja, mutta etänäe taulukoita ja kenttiä itse koontinäytössä. |Kyllä. Tietojoukon taulukot ja kentät ja arvot ovat näkyvissä. |
| Mukauttaminen |Ei |Lukunäkymässä voidaan julkaista, upottaa, suodattaa, viedä, ladata .pbix-tiedostona, katsella liittyvää sisältöä, luoda QR-koodeja, analysoida Excelissä ja paljon muuta.  |

## <a name="next-steps"></a>Seuraavat vaiheet
* Tutustu koontinäyttöihin paremmin tutustumalla johonkin [mallikoontinäytöistämme](sample-tutorial-connect-to-the-samples.md).
* Lue lisätietoja [koontinäytön ruuduista](service-dashboard-tiles.md) ja siitä, mitä tapahtuu, kun valitset sellaisen.
* Haluatko seurata yksittäistä koontinäytön ruutua ja saada sähköpostiviestin, kun se saavuttaa tietyn raja-arvon? [Luo hälytyksiä ruuduista](service-set-data-alerts.md).
* Pidä hauskaa ja esitä kysymyksiä koontinäytöistä. Opettele käyttämään [Power BI:n kysymyksiä ja vastauksia](power-bi-tutorial-q-and-a.md) -toimintoa kysymyksen esittämiseksi tietojasi koskien, jolloin saat vastauksen visualisoinnin muodossa.
