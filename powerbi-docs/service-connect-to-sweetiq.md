---
title: Yhteyden muodostaminen SweetIQ:iin Power BI:llä
description: SweetIQ Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 665640596dba13dbd444b7a3f98b677380300d29
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/30/2019
ms.locfileid: "73060481"
---
# <a name="connect-to-sweetiq-with-power-bi"></a>Yhteyden muodostaminen SweetIQ:iin Power BI:llä
Power BI -sisältöpaketti hakee tietoja SweetIQ-tililtäsi ja luo valmiita sisältösarjoja, joiden avulla voit helposti tarkastella tietojasi. SweetIQ-sisältöpaketin avulla voit analysoida tietoja sijainnista, luetteloista, luokituksista ja arvioista. Tiedot on määritetty päivittymään päivittäin, niin että seuraamasi tiedot ovat varmasti ajan tasalla.

Muodosta yhteys [SweetIQ-sisältöpakettiin](https://app.powerbi.com/groups/me/getdata/services/sweetiq) Power BI:lle.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemmassa siirtymisruudussa **Nouda tiedot.**
   
    ![](media/service-connect-to-sweetiq/getdata.png)
2. Valitse **SweetIQ** ja napsauta **Nouda.**
   
    ![](media/service-connect-to-sweetiq/sweetiq.png)
3. Anna SweetIQ-asiakastunnus. Tämä on yleensä aakkosnumeerinen arvo. Lisätietoja arvon löytämisestä on alla.
   
    ![](media/service-connect-to-sweetiq/parameter.png)
4. Valitse **Avain**-todennustyyppi ja anna oma Sweet IQ API -avaimesi. Tämä on yleensä aakkosnumeerinen arvo. Lisätietoja arvon löytämisestä on alla.
   
    ![](media/service-connect-to-sweetiq/credentials.png)
5. Power BI aloittaa tietojesi lataamisen, mikä saattaa kestää jonkin aikaa tilisi tietojen koon mukaan: Kun lataus on valmis, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon.
   
    ![](media/service-connect-to-sweetiq/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="finding-parameters"></a>Parametrien löytäminen
Tämä Asiakastunnus ja API-avain tälle sisältöpaketille ei ole sama kuin SweetIQ-käyttäjänimi ja salasana.

Valitse Asiakastunnus yhdelle asiakkaalle, jolle tililläsi on pääsy. Voit hakea asiakasluettelon kohdasta ”Asiakashallinta” SweetIQ-tililtäsi.

Ota yhteyttä järjestelmänvalvojaan API-avaimesi saamiseksi tietyn asiakkaan tietoihin.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](fundamentals/power-bi-overview.md)

[Tietojen noutaminen Power BI:hin](service-get-data.md)

