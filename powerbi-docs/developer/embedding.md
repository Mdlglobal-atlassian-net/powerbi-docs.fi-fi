---
title: Upottaminen Power BI:llä
description: Power BI tarjoaa ohjelmointirajapintoja, jotka mahdollistavat koontinäyttöjen ja raporttien upottamisen sovelluksiin.
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 11/30/17
ms.author: mihart
ms.openlocfilehash: 4d112ae4c25f080a3eb90de596c056366da3fe1d
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
---
# <a name="embedding-with-power-bi"></a>Upottaminen Power BI:llä
Power BI tarjoaa ohjelmointirajapintoja, jotka mahdollistavat koontinäyttöjen ja raporttien upottamisen sovelluksiin. Power BI:n ohjelmointirajapinnat tarjoavat yhtenäisen ominaisuusjoukon ja mahdollistavat uusimpien Power BI -toimintojen, kuten koontinäyttöjen, yhdyskäytävien ja sovellustyötilojen, käytön sisällön upottamisessa.

## <a name="a-single-api"></a>Yksittäinen ohjelmointirajapinta
Power BI-sisällön upottamisessa on kaksi pääskenaariota:  upottaminen organisaation käyttäjien (joilla on Power BI -käyttöoikeudet) käyttöön sekä upottaminen käyttäjille ja asiakkaille, joilta ei edellytetä Power BI-käyttöoikeutta. Power BI REST -ohjelmointirajapinta sallii molemmat skenaariot. 

Niitä asiakkaita ja käyttäjiä varten, joilla ei ole Power BI-käyttöoikeuksia, voit upottaa koontinäyttöjä ja raportteja mukautettuun sovellukseen käyttäen samaa ohjelmointirajapintaa joko organisaatiosi tai asiakkaiden palvelemiseen. Asiakkaasi näkevät tiedot, joita sovellus hallitsee. Power BI-käyttäjät organisaatiossasi voivat lisäksi tarkastella *omia tietojaan* suoraan Power BI:ssä tai upotetun sovelluksen kontekstissa. Voit hyödyntää JavaScriptia ja REST-ohjelmointirajapintoja täysipainoisesti upotustarpeisiisi.

Näyte siitä, kuinka upottaminen toimii, annetaan artikkelissa [JavaScript-upotuksen näyte](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Upottaminen organisaation käyttöön
Upottaminen organisaation käyttöön mahdollistaa Power BI -palvelun laajentamisen. Tämä edellyttää, että sovelluksesi käyttäjät kirjautuvat Power BI -palveluun, kun he haluavat tarkastella sisältöään. Kun käyttäjä organisaatiossasi kirjautuu sisään, hän voi käyttää vain koontinäyttöjä ja raportteja, jotka hän omistaa tai jotka on jaettu hänen kanssaan Power BI -palvelussa. 

*Sisäinen verkkosovellus, SharePoint Onlinen WWW-osa ja Microsoft Teams -integrointi ovat esimerkkejä upottamisesta organisaation käyttöön.*

Organisaation käyttöön upottamisen osalta katso seuraavia ohjeaiheita:

* [Koontinäytön integrointi sovellukseen](integrate-dashboard.md)
* [Ruudun integrointi sovellukseen](integrate-tile.md)
* [Raportin integrointi sovellukseen](integrate-report.md)

Itsepalvelutoiminnot, kuten muun muassa muokkaus ja tallennus, ovat käytettävissä [JavaScript-ohjelmointirajapinnassa](https://github.com/Microsoft/PowerBI-JavaScript), kun käytetään upotusta Power BI -käyttäjien käyttöön.

## <a name="embedding-for-your-customers"></a>Upottaminen asiakkaiden käyttöön
Upottaminen asiakkaiden käyttöön mahdollistaa koontinäyttöjen ja raporttien upottamisen käyttäjille, joilla ei ole Power BI -tiliä. Asiakkaiden ei tarvitse tietää mitään Power BI:stä. Upotetun sovelluksen luomiseen vaaditaan vähintään yksi Power BI Pro -tili. Power BI Pro -tili toimii sovelluksesi päätilinä. Voit ajatella sitä eräänlaisena välityspalvelimen tilinä. Power BI Pro -tilin avulla voit luoda myös upotustunnuksia, jotka mahdollistavat pääsyn sovelluksesi omistamiin/hallitsemiin koontinäyttöihin ja raportteihin Power BI -palvelussa. 

*Muille yrityksille myytävä ISV-sovellus on esimerkki upottamisesta asiakkaiden käyttöön.*

![Asiakkaiden käyttöön upottamisen työnkulku](media/embedding/powerbi-embed-flow.png)

Käytät koontinäyttöjen, raporttien ja ruutujen upottamiseen samoja ohjelmointirajapintoja, joita käyttäisit upottamisessa organisaation käyttöön.

> [!IMPORTANT]
> Vaikka upottaminen on riippuvaista Power BI-palvelusta, asiakkaasi eivät ole riippuvaisia Power BI:stä. Heidän ei tarvitse rekisteröityä Power BI -käyttäjiksi, jotta he voisivat tarkastella upotettua sisältöä sovelluksessasi.
> 
> 

Kun olet valmis siirtymään tuotantoon, sovellustyötilallesi täytyy määrittää tietty kapasiteetti. Microsoft Azureen sisältyvä Power BI Embedded tarjoaa kapasiteettia käyttöön sovellustesi kanssa.

Saat upottamista koskevia yksityiskohtaisia tietoja artikkelista [Power BI:n koontinäyttöjen, raporttien ja ruutujen upottaminen](embedding-content.md).

Jos käytit Power BI Workspace Collections -palvelua Azuressa, katso artikkelista [Sisällön siirtäminen Azuren Power BI Workspace Collections -palvelusta](migrate-from-powerbi-embedded.md) lisätietoja siitä, miten voit siirtää sisältösi.

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n koontinäyttöjen, raporttien ja ruutujen upottaminen](embedding-content.md)  
[Power BI Embedded -työtilan kokoelman sisällön siirtäminen Power BI:hin](migrate-from-powerbi-embedded.md)  
[Power BI Premium – mikä se on?](../service-premium.md)  
[JavaScript API Git -säilö](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git -säilö](https://github.com/Microsoft/PowerBI-CSharp)  
[JavaScript-upotuksen näyte](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Upotetun analytiikan kapasiteetin suunnittelun tekninen raportti](https://aka.ms/pbiewhitepaper)  
[Power BI Premiumin tekninen raportti](https://aka.ms/pbipremiumwhitepaper)  

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)

