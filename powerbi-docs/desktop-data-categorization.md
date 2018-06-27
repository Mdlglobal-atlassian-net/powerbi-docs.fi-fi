---
title: Tietojen luokittelu Power BI Desktopissa
description: Tietojen luokittelu Power BI Desktopissa
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 9fa7310b3d0a20a588b2cc26fc0df177f3d0ab70
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34285412"
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

