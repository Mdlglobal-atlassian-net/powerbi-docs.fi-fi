---
title: Yhteyden muodostaminen Projectplaceen Power BI:ssä
description: Projectplace Power BI:lle
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 8827f7dc500ff23e69577ac67b43480d8633f5ef
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721264"
---
# <a name="connect-to-projectplace-by-planview-with-power-bi"></a>Yhteyden muodostaminen Planview Projectplaceen Power BI:ssä
Planview Projectplace -sisältöpaketin avulla voit visualisoida yhteistyöprojektitietosi kokonaan uusilla tavoilla suoraan Power BI:ssä. Tarkastele Projectplace-kirjautumisen tunnistetietojesi avulla vuorovaikutteisesti projektin tärkeitä tilastotietoja, selvitä aktiivisimmat ja tuottavimmat ryhmänjäsenesi ja tunnista riskialttiit kohteet ja toimet Projectplace-tilisi projekteissa. Voit myös laajentaa valmista koontinäyttöä ja raportteja, jotta saat sinulle tärkeimmät merkitykselliset tiedot.

[Yhteyden muodostaminen Projectplace-sisältöpakettiin Power BI:ssä](https://app.powerbi.com/getdata/services/projectplace)

>[!NOTE]
>Projectplace-tietojen tuominen Power BI:hin edellyttää, että olet Projectplace-käyttäjä. Lisävaatimukset ovat alla.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
    ![](media/service-connect-to-projectplace/get.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
    ![](media/service-connect-to-projectplace/services.png)
3. Valitse Power BI -sivulla **Planview Projectplace** ja valitse sitten **Nouda**:  
   
    ![](media/service-connect-to-projectplace/projectplace.png)
4. Kirjoita OData-syötteen URL-osoite -ruutuun käytettävän Projectplace OData -syötteen URL-osoite seuraavassa kuvassa esitetyllä tavalla:
   
    ![](media/service-connect-to-projectplace/params.png)
5. Valitse Todennusmenetelmä-luettelosta **OAuth**, jos se ei jo ole valittuna. Valitse **Kirjaudu sisään** ja noudata kirjautumisohjeita.  
   
   ![](media/service-connect-to-projectplace/creds.png)
6. Valitse vasemmanpuoleisessa ruudussa **Projectplace** koontinäyttöjen luettelosta. Power BI tuo Projectplace-tiedot koontinäyttöön. Huomaa, että tietojen lataamiseen voi kulua jonkin aikaa.  
   
    Koontinäyttö sisältää ruutuja, jotka näyttävät Projectplace-tietokannan tiedot. Seuraavassa kuvassa on esimerkki oletusarvoisesta Projectplace-koontinäytöstä Power BI:ssä.
   
    ![](media/service-connect-to-projectplace/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements"></a>Järjestelmävaatimukset
Projectplace-tietojen tuominen Power BI:hin edellyttää, että olet Projectplace-käyttäjä. Tässä prosessissa oletetaan, että olet jo kirjautunut sisään Microsoft Power BI -aloitussivulla käyttäen Power BI -tiliä. Jos sinulla ei ole Power BI -tiliä, siirry osoitteeseen [powerbi.com](https://powerbi.microsoft.com/get-started/) ja valitse kohdasta **Power BI - Pilviyhteistyö ja -jakaminen** **Kokeile ilmaiseksi**. Valitse sitten **Nouda tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Power BI -palvelun peruskäsitteitä suunnittelijoille](service-basic-concepts.md)

