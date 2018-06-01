---
title: Tietojen luokittelu Power BI Desktopissa
description: Tietojen luokittelu Power BI Desktopissa
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: cc66655e49860160b43afa5d1acb688c37468212
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2018
ms.locfileid: "30976952"
---
# <a name="data-categorization-in-power-bi-desktop"></a>Tietojen luokittelu Power BI Desktopissa
**Power BI Desktopissa** voit määrittää sarakkeen tietoluokan, jolloin Power BI Desktop tietää, miten sen on käsiteltävä kyseisen sarakkeen arvoja visualisoinnissa.

Kun Power BI Desktop tuo tietoa, se ei ainoastaan nouda itse tietoa, vaan lisäksi se noutaa tietoja, kuten taulukon ja sarakkeiden nimet, onko kyseessä perusavain jne.  Näillä tiedoilla Power BI Desktop tekee joitakin oletuksia siitä, miten se voi antaa sinulle hyvän oletuskokemuksen visualisointia luodessaan. 

Esimerkiksi: kun Power BI Desktop havaitsee, että sarakkeessa on numeerisia arvoja, haluat luultavasti koostaa sen jotenkin, joten se sijoitetaan Arvot-alueelle. Tai jos sarakkeessa on päivämäärä-aika-arvoja, oletuksena on, että käytät sitä luultavasti aikahierarkia-akselina viivakaaviossa.

On kuitenkin joitakin haastavampia tapauksia, esimerkiksi maantiede. Tarkastele seuraavaa Excel-laskentataulukon taulukkoa:

![](media/desktop-data-categorization/datacategorizationtable.png)

Pitäisikö Power BI Desktopin käsitellä GeoCode-sarakkeen koodeja maalyhenteinä vai Yhdysvaltojen osavaltioiden lyhenteinä?  Se ei ole selvää, koska tällainen koodi voi tarkoittaa kumpaa tahansa.  Esimerkiksi AL voi tarkoittaa Alabamaa tai Albaniaa, AR voi tarkoittaa Arkansasia tai Argentiinaa tai CA voi tarkoittaa Kalifornia tai Kanadaa. Tällä on merkitystä, kun aletaan siirtää GeoCode-kenttää kartalle.  Pitäisikö Power BI Desktopin näyttää kuvaa maailmasta tietyt maat korostettuina vai kuvaa Pohjois-Amerikasta tietyt osavaltiot korostettuina?  Voit määrittää tietoluokan juuri tällaisille tiedoille. Tietojen luokittelulla tarkennetaan edelleen tietoja, joita Power BI Desktop voi käyttää parhaiden mahdollisten visualisointien tarjoamiseksi.  

**Tietoluokan määrittäminen**

1. Valitse raporttinäkymässä tai tietonäkymässä olevasta **Kentät**-luettelosta kenttä, jonka haluat lajiteltavan eri luokittelun mukaan.
2. Napsauta valintanauhan **Mallinnus**-välilehdessä avattavaa luetteloa **Tietoluokka:**.  Tämä näyttää luettelon mahdollisista tietoluokista, jotka voit sarakkeellesi valita.  Jotkut valinnat voi olla poistettu käytöstä, jos ne eivät toimi sarakkeesi tämänhetkisen tietotyypin kanssa.  Esimerkiksi jos sarake on binaarista tietotyyppiä, Power BI Desktop ei anna sinun valita maantieteellisten tietojen luokkia. 

![](media/desktop-data-categorization/datacategorization.gif)

Siinä kaikki!  Toiminta, joka tavallisesti kertyy visualisointiin, toimii nyt automaattisesti.  

Saatat olla myös kiinnostunut oppimaan aiheesta [maantieteellinen suodatus Power BI -mobiilisovelluksissa](desktop-mobile-geofiltering.md).

