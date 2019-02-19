---
title: Asenna Power BI -raporttipalvelimelle optimoitu Power BI Desktop
description: Opi asentamaan Power BI -raporttipalvelimelle optimoitu Power BI Desktop
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/24/2019
ms.openlocfilehash: 7abf679c663f9c71c277c74960fe65c9aee6568d
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/16/2019
ms.locfileid: "56324963"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Asenna Power BI -raporttipalvelimelle optimoitu Power BI Desktop

Opi asentamaan Power BI -raporttipalvelimelle optimoitu Power BI Desktop.

Jotta voit luoda Power BI -raportteja Power BI -raporttipalvelimelle, sinun on ladattava ja asennettava Power BI -raporttipalvelimelle optimoitu Power BI Desktop. Tämä versio on erilainen kuin Power BI -palvelun kanssa käytettävä Power BI Desktop. Power BI Desktopin versio Power BI -palvelulle sisältää esimerkiksi esiversio-ominaisuuksia, joita Power BI -raporttipalvelinversiossa ei ole ennen niiden julkaisua. Käyttämällä tätä versiota varmistetaan, että raporttipalvelin voi käsitellä raporttien ja mallin tunnettua versiota. 

Onneksi voit asentaa Power BI Desktopin ja Power BI -raporttipalvelimelle optimoidun Power BI Desktopin rinnakkain samalle tietokoneelle.

## <a name="download-and-install-power-bi-desktop"></a>Power BI Desktopin lataaminen ja asentaminen

Helpoin tapa varmistaa, että sinulla on Power BI -raporttipalvelimelle optimoidun Power BI Desktopin uusin versio, on aloittaa raporttipalvelimesi verkkoportaalista.

1. Valitse raporttipalvelimen verkkoportaalissa **Lataa**-nuoli > **Power BI Desktop**.

    ![Lataa Power BI Desktop verkkoportaalista](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Voit myös siirtyä suoraan kohtaan [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=2055039) (optimoitu Power BI -raporttipalvelimelle – tammikuu 2019) Microsoft Download Centerissä.

2. Valitse Download Center -sivulla **Lataa**.

3. Tietokoneestasi riippuen valitse: 

    - **PBIDesktopRS.msi** (32-bittinen versio) tai

    - **PBIDesktopRS_x64.msi** (64-bittinen versio).

1. Kun olet ladannut asennusohjelman, suorita Power BI Desktopin (tammikuu 2019) ohjattu asennus.

2. Asennuksen lopussa valitse **Käynnistä Power BI Desktop nyt**.

    Se käynnistyy automaattisesti ja on valmiina käyttöön.

## <a name="verify-youre-using-the-correct-version"></a>Varmista, että käytät oikeaa versiota
Oikean Power BI Desktop -version varmistaminen on helppoa: vilkaise Power BI Desktopin käynnistysruutua tai otsikkoriviä. Otsikkorivi ilmaisee version julkaisukuukauden ja -vuoden. Myös Power BI -logon värit ovat päinvastaiset: keltaista mustalla taustalla eikä päinvastoin.

![Power BI -raporttipalvelimelle optimoidun Power BI Desktopin otsikkorivi](media/install-powerbi-desktop/power-bi-report-server-desktop-jan-2019.png)

Power BI -palvelun Power BI Desktop -versiossa ei ole kuukautta ja vuotta otsikkorivillä.

## <a name="file-extension-association"></a>Tiedostotunnisteen kytkentä
Jos asennat sekä Power BI Desktopin että Power BI -raporttipalvelimelle optimoidun Power BI Desktopin samalle koneelle, Power BI Desktopin uusimmassa asennuksessa on tiedostokytkentä .pbix-tiedostoille. Toisin sanoen kun kaksoisnapsautat .pbix-tiedostoa, se avataan viimeksi asennetussa Power BI Desktopissa.

Jos sinulla on Power BI Desktop ja asennat sitten Power BI -raporttipalvelimelle optimoidun Power BI Desktopin, kaikki .pbix-tiedostot avataan oletuksena Power BI -raporttipalvelimelle optimoidussa Power BI Desktopissa. Jos haluat, että .pbix-tiedostot avataan oletusarvoisesti Power BI Desktopissa, asenna [Power BI Desktop uudelleen Microsoft Storesta](http://aka.ms/pbidesktopstore).

Voit myös aina ensin avata sen Power BI Desktopin version, jota haluat käyttää. Ja avata sitten tiedoston Power BI Desktopista.

Power BI -raportin muokkaaminen Power BI -raporttipalvelimesta tai uuden Power BI -raportin luominen verkkoportaalista avaa aina Power BI Desktopin oikean version.

## <a name="considerations-and-limitations"></a>Huomioitavat asiat ja rajoitukset

Power BI -raporttipalvelimen Power BI -raportit Power BI -palvelussa (http://app.powerbi.com), ja Power BI -mobiilisovelluksissa toimivat lähes täsmälleen samoin, mutta jotkut ominaisuudet ovat erilaisia.

### <a name="in-a-browser"></a>Selaimessa

Power BI -raporttipalvelimen raportit tukevat kaikkia visualisointeja, mukaan luettuina seuraavat:

* Mukautetut visualisoinnit

Power BI -raporttipalvelimen raportit eivät tue seuraavia:

* R-visualisoinnit
* ArcGIS-kartat
* Navigointipolut
* Power BI Desktopin esikatselutoiminnot

### <a name="in-the-power-bi-mobile-apps"></a>Power BI -mobiilisovelluksissa

Power BI -raporttipalvelimen raportit tukevat [Power BI -mobiilisovellusten](../consumer/mobile/mobile-apps-for-mobile-devices.md) kaikkia tavallisia toimintoja, mukaan luettuina seuraavat:

* [Puhelimen raporttiasettelu](../desktop-create-phone-report.md): voit optimoida raportin Power BI -mobiilisovelluksia silmällä pitäen. Optimoiduilla raporteilla on matkapuhelimessa erityinen kuvake, ![Puhelimen raporttiasettelun kuvake](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png), sekä asettelu.
  
    ![Puhelimille optimoitu raportti](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

Power BI -raporttipalvelimen raportit eivät tue näitä ominaisuuksia Power BI -mobiilisovelluksissa:

* R-visualisoinnit
* ArcGIS-kartat
* Mukautetut visualisoinnit
* Navigointipolut
* Geo-suodatus tai viivakoodit

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop Power BI -raporttipalvelimen aiempiin versioihin

Jos raporttipalvelimesi on aiempi versio, tarvitset vastaavan version Power BI Desktopista. Tässä on aiempi versio.

- Microsoft Power BI Desktop ([optimoitu Power BI -raporttipalvelimelle – elokuu 2018](https://www.microsoft.com/download/details.aspx?id=57271))

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun sinulla on Power BI Desktop asennettuna, voit aloittaa Power BI -raporttien luomisen.

[Power BI -raportin luominen Power BI -raporttipalvelimeen](quickstart-create-powerbi-report.md)  
[Mikä on Power BI -raporttipalvelin?](get-started.md)

Onko sinulla kysyttävää? [Voit esittää kysymyksiä Power BI -yhteisössä](https://community.powerbi.com/)
