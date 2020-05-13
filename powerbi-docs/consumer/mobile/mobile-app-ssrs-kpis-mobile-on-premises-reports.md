---
title: Paikallisten raporttien ja suorituskykyilmaisimien tarkastelu Power BI -mobiilisovelluksissa
description: Power BI -mobiilisovellukset tarjoavat reaaliaikaisen, kosketuskäyttöisten mobiiliyhteyden paikan päällä oleviin yritystietoihisi SQL Server Reporting Services -palvelussa ja Power BI -raporttipalvelimessa.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 12/05/2019
ms.author: painbar
ms.openlocfilehash: 387f0cd4ecea59fd55af0a9eceff2272ddd8097b
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83278855"
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>Paikallisten raporttipalvelinten raporttien ja suorituskykyilmaisimien tarkastelu Power BI -mobiilisovelluksissa

Power BI -mobiilisovellukset tarjoavat reaaliaikaisen, kosketuskäyttöisten mobiiliyhteyden paikan päällä oleviin yritystietoihisi Power BI -raporttipalvelimessa ja SQL Server 2016 Reporting Services -palvelussa (SSRS).

Koskee seuraavia:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android-puhelin](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android-tabletti](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhonet |iPadit |Android-puhelimet |Android-tabletit |


![Raporttipalvelimen aloitussivu mobiilisovelluksissa](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>Aloitetaan tärkeimmästä
**Mobile-sovellukset sijaitsevat siellä, missä voit tarkastella Power BI-sisältöä, eivät siellä, missä ne luotiin.**

* Sinä ja muut raporttien luojat organisaatiossasi [voitte luoda Power BI -raportteja Power BI Desktopissa ja julkaista ne Power BI -raporttipalvelimen](../../report-server/quickstart-create-powerbi-report.md) verkkoportaalissa. 
* Voit luoda [suorituskykyilmaisimia suoraan verkkoportaalissa](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services), järjestää ne kansioihin ja merkitä haluamasi suosikit, jotta löydät ne helposti. 
* Voit luoda [Reporting Services -mobiiliraportteja](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) SQL Server 2016 Enterprise Edition Mobiiliraportin julkaisijalla ja julkaista ne [Reporting Services -verkkoportaalissa](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).  

Sitten voit Power BI -mobiilisovelluksissa yhdistää jopa viisi raporttipalvelinta Power BI -raportteihin ja suorituskykyilmaisimiin, jotka on järjestetty kansioihin tai kerätty suosikeiksi. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>Näytteisiin tutustuminen mobiilisovelluksissa ilman palvelinyhteyttä
Vaikka sinulla ei olisikaan pääsyä Reporting Services -verkkoportaaliin, voit tutustua Reporting Services -mobiiliraporttien ja suorituskykyilmaisinten ominaisuuksiin. 

1. Napauta profiilikuvaasi vasemmassa yläkulmassa ja valitse sitten **Asetukset** ulosliukuvassa Tilit-paneelissa.

2. Napauta avautuvalla Asetukset-sivulla **Reporting Services -malleja**, jonka jälkeen voit siirtyä käsittelemään suorituskykyilmaisinmalleja ja mobiiliraportteja.
   
   ![Reporting Services -mallit](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-report-server"></a>Yhteyden muodostaminen paikalliseen raporttipalvelimeen
Voit myös katsella paikallisia Power BI -raportteja, Reporting Services -mobiiliraportteja ja suorituskykyilmaisimia Power BI -mobiilisovelluksissa. 

1. Avaa Power BI -sovellus mobiililaitteessasi.
2. Jos et ole vielä kirjautunut sisään Power BI:hin, napauta **Raporttipalvelinta**.
   
   ![Kirjautuminen sisään raporttipalvelimeen](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Jos olet jo kirjautunut sisään Power BI-sovellukseen, napauta profiilikuvaasi vasemmassa yläkulmassa ja valitse sitten **Asetukset** ulosliukuvassa Tilit-paneelissa.
3. Valitse avautuvalla Asetukset-sivulla **Yhdistä palvelimeen**.
   
    ![Yhdistä palvelimeen](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)

    Mobiilisovellus tarvitsee yhteyden palvelimeen jollakin tavalla. Se voidaan tehdä muutamia tavoilla:
     * Samassa verkossa oleminen tai VPN:n käyttäminen on helpoin tapa.
     * Verkkosovelluksen välityspalvelinta voidaan käyttää yhteyden muodostamiseksi organisaation ulkopuolelle. Katso lisätietoja ohjeaiheesta [Reporting Servicesiin yhdistäminen OAuth-todennuksen avulla](mobile-oauth-ssrs.md).
     * Avaa yhteys (portti) palomuurissa.

4. Täytä palvelimen osoite ja anna palvelimelle kutsumanimi, jos haluat. Käytä tätä muotoilua palvelimen osoitteessa:
   
     `https://<servername>/reports`
   
     TAI
   
     `https://<servername>/reports`
   
   Lisää **http** tai **https** yhteysmerkkijonon eteen.
   
    ![Yhdistä palvelimeen -valintaikkuna](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. Kun olet kirjoittanut palvelimen osoitteen ja valinnaisen kutsumanimen, valitse **Yhdistä** ja anna sitten käyttäjänimi ja salasana pyydettäessä.
6. Nyt näet palvelimen Tilit-ruudussa – tässä esimerkissä sitä kutsutaan työpalvelimeksi.
   
   ![Raporttipalvelin siirtymisruudussa](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="connect-to-an-on-premises-report-server-in-ios-or-android"></a>Yhteyden muodostaminen paikalliseen raporttipalvelimeen iOS- tai Android-laitteessa

Jos tarkastelet Power BI:tä iOS- tai Android-mobiilisovelluksessa, IT-järjestelmänvalvojasi on saattanut määrittää sovelluksen määrityskäytännön. Tässä tapauksessa yhteyden muodostaminen raporttipalvelimeen on helppoa eikä sinun tarvitse antaa niin paljon tietoja muodostaessasi yhteyden raporttipalvelimeen. 

1. Näyttöön tulee sanoma, jossa ilmoitetaan mobiilisovelluksen olevan määritetty raporttipalvelimen kanssa. Napauta **Kirjaudu sisään**.

    ![Kirjaudu sisään raporttipalvelimeen](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-config-server-sign-in.png)

2.  **Muodosta yhteys palvelimeen** -sivulla raporttipalvelimen tiedot on valmiiksi täytetty. Napauta **Yhdistä**.

    ![Raporttipalvelimen tiedot esitäytettynä](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-remote-configure-connect-server.png)

3. Kirjoita salasana todennusta varten ja napauta sitten **Kirjaudu sisään**. 

    ![Raporttipalvelimen tiedot esitäytettynä](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-config-server-address.png)

Nyt voit tarkastella ja käsitellä raporttipalvelimeen tallennettuja suorituskykyilmaisimia ja Power BI -raportteja.

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Power BI -raporttien ja suorituskykyilmaisinten tarkastelu Power BI-sovelluksessa
Power BI -raportit, Reporting Services -mobiiliraportit ja suorituskykyilmaisimet näkyvät samoissa kansiossa, joissa ne ovat Reporting Services -verkkoportaalissa. 

* Napauta Power BI -raporttia ![Power BI -raportin kuvake](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png). Se aukeaa vaakasuunnassa, ja voit käsitellä sitä Power BI -sovelluksessa.

    > [!NOTE]
  > Poraudu alaspäin ja ylöspäin -toimintoa ei tällä hetkellä ole otettu käyttöön Power BI -raporteissa Power BI -raporttipalvelimella.
  
    ![Power BI -raportti](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* Power BI Desktopissa raporttien omistajat voivat [optimoida raportin](../../create-reports/desktop-create-phone-report.md) Power BI -mobiilisovelluksia silmällä pitäen. Matkapuhelimessa optimoiduilla raporteilla on erityinen kuvake, ![Optimoidun Power BI -raportin kuvake](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png) ja asettelu.
  
    ![Mobiililaitteille optimoitu Power BI -raportti](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Napauta Suorituskykyilmaisinta sen näkemiseksi tarkastelutilassa.
  
    ![Suorituskykyilmaisin tarkastelutilassa](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Suosikkisuorituskykyilmaisinten ja -raporttien tarkastelu
Voit merkitä suorituskykyilmaisimia ja raportteja suosikeiksi verkkoportaalissa ja tarkastella niitä yhdessä kätevässä kansiossa mobiililaitteessasi Power BI -suosikkikoontinäyttöjesi kera.

* Valitse **Suosikit** siirtymispalkissa.
  
   ![Suosikit siirtymisruudussa](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server-update.png)
  
   Suosikkisi suorituskykyilmaisimista ja verkkoportaalin raporteista ovat kaikki tällä sivulla, yhdessä Power BI -koontinäyttöjen kanssa Power BI -palvelussa:
  
   ![Power BI -raportteja ja koontinäyttö Suosikit-sivulla](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Yhteyden poistaminen raporttipalvelimeen
1. Avaa Tilit-ruutu ja valitse **Asetukset**.
2. Napauta sen palvelimen nimeä, johon et halua olla yhteydessä.
3. Napauta **Poista palvelin**.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Mikä on Power BI?](../../fundamentals/power-bi-overview.md)  
* Onko sinulla kysymyksiä? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
