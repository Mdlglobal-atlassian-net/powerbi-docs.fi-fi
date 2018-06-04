---
title: Asenna Power BI -raporttipalvelimelle optimoitu Power BI Desktop
description: Opi asentamaan Power BI -raporttipalvelimelle optimoitu Power BI Desktop
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
ms.date: 03/22/2018
ms.author: maggies
ms.openlocfilehash: c22e909130767abd1dc6f0aa00d76e1fb6b99ee7
ms.sourcegitcommit: fe859130099d923ee30da6091efcc70a264dcba6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/28/2018
ms.locfileid: "30975977"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Asenna Power BI -raporttipalvelimelle optimoitu Power BI Desktop
Opi asentamaan Power BI -raporttipalvelimelle optimoitu Power BI Desktop.

Jotta voit luoda Power BI -raportteja Power BI -raporttipalvelimelle, sinun on ladattava ja asennettava Power BI -raporttipalvelimelle optimoitu Power BI Desktop. Tämä versio on erilainen kuin Power BI -palvelun kanssa käytettävä Power BI Desktop. Power BI Desktopin versio Power BI -palvelulle sisältää esimerkiksi esikatseluominaisuuksia, joita ei ole käytettävissä Power BI -raporttipalvelinversiossa ennen kuin ne on julkaistu. Käyttämällä tätä versiota varmistetaan, että raporttipalvelin voi käsitellä raporttien ja mallin tunnettua versiota. 

Onneksi voit asentaa Power BI Desktopin ja Power BI -raporttipalvelimelle optimoidun Power BI Desktopin rinnakkain samalle tietokoneelle.

## <a name="download-and-install-power-bi-desktop"></a>Power BI Desktopin lataaminen ja asentaminen

Helpoin tapa varmistaa, että sinulla on Power BI -raporttipalvelimelle optimoidun Power BI Desktopin uusin versio, on aloittaa raporttipalvelimesi verkkoportaalista.

1. Valitse raporttipalvelimen verkkoportaalissa **Lataa**-nuoli > **Power BI Desktop**.

    ![Lataa Power BI Desktop verkkoportaalista](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Voit myös siirtyä suoraan kohtaan [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) (optimoitu Power BI -raporttipalvelimelle – maaliskuu 2018) Microsoft Download Centerissä.

2. Valitse Download Center -sivulla **Lataa**.

3. Tietokoneestasi riippuen valitse: 

    - **PBIDesktopRS.msi** (32-bittinen versio) tai

    - **PBIDesktopRS_x64.msi** (64-bittinen versio).

1. Kun olet ladannut asennusohjelman, suorita Power BI Desktopin (lokakuu 2017) ohjattu asennus.
2. Asennuksen lopussa valitse **Käynnistä Power BI Desktop nyt**.
   
    Se käynnistyy automaattisesti ja on valmiina käyttöön.

## <a name="verify-you-are-using-the-correct-version"></a>Varmista, että käytät oikeaa versiota
Voit varmistaa, että käytät Power BI Desktopin oikeaa versiota, Power BI Desktopin käynnistysnäytöstä tai otsikkoriviltä. Otsikkorivi ilmaisee version julkaisukuukauden ja -vuoden.

![Power BI -raporttipalvelimelle optimoidun Power BI Desktopin otsikkorivi](media/quickstart-create-powerbi-report/report-server-desktop-march-2018.png)

Power BI -palvelun Power BI Desktop -versiossa ei ole kuukautta ja vuotta otsikkorivillä.

## <a name="file-extension-association"></a>Tiedostotunnisteen kytkentä
Jos olet asentanut sekä Power BI Desktopin että Power BI -raporttipalvelimelle optimoidun Power BI Desktopin samalle koneelle, Power BI Desktopin viimeisimmässä asennuksessa on tiedostokytkentä .pbix. Tämä tarkoittaa, että kun kaksoisnapsautat pbix-tiedostoa, viimeksi asennettu Power BI Desktop käynnistyy.

Jos sinulla oli Power BI Desktop ja asensit sitten Power BI -raporttipalvelimelle optimoidun Power BI Desktopin, kaikki pbix-tiedostot avataan oletuksena Power BI -raporttipalvelimelle optimoidussa Power BI Desktopissa. Jos haluat, että pbix-tiedoston avaamisen yhteydessä oletuksena käynnistyvä ohjelma on Power BI Desktop, asenna Power BI Desktop uudelleen Power BI -palvelusta.

Voit myös aina ensin avata sen Power BI Desktopin version, jota haluat käyttää. Ja avata sitten tiedoston Power BI Desktopista.

Power BI -raportin muokkaaminen Power BI -raporttipalvelimesta tai uuden Power BI -raportin luominen verkkoportaalista avaa aina Power BI Desktopin oikean version.

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset
Power BI -raporttipalvelimen ja Power BI -palvelun raportit (http://powerbi.com) toimivat lähes täsmälleen samoin, mutta jotkut ominaisuudet ovat erilaisia.

### <a name="in-a-browser"></a>Selaimessa
Power BI -raporttipalvelimen raportit tukevat kaikkia visualisointeja, mukaan luettuina seuraavat:

* Mukautetut visualisoinnit

Power BI -raporttipalvelimen raportit eivät tue seuraavia:

* R-visualisoinnit
* ArcGIS-kartat
* Navigointipolut
* Power BI Desktopin esikatselutoiminnot

### <a name="in-the-power-bi-mobile-apps"></a>Power BI -mobiilisovelluksissa
Power BI -raporttipalvelimen raportit tukevat [Power BI -mobiilisovellusten](../mobile-apps-for-mobile-devices.md) kaikkia tavallisia toimintoja, mukaan luettuina seuraavat:

* [Puhelimen raporttiasettelu](../desktop-create-phone-report.md): voit optimoida raportin Power BI -mobiilisovelluksia silmällä pitäen. Optimoiduilla raporteilla on matkapuhelimessa erityinen kuvake, ![Puhelimen raporttiasettelun kuvake](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-icon.png), sekä asettelu.
  
    ![Puhelimille optimoitu raportti](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-report.png)

Power BI -raporttipalvelimen raportit eivät tue näitä ominaisuuksia Power BI -mobiilisovelluksissa:

* R-visualisoinnit
* ArcGIS-kartat
* Mukautetut visualisoinnit
* Navigointipolut
* Geo-suodatus tai viivakoodit

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop Power BI -raporttipalvelimen aiempiin versioihin

Jos raporttipalvelimesi on aiempi versio, tarvitset vastaavan version Power BI Desktopista. Tässä ovat kaksi aiempaa versiota.

- Microsoft Power BI Desktop ([optimoitu Power BI -raporttipalvelimelle - lokakuu 2017](https://www.microsoft.com/download/details.aspx?id=56136))
- Microsoft Power BI Desktop ([optimoitu Power BI -raporttipalvelimelle - kesäkuu 2017](https://www.microsoft.com/download/details.aspx?id=55330))

## <a name="next-steps"></a>Seuraavat vaiheet
Nyt kun sinulla on Power BI Desktop asennettuna, voit aloittaa Power BI -raporttien luomisen.

[Pikaopas: Power BI -raportin luominen Power BI -raporttipalvelimeen](quickstart-create-powerbi-report.md)  
[Aloita Power BI Desktopin käyttö](../desktop-getting-started.md)  
Ohjattu oppiminen: [Power BI Desktopin käytön aloittaminen](../guided-learning/gettingdata.yml#step-2)  
[Yleiskatsaus käyttöoppaasta, Power BI -raporttipalvelin](user-handbook-overview.md)

Onko sinulla muuta kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
