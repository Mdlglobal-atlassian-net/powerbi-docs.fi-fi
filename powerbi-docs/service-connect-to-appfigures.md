---
title: appFiguresien yhdistäminen Power BI:n avulla
description: appFigures Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 7990cdbc0741e80bf2cbb60431228ff6a1d41485
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34243818"
---
# <a name="connect-to-appfigures-with-power-bi"></a>appFiguresien yhdistäminen Power BI:n avulla
Sovelluksia koskevien tärkeiden tilastotietojen seuraaminen on helppoa Power BI:n ja appFigures-sisältöpaketin avulla. Power BI noutaa tiedot, esimerkiksi sovellusmyynnin, lataukset ja mainostilastot ja laatii sitten oletuskoontinäytön ja siihen liittyvät raportit kyseisten tietojen perusteella.

Muodosta yhteys [appFigures-sisältöpakettiin](https://app.powerbi.com/getdata/services/appfigures) tai lue lisää [appFiguresin integroinnista](https://powerbi.microsoft.com/integrations/appfigures) Power BI:hin.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
   ![](media/service-connect-to-appfigures/pbi_getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-appfigures/pbi_getservices.png)
3. Valitse **appFigures** \> **Nouda**.  
   
   ![](media/service-connect-to-appfigures/appfigures.png)
4. Valitse **todennusmenetelmäksi** **oAuth2** \> **Kirjaudu sisään**. Anna pyydettäessä appFiguresin tunnistetiedot ja noudata todennusprosessia.
   
   Ensimmäisen kerran, kun muodostat yhteyden, Power BI kysyy, haluatko sallia vain luku -käyttöoikeudet tiliisi. Aloita tuontiprosessi valitsemalla **Salli**. Tämä voi kestää muutamia minuutteja riippuen siitä, kuinka paljon tililläsi on tietoja.
   
   ![](media/service-connect-to-appfigures/appfiguresdoc_06.png)
5. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Uudet kohteet on merkitty keltaisella tähdellä \*:
   
    ![](media/service-connect-to-appfigures/pbi_appfigures3.png)
6. Valitse appFigures-koontinäyttö. Tämä on oletuskoontinäyttö, jonka Power BI on luonut tietojesi näyttämistä varten. Voit muokata tätä koontinäyttöä, jotta näet tiedot juuri haluamallasi tavalla.
   
    ![](media/service-connect-to-appfigures/appfiguresdoc_01.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](power-bi-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](service-dashboard-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="whats-included"></a>Paketin sisältö
Seuraavat tiedot ovat käytettävissä appFiguresista Power BI:ssä:

| **Taulukon nimi** | **Kuvaus** |
| --- | --- |
| Maat |Tämä taulukko antaa tietoja maan nimestä. |
| Päivämäärät |Tämä taulukko sisältää päivämääriä tästä päivästä taaksepäin niiden sovellusten aikaisimpaan julkaisupäivään, jotka ovat aktiivisia ja näkyvissä  appFigures-tililläsi. |
| Tapahtumat |Tämä taulukko sisältää lataus-, myynti- ja mainostietoja kullekin sovellukselle, maittain ja päivittäin. Huomaa, että sekä sovelluksen että sovelluksen sisäiset ostotiedot ovat kaikki yhdessä taulukossa – voit käyttää <strong>Tyyppi</strong>-saraketta niiden erottamiseen. |
| Inapps |Tämä taulukko sisältää sovelluksen sisäisistä ostotietoja, jotka on liitetty appFigures-tililläsi oleviin aktiivisiin, näkyviin sovelluksiin. |
| Tuotteet |Tämä taulukko sisältää tietoa eri sovelluksista, jotka on liitetty appFigures-tililläsi oleviin aktiivisiin, näkyviin sovelluksiin. |

## <a name="troubleshooting"></a>Vianmääritys
Jos tietoja jostakin sovelluksesta ei ole näkyvissä Power BI:ssa tarkista, että kyseiset sovellukset ovat näkyvissä ja aktiivisina appFigures-sivun **Sovellukset**-välilehdessä.

![](media/service-connect-to-appfigures/appfiguresdoc_11.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Power BI:n käytön aloittaminen](service-get-started.md)
* [Tietojen noutaminen Power BI:ssä](service-get-data.md)
