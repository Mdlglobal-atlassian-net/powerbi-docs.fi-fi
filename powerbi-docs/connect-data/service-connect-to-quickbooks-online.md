---
title: Yhteyden muodostaminen QuickBooks Onlineen Power BI:llä
description: Power BI:n QuickBooks Online
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 4c21c36694f36e4d6f95b8edc920648313dc8a7a
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348501"
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Yhteyden muodostaminen QuickBooks Onlineen Power BI:llä
Kun muodostat yhteyden QuickBooks Onlinen tietoihin Power BI:stä, saat heti Power BI:n koontinäytön ja Power BI:n raportit, jotka antavat merkityksellisiä tietoja muun muassa yrityksesi kassavirrasta, kannattavuudesta ja asiakkaista. Voit käyttää koontinäyttöä ja raportteja sellaisinaan tai mukauttaa niitä, jotta niissä korostuvat itseäsi eniten kiinnostavat tiedot. Tiedot päivitetään automaattisesti kerran päivässä.

Muodosta yhteys [QuickBooks Online -mallisovellukseen](https://dxt.powerbi.com/getdata/services/quickbooks-online) Power BI:tä varten.

>[!NOTE]
>Jos haluat tuoda QuickBooks Online -tietosi Power BI:hin, sinun on oltava järjestelmänvalvoja QuickBooks Online -tilissäsi ja kirjauduttava sisään järjestelmänvalvojan tilin tunnistetiedoilla. Et voi käyttää tätä liitintä QuickBooks Desktop -ohjelmalla. 

## <a name="how-to-connect"></a>Yhteyden muodostaminen

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. Valitse **QuickBooks Online** ja valitse sitten **Nouda**.
   
   ![QuickBooks-haku](media/service-connect-to-quickbooks-online/qbo.png)

4. Valitse **Asennetaanko tämä Power BI -sovellus?** -kohdassa **Asenna**.

    ![QuickBooks-asennus](media/service-connect-to-quickbooks-online/power-bi-install-quickbooks.png)

4. Valitse **Sovellukset**-ruudussa **QuickBooks**-ruutu.

   ![QuickBooks-ruudun valitseminen](media/service-connect-to-quickbooks-online/power-bi-quickbooks-tile.png)

6. Valitse **Aloita uuden sovelluksesi käyttö** -kohdassa **Yhdistä tiedot**.

    ![Aloita uuden sovelluksesi käyttö](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. Valitse todennusmenetelmäksi **oAuth2** ja valitse sitten **Kirjaudu sisään**. 
5. Anna pyydettäessä QuickBooks Onlinen tunnistetietosi ja noudata QuickBooks Onlinen todennusprosessia. Jos olet jo kirjautunut QuickBooks Onlineen selaimessa, tunnistetietoja ei välttämättä pyydetä.
   >[!NOTE]
   >Tarvitset QuickBooks Online -tilisi järjestelmänvalvojan tunnistetiedot.
6. Valitse seuraavassa näytössä yritys, jonka haluat yhdistää Power BI:hin.
   
   ![QuickBooks on lähes valmis](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)

7. Aloita tuontiprosessi valitsemalla seuraavassa ruudussa **Valtuuta**. Tämä prosessi voi kestää muutaman minuutin yrityksen tietojen koon mukaan. 
   
   ![QuickBooks-valtuutus](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
8. Kun Power BI on tuonut tiedot, QuickBooks -sovelluksen sisältöluettelo tulee näkyviin: uusi koontinäyttö, raportti ja tietojoukko.
9. Aloita etsintäprosessi valitsemalla QuickBooks-koontinäyttö. Power BI on luonut automaattisesti tämän koontinäytön tuotujen tietojen näyttämistä varten.

    ![QuickBooks-koontinäyttö](media/service-connect-to-quickbooks-online/power-bi-connect-quickbooks-sample.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](../consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](../create-reports/service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](../consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="troubleshooting"></a>Vianmääritys
**Oho! Havaittiin virhe.**

Jos saat tämän sanoman sen jälkeen kun valitsit **Valtuuta**:

Oho! Havaittiin virhe. Sulje tämä ikkuna ja yritä uudelleen.

Tämä sovellus on jo tilattu toiselle yrityksen käyttäjälle. Voit tehdä muutoksia tähän tilaukseen ottamalla yhteyttä osoitteeseen [järjestelmänvalvojan sähköpostiosoite].

![Oho! Tapahtui virhe](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

... tämä virhe tarkoittaa, että yrityksesi toinen järjestelmänvalvoja on jo yhdistänyt yrityksen tiedot Power BI:hin. Pyydä, että kyseinen järjestelmänvalvoja jakaa koontinäytön kanssasi. Tällä hetkellä vain yksi järjestelmänvalvojakäyttäjä voi yhdistää tietyn QuickBooks Online -yrityksen tietojoukon Power BI:hin. Kun Power BI on luonut koontinäytön, järjestelmänvalvoja voi jakaa sen useille työtovereilleen samoissa Power BI -vuokraajissa.

**"Tätä sovellusta ei ole määritetty sallimaan yhteyksiä maastasi"**

Power BI tukee tällä hetkellä vain QuickBooks Onlinen Yhdysvaltojen versioita. 

![Tätä sovellusta ei ole määritetty sallimaan yhteyksiä maastasi](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](../fundamentals/power-bi-overview.md)

[Power BI -palvelun peruskäsitteitä suunnittelijoille](../fundamentals/service-basic-concepts.md)
