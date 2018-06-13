---
title: Google Analyticsin yhdistäminen Power BI:hin
description: Google Analytics Power BI:hin
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b479c46ffe3e51ad5f15cc9884a2ea02626a4cc5
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34244626"
---
# <a name="connect-to-google-analytics-with-power-bi"></a>Google Analyticsin yhdistäminen Power BI:hin
Yhteyden muodostaminen Google Analyticsiin Power BI:n kautta alkaa muodostamalla yhteys Google Analytics -tiliin. Saat Power BI:n koontinäytön ja joukon Power BI -raportteja, jotka tarjoavat merkityksellisiä tietoja sivuston liikenne- ja käyttäjädimensioista. Voit käsitellä koontinäyttöä ja raportteja, mutta et voi tallentaa muutoksia. Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys [Google Analyticsiin](https://app.powerbi.com/getdata/services/google-analytics) Power BI:tä varten. Lue lisää [Google Analyticsin integroinnista](https://powerbi.microsoft.com/integrations/google-analytics) Power BI:hin.

Voit luoda mukautettuja koontinäyttöjä ja raportteja aloittamalla [Google Analytics -liittimestä](service-google-analytics-connector.md) Power BI Desktopissa. Muodosta vain yhteys Google Analytics -tiliisi ja luo omat mukautetut raportit, jotka voit julkaista Power BI -palvelussa.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

1. Valitse **Google Analytics** \> **Nouda**.
   
   ![](media/service-connect-to-google-analytics/ga.png)
2. Anna pyydettäessä Google Analytics -tunnistetietosi. Valitse todennusmenetelmäksi **oAuth 2** ja valitse **Kirjaudu sisään**. Noudata Googlen todennustyönkulkua, joka saattaa sisältää 2-vaiheisen todennuksen, jos se on määritettynä.
   
   ![](media/service-connect-to-google-analytics/creds.png)
3. Valitse **Hyväksy**, jotta Power BI voi käyttää Google Analytics -tietojasi.
   
   ![](media/service-connect-to-google-analytics/googleanalytics.png)
4. Power BI muodostaa yhteyden tiettyyn Google Analytics -näkymään. Valitse sen tilin nimi, ominaisuuden nimi ja näkymän nimi, johon haluat muodostaa yhteyden. Nämä tiedot löytyvät Google Analytics -tilistäsi joko vasemmasta yläkulmasta tai **Aloitus**-välilehdestä. Lisätietoja on alla. 
   
   ![](media/service-connect-to-google-analytics/params2.png)
5. Aloita tuontiprosessi valitsemalla **Yhdistä**. 

## <a name="view-the-google-analytics-dashboard-and-reports"></a>Google Analytics -koontinäytön ja -raporttien tarkasteleminen
[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-open-app.md)]

      ![](media/service-connect-to-google-analytics/googleanalytics2.png)

[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-what-now.md)]

## <a name="system-requirements"></a>Järjestelmävaatimukset
Jotta yhteys voidaan muodostaa Power BI:stä, sinulla on oltava [Google Analytics](https://www.google.com/analytics/) -tili. Muista Google-tileistä, joihin ei ole yhdistetty Google Analytics -tiliä, näytetään todennusvirhe.

## <a name="troubleshooting"></a>Vianmääritys
**Tunnistetiedot** Jos sinulla on useita Google-tilejä, käytä incognito-tilaa tai yksityistä selainikkunaa yhteyden muodostamisessa, jotta käytössä on varmasti oikea tili.

Jos näyttöön tulee virhesanoma, jonka mukaan tunnistetiedot ovat virheelliset, vaikka voit kirjautua Googleen, varmista, että käytössäsi on [Google Analytics](https://www.google.com/analytics/) -tili.

**Parametrit** Tällä hetkellä parametreille vaaditaan yksilöivät nimet. Jos näkyviin tulee virhesanoma, joka ilmaisee valitun arvon olevan kaksoiskappale, valitse toinen arvo tai muuta nimiä Google Analyticsissa, jotta ne ovat yksilöllisiä. Pyrimme aktiivisesti tekemään parannuksia tässä suhteessa.

>[!NOTE]
>Parametrien kirjainkoko on merkitsevä. Anna ne juuri sellaisina kuin ne näkyvät Google Analytics -tilissäsi.

![](media/service-connect-to-google-analytics/pbi_googleanalytics1.png)

Jatkuvatko ongelmat? Avaa tukipalvelupyyntö, jotta saat yhteyden Power BI -tiimiin:

* Valitse Power BI -sovelluksessa kysymysmerkki \> **Ota yhteyttä tukeen.**
* Valitse Power BI:n tukisivustossa (jossa luet tämän artikkelin) sivun oikealla puolella **Ota yhteyttä tukeen**.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Mitä ovat Power BI:n sovellukset?](service-install-use-apps.md)
* [Tietojen noutaminen Power BI:ssä](service-get-data.md)
* Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](http://community.powerbi.com/)
