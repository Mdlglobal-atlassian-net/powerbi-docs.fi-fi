---
title: Windowsin kehityskeskukseen yhdistäminen Power BI:n avulla
description: Power BI:n Windowsin kehityskeskus
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 81498dff9c70deaf8135faf244db96509b1cf18d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/29/2019
ms.locfileid: "61163976"
---
# <a name="connect-to-windows-dev-center-with-power-bi"></a>Windowsin kehityskeskukseen yhdistäminen Power BI:n avulla
Tutki ja katsele Windowsin kehityskeskuksen sovelluksen analytiikkatietoja Power BI:ssä Power BI -sisältöpaketin avulla. Tiedot päivitetään automaattisesti kerran päivässä.

Yhdistä Power BI:n [Windowsin kehityskeskuksen sisältöpakettiin](https://app.powerbi.com/getdata/services/devcenter).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-windows-dev-center/getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-windows-dev-center/services.png)
3. Valitse **Windowsin kehityskeskus** \>  **Nouda**.
   
   ![](media/service-connect-to-windows-dev-center/windowsdev.png)
4. Anna omistamasi sovelluksen sovellustunnus ja napsauta Seuraava. Alla on lisätietoja [näiden parametrien etsimisestä ](#FindingParams).
   
   ![](media/service-connect-to-windows-dev-center/params.png)
5. Valitse **todennusmenetelmäksi** **oAuth2** \> **Kirjaudu sisään**. Anna pyydettäessä Windowsin kehityskeskuksen tiliisi liitetyt Azure Active Directory -tunnistetiedot (lisätietoja on [järjestelmävaatimuksissa](#Requirements)).
   
    ![](media/service-connect-to-windows-dev-center/creds.png)
   
    ![](media/service-connect-to-windows-dev-center/creds2.png)
6. Tuonti alkaa hyväksymisen jälkeen automaattisesti. Kun tuonti on valmis, uusi koontinäyttö, raportti ja malli näkyvät siirtymisruudussa. Valitse koontinäyttö, jos haluat katsella tuotuja tietoja, ja valitse ruutu, jos haluat siirtyä pohjana oleviin raportteihin.
   
    ![](media/service-connect-to-windows-dev-center/dashboard.png)
   
    ![](media/service-connect-to-windows-dev-center/report.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Kehityskeskuksen Power BI -sisältöpaketti sisältää sovelluksen, lisäosahankintojen, luokitusten, arvostelujen ja sovelluksen kunnon analytiikkatiedot. Tiedot esitetään kolmen edellisen kuukauden ajalta. Lisäksi tiedot esitetään liukuvina keskiarvoina, joten ajanjaksoon sisältyvät päivämäärät päivittyvät sitä mukaa kuin tietojoukko päivittyy.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Järjestelmävaatimukset
Tämä sisältöpaketti edellyttää vähintään yhtä Windows Storeen julkaistua sovellusta ja Windowsin kehityskeskuksen tiliä (lisätietoja on [täällä](https://msdn.microsoft.com/windows/uwp/publish/manage-account-users)).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametrien etsiminen
Voit etsiä sovelluksen sovellustunnuksen sovellustenhallinnan sovelluksen tunnistetietosivulta.

Sovellustunnus on Windows 10 Storen URL-osoitteen lopussa, https://www.microsoft.com/store/apps/ **{applicationId}**

## <a name="next-steps"></a>Seuraavat vaiheet
[Power BI:n käytön aloittaminen](service-get-started.md)

[Tietojen noutaminen Power BI:ssä](service-get-data.md)

