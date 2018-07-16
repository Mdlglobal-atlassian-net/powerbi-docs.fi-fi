---
title: Tietojen tarkastelu offline-tilassa Power BI -mobiilisovelluksissa
description: 'Lue tietoja siitä, miksi tietoja kannattaa tarkastella Power BI -mobiilisovelluksessa mobiiliselaimen sijaan: voit tarkastella tietojasi myös silloin, kun et ole yhteydessä verkkoon.'
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/27/2018
ms.author: maggies
ms.openlocfilehash: cade8b126742610814f47587c950458796cca474
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2018
ms.locfileid: "37136475"
---
# <a name="view-your-data-offline-in-the-power-bi-mobile-apps"></a>Tietojen tarkastelu offline-tilassa Power BI -mobiilisovelluksissa
Koskee seuraavia:

| ![iPhone](media/mobile-apps-offline-data/iphone-logo-50-px.png) | ![iPad](media/mobile-apps-offline-data/ipad-logo-50-px.png) | ![Android-puhelin](media/mobile-apps-offline-data/android-phone-logo-50-px.png) | ![Android-tabletti](media/mobile-apps-offline-data/android-tablet-logo-50-px.png) | ![Windows 10](media/mobile-apps-offline-data/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |Windows 10 -laitteet |

Yksi etu tietojen tarkastelemisessa Power BI -mobiilisovelluksessa mobiiliselaimen sijaan on, että voit tarkastella tietojasi myös silloin, kun et ole yhteydessä verkkoon. 

![Ei verkkoa -sanoma](media/mobile-apps-offline-data/power-bi-iphone-no-network.png)

Oletusarvon mukaan Power BI päivittää tiedot usein, jotta saat ajan tasalla olevia vastauksia yrityksesi kysymyksiin milloin tahansa, vaikka olisit matkalla tai vieraan verkon piirissä.

## <a name="data-access-while-youre-offline"></a>Tietojen käyttö offline-tilassa
Kun olet offline-tilassa, voit käyttää ja käsitellä koontinäyttöjä, joita olet käyttänyt aiemmin mobiilisovelluksessa.

Sinulla on myös vain luku -oikeudet Power BI -raportteihin, joita olet käyttänyt aiemmin mobiilisovelluksessa. Voit nähdä koko raportin, mutta et voi suodattaa, ristiinsuodattaa tai lajitella sitä taikka käyttää siihen osittajia.

## <a name="background-data-refresh"></a>Taustatietojen päivitys
Taustapäivitys päivittää suosikkeihin lisäämäsi koontinäytöt sekä koontinäytöt ja raportit, joita olet tarkastellut edellisten kahden viikon aikana, Power BI -palvelussa olevilla tiedoilla (ei tietolähteen tiedoilla). Jos olet yhteydessä Wi-Fi-verkkoon, taustapäivitys päivittyy 2 tunnin välein. Jos olet 3G-verkossa, Power BI päivittää sisällön 24 tunnin välein.

Voit poistaa taustapäivityksen käytöstä esimerkiksi verkon käytön välttämiseksi. Tarkista laitteesi asetukset.

> [!NOTE]
> Jos käytät Power BI -mobiilisovellusta iOS-laitteessa ja organisaatiosi on määrittänyt Microsoft Intunen mobiilisovellusten hallinnan, tietojen päivittäminen taustalla on poistettu käytöstä. Kun avaat sovelluksen seuraavan kerran, Power BI päivittää tiedot verkossa olevasta Power BI -palvelusta.
> 
> Lue lisää [Power BI -mobiilisovellusten päivittämisestä Microsoft Intunella](service-admin-mobile-intune.md). 
> 
> 

## <a name="offline-indicators"></a>Offline-ilmaisimet
Power BI tarjoaa selvät ilmaisimet, kun siirryt offline-tilaan ja takaisin online-tilaan. Lisäksi ohjelmassa on ilmaisimet puuttuville koontinäytöille, raporteille ja ruuduille, jotka eivät ole käytettävissä offline-tilassa.

## <a name="limitations"></a>Rajoitukset
Kun olet offline-tilassa ja Power BI on mobiililaitteessasi, saatat kohdata näitä rajoituksia:

* Power BI voi tallentaa välimuistiin enintään 250 megatavua tietoa offline-tilassa.
* Tietyt ruututyypit edellyttävät, että käytössä on aktiivinen palvelinyhteys, joten ne eivät ole käytettävissä offline-tilassa. Tällaisia ovat esimerkiksi Bing-karttaruudut ja tietyt mukautetut ruudut.
* Power BI:ssä olevat koko Excel-työkirjat eivät ole käytettävissä offline-tilassa.
* Näet Reporting Services -mobiiliraportit ja -suorituskykyilmaisimet offline-tilassa, jos olet tarkastellut niitä online-tilassa. Ne eivät päivity taustalla. Ne päivittyvät aina, kun avaat ne.
* Et näe Power BI -mobiilisovelluksissa Power BI Desktop (.pbix) -tiedostoja, jotka on tallennettu Power BI -raporttipalvelimelle. 

## <a name="next-steps"></a>Seuraavat vaiheet
Palaute auttaa meitä päättämään, mitä toimintoja otamme käyttöön tulevaisuudessa, joten muista äänestää muita ominaisuuksia, jotka haluaisit nähdä Power BI ‑mobiilisovelluksissa. 

* [Power BI -sovellukset mobiililaitteille](mobile-apps-for-mobile-devices.md)
* Seuraa käyttäjää @MSPowerBI Twitterissä
* Liity keskusteluun [Power BI -yhteisössä](http://community.powerbi.com/)
* [Mikä on Power BI?](power-bi-overview.md)

