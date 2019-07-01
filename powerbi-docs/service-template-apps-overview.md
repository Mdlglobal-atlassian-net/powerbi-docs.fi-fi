---
title: Mitä Power BI -mallisovellukset ovat?
description: Tämä artikkeli on Power BI -mallisovellusten ohjelman yleiskatsaus. Opi kehittämään Power BI -sovelluksia, niin että koodausta tarvitaan vain vähän tai ei ollenkaan, ja ota sovellukset käyttöön keille tahansa Power BI -asiakkaille.
author: teddybercovitz
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: tebercov
ms.openlocfilehash: c05b53a5fd61d348b6d304b17123d5f2497ab647
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/27/2019
ms.locfileid: "67408204"
---
# <a name="what-are-power-bi-template-apps"></a>Mitä Power BI -mallisovellukset ovat?

Power BI:n uusien *mallisovellusten* avulla Power BI -kumppanit voivat kehittää Power BI -sovelluksia käyttäen vain vähän tai ei lainkaan koodausta, minkä lisäksi sovellukset voidaan ottaa käyttöön kenelle tahansa Power BI -asiakkaalle.  Tämä artikkeli on Power BI -mallisovellusten ohjelman yleiskatsaus.

Mallisovellukset korvaavat nykyiset palvelun sisältöpaketit. Power BI -kumppanina voit luoda valmista sisältöä asiakkaillesi ja julkaista sen itse.  

Voit kehittää mallisovelluksia, joiden avulla asiakkaasi voivat yhdistää ja alustaa tiedot omiin tileihinsä. Toimialueen asiantuntijoina he voivat avata tietojen lukituksen siten, että ne ovat helposti heidän yrityskäyttäjiensä käytettävissä.  

Lähetä mallisovelluksesi pilvikumppaniportaaliin. Sovellukset ovat sitten julkisesti saatavilla Power BI -sovellusvalikoimassa (app.powerbi.com/getdata/services) ja Microsoft AppSourcessa (appsource.microsoft.com). Tässä on korkean tason katsaus julkisen mallisovelluksen luomistoimintoon.  

## <a name="process"></a>Prosessi
Mallisovelluksen yleinen kehittämis- ja lähettämisprosessi koostuu useista vaiheista. Jotkin vaiheet voivat koostua useammasta kuin yhdestä samanaikaisesta toiminnosta.


| Vaihe | Power BI Desktop |  |Power BI -palvelu  |  |Pilvikumppaniportaali  |
|---|--------|--|---------|---------|---------|
| **Yksi** | Luo tietomalli ja raportti .pbix-tiedostoon |  | Luo työtila. Tuo .pbix-tiedosto. Luo täydentävä koontinäyttö  |  | Rekisteröidy kumppanina |
| **Kaksi** |  |  | Luo testipaketti ja suorita sisäinen vahvistus        |  | |
| **Kolme** | |  | Ylennä testipaketti esituotantoon, niin että se vahvistetaan Power BI -vuokraajan ulkopuolella, ja lähetä se AppSourceen  |  | Luo esituotantopaketilla Power BI -mallisovellustarjous ja aloita vahvistusprosessi |
| **Neljä** | |  | Ylennä esituotantopaketti tuotannoksi |  | Julkaise |

## <a name="before-you-begin"></a>Alkutoimet

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

Mallisovelluksen luomista varten tarvitaan oikeus mallisovelluksen luomiseen. Lisätietoja on Power BI:n [hallintaportaalin kohdassa Mallisovelluksen asetukset](service-admin-portal.md#template-apps-settings). 

Jotta voit julkaista mallisovelluksen Power BI -palveluun ja AppSourceen, sinun on täytettävä [Cloud Marketplace -julkaisijaksi ryhtymisen](https://docs.microsoft.com/azure/marketplace/become-publisher) ehdot.
 > [!NOTE] 
 > Mallisovellusten lähetyksiä hallitaan [Pilvikumppaniportaalissa](https://cloudpartner.azure.com). Käytä samaa Microsoftin kehittäjäkeskuksen rekisteröintitiliä sisäänkirjautumiseen. Sinulla pitäisi olla vain yksi Microsoft-tili AppSource-tarjouksia varten. Tilien ei tulisi olla palvelu- tai tarjouskohtaisia.

## <a name="tips"></a>Vinkkejä 

- Varmista, että sovelluksesi sisältää mallitietoja, niin että kaikki voivat aloittaa käytön yhdellä napsautuksella. 
- Tutki sovellustasi huolellisesti asentamalla se omassa vuokraajassasi ja toissijaisessa vuokraajassa. Varmista, että asiakkaat näkevät vain sen, mitä haluat heidän näkevän. 
- Käytä AppSourcea verkkosäilönä, joka isännöi sovellustasi. Näin kaikki Power BI:n käyttäjät voivat löytää sovelluksesi. 
- Harkitse useamman kuin yhden mallisovelluksen tarjoamista erillisiä ainutkertaisia skenaarioita varten. 
- Ota käyttöön tietojen mukauttaminen; tue esimerkiksi mukautettua yhteyttä ja asennusohjelman määrittämiä parametreja.

Lisää ehdotuksia on artikkelissa [Vihjeitä mallisovellusten luomiseen Power BI:ssä](service-template-apps-tips.md).

## <a name="support"></a>Tuki
Saat tukea kehityksen aikana osoitteesta [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support). Valvomme ja hallinnoimme tätä sivustoa aktiivisesti. Asiakastapaukset ohjataan nopeasti oikealle tiimille.

## <a name="next-steps"></a>Seuraavat vaiheet

[Mallisovelluksen luonti](service-template-apps-create.md)
