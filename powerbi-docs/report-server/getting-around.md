---
title: Sisällön hallinta Power BI -raporttipalvelimen verkkoportaalissa
description: Tutustu sisällön hallintaan Power BI -raporttipalvelimen verkkoportaalissa.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/24/2018
ms.author: maggies
ms.openlocfilehash: ecc33c6176214cb8178e55d716294bf9446a7b1d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "73859473"
---
# <a name="manage-content-in-the-web-portal"></a>Hallitse sisältöä verkkoportaalissa 
Power BI -raporttipalvelimen verkkoportaalissa voi tarkastella, tallentaa ja hallita paikallisia Power BI- ja mobiiliraportteja sekä sivutettuja raportteja ja suorituskykyilmaisimia.

![Raporttipalvelimen verkkoportaali](media/getting-around/report-server-web-portal.png)

Voit käyttää verkkoportaalia millä tahansa modernilla selaimella. Raportit ja suorituskykyilmaisimet on järjestetty kansioihin verkkoportaalissa, ja voit merkitä niitä suosikeiksi. Voit tallentaa sinne myös Excel-työkirjoja. Verkkoportaalista voit käynnistää raporttien luomiseen tarvitsemasi työkalut:

* Power BI Desktopissa luodut **Power BI -raportit**: voit tarkastella niitä verkkoportaalissa ja Power BI -mobiilisovelluksissa.
* Raportin muodostimessa luodut **sivutetut raportit**: modernit, kiinteästi asetellut asiakirjat, jotka on optimoitu tulostamista varten.
* Suoraan verkkoportaalissa luodut **suorituskykyilmaisimet**.

Voit selata verkkoportaalissa raporttipalvelimen kansioita tai etsiä tiettyä raporttia. Voit tarkastella raporttia, sen yleisiä ominaisuuksia ja sen aiempia kopioita, jotka on tallennettu raporttihistoriaan. Käyttöoikeuksistasi riippuen sinulla voi myös olla mahdollisuus tilata raportteja, jotka toimitetaan sähköpostisi Saapuneet-kansioon tai tiedostojärjestelmän jaettuun kansioon.

## <a name="web-portal-roles-and-permissions"></a>Verkkoportaalin roolit ja käyttöoikeudet
Verkkoportaalisovellus toimii selaimessa. Kun käynnistät verkkoportaalin, näkemäsi sivut, linkit ja vaihtoehdot vaihtelevat raporttipalvelimessa sinulle määritettyjen käyttöoikeuksien mukaan. Jos sinulle on määritetty täydet käyttöoikeudet, pääset käyttämään kaikkia raporttipalvelimen hallinnan sovellusvalikoita ja sivuja. Jos sinulle on määritetty raporttien tarkastelu- ja suorittamisoikeudet, näet vain näihin toimintoihin tarvittavat valikot ja sivut. Sinulla voi olla erilaisia roolimäärityksiä eri raporttipalvelimissa tai jopa yhden raporttipalvelimen eri raporteissa ja kansioissa.

## <a name="start-the-web-portal"></a>Käynnistä verkkoportaali
1. Avaa selain.
   
    Katso luettelo [tuetuista selaimista ja versioista](browser-support.md).
2. Kirjoita verkkoportaalin URL-osoite osoiteriville.
   
    URL-osoite on oletusarvoisesti <em>http://[TietokoneenNimi]/reports</em>.
   
    Raporttipalvelin on ehkä määritetty käyttämään tiettyä porttia. Esimerkiksi <em>http://[TietokoneenNimi]:80/reports</em> tai <em>http://[TietokoneenNimi]:8080/reports</em>
   
    Näet, että verkkoportaali ryhmittelee kohteet seuraaviin luokkiin:
   
   * Suorituskykyilmaisimet
   * Mobiiliraportit
   * Sivutetut raportit
   * Power BI Desktop -raportit
   * Excel-työkirjat
   * tietojoukot
   * Tietolähteet
   * Resurssit

## <a name="manage-items-in-the-web-portal"></a>Hallitse kohteita verkkoportaalissa
Power BI -raporttipalvelimen avulla voit hallita verkkoportaaliin tallentamiasi kohteita yksityiskohtaisesti. Voit esimerkiksi määrittää yksittäisten sivutettujen raporttien tilaukset, tallentamisen välimuistiin, tilannevedokset ja suojauksen.

1. Valitse kohteen oikeassa yläkulmassa **Enemmän vaihtoehtoja**  (...) ja valitse sitten **Hallitse**.
   
    ![Valitse Hallitse](media/getting-around/report-server-web-portal-manage-ellipsis.png)
2. Valitse ominaisuus, jonka haluat määrittää.
   
    ![Valitse ominaisuus](media/getting-around/report-server-web-portal-manage-properties.png)
3. Valitse **Käytä**.

Lue lisää [tilausten käsittelemisestä verkkoportaalissa](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal).

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI -raporttipalvelin?](get-started.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

