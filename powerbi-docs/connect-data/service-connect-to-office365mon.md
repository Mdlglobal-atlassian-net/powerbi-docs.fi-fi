---
title: Yhteyden muodostaminen Office365Moniin Power BI:n avulla
description: Office365Mon Power BI:lle
author: paulinbar
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 11/26/2019
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 0ea51e76e9637c78b4f8e18f8a38b35e29f00eee
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83337439"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Yhteyden muodostaminen Office365Moniin Power BI:n avulla
Office 365:n käyttökatkosten ja kunnon suorituskyvyn tietojen analysoiminen on helppoa Power BI:n ja Office365Mon-mallisovelluksen avulla. Power BI noutaa tiedot myös käyttökatkoksista ja kunnosta ja luo niiden pohjalta valmiin koontinäytön ja raportit.

Muodosta yhteys [Office365Mon-mallisovellukseen](https://msit.powerbi.com/groups/me/getapps/services/office365mon.office365mon_powerbi_v3) Power BI:lle.

>[!NOTE]
>Office365Mon-järjestelmänvalvojatiliä tarvitaan yhteyden muodostamiseen Power BI -mallisovellukseen ja sen lataamiseen.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse siirtymisruudun alareunasta **Nouda tiedot**.
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. Valitse **Office365Mon** \> **Hae**.
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. Valitse todennusmenetelmäksi **oAuth2** \> **Kirjaudu sisään**.
   
   Anna pyydettäessä Office365Monin tunnistetiedot ja noudata todennusprosessia.
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. Kun Power BI on tuonut tiedot, näet siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Uudet kohteet on merkitty keltaisella tähdellä \*, valitse Office365Mon-merkintä.
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](../consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](../create-reports/service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](../consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="troubleshooting"></a>Vianmääritys
Jos saat  **”kirjautuminen epäonnistui”** -virheilmoituksen, kun olet käyttänyt Office365Mon-tilauksen tunnistetietojasi kirjautumiseen, käyttämälläsi tilillä ei ole oikeutta hakea Office365Mon-tietoja tililtäsi. Varmista, että kyseessä on järjestelmänvalvojatili ja yritä uudelleen.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](../fundamentals/power-bi-overview.md)

[Tietojen noutaminen Power BI:hin](service-get-data.md)
