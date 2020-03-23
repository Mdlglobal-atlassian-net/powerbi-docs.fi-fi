---
title: Paikallisten raporttien ja suorituskykyilmaisimien tarkastelu Power BI:n Windows-sovelluksessa
description: Power BI -mobiilisovellus Windows 10:lle tarjoaa tärkeiden, paikalliseen liiketoimintaan liittyvien tietojen reaaliaikaisen, kosketuskäyttöisten mobiilikäytön.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/09/2020
ms.author: painbar
ms.openlocfilehash: 67daafc0938216b135b31d3190c191402e9a10de
ms.sourcegitcommit: abc8419155dd869096368ba744883b865c5329fa
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/17/2020
ms.locfileid: "79435371"
---
# <a name="view-on-premises-reports-and-kpis-in-the-power-bi-windows-app"></a>Paikallisten raporttien ja suorituskykyilmaisimien tarkastelu Power BI:n Windows-sovelluksessa
Power BI -sovellus Windows 10:lle tarjoaa tärkeiden, paikalliseen liiketoimintaan liittyvien tietojen reaaliaikaisen, kosketuskäyttöisen mobiilikäytön SQL Server 2016 Reporting Servicesissä. 

![Reporting Servicesin mobiiliraportit](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="first-things-first"></a>Aloitetaan tärkeimmästä
Voit luoda [Reporting Services -mobiiliraportteja](https://msdn.microsoft.com/library/mt652547.aspx) SQL Server 2016 Enterprise Edition -mobiiliraportin julkaisuohjelmalla ja julkaista ne [Reporting Services -verkkoportaalissa](https://msdn.microsoft.com/library/mt637133.aspx). Luo suorituskykymittarit suoraan verkkoportaalissa. Voit järjestää ne kansioihin ja merkitä haluamasi suosikit, jotta löydät ne helposti. 

Sitten voit tarkastella Windows 10:n Power BI -sovelluksessa suorituskykymittareita, mobiiliraportteja ja Power BI -raportteja, järjestää niitä kansioihin tai kerätä suosikeiksi. 

> [!NOTE]
> Laitteessa on oltava käytössä Windows 10. Sovellus toimii parhaiten laitteissa, joissa on vähintään 1 Gigatavua RAM-muistia ja 8 Gigatavua tallennustilaa.

>[!NOTE]
>Power BI -mobiilisovellustuki **Windows 10 Mobilea käyttäville puhelimille** lopetetaan 16. maaliskuuta 2021. [Lisätietoja](https://go.microsoft.com/fwlink/?linkid=2121400)

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>Tutustu näytteisiin ilman SQL Server 2016 Reporting Services -palvelinta
Vaikka sinulla ei olisikaan pääsyä Reporting Services -verkkoportaaliin, voit tutustua Reporting Services -mobiiliraporttien ominaisuuksiin.

1. Avaa Power BI -sovellus Windows 10 -laitteellasi.
2. Napauta yleistä siirtymispainiketta ![Yleinen siirtymispainike](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) vasemmassa yläkulmassa.
3. Napauta **Asetukset**-kuvaketta ![](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png), napsauta hiiren kakkospainikkeella tai napauta pitkään **Muodosta yhteys palvelimeen**, napauta sitten **Näytä mallit**.
   
   ![Näytä SSRS-näytteet](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-connect-ssrs-samples.png)
4. Avaa vähittäismyyntiraporttien tai myyntiraporttien kansio niiden suorituskykymittareiden ja mobiiliraporttien katselemiseksi.
   
   ![Esimerkki suorituskykymittareista ja mobiiliraporteista](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-ssrs-sample-kpis.png)

Selaa näytteitä suorituskykymittarien ja mobiiliraporttien käyttämiseksi vuorovaikutteisesti.

## <a name="connect-to-a-reporting-services-report-server"></a>Muodosta yhteys Reporting Servicesin -raporttien palvelimelle
1. Napauta siirtymisruudun alaosassa kohtaa **Asetukset** ![Asetukset-kuvake](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png)
2. Napauta **Yhdistä palvelimeen**.
3. Kirjoita palvelimen osoite ja käyttäjänimesi ja salasanasi. Käytä tätä muotoilua palvelimen osoitteessa:
   
     `https://<servername>/reports` TAI   `https://<servername>/reports`
   
   > [!NOTE]
   > Lisää **http** tai **https** yhteysmerkkijonon alkuun.
   > 
   > 
   
    Napauta halutessasi **Lisäasetus**, jos haluat antaa palvelimelle nimen.
4. Muodosta yhteys napauttamalla valintamerkkiä. 
   
   Nyt näet palvelimen siirtymissiirtymisruudussa.
   
   ![Palvelin siirtymisruudussa](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)
   
   >[!TIP]
   >Voit napauttaa ![Yleinen siirtymisnäkymä -painiketta](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) milloin tahansa ja siirtyä Reporting Services -mobiiliraporttien ja Power BI -palvelun koontinäyttöjen välillä. 
   > 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>Tarkastele Reporting Services -suorituskykymittareita ja mobiiliraportteja Power BI -sovelluksella
Reporting Services -mobiiliraportit, suorituskykyilmaisimet ja Power BI -raportit (esikatselu) näkyvät samoissa kansiossa, joissa ne ovat Reporting Services -verkkoportaalissa.

![Raportin kansiot](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

* Napauta Suorituskykyilmaisinta sen näkemiseksi tarkastelutilassa.
  
    ![Suorituskykyilmaisin tarkastelutilassa](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)
* Napauta mobiiliraporttia Power BI -sovelluksen avaamista ja käyttöä varten.
  
    ![Reporting Servicesin mobiiliraportit](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Suosikkisuorituskykymittareiden ja -raporttien tarkastelu
Voit merkitä suorituskykymittareita, mobiiliraportteja ja Power BI -raportteja suosikeiksi Reporting Services -verkkoportaalissa ja tarkastella niitä yhdessä kätevässä kansiossa Windows 10 -laitteessasi Power BI -suosikkikoontinäyttöjesi ja raporttien kera.

* Napauta **Suosikit**.
  
   ![Suosikit-kuvake](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
  
   Verkkoportaalin suosikit ovat kaikki tällä sivulla.
  
Lue lisää [suosikeista Power BI -mobiilisovelluksissa](mobile-apps-favorites.md).

## <a name="remove-a-connection-to-a-report-server"></a>Yhteyden poistaminen raporttipalvelimeen
Voit olla yhdistettynä vain yhteen raporttipalvelimen kerrallaan Power BI -mobiilisovelluksestasi. Jos haluat muodostaa yhteyden eri palvelimeen, sinun on katkaistava yhteys nykyiseen.

1. Napauta siirtymisruudun alaosassa kohtaa **Asetukset** ![Asetukset-kuvake](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png).
2. Napauta ja pidä palvelimen nimeä, johon et halua olla yhteydessä.
3. Napauta **Poista palvelin**.
   
    ![Poista palvelin](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)

## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Luo Reporting Services -mobiiliraportit ja suorituskykymittarit
Reporting Services -suorituskykymittareita ja mobiiliraportteja ei luoda Power BI -sovelluksella. Ne luodaan SQL Server Mobile Report Publisher- ja SQL Server 2016 Reporting Services -verkkoportaalien kautta.

* [Luo omat Reporting Services -raportit](https://msdn.microsoft.com/library/mt652547.aspx) ja julkaise ne Reporting Services -verkkoportaalissa.
* Luo [suorituskykymittarit Reporting Services -verkkoportaalissa](https://msdn.microsoft.com/library/mt683632.aspx)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Windows 10:n Power BI -mobiilisovelluksen käytön aloittaminen](mobile-windows-10-phone-app-get-started.md)  
* [Mikä on Power BI?](../../fundamentals/power-bi-overview.md)  
* Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)

