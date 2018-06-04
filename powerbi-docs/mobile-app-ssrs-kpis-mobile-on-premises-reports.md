---
title: Paikallisten raporttien ja suorituskykyilmaisimien tarkastelu Power BI -mobiilisovelluksissa
description: Power BI -mobiilisovellukset tarjoavat reaaliaikaisen, kosketuskäyttöisten mobiiliyhteyden paikan päällä oleviin yritystietoihisi SQL Server Reporting Services -palvelussa ja Power BI -raporttipalvelimessa.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
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
ms.date: 12/18/2017
ms.author: maggies
ms.openlocfilehash: 5bbd2f09187e9fac16f6cc4b9ac3ff59a888ed7f
ms.sourcegitcommit: ea247cb3cfc1cac076d4b076c1ad8e2fc37e15a1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 12/19/2017
ms.locfileid: "30972597"
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>Paikallisten raporttipalvelinten raporttien ja suorituskykyilmaisimien tarkastelu Power BI -mobiilisovelluksissa
Koskee seuraavia:

| ![iPhone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android-puhelin](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android-tabletti](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |

Power BI -mobiilisovellukset tarjoavat reaaliaikaisen, kosketuskäyttöisten mobiiliyhteyden paikan päällä oleviin yritystietoihisi Power BI -raporttipalvelimessa ja SQL Server 2016 Reporting Services -palvelussa (SSRS). 

 ![Raporttipalvelimen aloitussivu mobiilisovelluksissa](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>Aloitetaan tärkeimmästä
**Mobile-sovellukset sijaitsevat siellä, missä voit tarkastella Power BI-sisältöä, eivät siellä, missä ne luotiin.**

* Sinä ja muut raporttien luojat organisaatiossasi [voitte luoda Power BI -raportteja Power BI Desktopissa ja julkaista ne Power BI -raporttipalvelimen](report-server/quickstart-create-powerbi-report.md) verkkoportaalissa. 
* Voit luoda [suorituskykyilmaisimia suoraan verkkoportaalissa](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services), järjestää ne kansioihin ja merkitä haluamasi suosikit, jotta löydät ne helposti. 
* Voit luoda [Reporting Services -mobiiliraportteja](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) SQL Server 2016 Enterprise Edition Mobiiliraportin julkaisijalla ja julkaista ne [Reporting Services -verkkoportaalissa](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).  

Sitten voit Power BI -mobiilisovelluksissa yhdistää jopa viisi raporttipalvelinta Power BI -raportteihin ja suorituskykyilmaisimiin, jotka on järjestetty kansioihin tai kerätty suosikeiksi. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>Näytteisiin tutustuminen mobiilisovelluksissa ilman palvelinyhteyttä
Vaikka sinulla ei olisikaan pääsyä Reporting Services -verkkoportaaliin, voit tutustua Reporting Services -mobiiliraporttien ja suorituskykyilmaisinten ominaisuuksiin. 

1. Napauta yleistä siirtymispainiketta ![Yleinen siirtymispainike](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) vasemmassa yläkulmassa, napauta sitten oikeassa yläkulmassa näkyvää hammaspyöräkuvaketta ![Hammaspyöräkuvake](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png).
2. Napauta **Reporting Services -malleja**, jonka jälkeen voit siirtyä käsittelemään suorituskykyilmaisinmalleja ja mobiiliraportteja.
   
   ![Reporting Services -mallit](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-server"></a>Yhteyden muodostaminen paikalliseen palvelimeen
Voit myös katsella paikallisia Power BI -raportteja, Reporting Services -mobiiliraportteja ja suorituskykyilmaisimia Power BI -mobiilisovelluksissa. 

1. Avaa Power BI -sovellus mobiililaitteessasi.
2. Jos et ole vielä kirjautunut sisään Power BI:hin, napauta **Raporttipalvelinta**.
   
   ![Kirjautuminen sisään raporttipalvelimeen](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Jos olet jo kirjautunut sisään Power BI -sovellukseen, napauta yleistä siirtymispainiketta ![Yleinen siirtymispainike](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png), napauta sitten hammaspyöräkuvaketta ![Hammaspyöräkuvake](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) oikeassa yläkulmassa.
3. Napauta **Yhdistä palvelimeen**.
   
    ![Yhdistä palvelimeen](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)

     Mobiilisovellus tarvitsee yhteyden palvelimeen jollakin tavalla. Se voidaan tehdä muutamia tavoilla:

    - Samassa verkossa oleminen tai VPN:n käyttäminen on helpoin tapa.
    - Verkkosovelluksen välityspalvelinta voidaan käyttää yhteyden muodostamiseksi organisaation ulkopuolelle. Katso lisätietoja ohjeaiheesta [Reporting Servicesiin yhdistäminen OAuth-todennuksen avulla](mobile-oauth-ssrs.md). 
    - Avaa yhteys (portti) palomuurissa.

1. Kirjoita palvelimen osoite ja käyttäjänimesi ja salasanasi. Käytä tätä muotoilua palvelimen osoitteessa:
   
     `http://<servername>/reports`
   
     TAI
   
     `https://<servername>/reports`
   
   Lisää **http** tai **https** yhteysmerkkijonon eteen.
   
    ![Yhdistä palvelimeen -valintaikkuna](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. (Valinnainen) **Lisäasetukset**-kohdassa voit halutessasi antaa palvelimelle kutsumanimen.
6. Nyt näet palvelimen vasemmanpuoleisessa siirtymispalkissa, joka tässä esimerkissä on nimeltään ”power bi -raporttipalvelin”.
   
   ![Raporttipalvelin vasemmanpuoleisessa siirtymisruudussa](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Power BI -raporttien ja suorituskykyilmaisinten tarkastelu Power BI-sovelluksessa
Power BI -raportit, Reporting Services -mobiiliraportit ja suorituskykyilmaisimet näkyvät samoissa kansiossa, joissa ne ovat Reporting Services -verkkoportaalissa. 

* Napauta Power BI -raporttia ![Power BI -raportin kuvake](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png). Se aukeaa vaakasuunnassa, ja voit käsitellä sitä Power BI -sovelluksessa.
  
    ![Power BI -raportti](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* Power BI Desktopissa raporttien omistajat voivat [optimoida raportin](desktop-create-phone-report.md) Power BI -mobiilisovelluksia silmällä pitäen. Matkapuhelimessa optimoiduilla raporteilla on erityinen kuvake, ![Optimoidun Power BI -raportin kuvake](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png) ja asettelu.
  
    ![Mobiililaitteille optimoitu Power BI -raportti](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Napauta Suorituskykyilmaisinta sen näkemiseksi kohdistustilassa.
  
    ![Suorituskykyilmaisin kohdistustilassa](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Suosikkisuorituskykyilmaisinten ja -raporttien tarkastelu
Voit merkitä suorituskykyilmaisimia ja raportteja suosikeiksi verkkoportaalissa ja tarkastella niitä yhdessä kätevässä kansiossa mobiililaitteessasi Power BI -suosikkikoontinäyttöjesi kera.

* Napauta **Suosikit**.
  
   ![Suosikit vasemmanpuoleisessa siirtymisruudussa](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server-update.png)
  
   Suosikkisi suorituskykyilmaisimista ja verkkoportaalin raporteista ovat kaikki tällä sivulla, yhdessä Power BI -koontinäyttöjen kanssa Power BI -palvelussa:
  
   ![Power BI -raportteja ja koontinäyttö Suosikit-sivulla](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Yhteyden poistaminen raporttipalvelimeen
1. Napauta **Asetukset** vasemmanpuoleisen siirtymispalkin alaosasta.
2. Napauta palvelimen nimeä, johon et halua olla yhteydessä.
3. Napauta **Poista palvelin**.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI:n käytön aloittaminen](service-get-started.md)  
* Ilmenikö kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
