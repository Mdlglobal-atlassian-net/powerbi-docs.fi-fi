---
title: Yhteyden muodostaminen Planview Enterpriseen Power BI:llä
description: Planview Enterprise for Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6095faca7fd0d7d42fd6b3871c9e45658a32a14f
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007725"
---
# <a name="connect-to-planview-enterprise-with-power-bi"></a>Yhteyden muodostaminen Planview Enterpriseen Power BI:llä
Planview Enterprise -sisältöpaketin avulla voit visualisoida resurssien ja työn hallinnan tietoja kokonaan uudella tavalla suoraan Power BI:ssä. Käytä Planview Enterprise-tunnistetietojasi, niin näet vuorovaikutteisesti portfolio-sijoituksesi kulutuksen sekä budjetin ylitykset ja alitukset. Näin saat tietää, kuinka hyvin projektisi kohdistuvat yrityksen strategisiin prioriteetteihin. Voit myös laajentaa valmista raporttinäkymää ja raportteja, jotta saat sinulle tärkeimmät merkitykselliset tiedot.

Yhteyden muodostaminen [Planview Enterprise -sisältöpakettiin Power BI:ssä](https://app.powerbi.com/getdata/services/planview-enterprise)

>[!NOTE]
>Tuodaksesi Planview Enterprise -tietosi Power BI:hin sinun on oltava Planview Enterprise -käyttäjä, jonka roolissa on käytössä Reporting Portal Viewer -ominaisuus. Lisävaatimukset ovat alla.

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
    ![](media/service-connect-to-planview/get.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
    ![](media/service-connect-to-planview/services.png)
3. Valitse Power BI -sivulla **Planview Enterprise** ja valitse sitten **Nouda**:  
    ![](media/service-connect-to-planview/planview.png)
4. Kirjoita Planview Enterprise URL -tekstikenttään sen Planview Enterprise -palvelimen URL-osoite, jota haluat käyttää. Kirjoita Planview Enterprise -tietokannan nimi Planview Enterprise Database -kenttään ja valitse sitten Seuraava.  
    ![](media/service-connect-to-planview/params.png)
5. Valitse Todennusmenetelmä-luettelosta **Perus**, jos se ei jo ole valittuna. Kirjoita tilisi **Käyttäjänimi** ja **Salasana** ja valitse **Kirjaudu sisään**.  
   ![](media/service-connect-to-planview/creds.png)
6. Valitse vasemmanpuoleisessa ruudussa Planview Enterprise raporttinäkymien luettelosta.  
     Power BI tuo Planview Enterprise -tiedot raporttinäkymään. Huomaa, että tietojen lataamiseen voi kulua jonkin aikaa.  
    ![](media/service-connect-to-planview/dashboard.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="system-requirements"></a>Järjestelmävaatimukset
Tuodaksesi Planview Enterprise -tietosi Power BI:hin sinun on oltava Planview Enterprise -käyttäjä, jonka roolissa on käytössä Reporting Portal Viewer -ominaisuus. Lisävaatimukset ovat alla.

Tässä prosessissa oletetaan, että olet jo kirjautunut sisään Microsoft Power BI -aloitussivulla käyttäen Power BI -tiliä. Jos sinulla ei ole Power BI -tiliä, siirry osoitteeseen [powerbi.com](https://powerbi.microsoft.com/get-started/) ja valitse kohdasta **Power BI - Pilviyhteistyö ja -jakaminen** **Kokeile ilmaiseksi**. Valitse sitten **Nouda tiedot**.

## <a name="next-steps"></a>Seuraavat vaiheet:

[Mikä on Power BI?](power-bi-overview.md)

[Tietojen noutaminen Power BI:hin](service-get-data.md)