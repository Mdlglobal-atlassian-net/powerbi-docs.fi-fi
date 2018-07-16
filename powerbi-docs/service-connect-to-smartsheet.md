---
title: Yhteyden muodostaminen Smartsheetiin Power BI:llä
description: Smartsheet Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: dfcaabc7f36dd65c6e7dbf56b84778c62760da5d
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135693"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Yhteyden muodostaminen Smartsheetiin Power BI:llä
Smartsheet tarjoaa helpon alustan yhteiskäyttöön ja tiedostojen jakamiseen. Smartsheet-sisältöpaketti Power BI:lle sisältää koontinäytön, raportteja ja tietojoukon, joka näkyy  Smartsheet-tilisi yleiskuvauksessa. Voit käyttää myös [Power BI Desktopia](desktop-connect-to-data.md) yhteyden muodostamiseen tiliisi yksittäisiin laskentataulukoihin. 

Yhdistä Power BI:n [Smartsheet-sisältöpakettiin](https://app.powerbi.com/groups/me/getdata/services/smartsheet).

>[!NOTE]
>Suosittelemme Smartsheet järjestelmänvalvojan tiliä yhdistämään ja lataamaan Power BI -sisältöpaketin, sillä se sisältää lisäoikeuksia.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-smartsheet/pbi_getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-smartsheet/pbi_getservices.png) 
3. Valitse **Smartsheet \> Nouda**.
   
   ![](media/service-connect-to-smartsheet/smartsheet.png)
4. Valitse todennusmenetelmäksi **oAuth2 \>Kirjaudu sisään**.
   
   Anna pyydettäessä Smartsheetin tunnistetiedot ja noudata todennusprosessia.
   
   ![](media/service-connect-to-smartsheet/creds.png)
   
   ![](media/service-connect-to-smartsheet/creds2.png)
5. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Uudet kohteet on merkitty keltaisella tähdellä \*, valitse Smartsheet-merkintä.
   
   ![](media/service-connect-to-smartsheet/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Smartsheet-sisältöpaketti Power BI:lle sisältää yleiskatsauksen Smartsheet-tilistäsi kuten työtiloista, raporteista ja työkirjoista, joita sinulla on, kun niitä muokataan jne. Järjestelmänvalvojan käyttäjät näkevät myös tietoja käyttäjistä omassa järjestelmässään, kuten parhaat taulukoiden laatijat.  

Voit käyttää myös [Power BI Desktopin](desktop-connect-to-data.md) Smartsheet-liitintä yhteyden muodostamiseen tiliisi yksittäisiin taulukoihin.  

## <a name="next-steps"></a>Seuraavat vaiheet:

[Mikä on Power BI?](power-bi-overview.md)

[Tietojen noutaminen Power BI:hin](service-get-data.md)