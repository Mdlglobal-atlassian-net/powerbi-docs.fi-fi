---
title: MailChimpiin yhdistäminen Power BI:n avulla
description: Power BI:n MailChimp
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e4986227b408dfec7ac10a880ff6110aa2ad5b9a
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007667"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>MailChimpiin yhdistäminen Power BI:n avulla
Power BI -sisältöpaketti hakee tietoja MailChimp-tililtäsi ja luo koontinäytön, raportteja ja tietojoukon, joiden avulla voit tutkia tietojasi. Hae analytiikkatietoja, jotta voit luoda [MailChimp-koontinäyttöjä](https://powerbi.microsoft.com/integrations/mailchimp) ja tunnistaa kampanjoihin, raportteihin ja yksittäisiin tilaajiin liittyviä trendejä nopeasti. Tiedot on määritetty päivittymään päivittäin, niin että seuraamasi tiedot ovat varmasti ajan tasalla.

Yhdistä Power BI:n [MailChimp-sisältöpakettiin](https://app.powerbi.com/getdata/services/mailchimp).

## <a name="how-to-connect"></a>Yhteyden muodostaminen
1. Valitse vasemman siirtymisruudun alareunassa **Nouda tiedot**.
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. Valitse **Palvelut**-ruudussa **Nouda**.
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. Valitse **MailChimp** \> **Nouda**.
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. Valitse todennusmenetelmäksi **oAuth2** \> **Kirjaudu sisään**.
   
    Anna pyydettäessä MailChimpin tunnistetiedot ja noudata todennusprosessia.
   
    Kun yhdistät ensimmäisen kerran, sinua pyydetään sallimaan Power BI:lle vain luku -oikeudet tilillesi. Valitse **Salli** aloittaaksesi tuonnin, joka voi kestää muutamia minuutteja sen mukaan, kuinka paljon tililläsi on tietoja.
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. Kun Power BI on tuonut tiedot, näet vasemmassa siirtymisruudussa uuden koontinäytön, raportin ja tietojoukon. Tämä on oletuskoontinäyttö, jonka Power BI on luonut tietojen näyttämistä varten. Voit muokata tätä koontinäyttöä, jotta näet tiedot juuri haluamallasi tavalla.
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**Mitä seuraavaksi?**

* Kokeile [kysymyksen esittämistä raporttinäkymän yläreunassa olevassa Q&A-ruudussa](consumer/end-user-q-and-a.md).
* [Muuta koontinäytön ruutuja](service-dashboard-edit-tile.md).
* [Valitse jokin ruutu](consumer/end-user-tiles.md), jolloin siihen liittyvä raportti avautuu.
* Tietojoukko on ajastettu päivittymään päivittäin, mutta voit muuttaa päivitysaikataulua tai kokeilla tietojoukon päivittämistä **Päivitä nyt** -toiminnolla haluamanasi ajankohtana

## <a name="next-steps"></a>Seuraavat vaiheet
[Mikä on Power BI?](power-bi-overview.md)

[Power BI:n peruskäsitteet](consumer/end-user-basic-concepts.md)

