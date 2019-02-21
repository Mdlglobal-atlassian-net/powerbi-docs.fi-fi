---
title: Mitä Power BI -mallisovellukset ovat? (esikatselu)
description: Tässä artikkelissa on yleiskatsaus Power BI -mallisovellusten ohjelmasta. Opi kehittämään Power BI -sovelluksia, niin että koodausta tarvitaan vain vähän tai ei ollenkaan, ja ota sovellukset käyttöön keille tahansa Power BI -asiakkaille.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: maggies
ms.openlocfilehash: 445f5f087bd9589b18f798e8db40a63b0ddceafe
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/14/2019
ms.locfileid: "56249742"
---
# <a name="what-are-power-bi-template-apps-preview"></a>Mitä Power BI -mallisovellukset ovat? (esikatselu)

Power BI:n uusien *mallisovellusten* avulla Power BI -kumppanit voivat kehittää Power BI -sovelluksia käyttäen vain vähän tai ei lainkaan koodausta, minkä lisäksi sovellukset voidaan ottaa käyttöön kenelle tahansa Power BI -asiakkaalle.  Tämä artikkeli on Power BI -mallisovellusten ohjelman yleiskatsaus.

Mallisovellukset korvaavat nykyiset palvelun sisältöpaketit. Power BI -kumppanina voit luoda valmista sisältöä asiakkaillesi ja julkaista sen itse.  

Voit kehittää mallisovelluksia, joiden avulla asiakkaasi voivat yhdistää ja alustaa tiedot omiin tileihinsä. Toimialueen asiantuntijoina he voivat avata tietojen lukituksen siten, että ne ovat helposti heidän yrityskäyttäjiensä käytettävissä.  

Lähetä kumppanien kehittämät mallisovellukset pilvikumppaniportaaliin. Sovellukset ovat sitten julkisesti saatavilla Power BI -sovellusvalikoimassa (app.powerbi.com/getdata/services) ja Microsoft AppSourcessa (appsource.microsoft.com). Tässä on esimerkki julkisen mallisovelluksen käyttökokemuksesta.  

## <a name="overview"></a>Yleiskatsaus
Mallisovelluksen yleiseen kehittämis- ja lähetysprosessiin liittyy useita vaiheita, joista joissakin saattaa olla useita samanaikaisia toimintoja.


| Vaihe | Power BI Desktop |  |Power BI -palvelu  |  |Pilvikumppaniportaali  |
|---|--------|--|---------|---------|---------|
| **Yksi** | Luo tietomalli ja raportti .pbix-tiedostoon |  | Luo työtila. Tuo .pbix-tiedosto. Luo täydentävä koontinäyttö  |  | Rekisteröidy kumppanina |
| **Kaksi** |  |  | Luo testipaketti ja suorita sisäinen vahvistus        |  | |
| **Kolme** | |  | Ylennä testipaketti esituotantoon, niin että se vahvistetaan Power BI -vuokraajan ulkopuolella, ja lähetä se AppSourceen  |  | Luo esituotantopaketilla Power BI -mallisovellustarjous ja aloita vahvistusprosessi |
| **Neljä** | |  | Ylennä esituotantopaketti tuotannoksi |  | Julkaise |

## <a name="requirements"></a>Vaatimukset

Mallisovelluksen luomista varten tarvitaan oikeus mallisovelluksen luomiseen. Lisätietoja on Power BI:n hallintaportaalin kohdassa Mallisovelluksen asetukset. 

Jotta voit julkaista mallisovelluksen Power BI -palveluun ja AppSourceen, sinun on täytettävä [Cloud Marketplace -julkaisijaksi ryhtymisen](https://docs.microsoft.com/azure/marketplace/become-publisher) ehdot.
 
## <a name="high-level-steps"></a>Ylätason vaiheet

Tässä ovat ylätason vaiheet. 

1. [Tarkista edellytykset](#requirements) ja varmista, että täytät ne. 

1. Luo raportti Power BI Desktopissa. Käytä parametreja, niin että voit tallentaa raportin tiedostona, jota muut voivat käyttää. 

1. Luo mallisovellukselle työtila Power BI -palvelun vuokraajassasi (app.powerbi.com). 

1. Tuo .pbix-tiedosto ja lisää sovellukseesi sisältöä, kuten koontinäyttö. 

1. Luo testipaketti, niin että voit itse testata mallisovellusta organisaatiossasi. 

1. Ylennä testisovellus esituotantoon, niin että voit lähettää sovelluksen vahvistettavaksi AppSourcessa sekä testata oman vuokraajasi ulkopuolella. 

1. Lähetä sisältö Cloud Partner Platformiin julkaistavaksi. 

1. Määritä tarjouksesi käyttöönottotilaan AppSourcessa ja siirrä sovelluksesi tuotantoon Power BI:ssä.
2. Voit nyt alkaa kehittää samassa työtilassa seuraavaa versiota esituotannossa. 

## <a name="requirements"></a>Vaatimukset

Mallisovelluksen luomista varten tarvitaan oikeus mallisovelluksen luomiseen. Lisätietoja on Power BI:n [hallintaportaalin kohdassa Mallisovelluksen asetukset](service-admin-portal.md#template-apps-settings-preview). 

Jotta voit julkaista mallisovelluksen Power BI -palveluun ja AppSourceen, sinun on täytettävä [Cloud Marketplace -julkaisijaksi ryhtymisen](https://docs.microsoft.com/azure/marketplace/become-publisher) ehdot.

## <a name="tips"></a>Vinkkejä 

- Varmista, että sovelluksesi sisältää mallitietoja, niin että kaikki voivat aloittaa käytön yhdellä napsautuksella. 
- Tutki sovellustasi huolellisesti asentamalla se omassa vuokraajassasi ja toissijaisessa vuokraajassa. Varmista, että asiakkaat näkevät vain sen, mitä haluat heidän näkevän. 
- Käytä AppSourcea verkkosäilönä, joka isännöi sovellustasi. Näin kaikki Power BI:n käyttäjät voivat löytää sovelluksesi. 
- Harkitse useamman kuin yhden mallisovelluksen tarjoamista erillisiä ainutkertaisia skenaarioita varten. 
- Ota käyttöön tietojen mukauttaminen; tue esimerkiksi mukautettua yhteyttä ja asennusohjelman määrittämiä parametreja.

Lisää ehdotuksia on artikkelissa [Vihjeitä mallisovellusten luomiseen Power BI:ssä (esikatselu)](service-template-apps-tips.md)

## <a name="support"></a>Tuki
Saat tukea kehityksen aikana osoitteesta [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Valvomme ja hallinnoimme tätä sivustoa aktiivisesti. Asiakastapaukset ohjataan nopeasti oikealle tiimille.

## <a name="next-steps"></a>Seuraavat vaiheet

[Mallisovelluksen luonti](service-template-apps-create.md)