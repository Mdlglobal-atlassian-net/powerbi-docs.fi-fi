---
title: Raportin luominen SharePoint-luettelosta
description: Tässä opetusohjelmassa kuvataan, kuinka voit muuntaa SharePoint-luettelotietosi Power BI -raportiksi.
author: AdamDWilson
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 11/27/2019
ms.author: adamw
LocalizationGroup: Visualizations
ms.openlocfilehash: a583957cddfc6554aae323624caaa5430038cecf
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/09/2020
ms.locfileid: "75772697"
---
# <a name="create-a-report-on-a-sharepoint-list"></a>Raportin luominen SharePoint-luettelosta

Monet tiimit ja organisaatiot käyttävät SharePoint Onlinen luetteloita tietojen tallentamiseen, koska toiminto on helppo määrittää ja käyttäjät voivat päivittää helposti.  Joskus käyttäjät voivat ymmärtää datan paljon helpommin tutkimalla kaaviota kuin katsomalla itse luetteloa. Tässä opetusohjelmassa kuvaamme, kuinka voit muuntaa SharePoint-luettelotietosi Power BI -raportiksi.

Katso viiden minuutin opetusvideo tai selaa alaspäin, jos haluat tarkastella vaiheittaisia ohjeita.

<iframe width="400" height="450" src="https://www.youtube.com/embed/OZO3x2NF8Ak" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-connect-to-your-sharepoint-list"></a>Osa 1: Yhdistäminen SharePoint-luetteloon

1. Jos sinulla ei vielä ole [Power BI Desktopia](https://powerbi.microsoft.com/desktop/), voit ladata ja asentaa sen.
2. Avaa Power BI Desktop ja valitse sitten valintanauhan Aloitussivu-välilehdessä **Nouda tiedot** > **Lisää**.
3. Valitse **Online-palvelut** ja valitse sitten **SharePoint Online -luettelo**.  

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-getdata.png" alt="get data" width="350"/>

4. Valitse **Muodosta yhteys**.
4. Etsi sen SharePoint Online -sivustosi osoite (eli URL), joka sisältää luettelon.  Saat yleensä sivuston osoitteen SharePoint Onlinen sivulta valitsemalla siirtymispalkista **###Aloitussivu**-vaihtoehdon tai napsauttamalla sivuston kuvaketta sivun yläosassa, minkä jälkeen voit kopioida osoitteen verkkoselaimen osoiteriviltä.

   Katso tämän vaiheen video:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=48&end=90" frameborder="0" allowfullscreen></iframe>

5. Liitä Power BI Desktopissa osoite avoimen valintaikkunan **Sivuston URL** -kenttään.

6. Saatat nähdä seuraavaa kuvaa vastaavan SharePoint-käyttöoikeuksien ruudun.  Jos sitä ei tule näkyviin, siirry vaiheeseen 10.  Jos se tulee näkyviin, valitse sivun vasemmasta reunasta **Microsoft-tili**.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-auth1.png" alt="choose Microsoft account" width="500"/>

7. Valitse **Kirjaudu** ja anna käyttäjätunnus ja salasana, joilla kirjaudut sisään Microsoft Office 365:een.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-auth2.png" alt="sign in" width="500"/>

8. Kun olet kirjautunut sisään, valitse **Yhdistä**.

9. Valitse siirtymistoiminnon vasemmassa reunassa sen SharePoint-luettelon vieressä oleva valintaruutu, johon haluat muodostaa yhteyden.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-select-list.png" alt="get data" width="450"/>

10. Valitse **Lataa**.  Power BI lataa luettelotiedot uuteen raporttiin.

## <a name="part-2-create-a-report"></a>Osa 2: Luo raportti

1. Valitse vasemmalla reunalla **Data**-kuvake, niin huomaat, että SharePoint-luettelon tiedot on ladattu.

2. Varmista, että numeroita sisältävissä luettelon sarakkeissa on Summa- tai Sigma-kuvake oikean reunan **Kentät-ruudussa**.  Jos sitä ei jossakin sarakkeessa ole, valitse taulukkonäkymässä sarakkeen otsikko, valitse **Mallinnus**-välilehti ja vaihda sitten **Tietotyyppi**-kohdan arvoksi **Desimaaliluku** tai **Kokonaisluku** sen mukaan, millaisia tiedot ovat.  Jos sinua pyydetään vahvistamaan muutos, valitse **Kyllä**.  Jos numero on erikoismuotoa, kuten valuutta, voit valita sen myös määrittämällä **Muoto**-asetuksen.

   Katso tämän vaiheen video:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=147&end=204" frameborder="0" allowfullscreen></iframe>

3. Valitse vasemmalla puolella **Raportti**-kuvake.
4. Valitse visualisointiin haluamasi sarakkeet valitsemalla niiden vieressä oleva valintaruutu **Kentät**-ruudussa oikealla.

   Katso tämän vaiheen video:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=215&end=252" frameborder="0" allowfullscreen></iframe>

5. Vaihda tarvittaessa visualisointityyppiä.
6. Voit luoda useita visualisointeja samassa raportissa poistamalla aiemman visualisoinnin ja valitsemalla sitten muiden sarakkeiden valintaruudut **Kentät**-ruudussa.
7. Tallenna raportti valitsemalla **Tallenna**.
