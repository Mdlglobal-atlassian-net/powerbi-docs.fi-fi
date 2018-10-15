---
title: Yhteyden muodostaminen Office365Moniin Power BI:n avulla
description: Office365Mon Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e823492c98a5386dcbb0aa842140af540b80b2ef
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/21/2018
ms.locfileid: "46549663"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Yhteyden muodostaminen Office365Moniin Power BI:n avulla
Office 365:n käyttökatkosten ja kunnon suorituskyvyn tietojen analysoiminen on helppoa Power BI:n ja Office365Mon-sisältöpaketin avulla. Power BI noutaa tiedot myös käyttökatkoksista ja kunnosta ja luo niiden pohjalta valmiin koontinäytön ja raportit.

Muodosta yhteys [Office365Mon-sisältöpakettiin](https://app.powerbi.com/groups/me/getdata/services/office365mon) Power BI:lle.

>[!NOTE]
>Office365Mon-järjestelmänvalvojatiliä tarvitaan yhteyden muodostamiseen Power BI-sisältöpakettiin ja lataamiseen.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. Valitse **Office365Mon** \> **Nouda**.
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. Valitse todennusmenetelmäksi **oAuth2**\>**Kirjaudu sisään**.
   
   Anna pyydettäessä Office365Monin tunnistetiedot ja noudata todennusprosessia.
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Uudet kohteet on merkitty keltaisella tähdellä \*, valitse Office365Mon-merkintä.
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="troubleshooting"></a>Vianmääritys
Jos saat  **”kirjautuminen epäonnistui”**-virheilmoituksen, kun olet käyttänyt Office365Mon-tilauksen tunnistetietojasi kirjautumiseen, käyttämälläsi tilillä ei ole oikeutta hakea Office365Mon-tietoja tililtäsi. Varmista, että kyseessä on järjestelmänvalvojatili ja yritä uudelleen.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Tietojen noutaminen Power BI:hin](service-get-data.md)

