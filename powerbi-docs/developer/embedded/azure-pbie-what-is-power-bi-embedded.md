---
title: Mikä on Azure Power BI Embedded ja upotettu analysointi | Microsoft Docs
description: Power BI Embedded on upotetun analysoinnin työkalu. Sen tarkoituksena on yksinkertaistaa sitä, miten riippumattomat ohjelmistotoimittajat ja -kehittäjät käyttävät Power BI -ominaisuuksia auttamalla heitä lisäämään sovelluksiin nopeasti upeita visualisointeja, raportteja ja koontinäyttöjä. Lue, miten käyttää upotetun analysoinnin ohjelmistoa, upotetun analysoinnin työkaluja tai upotetun liiketoimintatiedon hallinnan työkaluja Power BI Embeddin avulla.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: nishalit
ms.service: power-bi-embedded
ms.subservice: ''
ms.devlang: csharp, javascript
ms.topic: overview
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: f04621fdfe7e6055d84fa4d2672c874837ff5ea4
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/05/2020
ms.locfileid: "79495270"
---
# <a name="what-is-power-bi-embedded-in-azure"></a>Mikä on Power BI Embedded Azuressa?

Power BI Embeddedin tarkoituksena on yksinkertaistaa sitä, miten riippumattomat ohjelmistotoimittajat ja -kehittäjät käyttävät Power BI -ominaisuuksia upotetun analysoinnin avulla. Power BI Embedded yksinkertaistaa Power BI -ominaisuuksia auttamalla sinua lisäämään upeita visualisointeja, raportteja ja koontinäyttöjä sovelluksiisi nopeasti. Microsoft Azureen luotujen sovellusten tapaan käytössä on palveluja, kuten koneoppiminen ja IoT. Riippumattomat ohjelmistotoimittajat mahdollistavat asiakkaiden nopeiden ja tietoon perustuvien päätösten tekemisen kontekstissa, sillä tietojen välillä siirtyminen on sovelluksissa helppoa.

> [!VIDEO https://www.youtube.com/embed/iEHfUuoZseo]

Toukokuussa 2017 ilmoitimme Power BI- ja Power BI Embedded -palveluiden konvergenssista. Konvergenssi tuotti yhden ohjelmointirajapinnan, yhtenäisen ominaisuusjoukon ja pääsyn uusimpiin ominaisuuksiin kummassakin palvelussa. Lisäksi otimme käyttöön kapasiteettipohjaisen hinnoittelumallin, joka yksinkertaistaa Power BI:n käyttämistä.

Power BI Embedded on lisännyt joustavuutta sen suhteen, miten itsenäiset ohjelmistotoimittajat ja -kehittäjät voivat upottaa tietoja sovelluksiin käyttämällä Power BI -ohjelmointirajapintoja. Ohjelmistotoimittajat ja -kehittäjät voivat hyödyntää minimoitua kehitystyötä päästääkseen nopeammin markkinoille ja erottautuakseen muista ottamalla sovelluksissaan käyttöön Microsoftin maailmanluokan analysointimoduulin. Samalla tavalla kehittäjät voivat käyttää aikaa keskittyen siihen, että sovellus vastaa asiakkaan tarpeisiin, visuaalisten analysointiominaisuuksien kehittämisen sijaan. Lisäksi Power BI Embeddedin avulla voit käyttää tuttuja kehitysympäristöjä Visual Studiota ja Azurea, joita jo käytät.

Onko käytössäsi sovellus, jossa on upotettua Power BI -sisältöä ja joka käyttää Power BI Premiumia? Jos olet ohjelmistotoimittaja tai -kehittäjä, joka toimittaa sovelluksia, tai organisaatio, joka käyttää niitä, mitään toimia ei tarvita. Sinä ja asiakkaasi voitte jatkaa näiden sovellusten käyttämistä keskeytyksettä. Jos käytössäsi on Power BI -työtilakokoelmiin pohjautuva sovellus ja olet kiinnostunut hyödyntämään konvergoitua ohjelmointirajapintaa ja uusia kapasiteettipohjaisia Azuren varastointiyksiköitä, katso siirtymisohjeet dokumentaatiosta.

## <a name="comparing-power-bi-embedded-with-power-bi-premium"></a>Power BI Embeddedin vertailu Power BI Premiumiin

**Power BI Embedded** on tarkoitettu itsenäisille ohjelmistotoimittajille ja -kehittäjille, jotka luovat sovelluksia asiakkailleen. Sitä voidaan käyttää kolmannen osapuolen liiketoimintatiedon hallintapalveluna, jonka avulla voit visualisoida sovellustietoja sen sijaan, että loisit palvelun itse. Power BI Embedded on ohjelmisto palveluna (SaaS) -tyyppinen analytiikkaratkaisu, jossa kehittäjät voivat upottaa raportteja ja koontinäyttöjä sovellukseen asiakkaitaan varten. **Power BI Premium** on ohjelmisto palveluna (SaaS) -tyyppinen analytiikkaratkaisu, joka mahdollistaa organisaatioille kriittisimpien liiketoimintatietojen tarkastelun yhdessä näkymässä. 

[Power BI Embedded](https://azure.microsoft.com/pricing/details/power-bi-embedded/) on käytön mukaan laskutettava ominaisuus, kun taas [Power BI Premium](https://powerbi.microsoft.com/calculator/) on kuukausimaksullinen. Tällä [videolla](https://www.youtube.com/watch?v=0y2oJikC6Xc&t=0s&list=PLv2BtOtLblH1dQPV49Ni12olDcUoW-GEl&index=3) on lisätietoja niiden ominaisuuksista toisiinsa verrattuna.

## <a name="easy-to-use-tools"></a>Helppokäyttöiset työkalut

Power BI Embeddedin avulla voit keskittyä siihen, minkä osaat parhaiten, eli erinomaisten sovellusten luomiseen. Power BI Embeddedillä hallinta ja kehittäminen onnistuu niillä työkaluilla ja taidoilla, joita sinulla jo on.

* [**Azure-portaali**](https://portal.azure.com/): verkkopohjainen sovellus kaikkien Azure-palveluiden hallintaan
* [**Visual Studio -koodi**](https://code.visualstudio.com/docs): maksuton, ladattava, avoimen lähdekoodin laajennuksia tukeva koodieditori Windows-, macOS- ja Linux-käyttöjärjestelmille
* [**Power BI Desktop**](https://powerbi.microsoft.com/desktop/): maksuton, ladattava työkalu monipuolisten ja vuorovaikutteisten raporttien luomiseen visuaalisella analysoinnilla

REST-ohjelmointirajapinnan avulla Power BI Embedded sallii kehittämisen millä tahansa kielellä.

## <a name="engage-with-the-power-bi-engineering-team"></a>Ole yhteydessä Power BI:n tekniseen tiimiin

* [Yhteisöt](https://community.powerbi.com/): Esitä Power BI -kysymyksiä
* [Power BI -ideoita](https://ideas.powerbi.com): Pyydä ja äänestä ominaisuuksia
* [Reddit](https://www.reddit.com/r/PowerBI/): Keskustele Power BI:stä

## <a name="next-steps"></a>Seuraavat vaiheet

Katso lisätietoja kapasiteetin solmusta [hinnoittelusivulta](https://azure.microsoft.com/pricing/details/power-bi-embedded/).

Lisätietoa Power BI Embedded ‑kapasiteetin luomisesta saat ohjeaiheesta [Power BI Embedded -kapasiteetin luominen Azure-portaalissa](azure-pbie-create-capacity.md)

Jos haluat aloittaa Power BI -sisällön upottamisen, katso artikkelia [Power BI -koontinäyttöjen, -raporttien ja -ruutujen upottaminen](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).
