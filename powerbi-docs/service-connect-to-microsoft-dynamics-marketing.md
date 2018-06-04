---
title: Yhteyden muodostaminen Microsoft Dynamics Marketingiin Power BI:n avulla
description: Microsoft Dynamics Marketing Power BI:lle
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 059f842dae35fa7a46094d0ade990df7514908d6
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815284"
---
# <a name="connect-to-microsoft-dynamics-marketing-with-power-bi"></a>Yhteyden muodostaminen Microsoft Dynamics Marketingiin Power BI:n avulla
Microsoft Dynamics Marketingin Power BI -sisältöpaketin avulla voit helposti käyttää ja analysoida tietojasi Dynamics Marketingista. Sisältöpaketti hyödyntää OData-syötteen päällä kuvaavaa mallia, joka sisältää kaikki kohteet ja mittarit, kuten ohjelmat, kampanjat, markkinoinnin yhteyshenkilöt ja yritykset, liidit, liidien vuorovaikutukset ja liidien pisteyttämisen, sähköpostimarkkinoinnin viestit ja verkkosivustot, havainnot käyttäytymisestä, budjetit, kirjanpitotapahtumat, suorituskykyilmaisimet jne. 

Muodosta yhteys Power BI:lle tarkoitettuun [Dynamics Marketing -sisältöpakettiin](https://app.powerbi.com/getdata/services/microsoft-dynamics-marketing).

>[!NOTE]
>Sinun on määritettävä kelvollinen OData-URL-osoite Dynamics Marketingin esiintymää varten (sisältöpaketti ei toimi paikallisen CRM-version kanssa). Lisävaatimukset ovat alla.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa Nouda tiedot.
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_getservices.png) 
3. Valitse **Microsoft Dynamics Marketing** \> **Nouda**.
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/mdmarketing.png)
4. Anna tiliisi liitetty OData-URL-osoite.  Se on muodossa "https://[esiintymä\_nimi].marketing.dynamics.com/analytics."
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynmktgserviceurl.png)
5. Anna tunnistetietosi, kun niitä pyydetään (tämän vaiheen voi ohittaa, jos olet jo kirjautunut sisään selaimellasi). Kirjoita todentamismenetelmäksi **oAuth2** ja valitse **Kirjaudu sisään**:
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynammktgoauth2.png)
6. Kun yhteys on muodostettu, näet Dynamics Marketingin koontinäytön, joka on päivitetty tiedoillasi. Keltaiset tähtikertomerkit vasemmassa siirtymisruudussa osoittavat uudet kohteet.
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynammktgnewdash.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä koontinäytön yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana.

## <a name="system-requirements"></a>Järjestelmävaatimukset
* Sinun on määritettävä kelvollinen OData-URL-osoite Dynamics Marketingin esiintymää varten (sisältöpaketti ei toimi paikallisen CRM-version kanssa).  
* Järjestelmänvalvojan on otettava käyttöön OData-päätepiste sivuston asetuksissa. OData-päätepisteen osoite löytyy siirtymällä **Organisaation tietopalvelu** -osaan ja valitsemalla **Aloitus \> Asetukset \> Sivuston asetukset**.  OData-URL-osoitteen muoto on: https://[esiintymä\_nimi].marketing.dynamics.com/analytics  
* Käyttäjätilin/käyttäjätietojen, joilla käytät Microsoft Dynamics Marketingia, on oltava samat kuin joilla olet rekisteröitynyt Power BI:n käyttäjäksi. Kun kirjaudut sisään Microsoft Dynamics Marketingiin, sinut kirjataan sisään automaattisesti samoilla käyttäjätiedoilla kuin Power BI:ssä. Jos haluat kirjautua sisään Microsoft Dynamics Marketingiin toisella tilillä, rekisteröidy Power BI:n käyttäjäksi tällä kyseisellä tilillä. Toivomme voivamme ratkaista tämän ongelman tulevassa julkaisuversiossa.   

## <a name="troubleshooting"></a>Vianmääritys
Jos saat Kirjautuminen epäonnistui -ilmoituksen, kun yrität muodostaa yhteyttä Dynamics CRM -tiliisi, varmista että olet kirjautumassa sisään Power BI:hin samalla tilillä, jolla käytät CRM Online OData -syötettä. Kokeile kirjautua syötteeseen myös selaimellasi.

Pyydä järjestelmänvalvojaasi vahvistamaan, että OData-URL-osoite on oikein ja että OData-päätepiste on käytössä.

Tarkista käyttämäsi Dynamics Marketing -versio. Versioihin 18.0 ja 18.1 tehtiin lisäkorjauksia, joten jos edelleen havaitset ongelmia ja käytät vanhempaa versiota, harkitse päivittämistä uudempaan.

Jos ongelmat jatkuvat, ota yhteyttä Power BI:n tiimiin tekemällä tukipalvelupyyntö:

* Valitse Power BI -sovelluksessa kysymysmerkki \> **Ota yhteyttä tukeen**.
* Valitse Power BI:n tukisivustossa (jossa luet tämän artikkelin) sivun oikealla puolella **Ota yhteyttä tukeen**.

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietojen noutaminen Power BI:hin](service-get-data.md)

[Power BI:n käytön aloittaminen](service-get-started.md)
