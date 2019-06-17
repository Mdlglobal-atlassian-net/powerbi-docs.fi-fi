---
title: Yhteyden muodostaminen AT Internet Bridgeen Power BI:n avulla
description: AT Internet Bridge for Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 41b390190f8ce3c071f790edcdf86f0e3bd4a0c2
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721314"
---
# <a name="connect-to-at-internet-bridge-with-power-bi"></a>Yhteyden muodostaminen AT Internet Bridgeen Power BI:n avulla
AT Internetin ja sen digitaalisen Analytics Suite -analyysialustan avulla voit poimia tiedoistasi välittömän arvon. Power BI:lle kehitetty AT Internet Bridge -sisältöpaketti sisältää tietoja, jotka koskevat sivuston vierailuja, lähteitä, lokalisointia ja laitteita.

Yhteyden muodostaminen [AT Internet Bridge -sisältöpakettiin](https://app.powerbi.com/getdata/services/at-internet-bridge) Power BI:ssä.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-at-internet/pbi_getdata.png) 
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-at-internet/pbi_getservices.png) 
3. Valitse **AT Internet Bridge** \> **Hanki**.
   
   ![](media/service-connect-to-at-internet/atinternet.png)
4. Määritä AT Internet -sivuston numero, johon haluat muodostaa yhteyden.
   
   ![](media/service-connect-to-at-internet/params.png)
5. Valitse **Perus**-todennusmekanismi, kirjoita AT Internet -käyttäjänimesi ja -salasanasi ja valitse **Kirjaudu sisään**.
   
   ![](media/service-connect-to-at-internet/creds.png)
6. Aloita tuontiprosessi valitsemalla **Yhdistä**. Kun kaikki on valmista, uusi raporttinäkymä, raportti ja malli näkyvät siirtymisruudussa. Voit tarkastella tuotuja tietoja valitsemalla raporttinäkymän.
   
    ![](media/service-connect-to-at-internet/atinternet.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Tämä sisältöpaketti sisältää viimeisen 45 päivän tiedot seuraavista taulukoista:  

    - Muunto  
    - Laitteet  
    - Lokalisointi  
    - lähteet  
    - Vierailujen kokonaismäärä  

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

