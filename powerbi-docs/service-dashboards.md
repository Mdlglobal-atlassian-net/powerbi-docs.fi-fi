---
title: Johdatus raporttinäkymiin Power BI -kehittäjille
description: Koontinäyttö on yksi Power BI -palvelun tärkeistä ominaisuuksista. Raporttinäkymä on yksittäinen sivu, jossa kerrotaan tarina visualisointien kautta.
author: maggieMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/10/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 61d7bf9f9794545e963ca19c8f983d6d6cfefa54
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61150386"
---
# <a name="intro-to-dashboards-for-power-bi-designers"></a>Johdatus raporttinäkymiin Power BI -kehittäjille

Power BI -***raporttinäkymä*** on yksittäinen sivu, joka kertoo tarinan visualisointien kautta. Koska se on rajattu yhdelle sivulle, hyvin suunniteltu raporttinäkymä sisältää vain tarinan kohokohdat. Lukijat voivat tutustua yksityiskohtiin raporttinäkymään liittyvien raporttien kautta.

![koontinäyttö](media/service-dashboards/power-bi-dashboard2.png)

Raporttinäkymä on Power BI -palvelun ominaisuus. Raporttinäkymät eivät ole käytettävissä Power BI Desktopissa. Raporttinäkymiä ei voi luoda mobiililaitteilla, mutta niitä voi [tarkastella ja jakaa](mobile-apps-view-dashboard.md) niillä.

## <a name="dashboard-basics"></a>Raporttinäkymien perusteet 

Raporttinäkymän visualisointeja kutsutaan *ruuduiksi*. Ruutuja *kiinnitetään* raporttinäkymiin raporteista. Jos olet uusi Power BI:n käyttäjä, saat hyvän pohjan sen käyttöön lukemalla [Power BI:n peruskäsitteet](service-basic-concepts.md).

> [!IMPORTANT]
> Raporttinäkymien luomiseen tarvitaan [Power BI Pro](service-free-vs-pro.md) -käyttöoikeus.

Raporttinäkymän visualisoinnit ovat peräisin raporteista, ja kukin raportti perustuu tietojoukkoon. Itse asiassa raporttinäkymää voidaan ajatella eteisenä, josta pääsee sen pohjana oleviin raportteihin ja tietojoukkoihin. Valitsemalla visualisoinnin pääset sen perustana olevaan raporttiin (ja tietojoukkoon).

![kaavio, jossa näkyy koontinäyttöjen, raporttien ja tietojoukkojen välinen suhde](media/service-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>Koontinäyttöjen edut
Raporttinäkymät tarjoavat erinomaisen tavan liiketoiminnan tarkkailuun ja tärkeimpien tietojesi näkemiseen yhdellä silmäyksellä. Koontinäytöillä olevat visualisoinnit saattavat olla peräisin yhdestä tai useammasta tietojoukosta sekä yhdestä tai useammasta pohjana olevasta raportista. Raporttinäkymä yhdistää paikalliset ja pilvipalvelussa olevat tiedot ja tarjoaa niistä yhdistetyn näkymän riippumatta siitä, missä tiedot todella sijaitsevat.

Raporttinäkymä ei ole pelkkää koreilua. Se on erittäin vuorovaikutuskykyinen, ja sen ruudut päivittyvät sitä mukaa, kun pohjana olevat tiedot muuttuvat.

## <a name="dashboards-versus-reports"></a>Koontinäytöt vs. raportit
[Raportit](service-reports.md) ja raporttinäkymät vaikuttavat samankaltaisilta, koska ne ovat molemmat eräänlaisia pohjia, jotka ovat täynnä visualisointeja. Niissä on kuitenkin merkittäviä eroja.

| **Ominaisuus** | **Koontinäytöt** | **Raportit** |
| --- | --- | --- |
| Sivut |Yksi sivu |Yksi tai useampi sivu |
| Tietolähteet |Yksi tai useampi raportti ja yksi tai useampi tietojoukko koontinäyttöä kohden |Yksi tietojoukko raporttia kohden |
| Käytettävissä Power BI Desktopissa |Ei | Voi luoda ja tarkastella raportteja Power BI Desktopissa |
| Tilaa |Koontinäytön voi tilata |Raporttisivuja voi tilata |
| Suodatus |Ei voi suodattaa tai jakaa sektoreihin |Monta eri tapaa suodattaa, korostaa ja jakaa sektoreihin |
| Esittelyssä |Voit määrittää jonkin koontinäytön ”esittelyssä” olevaksi koontinäytöksi |Esittelyssä olevaa raporttia ei voida luoda |
| Suosikki | Koontinäyttöjä voi merkitä *suosikeiksi* | Raportteja voi merkitä *suosikeiksi*
| Hälytysten asettaminen |Käytettävissä koontinäytön ruuduilta tietyissä tilanteissa |Ei ole käytettävissä raporteista |
| Kyselyt luonnollisella kielellä (Q&A) |Käytettävissä raporttinäkymissä | Käytettävissä raporteissa |
| Pohjana olevat tietojoukkojen taulukot ja kentät ovat näkyvissä |Ei. Voit viedä tietoja, mutta etänäe taulukoita ja kenttiä itse koontinäytössä. |Kyllä. Tietojoukon taulukot ja kentät ja arvot ovat näkyvissä. |


## <a name="next-steps"></a>Seuraavat vaiheet
* Tutustu koontinäyttöihin paremmin tutustumalla johonkin [mallikoontinäytöistämme](sample-tutorial-connect-to-the-samples.md).
* Lue lisää [raporttinäkymien ruuduista](service-dashboard-tiles.md).
* Haluatko seurata yksittäistä koontinäytön ruutua ja saada sähköpostiviestin, kun se saavuttaa tietyn raja-arvon? [Luo hälytyksiä ruuduista](service-set-data-alerts.md).
* Opettele käyttämään [Power BI:n kysymyksiä ja vastauksia](power-bi-tutorial-q-and-a.md) -toimintoa kysymyksen esittämiseksi tietojasi koskien, jolloin saat vastauksen visualisoinnin muodossa.
